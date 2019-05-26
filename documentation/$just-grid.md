# $just-grid

This variable is a SASS map with all the grid settings and can be overrided.

## Properties

| Name    | Type               | Default | Description                       |
| ------- | ------------------ | ------- | --------------------------------- |
| columns | number (unitless)  | 12      | Default total number of columns.  |
| gap     | number (with unit) | 1rem    | Default gap between columns.      |

## Example

SCSS:

```scss
$just-grid: (
    columns: 6,
    gap: 2rem
);
```