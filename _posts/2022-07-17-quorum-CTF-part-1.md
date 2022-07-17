---
layout: post
author: Joel Clement
---

Recently I was invited to take part in the Quorum Cyber CTF organised by Capture The Talent. In this 3 part series I go over my 3 favourite challenges from the CTF showing how I solved them and what I learned from them.

## Wiggle It

In this first part we look at a challenge called "Wiggle It". This was a really fun challenge. We were given the name of a crematorium in Sheffield and had to find the specific make and model of the printer they use at the site. 

![challenge description](https://i.imgur.com/2v4kCYK.png) 

As an OSINT noob I had no idea where to start with this one – I found the crematorium but that was just a simple google search away where could I possibly go from here? After a bit of searching it turns out there was a huge clue in the name… Wiggle is refering to wigle.net a wireless network mapping website. 

![wigle](https://i.imgur.com/IsTEHnZ.png) 


Now all I had to do was find the crematorium and the printer. Looking on google again it’s easy to find the address so I just put that into wigle.net

![cremgoog](https://i.imgur.com/e2Drqwy.png) 
 
![cremwigle](https://i.imgur.com/gLGFOGD.png)

Well we got the road but its not the exact right place so next I did a bit of searching and it looks like we found the right place.

![cremfound](https://i.imgur.com/BLlI4pi.png) 
 
![printer](https://i.imgur.com/EIYOqDQ.png)

I zoomed in and found this so the flag is “CTT{HP_ENVY_4520}”!
