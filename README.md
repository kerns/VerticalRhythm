# Vertical Rhythm

A Sass mixin that abstracts the maths involved in applying vertical rhythms with CSS.

## Usage

	// Custom variables. These are the defaults.
	$font-size: 1em;
	$line-height: 1.5em;

	// Link to the mixin.
	@import "library/vertical-rhythm";

	// Parameters: baseline($grid, $behind);
	@include baseline(true);

Then, for each element you want to apply to the vertical rhythm:

	h1 {
		// Parameters: vertical-rhythm($font-size, $lines);
		@include vertical-rhythm(3, 2);
	}

The first parameter specifies the font size you want the element to be, relative to `$font-size`. The second paramater specifies how many lines of the vertical rhythm you would like an element use as its line height. By specifying these values, the mixin calculates the appropriate values for `line-height` and `margin-bottom`.

For exampe, you might want paragraph text to be the default font-size and the same line-height as the vertical rhythm.

	p {
		@include vertical-rhythm(1, 1);
	}

### Notes

This mixin currently only works with `em` measurements.