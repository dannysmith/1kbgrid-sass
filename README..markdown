# 1kb Grid System for Sass

This is a tiny little [Sass](http://sass-lang.com) version of the [1kb Grid](http://1kbgrid.com/) by Tyler Tate.

## What does it do?
Once you've set up the variables in grid.sass the work of calculating the grid values is done by Sass. For a 960px grid with 12 columns and a gutter of 20px:

    $column_width: 60
    $column_count: 12
    $column_gutter: 20

This will generate the correct classes like:

    .grid_1 {
      width: 60px; }

    .grid_2 {
      width: 140px; }

    .grid_3 {
      width: 220px; }
    
    ...
  
It will also create Sass mixins that can be used in other stylesheets like:

    .header
      +grid(12)
    
This avoids the need for hundreds of .row, .column and .grid_x classes in your markup.

## Example Page
The example page contains an example similar to the one included in the 1kbGrid Download, as well as some code to put a [Layout Grid](Gridhttp://gridlayouts.com/) behind it.

If you want to use this, you should alter the values at the bottom of the demo page to match those defined in your grid.sass file:

    #GridLayout
      #GridLayout-params
        {
        column_width:60,
        column_count:12,
        subcolumn_count:1,
        column_gutter:20,
        align:'center'
        }
    
There's no easy way to do this with just Sass and Haml.

This will let you toggle a grid with Ctrl-Shift-G.


## Get it Working on its own
You could run [Serve](http://github.com/jlong/serve) in the /served directory

    gem install serve
    cd 1kbgrid-sass/served
    serve

You'll see it at http://localhost:4000.

If you want to change the Haml or Sass you'll obviously have to re-render the HTML and CSS with something like:

haml -f html5 example.haml served/index.html
sass styles.sass served/styles.css

## Author
1KbGrid-sass was written by [Danny Smith](http://dasmith.co.uk).<br>
The 1Kb Grid was dreamed up by [Tyler Tate](http://www.tylertate.com/). See [http://www.1kbgrid.com/](http://www.1kbgrid.com/)
