# $breakpoints

A sort of breakpoints variables to simplify media query creation. Can be override.

This variables is based in Bootstrap breakpoints, using a default setting, but is not required do be used. You can ignore completely and use breakpoints in other way.

## Properties

| Name         | Type | Default     | Description                              |
| ------------ | ---- | ----------- | ---------------------------------------- |
| $custom-grid | map  | (see above) | The grid to be used in that breakpoint.  |

## Example

Default:

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

> Don't forget, if you want to change this values, change the full name variables, not the short ones.

SCSS:

```scss
$small-screen: (
    columns: 6,
    gap: 0.5rem,
    media: 360px
);

.element {
    @include media($sm) {
        @include columns(6)
    }
}
```

CSS output:

```css
@media only screen and (min-width: 360px) {
    .column {
        margin-left: 0.5rem;
        width: calc(1 * 100% - 0.5rem);
    }
}
```