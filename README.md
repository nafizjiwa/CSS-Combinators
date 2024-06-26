# CSS-Combinators
What they are ? and Examples.

##### First,<br> 
CSS Selectors are used to select HTML elements on our web pages that we want to style.<br>

        SELECTOR {
        CSS Rule states which html element is selected to have the css property values inside the rule applied to them.
        }
 <br>
 
        h1 {
        color: blue;       //so style the h1 element with the text a color blue
           }
| The group of Selectors | What the selector styles | Example | 
| :--------------- | :---------------------------------------|:-----:| 
| Type Selector | Targets an html element   | h1 | 
| Class Selector | Targets an element with a specific value for its class attribute  | .box | 
| ID Selector | Targets an element that has a specific value for its id attribute   | #unique | 
| Attribute Selector | select elements based on the presence of a certain attribute on an element  | a[title] | 
| Attribute Selector | make a selection based on the presence of an attribute with a particular value | a[href="https://example.com"] | 
| Psuedo-classes | Styles a certain state of an element  | a:state | 
|  EG. a:state | selects an element only when it is being hovered over  | a:hover | 
| Psuedo-elements | select a certain part of an element rather than the element itself  | element::part of element | 
| element::part of element | selects the first line of text inside the element p | p::first-line | 

Example: <br>

| Simple Selectors | Example | Description |
| :--------------- | :-----: | :---------------------------------------|
| .class  | .intro | Selects *elements* with class = "intro" to style        |
| element.class | p.intro | Selects *all p elements* with class="intro"    |
| [attribute] | [target] | Selects elements with an attribute of target    |
| :active | a:active | Selects the active a link                             |
| ::after | p::after | Insert something after the content of each p element |
| ::before | p::before | Insert something before the content of each p element: |
##### Combine 2 or more selectors with a comma:

        h1, .special {
                  color: blue;
                }


# CSS Combinators
Combinators are selectors that combine other selectors in a way to give them a useful relationship to each other and the LOCATION of content in a document.<br>
There are 4 different combinators in CSS:<br>

    descendant selector (space)  ------> matches all elements that are descendants of a specified element.
                                                div p {} - selects all <p> elements inside <div> elements.
                               
    child selector (>)      -----------> selects all elements that are ONLY the CHILDREN of a specified element
                                                div > p {} - selectS <p> elements that are children of a <div>.
                               
    adjacent sibling selector (+)  ----> selects elements that is directly after another specific element
                                                    (must be in parent container)
                                        div + p {} - selects the first <p> element placed immediately after a closimg </div>.
                                
    general sibling selector (~)  ------> selects elements that are NEXT siblings of a an element
                                             div ~ p {} - selects <p> elements that are ONLY next
                                                        siblings of a <div> NOT BEFORE SIBLINGS div.
                                                        The div must precedes p element
                               

Between the simple selectors, we can include ONE OF THESE COMBINATORS.<br>
***SYNTAX:*** 

    simple selector (1 of 4 combinators here) simple selector<br>
#### Combined selectors
| Combinator with selectors  | Example       | What Combinator does                                                 | COMBINATOR USED           |
| :----:                 | :----------:      | :----                                                                        |  :----:  |
| .class1 .class2        |  .name .name2,  | Selects name2 elements having a descendant element of name                 |  SPACE or " "  |
| element > element     | div > p       | Selects all p elements where the parent is a div element                      |         >   |
| element + element     | div + p2      | Selects the 1st p element immediately after a closing div element          |         +  |
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



   

