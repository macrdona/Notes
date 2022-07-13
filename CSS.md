**CSS**

- A popular style sheet language that determines how a document created in HTML is styled (colors, font styles, layout and responsive features).

**Basic CSS Syntax**

![Basic CSS syntax](https://user-images.githubusercontent.com/70952936/130702428-4808becb-cbc4-4a4d-8fa7-f9aa5409768d.jpg)



**Selectors**

- Selectors simply refer to the HTML elements to which CSS rules apply

**Universal Selectors**

- The universal selector will select elements of any type

  ```css
  * {
    color: purple;
  }
  ```

**Type Selectors**

- A type selector (or element selector) will select all elements of the given element type, and the syntax is just the name of the element

  ```css
  div {
    color: white;
  }
  ```

**Class Selectors**

- Class selectors will select all elements with the given class, which is just an attribute you place on an HTML element.

  ```html
  <!-- index.html -->
  
  <div class="alert-text">
    Please agree to our terms of service.
  </div>
  ```

  ```css
  /* styles.css */
  
  .alert-text {
    color: red;
  }
  ```

**ID Selectors**

- They select an element with the given ID, which is another attribute you place on an HTML element

  ```html
  <!-- index.html -->
  
  <div id="title">My Awesome 90's Page</div>
  ```

  ```css
  /* styles.css */
  
  #title {
    background-color: red;
  }
  ```

**Grouping Selectors**

```css
.read,
.unread {
  color: white;
  background-color: black;
}
```

**Descendant Combinator**

- Combinators allow us to combine multiple selectors differently than either grouping or chaining them, as they show a relationship between the selectors.

  ```html
  <!-- index.html -->
  
  <div class="ancestor"> <!-- A -->
    <div class="contents"> <!-- B -->
      <div class="contents"> <!-- C -->
      </div>
    </div>
  </div>
  
  <div class="contents"></div> <!-- D -->
  ```

  ```css
  /* styles.css */
  
  .ancestor .contents {
    /* some declarations */
  }
  ```

**Specificity**

- A CSS declaration that is more specific will take precedence over less specific ones
  1. ID selectors (most specific selector)
  2. Class selectors
  3. Type selectors

**Adding CSS to HTML**

```html
<!-- index.html -->

<head>
  <link rel="stylesheet" href="styles.css">
</head>
```

**The Box Model**

- Every single thing on a webpage is a rectangular box. These boxes can have other boxes in them and can sit alongside one another.

**Padding, Margin, Border**

- `padding` increases the space between the edge of a box and the content inside of it.

- `margin` increases the space between a box and any others that sit next to it.

- `border` adds space (even if it’s only a pixel or two) between the margin and the padding.

  ![the box model](https://cdn.statically.io/gh/TheOdinProject/curriculum/main/foundations/html_css/the-box-model/imgs/box-model.png)

**Block vs Inline**

- By default, block elements will appear on the page stacked atop each other, each new element starting on a new line.
- Inline elements, however, do not start on a new line. They appear in line with whatever elements they are placed beside.

**Divs and Spans**

- Div is a block-level element by default. It is commonly used as a container element to group other elements. Divs allow us to *divide* the page into different blocks and apply styling to those blocks.
- Span is an inline-level element by default. It can be used to group text content and inline HTML elements for styling and should only be used when no other semantic HTML element is appropriate.

**Flexbox**

- Flexbox is a way to arrange items into rows or columns. These items will flex (i.e. grow or shrink) based on some simple rules that you can define.
- A flex container is any element that has `display: flex` on it. A flex item is any element that lives directly inside of a flex container.

![container-vs-child](https://cdn.statically.io/gh/TheOdinProject/curriculum/495704c6eb6bf33bc927534f231533a82b27b2ac/html_css/v2/foundations/flexbox/imgs/03.png)

**Flexbox Growing and Shrinking**

- `Flex` is actually a shorthand for `flex-grow`, `flex-shrink` and `flex-basis`.

![flex shorthand](https://cdn.statically.io/gh/TheOdinProject/curriculum/495704c6eb6bf33bc927534f231533a82b27b2ac/html_css/v2/foundations/flexbox/imgs/10.png)

- `flex-grow` expects a single number as its value, and that number is used as the flex-item’s “growth factor”. When we applied `flex: 1` to every div inside our container, we were telling every div to grow the same amount.
- `flex-shrink` is similar to `flex-grow`, but sets the “shrink factor” of a flex item. `flex-shrink` only ends up being applied if the size of all flex items is larger than their parent container.
- `flex-basis` simply sets the initial size of a flex item, so any sort of `flex-grow`ing or `flex-shrink`ing starts from that baseline size.

**Flexbox Axes**

- The default direction for a flex container is horizontal, or `row`

  ```css
  .flex-container { 
  	flex-direction: column; 
      flex: 1 1 auto; //Usual flex setting for columns
  }
  ```

**Flebox Alignment**

- `justify-content` aligns items across the **main axis**
- To change the placement of items along the **cross axis** use `align-items`
- The main axis is your defining direction of how your flex items are placed in the flex container
  - Ex. flex-direction: row //main axis
- Determining the cross axis is very simple, it's in the direction that's perpendicular to your main axis
  - Ex. If flex-direction: row, then cross-axis is column
- GAP - setting `gap` on a flex container simply adds a specified space between flex items



