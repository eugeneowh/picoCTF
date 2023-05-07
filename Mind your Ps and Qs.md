Title: Mind your Ps and Qs

Points: 20 points

Source: picoCTF2021 Cryptography

![image](https://user-images.githubusercontent.com/91729496/236677131-f5df895c-4035-4a20-86dc-2d00c66e93d0.png)

downloading the values, we are given n, e, and c. we can easily dump all those values into an online decrypter like `https://www.dcode.fr/rsa-cipher`, but what is the fun in that?
lets try to crack it ourselves.

`n = p * q`, where `p` and `q` are private keys. `c` is the ciphertext to be decrpyted. the formula for decryption is `c**d mod n = m`, where `m` is the message in cleartext.
`d = e**-1 mod ((p-1)(q-1))`. with so many formulas, lets start 1 by 1. `p` and `q` are the most important, as they form the basis of all the private keys that are not given.
To find `p` and `q`, we have 2 find 2 prime numbers that multiply to form n. to do this naively, lets run through all the numbers from 2 to sqrt n to find p and q. after which we can check if p and q are prime numbers just as a confirmation (not necessary)

After running for about 30 minutes, i gave up and let it run, while i got the values of p and q (and everything else) from the online decrypter. However, with just the p and q values, lets calculate the rest of the values, just for the fun of it.

![image](https://user-images.githubusercontent.com/91729496/236685424-6ce59d10-9aef-4ae9-979c-2b9ebb1a802c.png)

`p = 1899107986527483535344517113948531328331`, `q = 674357869540600933870145899564746495319033`. `phi = (p-1)*(q-1) = 1280678415822214057864524798453297819181234364596418349127352680639289550089776560`.
Which matches what was given on the decrypter.

![image](https://user-images.githubusercontent.com/91729496/236685535-32dd5631-fcdb-4df5-a5ea-f5a512c51e38.png)

Next to find `d` is also simple `d = e**-1 mod phi`, or in python: `d = pow(e,-1,phi) = 449332735606084960351204406909610297301574728466820933515942864925459265983556193`.
which again matches the decrypter.

![image](https://user-images.githubusercontent.com/91729496/236685698-cb82e16b-1c79-4702-982c-97db5a9b53d9.png)

with these values, we can decrpyt the ciphertext using  `c**d mod n = m`, or in python `pow(c,d,n) = 13016382529449106065927291425342535437996222135352905256639555654677400177227645`

![image](https://user-images.githubusercontent.com/91729496/236685863-489bbd5f-d76c-495c-9886-2c03e8282474.png)

After getting the message in numbers, i was unable to decode it into text. Hence... falling back to the online decrypter, we get the message converted to text <<TODO: find out what encoding this is??>>

![image](https://user-images.githubusercontent.com/91729496/236689511-1fb714ea-e7a0-4c90-973e-1af22ca89bef.png)

