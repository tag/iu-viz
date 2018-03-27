# 2 - Introduction to CSS

  - [ ] Review included slides (Lesson #1). Answer the following questions:
 
    * What does CSS stand for?
    * What is a selector?
    * Where are CSS declarations valid?
        - Inline, in a style attribute
        - Inside a `<style>` tag, within the `<head>`
        - In a separate file

  - [ ] There are three main types of selectors
  
    * `#Id` selectors
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

## Color and Color Theory

    - [ ] Describing colors ([see this explanation](http://colorizer.org))
    
      * RGB
          - Hex
          - `rgb(0–255, 0–255, 0–255)`
          - `rgba(0–255, 0–255, 0–255, 0.0–1.0)`
      * HSB
      * [Color keywords](https://www.w3.org/TR/SVG/types.html#ColorKeywords)
      
      * [Excellent introduction to describing color with HSB](https://learnui.design/blog/the-hsb-color-system-practicioners-primer.html)
    
    - [ ] Color pallettes
    
      * [ColorBrewer](http://colorbrewer2.org)
      * [D3JS colors](https://github.com/d3/d3-scale-chromatic)
        
    - [ ] Other color tools
    
      * [Adobe Color](https://color.adobe.com)
    
## Charts with HTML/CSS
    
    - [ ] It's possible to create charts using just HTML and CSS. (Give it a try?)
    
    - [ ] Creating charts manually is a lot of work. Better is to use a scripting language, like Javascript. See, e.g.,
    
      * https://css-tricks.com/making-charts-with-css/
      * Eric Meyer has [an old-school method](https://meyerweb.com/eric/css/edge/bargraph/demo-table.html), using tables
      * If you want to try adding scripts, experiment with [Google Charts](https://google-developers.appspot.com/chart/)