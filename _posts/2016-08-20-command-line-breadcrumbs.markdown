---
layout: post
title:  "Command-line Breadcrumbs"
date:   2016-08-20 16:11:59 -0500
categories:
    - productivity
    - organization
tags:
    - command-line
    - cli
    - dev
    - terminal
    - linux
    - unix
    - gtd
---

## Gist

Use bash's comment char (`#`) at the command-line prompt to leave yourself a trail of breadcrumbs back to how, why and when, e.g.

{% highlight bash %}
$ cd ~/project-foo/
$ # Adding .gitignore file per https://help.github.com/articles/ignoring-files/
$ touch .gitignore
{% endhighlight %}

To retrieve your comment breadcrumbs pipe the output from the `history` command to `grep` to filter lines containing bash's comment char (`#`)[^backslashEscapes].

### Input

{% highlight bash %}
$ history | grep \#
{% endhighlight %}

[^backslashEscapes]: the hash (`#`) must be escaped with a backslash (`\`)

*[char]: character

### Output:

{% highlight bash %}
10 # Adding .gitignore file per https://help.github.com/articles/ignoring-files/
{% endhighlight %}

## histtimeformat

Breadcrumbs are even more useful if you configure the `HISTTIMEFORMAT` environmental variable by adding the following line to your `.bashrc`[^bash_profile]:

{% highlight bash linenos %}
# ~/.bashrc
# show the date and time
export HISTTIMEFORMAT="%Y-%m-%d %T "
{% endhighlight %}

To add the `HISTTIMEFORMAT` variable to your `.bashrc` and re-source the file do:

{% highlight bash %}
$ echo "export HISTTIMEFORMAT="%Y-%m-%d %T " >> ~/.bashrc; source ~/.bashrc
{% endhighlight %}

Now, the `history | grep \#` output will also provide date/time when the line was added to the `.bash_history` file like:

{% highlight bash %}
10  16-08-20 16:40:07    # Adding .gitignore file per https://help.github.com/articles/ignoring-files/
{% endhighlight %}

[^bash_profile]: or `.bash_profile` depending on your setup
