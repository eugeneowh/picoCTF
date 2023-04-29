Title: dont-use-client-side

Points: 100 points

Source: picoCTF2019 Web Exploitation

![image](https://user-images.githubusercontent.com/91729496/235286061-3b14c0cb-5c12-48a6-8998-e4beee921435.png)

First, going to the link given

![image](https://user-images.githubusercontent.com/91729496/235286081-4380ed06-2f1c-436f-873c-c73a5ba1fc4a.png)

Inspecting the source gives a scrambled password:

![image](https://user-images.githubusercontent.com/91729496/235286126-006d3e3f-99eb-4e5e-8147-0757f453e612.png)

The password is broken into 4 char each to check, so by ordering the password from split*0 to split*8 would give the answer. Learning from previously, doing this manually is much faster...
