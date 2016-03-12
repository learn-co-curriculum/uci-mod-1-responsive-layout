# Responsive Layout

## Overview

In this lesson we will show a practical strategy for adjusting layout wrappers and columns on different size devices.

## Objectives

1. Alternate wrapper size between fixed and fluid at different screen sizes.
2. Adjust column size and position to be responsive at different screen sizes.

## Simple Responsive Layout Techniques

<iframe width="640" height="480" src="//www.youtube.com/embed/ifbnTWVH6hM?rel=0" frameborder="0" allowfullscreen></iframe>

*Note: Slides for this lecture video are provided in the resources at the bottom of this lesson.*

### Alternating Wrapper Measurement

Some of your website visitors will be viewing your website on large displays such as big desktop computers or smart tvs, others might be viewing your website on small tablets and mobile devices. For this reason we might want to adjust our wrapper size to change between fluid for smaller devices to fixed for larger devices. For example a common strategy is to make a layour center and stay within a fixed pixel size on large screens that way our content doesn't get stretched out to wide, yet on smaller devices we may want to switch to a liquid (fluid) size using percents so our content will squish and expand on many different small and medium size devices taking up the maximum amount of space available. Let's look at some example code,

#### Desktop Down

```css
.wrapper { 
  width: 960px; 
}

@media only screen and (max-width: 980px) {
  .wrapper { width: 90%; }
}
```

In the code above on line 2 we are setting the default size of our wrapper element to 960px. Then on line 6 we are changing the wrapper size to a fluid 90% of the screen width when the screen size gets below 980px.

#### Mobile Up (Mobile First)

```css
.wrapper { 
  width: 90%; 
}

@media only screen and (min-width: 980px) {
  .wrapper { width: 960px; }
}
```

In the code above on line 2 we are setting the default size of our wrapper element to 90% width of the screen size. Then on line 6 we are changing the wrapper size to a fixed 960px when the screen size gets above 980px.

Check out these code examples in the resource links at the bottom of thsi lesson. 

### Adjusting Column Size and Positioning

Another common issue we battle when building responsive sites is how to handle multi column layouts on smaller devices. On a large screen having 3 columns across the page might look great, but on a smaller mobile device this will squish the content very tight. In these cases it is a common strategy to change the multi column layout into a single column layout. This can be achieved easily by changing floating columns to `float:none` on smaller devices and adjusting their widths accordingly.Let's look at some example code,

#### Desktop Down

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

In the code above on line 2 we are setting the default size of our column element to `33.333%` wide and `float: left` to get a three column layout. Then on line 8 we are changing the column size to `100%` of the screen width and `float: none` on line 9 when the screen size gets below 600px. This creates a single column on smaller devices 600px and below.

#### Mobile Up (Mobile First)

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

In the code above on line 2 we are setting the default size of our column element to `100%` wide and `float: none` to get a single column layout. Then on line 8 we are changing the column size to `33.333%` of the screen width and `float: left` on line 9 when the screen size gets above 600px. This creates a multi column layout on larger devices 600px and above.

## Summary

- It is a common strategy to adjust wrapper widths from fixed to fluid on different size devices.
- It is also a common strategy to adjust column size and float positioning to go from multi column layout to single column layout on smaller devices.

## Resources

- [Presentation Slides](https://docs.google.com/presentation/d/1j_i5pGPB5lHbgr4fpdUDheRBv2kAeOk_yhfd1Uc2f3s/edit?usp=sharing)
- [Desktop Down Responsive Layout - Code Example](http://jsfiddle.net/flatiron_school/jERBH/4/)
- [Mobile First Responsive Layout - Code Example](http://jsfiddle.net/flatiron_school/jERBH/5/)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/responsive-layout' title='Responsive Layout'>Responsive Layout</a> on Learn.co and start learning to code for free.</p>
