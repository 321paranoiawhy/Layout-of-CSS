## Overview
It shows a web with two columns: one column with fixed width ( __200px__ ) and another column with adaptive width.

__But__ the height of two columns are __not equal__.

[ View it in codepen.io: ] ( https://codepen.io/paraoiawhy/pen/RwjObxy )

Here are two ways to solve the problem: using __CSS table layout__ and using __flexbox__.
## Using __CSS table layout__
Using __CSS table layout__ can make the height of two columns are equal and the column with lower height will __extend__ to the height of higher column. The contents of 
.css file are:

···CSS
.container {
    display: table;
    box-shadow: 2px 5px 12px;
    border-spacing: 1.5em;
    box-shadow: 2px 5px 12px;
}
.left {
    display: table-cell;
    width: 200px;
    color: black;
    background-image: linear-gradient(to bottom right, #c973ff, #aebaf8);
    box-shadow: 2px 5px 12px;
}
.right {
    display: table-cell;
    width: calc(100% - 200px);
    color: black;
    background-image: linear-gradient(to bottom right, #c973ff, #aebaf8);
    box-shadow: 2px 5px 12px;
}
···
But box-shadow will make the left column have a left margin of 1.5 em. 
To solve it, a new container should wrap around the whole table and apply a left and right margin of -1.5 em to counteract the 1.5 em of the border spacing.
[ View it in codepen.io: ] ( https://codepen.io/paraoiawhy/pen/LYOvYjg )
## Using flexbox
