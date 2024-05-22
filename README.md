# CSS-Combinators
What they are ? and Examples.

# CSS Combinators
Combinators are selectors that combine other selectors and provide a useful relationship to each other and the locadtion of content in a document.

First, CSS Selectors are patterns used to select elements.<br>
    Example: <br>


| Simple Selectors | Example | Description |
| :--------------- | :-----: | :---------------------------------------|
| .class  | .intro | Selects *elements* with class = "intro"             |
| element.class | p.intro | Selects *all p elements* with class="intro"    |
| [attribute] | [target] | Selects elements an attribute of target    |
| :active | a:active | Selects the active a link                             |
| ::after | p::after | Insert something after the content of each p element |
| ::before | p::before | Insert something before the content of each p element: |
    
   
There are 4 different combinators in CSS:<br>

    descendant selector (space)  ------> matches all elements that are descendants of a specified element.
                                                div p {} - selects all <p> elements inside <div> elements.
                               
    child selector (>)      -----------> selects all elements that are the children of a specified element
                                                div > p {} - selects all <p> elements that are children 
                                                                                of a <div> element.
                               
    adjacent sibling selector (+)  --------> selects an element that is directly after another specific element.
                                                    (must be in parent container)
                                            div + p {} - selects the first <p> element that are placed
                                                                    immediately after <div> elements.
                                
    general sibling selector (~)  ---------> selects all elements that are next siblings of a specified element.
                                             div ~ p {} - selects all <p> elements that are next
                                                                     siblings of <div> elements.
                               

Between the simple selectors, we can include ONE OF THESE COMBINATORS.<br>
***SYNTAX:*** 

    simple selector (1 of 4 combinatores between) simple selector<br>
#### Combined selectors
| Combinator with selectors  | Example       | What Combinator does                                                                   | COMBINATOR USED           |
| :----:                 | ----------:      | :----                                                                        |  :----:  |
| .class1 .class2        |  .name .name2  | Selects name2 elements having a descendant element of name                 |  SPACE OR " "  |
| element > element     | div > p       | Selects all p elements where the parent is a div element                      |         >   |
| element + element     | div + p2      | Selects the 1st the p element that is immediately after div elements          |         +  |
| element1 ~ element2   | p ~ ul        | Selects every ul element that is preceded by a p element                      |          ~ |

An example hover over one element and highlight the other element. Here a cube is in a container div. <br>
If the cube is directly inside the container:<br>

    #container:hover > #cube { background-color: yellow; }
If cube is next to (after containers closing tag) the container:<br>

    #container:hover + #cube { background-color: yellow; }
If the cube is somewhere inside the container:<br>

    #container:hover #cube { background-color: yellow; }
If the cube is a sibling of the container:<br>

    #container:hover ~ #cube { background-color: yellow; }



   

