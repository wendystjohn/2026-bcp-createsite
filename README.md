# Welcome!

This is a [Jekyll] site for the 2026 summer BCP 101 workshop at UC
Davis. It uses the [Just the Docs] theme and is built and published on
[GitHub Pages]. The site itself is published at
[ngs-docs.github.io/2026-summer-bcp-101](https://ngs-docs.github.io/2026-summer-bcp-101/).

Please see
[the front page](https://ngs-docs.github.io/2026-summer-bcp-101/) for
details on the workshop itself. Contact any and all of Titus Brown,
Cassie Olivas, and Max Chin for more information - you can reach
Titus at ctbrown@ucdavis.edu.

## Adding pages

To add a new page, put a Markdown file in the top-level directory of this
site with the following information in a YAML section at the top:

```
---
title: Home
layout: home
---
```

To link pages, link them using the HTML filename.

Once committed and pushed, the updated page(s) should be available within
3 minutes.

## Licensing and Attribution

This repository is licensed under the [MIT License]. You are generally free to reuse or extend upon this code as you see fit; just include the original copy of the license (which is preserved when you "make a template"). While it's not necessary, we'd love to hear from you if you do use this template, and how we can improve it for future use!

The deployment GitHub Actions workflow is heavily based on GitHub's mixed-party [starter workflows]. A copy of their MIT License is available in [actions/starter-workflows].

----

[^1]: [It can take up to 10 minutes for changes to your site to publish after you push the changes to GitHub](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll#creating-your-site).

[Jekyll]: https://jekyllrb.com
[Just the Docs]: https://just-the-docs.github.io/just-the-docs/
[GitHub Pages]: https://docs.github.com/en/pages
[GitHub Pages / Actions workflow]: https://github.blog/changelog/2022-07-27-github-pages-custom-github-actions-workflows-beta/
[Bundler]: https://bundler.io
[use this template]: https://github.com/just-the-docs/just-the-docs-template/generate
[`jekyll-default-layout`]: https://github.com/benbalter/jekyll-default-layout
[`jekyll-seo-tag`]: https://jekyll.github.io/jekyll-seo-tag
[MIT License]: https://en.wikipedia.org/wiki/MIT_License
[starter workflows]: https://github.com/actions/starter-workflows/blob/main/pages/jekyll.yml
[actions/starter-workflows]: https://github.com/actions/starter-workflows/blob/main/LICENSE
