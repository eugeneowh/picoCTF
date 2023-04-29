Title: la cifra de

Points: 200 points

Source: picoCTF2019 Cryptography

![image](https://user-images.githubusercontent.com/91729496/235291853-27ec2b58-0d23-426d-a2b6-a2202a6cbd39.png)

Connecting with nc gives an encoded bunch of text, with a promising line:

![image](https://user-images.githubusercontent.com/91729496/235291892-d648d86c-fcaa-4768-81ca-ce1a8f2ab490.png)

Searching la cifra de on the internet tells us that it is spanish for `the figure of`. It also tells us that the bok La cifra del describes the Vigenere cipher. lets try decoding it in cyber chef `www.cyberchef.org` using that cypher then.
Using only the phrase that looks the most similar to the flag, lets see if we can figure out the key. To decipher it, we are trying to make `pohzCZK` into `picoCTF`. with that, the key would have to start with `a`, then `g`, and so on. we can use this table to help.
we look at the alphabet we want out of it on the top row (plaintext), and match it to the alphabet that we have inside the table (ciphertext), and refer to the left column to get the key.

![image](https://user-images.githubusercontent.com/91729496/235292417-e4e1c0d2-eee8-4147-98c3-3f662ef2d7a0.png)

the key repeats itself, giving the key as `agflagflagflag...` Revealling the flag!

![image](https://user-images.githubusercontent.com/91729496/235292709-424e77c9-48ff-49b8-a8d2-4a944ea50650.png)
