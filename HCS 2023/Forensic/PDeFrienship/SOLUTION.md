# PDeFriendsip
Author: abdierryy

Category: Forensic

**Flag: HCS{PDF_IS_FRIENDS_OF_ALL}**

## Description
PDeF dan XeMaiL adalah sahabat dan teman baik, walaupun keduanya berasal dari negara yang berbeda namun mereka bisa akrab karena keduanya menggunakan bahasa yang sama pada saat berinteraksi

note: wrap the flag with HCS{}

please spare the every part of word with underscore

## Difficulty
Advance

## Solution
binwalk-ing the PDF file and _kaboom!_ there was two pics inside it

![binwalk1 2](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/a222e0d4-fcb3-4c29-b235-4142318fa8bf)

let's extract them all with command : **binwalk --dd='.*' (filename)** and look what we found

![extract1](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/2bfa514d-9a71-4c64-a708-c6e79dcda562)

alright let's visit this website
![629](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/9000905e-f235-4ec9-b576-c0a321880766)

well.. found this long base64
>aW4gdGhlIHRhZXN0cnkgb2YgbGlmZSwgYSB0aHJlYWQgc28gdHJ1ZSwKZnJpZW5kc2hpUCdzIGJvbmQgZW1lcmdlcyBpbiB2aWJyYW50IGh1ZS
>4KdHdvIHNvdWxzIGVudHdpbmVkLCBhIGpvdXJuZXkgdG8gZW1iYXJrLAphIHN5bXBob255IG9mIHRydXN0LCBsaWdodGluZyB1cCB0aGUgRGFyay4KC
>nRocm91Z2ggdmFsbGV5cyBsb3cgYW5kIG1vdW50YWlucyBoaWdoLApGcmllbmRzaGlwJ3Mgd2luZ3MgaGVscCB1cyB0b3VjaCB0aGUgc2t5LgphIHNoZWx0ZXIgSW4gc3Rvcm1
>zLCBhIGJlYWNvbiBpbiB0aGUgbmlnaHQsCmd1aWRpbmcgdXMgZm9yd2FyZCB3aXRoIGl0UyBnZW50bGUgbGlnaHQuCgpsaWtlIGEgc3ByaW5nJ3MgZml
>yc3QgYmxvb20sIEZyaWVuZHNoaXBzIHN0YXJ0LApudXJ0dXJlZCBieSBraW5kbmVzcyBmcm9tIHRoZSBoZWFydC4KaW4gbGF1Z2h0ZXIgc2hhcmVkIGFuZCB0ZWFycyB
>0aGF0IGZhbGwsCndlIGZpbmQgc29sYWNlIGluIGVhY2ggb3RoZVIncyBjYWxsLgoKZGlmZmVyZW50IGFzIHJpdmVycyB0aGF0IHdpbmQgYW5kIHR3aXN0LAp5ZXQgbWVyZ2luZ
>yBpbiBoYXJtb255LCBuZXZlciB0byByZXNpc3QuCnVuaXRlZCBpbiBwdXJwb3NlLCBoYW5kIEluIGhhbmQsCmZyaWVuZHNoaXAncyBkYW5jRSBhY3Jvc3MgdGhlIGxhbmQuCgppbiB0aGU
>gZ2FyZGVuIG9mIGxpZmUsIGZyaWVuZHNoaXAncyBhIGZsb3dlciwKYmxvb21pbmcgd2l0aCBncmFjZSwgaXRzIGZyYWdyYW5jZSBhIHNob3dlci4Kd2F0ZXJlZCBieSBtb2
>1lbnRzLCBib3RoIGJpZyBhTmQgc21hbGwsCml0IHN0YW5kcyBzdHJvbmcgYW5EIHRhbGwsIG5ldmVyIHRvIGZhbGwuCgp3aXRoIGVtcGF0aHkgYXMgaXRzIHJvb3RTIGFuZCBqb
>3kgYXMgaXRzIGxlYXZlcywKZnJpZW5kc2hpcCdzIG1hZ2ljIHNPb3RoZXMgYW5kIHJlbGlldmVzLgppbiB0aGUgZ2FsbGVyeSBvZiBtZW1vcmllcywgcG9ydHJhaXRzIGJ
>yaWdodCwKRnJpZW5kc2hpcCBwYWludHMgY29sb3JzIG9mIHNoZWVyIGRlbGlnaHQuCgpkaXN0YW5jZSBtYXkgc3RyZXRjaCBpdHMgdGhyZWFkcyB0aGluLApidXQgaW4gdGh
>lIGhlYXJ0J3MgY2FudmFzLCBpdCdzIHdvdmVuIGluLgp0aW1lIG1heSBhZ2UgdGhlIHN0b3JpZXMgd2UndmUgc3B1biwKYnV0IGZyaWVuZHNoaXAncyBtZWxvZHkgY0FuIG5ldmVyIGJlIHV
>uZG9uZS4KCnNvIExldCdzIHJhaXNlIGEgdG9hc3QgdG8gYm9uZHMgdGhhdCBiaW5kLAphIHRyZWFzdXJlIG9mIHRoZSBoZWFydCwgb25lIG9mIGEga2luZC4KdGhyb3VnaCBsaWZlJ3MgZ
>WJiIGFuZCBmbG93LCBoYW5kIGluIGhhbmQsCmZyaWVuZHNoaXAncyBzeW1waG9ueSBwTGF5cywgZm9yZXZlciBncmFuZA

alright let's decode it to string with this website https://www.base64decode.org/

and found some paragraphs
>in the taestry of life, a thread so true,
>friendshiP's bond emerges in vibrant hue.
>two souls entwined, a journey to embark,
>a symphony of trust, lighting up the Dark.

>through valleys low and mountains high,
>Friendship's wings help us touch the sky.
>a shelter In storms, a beacon in the night,
>guiding us forward with itS gentle light.

>like a spring's first bloom, Friendships start,
>nurtured by kindness from the heart.
>in laughter shared and tears that fall,
>we find solace in each otheR's call.

>different as rivers that wind and twist,
>yet merging in harmony, never to resist.
>united in purpose, hand In hand,
>friendship's dancE across the land.

>in the garden of life, friendship's a flower,
>blooming with grace, its fragrance a shower.
>watered by moments, both big aNd small,
>it stands strong anD tall, never to fall.

>with empathy as its rootS and joy as its leaves,
>friendship's magic sOothes and relieves.
>in the gallery of memories, portraits bright,
>Friendship paints colors of sheer delight.

>distance may stretch its threads thin,
>but in the heart's canvas, it's woven in.
>time may age the stories we've spun,
>but friendship's melody cAn never be undone.

>so Let's raise a toast to bonds that bind,
>a treasure of the heart, one of a kind.
>through life's ebb and flow, hand in hand,
>friendship's symphony pLays, forever grand

if you look CLOSELY, there's one suspicious thing, YUP! the uppercase!  
(_then i tried to write it down one by one but kept getting the wrong flag_)

So let's make a script! i wrote mine in C++ but it didn't work, so let's try Python!

![py](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/5981d8cf-768c-4993-8800-b94598191b99)

run the py file and put those paragraph as input and LOOK WHAT WE GOT!

![finish](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/9a89aebe-a6e1-4975-93b9-b6784ebe2c28)

then just add the brackets and underscores for each word and there you go the flag! :D  
**HCS{PDF_IS_FRIENDS_OF_ALL}**



