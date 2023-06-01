
```scss
$col-count: 12
$gutter-width: 20px;

@mixin grid-container() {
	margin-left: auto;
	margin-right: auto;
	max-width: 1200px;
}

@mixin grid-column($columns) {
	width: percent($columns / $column-count);
	float: left;
	padding-left: $gutter-width / 2;
	padding-right: $gutter-width / 2;
}

@mixin clearfix() {
	&:after {
		content: "";
		display: table;
		clear: both
	}
}

.grid-container {
	@include grid-container();
}

@for $i from 1 through $column-count {
	.col-#{$i} {
		@include grid-column($i);
	}
}

.grid-container {
	@include clearfix();
}

$breakpoints: (
	sm: 576px,
	md: 768px,
	lg: 992px,
	xl: 1200px
);

@each $breakpoint, $width in $breakpoints {
	@media (min-width: $width) {
		.grid-container {
			max-width: $width;
		}
	}
}
```

This is how to use the grid system in HTML

```html
<div class="grid-container">
	<div class="col-6">col 1</div>
	<div class="col-6">col 2</div>
</div>
```