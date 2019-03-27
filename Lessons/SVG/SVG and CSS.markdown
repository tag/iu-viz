# Move SVG

## Grouping with `<g>`

The `<g>` tag wraps a group of shapes. Attributes applied to the group are
applied by default to its child elements.

Groups may also be referenced later with the `<use>` element.

See the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/g).

## Reusing elements with `<use>`

If you wish to reuse an element (including a group), first you must give it an
`id` attribute.

```svg
<svg viewBox="0 0 30 10"">
  <circle id="myCircle" cx="5" cy="5" r="4"/>
</svg>
```

See the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/use).

### The `id` attribute
An `id` attribute should be unique in the document. That is, no other element
should have the same `id`. It acts like a name for the element. Other elements can
refer to the named element, usually prefixing the `id` with `#`.

### The `href` element
Once some shape or group is uniquely defined with an `id`, it can be referenced
with a `<use>` element. A copy is made and placed at the specified `x` and `y`
coordinates. The element to be copied ("used") is specified with the `href`
element, with the hash symbol prefixing the copied element's `id`. For example:

```svg
<svg viewBox="0 0 30 10"">
  <circle id="myCircle" cx="5" cy="5" r="4"/>
  <use href="#myCircle" x="10" fill="none" stroke="red"/>
  <use href="#myCircle" x="20" fill="none" stroke="blue"/>
</svg>
```

Unfortunately, the `href` attribute (from SVG 2.0) doesn't work in Safari. If you need cross-browser compatibility, also use the older `xlink:href` attribute.

```svg
<svg viewBox="0 0 30 10"">
  <circle id="myCircle" cx="5" cy="5" r="4"/>
  <use href="#myCircle" xlink:href="#myCircle" x="10" fill="none" stroke="red"/>
  <use href="#myCircle" xlink:href="#myCircle" x="20" fill="none" stroke="blue"/>
</svg>
```

## Defining with `<defs>`

When making copies of an element with the `<use>` element, the original doesn't
have to be visible by default.

Any elements wrapped in `<defs>` are saved for later (re)use, for example, with
the `<use>` element.

See the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs).

# Exercises

1. Recreate *one* of the squares from the waffle chart in [this Makeover Monday example](http://www.vizwiz.com/2017/03/secret-of-success.html) (complete with text labels and colors).

2. What are some ways creating small repeated visualizations like this could
take advantage of `<defs>`, `<g>`, and `<use>`?

# Transforms

Transformations can be applied to any shape, but perhaps more usefully, they
may also be applied to the group element.

* `translate(x y)`: Move the shape by a particular offset
  ```svg
  <rect x="20" y="20" width="50" height="50" stroke="blue fill="none" />

  <rect x="20" y="20" width="50" height="50" fill="blue"
      transform="translate(75,25)" />
  ```

* `rotate()`: Rotates around a specified point. If no point is specified, the
  rotation occurs relative to the origin.
  ```svg
  <rect x="20" y="20" width="50" height="50" stroke="blue fill="none" />

  <!-- Rotation relative to origin (0,0) -->      
  <rect x="20" y="20" width="50" height="50" fill="blue"
      transform="rotate(30)" />

  <!-- Rotation relative to some other point, in this case, the box center: (45,45) -->      
  <rect x="20" y="20" width="50" height="50" stroke="red" fill="none"
      transform="rotate(30 45 45)" />
  ```

* `scale()`
* `skew()`
* `matrix()`

There's a good tutorial [here](http://tutorials.jenkov.com/svg/svg-transformation.html)
or [here](https://www.sarasoueidan.com/blog/svg-transformations/).


# CSS

Elements may have `id` and `class` attributes ...

It's sometimes good to separate style from structure. In particular, text
elements often require heavy styling, and adding style information within the
element can be messy.

## Using the `<style>` tags

The way we use CSS is almost identical between HTML and SVG.

```html
<style>
/* Comments in a CSS block are different from HTML or SVG comments */

#elementId { /* modifies the element with id="elementId" */
  fill: black;
  stroke-width: 5;
  stroke: red;
}

.elementClass { /* modifies all elements with class="elementClass" */
  fill: rgb(180,180,10);  /*Remember the different ways to do colors? */
  stroke: hsl(360, 90%, 50%);
}

circle {  /* neither a class nor an id; modifies all <circle> elements */

}
</style>
```

<!-- Although CSS can make positional adjustments for HTML, support for using SVG modify positional attributes is mixed. -->

Any style that can be applied within a `<style>` tag can be applied directly to
an element by using the `style` attribute.

## Properties are like attributes
In most cases, the CSS property name matches the SVG attribute name or is
similar. Transformations might work a bit differently.

There is a good partial list of CSS properties here:
http://tutorials.jenkov.com/svg/svg-and-css.html

The ones we are most likely to use are:

* `fill`: The fill color of text or shapes
* `stroke`: The outline color of text or shapes
* `stroke-width`: The width of the outline
