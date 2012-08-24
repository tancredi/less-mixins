LESS Mixins
==============

A collection of useful mixins I use in my projects

##Utilities

###.sprite (x, y, sprite-img, width, height, spacing)

Use this mixin to handle sprites in a simpler way.

E.g.
```less
.first-piece () {
	.sprite (0, 0, 'path/to/sprite.png', 100px, 100px, 0);
}

.second-piece () {
	.sprite (1, 0, 'path/to/sprite.png', 100px, 100px, 0);
}
```

###.inline-block ()

Polyfill mixin for inline-block display on elements.

E.g.
```less
a.button {
	.inline-block();
}
```

####.Sprite-icon (x, y, sprite-img, width, height, spacing)

Extends `.sprite`, use this mixin to handle icon sprites.
Will apply `.inline-block` and hide text (good to use for span icons with explanatory text for accessibility).

E.g.
```less
.icons-set-small (@id, @status: 0) {
	.sprite-icon(@id, @status, 'path/to/icons-set.png', 18px, 18px, 0);
}

.icon-small-first {
	.icons-set-small(0);

	&:hover {
		.icons-set-small(0, 1);
	}
},

.icon-small-second {
	.icons-set-small(0);

	&:hover {
		.icons-set-small(0, 1);
	}
}
```

###.clearfix ()

Standard clearfix polyfill.

E.g.
```less
.columns-wrapper {
	.clearfix();
}
```

###.hidden ()

Simply applies `display: hidden`, good for readability.

E.g.
```less
.tooltip {
	.hidden();
}
```

###.ellipsis ()

Compatibility polyfill hiding text overflows with `&hellip;`.
Apply a max-width and .inline-block() if needed.

E.g.
```less
span.long-text {
	.inline-block();
	width: 100%;
	.ellipsis();
}
```

###.list ()

Removes list default styling. Useful to keep DRY styles when using list elements.

E.g.
```less
ul.navigation {
	.list()
}
```

##CSS3

###.rounded-corners (radius)

Rounded corners compatibility.

E.g.
```less
.box {
	.rounded-corners(5px);
}
```

###.rounded-corners-custom (top-left, top-right, bottom-right, bottom-left)

Custom rounded corners compatibility.

E.g.
```less
.weird-box {
	.rounded-corners-custom(2px, 5px, 1px);
}
```

###.shadow (x, y, blur, spread, color)

Box shadow corners compatibility.

E.g.
```less
.button {
	.shadow(0, 1px, 1px, 0, fade(#000, 5%));
}
```

###.inner-shadow (x, y, blur, spread, color)

Same as `.shadow`, but inset. Good for readability.

E.g.
```less
.button {
	.inner-shadow(0, 1px, 0, 0, fade(#fff, 20%));
}
```

###.multi-shadow (shadow-1, shadow-2, shadow-3, shadow-4, shadow-5)

Multiple shadows. Falls back to single one if missing compatibility.

E.g.
```less
.button {
	.multi-shadow(0 1px 0 0 fade(#ff, 20%) inset, 0 1px 1px 0 fade(#000, 20%));
}
```

###.no-shadow ()

Shadow reset. Sometimes you'll have no choice but overwriting.

E.g.
```less
.button.plain {
	.no-shadow();
}
```

###.transition (property, time, easing)

Transition compatibility mixin. Quiet straight forward

E.g.
```less
a.fancy {
	.transition(color, .1s);
}
```

###.vertical-gradient (start-color, stop-color)

Vertical gradient background compatibility mixin. Will falloff on calculated color.

E.g.
```less
a.button {
	.vertical-gradient(#555, #222);
}
```

###.opacity (alpha)

Compatibility mixin for opacity.

E.g.
```less
.overlay {
	.opacity(0.5);
}
```

##Typography

Note: `typography.less` will set `font-size: 62.5%;` to `html`. This is required in order to make px measures match with REMs.
Using this set of mixins will be useful if you want to use REMs to define typographic rules.
Every value set in these mixins params will be translated to REMs matched and falling back to pixels.

###.type-size (size)

Applies safe REM font-size.

E.g.
```less
h1 {
	.type-size(20); // This will appear as 20px text, and be defined in REMs with px fallback
}
```

###.type-padding (value-top, value-bottom)

Applies safe Rem padding top and bottom.

E.g.
```less
ul, ol {
	.type-padding(15, 15);
}
```

###.type-padding-top (value)

Applies safe Rem padding-top.

E.g.
```less
ul, ol {
	.type-padding-top(15);
}

###.type-padding-bottom (value)

Applies safe Rem padding-bottom.

E.g.
```less
ul, ol {
	.type-padding-bottom(15);
}

###.type-margin (value-top, value-bottom)

Applies safe Rem padding top and bottom.

E.g.
```less
ul, ol {
	.type-padding(15, 15);
}
```

###.type-margin-top (value)

Applies safe Rem margin-top.

E.g.
```less
ul, ol {
	.type-margin-top(15);
}

###.type-margin-bottom (value)

Applies safe Rem margin-bottom.

E.g.
```less
ul, ol {
	.type-margin-bottom(15);
}




