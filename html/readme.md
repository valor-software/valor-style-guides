# HTML Style Guide

## Use correct document type

Always declare the document type as the first line in your document:

```html
<!-- good -->
<!DOCTYPE html>

<!-- good -->
<!doctype html>
```

## Language

Always define which language the page is written in.

```html
<html lang="en"></html>
```

## Tag `meta`.

The `<meta />` tag provides metadata about the HTML document. Metadata will not be displayed on the page, but will be machine parsable.

Meta elements are typically used to specify page description, keywords, author of the document, last modified, and other metadata.

The metadata can be used by browsers (how to display content or reload page), search engines (keywords), or other web services.

For examples:

```html
<!-- Define keywords for search engines: -->
<meta name="keywords" content="HTML, CSS, JavaScript">

<!-- Define a description of your web page: -->
<meta name="description" content="HTML Style Guide">

<!-- Define the author of a page: -->
<meta name="author" content="Yura Betozov">

<!-- Refresh document every 30 seconds: -->
<meta http-equiv="refresh" content="30">

<!-- Redirect page after 3 seconds -->
<meta http-equiv="refresh" content="3;url=http://www.mozilla.org/">
```

[**More examples**](http://code.lancepollard.com/complete-list-of-html-meta-tags)

## Encoding

Always define the character encoding. The encoding should be defined as early as possible.

```html
<!-- Defining the charset in HTML4 -->
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />

<!-- In HTML5 -->
<meta charset="utf-8" />
```

## Close empty HTML elements

In HTML5, it is optional to close empty elements but I recommend to close empty elements.

For example:

```html
<!-- bad -->
<meta charset="utf-8">

<!-- good -->
<meta charset="utf-8" />
```

## Omit type attributes for style sheets and scripts

Do not use type attributes for style sheets and scripts.

Specifying type attributes in these contexts is not necessary as HTML5 implies text/css and text/javascript as defaults.
This can be safely done even for older browsers.

```html
<!-- bad -->
<link rel="stylesheet"
      href="//www.google.com/css/maia.css"
      type="text/css" />

<!-- good -->
<link rel="stylesheet"
      href="//www.google.com/css/maia.css" />

<!-- bad -->
<script src="//www.google.com/js/gweb/analytics/autotrack.js"
        type="text/javascript"></script>

<!-- good -->
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```

## Use lower case element names

```html
<!-- bad -->
<SECTION>
  <p>There should be the content.</p>
</SECTION>

<!-- bad -->
<Section>
  <p>There should be the content.</p>
</SECTION>

<!-- good -->
<section>
  <p>There should be the content.</p>
</section>
```

## Use lower case attribute names

```html
<!-- bad -->
<div CLASS="menu"></div>

<!-- good -->
<div class="menu"></div>
```

## Quote attribute values

```html
<!-- bad -->
<table class=table striped></table>

<!-- good -->
<table class="table striped"></table>
```

## Image attributes

Always use the alt attribute with images. It is important when the image cannot be viewed.

```html
<!-- bad -->
<img src="logo.jpg">

<!-- good -->
<img src="logo.jpg" alt="Logo" />
```

## Spaces and equal signs

```html
<!-- bad -->
<link rel = "stylesheet" href = "styles.css" />

<!-- good -->
<link rel="stylesheet" href="styles.css" />
```

## Avoid long code lines

When using editor, it is inconvenient to scroll right and left to read the HTML code.

Try to avoid code lines longer than 80 characters.

## Blank Lines and Indentation

Do not add blank lines without a reason.

For readability, add blank lines to separate large or logical code blocks.

```html
<!-- bad -->
<body>
<div id="header"></div>
<div id="main">
  <div class="article">

    <h2>Title</h2>

    <h3>Subtitle</h3>

    <p>Paragraph</p>
  </div>
</div>


<div id="footer"></div>
</body>

<!-- good -->
<body>
<div id="header"></div>

<div id="main">
  <div class="article">
    <h1>Title</h1>

    <h2>Subtitle</h2>
    <p>Paragraph</p>
  </div>
</div>

<div id="footer"></div>
</body>
```

## Reducing markup

Whenever possible, avoid superfluous parent elements when writing HTML.
Many times this requires iteration and refactoring, but produces less HTML.

For example:

```html
<!-- Not so great -->
<span class="avatar">
  <img src="..." alt="..." />
</span>

<!-- Better -->
<img class="avatar" src="..." alt="..." />
```

## Responsive meta tag

The viewport Meta tag alters the behavior of a mobile browser by modifying the "virtual viewport" of the device.
The virtual viewport is the view of a mobile device screen that is other than the default view;
therefore being deemed "virtual". This allows the screen on devices to have specified zoom behaviors.

```html
<meta name="viewport" content="width=device-width" />
```

This Meta tag tells the mobile device to not zoom.
This allows the Responsive Template for mobile devices to be loaded in the scripts.

It is a table of different properties that can be used for the viewpoint Meta Tag.

Property      | Description
--------------|------------------------------------------------------------------------
width	        | The width of the virtual viewport of the device.
device-width	| The physical width of the device's screen.
height	      | The height of the "virtual viewport" of the device.
device-height	| The physical height of the device's screen.
initial-scale	| The initial zoom when visiting the page. 1.0 does not zoom.
minimum-scale	| The minimum amount the visitor can zoom on the page. 1.0 does not zoom.
maximum-scale	| The maximum amount the visitor can zoom on the page. 1.0 does not zoom.
user-scalable	| Allows the device to zoom in and out. Values are yes or no.
