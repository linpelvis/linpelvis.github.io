#Elvis Blog

###[View Live Elvis Blog &rarr;](http://linpelvis.github.io)



### "Page Build Warning" email

These days, some of you must receive a "Page Build Warning" email from github after you commit happily. **Don't Worried!** It just that github changes its build environment.

In this mail, github told us:

> You are attempting to use the 'pygments' highlighter, which is currently unsupported on GitHub Pages. Your site will use 'rouge' for highlighting instead. To suppress this warning, change the 'highlighter' value to 'rouge' in your '_config.yml'.

So, just edit `_config.yml`, find `highlighter: pygments`, change it to `highlighter: rouge` and the warning will be gone.



## Translation

 - ![cn](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/China.png) **Chinese (Simplified)**: 感谢 [@BrucZhaoR](https://github.com/BruceZhaoR) 的 [中文翻译 &rarr;](https://github.com/linpelvis/linpelvis.github.io/blob/master/README.zh.md)


## Document

* Get Started
	* [Environment](#environment)
	* [Get Started](#get-started)
	* [Write Posts](#write-posts)
* Components
	* [SideBar](#sidebar)
	* [Mini About Me](#mini-about-me)
	* [Featured Tags](#featured-tags)
	* [Friends](#friends)
	* [Keynote Layout](#keynote-layout)
* Comment & Analysis
	* [Comment](#comment)
	* [Analytics](#analytics)
* Advanced
	* [Customization](#customization)
	* [Header Image](#header-image)
	* [SEO Title](#seo-title)

#### Environment

If you have jekyll installed, simply run `jekyll serve` in Command Line
and preview the themes in your browser. You can use `jekyll serve --watch` to watch for changes in the source files as well.


#### Get Started

You can easily get started by modifying `_config.yml`:

```
# Site settings
title: Elvis Blog             # title of your website
SEOTitle: Elvis Blog			# check out docs for more detail
description: "Cool Blog"    # ...

# SNS settings      
github_username: linpelvis     # modify this account to yours
weibo_username: linpelvis      # the footer woule be auto-updated.

# Build settings
# paginate: 10              # nums of posts in one page
```

There are more options you can check out in the [Jekyll - Official Site](http://jekyllrb.com/), or you can directly dive into code to find more.


#### Write Posts

Feel free to checkout Markdown files in the `_posts/`, you will quickly realized how to post your articles with magical markdown plus this nice theme.

The **front-matter** of a post looks like that:

```
---
layout:     post
title:      "Hello 2015"
subtitle:   "Hello World, Hello Blog"
date:       2015-01-29 12:00:00
author:     "Elvis"
header-img: "img/post-bg-2015.jpg"
tags:
    - Life
---

```

#### SideBar

![](http://huangxuan.me/img/blog-sidebar.jpg)

Seeing more information may be necessary for you to display, from V1.1, a clean, gorgeous **SideBar** is added for you, which provide more area for displaying possible modules. You can enable *(it is default enable)* this feature by simply config:

```
# Sidebar settings
sidebar: true
sidebar-about-description: "your description here"
```

We default support *[Featured Tags](#featured-tags)*, *[Mini About Me](#mini-about-me)* and *[Friends](#friends)* these three modules and you can add your own. The sidebar is naturally responsive and would be push to bottom in a small screen size (`<= 992px`, according to [Bootstarp Grid System](http://getbootstrap.com/css/#grid))  
More details of these three separate modules are talking below.

#### Mini About Me

Mini-About-Me module display all your SNS buttons also your avatar and the description if you set `sidebar-avatar` and `sidebar-about-description` which is very useful and common for a sidebar so it is default with your sidebar.

It is really nice-looking and well-designed. It would be hidden in a small screen seeing the sidebar would be push to bottom and there is already a footer including SNS feature which is similar.

#### Featured Tags

Considering the Featured-Tags feature in [Medium](http://medium.com) is pretty cool, so I add it in my blog theme also.   
This module is independent of sidebar from V1.4, so it can definitely live without enable sidebar, which would be displayed in the bottom when `sidebar` set to false, and it is not only displayed in home page but also every post page bottom.


```
# Featured Tags
featured-tags: true  
featured-condition-size: 1     # A tag will be featured if the size of it is more than this condition value
```

The only one thing need to be paid attention to is the `featured-condition-size`: A tag will be featured if the size of it is more than this condition value.  
Internally, a condition template `{% if tag[1].size > {{site.featured-condition-size}} %}` is used to do the filter.

#### Friends

Friends is a very common feature of a blog seeing the SEO, so I add it in V1.1 release to help that.   
Friends can also live without enable sidebar, also be displayed in the bottom when sidebar unable, and be displayed in every post page bottom.


You can just add your friends information in `_config.yml` with a familiar JSON syntax and everything is done, very easy:

```
# Friends
friends: [
    {
        title: "Foo Blog",
        href: "http://foo.github.io/"
    },
    {
        title: "Bar Blog",
        href: "http://bar.github.io"
    }
]
```


#### Keynote Layout

![](http://huangxuan.me/img/blog-keynote.jpg)

There is a increasing tendency to use Open Web technology to create keynotes, presentations, like Reveal.js, Impress.js, Slides, Prezi etc. I consider a modern blog should have abilities to post these HTML based presentation easily also abilities to play it directly.

Under the hood, a `iframe` is used to include webpage from outer source, so the only things left is to give a url in the **front-matter**:

```
---
layout:     keynote
iframe:     "http://huangxuan.me/js-module-7day/"
---
```

The iframe will be automatically resized to adapt different form factors also the device orientation. A padding is left to imply user that there has more content below, also to ensure that there is a area for user to scroll down in mobile device seeing most of the keynote framework prevent the browser default scroll behavior.


#### Comment

This theme support both [Disqus](http://disqus.com) and [Duoshuo](http://duoshuo.com) as the third party discussion system.

First, you need to sign up and get your own account. **Repeat, DO NOT use mine!** (I have set Trusted Domains) It is deathly simple to sign up and you will get the full power of management system. Please give it a try!

Second, from V1.5, you can easily complete your comment configuration by just adding your **short name** into `_config.yml`:

```
duoshuo_username: _your_duoshuo_short_name_
# OR
disqus_username: _your_disqus_short_name_
```

**To the old version user**, it's better that you pull the new version, otherwise you have to replace code in `post.html`, `keynote.html` and `about.html` by yourselves.

Furthermore, Duoshuo support Sharing. if you only wanna use Duoshuo comment without sharing, you can set `duoshuo_share: false`. You can use Duoshuo Sharing and Disqus Comments together also.



#### Analytics

From V1.5, we support Google Analytics and Baidu Tongji officially with a deathly simple config:

```
# Baidu Analytics
ba_track_id: 4cc1f2d8f3067386cc5cdb626a202900

# Google Analytics
ga_track_id: 'UA-49627206-1'            # Format: UA-xxxxxx-xx
ga_domain: huangxuan.me
```

Just checkout the code offered by Google/Baidu, and copy paste here, all the rest is already done for you.



#### Customization

If you wanna do more customization and change code yourself, a [Grunt](gruntjs.com) environment is also included. (Thanks to Clean Blog.)

There are a number of tasks it performs like minification of the JavaScript, compiling of the LESS files, adding banners to keep the Apache 2.0 license intact, and watching for changes. Run the grunt default task by entering `grunt ` into your command line which will build the files. You can use `grunt watch` if you are working on the JavaScript or the LESS.

**Try to understand code in `_include/` and `_layouts/`, then you can modify Jekyll [Liquid](https://github.com/Shopify/liquid/wiki) template directly to do more creative customization.**



## Thanks

This theme is forked from [IronSummitMedia/startbootstrap-clean-blog-jekyll](https://github.com/IronSummitMedia/startbootstrap-clean-blog-jekyll)  
Thanks Jekyll and Github Pages!
