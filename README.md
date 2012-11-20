# The Grid

Helium uses a nestable grid based on fluid-width columns, based largely off the one found in ZURB Foundation. Each column's width is expressed as a percentage rather than a fixed number of pixels, so as the width of the viewport grows or shrinks, the grid does too.

## Selectively Responsive

By default, Helium uses a fixed-width layout. However, making it responsive is as simple as adding a class of `responsive` to the `<body>` element of your page. Responsive design is by its nature rather resource-intensive, so I built Helium to allow you to toggle responsive behavior on a per page basis so you can build out responsive pages as time and budgets permit. You can also use the `responsive` class as a hook to target only responsive pages with your SCSS. 

	<body class="responsive">

## SASS Variables

There are three SASS variables that will determine the makeup of your grid. As with nearly every other variable in Helium, these are stored in `scss/config.scss`

### $page-width

(pixels) This is the width of your content if you are using a fixed-width design, or the maximum width of your content if you are using a responsive design.

### $column-count

(positive integer) The number of columns you would like in your grid. Some designs call for 12, others for 16, or for a simple site you might just want 3 or 6.

### $column-gutter

(pixels) The amount of space between your columns.

If you are clever with your math, you can ensure that the column widths are round multiples of 10 pixels. This can be helpful on a fixed-width design. For example, a $page-width of 940px, $column-count of 12 and $column-gutter of 20px will give you 60px wide columns. These are the same values used by the popular 960 grid system.

## Grid Markup

The markup for building a grid in Helium is very lightweight and should look familiar to you if you've ever used ZURB Foundation, 960gs or Bootstrap. Keep in mind that the sum total of the `spanX` elements in a row must not exceed the value set for the `$column-count` variable in `config.scss`. The markup below would be appropriate for a 12 column grid.

	<div class="container">
		<div class="row">
			<div class="span4">
			</div>
			
			<div class="span4">
			</div>
			
			<div class="span4">
			</div>
		</div>
	</div>


## The Breakpoint

### $responsive-breakpoint

(pixels) At a certain point, you are going to want your multi-column grid to collapse into a single column as the individual columns will start to become too narrow. By default, this is set to 767px, so anything smaller than an iPad in portrait mode with get a single-column layout. Feel free to adjust this value as your design requires.

# Buttons

Buttons are a big component of any UI. Helium tries to include many common button patterns without making too many assumptions about how you will use them.

## Basic button style

A clean, flexible button style for all different kinds of UI tasks. Keep in mind that you can use the `button` class on both `<a>` and `<button>` elements.

	<a class="button>Here's a button</a>
	
	<button class="button>Here's another</button>
	
## Large buttons

Often times, you want your primary call to action button to be larger than other UI buttons. Just append an additional class of `button-large`.

	<a class="button button-large">I’m a call to action!</a>
	
## Small buttons

Sometimes you need to fit buttons in a smaller space or de-emphasize them. Just append a class of `button-small`.

	<a class="button button-small">I'm a small button</a> 
	
