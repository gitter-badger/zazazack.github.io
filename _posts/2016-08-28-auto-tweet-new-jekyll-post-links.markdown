---
    layout: post
    title: "Automatically Tweet New Jekyll Blog Posts Using IFTTT"
    date: 2016-08-28 12:26:41 -0500
    categories:
        - marketing
    tags:
        - blogging
        - Jekyll
        - GitHub Pages
        - Twitter
        - IFTTT
        - Social Media
        - automation
        - marketing
        - beginner
---
![](https://www.dropbox.com/s/nc4flb505q17ksi/Screenshot%202016-08-28%2012.57.10.png?dl=1 "https://ifttt.com")

If your site has an RSS feed, You can use IFTTT's Twitter channel to automatically tweet a link to new posts when a new feed item is generated.

# Prerequisites

Before you start, you'll need the following:

* A site with an RSS feed (e.g. [Jekyll](http://jekyllrb.com))
* [Twitter Account](https://twitter.com/signup)
* [IFTTT Account](https://ifttt.com/join)
* [Twitter Channel configured in IFTTT](https://ifttt.com/twitter)

# How to

First, go to your site and copy your site's RSS feed URL[^feedUrl]. For example, the feed URL for this site is <https://zazazack.github.io/feed.xml>

![Your rss feed url should be accessible from your site's homepage ](https://www.dropbox.com/s/z1mlrfzqng1zi5k/Screenshot%202016-08-28%2013.53.33.png?dl=1)

Next, go to [IFTTT](https://ifttt.com), click the &#9660; next to your username to open the dropdown menu, then click **Create**

![](https://www.dropbox.com/s/tyliu6gvku8rku6/Screenshot%202016-08-28%2013.30.15.png?dl=1)

Click **this** to start creating your recipe

![](https://www.dropbox.com/s/k8lqlzuvm6vjhg8/Screenshot%202016-08-28%2013.33.40.png?dl=1)

In the search bar, type **rss**, then click the **Feed** icon to choose your trigger channel

![](https://www.dropbox.com/s/9h8ztpw6gt3377t/Screenshot%202016-08-28%2013.35.12.png?dl=1)

Under **Choose a Trigger** select **New Feed Item**

![](https://www.dropbox.com/s/f00zxx82x2jsyfs/Screenshot%202016-08-28%2013.38.58.png?dl=1)

Under **Complete Trigger Fields**, input your feed's url and click **Create Trigger**

![](https://www.dropbox.com/s/qgk1xtwi411bah6/Screenshot%202016-08-28%2013.40.11.png?dl=1)

Click **that**

![](https://www.dropbox.com/s/qhadcy7s0oqk3x0/Screenshot%202016-08-28%2013.41.32.png?dl=1)

Under **Choose Action Channel**, search for **twitter**, then click the Twitter icon

![](https://www.dropbox.com/s/wv76jfvszsk9nlu/Screenshot%202016-08-28%2013.42.26.png?dl=1)

Choose **Post a Tweet**

![](https://www.dropbox.com/s/rcuikfjcsdbaq3z/Screenshot%202016-08-28%2013.44.15.png?dl=1)

Click **Create Action** (you can modify the **Action Fields** later)

![](https://www.dropbox.com/s/cp2cuolyqkwmu2o/Screenshot%202016-08-28%2013.44.52.png?dl=1)

Click **Create Recipe** (you can modify pretty much every option you've just selected later so don't worry about using the default)

![](https://www.dropbox.com/s/j0n2b68ko8y1vtj/Screenshot%202016-08-28%2013.46.26.png?dl=1)

That's it, you're done! Next time you publish a post, it will be automatically tweeted from your Twitter account!

[^feedUrl]: Make sure to copy the link from your live site (i.e. not a locally served url like `127.0.0.1/foo`).
