# CSS-Combinators '+', '>','~'and'space'

##### First,<br> 
Selectors select the HTML element to style.<br>

        h1 {CSS SELECTOR} { --> selects h1 element 
               `properties: values` to style element 
               color: blue;
        }
 <br>
#### Attributes are things like href, title, alt, etc., defined in HTML tags.
| Attribute Selectors | What the selector styles | 
| :--------------- | :-------------------|
| [attribute] | Selects elements that have a this specific attribute |
|a[title] → Styles any <a> tag that has a title attribute.|
|input[required]| targets all <input> elements that include the required attribute|
| [attribute="value"] | selects elements that have a specific attribute with an exact value|
|a[href="https://example.com"] |This targets only <a> elements whose href exactly matches "https://example.com"| 
### Examples of Common HTML Attributes
|Attribute|	Used In	Purpose|
|href|	<a>|	Specifies the link destination|
|src|	<img>|	Specifies the image source|
|alt|	<img>|	Provides alternative text|
|title|	Any tag|	Tooltip text on hover|
|type|	<input>|	Defines input type (e.g., text, checkbox)|
|required|	<input>|	Marks field as mandatory|
        ---
| Pseudo-element Selector |let you style parts of an elements | 
| :--------------- | :-------------------|
| element::first-line | Lets you style first line of the element|
|p::first-line | Targets the first line of visible text inside a block-level element like <p>|

#### Example:

| Simple Selectors | Example | Description |
| :--------------- | :-----: | :---------------------------------------|
| .class  | .intro | Selects *elements* with class = "intro" to style        |
| element.class | p.intro | Selects *all p elements* with class="intro"    |
| [attribute] | [target] | Selects elements with an attribute of target    |
| :active | a:active | Selects the active a link                             |
| ::after | p::after | Insert something after the content of each p element |
| ::before | p::before | Insert something before the content of each p element: |
##### Combine 2 or more selectors with a comma:

        h1, .special { }


## CSS Combinators '+', '>' '~' and 'space'.
Are Selectors that combine selectors to show a relationship between.<br>

***SYNTAX:*** 

     FORMER_ELEMENT [Combinator inserted here] TARGET_ELEMENT { 
             styles  }

4 different combinator selectors in CSS:<br>

    (space) or " " DESCENDENT selector   ------> Styles all children ( or descendants) element of an element.
            
            div p {} - selects all <p> elements inside a <div>. Descendent children elements of a Div.
                               
    (>) CHILD selector       -----------> Style ONLY the DIRECT children of the former element

            div > p {} - selects <p> elements that are DIRECT children of a <div>.
                               
    (+) ADJACENT SIBLING selector   ----> Styles the immediate NEXT sibling element of former element.
                                        
            div + p {} - selects the 1st <p> element immediately after a <div>.
                                
    (~) SIBLING selector   ------> Styles  ALL siblings AFTER former element.
                                             
            div ~ p {} - selects <p> sibling elements AFTER a <div> or selects all p 

|Combinator with selectors |Example|
|:----:|:----------|
|h1 p:|selects any p inside an h1|
|h1 ~ p: |selects all p siblings of h1, not just the first (have same parent)|
|h1 + p: |selects 1st p sibling of h1 (have same parent)|
|h1 > p: |selects direct child p elements. Only if p is nested inside h1.|

### EXAMPLEs

Hover over one element and highlight the other element. A cube is in a container <div class="container"></div> <br>
If the cube is directly inside the container:<br>

    #container:hover > #cube { background-color: yellow; }
If cube is next to (after containers closing tag) the container:<br>

    #container:hover + #cube { background-color: yellow; }
If the cube is somewhere inside the container:<br>

    #container:hover #cube { background-color: yellow; }
If the cube is a sibling of the container:<br>

    #container:hover ~ #cube { background-color: yellow; }

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
<div class="container">
    <h2>Heading</h2>
    <p>Paragraph directly after h2</p>
    <p>Another paragraph inside container</p>
    <ul>
      <li>List item 1</li>
      <li>List item 2</li>
    </ul>
  </div>


 /* Descendant selector */
    .container p {                  ---> Styles all <p> inside .container (descendant).
      color: blue;
    }

    /* Child selector */
    .container > h2 {               ---> Styles <h2> only if it's a direct child of .container
      color: green;
    }

    /* Adjacent sibling selector */
    h2 + p {                        ---> Styles the first <p> that comes immediately after <h2>
      font-weight: bold;
    }

    /* General sibling selector */
    h2 ~ ul {                     ---> Styles all <ul> that are siblings of <h2> and come after it.
      background-color: #f0f0f0;
    }
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







   

