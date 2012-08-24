LESS Mixins
==============

A collection of useful mixins I use in my projects

##Utilities

####.Sprite (x, y, sprite-img, width, height, spacing)

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

Compatibility mixin for inline-block display on elements.

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

Simply applying display: hidden, good for readability.

E.g.
```less
.tooltip {
	.hidden();
}
```

###.ellipsis ()

Compatibility polyfill hiding text overflows with `hellip;`.
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

Removes list default styling. Useful to keep DRY styles when using list elements

E.g.
```less
ul.navigation {
	.list()
}
```




