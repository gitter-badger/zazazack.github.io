---
    layout: post
    title: "Configuring Jekyll for Comments with Disqus"
    date: 2016-08-27 23:43:33 -0500
    categories:
        - development
    tags:
---

<!-- # TODO:

1. Input correct liquid syntax data into the embed code in `_includes/comments.html`
2. Provide instructions for using the "Comment-count" embed code -->

# Prerequisites

* [Jekyll site](https://zazazack.github.io/development/2016/08/21/gh-pages+jekyll.html)
* [Disqus account](https://disqus.com/profile/signup/)
* [Registered Forum on Disqus](https://disqus.com/admin/create/)

# Steps

Open terminal and change to your site's root directory, e.g.

```bash
$ cd ~/path/to/your/sites/username.github.io/
```

Open `_config.yml` and add the following to the end of the file

```yaml
# Defaults
defaults:
    -
        scope:
            path: ""
            type: "posts"
        values:
            comments: true
```

Open `_layouts/post.html` and add the following before the closing `</article>` tag

```liquid
{% raw %}{% include comments.html %}{% endraw %}
```


[Copy your Universal Embed Code](https://help.disqus.com/customer/portal/articles/466182-quick-start-guide) for the forum associated with your site

![Copy your Universal Embed Code](https://www.dropbox.com/s/dcxbeod72nvjtsd/Screenshot%202016-08-27%2017.10.07.png?dl=1 "https://disqus.com")

Switch back to terminal then change to your `_includes` directory

```bash
$ cd _includes/
```

Paste the _Universal Embed Code_ into a file called `comments.html`

```bash
$ nano comments.html
```

![`comments.html`](https://www.dropbox.com/s/5rpsuy3uiufmkcg/Screenshot%202016-08-27%2020.01.00.png?dl=1)

Then wrap your embed code as follows and save the file

```liquid
{% raw %}
{% comment %}
DISQUS UNIVERSAL EMBED CODE
Configure default behavior in `_config.yml`
Default is `comments: true` (i.e. all posts)
Toggle per post in frontmatter with `comments: false`
{% endcomment %}
{% if page.comments %}

**YOUR_EMBED_CODE_HERE**

{% endif %}
{% endraw %}
```

That's it! Verify that it works!

```bash
$ cd ..
$ bundle exec jekyll serve
```

![](https://www.dropbox.com/s/belmn8kz3pr46y2/Screenshot%202016-08-27%2023.04.59.png?dl=1)

[Disqus]: https://www.dropbox.com/s/moalss47rmi0q5w/Screenshot%202016-08-27%2016.38.59.png?dl=1 "https://disqus.com"
