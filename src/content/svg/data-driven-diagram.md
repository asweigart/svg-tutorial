---
day: 24
title: How to Generate an SVG Diagram from JavaScript
component: Diagram
description: In this example we learn how to draw a data driven SVG diagram with JavaScript.
previous:
  title: Interaction
  link: interaction
next:
  title: How to Break Down an SVG Image into Multiple Components
  link: multiple-components
---

SVG also work well with frontend libraries. Here’s an example of a React component that generates a data-driven diagram. In this example we have two things. We are generating a list of rectangles to create a column diagram based on some arbitrary data. And we also generate a series of coordinates for a polyline.

For simple use cases, you can code your own diagram like this. But if you need more complex diagrams then check out the <a href="https://d3js.org/"  target="_blank" rel="noopener">D3 library</a>. The D3 library uses SVG under to hood to create all sorts of diagrams.

<div class="code-flex">

```jsx
function Diagram() {
  const dataPoints = [3, 4, 7, 5, 3, 6];
  const sineWave = Array.from({ length: 115 })
    .map((item, index) => `${index - 55},${Math.sin(index / 20) * 20 + 10}`)
    .join(" ");

  return (
    <svg width="200" height="200" viewBox="-100 -100 200 200">
      {dataPoints.map((dataPoint, index) => (
        <rect
          key={index}
          x={index * 20 - 55}
          y={50 - dataPoint * 10}
          width="15"
          height={dataPoint * 10}
          fill="#CD803D"
        />
      ))}

      <polyline points={sineWave} fill="none" stroke="black" stroke-width="5" />
    </svg>
  );
}
```

</div>
