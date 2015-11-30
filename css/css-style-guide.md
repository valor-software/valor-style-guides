# Css Style Guide

# 21 CSS-selectors, which is useful to remember

## *

The symbol ```*``` selects all elements on the page.<br/>
In the example below we will set ```margin``` and ```padding``` to ```0``` for all the elements on the page:

```css
* {
 margin: 0;
 padding: 0;
}
```

Also, the symbol ```*``` can be used for the children of the element:

```css
#container * {
 border: 1px solid black;
}
```

So when applied to the following html:

```html
<div id="container">
  <h1>Lorem ipsum</h1>
  <p>Lorem ipsum dolor sit amet</p>
</div>
```

affected elements are: ```h1``` and ```p```.

## \#X

The symbol ```#``` enables us to select elements by id:

```css
#container {
   width: 1170px;
   margin: 0 auto;
}
```

Let's consider a little piece of html:

```html
<div id="container">
  <h1>Lorem ipsum</h1>
  <p>Lorem ipsum dolor sit amet</p>
</div>
```

in here, only ```div``` with an id ```container``` is affected.


**Note:** On page should not be two identical ids

## X > Y

Selects only the immediate child of a parent element:

```css
div > span {
   color: red;
}
```

In order to understand what this selector does let's have a look at the example below:

```html
<div>
  <span>Immediate child</span>
  <p>
    <span>Paragraph somewhere in the deep:)</span>
  </p>
</div>
```

in this example only ```<span>Immediate child</span>``` is selected and gets ```color: red;``` for it's content

## X + Y

This selector is known as an _adjacent_ selector. It will select only the element that is immediately preceded by the former element:

```css
ul + p {
   color: red;
}
```

It is much easier to have a look at the example:

```html
<ul>
  <li>Item1</li>
  <li>Item2</li>
</ul>
<p id="first">Lorem ipsum one</p>
<p id="second">Lorem ipsum two</p>
```

in here only ```<p id="first">Lorem ipsum one</p>``` is selected and colorized in red

## X ~ Y

A general sibling combinator selects instances of an element appearing anywhere after another element within the same parent:

```css
h1 ~ p {
	color: red;
}
```

And once more - good example is worth a thousand words :)

```html
<h1>Lorem ipsum</h1>
<p>sibling 1</p>
<p>sibling 2</p>
<div>
  <p>Somewhere in the deep</p>
</div>
```

given our css selector ```h1 ~ p``` only ```<p>sibling 1</p>``` and ```<p>sibling 2</p>``` are selected.

## X[attributeName]

Allows to select tags that have attributes. While it can match the class and the id selector, its specificity value is lower:

```css
button[type] {
   color: green;
}
```

The guy above applied to the following structure:

```html
<div>
  <button type="submit">Submit</button>
  <button>Do smth</button>
</div>
```

colorizes only ```<button type="submit">Submit</button>```

## X[attributeName="val"]

The following style rule selects any element with an ```href``` attribute whose value equals "http://www.codeharmony.ru":

```css
a[href="http://www.codeharmony.ru"] {
  color: red;
}
```

And again little example:

```html
<div>
  <a href="http://www.codeharmony.ru">Know what is harmony</a>
  <a href="http://www.nowhere.com">Go to nowhere</a>
</div>
```

in this example selector's target is ```<a href="http://www.codeharmony.ru">Know what is harmony</a>```

## X[attributeName^="val"]

The following style rule selects any element with an ```href``` attribute whose value begins with "http":

```css
a[href^='http'] {
  color: pink;
}
```

Selector applied to the piece of html:

```html
<div>
  <a href="http://google.com"></a>
  <a href="file://file.txt"></a>
  <a href="file://http.txt"></a>
</div>
```

only ```<a href="http://google.com"></a>``` is selected

## X[attributeName="val"]

The following style rule selects any element with an ```src``` attribute whose value ends with ".jpg":

```css
img[src$=".jpg"] {
  border: 1px solid red;
}
```

Selector applied to the piece of html:

```html
<div>
  <img src="cat.jpg" alt="cat">
  <img src="dog.png" alt="dog">
  <img src="dogjpg.png" alt="dogjpg">
</div>
```

only ```<img src="cat.jpg" alt="cat">``` is selected

## X[attributeName*="val"]

The following style rule selects any element with an ```href``` attribute whose value contains the substring "goo":

```css
a[href*="goo"] {
  color: red;
}
```

Selector applied to the piece of html:

```html
<div>
  <a href="http://google.com"></a>
  <a href="file://file.txt"></a>
  <a href="file://world_of_goo.txt"></a>
</div>
```

only ```<a href="http://google.com"></a>``` and ```<a href="file://world_of_goo.txt"></a>``` are selected

## X:checked

The ```:checked``` selector applies to toggable elements (e.g. radio buttons or checkboxes) that are toggled on:

```css
input[type=radio]:checked {
  border: 1px solid black;
}
```

Selector applied to the piece of html:

```html
<div>
  <input type="checkbox" checked="checked">cat</input>
  <input type="checkbox" value='dog'>dog</input>
</div>
```

only ```<input type="checkbox" checked="checked">cat</input>``` is selected

## X:after

Creates a pseudo-element, which allows you to insert content onto a page from CSS after the selected element:

```css
.title:after {
  content: "";
  display: block;
  border-bottom: 1px solid black;
}
```

Selector applied to the piece of html:

```html
<div class="title">lorem ipsum</div>
```

underlines ```div``` given in the example (creates a content with bottom border that occupies all the width of the given ```div``` and by doing this creates effect of 'underline').


## X:before

Creates a pseudo-element, which allows you to insert content onto a page from CSS before the selected element:

```css
.title:before {
  content: "";
  display: block;
  border-top: 1px solid black;
}
```

Selector applied to the piece of html:

```html
<div class="title">lorem ipsum</div>
```

creates a content with a top border that occupies all the width of the given ```div``` so that we can see line above the given ```div```.


## X:not(...)

The ```:not(...)``` sets the sampling rules for the elements that don't contain the specified selector:

```css
span:not(.error) {
  color: pink;
}
```

Selector applied to the piece of html:

```html
<div>
  <span class="error">Error message</span>
  <span class="success">Success message</span>
</div>
```

only ```<div class="success">Success message</div>``` is selected and will be colorized in pink.


## X:first-line

The ```:first-line``` selector is used to add a style to the first line of the specified selector:

```css
p:first-line {
	font-weight: bold;
}
```

Selector applied to the piece of html:

```html
<div>
  <p>
    Lorem<br/> ipsum dolor
  </p>
</div>
```

in this example only ```Lorem``` will be rendered in bold, because all the other words ```ipsum dolor``` begin on the new line (created by ```<br/>``` tag).

## X:first-letter

The ```:first-letter``` selector is used to add a style to the first letter of the specified selector:

```css
p:first-letter {
	font-weight: bold;
}
```

Selector applied to the piece of html:

```html
<p>
  Lorem ipsum dolor
</p>
```

in here only first letter (in our example this is ```L```) of the content of the tag  ```<p>``` will be rendered in bold


## X:nth-child(n)

The ```:nth-child(n)``` selector matches every element that is the nth-child, regardless of type, of its parent.
```n``` can be a number, a keyword, or a formula:

```css
li:nth-child(3) {
   color: red;
}
```

Value   | ```#``` of selected element
------- | ------------
5       | 5
2n      | 2, 4, 6, 8, 10, ...
2n+1    | 1, 3, 5, 7, 9, ...
3n+2    | 2, 5, 8, 11, 14, ...
-n+3    | 3, 2, 1, ...
5n-2    | 3, 8, 13, 18, 23, ...
even    | 2, 4, 6, 8, 10, ...
odd     | 1, 3, 5, 7, 9, ...

Selector applied to the piece of html:

```html
<ul>
  <li>1</li>
  <li>2</li>
  <li>3</li>
  <li>4</li>
  <li>5</li>
</ul>
```

with a ```li:nth-child(3)``` only third ```<li>3</li>``` item will be selected.<br/>
with a ```even```, element that are selected: ```<li>2</li>``` and ```<li>4</li>```<br/>
and so on.


## X:nth-last-child(n)

The ```:nth-last-child(n)``` selector matches every element that is the nth child, regardless of type, of its parent, counting from the last child.
```n``` can be a number, a keyword, or a formula:

```css
li:nth-last-child(2) {
   color: red;
}
```

Selector applied to the piece of html:

```html
<ul>
  <li>1</li>
  <li>2</li>
  <li>3</li>
  <li>4</li>
  <li>5</li>
</ul>
```

with a ```li:nth-last-child(2)``` only third ```<li>4</li>``` item will be selected.<br/>
with a ```even```, element that are selected: ```<li>4</li>``` and ```<li>2</li>```<br/>
and so on.

## X:first-child

The ```:first-child``` pseudo-class represents an element that is the first child of some other element:

```css
li:first-child {
   color: red;
}
```

Selector applied to the piece of html:

```html
<div>
  <p>1</p>
  <p>2</p>
</div>
```

affects only ```<p>1</p>``` element

## X:last-child

The ```:last-child``` pseudo-class represents an element that is the last child of some other element.

```css
li:last-child {
   color: red;
}
```

Selector applied to the piece of html:

```html
<div>
  <p>1</p>
  <p>2</p>
</div>
```

affects only ```<p>2</p>``` element

## X:empty

The ```:empty``` selector matches every element that has no children (including text nodes):

```css
div:empty {
   background-color: green;
}
```

Selector applied to the piece of html:

```html
<div id="no-children"></div>
<div id="with-children">
  <p>lore, ipsum</p>
</div>
```

affects only ```<div id="no-children"></div>``` element.<br/>
**Note:** text is also treated as a child, hence this selector won't be applied to ```<div id="no-children">lorem</div>```
