# Introduction to Scalable Vector Graphics

## Introduction

SVG stands for **S**calable **V**ector **G**raphics. Because the graphics are drawn as vectors, they can be scaled to any resolution without pixelation.

SVG images are actually defined as text files. The syntax is pretty straightforward.

## Tags are elements
_Elements_ in SVG (sometimes also called _nodes_), including the SVG declaration itself, are defined by _tags_. A tag is an element with angle brackets around the tag name.

```svg
<svg>
  <rect x="10" y="10" width="100" height="100" stroke="blue" fill="purple" />
</svg>
```

### Opening tags and closing tags
Some tags come in pairs, with an opening tag (e.g., `<svg>`) and a closing tag that starts with a slash and then repeats the tag name (e.g., `</svg>`). If a tag can be opened and closed, then other content may be nested between the two parts.

Other tags are “self-closing,” because it doesn't make sense to put content between the open and close tag. Self-closing tags have the closing slash as the _last_ character of the open tag.

Whitespace between tags doesn’t matter.

Look at the example below, and identify the opening tags, closing tags, and the self-closing tags.

```svg
<svg width="300" height="200">
  <g>
    <circle cx="50" cy="100" r="50" fill="red" />
    <circle cx="150" cy="100" r="50" fill="green" />
    <circle cx="250" cy="100" r="50" fill="blue" />
  </g>

  <rect x="0" y="150" width="300" height="50" fill="gray"/>
  <text x="65" y="185" font-size="30" text-anchor="top"fill="white">
    Primary colors
  </text>
</svg>
```

### Elements may have attributes
Every element has a _tag name_, which is the first word in the element. Many elements also have _attributes_. Attributes are (almost always) followed by a value, which should be wrapped in double quotes (`""`).

In the following example, the tag represents a rectangle. The tag name is `rect`. The rectangle has several attributes, including `x` and `y` coordinates, and `height` and `width` attributes.

## A blank SVG
All SVG documents begin with a `<svg>` opening tag, and end with the corresponding closing tag `</svg>`. The `height` and `width` attributes are measured in pixels, and define the canvas the image will be drawn on. By default, the background of a SVG image is transparent.

```svg
<svg width="300" height="200">

</svg>
```
### Coordinate system
It may seem a bit counter-intuitive, but the _origin_ of the canvas (the place where `x="0"` and `y="0"`) is in the top left. The y-values increase going down from the top left, while the x-values increase going to the right from the origin. It’s okay for values to be negative (it just means they won't be shown by default).

## Shapes

There are several shapes that can be used. The Mozilla Developer Network (MDN) has some great [tutorials][MDN tutorial] and [documentation][MDN documentation] to help.

* [`<circle>`][circle]
* [`<ellipse>`][ellipse]
* [`<rect>`][rect]
* [`<polygon>`][polygon]
* [`<line>`][line]
* [`<path>`][path]

`<line>` and `<path>` are, of course, not shapes (as such), but behave similarly. The method for describing a `<path>` is a little more complicated, but the [MDN tutorial][path_tutorial] walks through it well.

[circle]:https://developer.mozilla.org/en-US/docs/Web/SVG/Element/circle
[ellipse]:https://developer.mozilla.org/en-US/docs/Web/SVG/Element/ellipse
[rect]:https://developer.mozilla.org/en-US/docs/Web/SVG/Element/rect
[polygon]:https://developer.mozilla.org/en-US/docs/Web/SVG/Element/polygon
[line]:https://developer.mozilla.org/en-US/docs/Web/SVG/Element/line
[path]:https://developer.mozilla.org/en-US/docs/Web/SVG/Element/path
[path_tutorial]:https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths

[MDN documentation]:https://developer.mozilla.org/en-US/docs/Web/SVG
[MDN tutorial]:https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial

### Shape edges

There are a few basic stroke attributes:

* `stroke`, which specifies a color

* `stroke-width`, which specifies how thick the line is

* `stroke-linecap`, which controls the shape of the ends of the lines. May be one of `butt` (straight edge), `square` which is similar, but stretches the stroke slightly beyond the actual path by half the stroke-width, and `round`, which (unsurprisingly) produces a rounded effect with a radius controlled by the stroke-width.

  ```svg
  <svg width="160" height="140" xmlns="http://www.w3.org/2000/svg"   version="1.1">
    <line x1="40" x2="120" y1="20" y2="20" stroke="black" stroke-  width="20" stroke-linecap="butt"/>
    <line x1="40" x2="120" y1="60" y2="60" stroke="black" stroke-  width="20" stroke-linecap="square"/>
    <line x1="40" x2="120" y1="100" y2="100" stroke="black" stroke-  width="20" stroke-linecap="round"/>
  </svg>
  ```

* `stroke-linejoin` to control how the joint between two line segments is drawn, one of `miter`, `round`, or `bevel`

  ```svg
  <?xml version="1.0" standalone="no"?>
  <svg width="160" height="280" xmlns="http://www.w3.org/2000/svg"   version="1.1">
    <polyline points="40 60 80 20 120 60" stroke="black" stroke-width="20"
        stroke-linecap="butt" fill="none" stroke-linejoin="miter"/>

    <polyline points="40 140 80 100 120 140" stroke="black" stroke-width="20"
        stroke-linecap="round" fill="none" stroke-linejoin="round"/>

    <polyline points="40 220 80 180 120 220" stroke="black" stroke-width="20"
        stroke-linecap="square" fill="none" stroke-linejoin="bevel"/>
  </svg>
  ```

See the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Fills_and_Strokes) for examples.

## Colors

* Fill attribute?
* Stroke attribute?

## Practice!

1. Draw an ice cream cone with two scoops. Use `<polygon>` for the cone and `<circle>` for the scoops on top. Use colors to make your cone look delicious.

2. Draw a Cartesian axis (an x & y coordinate axis). Make each axis go from [-50,50], with tick marks every 10 pixels. Add `"x"` and `"y"` as text labels.

3. Draw the IU logo. Although it can be done as a single `<path>`, it's probably easier to start

# Other Tools

Okay, so you don't always have to draw SVG by hand. Many decent online and desktop tools exist to help you. You can use a GUI to make drawings, and export them in SVG format.

* https://vectr.com

## For next time

* Grouping with `<g>`
  - `transform="translate(0, 163)"`
