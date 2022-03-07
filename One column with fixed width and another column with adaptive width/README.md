## Overview

It shows a web with two columns: one column with fixed width ( __200px__ ) and another column with adaptive width.

__But__ the height of two columns are __not equal__.

[ View it on codepen.io] ( https://codepen.io/paraoiawhy/pen/LYOvZrM )

[ View it on gist.github.com] ( https://gist.github.com/321paranoiawhy/2d662b488a961d69696e04d8590f1afe )

Here are two ways to solve the problem: using `CSS table layout` and using `flexbox`.

## Using __CSS table layout__

Using `CSS table layout` can make the height of two columns are equal and the column with lower height will __extend__ to the height of higher column. The contents of 
.css file are:

```CSS
.container {
    display: table;
    border-spacing: 1.5em;
    box-shadow: 2px 5px 12px;
}
.left {
    display: table-cell;
    width: 200px;
    background-image: linear-gradient(to bottom right, #c973ff, #aebaf8);
    box-shadow: 2px 5px 12px;
}
.right {
    display: table-cell;
    width: calc(100% - 200px);
    background-image: linear-gradient(to bottom right, #c973ff, #aebaf8);
    box-shadow: 2px 5px 12px;
}
```

But box-shadow will make the left column have a left margin of 1.5 em.

[ View it on codepen.io] ( https://codepen.io/paraoiawhy/pen/qBVwNML )

[ View it on gist.github.com] ( https://gist.github.com/321paranoiawhy/65cb0bb7ad20c9cfa8dec17c69b80ff0 )

To solve it, a new container should wrap around the whole table and apply a left and right `negative margin` of -1.5 em to counteract the 1.5 em of the border spacing.

[ View it on codepen.io] ( https://codepen.io/paraoiawhy/pen/mdqgEQd )

[ View it on gist.github.com] ( https://gist.github.com/321paranoiawhy/b3e88552cfcd925dca7a8f68ee62af5b )

## Using flexbox
