Title: basic-mod2

Points: 100 points

Source: picoCTF2022 Cryptography

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/fc699c78-658f-42be-9a98-06cee2551fb2)

As per basic-mod1, it gives us instructions as to how to decrypt it. Lets follow the instructions and write a programme for it.

```
import string

msg = '104 372 110 436 262 173 354 393 351 297 241 86 262 359 256 441 124 154 165 165 219 288 42'

mapping = [' '] + list(string.ascii_uppercase) + list(range(0,10)) + ['_']
# [' '] adds an empty space in index 0, as it stated that the alphabet starts at 1
# list(string.ascii_uppercase) gives the list of alphabet in uppercase from A to Z as a list
# list(range(0,10)) gives the numbers 0 to 9 as a list
# ["_"] adds _ as the 36th character of the list "mapping"
# mapping will look like this: [' ', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z', 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, '_']
     
msg = msg.split() #to split each number into its own entry in the list
msg = [pow(int(i), -1, 41) for i in msg] #find the inverse mod of all entry in list (a^-1 mod b)
print(msg)
msg = ''.join([str(mapping[i]) for i in msg]) #maps the numbers to the index in mapping (so 1 becomes A, 36 becomes 9, etc.) and join them together as a string.

print (msg)
```

and that gives us our flag!

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/ad6aa77b-152e-4cd0-8697-31d9a3b45e8d)
