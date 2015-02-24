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
  @include ily-font-smoothing;
}

.font-smoothing-disable {
  @include ily-font-smoothing-disable;
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
    @include ily-icomoon-base;
  }

  &--example-1:before {
    content: $icomoon-example-1;
  }

  &--example-2:before {
    content: $icomoon-example-2;
  }
}
```