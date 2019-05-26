# media()

Create a media query based in a grid.

For each grid you can set gap and total columns size and, for each one, will be setted a diferente definition for each media query.

## Arguments

| Name  | Type | Default | Description                       |
| ----- | ---- | :-----: | --------------------------------- |
| $grid | map  | -       | Grid or grids to be used. Each grid should contain `media`. |

## Example

SCSS:

```scss
$custom1: (media: 576px);
$custom2: (columns: 6, gap: 2rem, media: 768px);
$custom3: (columns: 6, gap: 2rem, media: "(max-width: 1280)");

.element {
    @include media($custom1, $custom2, $custom3) {
        @include column(6);
    }
}
```

CSS output:

```css
@media only screen and (min-width: 576px) {
    .element {
        margin-left: 1rem;
        width: calc(0.5 * 100% - 1rem);
    }
}

@media only screen and (min-width: 768px) {
    .element {
        margin-left: 2rem;
        width: calc(1 * 100% - 2rem);
    }
}

@media (max-width: 1280) {
    .element {
        margin-left: 2rem;
        width: calc(1 * 100% - 2rem);
    }
}
```

***

To assist `media()` there is global variables with default breakpoints that can be used.

- `$sm`: 576px
- `$md`: 768px
- `$lg`: 992px
- `$xl`: 1200px

SCSS:

```scss
.column {
    @include media($sm) {
        @include column(6);
    }
}
```

CSS output:

```css
@media only screen and (min-width: 576px) {
    .column {
        margin-left: 1rem;
        width: calc(0.5 * 100% - 1rem);
    }
}
```