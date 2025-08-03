  Table Grid by @mdo  /\* Grid: PC, NOT mobile-first \*/ .grid { display: table; width: 100%; table-layout: fixed; } .col { display: table-cell; } .grid-padded .grid { border-spacing: 14px 0px; } .col-1 { width: 8.33333%; } .col-2 { width: 16.6667%; } .col-3 { width: 25%; } .col-4 { width: 33.3333%; } .col-5 { width: 41.6667%; } .col-6 { width: 50%; } .col-7 { width: 58.3333%; } .col-8 { width: 66.6667%; } .grid-align-middle .col { vertical-align: middle; } .grid-reverse { direction: rtl; } .grid-reverse .col { direction: ltr; } .highlight{display: block !important;} /\* Firefox 2.0 fix \*/ /\* Here's code for the Smartphone: \*/ @media screen and (max-width: 800px){ .col {display: block;} .col-1, .col-2, .col-3, .col-4, .col-5, .col-6, .col-7, .col-8{ width: 100%;display: block;} .grid-padded{margin-left: auto;margin-right: auto;} } /\* YOU DON'T NEED THIS STYLE FOR GRIDS TO WORK! Page design: \*/ body { font-size: 14px; } /\*@media (min-width: 600px) { body { font-size: 16px !important; } }\*/ @media screen and (-moz-images-in-menus:0) { body { font-size: 14px; } } body { margin: 0px; padding-bottom: 54px;/\* 18px/1.5 \*/ font: 18px /\*-apple-system, BlinkMacSystemFont,\*/"Segoe UI","Roboto","Oxygen","Ubuntu","Cantarell","Fira Sans","Droid Sans","Helvetica Neue",Arial,sans-serif; color: rgb(85, 85, 85); text-align: center; background-color: rgb(255, 255, 255); } @media screen and (max-width: 800px){ body { font-size: 14px !important; } } @media screen and (min-width: 62.5rem){ .container { max-width: 980px; margin-right: auto; margin-left: auto; } } /\*.container { max-width: 54rem; padding: 0px 18px; }\*/ a { color: rgb(24, 116, 205); text-decoration: none; } a:hover { color: rgb(16, 78, 139); } h1, h2, h3 { margin-top: 0px; margin-bottom: 9px /\*0.5rem\*/; font-weight: 500; line-height: 1.1; color: rgb(51, 51, 51); } h1 { font-size: 54px; } h2 { margin-top: 54px; font-size: 36px; } p { margin-top: 0px; margin-bottom: 18px; } .container > p { margin: 9px /\*0.5rem\*/ auto 18px; max-width: 800px; } hr { max-width: 100px; border-width: 0.18px 0px 0px; border-style: solid none none; border-color: rgb(238, 238, 238) currentcolor currentcolor; -moz-border-top-colors: none; -moz-border-right-colors: none; -moz-border-bottom-colors: none; -moz-border-left-colors: none; border-image: none; } code { /\*padding: 24px 0.54px;\*/ font-family: Menlo,"Courier New",monospace; font-size: 90%; /\*padding: 0.15rem 0.54rem\*/ color: rgb(205, 51, 51); background-color: rgb(245, 245, 245); border-radius: 3px; } .inline-block { display: inline-block; } .masthead { padding: 24px 16px; font-weight: 300; color: #E7C0BF /\*rgba(255, 255, 255, 0.65)\*/; text-align: center; background-color: rgb(185, 74, 72); } .masthead a, .masthead strong { font-weight: normal; color: rgb(255, 255, 255); } .masthead p { font-size: 18px; } /\* 1.25rem \*/ .grid-example { margin-bottom: 18px; } /\* was 18px \*/ .grid-example .col { line-height: 3; text-align: center; color: rgb(51, 51, 51); background-color: #FFD9D9 /\*rgba(255, 0, 0, 0.15)\*/; } .grid-example .col:nth-child(2n+1) { background-color: #FFB2B2 /\*rgba(255, 0, 0, 0.3)\*/; } .grid-example .grid-example { margin-top: 9px /\*0.5rem\*/; margin-bottom: 0px; } .grid-example.grid-align-middle { height: 200px; } .grid-example.grid-align-middle .col { min-height: 54px; line-height: 1.5; } .c { color: rgb(153, 153, 153); } .s { color: rgb(212, 73, 80); } .na { color: rgb(79, 159, 207); } .nt { color: rgb(47, 111, 159); } .highlight {text-align: left; background-color: rgb(247, 247, 249); } .highlight pre { padding: 0px; margin-top: 0px; margin-bottom: 0px; background-color: transparent; border: 0px none; } .highlight pre code { font-size: inherit; color: rgb(51, 51, 51); background-color: transparent; } @media screen and (max-width: 800px){ .wordmark a{font-size: 36px} } /\* YOU DON'T NEED THIS STYLE FOR GRIDS TO WORK! \*/

[@mdo/table-grid](https://github.com/mdo/table-grid)
====================================================

This is a serious-fun-dumb-useful experiment for writing a simple,  
responsive, and mobile-compatible CSS grid system. **With tables.**

**IE8+, Firefox 2.0+, Opera 9+, Safari 5.1.7+ (modified by s60team)**

Premise
-------

CSS grid systems are typically built in one of two ways today – `float`s  
or some `display: inline-block;` hackery.  
Both are fine and well established, but `table`s are way cooler thanks to `table-layout`  
and dead simple alignment.

Let’s take a look:

* * *

Typical approach
----------------

The typical approach is to create twelve fixed-width columns in all the usual combinations.  
Cool, super easy to do, and [@mdo/table-grid](https://github.com/mdo/table-grid) supports that.  
There’s also a base class for ease of use that makes our columns use `display: table-cell;` and more.

1

1

1

1

1

1

1

1

1

1

1

1

2

2

2

2

2

2

3

3

3

3

4

4

4

5

7

6

6

8

4

12

    <div class="grid">
      <div class="col col-8">8</div>
      <div class="col col-4">4</div>
    </div>

* * *

Table layout
------------

Now comes the really fun part. With `table-layout: fixed;`, we can drop half our grid classes.  
**Fixed table layouts render equal-width columns when no other width is set.**

Col

Col

Col

Col

Col

Col

Col

Col

Col

Col

Col

Col

Col

Col

Col

Col

Col

Col

Column

Column

Column

Column

Column

Column

Column

Column

Column

Column

    <div class="grid">
      <div class="col">Column</div>
      <div class="col">Column</div>
      <div class="col">Column</div>
    </div>

* * *

Nested
------

With or without those extra classes, table grids are easily nestable.  
Just place a `.grid` with any combination of columns within an existing `.col`.

8

Column

Column

4

    <div class="grid">
      <div class="col col-8">
        8
        <div class="grid">
          <div class="col">Column</div>
          <div class="col">Column</div>
        </div>
      </div>
      <div class="col col-4">4</div>
    </div>

* * *

Grids with gutters
------------------

Wrap the `.grid` with `div.grid-padded` to add gutters between columns.  
Works on any column, even the `width`\-less base class.

The wrapping `.grid-padded` applies negative horizontal margins to account for the gutters.  
Tables that are 100% wide cannot have negative horizontal margins directly applied to them, so we must use a wrapper.

Column

Column

Column

Column

Column

8

4

    <div class="wrap">
      <div class="grid-padded">
        <div class="grid">
          <div class="col">Column</div>
          <div class="col">Column</div>
        </div>
      </div>
    </div>

* * *

Vertically center content
-------------------------

Add the `.grid-align-middle` class to the `.grid` and voilà.  
Requires the use of `inline`, `inline-block`, or `table` based elements within a column.  
IE6 needs a wrapper.

Free-form text wraps while remaining vertically centered.

Nested columns center, too.

Column

Column

A \`div\` with \`inline-block\` works great, too.

    <div class="grid-padded">
      <div class="grid grid-align-middle">
        <!-- Columns -->
      </div>
    </div>

* * *

Reverse column sorting
----------------------

Add the `.grid-reverse` class to the `.grid` table and you’ll have reversed columns.  
In the example below, **Column 1** is first in the markup, but appears last when rendered.  
And because our table grid is responsive, they’re stacked in order on mobile, too.

Column 1

Column 2

    <div class="grid-padded">
      <div class="grid grid-reverse">
        <div class="col">Column 1</div>
        <div class="col">Column 2</div>
      </div>
    </div>

* * *

Download
--------

Head to GitHub to [download @mdo/table-grid](https://github.com/mdo/table-grid) (includes source Sass and docs).

* * *

Shoutout tables.

<3