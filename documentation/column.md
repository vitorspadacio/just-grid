# column()

Create a grid column.

## Arguments

| Name     | Type                           | Default    | Description                       |
| -------- | ------------------------------ | ---------- | --------------------------------- |
| $columns | number (unitless) *or* string  | null       | Determine the size of the column based in the total columns.<br>You can use a shorthand `1 of 3` to determine the size of column and the total columns expected. |
| $grid    | map                            | $just-grid | Used to determine the grid settings. |

## Example

SCSS:

```scss
.element {
    @include column(3);
}
```

CSS output:

```css
.element {
    margin-left: 1rem;
    width: calc(0.25 * 100% - 1rem);
}
```