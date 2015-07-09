I Love You SCSS
===============

❤ ❤ ❤

Installation
============

```
@import 'ily';
```

Utilities
=========

Font smoothing
--------------

```
.font-smoothing {
  @include ily-font-smoothing();
}

.font-smoothing-disable {
  @include ily-font-smoothing-disable();
}
```

Strip unit
----------

```
ily-strip-unit(12px) = 12
ily-strip-unit(1.2em) = 1.2
```

Pixels to em
------------

### Basic usage

```
.example {
  font-size: ily-px-to-em(10px, 18px);
  line-height: ily-px-to-em(18px, 10px);
}
```

### Base font size

```
$base-font-size: 18px;

body {
  font-size: $base-font-size;
}

.example {
  font-size: ily-px-to-em(10px);
  line-height: ily-px-to-em(18px, 10px);

  .inherit {
    font-size: ily-px-to-em(8px, 10px);
    line-height: ily-px-to-em(12px, 8px);
  }
}
```

Pixels to rem
-------------

Notice the fallback for browsers without rem support

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

Icomoon
-------

### Basic usage

```
.icon-example:before {
  @include ily-icomoon($icomoon-example);
}
```


### Using base mixin to reduce CSS output

```
.icon {
  &:before {
    @include ily-icomoon-base();
  }

  &--example-1:before {
    content: $icomoon-example-1;
  }

  &--example-2:before {
    content: $icomoon-example-2;
  }
}
```

Screen reader only
------------------

Element is hidden visually, but readable by screen readers

```
.example {
  @include ily-screen-reader-only();
}
```

Animation
---------

Sensible defaults for animations

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

Variables
=========

Most of these variables are used simply to improve code readability

Breakpoints
-----------

Assumes mobile first and usage with http://breakpoint-sass.com/

Breakpoint values do not exactly match device dimensions, instead they are more of a guideline

Breakpoint values should be adjusted to match each particular design, rather than target specific devices

Device dimension reference: http://www.mydevice.io/devices/

Variable | Value | Comments
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
$color-gray-web | #808080
$color-white | #fff

Font weights
------------

Variable | Value
--- | ---
$font-weight-thin | 100;
$font-weight-extra-light | 200;
$font-weight-light | 300;
$font-weight-normal | 400;
$font-weight-medium | 500;
$font-weight-semi-bold | 600;
$font-weight-bold | 700;
$font-weight-heavy | 800;
$font-weight-black | 900;

Z Indexes
---------

Variable | Value
--- | ---
$z-index-lowest | -3;
$z-index-lower | -2;
$z-index-low | -1;
$z-index-standard | 0;
$z-index-high | 1;
$z-index-higher | 2;
$z-index-highest | 3;
$z-index-overlay | 4;
$z-index-overlay-breakout | 5;

Style
=====

These are not included by default, but may be useful for your application

Global border box
-----------------

Use if border box sizing is your default site-wide preference 

```
@import "ily/style/global-border-box";
```

Global layout
-------------

Adds 100% height to `html` and `body` elements, a common tactic for websites containing full height elements

```
@import "ily/style/global-layout";
```
