---
title: "Labeling Regions"
permalink: /tutorials/page-structure/labels/
ref: /tutorials/page-structure/labels/
lang: en
# translators: # Uncomment (remove #) for translations, one - name line per translator.
# - name: Translator 1
# - name: Translator 2
# contributors:
# - name: Contributor 1
# - name: Contributor 2
github:
  repository: w3c/wai-tutorial-page-structure
  path: content/labels.md
footer: > # Text in footer in HTML
  <p> This is the text in the footer </p>

resource:
  ref: /tutorials/page-structure/

navigation:
  previous: /tutorials/page-structure/regions/
  next: /tutorials/page-structure/headings/

wcag_success_criteria:
  - 2.4.1
  - 2.4.6
wcag_techniques:
  - H69
  - ARIA11
---

Provide labels to distinguish two page regions of the same type, such as “main navigation” and “sub-navigation” menus using a `<nav>` element on the same page. Labels are also used to change the default identification of page regions, for example, to identify a `<aside>` region as “advertisement”. Regions that are unique, such as `<main>`, do not need additional labels.

## Using `aria-labelledby`
{:.ap}

Use `aria-labelledby` to point to an existing element by its (unique) `id`. The label of the region is the content of the referenced element. Every element can be a label this way. Labels should be short and descriptive. If a heading is present in the region, consider using it as the label:

{::nomarkdown}
{% include box.html type="start" title="Code Snippet" class="example" %}
{:/}

~~~html
<nav aria-labelledby="regionheading">
  <h3 id="regionheading">On this Page</h3>
    …
</nav>
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{% include ednote.html note="Figure out how to display links now that the sidebar is not available anymore." %}

Explore other WAI-ARIA resources:

* [WAI-ARIA Overview](https://www.w3.org/WAI/intro/aria)
* [Notes on Using ARIA in HTML](https://www.w3.org/TR/aria-in-html/)

Note: This approach using headings is also backward compatible for older web browsers and assistive technologies do not process HTML5 and WAI-ARIA.

## Using `aria-label`
{:.ap}

Use the WAI-ARIA `aria-label` attribute to label the region. Consider this approach if the label should not appear visually on the page.

{::nomarkdown}
{% include box.html type="start" title="Code Snippet" class="example" %}
{:/}

~~~html
<nav aria-label="Main Navigation">
  …
</nav>
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{% include ednote.html note="Figure out how to display links now that the sidebar is not available anymore." %}

View a [complete code example](example.html) with regions and labels.
