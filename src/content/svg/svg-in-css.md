---
day: 21
title: How to Inline SVG in CSS
component: Background
description: In this example we learn how to Inline SVG in CSS, and how to create background patterns.
previous:
  title: Snowing
  link: snowing
next:
  title: How to Draw a Clock that Shows the Actual Time with SVG and JavaScript
  link: clock
---

In many cases, an inlined SVG feels like a bit of noise in HTML. If we add an icon then the icon itself feels more like styling than content that should be part of the DOM structure. The good news is, we can move SVG images entirely into CSS.

For example, let's take the close button on this page at the top right corner. In HTML the close button is simply an anchor element with a class:

```html
<a href="/" class="close"></a>
```

Then in CSS we can set a `background-image` property. For this CSS property, we usually provide a link to an image, but we can also inline an SVG:

```css
.close {
  display: block;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: gray;

  background-image: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='50' height='50' viewBox='0 0 100 100'><path d='M 30 30 L 70 70 M 30 70 L 70 30' stroke='white' stroke-width='10' /></svg>");
}
```

The inlined SVG above is simply an X as follows (except that the `stroke` property is set to black in this case for visibility). The gray circle around it is made with CSS (by setting the `background-color` and the `border-radius` properties).

<div class="grid-200">

<svg xmlns='http://www.w3.org/2000/svg' width='50' height='50' viewBox='0 0 100 100'>
<path d='M 30 30 L 70 70 M 30 70 L 70 30' stroke='black' stroke-width='10' />
</svg>

<!-- prettier-ignore -->
```html
<svg 
  xmlns='http://www.w3.org/2000/svg' 
  width='50' 
  height='50' 
  viewBox='0 0 100 100'
>
  <path 
    d='
      M 30 30 
      L 70 70 
      M 30 70 
      L 70 30'
    stroke='black' 
    stroke-width='10' 
  />
</svg>
```

</div>

When we inline an SVG in CSS, we need to set the XML namespace property. Earlier we inlined SVGs into HTML and in that case it's optional. In CSS we have to set the `xmlns` property.

### Background Patterns with SVG in CSS

We can also use this technique to generate a background pattern. By default if the image we define in `background-image` is smaller than the element itself, then the image will repeat itself.

In the main example for today we simply repeat the following SVG:

<div class="grid-200">

<svg xmlns='http://www.w3.org/2000/svg' width='50' height='50' viewBox='0 0 120 120'><polyline fill="none" stroke="#0c5c4c" stroke-width="42.4" points="-30 0 60 90 150 0"/></svg>

<!-- prettier-ignore -->
```html
<svg 
  xmlns='http://www.w3.org/2000/svg' 
  width='50'
  height='50'
  viewBox='0 0 120 120'
>
  <polyline
    fill='none'
    stroke='#0c5c4c'
    stroke-width='42.4'
    points='-30 0 60 90 150 0'
  />
</svg>
```

</div>

In this example we encode some special characters in the inlined string. In the example below we encode the pointy brackets (`<` and `>`) and the `#` key in the color value to make sure it works in every browser. This makes it hard to read, but what we have here is still a simple SVG.

<div class="code-flex">

```html
<div class="background" />
```

```css
.background {
  background-color: #38755b;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='50' height='50' viewBox='0 0 120 120'%3E%3Cpolyline fill='none' stroke='%230c5c4c' stroke-width='42.4' points='-30 0 60 90 150 0' /%3E%3C/svg%3E");
}
```

</div>

You might also note that this SVG image doesn't even have a background color set. We set that in CSS.

This is a great way to create background patterns with only a few lines of code in CSS. If you like this idea check out <a href="https://www.svgbackgrounds.com/" target="_blank" rel="noopener">svgbackgrounds.com</a> for a lot more great patterns.
