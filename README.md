I Love You SCSS
===============

❤ ❤ ❤

Installation
============

Download
--------

### Bower

```
bower install ily-scss
```

### GitHub

- Download [zip](https://github.com/turnbullm/ily-scss/archive/v0.1.3.zip) file
- Download [tar.gz](https://github.com/turnbullm/ily-scss/archive/v0.1.3.tar.gz) file

Import into your SCSS
---------------------

Import everything;

```
@import 'ily';
```

Alternatively, import individual utilities as shown below

Utilities
=========

Animation
---------

Sensible defaults for animations

### Installation

```
@import "ily/utilities/animation";
```

### Example usage

```
.animation-fade-in {
  @include ily-animation-in();
  animation-name: fade-in;
}

.animation-fade-out {
  @include ily-animation-out();
  animation-name: fade-out;
}
```

Box sizing
----------

If using global border box reset, this mixin will remove issues with 3rd party widgets (eg: Google Maps)

### Installation

```
@import "ily/utilities/box-sizing";
```

### Example usage

```
.3rd-party-widget {
  @include ily-border-box-reset();
}
```

Font smoothing
--------------

### Installation

```
@import "ily/utilities/font-smoothing";
```

### Example usage

```
.example {
  @include ily-font-smoothing();
}

.example {
  @include ily-font-smoothing-disable();
}
```

Icomoon
-------

Easily embed characters from fonts generated with [IcoMoon](https://icomoon.io/)

Assumes the font family name is 'icomoon'

### Installation

```
@import "ily/utilities/icomoon";
```

### Requirements

- [Font smoothing utility](#font-smoothing)

### Example usage

```
$icon-icomoon-burger: 'x';

.icon-example:before {
  @include ily-icomoon($icon-icomoon-burger);
}
```

#### Using base mixin to reduce CSS output

```
.icon {
  &:before {
    @include ily-icomoon-base();
  }

  &--example-1:before {
    content: $icon-icomoon-arrow-left;
  }

  &--example-2:before {
    content: $icon-icomoon-arrow-right;
  }
}
```

Pixels to em
------------

Convert pixel units to em units

### Installation

```
@import "ily/utilities/px-to-em";
```

### Requirements

- [Strip unit utility](#strip-unit)

### Example usage

```
.example {
  font-size: ily-px-to-em(10px);
  line-height: ily-px-to-em(18px, 10px);

  .inherit {
    font-size: ily-px-to-em(8px, 10px);
    line-height: ily-px-to-em(12px, 8px);
  }
}
```

### Base font size

The default base font size is 16px

This can be changed by altering the `$base-font-size` variable

```
$base-font-size: 18px;

body {
  font-size: $base-font-size;
}
```

Pixels to rem
-------------

Convert pixel units to rem units

### Installation

```
@import "ily/utilities/px-to-rem";
```

### Requirements

- [Strip unit utility](#strip-unit)

### Example usage

Usage is very similar to the [pixels to em utility](#pixels-to-em)

Notice the fallback for browsers without rem support (IE8 and below)

```
$base-font-size: 18px;

body {
  font-size: $base-font-size;
}

.example {
  @include ily-font-size-px-to-rem(16px);

  padding-left: 20px;
  padding-left: ily-px-to-rem(20px);
}
```

Reset
-----

Reset all browser defaults

Useful if using [normalize.css](https://necolas.github.io/normalize.css/), and would like to hard reset specific elements

### Installation

```
@import "ily/utilities/reset";
```

### Example usage

```
.example {
  @include ily-reset();
}
```

Screen reader only
------------------

Element is hidden visually, but readable by screen readers

### Installation

```
@import "ily/utilities/screen-reader-only";
```

### Example usage

```
.example {
  @include ily-screen-reader-only();
}
```

Scroll
------

Easily create scrollable elements

### Installation

```
@import "ily/utilities/scroll";
```

### Example usage

```
.example-1 {
  @import ily-scroll();
}

.example-2 {
  @import ily-scroll-horizontal-only();
}

.example-3 {
  @import ily-scroll-vertical-only();
}
```

Strip unit
----------

Useful function for allowing mixins to accept *any* type of parameter

```
ily-strip-unit(12px) = 12
ily-strip-unit(1.2em) = 1.2
```

### Installation

```
@import "ily/utilities/strip-unit";
```

### Example usage

```
$value: ily-strip-unit($value);
```

Tap highlight
-------------

Touch devices outline taps with a gray box

Disable the effect with this mixin, and handle active states yourself

### Installation

```
@import "ily/utilities/tap-highlight";
```

### Example usage

```
.example {
  @include ily-tap-highlight-disable();

  &:active {
    //...
  }
}
```

### Global usage

```
a,
button,
input,
label,
select,
textarea {
  @include ily-tap-highlight-disable();
}
```

### Javascript

This javascript code will ensure the `:active` selector is fired across all mobile devices

```
document.addEventListener("touchstart", function(){}, true);
```

Vertical align
--------------

Vertically align a block element within its parent

### Installation

```
@import "ily/utilities/vertical-align";
```

### Example usage

```
.example {
  @include ily-vertical-align();
}
```

Variables
=========

Most of these variables are used simply to improve code readability

Breakpoints
-----------

Assumes mobile first and usage with http://breakpoint-sass.com/

Breakpoint values do not exactly match device dimensions, instead they are more of a guideline

Breakpoint values should be adjusted to match each particular design, rather than target specific devices

Device dimension reference: http://www.mydevice.io/devices/

Variable | Value |
--- | --- | ---
$bp-xxs | 360px | Galaxy S4 - S6
$bp-xs | 375px | iPhone 6
$bp-s | 410px | iPhone 6 Plus
$bp-m | 768px | Tablets
$bp-l | 992px | Desktop
$bp-xl | 1200px | Large desktop
$bp-height-xxs | min-height 640px | Galaxy S4
$bp-height-xs | min-height 665px | iPhone 6
$bp-height-s | min-height 735px | iPhone 6 Plus
$bp-height-m | min-height 1024px | Tablets

### Installation

```
@import "ily/vars/bp";
```

Colors
------

Some basic colors, add more with http://name-of-color.com

Variable | Value
--- | ---
$color-black | #000
$color-gray | #bebebe
$color-gray-dark | #a9a9a9
$color-gray-dim | #696969
$color-gray-light | #d3d3d3
$color-white | #fff

### Installation

```
@import "ily/vars/color";
```

### Example usage

It's recommended to use the contents of this file within your own project as a starting point

Font weights
------------

Improve code readability

Variable | Value
--- | ---
$font-weight-thin | 100
$font-weight-extra-light | 200
$font-weight-light | 300
$font-weight-normal | 400
$font-weight-medium | 500
$font-weight-semi-bold | 600
$font-weight-bold | 700
$font-weight-heavy | 800
$font-weight-black | 900

### Installation

```
@import "ily/vars/font-weight";
```

Z Indexes
---------

Improve readability within code, and limit the usage (no `z-index: 99999`!)

Variable | Value
--- | ---
$z-index-lowest | -3
$z-index-lower | -2
$z-index-low | -1
$z-index-standard | 0
$z-index-high | 1
$z-index-higher | 2
$z-index-highest | 3
$z-index-overlay | 4
$z-index-overlay-breakout | 5

### Installation

```
@import "ily/vars/z-index";
```

Style
=====

These are not included by default, but may be useful for your application

Global border box
-----------------

Use if border box sizing is your default site-wide preference 

This may cause issues with 3rd party widgets; see [box sizing utility](#box-sizing)

### Installation

```
@import "ily/style/global-border-box";
```

Global layout
-------------

Adds 100% height to `html` and `body` elements

A common tactic for websites containing full height elements

### Installation

```
@import "ily/style/global-layout";
```

More documentation
==================

- [Publish new version](docs/publish-new-version.md)

Changelog
=========

See [`CHANGELOG.md`](CHANGELOG.md) file

Author
======

[Matthew Turnbull](http://turnbullm.com) <[turnbullm@gmail.com](mailto:turnbullm@gmail.com)>

License
=======

Open sourced under the [MIT license](http://turnbullm.mit-license.org/).
