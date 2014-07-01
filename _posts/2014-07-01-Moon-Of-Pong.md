---
title: Moon of Pong
date: 2014-07-01 1:00:00 -0300
layout: post
comments: true
demo: true
---
<div style="text-align:center" markdown="1">
![Moon of Pong](/images/MoonOfPong.png)
</div>

After finishing my game for [One Game a Month](http://www.onegameamonth.com/) I decided I wanted
to write a Pong clone for June's entry. I'm happy to say that I just finished it and I'll be sending it
today!

This time I've used the excellent [Löve](http://love2d.org/) framework to develop my game and I'm very glad
I did it. Lua itself has some pitfalls that I fell for but overall it's a very interesting language for rapid
development. Löve is also very simple and takes care of most of the plumbing you'd have to do for a game,
which in my case resulted in a quickier development experience.

Pong made me revisit some topics on analytic geometry and calculus in order to find some interesting logic
for the ball-paddle reflections. In the end I decided to extract the normals of the paddle's surface from
an ellipse equation, which by itself will probably earn a post in this blog in the near future.

You can play the game [here](/files/MoonOfPong.zip). The keyboard controls are up/down and w/s and
there's support for joysticks too.
