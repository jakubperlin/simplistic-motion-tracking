# Simplistic motion tracking

By Jakub (Kuba) Perlin.

I implemented elementary motion tracking in Python. Only libraries I used were used for extracting frames from video and loading/saving pictures.

This project exists because I thought it would be nice to use motion capture to get animations for 2D game characters instead of creating them in software.

Currently this repository only contains the demo of the results, no code.

You can read a bit more about the program below the demo.

---

1. The source video (bike lights in a dark room):
![](https://raw.githubusercontent.com/jakubperlin/simplistic-motion-tracking/master/01a.gif)

2. After color ramping which detects objects of interest:
![](https://raw.githubusercontent.com/jakubperlin/simplistic-motion-tracking/master/01b.gif)

3. Centre of mass taken for each object. The visualization:
![](https://raw.githubusercontent.com/jakubperlin/simplistic-motion-tracking/master/01c.gif)

---

I also implemented (but haven't properly tested) the following features:

+ Suppose the points of interest are joints to a '2D person'. 
  
  Then I can specify how the joints are connected by bones (as long as it's a tree) and the program will ensure that bones never stretch throughout the animation.

+ The program also handles some cases of joint occlusion, i.e. interpolates if a joint is invisible for some frames.

Working on this simplistic project yielded lots of interesting questions, such as:

+ To make this approach work, one needs a distinct color material for each joint. How to make the single color version work, where joint-areas on video would constantly get occluded and merge together? 

+ With bone length normalization turned on, how to prevent the character model from shaking throughout animation?

+ How to best interpolate joint position while it's occluded? How to extrapolate (i.e. joint invisible till the last frame or from the 1st frame)?

---

Can also use the color ramping functionality for art:

![](https://raw.githubusercontent.com/jakubperlin/simplistic-motion-tracking/master/cactus.png)
