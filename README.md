# VerticalRhythm

A Sass module that abstracts the maths involved in applying vertical rhythms with CSS.

## Example

You can the result of the example included [here](http://oliverjash.github.com/VerticalRhythm/).

## Usage

    // Default variables
    $base-font-size: 16px;
    $base-line-height: 1.5;

    // Link to the module
    @import "vertical-rhythm";

    body {
      // Call this mixin every time you change the font-size
      @include establish-baseline();
    }

For each element you want to apply to the vertical rhythm:

    h1 {
        // Parameters: vertical-rhythm($font-size, $lines);
        @include vertical-rhythm(3, 2);
    }

To overlay a baseline ruler:

    body {
      @include debug-vertical-alignment();
    }

The first parameter specifies the font size you want the element to be, relative to `$base-font-size`. The second paramater specifies how many lines of the vertical rhythm you would like an element to use as its line height. By specifying these values, the mixin calculates the appropriate values for `line-height` and `margin-bottom`.

If you want to change the font size at a breakpoint in your design, update the `$base-font-size` variable and re-include the `establish-baseline()` mixin:

    body {
      @include establish-baseline();
      @include debug-vertical-alignment();

      @media screen and (max-width: 500px) {
        $base-font-size: 16px;
        @include establish-baseline();
      }
    }