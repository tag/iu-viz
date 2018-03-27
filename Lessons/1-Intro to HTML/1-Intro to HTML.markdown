# 1 - Introduction to HTML

  - [ ] Review included slides. Answer the following questions:
    * What does HTML stand for?
    * What is a tag?
    * What is the DOM?
    * What is the structure of the DOM?
    
  - [ ] Create a simple HTML file. Call it `practice.html`
    
    * Files named `index.html` (or `index.htm`) get special treatment by the web server

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

  - [ ] PRACTICE: Add some basic tags to the body 
  
    ```html
    <div class="content">
        <h1>Hello World!</h1>
        <p>Welcome to Bloomington!</p>
    </div>
    ```

      * `<div>` is a generic block element tag
      * `<p>` is a block element that defines a paragraph of text
      * `<h1>` through `<h6>` tags are block tags that define headings (level 1 thru level 6 headings)
  
  - [ ] The inline tags `<strong>` and `<em>` and make some thing bold or italics, respectively.
  
    ```html
    <div class="content">
        <h1>Hello World!</h1>
        <p><em>Welcome</em> to <strong>Bloomington!</strong></p>
    </div>
    ```
    
  - [ ] In general, there are two difference types of content tags: *inline elements* and *block elements*.
        
      * Are `<p>` tags block or inline?
      * What about `<strong>` (bold) and `<em>` (italics)?
      * `<div>` and `<p>` are the most common block elements
      * `<span>` is a common, generic inline element
    
  - [ ] A tag may have one or more **attributes**. The `id` and `class` attributes may be applied to any element.
  
     * An `id` should be unique on a given page
     * Many elements can share the same class(es)
     * An element may have more than one class (separate multiple class names with a space)
     
     ```html
     <div id="mySpecialDiv" class="someClass anotherClass">Yet another div.</div>
     ```
  
  - [ ] There are many other tags you may find useful. For example, the 
    unordered list `<ul>` and list item `<li>` can be used to create a simple nav bar. 
    Hyperlinks are build with `<a href="...">...</a>`
  
    ```html
    <div id="nav">
        <ul>
            <li><a href="#">Link one</a></li>
            <li><a href="https://duckduckgo.com">Search</a></li>    
        </ul>
    </div>
    ```
  
