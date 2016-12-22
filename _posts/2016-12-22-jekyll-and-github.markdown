---
layout: post
title:  "Jekyll and Github pages"
date:   2016-12-22 15:42:00 +1100
---

Since starting my adventure in learning to code, I'd been meaning to make a blog to document some of the things I've been learning - difficulties, lessons, achievements. Now it will also include some of the meetups I've been attending, as I'm realising more and more than networking and communities are going to be just as important in making me into a well rounded developer as technical skills.

Originally I'd planned to make myself a blog in Django to cement my understanding of the python framework. This presented some problems though:

* while it may have been a great learning opportunity, I was reinventing the wheel
* I'd have to host it somewhere
* I was opening up a can of security worms that I don't have the time or potentially the skills to deal with.

Then [Lucy][Lucy] posted on the Girl Geek Sydney slack channel about Github pages (hit me up if you're a Sydney Girl Geek and you'd like to join). If, like me, you hadn't heard of Github pages, Github allows you to attach a website to your github account, and gives you the url **username.github.io**. All you have to do it make a new repository called username.github.io (replacing username with your actual github username) and you can publish content simply by placing files in this repository. Boom, you have a website.

This seemed to be to be both a great idea to finally get good at  git, utilise that github account that had been sitting around empty for some time, and get myself a blog, all in one. And I'm pleased to say that since creating this blog in October I have now started utilising [my github account][github] and pushing code that I'm working on to it.

So that's the website, but now for the blog bit. Github pages comes with [Jekyll][Jekyll] ready installed. Jekyll is a static blogging framework built in Ruby. It uses markdown ([Kramdown][Kramdown]) for posts and [Liquid][Liquid] for templating. All you have to do is install ruby and jekyll on your computer, and then you can write and view your blog locally. You make a new .markdown file for each blog post, save it in your _posts folder and Jekyll does the rest. Once you're ready to show it off to the world you just git push the file to your github and voila! It's there for public consumption, formatted nicely, filed away in a folder structure organised by date, and linked from your homepage (or wherever you tell Jekyll to base itself in the config file).

You can tweak your css and templates to your liking. If you're using the default template then you can easily add disqus comments by adding the following to your config (if you're not using the default template then you will need to add some code to your templates or individual posts):

	disqus:
		shortname: my_disqus_shortname

Note: If you've installed Jekyll recently and noticed that when running locally, the Minima theme was creating its urls using the base hostname you'd specified in the config file, including for your css file, thus pulling your css from github instead of localhost - [update jekyll and github pages][update]! This has been fixed and you will no longer need the [workarounds][workarounds].

For more information check out the [Jekyll documentation][Jekyll docs] and the walkthroughs on [Github Pages][github pages] and [installing Jekyll locally][local Jekyll].

[Lucy]: http://lucybain.com/
[Liquid]: http://shopify.github.io/liquid/
[Kramdown]: https://kramdown.gettalong.org/
[github]: https://github.com/hannahcancode
[Jekyll]: https://jekyllrb.com
[Jekyll docs]: https://jekyllrb.com/docs/home/
[github pages]: https://pages.github.com/
[local Jekyll]: https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/
[workarounds]: https://talk.jekyllrb.com/t/current-jekyll-with-minima-does-not-render-css-on-localhost/2959
[update]: https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/#keeping-your-site-up-to-date-with-the-github-pages-gem