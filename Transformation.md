Title: Transformation

Points: 20 points

Source: picoCTF2021 Reverse Engineering

![image](https://user-images.githubusercontent.com/91729496/235976696-c9a31b96-17b2-4e09-bd63-874c3fdc9daa.png)

it gives a encoded file, and a line of python code `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`

![image](https://user-images.githubusercontent.com/91729496/235978475-fe3cbb67-cec3-4802-b6dd-034ff1a69cb2.png)

lets try taking the enc file as an input and running this line in python. this resulted in an out of range error

```
python3
flag = open('enc','r').read() //open the enc file and read it, storing the values as flag
''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)]) // running the code given with flag as the input
```

![image](https://user-images.githubusercontent.com/91729496/235978716-fafc9612-565c-4954-aa6f-2e4301c20a23.png)

lets break down what each part of the code does, to get a sense of how to solve this.

still in `python3`:

`print([flag[i] for i in range(len(flag))]) // prints each char in the enc file`

![image](https://user-images.githubusercontent.com/91729496/235979457-3e883d42-e445-484f-b2cf-2c22bbce0279.png)

`print([ord(flag[i]) for i in range(len(flag))]) // prints the unicode for each char in the enc file`
![image](https://user-images.githubusercontent.com/91729496/235979591-6d5fdbde-ea3d-4ecf-99fc-952d20b5a1ea.png)

`print([ord(flag[i]) << 8 for i in range(len(flag))]) //bitwise shift of 8 bits to the left for each char` This is a bitwise operation. take for example the first char, which has a unicode of 28777.
this is 111000001101001 in binary. a shift of 8 bits to the left means that it would add 8 '0's on the right of the bits, resulting in 11100000110100100000000, which is 7366912 in decimal.

![image](https://user-images.githubusercontent.com/91729496/235980117-0ba7ea91-450b-4876-a70e-f7db0ef32974.png)

as this is obviously not a valid char code, it would seem that this was the encoding function used. to decode it, we would apply a right shift of 8 bits `ord(flag[i]) >> 8` instead.
so from 111000001101001, we would get 1110000, which is 112 in dec. the complete code would look like this: `''.join([chr((ord(flag[i]) >> 8) for i in range(0, len(flag), 2)])`

![image](https://user-images.githubusercontent.com/91729496/235982118-1a3154d8-2dfd-40f2-aa01-5d4d33a6e55b.png)

this gives us half of the flag. there is a second portion of the code we have not solved yet ` + ord(flag[i + 1]))`. since that was the encoding function, lets assume that the reverse would return us the decoding function
`''.join([chr((ord(flag[i]) >> 8) - ord(flag[i + 1])) for i in range(0, len(flag), 2)])`

that faced an out of range error. lets break down the code step by step to figure it out...


```
''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])

''.join(                  //ignore first
  [                       //start of list compre
    chr(                  //convert to char
      (ord(flag[i]) << 8) //flag shift left 8 bits, then convert to unicode
      +                   //add unicodes together
      ord(flag[i + 1])    //flag next char convert to unicode
    )                     //everything between convert to char
      for i in range(0, len(flag), 2) //every 2 char in flag
  ]
)
```

Or we can rewrite the above code to make it easier to understand and reverse engineer

```
lst = []
for i in range(0, len(flag), 2):
  first_char = ord(flag[i] << 8)
  second_char = ord(flag[i+1])
  character = chr(first_char + second_Char)
  lst.append(character)
```
  
  to reverse this:
```
  lst = enc
  flag = []
  for i in range(0, len(lst)): //since 2 char has been combined into 1, we need to iterate over every value now
    char_uni = ord(lst[i]) //reverses to get character = chr(first_char + second_Char)
    //to break down back into 1st and 2nd char - first_char was left shifted 8 bits. hence the remaining 8 bits should be 0.
    //however, the number do not reflect that. so, to split the first and the second char, we can assume that the last 8 bits (left most 8 bits) are the 2nd char and anything right of that is the first.
    first_char = char_uni >> 8
    second_char = int(bin(char_uni) && 0b11111111)
    flag.append(first_char)
    flag.append(second_char)
```

to simplify: `''.join([chr(ord(flag[i]) >> 8) + chr(ord(flag[i]) & 0b11111111) for i in range(0,len(flag))])`
which gives us our flag!

![image](https://user-images.githubusercontent.com/91729496/236002987-54d935de-48cb-4f17-8f86-dd6d9657b228.png)
