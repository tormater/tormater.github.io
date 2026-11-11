---
layout: news
author: Alfred Don
tags: games devlog
---
![]({{ "assets/images/news/screenshot.png" | absolute_url }})

Today, I've added a new lighting system, which has a day and night cycle. Most bright things in-game now emit a spotlight, which shows as a bright spot through a dark overlay.

The way the lighting system works is fairly simple. I created a texture with a blue background, and I set that as the rendering target. Then, I draw an additive gradient from light to black on top of the background. All the little lights on-screen are drawn with the same method.

The day and night cycle is achieved by a timer that controls the opacity of an additive white overlay on the texture. Once all the modifications are done, the texture is drawn on-screen with a modulate blend mode.

After doing all of this, I end up with a pretty convincing night look in the game. In the future, I may try to implement shadows during the day with the same system.
