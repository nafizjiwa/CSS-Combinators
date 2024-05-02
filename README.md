# CSS-Combinators
What they are ? and Examples.

# CSS Combinators
Combinators explain the relationship between the selectors they surround.<br>


First, CSS Selectors are patterns used to select elements.<br>
    Example: <br>
    
| Simple Selectors | Example | Description |
| :---- | :----: | ----: |
|  .class  | .intro | Selects all elements with class = "intro" |
| element.class | p.intro | Selects all <p> elements with class="intro" |
| [attribute] | [target] | Selects all elements with a target attribute |
| :active | a:active | Selects the active link |
| ::after | p::after | Insert something after the content of each <p> element |
| ::before | p::before | Insert something before the content of each <p> element: |
    
   

Between the simple selectors, we can include a combinator. There are 4 different combinators in CSS:

    descendant selector (space)
    child selector (>)
    adjacent sibling selector (+)
    general sibling selector (~)

| Header1 | Header2 | Header3 |
| :---- | :----: | ----: |
| R1C1 | R1C2 | R1C3 |
| R2C1 | R2C2 | R2C3 |

.class1 .class2            .name1 .name2	             - Selects all elements with name2 that is a descendant of an element with name1
element>element	           div > p	                   - Selects all <p> elements where the parent is a <div> element
element+element	           div + p	                   - Selects the first <p> element that is placed immediately after <div> elements
element1~element2	         p ~ ul	                     - Selects every <ul> element that is preceded by a <p> element

   

