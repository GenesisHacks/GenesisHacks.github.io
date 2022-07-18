---
layout: post
author: Joel Clement
---

Recently I was invited to take part in the Quorum Cyber CTF organised by Capture The Talent. In this 3 part series I go over my 3 favourite challenges from the CTF showing how I solved them and what I learned from them.

## "2+2=4-1=3 Qwik Maffs"

Now for some cryptography. In this final part we look at a challenge called "2+2=4-1=3 Qwik Maffs". I’m a little bit more familiar with cryptography but this was still something new to me and helped me learn a little more about RSA.

![challenge description](https://i.imgur.com/gzSqdkP.png) 

The challenge asks us to find the original message using 3 numbers and 3 cipher texts. The message has the same value for 3 public moduli. Using this information, I learnt that I can perform a hastad broadcast attack. This attack uses Chinese remainder theorem to decrypt the message, so I had a look at how to do this and wow all that maths looks a bit too confusing for now. Fortunately, I also found a nice python script that can do the work for us 😊 

```python

from sympy.ntheory.modular import crt
from gmpy2  import iroot

n = [86812553978993, 81744303091421, 83695120256591] 
c = [8875674977048, 70744354709710, 29146719498409] 

e=3

resultant, mod = crt(n,c)
value, is_perfect = iroot(resultant,e)
if is_perfect:
  print(value)
```

![result](https://i.imgur.com/E5U2Aks.png) 

If we run this we get “683435743464” we’ve still not got the flag just yet but I can tell this is hex so lets try putting it in cyberchef 

![answer](https://i.imgur.com/vgcISF8.png) 

We get the output h45t4d so we know the flag is CTT{h45t4d}.
