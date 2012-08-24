LESS Mixins
==============

A collection of userful mixins I use in my projects

##Utilities

####.Sprite-icon (x, y, sprite-img, width, height, spacing)

Use this sprite to handle icon sprites.

E.g.
```.icons-set-small (@id, @status: 0) {
	.sprite-icon(@id, @status, 'path/to/sprite.png', 18px, 18px, 0);
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
}```


