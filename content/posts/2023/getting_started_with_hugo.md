+++
title = "Getting started with Hugo for course content."
tags = ["hugo"]
draft = false
mathjax = true
hideMeta = false
date = 2022-08-05
ShowCodeCopyButtons = true
ShowBreadCrumbs = true
+++

I wanted a "simple" way to write my class materials in Markdown. Hugo magically makes it a website.
<!--more-->
I've been using Discourse for class content for about three years now - written in Markdown, I can easy mix text, math, and youtube videos and Discourse magically created the pre-class and post-class content pages. But of course that required students have a separate place to check for course materials, and I'm worried it wasn't viewed as often as I'd like.

Hugo takes Markdown and (almost) magically creates a static website. Nice!

In this post I'm going to document setting up the hugo blog for my course materials -- mostly for myself in case I need to recreate it in the future -- if you are reading this and are not me, let me know if it helps!


## Basic setup of the hugo blog {#basic-setup-of-the-hugo-blog}

... For this, look elsewhere and come back. (sorry)

Here's a [link to mine on GitHub](https://github.com/jmhammond/math-courses) with information about cloning and setting up.


## Setting up Mathjax 3 {#setting-up-mathjax-3}

There's really three things that need to happen to use Mathjax on a page:

1.  You need to create a mathjax `partial`. This will live in `site-name/layouts/partials/mathjax_support.html`:
    ```html
       <script>
         MathJax = {
         tex: {
         packages: ['base', 'ams'],        // extensions to use
         inlineMath: [ ['$','$'], ['\\(','\\)'] ],
         displayMath: [             // start/end delimiter pairs for display math
         ['$$', '$$'],
         ['\\[', '\\]']
         ],
         processEscapes: true,      // use \$ to produce a literal dollar sign
         processEnvironments: true, // process \begin{xxx}...\end{xxx} outside math mode
         formatError:               // function called when TeX syntax errors occur
         (jax, err) => jax.formatError(err)
         }
         };
       </script>
       <script type="text/javascript" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
       </script>
    ```

2.  and then in the `site-name/layouts/extend_head.html` file, add the following:
    ```go
       {{ if .Params.mathjax }}{{ partial "mathjax_support.html" . }}{{ end }}
    ```
    The conditional means that mathjax won't load on every page (since it does add overhead). It will only be on pages that request it.

3.  To add mathjax to the page, you need to add the page parameter to the (toml) frontmatter: `mathjax= true`.


## Fonts and Colors {#fonts-and-colors}

In order to match some of the [look and feel of the official WSU website](https://www.wichita.edu/services/strategic_communications/brand_standards/colors_and_fonts.php), I specified css files for hugo which automatically get picked up and used. For this, I created a `fonts.css` and `custom.css` file in the folder `site-name/assets/css/extended`.


## Spoiler shortcode {#spoiler-shortcode}

If you want to be able to hide an answer/solution so students need to click to reveal it,


I've created a simple spoiler tag as a [Hugo shortcode.](https://gohugo.io/content-management/shortcodes/)  The above example was created by:

```html
{{ < spoiler > }}
... like this ...
{{ </ spoiler > }}
```

Add this file to `site-name/layouts/shortcodes/spoiler.html`

```html
<div class="spoiler"><details {{ if (eq (.Get "openByDefault") true) }} open=true {{ end }}>
  <summary markdown="span">Click to reveal the answer.</summary>
  {{ .Inner | markdownify }}
</details></div>
```

and add this CSS to the `site-name/assets/css/extended/custom.css` file:

```css
/* For the spoiler tags  */

.spoiler {
    margin: 0 5px 40px 5px;
    border: 1px solid var(--border);
    background: var(--entry);
    border-radius: var(--radius);
    padding: 0.4em;
}

.dark .spoiler {
    background: var(--entry);
}

.spoiler details summary {
    cursor: zoom-in;
    margin-inline-start: 20px;
}

.spoiler details[open] summary {
    cursor: zoom-out;
}

.spoiler .details {
    display: inline;
    font-weight: 500;
}

.spoiler .inner {
    margin: 0 20px;
    padding: 10px 20px;
}

.spoiler li ul {
    margin-inline-start: var(--gap);
}

.spoiler summary:focus {
    outline: 0;
}
```
