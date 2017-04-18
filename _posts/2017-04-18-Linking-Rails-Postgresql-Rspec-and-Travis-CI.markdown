---
layout: post
title:  "Linking Rails, Postgresql, Rspec and Travis CI"
---

One of the things we're encouraged to do at Coder Factory Academy is - if we find a solution to something that isn't widely documented, write it up!

Well, I've done just that. A bit of background - our major project for Term 2 is to create a two sided platform using Ruby on Rails. We're required to use Postgresql for our database, and implement testing with Rspec. We've also been encouraged to look into code quality and deployment tools, so I wanted to get [Travis CI](https://travis-ci.org/) working to make sure my tests are passing with each push to and pull request on Github, and get that shiny badge on my project repository. Which I did!

![Travis CI build passing]({{ site.url }}/assets/travis-build-passing.png){: .small-image-centre}

However, while I could find advice for using Travis CI with postgresql, Travis CI with Rspec and Travis CI with Rails, I struggled to find something that pulled all three together. So, I wrote this tutorial to document what worked for me, and hopefully save others in my class a few stumbles down the wrong path. Check it out [on Github](https://github.com/hannahcancode/CFA-Travis-CI-Rails-Postgresql-Rspec), and let me know if there are any issues!
