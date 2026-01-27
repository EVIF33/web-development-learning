*The summary is based on the study of MDN (Mozilla Developer Network) materials*

# HTML Basics: Some important things

**HTML** *(Hypertext Markup Language)* - consists of a set of special tags and is used to mark up the structure and content of a website, which are then analyzed and interpreted by the browser.

**HTML** is the *framework* of the house (the beams, walls, and floors).

Think of **HTML** as the *blueprint* for a house. It defines where the walls, windows, and doors go. The browser is the *construction crew* that reads this *blueprint* and builds the structure you see on the screen.

## HTML Element Structure

Example of basic HTML element.
```html
<p>Create my first HTML element</p>
```
- `<p>` - opening tag.
- "Create my first HTML element" - Content.
- `</p>` - Closing tag.

## Nesting 

Elements can be *nested*, but it is important to follow the *sequence* of opening and closing tags.

```html
<p>Create my <strong>first</strong> HTML element</p>
```

Some elements have content restrictions:
- `<p>` cannot contain other block-level elements (div, section, another p)
- Use `<div>`, `<section>`, `<article>` to group content.


## Void Elements

There are also void elements that consist of a single tag. They can be used, for example, to embed content on a page.

```html
<img src="./source/void.jpg"/>
```

`/` is not required, but it does affect whether the HTML is valid XML.

## Attributes

Is a named value (a key-value pair) that modifies, configures, or defines the properties and behavior of the HTML element to which it is applied.

```html
<img src="./source/void.jpg" alt="Void element" width="600" height="600">
```

## Boolean attribute 

A Boolean attribute is a special type of attribute in HTML that does not require an explicit value. Its presence in the opening tag of an element activates a specific state or behavior (equivalent to true), while its absence deactivates it (equivalent to false).

Examples: *disabled*, *readonly*, *required*, *checked*, *selected*, *multiple*, *hidden*.

```html
<input type="checkbox" checked>
<input type="checkbox" checked="checked">
<input type="checkbox" checked="">
<input type="checkbox" checked="false"> <!--It's still true. -->
<button disabled>Disabled button</button>
```

```html
<input type="checkbox">
<button>Enabled button</button>
```

## HTML Document Structure

### Basic structure:

```html
<!doctype html> 
<html lang="en-US">
    <head>
        <meta charset="utf-8">
        <title>My basic HTML structure page</title>
    </head>
    <body>
        <p>Some content on the page</p>
    </body>
</html>
```
- `<!doctype html>` - **Document Type Declaration**. Activating the standard mode in the browser. Without <!doctype>, the browser can switch to compatibility mode (Quirks Mode). 
    - Standards Mode - The browser follows modern HTML/CSS standards. Correct display and predictable operation of layouts.
    - Quirks Mode - Emulates the behavior of old browsers (IE5, Netscape). Broken layout, incorrect box-model, dimensions.

- `<html></html>` - The **root** element of the HTML document. All the content of the page is *inside* it.
- `<head></head>` - Service container for page metadata. Its contents are not displayed in the browser window. These are instructions for the browser and search engines.
    - `<meta charset="utf-8">` - Specifying the character encoding for the document. It should be the first element inside `<head>` (immediately after the opening tag).
    - `<title></title>` - Page title. It is displayed not on the page itself, but in the browser tab, history, and search results.
- `<body></body>` - Container for all the visible content of a web page. Users see what's inside.

---

### Practical conclusions (for sandbox)

- Always start with `<!doctype html>`.
- Always add `<meta charset="utf-8">` first in `<head>`.
- `<p>` cannot contain other block-level elements.
- Do not use `px` in HTML attributes for `width/height`.
- Boolean attributes: presence = true, even if the value is `"false"`


