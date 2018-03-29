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
      
      * `padding` is the space between the border and the content. You can use the `padding-top`, `padding-right`, `padding-bottom`, `padding-left` properties, or the shortcut property `padding`
      
      
      * `margin` is the space outside of the border separating the element from other elements. Much like with padding, You can use the `margin-top`, `margin-right`, `margin-bottom`, `margin-left` properties, or the shortcut property `margin`
      
      * `width` is just the content width, and by default doesn't include padding and border width. The same is true for `height`.
      
      * See, e.g, [the Mozilla Developer Reference explanation](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Box_model)
        or [a tutorial on the CSS box model](https://internetingishard.com/html-and-css/css-box-model/)
    
    - [ ] Positioning in CSS
    
       * Most elements flow to their natural position. You can maniupulate an element's position
         by altering the `position` attribute in CSS. Useful values are `relative` and `absolute`
         
         - Relatively positioned elements are offset from where they should be. For example:
           
           ```css
           #someElement {
               position: relative;
               top: 5px;
               left: -5px;
               /* The top left corner of this element is positioned 5px below and 5px to the left 
                  of where it would be naturally positioned. */
           }
           ```
         - Absolutely positioned elements are removed from the document flow 
           (meaning neighboring elements will act as if they're not there. You 
           may have to explicitly make space for them.) The absolute position is 
           determined from the top left corner of the closest ancestor element with
           a position defined.
         
           ```html
           <div id="parentElement">
              <div id="absElement"></div>
           </div>
           ```
           
           ```css
           #parentElement {
               position:relative;
               border: 1px solid blue;
           }
  
           #absElement {
               position: absolute;
               top: -10px;
               left: 10px;
               /* The top left corner of this element is positioned 10px above and 10px to the right 
                  of where it would be naturally positioned. */
               border: 1px dotted red;
           }
           ```
    