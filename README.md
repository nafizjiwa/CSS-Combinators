# CSS-Combinators '+', '>','~'and'space'
What they are ?

##### First,<br> 
Selectors select the HTML element to style.<br>

        h1 {CSS SELECTOR} {
               `properties: values` to style element 
               color: blue;
        }
 <br>
| The group of Selectors | What the selector styles | Example | 
| :--------------- | :---------------------------------------|:-----:| 
| Attribute Selector | select elements based on the presence of a certain attribute on an element  | a[title] | 
| Attribute Selector | make a selection based on the presence of an attribute with a particular value | a[href="https://example.com"] | 
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
Are Selectors that combine selectors to show a relationship between.<br>

***SYNTAX:*** 

     FORMER_ELEMENT [Combinator inserted here] TARGET_ELEMENT { 
             styles  }

4 different combinator selectors in CSS:<br>

    DESCENDENT selector (space)  ------> Styles all children ( or descendants) element of an element.
            
            div p {} - selects all <p> elements inside a <div>. Descendent children elements of a Div.
                               
    CHILD selector (>)      -----------> Style ONLY the DIRECT children of the former element

            div > p {} - selects <p> elements that are DIRECT children of a <div>.
                               
    ADJACENT SIBLING selector (+)  ----> Styles direct siblings elements of former element.
                                        
            div + p {} - selects the FIRST <p> element placed immediately after a <div>.
                                
     SIBLING selector (~)  ------> Styles  siblings ONLY after former element. (NOT siblings before)
                                             
            div ~ p {} - selects <p> sibling elements AFTER a <div>
                                               

#### Combinator selectors
|Combinator with selectors|Example|What Combinator does| COMBINATOR USED|
|:----:|:----------:| :----|:----:|
| .class1 .class2|.name .name2|Selects name2 elements having a descendant element of name|SPACE or " "|
| element > element| div > p| Selects all p elements where the parent is a div element|>   |
| element + element | div + p2| Selects the 1st p element immediately after a closing div element|+  |
| element1 ~ element2 | p ~ ul| Selects every ul element that is preceded by a p element|~ |

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

.main.content (with no space) targets elements with both main and content class.<br>

                <p class="main content">

.main .content (with a space) targets DESCENDENTS of .main  with a class of content.<br>

                 <p class="main">
                        <p class="content">

.content:last-child Targets the last element of a group of sibling and class of content.<br>

                <p class="content">
                        <p></p>
                        <p></p>
                        <p></p> --> target only this element

---

## 🧾 CSS Selectors Cheat Sheet 

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







   

