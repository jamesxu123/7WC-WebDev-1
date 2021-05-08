# 7WC: Intro to Web Dev

## Getting started with HTML

The core component behind a website is the index file. This is the file that browsers will first load when a URL (https://7wc.vmcs.club) is loaded and this file is usually called “index.html”. A web server will usually serve this and other HTML files. For our lesson today, all you need is a text-editor and a web browser because opening local HTML files is quite simple.

HTML is used to define the content and structure of a website. The language is based on tags as shown below.

```html
<html>
<head>
	<title>Our first website!</title>
</head>
<body>
	<h1>An wesome website</h1>
	<p>This is some paragraph text. This could be anything</p>
	<img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/iphone-12-pro-family-hero?wid=940&amp;hei=1112&amp;fmt=jpeg&amp;qlt=80&amp;.v=1604021663000"></img>
</body>
</html>
```

As you'll notice, tags are generally in the format `<tag>content</tag>`. You must always **close the tags** or there will be an error.

I'm going to list a few of the basic tags below, please feel free to play around with them in your own time

| Tag | Explanation |
| ---- | ------------ |
| `<html>`|Defines an HTML document.|
| `<head>` | Contains miscellaneous information. Most important one for now is the `<title>`. |
| `<title>` | Title of your website. Shows up in your browser tabs. |
| `<body>` | Body of your website. Generally contains all content.|
|`<h1>`,`<h2>`,...,`<h6>`| HTML headings. Big text. Like headings in a Word doc.|
|`<p>`| Paragraph tag. This is where your paragraphs or other large amounts of text go.|
|`<img src="https:///some.com/pic.png" alt="test image"`| Displays an image from a link. Can be a relative file path or a URL.|
|`<a href="https://google.ca">Link</a>`| Link tag. Brings users to another page when they click it. Can be a relative file path or a URL|

### Quick Example: Basic Personal Website
 Let's build a quick personal website that displays your name, your school, and a short biography. Also show an image underneath all that. 
 
 ---
 ```html
 <html>
<head>
	<title>James Xu's Website</title>
</head>
<body>
	<h1>James Xu</h1>
	<h2>McGill University</h2>
	<p>Hey! I'm James Xu, a first-year student at McGill studying business and computer science. I have experience developing applications using modern web frameworks such as Vue, React, and Node.js. In my free time you'll find me working on my projects and learning new things. Check out some of the highlights here!</p>

	<img src="https://specials-images.forbesimg.com/imageserve/607f495b756f30e8b9e79b3b/960x0.jpg?cropX1=77&cropX2=1376&cropY1=39&cropY2=770">
</body>
</html>
```

### Going further
These are only some of the many HTML tags. I encourage everyone to go deeper into the options and other tags available. For example, something you may want to look into could be HTML tables.

A great resource is W3Schools: https://www.w3schools.com/html/default.asp.

## Basic CSS
After the previous exercise, you should see something like this:
![Preview](https://assets.jamesxu.ca/file/jamesxu-ca/7wc-basicpreview.png)
This looks really plain and visually unappealing and we probably want to do something about that.

This is where CSS comes in. CSS lets us style things to look better! HTML is really about defining the basic layout of a website, but CSS lets us add styling and create advanced layouts as well.

The most popular way to define CSS styles is to create a CSS file. A CSS file is simply a file that ends with the extension “.css” and is linked to your HTML file with a `<link>` tag. This usually goes in the `<head>` section of your HTML file.

```html
<head>
	<link rel="main.css"></link>
	<title>James Xu's Personal Website</title>
</head>
```

There are two main parts of a CSS file: selectors and declarations. Selectors specify what elements a set of declarations apply to. Declarations are a key-value pair of a CSS property and its desired value. For example, this block of CSS will make all text in `<p>` tags yellow:

```css
p {
	color: yellow;
}
```

If we wanted all our paragraph text to be yellow, we would put this in `main.css`.

---
Let's go through a few of the most common ways of selecting items for CSS styling:

| Method | Explanation |
| ------ | ----------- |
| `element` | Selects all elements named `element` |
| `.class` | Selects all elements with class `class` |
| `#id` | Selects the element with the ID `id` |

Selectors can be combined by putting a space in between them. For example, to select all elements that have the class “comments” which are inside an element with the class `post`, your selector would be `.post .comments`.

**A list of CSS selectors can be found at [https://www.w3schools.com/cssref/css\_selectors.asp](https://www.w3schools.com/cssref/css_selectors.asp).**

To apply a set of declarations to a selector, wrap them with a set of curly braces. Here is an example of a declaration which will make the text inside all tags with the class “cta” bold. As you can see, we are setting the property (font-weight) to the value bold. You must end all declarations with a semicolon.

```css
.cta {
	font-weight: bold;
}
```

Here are some common CSS properties that people use:

| Property | Explanation |
| --- | --- |
| `background` | Sets the background of an element. Can be many things such as a color, image, or gradient |
| `border` | Specifies how a border should be drawn around an element |
| `color` | Sets the color of the text inside an element. Can be RGB, RGBA, HEX, or word (e.g. `red`) |
| `font-[family, size, weight]` | Sets the font family (e.g. Arial, Helvetica), size, and weight (boldness) of a text inside an element |
| `height`/`width` | Sets the height and width of an element |
| `margin` | Sets the amount of margin of an element. Margin is the space in-between elements (but outside the element). |
| `padding` | Sets the amount of padding for an element. Padding is the space inside an element |
| `text-align` | Sets the alignment method of text within an element (.e.g left, center, right, justify) |

A list of CSS properties can be found at [https://www.w3schools.com/cssref/](https://www.w3schools.com/cssref/).

An element will usually inherit (take the value of) the value of a CSS property from its parent. If you would like to force this behaviour, simply put “inherit” instead of a value when setting a CSS property.

### Quick Exercise: Add some style to our personal website
Now that you have created a basic personal site, use CSS to spice things up. Change the font that is used, add a background image, or even create a border!

## Time for some JavaScript!
Now we will be learning about JavaScript, which allows us to create dynamic and interactive websites. Do note however, that any code you write in JavaScript on your website can be changed and accessed by the user, so do not put anything that you don’t want your users to see or control!

### Adding JavaScript
JavaScript can be added to your site with the use of the `<script>` tag in two ways: inline, and external.
```html
<!--External-->
<script src="/path/to/script.js"></script>

<!--Internal-->
<script>
console.log("Hello World")
</script>
```

### Basic Syntax
JavaScript syntax is very similar to that of Java and, by extension, C and C++. However, you do NOT need to define variable types. Semicolons are also not required like Python. If you know Python, JavaScript should be pretty quick to learn. A few basic operations that you’ll need:

```js
let myVariable = 8;  
let myOtherVariable = ["Web", "Dev", "Workshop"];

let yetAnotherVariable = "Web";  
  
const myConstant = "HELLO";  
myConstant = "BYE"; // Not going to work  
  
console.log(myVariable); // 8  
console.log(myVariable + 8); // 16  
console.log(myVariable - 8); // 0  
console.log(myVariable * 8); // 64  
console.log(myVariable / 2); // 4  
console.log(Math.pow(8, 2)); // 64  
  
alert("Very annoying thing. Do not do this if possible");  
let userInput = prompt("What is your input"); // Gives you a string;  
let userInputInt = parseInt(userInput);  
let userInputFloat = parseFloat(userInput);  
  
let userInputString = userInputFloat.toString();  
  
document.write("Hello");  
  
let ele = document.getElementById("myElement");  
ele.innerHTML = "Hello";
```

### Challenge: Let's create a simple calculator
Create a simple calculator that prompts the user for two numbers and an operation, then display the output. **BONUS: Use textboxes and dropdowns instead of prompts.** (bonus version shown below)
```html
<!DOCTYPE html>
<head\>
    <title>Simple Calculator</title>
</head>
<body>
    <input id="num1">
    <select id="operation">
        <option>+</option>
        <option>-</option>
        <option>*</option>
        <option>/</option>
    </select>
    <input id="num2">
    <button onclick="run()">Calculate</button>
    <p id="ans"></p>
</body>
<script src="https://cdn.jsdelivr.net/npm/sweetalert2@9.7.0/dist/sweetalert2.all.min.js" integrity="sha256-PokS6eWvc67qkBbhxlpg/W4UHnseEHRwArGs9+0zbXI=" crossorigin="anonymous"></script>
<script>

    function run() {
        let opSelector = document.getElementById("operation")
        let op = opSelector.options[opSelector.selectedIndex].text
        let num1 = Number(document.getElementById("num1").value)
        let num2 = Number(document.getElementById("num2").value)
        let ansSpan = document.getElementById("ans")
        switch (op) {
            case '+':
                ansSpan.innerHTML = num1 + num2
                break
            case '-':
                ansSpan.innerHTML = num1 - num2
                break
            case '/':
                ansSpan.innerHTML = num1 / num2
                break
            case '*':
                ansSpan.innerHTML = num1 * num2
                break
            default:
                Swal.fire({
                    icon: 'error',
                    title: 'Oops...',
                    text: 'Not a valid symbol!'
                })
        }  
    }   

</script>
```

## Conclusion
Today we learned about:
- HTML: tags, layout
- CSS: used to make things look nice, some basic properties
- JS: Accessing HTML elements, writing some simple logic
