# Css Style Guide

# 21 CSS-selectors, which is useful to remember

## *

The symbol # selects all elements on the page.

```css
* {
 margin: 0;
 padding: 0;
}
```

Also, the * symbol can be used for the children of the object.

```css
#container * {
 border: 1px solid black;
}
```

## #X

The symbol of the lattice enables us to select elements by id.

```css
#container {
   width: 1170px;
   margin: 0 auto;
}
```

**On page should not be two identical id.**

* ```X > Y```

Selects only the immediate child of a parent element.

```css
div > p {
   color: red;
}
```

## X + Y

This is referred to as an adjacent selector. It will select only the element that is immediately preceded by the former element.

```css
ul + a {
   color: red;
}
```

## X ~ Y

A general sibling combinator selects instances of an element appearing anywhere after another element within the same parent.

```css
p ~ span {
	color: red;
}
```

* ```X[attributeName]```

Allows to select tags that has an attributes. While it can match the class and the id selector, its specificity value is lower.

```css
button[type] {
   color: green;
}
```

## X[attributeName="val"]

The following style rule selects any element with an "href" attribute whose value equally "http://www.codeharmony.ru".

```css
a[href="http://www.codeharmony.ru"] {
  color: red;
}
```

## X[attributeName^="val"]

The following style rule selects any element with an "href" attribute whose value begins with "http".

```css
a[href^='http'] {
  color: pink;
}
```

## X[attributeName="val"]

The following style rule selects any element with an "src" attribute whose value ends with ".jpg".

```css
img[src$=".jpg"] {
  border: 1px solid red;
}
```

## X[attributeName*="val"]

The following style rule selects any element with an "href" attribute whose value includes the substring "goo".

```css
a[href*="goo"] {
  color: red;
}
```

## X:checked

The :checked selector applies to toggable elements (e.g. radio buttons or checkboxes) that are toggled on.

```css
input[type=radio]:checked {
  border: 1px solid black;
}
```

## X:after

Creates a pseudo-element, which allows you to insert content onto a page from CSS after the selected element.

```css
.title:after {
  content: "";
  display: block;
  border-bottom: 1px solid black;
}
```

## X:before

Creates a pseudo-element, which allows you to insert content onto a page from CSS before the selected element.

```css
.title:before {
  content: "";
  display: block;
  border-top: 1px solid black;
}
```

## X:not(...)

The ":not(...)" sets the sampling rules for the elements that don't contain the specified selector.

```css
.p:not(.error) {
  color: pink;
}
```

## X:first-line

The ::first-line selector is used to add a style to the first line of the specified selector.

```css
p:first-line {
	font-weight: bold;
}
```

## X:first-letter

The ::first-letter selector is used to add a style to the first letter of the specified selector.

```css
p:first-letter {
	font-weight: bold;
}
```

## X:nth-child(n)

The :nth-child(n) selector matches every element that is the nth-child, regardless of type, of its parent.

n can be a number, a keyword, or a formula.

```css
li:nth-child(3) {
   color: red;
}
```

Value   | Non elements
------- | ------------
5       | 5
2n      | 2, 4, 6, 8, 10, ...
2n+1    | 1, 3, 5, 7, 9, ...
3n+2    | 2, 5, 8, 11, 14, ...
-n+3    | 3, 2, 1, ...
5n-2    | 3, 8, 13, 18, 23, ...
even    | 2, 4, 6, 8, 10, ...
odd     | 1, 3, 5, 7, 9, ...

## X:nth-last-child(n)

The :nth-last-child(n) selector matches every element that is the nth child, regardless of type, of its parent, counting from the last child.

n can be a number, a keyword, or a formula.

```css
li:nth-last-child(2) {
   color: red;
}
```

## X:first-child

The :first-child pseudo-class represents an element that is the first child of some other element.

```css
li:first-child {
   color: red;
}
```

## X:last-child

The :last-child pseudo-class represents an element that is the last child of some other element.

```css
li:last-child {
   color: red;
}
```

## X:empty

The :empty selector matches every element that has no children (including text nodes).

```css
div:empty {
   background.color: green;
}
```
