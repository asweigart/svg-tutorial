---
day: 17
title: How to Draw Text Along a Path with SVG
component: Text
description: In this example we learn how draw a text along a path with SVG.
previous:
  title: Bear
  link: bear
next:
  title: How to Animate Along a Path with SVG
  link: path-based-animation
---

Drawing shapes is not the only use case for paths. We can also use them to render text along an invisible path. We can define a path in the definitions section and use it in a `textPath` element to make the text go around the circle. Here we use arc again, but you can use any other path and the text will follow the stroke.

<div class="code-flex">

```html
<svg width="200" height="200" viewBox="-100 -100 200 200">
  <defs>
    <path id="text-arc" d="M 0, 50 A 50 50 0 1 1 1,50" />
  </defs>

  <text
    fill="#0c5c4c"
    font-family="Tahoma"
    font-size="0.77em"
    font-weight="bold"
  >
    <textPath href="#text-arc">
      Happy Holidays! Happy Holidays! Happy Holidays!
    </textPath>
  </text>
</svg>
```

</div>
