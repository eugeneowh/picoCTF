Title: Caesar

Points: 100 points

Source: picoCTF2019 Cryptography

![image](https://user-images.githubusercontent.com/91729496/235285725-b7fa7691-f951-4245-b226-be75b767d952.png)

it looks like a simple problem that can be solved with cyberchef `www.cyberchef.org` too! Downloading the file given gives a ciphertext.

![image](https://user-images.githubusercontent.com/91729496/235285765-b0ca87b8-88b8-42ed-9f10-eb6da48667de.png)

We do not know what is the key to this cipher, so lets just try to brute force it and find the most likely answer

![image](https://user-images.githubusercontent.com/91729496/235285887-dba48a5a-d80e-4927-b5ac-a61226087823.png)

We can try to input the flag 1 by 1. But we just looked for the decrypted value that looks most like a proper sentence. Indeed that was the flag!
