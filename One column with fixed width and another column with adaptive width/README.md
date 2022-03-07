## Overview

It shows a web with two columns: one column with fixed width ( __200px__ ) and another column with adaptive width.

__But__ the height of two columns are __not equal__.

[ View it on codepen.io] ( https://codepen.io/paraoiawhy/pen/LYOvZrM )

[ View it on gist.github.com] ( https://gist.github.com/321paranoiawhy/2d662b488a961d69696e04d8590f1afe )

Here are two ways to solve the problem: using `CSS table layout` and using `flexbox`.

## Using __CSS table layout__

Using `CSS table layout` can make the height of two columns are equal and the column with lower height will __extend__ to the height of higher column.

The contents of `.html` file are:

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>1.2</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <div class="container">
        <div class="left">Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloribus repellendus labore
            consequuntur ad debitis dicta amet corrupti accusamus optio? Sed, aut vel. Voluptatem beatae quo eius ipsam
            quae voluptas. Dolorum ducimus unde debitis molestias eum. Sapiente, dolore quia? Laudantium quas officiis
            dolore tempora ab saepe quibusdam reprehenderit recusandae adipisci similique.</div>
        <div class="right">Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloribus repellendus labore
            consequuntur ad debitis dicta amet corrupti accusamus optio? Sed, aut vel. Voluptatem beatae quo eius ipsam
            quae voluptas. Dolorum ducimus unde debitis molestias eum. Sapiente, dolore quia? Laudantium quas officiis
            dolore tempora ab saepe quibusdam reprehenderit recusandae adipisci similique.</div>
    </div>
</body>

</html>
```

The contents of `.css` file are:

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

__But__ box-shadow will make the left column have a left margin of 1.5 em.

[ View it on codepen.io] ( https://codepen.io/paraoiawhy/pen/qBVwNML )

[ View it on gist.github.com] ( https://gist.github.com/321paranoiawhy/65cb0bb7ad20c9cfa8dec17c69b80ff0 )

To solve it, a new container should wrap around the whole table and apply a left and right `negative margin` of -1.5 em to counteract the 1.5 em of the border spacing.

The contents of `.html` file are:

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>1.3</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <div class="wrapper">
        <div class="container">
            <div class="left">Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloribus repellendus labore
                consequuntur ad debitis dicta amet corrupti accusamus optio? Sed, aut vel. Voluptatem beatae quo eius
                ipsam
                quae voluptas. Dolorum ducimus unde debitis molestias eum. Sapiente, dolore quia? Laudantium quas
                officiis
                dolore tempora ab saepe quibusdam reprehenderit recusandae adipisci similique.</div>
            <div class="right">Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloribus repellendus labore
                consequuntur ad debitis dicta amet corrupti accusamus optio? Sed, aut vel. Voluptatem beatae quo eius
                ipsam
                quae voluptas. Dolorum ducimus unde debitis molestias eum. Sapiente, dolore quia? Laudantium quas
                officiis
                dolore tempora ab saepe quibusdam reprehenderit recusandae adipisci similique.</div>
        </div>
    </div>
</body>

</html>
```

The contents of .css file are:

```CSS
.container {
    display: table;
    border-spacing: 1.5em;
    box-shadow: 2px 5px 12px;
}
.wrapper {
    margin: 0 -1.5em;
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

[ View it on codepen.io] ( https://codepen.io/paraoiawhy/pen/mdqgEQd )

[ View it on gist.github.com] ( https://gist.github.com/321paranoiawhy/b3e88552cfcd925dca7a8f68ee62af5b )

## Using flexbox
