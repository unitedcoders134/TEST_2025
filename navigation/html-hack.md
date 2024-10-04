---
layout: page
title: HTML Tutorial
permalink: /Html-Tutorial/
---

{% include nav/home.html %}

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML vs Markdown</title>
</head>
<body>
    <h2>How HTML Works</h2>
    <p>HTML works similarly to Markdown in that the syntax defines how content should be displayed on a webpage.</p>

    <h3>HTML Tags</h3>
    <p>HTML is based on beginning and closing tags:</p>
    <pre><code>&lt;tagname&gt;content&lt;/tagname&gt;</code></pre>
    <p>Note the “/” on the closing tag.</p>

    <h3>Comparison of Markdown vs HTML</h3>
    <h4>Markdown Example</h4>
    <pre><code>### Markdown: This is a Heading</code></pre>
    <pre><code>This is a paragraph</code></pre>

    <h4>HTML Example</h4>
    <pre><code>&lt;h3&gt;HTML: This is a Heading&lt;/h3&gt;</code></pre>
    <pre><code>&lt;p&gt;This is a paragraph.&lt;/p&gt;</code></pre>

    <h3>Attributes</h3>
    <p>Tags can have additional info in the form of attributes, which usually come in name/value pairs like:</p>
    <pre><code>&lt;tagname attribute_name="attribute_value"&gt;content&lt;/tagname&gt;</code></pre>

    <h4>Example with href attribute:</h4>
    <pre><code>&lt;a href="https://www.w3schools.com/html/default.asp"&gt;Visit W3Schools HTML Page&lt;/a&gt;</code></pre>
    <p><a href="https://www.w3schools.com/html/default.asp">Visit W3Schools HTML Page</a></p>

    <h3>Markdown vs HTML Tags</h3>
    <h4>Image Tag - Markdown</h4>
    <pre><code>![describe image](link to image)</code></pre>

    <h4>Image Tag - HTML</h4>
    <pre><code>&lt;img alt="describe image" src="link to image" width="100" height="200"&gt;</code></pre>

    <h4>Link Tag - Markdown</h4>
    <pre><code>[link text](link)</code></pre>

    <h4>Link Tag - HTML</h4>
    <pre><code>&lt;a href="link"&gt;link text&lt;/a&gt;</code></pre>

    <h4>Bolded Text - Markdown</h4>
    <pre><code>**Bolded Text**</code></pre>

    <h4>Bolded Text - HTML</h4>
    <pre><code>&lt;strong&gt;Bolded Text&lt;/strong&gt;</code></pre>

    <h4>Italic Text - Markdown</h4>
    <pre><code>*Italic Text*</code></pre>

    <h4>Italic Text - HTML</h4>
    <pre><code>&lt;i&gt;Italic Text&lt;/i&gt;</code></pre>

    <h3>More HTML Tags</h3>
    <h4>P Tag</h4>
    <pre><code>&lt;p&gt;This is a paragraph&lt;/p&gt;</code></pre>

    <h4>Button Tag</h4>
    <pre><code>&lt;button&gt;Click Me!&lt;/button&gt;</code></pre>
    <button>Click Me!</button>

    <h4>Div Tag</h4>
    <p>Div groups related content together:</p>
    <pre><code>
&lt;div&gt;
    &lt;p&gt;This is a paragraph in section 1&lt;/p&gt;
    &lt;p&gt;This is another paragraph in section 1&lt;/p&gt;
&lt;/div&gt;

&lt;div&gt;
    &lt;p&gt;This is a paragraph in section 2&lt;/p&gt;
    &lt;p&gt;This is another paragraph in section 2&lt;/p&gt;
&lt;/div&gt;
    </code></pre>

    <div>
        <p>This is a paragraph in section 1</p>
        <p>This is another paragraph in section 1</p>
    </div>

    <div>
        <p>This is a paragraph in section 2</p>
        <p>This is another paragraph in section 2</p>
    </div>

    <h3>Resources</h3>
    <p>For more information, visit <a href="https://www.w3schools.com/html/default.asp">W3Schools HTML Page</a>.</p>
</body>
</html>