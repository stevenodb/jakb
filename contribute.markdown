---
layout: default
title: "Contributing"
nav_order: 3
permalink: /contribute
---

# How to contribute to this knowledge base
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Summary
{: .no_toc }

1. If you don't have already, request _write_ access to `URL OF REPOSITORY`
2. Use the [GitHub.com interface][github] or clone the repository.
3. In the `{{ site.baseurl }}/pages` directory, __modify__ or [__add__ a new page](#adding-a-new-page).
4. Commit the result in a __new branch__.
5. Create a __Pull Request__.

[github]: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-content-to-your-github-pages-site-using-jekyll#adding-a-new-page-to-your-site


## Adding a new page

Pages are written in the popular [Markdown syntax][], optionally extended with [Liquid expressions][] and [Jekyll variables][].

### Front matter
Every page starts with a YAML _front matter_ block:
> The front matter must be the first thing in the file and must take the form of valid YAML set between triple-dashed lines.

```yaml
---
layout: default
title: "Contributing"
nav_order: 3
published: true # default: true ; false to hide
---
```

or, alternatively, leaving the front matter completely empty (two triple dashes `---` with nothing in between) is enough for Jekyll to pick up a page for publishing with sane defaults.

## Adding a section

Adding a section (or a _page with children_) is supported and can be nested too. For an explanation, you should [read the fine manual][sections] on this topic.

## Linking to pages within the site

Nothing stops you from using regular html links or markdown links
```html
<a href="https://link/to/page/awesome">read this awesome page</a>
[read this awesome page](https://link/to/page/awesome)
```
but these links would break when you move files around on the site---as links on the web do. There's a better way to create links that are validated when the site is redeployed: use Liquid script to build the link to the source document itself:
```markdown
[read this awesome page]({% raw %}{{ site.baseurl }}{% link link/to/page/awesome.markdown %}{% endraw %})
```

## Other features

For a complete list of layouting features we refer to the [complete documentation][] of Just The Docs.

[Markdown syntax]: https://www.markdownguide.org/basic-syntax#blockquotes-1
[Liquid expressions]: https://jekyllrb.com/docs/liquid/
[Jekyll variables]: https://jekyllrb.com/docs/variables/
[sections]: https://pmarsceill.github.io/just-the-docs/docs/navigation-structure/#pages-with-children
[complete documentation]: https://just-the-docs.github.io/just-the-docs/
