---
layout: news
author: Alfred Don
tags: games devlog
---
![]({{ "assets/images/news/Screenshot_Doom_20230426_143141.png" | absolute_url }})


Random events have been added to Tormater 2: Electric Boogaloo. For most of them, they involve spawning in objects, or giving inventory items to the player. Most of the events are shown on screen, but others happen without any notice.

I've added an ACS script to the mod that runs a while loop, which has an if block inside that determines whether it should trigger an event. No event can happen twice in a row, and they have a delay of about a minute and a half before it will run the code again.

Overall, it adds to the TORMATER in Tormater 2. The new update will be coming soon!
