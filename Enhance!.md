Title: Enhance!

Points: 100 points

Source: picoCTF2022 Forensics

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/88e3d6e4-3bea-459f-b093-a4ef2d9589d7)

downloading the image file gives us an svg that looks like this if opened in GIMP.

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/42e10259-9cf1-4044-b238-9557e5ccf630)

After playing with it awhile on GIMP using enhance, i was unable to find the flag. So I opened it using Geany, to look at the code. Scrolling all the way down, it looks like the flag is there!

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/908280aa-a996-431b-b5f7-4c2d6f2628be)

Lets combine it manually to get our flag. Take note that it is separated by a space each char, so we have to combine it without the spaces, and that there is an additional space, which i assumed to be "_". that gave us our flag!
