Title: strings it

Points: 100 points

Source: picoCTF2019 General Skills

![image](https://user-images.githubusercontent.com/91729496/235212587-7ed6dc13-0234-48dc-893d-dda3b6d1372d.png)

First, download the file. we get a file without extension. The title actually provided us the answer, so lets try using the strings command on it `strings strings` (yes it is confusing. the second "strings" is the file name, and the first one is the command)

![image](https://user-images.githubusercontent.com/91729496/235213092-c2e53b1c-62c3-4c45-8a21-9fdd900f4e4b.png)

we got a bunch of.... strings. lets use grep to find if any strings contain the flag format "picoCTF" `strings  strings | grep "picoCTF"`

![image](https://user-images.githubusercontent.com/91729496/235213293-aee54b3b-2ec3-4d69-8f26-f8116426389e.png)

got it!
