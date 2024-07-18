# CSS-Combinators '+', '>','~'and'space'
What they are ?

##### First,<br> 
CSS Selectors are used to select HTML elements on our web pages that we want to style.<br>

        CSS SELECTOR {
               The CSS Rule within curly braces states the css property and values to style the CSS selector.
        }
 <br>
 
        h1 {
        color: blue;       //style the h1 element with the color blue
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


# CSS Combinators '+', '>' '~' and 'space'.
Are Selectors that combine other selectors to show a relationship to each other and the LOCATION of content to be styles in the document.<br>

        former_element + target_element { style properties }
There are 4 different combinators in CSS:<br>

    DESCENDENT selector (space)  ------> Styles all element children (descendants) of the former element.
                                                div p {} - selects all <p> elements inside <div> directl or indirect children elements.
                               
    CHILD selector (>)      -----------> selects all elements that are ONLY the CHILDREN of a specified element
                                                div > p {} - selectS <p> elements that are children of a <div>.
                               
    ADJACENT SIBLING selector (+)  ----> selects elements that is directly after another specific element
                                                    (must be in parent container)
                                        div + p {} - selects the first <p> element placed immediately after a closimg </div>.
                                
    GENERAL SIBLING selector (~)  ------> selects elements that are NEXT siblings of a an element
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

### FINAL EXAMPLE
----
|CSS STYLE|
|---|
|.main {|
|        margin: 20px auto;|
|}|          
|.content {|
|margin: 10px auto;|
|}|


        Using .main.content (with no space) will target any elements that have a class of both main and content.
<br>

        Using .main .content (with a space) will target any elements with a class of .content
        that are descendants of an element with a class of .main. ALL DESCENDENTS OF .main.
<br>

        If you are trying to target the final element with a class of content use the `:last-child` pseudo-class.
        This pseudo-class represents the last element of a group of sibling elements.

|CSS STYLE|
|---|
|.content:last-child {|
|        margin-bottom:0px;|
|}| 






   

