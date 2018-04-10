# 

  - [ ] Open a new boilerplate document, and save it as `lesson_6_1.html`
  
  - [ ] Add the following inside your `<script>` tag:
  
  ```javascript
  d3.select('svg')
    .selectAll('rect')
    .data( [12, 48, 6, 100, 10] )
    .enter()
    .append('rect')
    .attr('width', 10)
    .attr('height', d => d)
  ```
  - [ ] Answer some questions about the data
    
    * What is the data?
    
    ```javascript
    [12, 48, 6, 105, 10]
    ```
    
    * What is the *domain* of the data? (6–105)
    * What is the *range* of the data? (100) (? This may prompt some good discussion about scaling.)
    
    * There's only one box showing. Why is that? 
    (All the boxes are being drawn one on top of the other.) Demonstration:
      ```javascript    
          .style('opacity', 0.25)
      ```
    
  - [ ] Let's go through the code line by line.
  
    ```javascript
    d3.select('svg')
      .selectAll('rect')
      .data( [12, 48, 6, 105, 10] )
      .enter()
      .append('rect')
      .attr('width', 10)
      .attr('height', d => d)
    ```

    * Of particular note is the `enter()` function. Everything in the chain 
    following that describes a blueprint for how each data element should be
    represented. There is a similar function `.exit()`, not shown, which allows
    chainging of actions for an element if it is removed from the dataset. 
    Recall that D3.js can be used with dynamic data. All we have to do is update
    the data set, and the blueprint takes care of redrawing the vizualization.
    
    * Also note the `.attr('height', d => d)` line. In this case, `d` represents 
    each element of data, considered one at a time. It could be called anything,
    but by convention D3.js developers will use `d`.
    
    In programmer-speak, `d => d` is actually a function that means, “given some
    element *d*, return the value of that element.” We could double the height of
    rectangles by instead writing `d => d * 2`.
    
  - [ ] The boxes are still overlapping. What to do?
  
    ```javascript
    .attr('x', (d,i) => i * 10)
    ```
    
    * This separates the boxes. Much like the definition of `height`, we've defined
    a function, this time with two pieces of information: the data element and the 
    data index. The first is still `d` (which we could have named anything, but 
    convention makes our meaning easy to understand), because no matter what we 
    call it, D3 will pass the data element as the first parameter. The second 
    parameter, `i`, is the *index* of the data element (first, second, third, etc.),
    starting at 0. (Programmers nearly always count from zero.)
    
    * We don't use `d` in this simple function, but D3.js supplies arguments in 
    the same order every time. Because we want to use the index `i`, we also have 
    to ask for the data element `d`
    
    * Try create some separation between the boxes.
    ```javascript
    .attr('x', (d,i) => i * 10 + 20)
    ```
  
  - [ ] The boxes are being drawn down from the top of the Canvas. Can you modify 
    the `y` values to have them drawn up from a baseline 200px from the top?
    
    ```javascript
    .attr('y', d => 200 - d)
    ```
  
  - [ ] Experiment with some additional items that can be added to the blueprint
  for visualizing data elements. For example:
  
    ```javascript
    .style('fill', 'rgb(200,180,0)')
    ```
  
  - [ ] What if our data were too big to draw in our canvas? (Recall, we specified 
  the canvas as 500x500 pixels). Some sort of scaling would be helpful. D3.js can 
  scale the data automatically. The example below uses linear scaling, but [other 
  options](http://d3indepth.com/scales/) including logarithmic scaling, are possible.
    
    ```javascript
    .attr('height', d => yScale(d))
    .attr('y', d => 100 - yScale(d))
    ;
    
    var yScale = d3.scaleLinear().domain([0,105]).range([0,100]);
    ```
    
    * In this example, we wrote a new function `yScale`, and used D3's scale functions
    to define it dynamically.
    
    * It's better to defing the yScale function before we need it. Place that line *above* the d3 shape blueprint.
    
    * Notice that the scale definition required hard-coding the domain and range. 
      What if we didn't know the domain of the data? (Assume data are in the variable `data`.)
      
      ```javascript
      var yScale = d3.scaleLinear().domain([0,d3.max(data)]).range([0,100]);
      ```


  - [ ] The final code looks something like the following. The order of attributes and
    styles doesn't matter, so long as they are after `.append('rect')`:
  
    ```javascript
    var data = [12, 48, 6, 105, 10];

    var yScale = d3.scaleLinear().domain([0,d3.max(data)]).range([0,100]);
    
    d3.select('svg')
      .selectAll('rect')
      .data(data)
      .enter()
      .append('rect')
      .attr('x', (d,i) => i * 10 + 20)
      .attr('y', d => 100 - yScale(d))
      .attr('width', 10)
      .attr('height', d => yScale(d))
      .style('fill', 'rgb(200,180,0)')
    ;
    ```
    
