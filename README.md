# html_and_css

## Omnifood Project README in starter/07-Omnifood-Desktop

* https://www.udemy.com/course/design-and-develop-a-killer-website-with-html5-and-css3/
* Author's Repo: https://github.com/jonasschmedtmann/html-css-course
* Flexbox and CSS Grid: https://github.com/nuthanc/angular_advanced_fast/blob/main/flexbox_css_grid/README.md
* Author's Instruction in **author.md**
* **Check the Pdf** as it has all the notes

### Resources

* https://codingheroes.io/resources/
* Download Course Resources from 1st section

### Static and Dynamic Sites

* Static: Files served as is
  * Just Web Server is required
* Dynamic: Files generated dynamically(assembled on server) and served
  * Interaction with Database, Backend(Node, Python, PHP)

### HTML Fundamentals

* Anatomy of an html element
  * Opening tag
  * Content: Content of the element or another element(Child element)
    * Some elements like img have no content
  * Closing tag
* Doctype specifying the version of the html
* html element containing head and body
* Headings from h1 to h6
* Each page should have **1 h1 heading**
* **strong**(semantic meaning) instead of **b**
* **em**(emphasize) instead of **i**
* **img** element
  * src attribute in img element
  * alt attribute important in img element(Screen readers)
  * width attribute automatically takes value in px(No need to specify explicitly)
  * VS Code provides width and height at the bottom for Opened images(Open post-img.png and check)
* **lang** attribute for html for specifying the language
* **meta** element with charset of UTF-8(Characters we use in English)
* Open link in new tab using target="_blank"
* External links using url and internal links by pointing to the html file
* href of **#** for going to the top of the Current Page
* **Structuring our Page**
  * nav element for Navigation containing the anchor elements
  * header element for Top Part of a Web Document or anything
    * header can be within article also
  * article element for Blog Post
  * aside: Secondary information that complements any other information(like article), also for Sidebar
  * footer element
* HTML entity(&copy;) using &(name);
* Semantic HTML: Elements have Meaning or Purpose
  * strong
  * em
  * nav instead of div for Navigation elements
  * header instead of div
  * SEO and accessibility

### Challenges

* Challenge 2: https://codepen.io/nuthan-chandra/pen/PoaewNP

### CSS

* Inline CSS
  * Inside the HTML element using `style` attribute
* Internal CSS
  * Inside the head with `style` element
* External CSS with a css file(style.css) and link it using link
  * `<link href="style.css" rel="stylesheet">`

### CSS Properties

* line-height
  * Space between the lines
  * Based on font-size, 1.5 means 1.5 times that of the font-size
  * Default 1
* Inheritance
* text-align: center
  * Center of its parent element
* font-size 16px by default
* Descendant selector
  * footer p
  * But not a good practise as it encodes the html structure into our CSS
* Separator is dash(-),e.g class="related-author"
* id to be used only once
* ul for related author, we used **class instead of id** even though it was selecting just one ul because we are **preparing for the future(potential changes)**
  * use class in real life scenario
* Boxes(Elements) containing multiple child elements are placed on top in CSS(Author's coding convention)

### Colors

* RGB Model
  * Each of the base colors take a value between 0 and 255
  * rgb(0, 255, 255)
  * RGB with transparency("alpha") rgba(0,255,255,0.3)
  * Color Picker
* Hexadecimal Notation
  * 0 to ff(255 in hexademical) for RGB respectively
  * #00ffff
  * Shorthand for the above: #0ff
* In Practice, we mostly use Hexadecimal values and rgba is used when we need transparency
* Shades of Grey
  * When colors in all 3 channels are the same, we get a grey color. For Ex
    * rgb(0,0,0)
    * rgb(69, 69, 69) also as #444444 or #444
    * rgb(183, 183, 183) also as #b7b7b7
    * #ffffff

### Pseudo Classes

* li:first-child instead of having classes to all first items
  * All li elements that are the first child element of its parent element
* Same semantics for last-child and nth-child(3)
* nth-child also takes keywords like odd, even etc
* Misconception about first-child pseudo-class
  * article p:first-child won't select the p because it is not the first child of article
* first-child, last-child are perfect for situations where all the child elements are same like ul and ol

### Styling hyperlinks

* Simply selecting *a tag* and styling it is not a best practice
* Target pseudo class of *a tag*
* a:link targets actual links(with href)
* a:visited targets visited
* a:hover when hovered
* a:active when clicked
* LVHA in this order

### Chrome Devtools

* Shortcut: Cmd + Option + I

### Conflicts Between Selectors

* When there are multiple selectors for the same element
  * All of them are applied
  * But conflicting ones will be decided on priority
* Highest priority
  * Declarations maked by **!important** keyword(Last resort)
  * Inline styles(style attribute in html)
  * ID selector
    * Multiple: Last selector
  * Class or Pseudo-class selector
  * Element selector
  * Universal selector
* Hover over selectors in VS code to get the specificity
* Write selectors as simple as possible
  * Don't have too many nestings, classes or ids for the same element

### CSS Inheritance

* *strong element* which is inside *p* gets the style of the p element
* Some Properties get inherited from Parent to Child elements
* Not all Properties get inherited, **mostly text related**
  * font-family, font-size, font-weight, font-style, color, line-height, letter-spacing, text-align, text-transform, text-shadow, list-style etc
* For e.g: border doesn't get inherited
* Like setting properties like color for body element gets inherited by all its child elements
* Inherited values have the lowest priority
* Universal Selector
  * Properties like color are inherited(so can be applied in body)
  * Used for properties we want to apply for all elements but which does not get inherited
  * E.g border-top on all elements using Universal Selector
  * Lowest priority
  * No Inheritance involved in Universal selector

### CSS Challenge

* Author's link: https://codepen.io/jonasschmedtmann/pen/zYNyMJL/256706a9de79baf1bd19abcb68e820d9

### CSS Box Model

* Each element can be seen as a Rectangular box
* Content: Actual content of the element
  * Text, Images, Table, Video etc
  * height and width using css
* Border: A line around the element, but still **inside of the element**
* Padding: Invisible space around the content, inside of the element
* Margin: Space **outside** of the element, between elements
* Fill Area: Area that gets filled with background color or background image
  * Text and Images inside the Content Box
  * But the same doesn't apply for Background image or color
    * It applies for Content, Padding and Border

### Element Height and Width Calculation

* If height or width is not specified, it is implied based on the **Content**
* Final element width = left border + left padding + width + right padding + right border
* Final element height = top border + top padding + height + bottom padding + bottom border
* The above is default behavior

### Using Margin and Paddings

* Shorthand for top and bottom for first value and left and right for second value
```css
.main-header {
  padding: 20px 40px;
}
```
* Global reset
  * Cannot be done in body, because margin is not inherited(not a text based property)
  * Use universal selector and set margin and padding to 0
    * It's also very easy to override if required later
* It is common to use **margin-bottom** to create vertical space instead of margin-top
* ul and ol need margin-left to show the bullet points and the numbers(Because of universal selector styles)
* **Collapsing margins**
  * When 2 margins occupy the same space, only one of them(larger of the 2) is visible
  * Ex: For h3 below p, h3 margin-top 40px and p margin-bottom 15 px, only 40px takes effect

### Adding Dimensions(height and width)

* height and width are for the content
* But final width and height takes into account the padding and border as well
* width specified in css overrides width attribute(in html) of img
* In html, height and width attributes were set for the image
  * If only width is set in css, the aspect ratio goes a little weird, since it overrides width but height is still taken from the attribute
  * height: auto fixes the aspect ratio when only width is specified
* **When any one of them(height or width) is only given in css, then the other will adapt automatically in order to get the original Aspect ratio of the image**
* If we use Percentages, it is Percentage of Width of the *Parent Container*
  * Parent of post-img class element is the header and its width is the entire width of the Page

### Centering our Page

* **Put all of our content into a container element and give it a width**
* The Child elements cannot be wider than the Parent element(Only as large as the Container element)
* Then margin-left: auto and margin-right: auto
* auto for Browser to calculate and adjust automatically
* margin: 0 auto; Author did this
  * I didn't feel top and bottom necessary as we had only given width to the container
  * Height will be the size of the Page

### Challenge

* I had added extra div as container when existing article container could have been used

### Types of Boxes

* Inline boxes: Occupies space exactly what they need and don't create line breaks
  * **height and width do not apply**
  * **Padding and margin** only **applied horizontally(left and right)**
  * For padding, it looks like some space is created vertically as well, but the Content remains exactly in the same place(In block case, it would have moved down)
  * E.g: strong, a, em, button
* Block: Occupies all the space that they can(100% of parent element's width) and create line breaks after them
  * Most of the HTML elements are block level elements
  * E.g: p, div, h2, li, body, main, header, footer, section
  * If height is set, the element doesn't expand to fit the content
    * So it is commented in main-header
* Inline-Block: Looks like inline from the *outside*, behaves like block-level on the *inside*
  * Occupies only content's space and causes no link-breaks
  * Width, Height, Padding and Margin Apply
  * E.g: img

### Absolute Positioning

* Normal Flow: Default Positioning
  * Elements are simply laid out according to their order in the HTML code
  * Or by setting it to *position: relative*
* Absolute Positioning: Element is removed from the normal flow
  * No impact on surrrounding elements, might overlap them
  * We use top, bottom, left or right to offset the element from *its first relatively positioned parent container*
  * position: absolute
* Ctrl + Cmd + Space for Emoji on MAC and Wind + . in Windows
* *By default, it's positioned in relation to the Viewport*(visible part of the page)
* Check Like button's positioning
* But we don't want its positioning from Viewport, we want in relation to some other **parent** element, so we set that parent's position as relative
* We want it from the Page and that is the body element, so we set body's position to relative

### Pseudo-elements

* Don't exist in HTML, but that we can still select and style in css
* Examples
  * First letter in a paragraph
  * First line in a paragraph
* Written using 2 colons(h1::first-letter)
* + for Adjacent Sibling selector(Immediately following the first and has the same parent)
* ::after pseudo-element creates a Pseudo element that will automatically be the very last child of the selected element
  * Very useful for small cosmetic style for which we don't have to add a new element to the HTML
  * Ex: TOP article
  * Mandatory property is the **content** property
* By default, **any Pseudo-element is an inline element**
* ::before pseudo-element creates a Pseudo element that will automatically be the very first child of the selected element

### Developer Skill

* Google for things like "css center anchor elements"
* Also check out documentation like "css mdn text align"
* *HTML Validator* and *Diff Checker*
* In CSS, keep selectors simple. Use Inspect from Browser

### Coding Challenge 3

* Horizontal padding double that of vertical
* Author used display: inline-block for sale class
  * It was not necessary when I added position: absolute

### Layouts

* Layout: Way in which text, images and other content is placed and arranged on a webpage
* Layout gives the page a visual structure, into which we place our content
* Page Layout and Component Layout
  * Bigger layout in the Page
  * Made out of small Components
* Check pdf for more

### 3 Ways of Building Layouts

1. Float Layouts: float css property, but this is outdated
2. Flexbox: 1-dimensional row
3. CSS Grid: 2-dimensional grid

### Using Floats

* With use of Floats, it is taken out of the Normal flow just like the Absolutely Positioned element
* Difference is **Text and Inline** elements will float around it
* The container will not adjust its height to the element
* For the element very next to the img, which is p, in our case, it is starting behind the img
  * It's as if the img is not on the page
  * So large padding and margin is required
  * To fix this, make the p element also as float: left
  * float: right would make it right side of the container
* A floated element can still add margins around it
* If we add float to h1 and nav, then the main-header(container) has zero height(Collapsing) now because all of its children are floated(Removed from the normal flow)
  * It is as if it has no child elements
  * The only reason the background color is still visible is because of the padding

### Clearing Floats

* Add an element to the container element and clear the floats
* clear works only on block elements
* A neat trick is to use ::after pseudo element and clear it from there. Note we need to make after a block level element
  * clearfix hack. Give all the parent a class of clearfix

### Building a Simple Float Layout

* Giving background-color makes it easier to see the boxes
* Need to change the width of article and aside as they are block elements and occupy 100% of the available width of the container
* We do not want footer to float around aside, so clear in it
* Instead of giving margin-right, decrease the article's width

### box-sizing: border-box

* Giving padding left and right to *aside* made it too big and now it reaches within article, so it comes down
* Final element width = left border + left padding + width + right padding + right border
* Final element height = top border + top padding + height + bottom padding + bottom border
* The above is default behavior
* box-sizing: border-box makes the width and height from one side of the border to the opposite side
* Any padding and border width or height reduces the Content's width or height
* Box-sizing is applied to every single element by specifying in Universal Selector
  * It is not specified in body as it does not get inherited

### Challenge using Layouts

* Author used float: left for both

### Introduction to Flexbox

* Flexbox and CSS Grid link: https://github.com/nuthanc/angular_advanced_fast/blob/main/flexbox_css_grid/README.md
* Slide is also very good
* Flexbox used for building 1-dimensional layouts
* Flex Container and Flex Items
* Each of the Items occupies **exactly the space it needs for its Contents**
* Vertically in our case all the Items are as tall as the Tallest element(One item given height of 150px) of the Flex Item
* Centering is very easy with align-items: center
* **Default of align-items is stretch**
* Flex Container and Flex Items Properties
![flex](img/flexbox.png)

### Spacing And Aligning Items

* Checkout the flexbox image
* For adding space between flex-items without space-around, we can use margin
* Or gap in the flex-container

### The flex property

* flex property shorthand for flex-grow, flex-shrink and flex-basis
* Default for flex-grow is 0, flex-shrink is 1 and for flex-basis it's auto
* flex-basis for width of the items and when the Content is larger, it fits the Content
  * Need to remove *gap* to see the flex-basis to what is being set
* Flexbox shrinks an item to fit it in the Container even when the flex-basis is too high
  * Setting flex-shrink: 0(no), then allows it to have the width specified in flex-basis
* flex-grow: 1(yes) for all elements, fills up the available space evenly between the remaining items
  * It doesn't have to be 1, it can be 1 and 2 for the other. 
  * The one having 2 will be double the size of Available empty space than the other ones
* Always use flex property

### Adding Flexbox to Our Project

* Manually giving article a flex-basis of 825px(which involves calculation) defeats the purpose of having flex-box
* So we just use flex-grow to 1 to take up available space
* Add flex: 1 to both the layouts to have equal width

### Introduction to CSS Grid

* The basic difference between CSS Grid Layout and CSS Flexbox Layout is that flexbox was designed for layout in one dimension - either a row or a column. Grid was designed for two-dimensional layout - rows, and columns at the same time
* Grid Container and Grid Items
* display: grid to the Grid Container
* Just like flexbox, the elements stretch across the entire cell
* Each of the Items occupies **exactly the space it needs for its Contents vertically by default**
* Vertically in our case all the Items are as tall as the Tallest element(One item given height of 150px) of the Grid Item
* Horizontally it will stretch
* grid-template-columns to define as many width columns as we want
* Rows would be accommodated accordingly after all the columns are placed
* Rows width can also be specified using grid-template-rows
* gap for Grid gap. There is also separate gaps for row and column
  * row-gap and column-gap
* We just have Row Axis and Column Axis(No flex-direction kind of property)
* Grid lines: Separate rows and columns
  * Use Chrome Inspect and click on grid
  * Grid lines for rows: #rows + 1
  * Grid lines for cols: #cols + 1
* Intersection of Grid lines produce Grid Cells
* Gutters are Gaps(row and column-gap)
* Grid track of row and column
![grid](img/grid.png)
  
### Sizing Grid Columns and Rows

* Using px is rigid
* We will use fr unit
* grid-template-columns: 150px 300px 200px 1fr;
  * For last column to take up all available empty space
  * Similar to setting flex: 1
* **auto** keyword to take size to fill exactly its content
* repeat keyword to repeat the unit n number of times
* Explicit rows and Implicit rows
  * Explicit because we explicitly specify the size for them in grid-template-rows
  * Implicit when it exceeds the space and is added automatically
* With 1fr for all, all the Items are as tall as the Tallest element(One item given height of 150px) of the Grid Item

### Placing and Spanning Grid Items

* Using grid-column and grid-row on the Grid Itemsa
* Use Dev Tools to see the numbers and use them for start and end
* grid-column: 2 / 3
* If the second value is just +1, it can be omitted
* For the above, we can write just, grid-column: 2
* The second value is to span till
* We can use span keyword
* grid-column: 1 / span 3; which is equivalent to grid-column: 1 / 4;
  * Start at 1 and span across 3 cells
* -1 to span till the end (grid-column: 1 / -1;)

### Aligning Grid Items and Tracks

* Aligning Grid Tracks(Columns and Rows) inside the Grid Container(Only possible if it is smaller than the Grid Container)
* Just like flexbox, you have justify-content
* align-content instead of align-items for centering vertically
  * space-between, start and end
* Now for aligning within the tracks
  * align-items for vertically
  * justify-items for horizontally
* For overriding individually,
  * align-self and justify-self

### Building a Simple CSS Grid Layout

* CSS grid works perfectly well with Flexbox
* So all the 1D layouts, continue using Flexbox
  * Like Author
  * Navigation
* Overall Page layout is 2D, so we use Grid there
* Just with display: grid, it display in rows by default
* Used grid-template-columns of 2 and then for header and footer stretched it all the way
* We use 300px for the aside but remaining space we just use 1fr to take up available empty space
* The rows take the space required for its content
* So it's **pretty common to only define grid-template-columns**

### Challenge using CSS Grid

* It's very easy for having a 2D layout with Grid
* Wherever 1D layout is used, continue using Flex
* Use grid with 3 columns, 1 of 250px since img is that width and use 1fr for the other 2 columns
* For h2 and button, grid-column: 1 / -1;

## Web Design Rules and Framework

### Project Overview

* Check starter/05-Design folder
* html is already coded, we'll work on the css

### Overview of Web Design and Website Personalities

* Web Designers create the overall look and feel of a website
* Web Developers implement the design using HTML, CSS and Javascript code
* Check Good Design vs Bad Design in the pdf
* Web Design Ingredients
  * Typography: Formatting and Designing text
  * Colors
  * Images/Illustrations
  * Icons
  * Shadows
  * Border Radius
  * Whitespace
  * Visual Hierarchy
  * User Experience
  * Components/Layout

#### Website Personalities Overview(Check pdf for more)

* Serious/Elegant
* Minimalist/Simple
* Plain/Neutral
* Bold/Confident
* Calm/Peaceful
* Startup/Upbeat
* Playful/Fun

### Typography

* Making text beautiful and easy to read
* Serif: Tails at the end of each letter(Check pdf)
* Sans-serif: No decorative lines and is Plain
* Use only good and popular typefaces
  * Sans-Serif: Inter, Open Sans, Roboto, Montserrat, Work Sans, Lato
  * Serif: Merriweather, Aleo, Playfair Display, Cormorant, Cardo, Lora
* It's okay to use just one typeface per page! If you want more, limit to 2 typefaces
* Choose the right typeface according to your website personality
* Regualar Font Weight of 400

### Check the rest of the Design Guidelines from PDF

### Implementing Typography

* Chair website: We want a Modern look, so we'll use sans-serif
* So checkout fonts.google.com and check for Inter
* Link that in the html head
  * Do it before our own CSS file
* Set font-family on the body to Inter
  * Can be used with or without quotes, but it is a good practice to use Quotes
* https://typescale.com/
* Take the font-sizes mentioned in style.css(Font Size System)
* Computed tab gives all the styles applied for that element
* Arrow keys up and down to increase or reduce by 1,and option key up and down to increase or reduce by .1
* Establish the hierarchy between different headings with font-size
* Have all normal text the same font-size and line-height

### Colors

* Choose the Right Color
  * Check the pdf with the above title
* Establish a color system
* Colors and Typography



## Components and Layout Patterns

### Web Design Rules #10 - Part 1: Elements and Components

* (Search for these titles in pdf)
* Final Design: From Elements to Webpage
  * Common Elements like Text, Buttons, Images, Input Elements and Tags
  * Group the Elements in a Component
  * Layout
  * Webpage
* Check pdf for Components and other index
* Breadcrumbs
* Pagination
* Alert and Status Bars
* Statistics
* Gallery
* Feature Box
* Preview and Profile Cards
* Accordion
* Tabs
* Carousel
* Customer Testimonials
* Customer Logos
* Featured-In Logos
* Steps
* Forms
* Tables
* Pricing Tables
* Modal Windows

### Building an Accordion Component

* Use 06-Components folder
* Use Inter font(copy from 05-Design index.html)
* Icons from heroicons.com
* Colors from https://yeun.github.io/open-color/
* Stroke for color for icons
* box-shadow
  * 1st - Horizontal offset
  * 2nd - Vertical offset
  * 3rd - Blur
  * 4th - Spread Radius(Can be Skipped)
  * 5th - Color
* For having space between each of the Accordion Items
  * Instead of giving margin-bottom to all items and finally removing it from the last item
  * We could have display of flex to the accordiion container and then use gap property
* Nice trick for opening only the 2nd item's hidden box
  * Use another class like open along with the item class
  * Then in selectors Use open class and descendant selector hidden-box
  * This will apply only for the 2nd item now

### Building a Carousel Component

* If width is not specified and only height is specified, then width will be adjusted accordingly to maintain the proportion
* I used absolute positioning for image but Author used transform with scale and for the spacing used padding and gap
* *align-items: center of flex works* even when the element is *absolutely* positioned
* Setting top: 50% = 50% of parent container's height
  * Check **Vertical Centering with Absolute Position and Transform** in Pdf
  * This moves the top of the element to the middle, not the element itself
  * Then use transform's translate to -50%(to the top) in the y-direction and-50% in the x-direction(to the left)
  * This 50% is the actual element's height
* For the dots, the author used button and space

### Building a Table Component

* table, tr, thead, tbody, th and td
* For column of equal width, we could have added `table-layout: fixed;` in table
* Author used the technique of giving `thead th` equal width of 25%(since there are 4 columns)

### Building a Pagination Component

* I had used padding for the Buttons but Author gave double the width of icon
* For the links to be perfect circle, we cannot using padding(Padding top and bottom doesn't work on inline elements and also even if used with inline-block, it wouldn't be perfect)
* Author gave equal width and height to make it a square first and then used border-radius
* Also Circles were made even before Hover
* Cool trick is `.btn:hover .btn-icon` using class like this, so that stroke would become white when hovered over button

### Building a Hero Section

* This time using Rubik Google Fonts
* Use 100vh for header height as 100% won't work
* Adding Gradient to image to make text more readable
  * Stack of background-images where the 1st background image is a gradient which is transparent
  * 1st is in top of 2nd in background-image property
* Centering done via **Vertical Centering with Absolute Position and Transform**

### Building a Web Application Layout

* 5 parts of our Application Layout
  * **nav** element for Navigation links
  * **menu** element for menu buttons in a Web App
  * **main** element for main piece of content of the Document
  * **aside** element for Additional information
* Background for above initially to see what is going on
* In my implemenatation, I had used *auto and fr* for column values, but Author gave *fixed width* for most
* The *body(grid container)* occupies *only the space that it needs for the content*
  * But we want for the whole page, so height: 100vh;
* **For some reason for the buttons**, the color **doesn't** get **inherited**
* The buttons are centered because they are inline and treated like text(so text-align: center centered them)
* For trash button placement at right, Author used **margin-left: auto**
* Flexbox treats text as **Flex Item**
* Author used **overflow: scroll** to section to keep it fixed so that it doesn't grow with content
* `overflow` is for how elements that don't fit into container appear
* But now the Flex items of section **shrink** *even though they have height of 96px* to accomodate this because all the Flex items have `flex-shrink: 1` by default
* So need to add `flex-shrink: 0` to all the flex items(.email in this case)

## Omnifood Project README in starter/07-Omnifood-Desktop