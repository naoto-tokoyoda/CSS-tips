# CSS tips

This repository explains CSS step by step

The basic pattern in CSS
```
selector {
    property: value;
}
```

## 1. Universal selector
This selects everything in HTML.
In this case below, it shows all pink in HTML
```
* {
    background-color:pink;
}
/* In this case above, it shows all pink in HTML */
```

## 2. ID selector
This selects the element with the ID that you name.
```
<p id="theme">This is theme</p>

#theme {
   font-family: Georgia, serif;
}
```

## 3. Element selector
This selects all elements in HTML
```
<h1>This is h1</h1>

h1 {
    border:1px solid red;
}
/* All h1 tag has a border with 1px, solid and red. */

<img src="image1.png" alt="image1">

img {
    width:500px;
    height:500px;
}
/* All image has 500px of width and 500px of height */
```

## 4. Multiple selectors
This selects more than one elements 
```
<h1>Same color</h1>
<h2>Same color</h2>

h1,h2 {
    color:green;
}
/* All h1 and h2 are set to green color */

<p class="class1">Same width and height</p>
<p class="class2">Same width and height</p>

.class1, class2{
    width:100px;
    height:100px;
}
/* select multiple classes */
```

## 5. Class selector
```
<h1 class="title">Class selecort</h1>

.title{
    background-color:blue;
}
```

## 6. Descendent selector
Select all <p>'s that are nested inside an <div> 
```
<div>
    <p>hello world</p>
    <p>hello world</p>
</div>

div p {
    color: green;
}
```

## 7. Adjacent selector
Select only the one element that is immediately preceded by another element
```
<ul>
    <li>One</li>
    <li>Two</li>
    <li>Three</li>
</ul>

li:first-of-type + li {
    color: red;
}
/* this means that only two with li tag will be set the style */

```

## 8. Direct child selector
Select only the <li>'s that are direct children of a <div> element
```
<div>
    <li>One</li>
    <li>Two</li>
    <li>Three</li>
</div>

div > li {
color: white;
}
/* One with li tag will be set the color */
```

## 9. Attribute selector
Select all input elements where the type attribute is set to "text"
```
<input type="passsword" placeholder="password">

input[type="text"] {
    width: 300px;
    color: yellow;
}

```

## 10. Pseudo-elements
This is the method of styling the specific element
```
<p>This is a paragraph</p>

p::first-letter{
    color:white;
}
/* "T" which is the first letter with p tag will be changed the color */
```

## 11. Pseudo-classes
Select all input elements where the type attribute is set to "text"
```
<button>
    <a>Hello</a>
</button>

button a:hover {
    color:blue;
}
/* Color on the button will be changed when the mouse pointer over it */
```
There are many pseudo-classes. You can check this website: [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)


# Conflicting among selectors (Specificity)
What happens when p elements are declared at the same time?
```
p {
    color: red;
}

p {
    color: blue;
}
```
p element is blue. The program will be read step by step, and the last code is color is blue.

## What is the specificity?
This means applying styles depends on how much you specify with the selector type.
For example here.
```
h1 {
    color: red;
}
/* one element selector  */ 

div h1 {
    color: blue;
}
/*two element selectors */ 
```
So, the h1 tag is blue, because it is more specific.

# What is the formula of specificity in CSS?
ID > CLASS > ELEMENT

More details:
ID selectors > Class, Attribute, and pseudo class selectors > Element and pseudo element selectors.

```
 div h1 {
    color: blue;
}
/* 0 > 0 > 2 */
/* Because there have two elements */
```
This will help your understandings: [Specificity calculator](https://specificity.keegan.st/)
