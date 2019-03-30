# Basic Grid 2.0

Basic Grid is a simple customizable CSS grid framework originally inspired by Bootstrap. Version 1.0 utilized floats and margins like Bootstrap, but with CSS Grid now the new standard, I wanted to make a new version of this system that utilizes CSS Grid as the backbone.

While this is a solid system for quick prototyping and even full builds, I will impress that it barely uses all the functions and options in CSS Grid Layout, and I would still suggest to those seeking to do more in their layouts to [learn CSS Grid in full](https://gridbyexample.com/) and create your own grids as you see fit.

If you like and want to use this system (or your own grids), I also have a responsive header navigation that sizes into a CSS-only hamburger menu, built using CSS Grid. You can check it out [here](https://github.com/amportfolio/css-dropDown-menu-2).

Like with version 1.0, I’m still using [Normalize](https://github.com/necolas/normalize.css) and [Eric Meyer’s reset](http://meyerweb.com/eric/tools/css/reset/) for improved cross-browser rendering. If you wish to remove this or use your own reset system, see Customizing Basic Grid at the bottom on how you can process your own customized version of this framework.

## Getting Started

Beyond the standards of HTML like declaring doctype, you will need to set your viewport in order to make this work perfectly:

`<meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0">`

## Grid Column Options

One major difference with this system versus Bootstrap is the addition of three additional breakpoints. You can see how things break down here:

Breakpoint | Size Range | Ideal For
------------ | ------------- | -------------
`.col-xxs-` | 1px–319px | Small Smartphones
`.col-xs-` | 320px–479px | Normal Smartphones
`.col-sm-` | 480px–767px | Phablets and Landscape Orientation
`.col-md-` | 768px–991px | Small Tablets
`.col-lg-` | 992px–1199px | Large Tablets and Small Laptops
`.col-xl-` | 1200px–1439px | Large Laptops and Workstation Monitors
`.col-xxl-` | 1440px+ | Large Screens

## Setting up grids (or rows)

Unlike Version 1.0, there is no requirement to use any kind of a *container* div anymore. You can simply set up a 12-column grid using the `.grid` class or the `.row` class. I kept `.row` in this system for those who are used to Bootstrap, but either does the same.

    <div class="grid">
        ···
    </div>

    <div class="row">
        ···
    </div>

The classes for the grid areas are also significantly different now compared to Bootstrap or Version 1.0. Instead of using just a number to signify how many columns your grid area spans, you instead enter two numbers signifying the starting column and the ending column:

`.col-[breakpoint]-[starting column]-[ending column]`

Any undeclared divs within the grid will be set to span the full 12 columns. Refer to *index.html* to see examples.

## Column Wrapping

Column wrapping can still happen within reason. While you cannot make the divs span a number of columns past the final column, you can see that divs will slide in and out of the first row if they can fit.

## Changing Grid Item Heights

In the past, you would simply set a height to a div and manipulate things around it. Setting a height in this system will make all the divs in a row grow in the same height. Refer to *index.html* to see it illustrated.

Now if you wanted to simply make one grid area taller but keep the rest in their own height, try using `.grid-row` in your CSS:


## No more Column Reset

Since CSS Grid does not use floats to place items, the idea of a *clearfix* to clear said floats within a row is gone. A simple solution would be to set up multiple rows or use the column classes, or even to explore using `.grid-row` in your CSS.

## Nested Columns

If you wish to nest columns within a column, you simply set up a new `.grid` or `.row` and go from there. The grid area you’re in will act as a container for the new row.

## Column Reordering

Since we are no longer using floats and margins to place items in a grid, the idea of having *push* and *pull* classes is redunant. Instead, just set up your placement using the column classes with the numbers as where you want things to place, but you'll also need to set your grid areas to be in one row using `grid-row` in the media queries. Refer to *index.html* to see it illustrated.


## Column Offset

Offsetting is a simpler matter with CSS Grid, as you can just set your grid areas to place exactly in the columns you wish. Refer to *index.html* to see it illustrated.

## Column Visibility

Just like before, you can make grid areas appear and disappear at certain breakpoints by using .hidden- and .visible- classes alongside your grid column classes. Simply use .hidden- or .visible- with the breakpoint you wish.

**NOTE:** It seems when you want to hide a grid area on one breakpoint, you need to declare the `.visible-` class on the other remaining breakpoints you wish this area to appear. It’s a bug I also noticed with Bootstrap and am exploring a workaround.

Also bear in mind that columns will not shift to the left when you hide a div area because we’re designating exactly where they place.

## Customizing Basic Grid
An additional benefit to this CSS framework is you can totally customize the number of breakpoints you want, the widths of those breakpoints, their names, the gutter, and the total number of columns you want.

I’ve included the SCSS files used to make the full grid. Simply open *_config.scss* and change the configuration as you see fit, then process it into finished CSS using a preprocessor such as Gulp or Koala.

## Questions? Comments? Suggestions?

Please feel free to reach out or fork this and improve on it.

## Authors

* **Alex Moschopoulos** - *Initial work* - [amportfolio](https://github.com/amportfolio)

## Acknowledgments

* Bootstrap...it was a nice start, but it drove me to push for more.
* SCSS...I love it
* [Grid By Example](https://gridbyexample.com/)...amazing free resource to learn CSS Grid.