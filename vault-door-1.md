Title: vault-door-1

Points: 100 points

Source: picoCTF2019 Reverse Engineering

![image](https://user-images.githubusercontent.com/91729496/235207668-6e21ccb8-a9ba-44ee-b5c1-509bc8c864c3.png)

Let's download the source code

![image](https://user-images.githubusercontent.com/91729496/235207866-50923120-5955-422f-9c5e-42e88fabc50c.png)

It seems like the password is there, just scrambled. I guess we could decypher it manually... but we are all lazy. so lets try writing a script for it.

```
    password = ['_'] * 32 #length of password 32
    password[0]  = 'd'
    password[29] = 'a' 
    password[4]  = 'r' 
    password[2]  = '5' 
    password[23] = 'r' 
    password[3]  = 'c' 
    password[17] = '4' 
    password[1]  = '3' 
    password[7]  = 'b' 
    password[10] = '_' 
    password[5]  = '4' 
    password[9]  = '3' 
    password[11] = 't' 
    password[15] = 'c' 
    password[8]  = 'l' 
    password[12] = 'H' 
    password[20] = 'c' 
    password[14] = '_' 
    password[6]  = 'm' 
    password[24] = '5' 
    password[18] = 'r' 
    password[13] = '3' 
    password[19] = '4' 
    password[21] = 'T' 
    password[16] = 'H' 
    password[27] = '6' 
    password[30] = 'f' 
    password[25] = '_' 
    password[22] = '3' 
    password[28] = 'd' 
    password[26] = 'f' 
    password[31] = '4'
    print(''.join(password))
```

ok. that took way more effort than manually unscrambling it.

![image](https://user-images.githubusercontent.com/91729496/235211593-a8edfc37-a803-4541-89bb-8787acc27885.png)
