---
title: Global Game Jam 2015 Report - We Are Fox
date: 2015-02-14 22:45:00 -0200
layout: post
comments: true
demo: true
---
<div style="text-align:center" markdown="1">
![We Are Fox](/images/now-adventures.png)
</div>

Last month me and [yuriks](https://twitter.com/yuriks) went to Porto Alegre and participated in the [Global Game Jam](http://globalgamejam.org/)
at the UNISINOS site. It was a very nice little journey, we met with a group of artists that also went there
together and were interested in learning other technologies we had experience with, since they've only used Construct 2 before the jam.

We ended up being a big group for GGJ standards, amounting a total of seven people, with two programmers and
five artists. Since we had a big art workforce, we decided to walk the extra miles when it came to animation
and other graphical assets, which turned our game pretty good-looking.

After some long brainstorm sessions, we came up with the idea of a self-replicating character that could
perform three actions: running, attacking and pushing. These clones and actions would be used in conjunction
to solve puzzles, which consisted in getting from point A to point B without being killed by arrows, monsters or
holes in the ground.

Tech-wise, we went with [Unity](http://unity3d.com/) and [Tiled](http://www.mapeditor.org/). Since Unity can't
load a TMX out-of-the-box, we also looked for something that could export to it, and that's when we found
[Tiled2Unity](http://www.seanba.com/tiled2unity), a very handy tool that can load a TMX file and then export it
as a prefab directly instantiable in a Unity scene. We were able to make some cool things, such as adding
"placeholder" images in a Tiled layer, along with some custom attributes that enabled us to hook our own prefabs
for the various scripted objects when importing the prefab. It's really a pretty good tool, I may write a bit
about it, but I encourage anyone interested in the subject to take a look at the tutorials presented in their website.

By the end of the first night we had some programmer-drawn characters able to walk around the level with come basic collision.
The core mechanic was implemented by the end of the first twenty four hours, everything still with our programmer drawn
art (stressed again on purpose). After some irregular sleep and coffee, we started integrating the assets drawn by
the artists, and that's precisely when things got tough.

The first problem we had was with the character animations and Mecanim. For some unknown reason, our animator asset
corrupted after a few hours of tinkering and we had to redo everything. We weren't even able to move the blend tree
nodes in the animator screen, and that becomes a problem when you have about 200 frames resulting in 18 animations in
a 720p screen. We had some hiccups setting everything up, but I'd say that we were succesful in the end.

Another problem we had was the bottleneck of two programmers integrating all the art drawn by the artists in the
last hours. This was by far the biggest issue, since we didn't communicate properly and ended up having
to scale things up in the last minute, fix colliders, add offsets to a few sprites, change some component
properties, etc. Our actual dungeon tileset wasn't as complete as we expected, but we were able to improvise with
what we had in order to not comprimise what we have planned as the gameplay experience.

All things considered, I think Global Game Jam was a very good learning experience and that our game was succesfully
developed in the time constraints we had, as most of what we envised for the gameplay is there and functional. We could
use some extra levels and some bug fixing, but learning to properly handle this things is part of the goal of a game jam.

The game can be played [here](http://gamejolt.com/games/puzzle/we-are-fox/49327/)!

