# CSS-Combinators '+', '>','~'and'space'
What they are ?

##### First,<br> 
CSS Selectors are used to select HTML elements on our web pages that we want to style.<br>

        CSS SELECTOR {
               The CSS Rule containes properties and values to style the CSS selector.
        }
 <br>
 
        h1 {
        color: blue;       //Style the h1 color blue
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
Selectors that combine other selectors to show a relationship to each other and the LOCATION of content to be styled.<br>

***SYNTAX:*** 

     FORMER_ELEMENT (simple selector) [Combinator inserted here] TARGET_ELEMENT (simple selector) { style properties }

There are 4 different combinators in CSS:<br>

    DESCENDENT selector (space)  ------> Styles all element children (descendants) of the former element.
            
            div p {} - selects all <p> elements inside <div> direct or indirect (descendent) children elements.
                               
    CHILD selector (>)      -----------> Style ONLY the DIRECT children of the former element

            div > p {} - selectS <p> elements that are DIRECT children (not all children) of a <div>.
                               
    ADJACENT SIBLING selector (+)  ----> Styles ONLY elements directly after the former element.  (must siblings)
                                        
            div + p {} - selects the FIRST <p> element placed immediately after a <div>.
                                
     SIBLING selector (~)  ------> Styles all the NEXT siblings of a former element but NOT siblings before.
                                             
            div ~ p {} - selects <p> elements that are NEXT siblings of a <div>
                       The div must precedes p element
                               

#### Combinator selectors
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


---

## 🧾 CSS Selectors Cheat Sheet (2-Column Format)

### 🔹 Basic Selectors

| Selector     | Description         | Example                |
|--------------|---------------------|------------------------|
| `*`          | Universal selector  | `* { margin: 0; }`     |
| `element`    | Type selector       | `p { color: blue; }`   |
| `.class`     | Class selector      | `.btn { background: green; }` |
| `#id`        | ID selector         | `#header { height: 80px; }` |

| Selector     | Description         | Example                |
|--------------|---------------------|------------------------|
| `[type="text"]` | Exact match      | `input[type="text"]`   |
| `[href^="https"]` | Starts with    | `a[href^="https"]`     |
| `[href$=".pdf"]` | Ends with       | `a[href$=".pdf"]`      |
| `[href*="docs"]` | Contains        | `a[href*="docs"]`      |

---

### 🔹 Combinators

| Combinator   | Description         | Example                |
|--------------|---------------------|------------------------|
| `A B`        | Descendant          | `div p`                |
| `A > B`      | Child               | `ul > li`              |
| `A + B`      | Adjacent sibling    | `h2 + p`               |
| `A ~ B`      | General sibling     | `h2 ~ p`               |

| Tip          | Description         |
|--------------|---------------------|
| Use commas   | Group styles: `h1, h2, h3` |
| Combine      | Precision: `.menu li:first-child:hover` |
| Siblings     | Must share same parent |

---

### 🔹 Pseudo-classes

| Selector         | Description     | Example                |
|------------------|-----------------|------------------------|
| `:hover`         | On hover        | `a:hover`              |
| `:first-child`   | First child     | `li:first-child`       |
| `:nth-child(n)`  | nth child       | `tr:nth-child(odd)`    |
| `:not(selector)` | Excludes        | `div:not(.active)`     |

| Selector         | Description     | Example                |
|------------------|-----------------|------------------------|
| `::before`       | Before content  | `p::before { content: "Note: "; }` |
| `::after`        | After content   | `p::after { content: "."; }`       |
| `::first-letter` | First letter    | `p::first-letter`      |
| `::selection`    | Highlighted text| `::selection`          |

---







   

