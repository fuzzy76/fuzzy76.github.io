# My homepage

My personal website. Used to be Wordpress. Now it isn't. :) 

This is a work in progress. I'll finish theme, plugins and content in that order.

## Tech stack

* [Github pages](https://help.github.com/categories/customizing-github-pages/)
* [Jekyll](https://jekyllrb.com/docs/home/)
* [Bootstrap](https://getbootstrap.com/docs/4.0/getting-started/introduction/)
* [Bootswatch](https://bootswatch.com)
* [Font Awesome](https://fontawesome.com)
* [Disqus](https://help.disqus.com/customer/portal/articles/1104788-web-integration)

## Features

* Responsive design
* Opengraph tags
* RSS-feed
* Sitemap
* Robots.txt
* Search
* OpenID2 provider link
* Google Analytics
* Favicons in way too many variants

## License

I'm not licensing this out in any way. It's open source, but still mine. I
really don't see any reason to change that for now.

## Design considerations

I am not a designer, so I'm relying on Bootstrap and Bootswatch for typography,
colors and components.

## Structure

This site contains a static frontpage, serving as an "about me" page as well as
two blog categories. The blog is divided into english and norwegian posts. The
former will be mostly technical articles, whiles the latter will be mostly
related to the discourse within Norway. There are also some hidden blog posts
mostly because I didn't want to delete my ancient "dear diary" posts, but didn't
see any reason to list them.

Unfortunately the index pages are not paginated because the builtin pagination
support in Jekyll isn't able to paginate across categories (which I use to
separate the blog sections). This can hopefully be fixed once
[https://github.com/sverrirs/jekyll-paginate-v2](jekyll-paginate-v2) is moved
into Jekyll core and deployed on GitHub pages.

## Configuration specifics

The excerpt separator is set to "&lt;--more--&gt;" for compatibility reasons.

## Jekyll-plugins

Relies on the following Jekyll plugins:
* [jekyll-gist](https://github.com/jekyll/jekyll-gist)
* [jekyll-relative-links](https://github.com/benbalter/jekyll-relative-links)
* [jekyll-default-layout](https://github.com/benbalter/jekyll-default-layout)
* [jekyll-titles-from-headings](https://github.com/benbalter/jekyll-titles-from-headings)
* [jekyll-seo-tag](https://github.com/jekyll/jekyll-seo-tag)
* [jekyll-feed](https://github.com/jekyll/jekyll-feed)
* [jekyll-sitemap](https://github.com/jekyll/jekyll-sitemap)

Might be handy:
* [jekyll-redirect-from](https://github.com/jekyll/jekyll-redirect-from)

## Validation concerns
Validated as of 08.04.2018.

### HTML

I won't declare language, since this site mixes norwegian and english. This is
allowed, just not recommended.

###  CSS

Bootstrap 4 creates a lot of errors warnings. Their priority is compatibility
over standard compliance – fair enough.

### Bootlint

Bootlint is not Bootstrap 4 compatible yet. As far as I could tell, everything
it reported was because of that.

### Feed

The Atom feed apparently reports wrong language code. Since my site is mixed
language and the functionality is from a third party plugin, it's not a
priority.

### OpenGraph

OpenGraph seems to validate.

### Sitemap

Sitemap seems to validate.

