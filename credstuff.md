Title: credstuff

Points: 100 points

Source: picoCTF2022 Cryptography

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/33a06b90-95ce-4d6a-a2e0-8ce3e9090e04)

They gave us a .tar file that contains a username.txt and a password.txt file, and the challenge tells us that the first username corresponds to the first password.

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/7fc234be-c1d5-4a45-9078-1f52df641079)

Searching for the username to be cracked, we found it on entry 378. The corresponding password looks like a flag format. Perhaps we can try using cyberchef to decypher it.

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/ee4020da-d7a9-436d-9c47-333c68bcb16a)

Trying to decypher it with ROT13 gave us our flag!

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/f388c62b-633c-4e00-94f8-c354efdf504b)
