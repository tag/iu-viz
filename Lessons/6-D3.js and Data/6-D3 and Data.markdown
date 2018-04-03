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
    * What is the *range* of the data? (100)
    
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
  
  - [ ] TODO:
  ```javascript

  .style('opacity', 0.25)
  .attr('x', (d,i) => i * 10)
  .attr('y', d => 105 - d)
  .style('fill', 'rgb(200,180,0)')
  ```
  
  - [ ] TODO:
  ```javascript
  .attr('height', d => yScale(d))
  .attr('y', d => 100 - yScale(d))
  ;
  
  var yScale = d3.scaleLinear().domain([0,24500]).range([0,100])
  ``` 

    