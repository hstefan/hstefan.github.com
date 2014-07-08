---
title: Pong Physics
date: 2014-07-06 22:20:00 -0300
layout: post
comments: true
---
Pong is one of the earliest arcade games, written to run in very simple hardware but with some interesting
properties with regards to its physics system. Basically, when the ball collides with the paddle its direction
is inverted and it starts going to the opposite side of the screen.

However, Pong itself and its several clones implement this in a way that the ball behaves differently according
to the part of the paddle it hits. This is exactly where things get a bit more interesting.

<div style="text-align:center" markdown="1">
![Ellipse Normals](/images/ellipse-normals.png)
</div>

The approach I took was to model the paddle as a convex surface, using the [parametric
equation of the ellipse](http://en.wikipedia.org/wiki/Ellipse#Parametric_form_in_canonical_position) and
its first derivative to obtain tangents (red lines in the figure above). After obtaining the equation for
the tangents, we can obtain our normals by finding a perpendicular vector to it (green lines).

![Pong Physics](/images/pong-physics.png)
The behaviour I wanted for the reflections is illustrated by drawing above. The black, green and red arrows represent
the current direction vector, surface normal and reflection vector, respectively.

What happens here is that the normals of the surface will affect the output angle of the ball, thus giving the player
more control on the player more control on where they want the ball to go.

The behaviour can be achieved by applying the [vector form equation of a specular reflection](http://en.wikipedia.org/wiki/Snell%27s_law#Vector_form).
To do that, we need to evaluate the equation of the normals at a given **t**, where **t** is the normalized height where the
ball hit the paddle.

And that's pretty much it. Have fun!
