---
layout: post
title:  "Coder Factory Academy - One Term Down"
---

Term one of Coder Factory is done and dusted! We're currently on a week break, and my classmates are variously recovering, sleeping, and even still going into class to study. I have been playing with my Arduino (a seperate post is in the works for that).

Week 5 was our introduction to Rails and the Model, View, Controller (MVC) proper. In week 4 we'd touched upon it to use the controller and views to make websites with no database backend, but now we're starting to get to grips with databases and where everything sits in MVC.

Once again Coder Factory comes through for me and my learn-by-doing style, with these concepts demonstrated by whipping up Instagram and Twitter clones. We used  Rails with PostgreSQL databases and some ruby gems - [Devise](https://github.com/plataformatec/devise) for user login, [Socialization](https://github.com/cmer/socialization) for likes and follows, and [Carrierwave](https://github.com/carrierwaveuploader/carrierwave) for image uploading.

One thing I really enjoyed about Rails was using the command line console to access our data, without needing to know all the usual SQL syntax. For example, this spits out just the information from the id and description columns of the Post table:

   `` > Post.pluck(:id, :description)``

Another console command I used a lot was this, which would allow you to find the Post with id: 1 and update one (or more) of it's attributes.

   `` > p = Post.find(1) ``

   `` > p.update!(title: "My Cool Title")``

Handy for development.

In my previous post I was pretty excited about the concept of putting logic in html - well, I've since learnt that while you can do this do some extent, it's much better to put your logic in the controller or the model and feed the result through to the view. Good to know!

Finally, I'm loving discoving different html frameworks available. This week I've been playing with [Materialize CSS](http://materializecss.com/), which is a framework built around Google's Materialize framework. It's kind of bizarre but very fun to emulate Google's design with a few short lines of code. It's pretty basic at the moment, but here's my Twitter clone, Meower, using Materialize CSS:

![Meower screenshot]({{ site.url }}/assets/meower.png){: .img-responsive, image-centre}

So that's what we've learnt in one term at Coder Factory. We've done ruby, rails, MVC, html, css and a few frameworks. We went from calculator terminal apps written in Ruby to pretty websites made with CSS and bootstrap, to twitter clones with database backends. I'm pretty impressed with everything we've managed to get through, and I'm still excited to see what we'll come up with once we throw JavaScript into the mix!
