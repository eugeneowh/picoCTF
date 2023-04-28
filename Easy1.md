Title: Easy1

Points: 100 points

Source: picoCTF2019 Cryptography

![image](https://user-images.githubusercontent.com/91729496/235213650-e0c5bb89-b8fa-4bde-83f9-f3311f194911.png)

As always, start by downloading the file given

![image](https://user-images.githubusercontent.com/91729496/235213870-4c8fa66b-469d-431f-8579-1596ed88c78d.png)

Seems like a decryption table. to decrypt `UFJKXQZQUNB` with the key of `SOLVECRYPTO`, lets match each alphebet in the table (e.g. U and S giving M, F and O, and so on).

![image](https://user-images.githubusercontent.com/91729496/235214379-53bf8c2f-30f4-4044-985d-e9000fcc9de3.png)

Doing this for the rest gives the flag.
