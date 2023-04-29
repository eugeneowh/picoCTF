Title: First Grep

Points: 100 points

Source: picoCTF2019 General Skills

![image](https://user-images.githubusercontent.com/91729496/235287290-3b1fe7ef-f382-443b-a04e-ca63bf2e0b0a.png)

lets download the file and see what we get: a file named file. Using the `file` command, we see that it is an ASCII file

![image](https://user-images.githubusercontent.com/91729496/235287342-741327ae-cb2d-4a3c-879c-4aba8efbd156.png)

Simply using the `grep` command, looking for the flag header `picoCTF`, we were able to find the flag! `grep "picoCTF" file`

![image](https://user-images.githubusercontent.com/91729496/235287368-e9609f7a-3bfa-4b97-95bf-13ede57beb21.png)
