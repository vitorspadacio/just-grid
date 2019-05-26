<img src="https://i.imgur.com/VaCjbQ2.png" width="200" alt="Just logo">

## Simple grids with flexbox

Just is a simple and straightforward SASS library that uses ```flex```box and can be customized as you want.

## Requirement

- SASS 3.4+

## Links

- [Installation](#installation)
- [Using](#using)
- [Customization](#gaps-and-customization)
- [Wiki](https://github.com/vsp193/just-grid/wiki)
- [About](#about)

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

Just consist in three mixins: [row()](https://github.com/vsp193/just-grid/wiki/row()), [column()](https://github.com/vsp193/just-grid/wiki/column()) and [media()](https://github.com/vsp193/just-grid/wiki/media()).

```scss
.element {
    @include row();
}
```

Means the setup of a row and defines this element with `display: flex`.

```scss
.element {
    @include column(1);
}
```

With this you defined a `1 of 12` column, using default `settings`.

You can pass how many columns you expect to `column` mixin, like this:

```scss
.element {
    @include column(1 of 3);   
}
```

This change the default `12` columns to `3` in this element.

# Customization

If you want to change the default `1rem` gap or the default `12` columns setting, you can override passing a `grid` (a SASS map) to the mixin.

```scss
$style: (columns: 6, gap: 2rem);

@include column(2, $style);
```

For more information visit our [wiki](https://github.com/vsp193/just-grid/wiki).

# About

Just was an idea of flexbox grid using only SASS based in [Neat](https://github.com/thoughtbot/neat) framework from [thoughtbot](https://thoughtbot.com). It's free to use and eager to receive new ideas and critiques.