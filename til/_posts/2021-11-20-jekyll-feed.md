---
layout: til
title: "Jekyll Feeds Plugin on Github pages"
---

On another site I'm creating I didn't want a `feeds.xml` file. The default Jekyll configuration for Github pages includes the minima theme and the jekyll-feed plugin by default.

Removing jekyll-feeds from the jekyll `_config.yml` doesn't actually disable the plugin. [It seems I'm not the only one to be confused by this.](https://github.com/github/pages-gem/issues/627) Fortunately the suggestions on that issue from [creadone](https://github.com/creadone) worked for me.

To repeat them here:
- Remove the `jekyll-feed` plugin and `minima` theme from `_config.yml`
- Comment out these lines from Gemfile
  - `gem "minima", "~> 2.5"`
  - `gem "jekyll-feed", "~> 0.12"`
- For local development restart the jekyll server