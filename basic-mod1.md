Title: basic-mod1

Points: 100 points

Source: picoCTF2022 Cryptography

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/e6b47087-193b-4527-ad83-1921b4e75fcc)

it gives an the instruction to decrypt this message in clear. so, lets just follow the instruction in a python script to make it easier for us.

```
import string

msg = '350 63 353 198 114 369 346 184 202 322 94 235 114 110 185 188 225 212 366 374 261 213' #input the message that was given as a string

mapping = list(string.ascii_uppercase) + list(range(0,10)) + ['_']
# list(string.ascii_uppercase) gives the list of alphabet in uppercase from A to Z as a list
# list(range(0,10)) gives the numbers 0 to 9 as a list
# ["_"] adds _ as the 36th character of the list "mapping"
# mapping will look like this: ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z', 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, '_']

msg = msg.split() #to split each number into its own entry in the list
msg = [int(i)%37 for i in msg] #mod 37 for all entries in the list
msg = ''.join([str(mapping[i]) for i in msg]) #maps the numbers to the index in mapping (so 0 becomes A, 35 becomes 9, etc.) and join them together as a string.

#this outputs the flag.
print (msg)
```

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/4cef2367-05dc-45f6-b035-d911d411305e)
