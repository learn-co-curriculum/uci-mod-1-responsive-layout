# Constructing a Responsive Layout

## Learning Goals

- Construct alternate wrapper sizes between fixed and fluid layouts
- Construct adjustable column properties for different screen sizes

## Introduction

Some of your website visitors will be viewing your website on large displays,
such as big desktop computers or smart TVs; others might be viewing your website
on small tablets and mobile devices. We want our website to look good on either,
and we can use media queries to do just that. How can we set our website up to
automatically switch between, say a _fluid_ layout for mobile devices and a _fixed_
layout for desktops, with only a few queries?

## Construct Alternate Wrapper Sizes Between Fixed and Fluid Layouts

One common way to handle this adjustment in CSS is to use a _wrapper_ class, one
class that wraps any and all core content of our site.  If we want to make
changes that affect all of that content using a media query, we can simply
modify the one _wrapper_ class. In the examples below, we will be looking at how
to use the wrapper class in a few situations.

### Using the Desktop Down Strategy with Wrappers

A popular strategy when using a wrapper class is to first make a layout for
large screens that is centered and stays within a fixed pixel size on the
screen so that our content doesn't get stretched out too wide. On smaller
devices, we switch to a liquid (fluid) size using percents so our content will
squish and expand on many different small and medium size devices, taking up the
maximum amount of space available. Let's look at some example code:

```css
.wrapper {
  width: 960px;
}

@media only screen and (max-width: 980px) {
  .wrapper { width: 90%; }
}
```

In the code above, on line 2, we are setting the default size of our wrapper
element to `960px`. Then, on line 6, we are changing the wrapper size to a fluid
90% of the screen width when the screen size gets below 980px. Larger screens
will always see a fixed wrapper width, but this will give the wrapper
flexibility to shrink to fit on smaller screens.

### Using the Mobile Up (Mobile First) Strategy with Wrappers

In the opposite direction, a design concept that is becoming more and more
prevalent is making a website for the smaller screen _first_, then adding in
media queries to handle larger and larger screen sizes.  The previous example,
reversed, would look like the following on when following the _mobile up_ design
pattern.

```css
.wrapper {
  width: 90%;
}

@media only screen and (min-width: 980px) {
  .wrapper { width: 960px; }
}
```

In the code above on line 2, we are setting the default size of our wrapper
element to 90% width of the screen size, so it will grow and shrink
automatically. Then on line 6, we are changing the wrapper size to a fixed 960px
when the screen size gets above 980px.

## Construct Adjustable Column Properties for Different Screen Sizes 

One common issue we battle when building responsive sites is handling
multi-column layouts on smaller devices. On a large screen, having 3 columns
across the page might look great, but on a smaller mobile device, this will
squish the content to be very narrow. In these cases, it is a common strategy to
change the multi-column layout into a single column layout. This can be achieved
easily by changing floating columns to `float:none` on smaller devices and
adjusting their widths accordingly. Below are the desktop down and mobile up
versions of this.

### Using the Desktop Down Strategy with Columns

```css
.column {
  width: 33.333%;
  float: left;
}

@media only screen and (max-width: 600px) {
  .column {
    width: 100%;
    float: none;
  }
}
```

In the code above, on line 2, we are setting the default size of our column
element to `33.333%` wide and `float: left` to get a three column layout. Then,
on line 8, we are changing the column size to `100%` of the screen width and
`float: none` on line 9 when the screen size gets below `600px`. This creates a
single column on smaller devices 600 pixels and below.

### Using the Mobile Up (Mobile First) Strategy with Columns

```css
.column {
  width: 100%;
  float: none;
}

@media only screen and (min-width: 600px) {
  .column {
    width: 33.333%;
    float: left;
  }
}
```

In the code above, on line 2, we are setting the default size of our column
element to `100%` wide and `float: none` to get a single column layout. Then, on
line 8, we are changing the column size to `33.333%` of the screen width and
`float: left` on line 9 when the screen size gets above 600px. This creates a
multi-column layout on larger devices 600 pixels and above.

When using more complex layout methods such as CSS grids, the premise is the
same, though instead of adjusting `width` and `float`, we can have media queries
that change the number of columns in a grid, or even tell an element to stretch
over multiple columns.

## Conclusion

When building responsive layouts, it is a common strategy to use wrappers and
adjust their widths from fixed to fluid on different size devices. In addition
to adjusting wrapper sizes, you can create variable column sizes and float positioning
to go from multi-column layout to a single column layout on smaller devices. This
will help keep your layouts flexible and usable on a multitude of devices.

## Resources

- [Desktop Down Responsive Layout - Code Example](http://jsfiddle.net/flatiron_school/jERBH/4/)
- [Mobile First Responsive Layout - Code Example](http://jsfiddle.net/flatiron_school/jERBH/5/)
