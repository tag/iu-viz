# 1 - Introduction to HTML

  - [ ] Review included slides. Answer the following questions:
    * What does HTML stand for?
    * What is a tag?
    * What is the DOM?
    * What is the structure of the DOM?
    
  - [ ] Create a simple HTML file. Call it `practice.html`
    
    * Files named `index.html` (and `index.htm` or 
      `index.php`) get special treatment by the web server

  - [ ] In general, metadata goes inside the `<head>`, and content goes inside the `<body>`
  
  - [ ] `<title>` is a require tag. Give your page a title.
        Save and reload.
    
    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>Demo 1 - Hello World</title>
    </head>
    <body>
    </body>
    </html>
    ```
  - [ ] In HTML, extra whitespace is ignored or compressed when displayed by a browser.

  - [ ] Add some basic tags to the body 
  
    ```html
    <div class="content">
        <h1>Hello World!</h1>
        <p>Welcome to Bloomington!</p>
    </div>
    ```

      * Explain `<div>` and `<p>` tags
      * Explain `<h1>` through `<h6>` tags
  
  - [ ] Make some thing bold or italics 
  
    ```html
    <div class="content">
        <h1>Hello World!</h1>
        <p><em>Welcome</em> to <strong>Bloomington!</strong></p>
    </div>
    ```
    
  - [ ] In general, there are two difference types of (visible) tags: *inline elements* and *block elements*.
        
      * Are `<p>` tags block or inline?
      * What about bold and italics?
      * `<div>` and `<p>` are the most common block elements
      * `<span>` is a common, generic inline element
    
  - [ ] The `id` and `class` attributes may be applied to any element.
  
  - [ ] Create a nav bar, explain lists `<ul>` and links `<a href="...">`
  
  ```html
  <div id="nav">
      <ul>
          <li><a href="#">Link one</a></li>
          <li><a href="https://duckduckgo.com">Search</a></li>    
      </ul>
  </div>
  ```
  