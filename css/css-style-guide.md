# Css Style Guide

# 21 CSS-selectors, about which is useful to remember

1. *

The symbol asterisk selects all elements on the page.

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

2. #X

The symbol of the lattice enables us to select elements by id.

```css
#container {
   width: 1170px;
   margin: 0 auto;
}
```

** On page should not be two identical id. **

3. X > Y

Selects only the immediate child of a parent element.

```css
div > p {
   color: red;
}
```

4. X + Y

This is referred to as an adjacent selector. It will select only the element that is immediately preceded by the former element.

```css
ul + a {
   color: red;
}
```

5. X ~ Y

A general sibling combinator selects instances of an element appearing anywhere after another element within the same parent.

```css
p ~ span {
	color: red;
}
```

6. X[attributeName]

Allows to select tags that has an attributes. While it can match the class and the id selector, its specificity value is lower.

```css
button[attributeName] {
   color: green;
}
```

7. X[attributeName="val"]

The following style rule selects any element with an "attr" attribute (set to any value).

```css
a[href="http://www.codeharmony.ru"] {
  color: red;
}
```

8. X[attributeName^="val"]

The following style rule selects any element with an "attr" attribute whose value begins with "http".

```css
a[href^='http'] {
  color: pink;
}
```

9. X[attributeName="val"]

The following style rule selects any element with an "attr" attribute whose value ends with ".jpg".

```css
img[src$=".jpg"] {
  border: 1px solid red;
}
```

10. X[attributeName*="val"]

The following style rule selects any element with an "attr" attribute whose value includes the substring "goo".

```css
a[href*="goo"] {
  color: red;
}
```

11. X:checked

The :checked selector applies to toggable elements (e.g. radio buttons or checkboxes) that are toggled on.

```css
input[type=radio]:checked {
  border: 1px solid black;
}
```

12. X:after

Creates a pseudo-element, which allows you to insert content onto a page from CSS after the selected element.

```css
.title:after {
  content: "";
  display: block;
  border-bottom: 1px solid black;
}
```

13. X:before

Creates a pseudo-element, which allows you to insert content onto a page from CSS before the selected element.

```css
.title:before {
  content: "";
  display: block;
  border-top: 1px solid black;
}
```

14. X:not(...)

The negation pseudo-class, :not(X), is a functional notation taking a selector (excluding the negation pseudo-class itself) as an argument. It represents an element that is not represented by its argument.

```css
.p:not(.error) {
  color: pink;
}
```

15. X:first-line

Represents the first line of an element. Note that the content of the first line varies depending on the available width and the styling of text (size, spacing).

```css
p:first-line {
	font-weight: bold;
}
```

16. X:first-letter

Represents the first letter of an element, if it is not preceded by any other content (such as images or inline tables) on its line.

```css
p:first-letter {
	font-weight: bold;
}
```

17. X:nth-child(n)

This selector enables you to refer to a specific serial child elements

The parameter takes an integer. If you choose the 2nd item in the list, you need to use a construction: li: nth-child (2).

We can even select group of child elements. For example, to select every fourth item in the list, you need to use a construction: li: nth-child (4n).

```css
li:nth-child(3) {
   color: red;
}
```

5         5, ...
2n        2, 4, 6, 8, 10, ...
2n+1      1, 3, 5, 7, 9, ...
3n+2      2, 5, 8, 11, 14, ...
-n+3      3, 2, 1, ...
5n-2      3, 8, 13, 18, 23, ...
even      2, 4, 6, 8, 10, ...
odd       1, 3, 5, 7, 9, ...

18. X:nth-last-child(n)

The :nth-last-child(an+b) pseudo-class notation represents an element that has an+b-1 siblings after it in the document tree, for any positive integer or zero value of n, and has a parent element.

```css
li:nth-last-child(2) {
   color: red;
}
```

19. X:first-child

The :first-child pseudo-class represents an element that is the first child of some other element.

```css
li:first-child {
   color: red;
}
```

20. X:last-child

The :last-child pseudo-class represents an element that is the last child of some other element.

```css
li:last-child {
   color: red;
}
```

21. X:empty

The :empty pseudo-class represents an element that has no children at all. In terms of the document tree, only element nodes and content nodes whose data has a non-zero length must be considered as affecting emptiness; comments, processing instructions, and other nodes must not affect whether an element is considered empty or not.

```css
div:empty {
   background.color: green;
}
```
