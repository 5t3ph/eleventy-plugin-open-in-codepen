## Eleventy Plugin: "Open in Codepen"

> An Eleventy shortcode to add "Open in CodePen" functionality for code demos.

## Usage

First, install the package:

```bash
npm install @11tyrocks/eleventy-plugin-open-in-codepen
```

Then, include it in your `.eleventy.js` config file:

```js
const openInCodepen = require("@11tyrocks/eleventy-plugin-open-in-codepen");

module.exports = (eleventyConfig) => {
  eleventyConfig.addPlugin(openInCodepen);
};
```

To use the shortcode, pass the expected properties inclusive of a `title`, `slug`, `css`, and `html`.

Within the context of a template, the `slug` is equivalent to the Eleventy provided `page.url` variable.

You can use the templating language abilities to set the variabls for `css` and `html`. For example `{% set css %}[CSS code]{% endset %}` for Nunjucks.

```js
{% postToCodepen "Pen Title", page.url, css, html %}
```

> **For an extended example** that includes how you might go about setting up the required demo data, review this [11ty Rocks tutorial](/posts/eleventy-templating-static-code-demos/).

## Config Options

| Option          | Type   | Default                      |
| --------------- | ------ | ---------------------------- |
| siteUrl         | string | https://codesampledomain.dev |
| siteTitle       | string | Example Site                 |
| siteTag         | string | codesampledomain             |
| buttonText      | string | Open in CodePen              |
| buttonClass     | string | open-in-codepen-button       |
| buttonIconClass | string | open-in-codepen-icon         |
| preDemoCSS      | string | _see below_                  |

The default `preDemoCSS` is a reduced sample from Andy Bell's [Modern CSS reset](https://piccalil.li/blog/a-modern-css-reset):

```css
/* Box sizing rules */
*,
*::before,
*::after {
  box-sizing: border-box;
}

/* Remove default margin */
body,
h1,
h2,
h3,
h4,
p {
  margin: 0;
}

/* Set core body defaults */
body {
  min-height: 100vh;
  text-rendering: optimizeSpeed;
  line-height: 1.5;
  font-family: system-ui, sans-serif;
}

/* Make images easier to work with */
img {
  display: block;
  max-width: 100%;
}
```

## Config Example

Here's an example of adding the plugin with config options set:

```js
eleventyConfig.addPlugin(openInCodepen, {
  siteUrl: "YourSite.dev",
  siteTitle: "Your Site",
  siteTag: "yoursite",
  buttonClass: "your-button-class",
  buttonIconClass: "your-button-icon-class",
});
```
