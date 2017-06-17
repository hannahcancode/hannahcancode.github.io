---
layout: post
title:  "Final CFA project - Jules' Wardrobe"
---

Last week was my final week of classes with Coder Academy (previously known as Coder Factory Academy) and on Friday we all presented our final projects. The variety was pretty outstanding, from VR galleries to warehouse scanners to restaurant buzzers and React dashboards - I was really proud of all my fellow classmates, we've come so far! I wanted to write a quick post about my project - Jules' Wardrobe.

![Jules' Wardrobe]( http://res.cloudinary.com/doe2gejvd/image/upload/s--E_LxoOj6--/v1497253693/Screen_Shot_2017-06-12_at_5.47.07_pm_yn9vio.png){: .img-responsive, .small-image-centre}

The spiel goes like this - have you seen Clueless? Because I made a mobile app inspired by Cher's Closet. It was on the request of a friend - we had to work with a client for this project - but it's a project I'm very excited about. If you haven't seen Clueless for a while, [this video](https://www.youtube.com/embed/XNDubWJU0aU) might give you some indication of what I was expected to make! (Well, not quite that. I'm yet to get touchscreen working on a Classic Macintosh!)

Jules' wardrobe is a visual representation of a user's wardrobe. It is a mobile app that allows them to upload photos of their clothes, categorize them as tops, bottoms or shoes (for the first iteration at least), and then flick through the carousels of clothes to see how an outfit would look without having to try it on. If the user is feeling uninspired there's also a shuffle button that will start all the carousels spinning and create a random outfit. It's a fun app with some useful benefits - if you've ever created a floordrobe while attempting to pick out a new outfit, or you always wear the same thing because you're not sure what will look good together, this is for you.

For the project my client and I decided an iPhone app would be the best platform. We'd been learning React in class, but I'd already looked into React Native and I decided that would be a good framework to use, along with a Node.js/Express.js/MongoDB backend using the Cloudinary API for image storage. I was really happy with the outcome from using React Native - it's a really satisfying feeling to have such responsive, native components on your device that respond well to touch.

![Jules wardrobe](http://res.cloudinary.com/doe2gejvd/image/upload/s--IxCYo44S--/c_scale,h_442,q_58/v1497684990/juleswardrobe_duetsk.gif)

That said, there's still lots of work to be done. As we had less than two weeks from ideation and initial design to presentation of our MVP (minimal viable product) my code needs some cleanup! I need to refactor my components into seperate files, implement Redux and recreate some of the open source components so they're more suited to my design. While the final project may be submitted and presented at this point, I still plan to keep working on this as a side project.

See the [GitHub repository](https://github.com/hannahcancode/CFA-wardrobefront) for more information on the project, including design and installation instructions. Let me know if you have any thoughts or ideas!
