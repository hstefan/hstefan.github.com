---
title: Pong Physics
date: 2014-07-06 5:56:00 -0300
layout: post
comments: true
---
Pong is one of the earliest arcade games, written to run in very simple hardware but with some interesting
properties with regards to its physics system. Basically, when the ball collides with the paddle it's direction
is inverted and it starts going to the other side of the screen. However, Pong itself and its several clones
implement this in way that the ball behaves differently accordingly to the part of the paddle it hits. This is
exactly where things get a bit more interesting.

![Pong Physics](/images/pong-physics.png)
The way I implemented this was by making the reflection logic take in account both the current direction on the
ball and the surface normal of the paddle. In scenario (a), we can see that the resulting direction (green line)
has a smaller angle than the angle of incidence, since the surface normal on that region is steeper in relation
to the Y axis. In scenario (b) both the incidence and the output angles are the same, since the normal is pointing
to the X-axis. In (c), we can observe that the output direction can have a bigger angle if the ball is moving in 
a direction closer to where the normal is pointing.

<div style="text-align:center" markdown="1">
![Ellipse Normals](/images/ellipse-normals.png)
</div>

The approach I took was to model the paddle as a convex surface, using the [parametric
equation of the ellipse](http://en.wikipedia.org/wiki/Ellipse#Parametric_form_in_canonical_position) and
its first derivative to obtain tangents. With this in hand, all we need to do is to find a perpendicular
vector to the tangent and we'll have our normals. Since we are working with 2D coordinates, we can achieve
that by swapping x and y coordinates and inverting the signal of one of them, (e.g. [x, y] becomes [-y, x]).

In order to find our new direction for the ball after it reflects on a paddle we can apply the [vector equation
of a specular reflection](http://en.wikipedia.org/wiki/Snell%27s_law#Vector_form). To do that, we need to
evaluate the equation of the normals at a given **t**, where **t** is the normalized y position where the
ball hitted the paddle. With this last piece, we can finally put our vectors back into the reflection equation and
obtain our new direction vector.

One last piece that you might want to do is to restrain a maximum angle to the vector, since we don't want
to make it possible for the ball to get stuck in the y-axis or take too long to reach the other side of the screen.
Unfortunately I wasn't able to find an elegant way of doing this. What I did was to find the absolute values of the
direction vector and measure the angle of it with the **i** vector. If this angle is bigger than our constraint,
we generate a new vector with the maximum inclination allowed and restore its signals.

And that's pretty much it. Have fun!
