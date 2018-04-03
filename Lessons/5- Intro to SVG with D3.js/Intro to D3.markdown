# Introduction to Javascript

  - [ ] This is not a Javascript course. It's not even a web development course. It's a visualization course. I don't expect (yet) that you'll be able to write a D3 visualzation from scratch. I *do* expect that you'll be able to read a working vizualization and be able to modify it for your purpose. Thus, some simple guidelines are in order.
  
    * Because we're modifying code in a formal language (Javascript, in this case), punctuation has a very specific meaning.
    * Whitespace is mostly added to make things easier to read.
    * Parentheses `()`, brackets `[]` and braces `{}` must always be paired and properly nested. `[ {} ]` is okay, but `[{ ]}` is not. Your text editor should help out by turning errors red.
    * Text (known as a *string*) is wrapped in double quotes `"Steve"`. Be careful to not copy/paste from Word (for example) or any other program that “helpfully” converts straight quotes to “smart quotes”. It will break your code.
    * Lists (properly called *arrays*) are described with square brackets `[ ]`
    * Objects are described with curly braces `{}`. Objects are lists of key–value pairs. There is a formal grammar that describes ["JavaScript Object Notation" (JSON)](http://json.org), which is modernly used to share data between applications, and is natively read by Javascript. *Keys* are always strings, but *values* can be anything, including a number, a string, a list, or even another object. 
    
    ```Javascript
    {
      "students": 25,
      "smartest": "Tom",
      "best-looking": {"first-name":"Tom", "last-name": "Gregory"},
      "most-common-ages": [28, 31]
    }
    ```
    * Items in a list `[]` or an object `{}` must be separated by a comma.
    * A semi-colon (not white space) is used to separate commands.
    
    ```Javascript
    var ages = [27, 28, 28, 30, 31, 31];
    var months = ['Jan', 'Feb', 'Mar'];
    ```

# Using D3.js

  - [ ] I will assume you've read (even if you didn't wholly understand) the day's assigned readings:
  
    * [“Let’s Make a Bar Chart Part III”](https://bost.ocks.org/mike/bar/2/), D3 Tutorials, Mike Bostock
    * [“From Zero to D3”](http://www.coppelia.io/2016/01/from-zero-to-d3/), Simon Reaper
    
    * Much of this lesson's content draws from *D3.js in Action (Second Edition)* by Elija Meeks, Manning Publications, 2017.
        
        - [Read Chapter 1 online](https://livebook.manning.com/#!/book/d3js-in-action-second-edition/chapter-1/93), if you like.

## Drawing SVG with D3.js

  - [ ] Start a new file with a [simple boilerplate](https://gist.github.com/tag/c21b2c242db7f8413120689e071c36a9). <script src="https://gist.github.com/tag/c21b2c242db7f8413120689e071c36a9.js"></script>
   
  - [ ] The D3.js library lets us programatically draw new items. Add a script tag to the bottom of your page, below the close of `<body>`. (See "d3-example1.html")
   
  ```html
  <script type="text/javascript">
  d3.select("svg")
   .append("line")
   .attr("x1", 20)
   .attr("y1", 20)
   .attr("x2", 400)
   .attr("y2", 400)
   .style("stroke", "black")
   .style("stroke-width", "2px");
  </script>
  ```
  
  - [ ] The SVG Canvas has the origin (0,0) at the top left. Height zero is at the top, and height 500 (in this case) is at the bottom.
  
  - [ ] We can use D3.js to draw circles or add text. (See "d3-example2.html")
  
  ```javascript
  d3.select("svg")
   .append("circle")
   .attr("r", 30)
   .attr("cx", 20)
   .attr("cy", 20)
   .style("fill", "yellow");
  d3.select("svg")
   .append("text")
   .attr("x", 20)
   .attr("y", 20)
   .attr("id", "text1")
   .style("fill", "rgb(190, 0, 0)")
   .text("Hello, world!");
  ```
  
  - [ ] Notice that these elements were drawn in the order we declared them. (Sometimes called the "z-order".) See what happens if you change the order. Draw the line last, for example.
  
  - [ ] Also notice that the style for color in SVG is `fill`, not `color` like it is for HTML elements.
  
  - [ ] From the browser, right click on one of the circles, and pick "Inspect Element ..." Notice how the SVG code looks like HTML? They are very similar. We could indeed [hand-craft the SVG](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Basic_Shapes) instead of writing Javascript to do it. The primary reason for drawing with Javascript instead of building the elements manually is that Javascript allows us to add a bit of interaction, which we can't accomplish with just SVG.
  
  - [ ] PRACTICE #1: Draw another circle in the bottom right corner (centered on `(400, 400)`). Write some text over the top of the circle. Give your circle the following attributes:
  
    * Radius 100
    * Fill color a shade of light blue

  - [ ] PRACTICE RECAP:
  
    * Did you get any errors?
    * Do you have more than one element with the same id? (If you copy/pasted the text element, did you remember to change the id?)
