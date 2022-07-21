**JavaScript**

Allows you to change CSS and HTML elements on your website after the site has been loaded, which gives you the ability to make your site more interactive and engaging for users.

**External JavaScript**

```html
<script src="javascript.js"></script>
```

**Declaring Variables**

```javascript
let x = 5;
const price1 = 5;
```

**Declaring Functions**

```javascript
function favoriteAnimal(animal) {
  console.log(animal + " is my favorite animal!")
}
 
favoriteAnimal('Goat')
```

**Adding variables in a string**

```javascript
clet variable = x;
onsole.log(`Computer selected ${variable}`);
```

- Have to enclose string inside ``

**Node.js**

A JavaScript runtime environment that allows you to run JavaScript outside of your web browser

To activate Node console, type on terminal: `node` and to exit: `.exit`

**Opening Developer Tools on a Browser**

Press `F12`

**Simulate mobile devices with Device Mode**

https://developer.chrome.com/docs/devtools/device-mode/

**Debug JS**

https://developer.chrome.com/docs/devtools/javascript/

**DOM - Document Object Model**

Is a tree-like representation of the contents of a webpage - a tree of “nodes” with different relationships depending on how they’re arranged in the HTML document.

```html
<div id="container">//parent
  <div class="display"></div>//child
  <div class="controls"></div>//child
</div>
```

**Targeting Nodes with Selectors**

```javascript
const container = document.querySelector('#container');
// selects the #container div (don't worry about the syntax, we'll get there)

console.dir(container.firstElementChild);                      
// selects the first child of #container => .display

const controls = document.querySelector('.controls');   
// selects the .controls div

console.dir(controls.previousElementSibling);                  
// selects the prior sibling => .display
```

**DOM Methods**

- **Query Selectors**
  - *element*.querySelector(*selector*) returns a reference to the first match of *selector*
  - *element*.querySelectorAll(*selectors*) returns a “nodelist” containing references to all of the matches of the *selectors*

- **Element Creation**

  ```javascript
  const div = document.createElement('div');
  ```

  - creates a new element of tag type tagName
  - This function does NOT put your new element into the DOM - it simply creates it in memory.

- **Append Elements**

  - *parentNode*.appendChild(*childNode*) appends *childNode* as the last child of *parentNode*
  - *parentNode*.insertBefore(*newNode*, *referenceNode*) inserts *newNode* into *parentNode* before *referenceNode*

- **Remove Elements**

  - *parentNode*.removeChild(*child*) removes *child* from *parentNode* on the DOM and returns a reference to *child*

- **Adding Inline Style**

  ```javascript
  div.style.color = 'blue';                                      
  // adds the indicated style rule
  
  div.style.cssText = 'color: blue; background: white;';          
  // adds several style rules
  
  div.setAttribute('style', 'color: blue; background: white;');    
  // adds several style rules
  ```

- **Editing Attributes **

  ```javascript
  div.setAttribute('id', 'theDiv');                              
  // if id exists, update it to 'theDiv', else create an id
  // with value "theDiv"
  
  div.getAttribute('id');                                        
  // returns value of specified attribute, in this case
  // "theDiv"
  
  div.removeAttribute('id');                                     
  // removes specified attribute
  ```

-  **Working with classes**

  ```javascript
  div.classList.add('new');                                      
  // adds class "new" to your new div
  
  div.classList.remove('new');                                   
  // removes "new" class from div
  
  div.classList.toggle('active');                                
  // if div doesn't have class "active" then add it, or if
  // it does, then remove it
  ```

**NOTE: the JavaScript does *not* alter your HTML, but the DOM - your HTML file will look the same, but the JavaScript changes what the browser renders.**

Your JavaScript, for the most part, is run whenever the JS file is run, or when the script tag is encountered in the HTML. If you are including your JavaScript at the top of your file, many of these DOM manipulation methods will not work because the JS code is being run *before* the nodes are created in the DOM. The simplest way to fix this is to include your JavaScript at the bottom of your HTML file so that it gets run after the DOM nodes are parsed and created.

Alternatively, you can link the JavaScript file in the `<head>` of your HTML document. Use the `<script>` tag with the `src` attribute containing the path to the JS file, and include the `defer` keyword to load the file *after* the HTML is parsed, as such:

```html
<head>
  <script src="js-file.js" defer></script>
</head>
```

**Events**

Events allow to manipulate the DOM dynamically, or on demand!

**Event Methods**

- **Method 1** 

  ```html
  <button onclick="alert('Hello World')">Click Me</button>
  ```

- **Method 2**

  ```html
  <!-- the HTML file -->
  <button id="btn">Click Me</button>
  ```

  ```javascript
  // the JavaScript file
  const btn = document.querySelector('#btn');
  btn.onclick = () => alert("Hello World");
  ```

- **Method 3**

  ```html
  <!-- the HTML file -->
  <button id="btn">Click Me Too</button>
  ```

  ```javascript
  // the JavaScript file
  const btn = document.querySelector('#btn');
  btn.addEventListener('click', () => {
    alert("Hello World");
  });
  ```

**Attaching listeners to groups of nodes**

```html
<div id="container">
    <button id="1">Click Me</button>
    <button id="2">Click Me</button>
    <button id="3">Click Me</button>
</div>
```

```javascript
// buttons is a node list. It looks and acts much like an array.
const buttons = document.querySelectorAll('button');

// we use the .forEach method to iterate through each button
buttons.forEach((button) => {

  // and for each one we add a 'click' listener
  button.addEventListener('click', () => {
    alert(button.id);
  });
});
```

**JavaScript Classes**

```javascript
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
}

let myCar1 = new Car("Ford", 2014);

```
