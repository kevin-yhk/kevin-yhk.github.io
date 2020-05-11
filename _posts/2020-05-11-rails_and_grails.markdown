---
layout: post
title:      "Rails and Grails"
date:       2020-05-11 05:52:52 +0000
permalink:  rails_and_grails
---


It was definitely a bittersweet moment getting to this point in this bootcamp.  I, unfortunately was afflicted by corona virus (even when I practiced all the safe measurements) and it was very daunting and challenging to be behind a bit during this module but eventually I was able to do it after a full recovery.  Rails appeared to just throw so much information compared to that of Sinatra, and while there is a very simple way to finish this Rails project by using scaffold, that simply would've just made all the learning up to this point moot. 

For this particular project, I decided to use shoes as my main focal point because I am an avid collector of sneakers. I set my models and relationships in a way that a Users would be able to write reviews on specific shoes or their own personal grails (coveted sneakers). The schema of this model would like this:
* Shoes would belong_to both User and Reviews
* A User has_many Shoes through Reviews and has_many Reviews
* Review has_many Users through Reviews and has_many Shoes

Seemed simple enough after getting the relationship set up but there was so much more to the project at hand that I simply overestimated my own abilities on getting this project done immediately. I took the time to look over the resources and the lessons that I have learned prior to this building process and applied those lessons directly to the project itself. 

Rails g resource was such a huge time saver as it would generate my database tables, my models, views, and controllers for me.  Taking it step by step and making sure that the relationship that I have set between these three models was very crucial in that even one little mishap can bring the entire project to fail, and there were many times when I felt as if I had hit a stonewall and didn't know how to progress any further. 

Looking back on it after having completed the project, I'm really ecstatic at how much I've come along and am really excited to finally get into JavaScript. I still remember Day 1 of this bootcamp and wondering if I will be able to make it as far as I have made it right now. 
