# Css Style Guide

## Syntax

* When grouping selectors, keep individual selectors to a single line.
* Include one space before the opening brace of declaration blocks for legibility.
* Place closing braces of declaration blocks on a new line.
* Include one space after `:` for each declaration.
* Each declaration should appear on its own line for more accurate error reporting.
* End all declarations with a semi-colon. The last declaration's is optional, but your code is more error prone without it.
* Comma-separated property values should include a space after each comma (e.g., box-shadow).
* Don't prefix property values or color parameters with a leading zero (e.g., .5 instead of 0.5 and -.5px instead of -0.5px).
* Lowercase all hex values, e.g., `#fff`. Lowercase letters are much easier to discern when scanning a document as they tend to have more unique shapes.
* Use shorthand hex values where available, e.g., `#fff` instead of `#ffffff` and `#abc` instead of `#aabbcc`.
* Avoid specifying units for zero values, e.g., `margin: 15px 0;` instead of `margin: 15px 0px;`.

```css
/* Bad */
.selector, .selector-secondary, .selector[type=text] {
  padding:15px;
  margin:0px 0px 15px;
  background-color:rgba(0,0,0,0.5);
  box-shadow:0px 1px 2px #CCC,inset 0 1px 0 #FFFFFF
}

/* Good */
.selector,
.selector-secondary,
.selector[type="text"] {
  padding: 15px;
  margin-bottom: 15px;
  background-color: rgba(0, 0, 0, .5);
  box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}
```

## Organization

* Organize sections of code by component.
* Develop a consistent commenting hierarchy.
* Use consistent white space to your advantage when separating sections of code for scanning larger documents.
* When using multiple CSS files, break them down by component instead of page. Pages can be rearranged and components moved.

```css
/*
 * Component section heading
 */

.element { ... }

/* Contextual sub-component or modifer */
.element-heading { ... }

```

## Selectors

* Use classes over generic element tag for optimum rendering performance.
* Avoid using several attribute selectors (e.g., [class^="..."]) on commonly occurring components. Browser performance is known to be impacted by these.
* Keep selectors short and strive to limit the number of elements in each selector to three.
* Scope classes to the closest parent only when necessary (e.g., when not using prefixed classes).

```css
/* Bad */
span {
  ...
}

.page-container #stream .stream-item .tweet .tweet-header .username {
  ...
}

.avatar {
  ...
}

/* Good */
.avatar {
  ...
}

.tweet-header .username {
  ...
}

.tweet .avatar {
  ...
}
```

## Names & Capitalization

* Keep classes lowercase and use dashes (not underscores or camelCase). Dashes serve as natural breaks in related class.
* Avoid excessive and arbitrary shorthand notation. `.btn` is useful for button, but `.s` doesn't mean anything.
* Keep classes as short and succinct as possible.
* Use meaningful names; use structural or purposeful names.
* Prefix classes based on the closest parent or base class.
* Use `.js-*` classes to denote behavior (as opposed to style), but keep these classes out of your CSS.

```css
/* Bad */

.b {
  ...
}

#headerContainer {
  ...
}

.logoContainer {
  ...
}

#header_container {
  ...
}

.logo_container {
  ...
}

/* Good */
.btn {
  ...
}

#header-container {
  ...
}

.logo-container {
  ...
}
```

HTML elements should be in lowercase.

```css
/* Bad */

BODY,
DIV {
  ...
}

Body,
Div {
  ...
}

/* Good */
body,
div {
  ...
}
```


## Shorthand notation

Shorthand notation are CSS properties that let you set the values of several other CSS properties simultaneously. Using a shorthand property, a Web developer can write more concise and often more readable style sheets, saving time.

**Background properties**

A background with the following properties:
```css
.menu {
  background-color: #000;
  background-image: url(images/bg.gif);
  background-repeat: no-repeat;
  background-position: top right;
}
```
Can be shortened to just one declaration:
```css
.menu {
  background: #000 url(images/bg.gif) no-repeat top right;
}
```

**Font properties**

The following declarations:
```css
.menu a {
  font-style: italic;
  font-weight: bold;
  font-size: 16px;
  line-height: 16px;
  font-family: Arial, sans-serif;
}
```
Can be shortened to the following:
```css
.menu a {
  font: italic bold 16px/16px Arial, sans-serif;
}
```

**Border properties**

With borders, the width, color, and style can be simplified into one declaration:
```css
.menu li {
  border-width: 1px;
  border-style: solid;
  border-color: #000;
}
```
Can be shortened to the following:
```css
.menu li {
  border: 1px solid #000;
}
```

**Margin and Padding properties**

Shorthand versions of margin and padding values work the same way. The following CSS declarations:
```css
.menu ul {
  margin-top: 10px;
  margin-right: 5px;
  margin-bottom: 10px;
  margin-left: 5px;
}
```
Can be shortened to the following:
```css
.menu ul {
  margin: 10px 5px;
}
```

## Don't use `@import`

Compared to `<link>s`, `@import` is slower, adds extra page requests, and can cause other unforeseen problems

```html
<!-- Bad -->
<style>
  @import url("style.css");
</style>

<!-- Good -->
<link rel="stylesheet" href="style.css">
```


## Media query

The @media rule is used to define different style rules for different media types/devices.

In CSS2 this was called media types, while in CSS3 it is called media queries.

Media queries look at the capability of the device, and can be used to check many things, such as:

* width and height of the viewport
* width and height of the device
* orientation (is the tablet/phone in landscape or portrait mode?)
* resolution
* and much more

#### Syntax

```css
@media not|only media type and (media feature) {
    CSS-Code;
}
```

You can also have different stylesheets for different media:

```html
<link rel="stylesheet"
      media="mediaType and|not|only (media feature)"
      href="myStylesheet.css">
```


#### Media Types

Value  | Description
-------|----------------
all    | Used for all media type devices.
print  | Used for printers.
screen | Used for computer screens, tablets, smart-phones etc.

#### Media Features

Value  | Description
-------|----------------
aspect-ratio            |	The ratio between the width and the height of the viewport.
color                   |	The number of bits per color component for the output device.
color-index             |	The number of colors the device can display.
device-aspect-ratio     |	The ratio between the width and the height of the device.
device-height           |	The height of the device, such as a computer screen.
device-width            | The width of the device, such as a computer screen.
grid                    |	Whether the device is a grid or bitmap.
height                  | The viewport height.
max-aspect-ratio        | The maximum ratio between the width and the height of the display area.
max-color               |	The maximum number of bits per color component for the output device.
max-color-index         |	The maximum number of colors the device can display.
max-device-aspect-ratio |	The maximum ratio between the width and the height of the device.
max-device-height       |	The maximum height of the device, such as a computer screen.
max-device-width        | The maximum width of the device, such as a computer screen.
max-height              | The maximum height of the display area, such as a browser window.
max-monochrome          | The maximum number of bits per "color" on a monochrome (greyscale) device.
max-resolution          | The maximum resolution of the device, using dpi or dpcm.
max-width               |	The maximum width of the display area, such as a browser window.
min-aspect-ratio        | The minimum ratio between the width and the height of the display area.
min-color               | The minimum number of bits per color component for the output device.
min-color-index         |	The minimum number of colors the device can display.
min-device-aspect-ratio |	The minimum ratio between the width and the height of the device.
min-device-width        | The minimum width of the device, such as a computer screen.
min-device-height       | The minimum height of the device, such as a computer screen.
min-height              | The minimum height of the display area, such as a browser window.
min-monochrome          | The minimum number of bits per "color" on a monochrome (greyscale) device.
min-resolution          | The minimum resolution of the device, using dpi or dpcm.
min-width               | The minimum width of the display area, such as a browser window.
monochrome              | The number of bits per "color" on a monochrome (greyscale) device.
orientation             | The orientation of the viewport (landscape or portrait mode).
overflow-block          | How does the output device handle content that overflows the viewport along the block axis (added in Media Queries Level 4).
overflow-inline         | Can content that overflows the viewport along the inline axis be scrolled (added in Media Queries Level 4).
resolution              | The resolution of the output device, using dpi or dpcm.
scan                    | The scanning process of the output device.
update-frequency        | How quickly can the output device modify the appearance of the content (added in Media Queries Level 4).
width                   | The viewport width.

[Examples.](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries#Media_features)

**dpi**

This unit represents the number of dots per inch. A screen typically contains 72 or 96 dpi; a printed document usually reach much greater dpi. As 1 inch is 2.54 cm, 1dpi ≈ 0.39dpcm.

**dpcm**

This unit represents the number of dots per centimeter. As 1 inch is 2.54 cm, 1dpcm ≈ 2.54dpi.


#### Default Sizes for Twitter Bootstrap’s Media Queries

```css
/*==================================================
=            Bootstrap 3 Media Queries             =
==================================================*/


/*==========  Mobile First Method  ==========*/

/* Custom, iPhone Retina */
@media only screen and (min-width : 320px) {

}

/* Extra Small Devices, Phones */
@media only screen and (min-width : 480px) {

}

/* Small Devices, Tablets */
@media only screen and (min-width : 768px) {

}

/* Medium Devices, Desktops */
@media only screen and (min-width : 992px) {

}

/* Large Devices, Wide Screens */
@media only screen and (min-width : 1200px) {

}


/*==========  Non-Mobile First Method  ==========*/

/* Large Devices, Wide Screens */
@media only screen and (max-width : 1200px) {

}

/* Medium Devices, Desktops */
@media only screen and (max-width : 992px) {

}

/* Small Devices, Tablets */
@media only screen and (max-width : 768px) {

}

/* Extra Small Devices, Phones */
@media only screen and (max-width : 480px) {

}

/* Custom, iPhone Retina */
@media only screen and (max-width : 320px) {

}
```
