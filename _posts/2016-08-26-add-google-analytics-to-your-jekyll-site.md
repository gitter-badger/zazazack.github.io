---
    layout: post
    title: "Add Google Analytics to your Jekyll Site"
    date: 2016-08-26 02:02:55 -0500
    categories:
        - marketing
    tags:
        - marketing
        - development
---

<!-- Don't forget obscure any sensitive info in these screenshots!!! -->

If you've [set up a Jekyll site via GitHub Pages](https://zazazack.github.io/development/2016/08/21/gh-pages+jekyll.html) it's pretty easy to add Google Analytics to your site. All you need is is a [Google Analytics account](https://support.google.com/analytics/answer/1008015?hl=en).

Here's what to do:

Copy your [Google Analytics tracking code](https://support.google.com/analytics/answer/1008080))

```html
<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

  ga('create', 'YOUR-TRACKING-ID-HERE', 'auto');
  ga('send', 'pageview');

</script>
```

Paste your tracking code into a file and name it `analytics.html`

![](https://www.dropbox.com/s/4g34c8fbtnda3nx/Screenshot%202016-08-26%2001.31.37.png?dl=1)

Place `analytics.html` in your `username.github.io/_includes` file.

![](https://www.dropbox.com/s/elv7c74qra3a2ef/Screenshot%202016-08-25%2021.43.42.png?dl=1)

Open `username.github.io/_layouts/default.html`

![](https://www.dropbox.com/s/r1qjeuoo71dzacf/Screenshot%202016-08-25%2021.44.51.png?dl=1)

Under `{% raw %}{% include head.html %}{% endraw %}` paste the following line:

![](https://www.dropbox.com/s/35dy13atkx6ggo0/Screenshot%202016-08-26%2001.46.07.png?dl=1)

Don't forget to commit and push your changes to github so you can view them on your site.

```bash
$ cd /foo/bar/username.github.io/
$ git add .
$ git commit -m "added ga-tracking code to enable Google-Analytics"
$ git push
```

Now [confirm analytics is running](https://support.google.com/analytics/answer/1008083?hl=en) and enjoy the beautiful data!
