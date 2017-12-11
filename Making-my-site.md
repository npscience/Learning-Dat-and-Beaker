---
title: Making my blogsite
author: npscience
date: 2017-12-11T12:34:00.000Z
---


<!-- toc -->

- [Summary of trials](#summary-of-trials)
- [Requirements](#requirements)
- [Content](#content)
  * [Learning software and web development](#learning-software-and-web-development)
  * [Other content: travel, politics](#other-content-travel-politics)
  * [Data science [TBD]](#data-science-tbd)
- [Options](#options)
  * [Language: HTML v markdown v blogdown](#language-html-v-markdown-v-blogdown)
  * [Static site generator: Jekyll v Hugo](#static-site-generator-jekyll-v-hugo)
  * [CMS: GitHub pages v Netlify](#cms-github-pages-v-netlify)
- [Design](#design)

<!-- tocstop -->

# Summary of trials

* Standard WWW

- [x] Make my own using Hugo [local files ~/Hugo/Exocytosis_blogsite] and Netlify (:exclamation:didn't deploy, URI: exocytosis.netlify.com) [MY TRIAL NOTES](# Build in Hugo)
- [ ] Try https://pages.github.com/ using Jekyll
- [ ] Try pushing pages to my domain using SSH (http://www.openssh.com/)

Notes for this are at [Learn-Hugo](Learn-Hugo.md)

* Beaker

- [x] Basic static site: [Tutorial](https://beakerbrowser.com/docs/tutorials/create-a-markdown-site.html) | [My site on Beaker via dat](dat://exocytosis-naomipenfold.hashbase.io/) | [My site served on HTTPS](https://exocytosis-naomipenfold.hashbase.io/) Note that the HTTP stie is unstyled (no automatic rendering of markdown)
- [ ] Blogsite using jekyll: [Tutorial](https://beakerbrowser.com/docs/tutorials/create-a-blog.html)
- [x] Blogsite using Pipette (Hugo-based): [Tutorial blog](https://pipette-dev-blog-jimpick.hashbase.io/post/introducing-pipette/) | [Source code](https://github.com/jimpick/pipette-hugo-worker)

Notes for this are at [Try-Beaker](Try-beaker.md)

# Requirements

What do I want from my site?

* Simple way to create new blog in markdown and push to site. Host the markdown on GitHub. (Wouldn't it be simpler to create a GitHub page?)
* Navigation menu
* RSS feed
* Accessible via HTTP too, ideally linked to my domain (naomipenfold.com)
* Possible to add a design later
* Include Rmarkdown
* Freedom to include interactivity widgets
* Ability to accept PRs i.e. host files on Github or other open source collaborative repository.

The dream? A reproducible (Rmarkdown), runnable (Binder) and forkable (Beaker or GitHub) R website for exploring the world around me (and learning R).

# Content

The blogsite: 'exocytosis'

## Learning software and web development

- [ ] I have an API blog. Needs a clean up.
- [ ] I have a Dat blog. markdown is on Github already.
- [ ] I have TIL blogs. markdown files are on GitHub already.

## Other content: travel, politics
- [ ] naomipenfold.wordpress.com content, e.g. Japan blog. Take care re distributing Jason's photos.

## Data science [TBD]

None yet.

# Options

## Language: HTML v markdown v blogdown

HTML is original plain text language of the web, but markdown is simpler and I know it better. I'd like to use the latter, for now.

to incorporate rmakrdown, there's blogdown: https://github.com/rstudio/blogdown
Yihui Xie introduces it: https://blog.rstudio.com/2017/09/11/announcing-blogdown/ and you can see it in action at his personal blogsite: https://yihui.name/en/
Note many R sites listed in https://github.com/rbind including https://simplystatistics.org/

^^ This looks super cool, a challenge for another day.

## Static site generator: Jekyll v Hugo

Jekyll is what GitHub uses to push Pages.

Hugo is an open-source static site generator, alternative to Jekyll. https://gohugo.io/
Benefits:
* it's super fast (<1ms per page)
* flexible with languages (markdown plus 'shortcodes')

There's a comparison blog here: https://opensource.com/article/17/5/hugo-vs-jekyll
Apparently Hugo's downside is no plugin API yet.

## CMS: GitHub pages v Netlify

Why be tied to GitHub? Netlify seems simple enough. It's free for personal use.

# Design

Hugo templates at https://themes.gohugo.io/

Prefer topline menu than sidebar. I chose minimo: https://minimo.netlify.com/docs/installation/

Extension challenge: Could I open blogdown pages in Lens one day? Would need blog content to be in XML. Or to adapt Lens to take rmarkdown (and identify which are elements to pull into right-hand pane).

<!-- # Host

Decide on a url. I have naomipenfold.com already (GoDaddy)
What about an .io? interesting history on [Wikipedia](https://en.wikipedia.org/wiki/.io) IO = Indian Ocean (British Indian Ocean Territory). Note that domain registration is min. 1 year, max. 5 year. Techies like it because io is input/output. Also in Italio, Io = I therefore appropriate for personal blog.

Save naomipenfold.com for personal web CV.
Use exocytosis in URL. How does hashbase make URLs? (Note: exocytosis.com is $$$$$) -->
