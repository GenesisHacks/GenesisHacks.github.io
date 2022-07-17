---
layout: post
author: Joel Clement
---

Recently I was invited to take part in the Quorum Cyber CTF organised by Capture The Talent. In this 3 part series I go over my 3 favourite challenges from the CTF showing how I solved them and what I learned from them.

## Amy's (Still) Confused

![challenge description](https://i.imgur.com/uPUa5fv.png) 

In this part we look at a challenge called "Amy's (Still) Confused". For this challenge the description was “Some stunning photography, I am sure you will agree. Look at the drama!” alongside this there was also a picture to download.

![challenge image](https://i.imgur.com/7aaphON.jpg) 

I first tried some basic ideas such as looking at the HEX data of the image and the exif data but had no luck with these, so I started thinking more about steganography tools. A really common one is steghide so I tried using this… Hmm it asks for a passphrase.

![steghide](https://i.imgur.com/wOFZdMc.png) 

It turns out that a passphrase isn’t always needed and just pressing enter to go to the next step will work just fine in this case, but this is where I need to admit I might have over complicated this one a bit.
Rather than trying no passphrase as intended, I looked for a way to crack it and I found stegseek. This is a really cool steghide cracker that uses a wordlist to brute force the passphrase so I installed it and gave it a go. This of course still worked and I found a file called “lolwut.m4a” 

![stegseek](https://i.imgur.com/opGd8fR.png)

This is an audio file, so I gave it a listen and it read out an encoded message. “3433203534203534203736203638203331203634203639203665203637203566203734203737203331203633203333203231203764”
I had no idea what type of encoding this could be, so I used the magic setting on cyberchef and got these results.
 
![cyberchef](https://i.imgur.com/eY8EKW4.png)

“CTTvh1ding_tw1c3!.” It’s not perfect but it’s enough for me to know the flag is CTT{h1ding_tw1c3!}
While my mistake of over complicating the challenge has left me feeling a bit dumb, I’m actually glad that I made it, I learned much more this way. Not only do I now know that a passphrase is not always required but I also found a nice tool to crack passphrases in the future.
