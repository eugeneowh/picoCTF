Title: Matryoshka doll

Points: 30 points

Source: picoCTF2021 Forensics

![image](https://user-images.githubusercontent.com/91729496/236832161-92d8e293-7f36-405a-b5a5-aa90d7f2b538.png)

downloading the jpg file that they gave and trying to open it gave a file type error!

![image](https://user-images.githubusercontent.com/91729496/236832339-0c6074c0-d3dd-4224-9ce8-617fc9c1ddad.png)

we can do a `file` to see what type of file it is `file dolls.jpg`

![image](https://user-images.githubusercontent.com/91729496/236832494-257e9203-6ae8-4dcd-b4fe-e5d2e6e1401f.png)

It shows that it is .png file. But im not convinced, so lets try doing a binwalk `binwalk dolls.jpg`. Of files detected, it showed that there is a zip file inside.

![image](https://user-images.githubusercontent.com/91729496/236832700-4bffd9d5-48fd-418e-89f3-ca65040e2799.png)

Lets extract the zip file: `binwalk -e dolls.jpg`. it gave us another zip file and a base_image folder, which contains another .jpg file that cannot be opened. lets just try to do a binwalk and extract the .jpg file.

![image](https://user-images.githubusercontent.com/91729496/236833456-8e276504-4be7-4cec-a56d-4a8f9d254cd9.png)

As expected, it contained another zip file, and another folder containing yet another image. lets just use binwalk to extract from the .jpg file again. and yet another folder containing the same thing. we are at the 4th image!
and this time, we get a flag.txt!

![image](https://user-images.githubusercontent.com/91729496/236834088-afe378fb-4270-4a8d-bdde-fe3fc616fe26.png)

opening it of course, gives us the flag.

![image](https://user-images.githubusercontent.com/91729496/236834252-42682275-d9c8-4d2e-8eb6-315436174480.png)
