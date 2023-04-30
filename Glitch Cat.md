Title: Glitch Cat

Points: 100 points

Source: Beginner picoMini2022 General Skills

![image](https://user-images.githubusercontent.com/91729496/235367964-b50f8ce3-78fc-482e-acf3-7de2146ef1b2.png)

Lets connect to the address given and see what is glitching! `nc saturn.picoctf.net 53638`

![image](https://user-images.githubusercontent.com/91729496/235367995-3a84c457-eef5-4de1-94e0-e740b3f3fe4e.png)

Guess is a hex to char conversion issue. We can decode the `char(HEX_VALUE)` using the below ascii table.

![image](https://user-images.githubusercontent.com/91729496/235368059-a8f6b7ef-2199-4341-8f8d-9f484c2a97f2.png)

`'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'`
chr(0x62) gives the letter 'b', chr(0x64) gives d, and so on. converting all of them gives us the flag.
