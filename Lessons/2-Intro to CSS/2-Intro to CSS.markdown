# 2 - Introduction to CSS

  - [ ] Review included slides introducing CSS (Lesson #1). Answer the following questions:
 
    * What does CSS stand for?
    * What is a selector?
    * Where are CSS declarations valid?
        - Inline, in a style attribute
        - Inside a `<style>` tag, within the `<head>`
        - In a separate file

  - [ ] There are three main types of selectors
  
    * `#id` selectors
    * `.class` selectors
    * `tagName` selectors 
    
  - [ ] PRACTICE:
  
    * Create a `<style>` tag inside your HTML file
    * Create a style definition using each type of selector
      ```html
      <head>
      <style type="text/css">
        #nav {
            border: 2px solid green;
        }
        
        .content {
            background-color: antiquewhite;
        }
        
        p {
            color: crimson;
        }
      </style>
      </head>
      ```
    
    - [ ] There are many other CSS attribtues you can play with. 
      Experiment with the following:
      
      * height  (use pt, px, em, ex, in, cm, mm, or %, among others)
      * width
      * font-size
      * color
      * background-color
      * border
      
    - [ ] TODO: CSS Box model
