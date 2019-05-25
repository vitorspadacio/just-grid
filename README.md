<img src="https://i.imgur.com/VaCjbQ2.png" width="200" alt="Just logo">

## Simple grids with flexbox

Just is a simple and straightforward SASS library that uses ```flex```box and can be customized as you want.

## Requirement

- SASS 3.4+

## Links

- [Installation](#installation)
- [Using](#using)
- [Gaps and customization](#gaps-and-customization)
- [Responsiveness](#responsiveness)

# Installation

1. Install Just from npm

```
npm install just-grid --dev
```

2. Import Just in your SASS main file

```scss
@import "just";
```

# Using

Just is simples, consist in three types of mixin: row, column and media.

```scss
.container {
    @include row();
}
```

Means the setup of a row and defines this element with ```display: flex```.

```scss
.column {
    @include column(1);
}
```

With this you defined a ```1 of 12``` column, using default ```settings```.

You can pass how many columns you expect to ```column``` mixin, like this:

```scss
@include column(1 of 3);
```

This change the default ```12``` columns to ```3```.
You can use just the number too, and the mixin will assume the default ```12``` columns.

# Gaps and customization

If you want to change the default ```1rem``` gap or the default ```12``` columns setting, you can override passing a ```map``` to the mixin. The structure is like this:

```scss
$map: (columns: 6, gap: 2rem);
```

This will override the setting that you defines.

```scss
$style: (columns: 6, gap: 2rem);

@include column(2, $style);
```

Can be used like this too.

```scss
@include column(2, (gap: 1.5rem));
```

If you want to change the default for all uses, you can change the ```$just-grid``` variable. You need to respect the default settings and override all of them.

```scss
$just-grid: (
    columns: 12,
    gap: 1rem,
    media: $xl
);
```

- ```columns```: Grid default total columns
- ```gap```: Gap size between columns
- ```media```: Media size to use

# Responsiveness

Using the ```media``` mixin you can set a @media for responsiveness purpose. There is a ton of ways to customize this. First, you can use the default breakpoint variables based in ```Bootstrap``` breakpoint.

```scss
$small-screen: (media: 576px);
$medium-screen: (media: 768px);
$large-screen: (media: 992px);
$xlarge-screen: (media: 1200px);
```

You can access this values by shortname like this.

```scss
$sm: $small-screen;
$md: $medium-screen;
$lg: $large-screen;
$xl: $xlarge-screen;
```

Don't forget, if you want to change this values, change the full name ones, not the shortname.

With this you can define a @media like this.

```scss
.column {
    @include column(1);

    @include media($md) {
        @include column(6);
    }
}
```

Creating a CSS output like this.

```css
.column {
    margin-left: 1rem;
    width: calc(0.083 * 100% - 1rem);

    @media only screen and (min-width: 768px) {
        .column {
            margin-left: 1rem;
            width: calc(0.5 * 100% - 1rem);
        }
    }
}
```

We highly reccomend using mobile-first approach, but, if you want to change the way media is created, you can pass a string like this.

```scss
@include media((media: "(max-width: 900px")) {
    @include column(6);
}
```

And the result will be:

```css
@media (max-width: 900px) {
    .column {
        margin-left: 1rem;
        width: calc(0.5 * 100% - 1rem);
    }
}
```

You can pass multiple settings and for each one will generate a @media with that configuration.

```scss
$custom1: (columns: 12, gap: 1rem, media: $sm);
$custom2: (columns: 6, gap: 2rem, media: $md);
$custom3: (columns: 6, gap: 2rem, media: "(max-width: 1280)");

.column {
    @include media($custom1, $custom2) {
        @include column(6);
    }
}
```

Resulting in:

```css
@media only screen and (min-width: 576px) {
    .column {
        margin-left: 1rem;
        width: calc(0.5 * 100% - 1rem);
    }
}

@media only screen and (min-width: 768px) {
    .column {
        margin-left: 2rem;
        width: calc(1 * 100% - 2rem);
    }
}

@media (max-width: 1280) {
    .column {
        margin-left: 2rem;
        width: calc(1 * 100% - 2rem);
    }
}
```

# About

Just was an idea of flexbox grid using only SASS based in [Neat](https://github.com/thoughtbot/neat) framework from [thoughtbot](https://thoughtbot.com). It's free to use and eager to receive new ideas and critiques.