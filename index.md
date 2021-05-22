---
layout: base.njk
templateEngineOverride: njk,md
---
{% set css%}
.bold { font-weight: bold; }
{% endset %}

{% set html %}
  <p class="bold">Hello world</p>
{% endset %}

### CSS
<pre><code>{{ css | safe }}</code></pre>

### HTML
<pre><code>{{ html | safe }}</code></pre>

{% postToCodepen "Plugin Test", "https://example.com/plugin-test", css, html %}
