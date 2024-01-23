# Lend Me Your Signature
Author: abdierryy

Category: Forensic

**Flag: HCS{N1c3_Th4ts_VerY_Ea5y_R1ghT????}**

## Description
Aku sedang dikirim gambar waifu oleh temanku, tapi sepertinya gambar tersebut tidak bisa dilihat. Tolong bantulah aku!

## Difficulty
Easy

## Solution
so we got a corrupt png file

![pngcheck](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/88e7e867-f50f-4d32-9165-e17eac069c22)

well i'm guessing it has something to do with the IHDR/IEND hex chunk? so let's see the hex with Bless

![bless1](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/cdd2a8ff-41a6-4645-9c42-e20ee2148a5d)

hummm that's not a correct hex for PNG signature..  
based on this website https://asecuritysite.com/forensics/png?file=%2Flog%2Fbasn0g01.png it should be  
 **89 50 4E 47 0D 0A 1A 0A**  
so let's repair that hex

![bless2](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/44c6109d-bf88-40b8-a77a-063e06dbeeef)

well after we saved that file, we still couldn't open it.. so let's try to find another wrong hex  

![bless4](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/dfd44c70-08c3-493c-a967-f2a4494105d9)

Hum.. what even is this? a png file ends with "IHCS"? nonono let's change it to IEND hex :
**49 45 4E 44** 

and.. we got the picture! _(as you might guess.. an anime..)_

![chall](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/e15d354a-b035-4e12-aa88-d3b1b2551d4b)

but humm.. we couldn't find anything in this picture.. so let's see more information about it with exiftool  
**exiftool (filename)**

![exif1](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/5257a059-a1ed-41dc-afdf-47ffe2fa12f9)

something caught my attention.. the Comment! it has a hint T***PNG? a PNG tool? well we also got a hint about the image dimension.. so let's try to find that tool  
> _(after lot of searching.. and lot of trying to change the dimension with its hex but didn't work.. i finally found the tool!)_
 
it was....  **TweakPNG**!

so let's install and run the tool
**Click the "Critical" in Attributes to change the dimension.. also use "Tools" for Image Viewer**

![tweak1](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/34808546-07c4-4e8a-891e-5ade64ba9e2a)

then we can just add the height until we can see the flag! (it will appear at 400)

![flag1](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/9b0e05d5-f896-494f-9695-8c8823f862be)

save the modified image and rotate it

![flag3](https://github.com/ZalfaNafila/HCS-writeup-2023/assets/92864261/0b04b721-3700-4fd6-b750-fb6b8fa587db)

Yey gottem! **HCS{N1c3_Th4ts_VerY_Ea5y_R1ghT????}**  
> nah, it wasn't easy.. i was stuck for hours trying to change the dimension and to find the tool D:



