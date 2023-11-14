### The 7 Steps to a Great Website

- Check **The Process Behind Building a Website** in pdf

1. Define: For Whom and What is the Business Purpose
2. Plan: Plan the Content, Images, Videos etc
3. Sketch: Sketch the Layout, the Components etc
4. Design and Build: Code
5. Test and Optimize
6. Launch
7. Maintain and Update

### About Omnifood

- Omnifood is startup that uses AI to create and deliver custom healthy meal plans
- They provided us with all the content for the website (content.md)

### Step 1: Define the Project

- Define **Who** the Website is for
  - For a Client(Omnifood Company)
- Define **What** is the Website is for
  - Business Goal: Selling monthly food subscription
  - User Goal: Eating well effortlessly, without spending a lot of time and money
- Define Target Audience
  - Inferring from the content
  - Busy people who like tech, are interested in a healthy diet and have a well-paying job

### Step 2: Plan the Project

- Plan and Gather website content: Already done in our case
- Plan out the sitemap
  - One-page marketing website(Landing page), no sitemap needed
- Define website personality
  - startup/upbeat and calm/peaceful
- Content guiding the design
- Sections (Analysed from author-content.md)
  - Logo + Navigation
  - Hero
  - Featured in
  - How it works
  - Meals (and list of diets)
  - Testimonials + Gallery
  - Pricing + Features
  - CTA (Call To Action)
  - Footer

### Step 3: Sketching Initial Layout Ideas

- Check out **First Ideas and Sketch** in pdf
- Sketch it out on Paper

### Step 4: First design and Development Steps

- Check comments in style.css
- Image Source:
  - unsplash.com and search for food
  - uifaces.co for faces

### Responsive Design Principles

- Check out **What is Responsive Design** in pdf
- Adjust style to **any possible screen size**

#### Responsive Design Ingredients

- Fluid Layouts
  - `Use %` (or `vh/vw`) unit instead of px
  - Use `max-width` instead of width
- Responsive Units
  - Use `rem` unit instead of px
  - Helpful trick: Set _1 rem to 10px_ for easy calculations
- Flexible Images
  - Always `use %` for image dimesions together with `Max-width`
- Media Queries
  - Change styles on certain viewport widths called breakpoints

### How rem and max-width work

#### max-width

- **max-width** for occupying the set space when space is available else will be same width(100% of its parent) as its container(parent element)

```html
<body>
  <div class="test">
</body>
```

```css
.test {
  padding: 20px;
  background-color: red;
  /* width: 1000px */
  max-width: 1000px;
}
```

#### rem

- rem is root(html) element's font size
- If nothing is specified, it will be browser's default font size(which is 16px)
- By specifiying units in rem, it will be very easy to scale to mobile, tablet and other screens just by setting different font-size in html element
  - With this way, we can also avoid writing Media Queries
- For easy calculation, we will use 10px as font-size in the html
- But with this, we don't respect User's definition of Browser font size(Chrome -> Appearance -> Font size -> Change from Medium to anything else)
- The trick is to use in %(62.5%) which is 10px/16px \* 100

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="css/style.css" />
    <title>Omnifood</title>
    <style>
      html {
        /* font-size: 10px; */
        font-size: 62.5%;
      }

      .test {
        background-color: red;
        /* max-width: 500px; */
        max-width: 50rem;
        /* padding: 100px; */
        padding: 10rem;
        font-size: 2rem;
      }
    </style>
  </head>
  <body>
    <h1>A healthy meal delivered to your door, every single day</h1>
    <div class="test">Test</div>
  </body>
</html>
```

### Building the Hero

* Checkout **Building the Hero** pdf
* section element
  * similar to article element, but article element is self-contained
  * For section to exist, there should be multiple sections which are then part of something bigger
* Give classname prefixed with section `class="section-hero"` so that it becomes easy to identify
* Select everything using classes in css for consistency
* `css grids` for the section-hero even though it is 1D layout to have equal sized columns and to have uniform layouts across the page
* It could have been done using flex also, something like this
```css
/* Hero section using my flex */
/* Earlier .section-hero had flex, but after adding new div called .hero, I changed it here as well */
.hero { 
  display: flex;
}

.hero-text-box {
  flex: 1;
}

.hero-img {
  width: 100%;
}

.hero-img-box {
  flex: 1;
}
```
* Need to give img a width of 100% to fill the parent element
* An additional div element with `class hero` to provide **fixed width**
* section-hero fills the entire width and will be used to give background-color
* Width given in rem and used max-width to not have that horizontal scrollbars when width is less
* With Grid
```css
/* Hero section with Grid */
.hero {
  max-width: 130rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  margin: 0 auto;
}

.hero-img {
  width: 100%;
}
```
* We can use px in situations where don't scale up or down and also when it is very small `letter-spacing: -0.5px`
* Tint and Shade Generator(https://maketintsandshades.com/)
* We want spacing inside of section-hero to preserve the background color, so we use padding
* To apply padding correctly(especially the vertical padding) to inline element(anchor tag), we make it inline-block

* Adding modifiers `btn--full` and `btn--outline` for the buttons
```
<a class="btn btn--full" href="#">Start eating well</a>
<a class="btn btn--outline" href="#">Learn More &rarr;</a>
```
* For 1 of the buttons, on hover, we want a border
  * But if we add a border on just hover, the layout jumps
  * So we need a trick to add border inside
  * We use `box-shadow` property along with `inset`
    * `box-shadow: inset 0 0 0 3px #fff;`
* Nice animations for buttons using just css
  * `transition: all 1s`
  * Put transition on the original state
  * We require for only background-color, so ``transition: background-color 0.3s``
  * Property to animate, over how much time
* For space between the buttons, we could just add `margin-right` to `btn--full`
  * But that's not the right way as all the button `btn--full` class will have margin-right
  * Instead we will add helper class `margin-right-sm`
```css
.margin-right-sm {
  margin-right: 1.6rem;
}
```