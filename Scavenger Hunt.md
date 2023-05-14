Title: Scavenger Hunt

Points: 50 points

Source: picoCTF2021 Web Exploitation

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/288ac6a7-b0f5-4870-9ace-fddecb2ce133)

On first glace, this is similar to picoCTF2019's insp3ct0r. Going to the link, it brings us to what looks exactly like the page for insp3ct0r.

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/caccafc9-960e-4c78-8bb0-9ee3357c65f1)

Inspecting the page source gives us 1/3 of the flag within the html source as well.

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/ada26d1c-4ee6-4c2b-a479-53f68199132c)

Then looking at css, it gives part 2 of the flag.

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/8ad69f94-e013-4273-a432-287ccdd7144d)

However, going to JS, it was a hint to the last part of the flag, instead of giving us the flag.

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/173aa13a-fb1a-4749-b60b-cceee3f45acc)

Google uses robots.txt to index pages, so adding a robots.txt to the end of the link would bring us to the robots page `http://mercury.picoctf.net:44070/robots.txt`.

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/17ac2d8c-7559-4c8b-b928-c9e8d11462dd)

It gives us part 3. but looks like there is another part. It tells us that it is an apache server. After some searching online, I came across that apache server could use `/htdocs` to set permission.
However, trying `http://mercury.picoctf.net:44070/htdocs` gave nothing. Further searching prompted me to try `.htaccess`, which allows changes to the permission of a directory. `http://mercury.picoctf.net:44070/.htaccess`. that gave us the 4th part of the flag, and another clue.

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/1353193f-3b40-4aa8-9e7f-3aaa193ec436)

Some searching online prompted that a Mac always creates a `.DS_Store` that stores custom attributes of the folder. It can be seen whenever we transfer stuff from a Mac to Windows computer through a thumbdrive. so trying `http://mercury.picoctf.net:44070/.DS_Store` gave us the final flag.

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/97dd1ac6-dc2a-4478-9d35-e61665896b6d)

Combining all 5 parts gave us the flag.
