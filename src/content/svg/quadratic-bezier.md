---
day: 11
title: How to Draw Quadratic Bézier Curves with SVG
component: ThreeWithCurves
description: In this example we draw a Tree with SVG and learn how to draw quadratic bézier curces.
previous:
  title: Snowman
  link: snowman
next:
  title: How to Draw Cubic Bézier Curves with SVG
  link: cubic-bezier
---

The path element becomes really powerful when we start using curves. One of them is the quadratic Bezier curve. We not only set the endpoint but we also have to set a control point.

The control point is an invisible coordinate to which the line is bending to, but not touching it. Look at this happy face! Here the invisible control point is at the middle of the bottom of the image (at `0,100`).

<div class="grid-200">

  <svg width="200" height="200" viewBox="-100 -100 200 200">
    <circle cx="-50" cy="-50" r="20" />
    <circle cx="50" cy="-50" r="20" />
    <path d="M -70,50 Q 0,100 70,50" fill="none" stroke="black" stroke-width="10" stroke-linecap="round" />
  </svg>

<!-- prettier-ignore -->
```html
<svg 
  width="200"
  height="200"
  viewBox="-100 -100 200 200"
>
  <circle cx="-50" cy="-50" r="20" />
  <circle cx="50" cy="-50" r="20" />
  <path 
    d="
      M -70,50 
      Q 0,100 70,50" 
    fill="none" 
    stroke="black" 
    stroke-width="10" 
    stroke-linecap="round" 
  />
</svg>
```

</div>

In the example above the control point is at the same distance of the two endpoints. This is not necessary. In the example below we mark the control point with a circle. Note, that the control point and the circle have the same coordinates.

<div class="grid-200">

  <svg width="200" height="200" viewBox="-100 -100 200 200">
    <path d="M -50,50 Q 50,-50 50,50" fill="none" stroke="black" stroke-width="5"  />
    <circle cx="50" cy="-50" r="5" />
  </svg>

<!-- prettier-ignore -->
```html
<svg 
  width="200"
  height="200"
  viewBox="-100 -100 200 200"
>
  <path 
    d="
      M -50,50 
      Q 50,-50 50,50" 
    fill="none"
    stroke="black"
    stroke-width="5"
  />
  <circle 
    cx="50"
    cy="-50"
    r="5" 
  />
</svg>
```

</div>

Click here for <a href="https://hunormarton.github.io/svg-curves" target="_blank" rel="noopener">an interactive demo</a> of Quadratic Béziers (select Quadratic Bézier at the top of the page).

In today's example, we have a series of quadratic beziers where the control points get further and further away from the center of the tree as the path goes down.

<div class="code-flex">

```html
<svg width="200" height="400" viewBox="-100 -200 200 400">
  <path
    d="
      M 0 -80
      Q 5 -75 0 -70
      Q -10 -65 0 -60
      Q 15 -55 0 -50
      Q -20 -45 0 -40
      Q 25 -35 0 -30
      Q -30 -25 0 -20
      Q 35 -15 0 -10
      Q -40 -5 0 0
      Q 45 5 0 10
      Q -50 15 0 20
      Q 55 25 0 30
      Q -60 35 0 40
      Q 65 45 0 50
      Q -70 55 0 60
      Q 75 65 0 70
      Q -80 75 0 80
      Q 85 85 0 90
      Q -90 95 0 100
      Q 95 105 0 110
      Q -100 115 0 120
      L 0 140
      L 20 140
      L -20 140"
    fill="none"
    stroke="#0C5C4C"
    stroke-width="5"
  />
</svg>
```

</div>

If we break down each quadratic bézier above into two line segments with the same coordinates, that would look like this:

<div class="grid-200">

  <svg width="200" height="400" viewBox="-100 -200 200 400">
    <path d="
      M 0 -80
      L 5 -75 L 0 -70
      L -10 -65 L 0 -60
      L 15 -55 L 0 -50
      L -20 -45 L 0 -40
      L 25 -35 L 0 -30
      L -30 -25 L 0 -20
      L 35 -15 L 0 -10
      L -40 -5 L 0 0
      L 45 5 L 0 10
      L -50 15 L 0 20
      L 55 25 L 0 30
      L -60 35 L 0 40
      L 65 45 L 0 50
      L -70 55 L 0 60
      L 75 65 L 0 70
      L -80 75 L 0 80
      L 85 85 L 0 90
      L -90 95 L 0 100
      L 95 105 L 0 110
      L -100 115 L 0 120
      L 0 140
      L 20 140
      L -20 140" fill="none" stroke="black"  />
  </svg>

<!-- prettier-ignore -->
```html
<svg 
  width="200"
  height="400"
  viewBox="-100 -200 200 400"
>
  <path 
    d="
      M 0 -80
      L 5 -75 L 0 -70
      L -10 -65 L 0 -60
      L 15 -55 L 0 -50
      L -20 -45 L 0 -40
      L 25 -35 L 0 -30
      L -30 -25 L 0 -20
      L 35 -15 L 0 -10
      L -40 -5 L 0 0
      L 45 5 L 0 10
      L -50 15 L 0 20
      L 55 25 L 0 30
      L -60 35 L 0 40
      L 65 45 L 0 50
      L -70 55 L 0 60
      L 75 65 L 0 70
      L -80 75 L 0 80
      L 85 85 L 0 90
      L -90 95 L 0 100
      L 95 105 L 0 110
      L -100 115 L 0 120
      L 0 140
      L 20 140
      L -20 140"
    fill="none"
    stroke="black"
  />
</svg>
```

</div>
