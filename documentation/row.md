# row()

Create a grid row.

## Arguments

| Name  | Type | Default    | Description                        |
| ----- | ---- | ---------- | ---------------------------------- |
| $grid | map  | $just-grid | Used to define the gap to the row. |

## Example

SCSS:

```scss
.element {
    @include row();
}
```

CSS output:

```css
.element {
    display: flex;
    flex-wrap: wrap;
    margin-left: -1rem;
}
```