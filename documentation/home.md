# Just

Just consist in three mixins:
- [row()](https://github.com/vsp193/just-grid/wiki/row())
- [column()](https://github.com/vsp193/just-grid/wiki/column())
- [media()](https://github.com/vsp193/just-grid/wiki/media())

And a sort of default variables that can be overrided:
- [$just-grid](https://github.com/vsp193/just-grid/wiki/%24just-grid)
- [$breakpoints](https://github.com/vsp193/just-grid/wiki/%24breakpoints)

You can begin using `row()` to define your base element.

```scss
.container{
    @include row();
}
```

Now you use `column(1)` to set the element to represent a column to this row.

```scss
.element {
    @include column(1);
}
```

With this you defined a `1 of 12` column, using default `settings`.
