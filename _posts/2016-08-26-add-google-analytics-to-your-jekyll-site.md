---
    layout: post
    title: "Add Google Analytics to your Jekyll Site"
    date: 2016-08-26 02:02:55 -0500
    categories:
        - marketing
    tags:
        - marketing
        - development
        - analytics
        - blogs
---

If you've [set up a Jekyll site via GitHub Pages](https://zazazack.github.io/development/2016/08/21/gh-pages+jekyll.html) it's pretty easy to add Google Analytics to your site. Analytics is a "free" service from Google and can help you improve the usefulness of your site with insight into user behavior.

![Google Analytics](https://www.dropbox.com/s/6ou9tpmbtn43w1e/Screenshot%202016-08-28%2010.34.54.png?dl=1)

# Prerequisites

* [Jekyll/GitHub Pages Site](https://zazazack.github.io/development/2016/08/21/gh-pages+jekyll.html)
* [Tracking code for your Google Analytics property](https://support.google.com/analytics/answer/1008015?hl=en&ref_topic=3544906)

# Implementation

Open terminal and change to your site's root directory, e.g.

```bash
$ cd ~/path/to/your/site/username.github.io/
```

Open `_layouts/default.html` in your favorite text editor, e.g.

```bash
$ nano _layouts/default.html
```

Under `{% raw %}{% include head.html %}{% endraw %}` add the following line:

```liquid
{% raw %}{% include analytics.html %}{% endraw %}
```

![`default.html`](https://www.dropbox.com/s/xs8xgprlsldchij/Screenshot%202016-08-28%2011.12.04.png?dl=1)

Visit <https://analytics.google.com> and copy your [Google Analytics tracking code](https://support.google.com/analytics/answer/1032385?hl=en)

![](https://www.dropbox.com/s/x1ktjcx0qkvy10e/Screenshot%202016-08-28%2010.48.54.png?dl=1)

Create a new file in `_includes/`, paste your tracking code in it and save it as `analytics.html`, e.g.

```bash
$ nano _includes/analytics.html
```

![`analytics.html`](https://www.dropbox.com/s/jy0kbduqrdjlh3a/Screenshot%202016-08-28%2011.15.46.png?dl=1)

# Test

Verify that your site is working locally

```bash
$ bundle exec jekyll serve
```

Copy the `Server Address`, e.g.

```bash
JekyllAdmin mode: production
  Server address: http://127.0.0.1:4000/    # open in your browser to view your site locally
Server running... press ctrl-c to stop.
```

While you're viewing your site, open your web inspector to view the page as source and check to see if the tracking code is visible

You should see the contents of `analytics.html` after the closing `</head>` tag, e.g.

![View your site pages' source to verify that your ga-analytics script is included ](https://www.dropbox.com/s/0m0kaj7eqkw7pit/Screenshot%202016-08-28%2011.55.38.png?dl=1)

Check that you see this code on all (or at least _some_ of) your site's pages.

# Deploy

If everything looks good, commit and push your changes to github so you can view them on your site

```bash
$ git add .
$ git commit -m "added ga-tracking code to enable Google-Analytics"
$ git push
```

Finally, [confirm analytics is running](https://support.google.com/analytics/answer/1008083?hl=en) on the live site and enjoy the beautiful data!
