Title: New Caesar

Points: 60 points

Source: picoCTF2021 Cryptography

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/3da994b5-35f1-4aa6-9b81-371540c2ea0d)

They have a long string as the encrypted text, and a python file for the encryption.

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/9364f92a-a55b-47e2-a0fc-9e47e128fa75)

Lets break the python file into small chunks to understand it. First, looking at the main code, it takes a flag, and a key, and assert that the key is within `ALPHABET`, as well as the key is of length 1.
Then, it calls the `b16_encode` function, and then calls the `shift` function on the output of `b16_encode`. Looking carefully at the line
```
for i, c in enumerate(b16):
	enc += shift(c, key[i % len(key)])
```

It seems like it shifts the code by an additional space each letter. However, as we recall above, the length of the key is 1. hence `i % 1` always returns 0. so the `i` that was called during enumerate is redundant.
Anyway, the key is of length 1. it will always be shifted by the same number (more explaination on that when explaining the function `shift`). So, as typical of a decoding function, lets look at it reversed from the encoding function: look at the shifting function first (as it was called last)

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/c7380c1a-cf6e-46c3-ae21-a9d7200bb15d)

This `shift` function is called per each letter of the b16_encoded output. It takes in `c`, a character of the b16_encoded output, and shift it by k places (the key).
For example: if the key is 'b', and the input is 'c', the result given would be 'd', as it shifted 'c' by 2 places (including itself).

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/e569cebe-7834-4c12-a17d-55ad857c2075)

We then create our own function to "unshift" the output. One problem is that we do not know the key.
We can just brute force it, since it is in a space of 16 characters only (length of `ALPHABET`.
we know through the line `assert all([k in ALPHABET for k in key])` that it has to be within the set of characters inside `ALPHABET`, which is defined as `ALPHABET = string.ascii_lowercase[:16]`, which is the first 16 characters of the english alphabet in lowercase.

```
unshifted = [""]*16

def unshift(c):
    for unkey in range(16):
	    new = ord(c)- LOWERCASE_OFFSET - unkey
	    unshifted[unkey] += (ALPHABET[new])
    return unshifted
```

Now we have "unshifted" the output, we can reverse the 16 results we got from the `b16_encode` function. Lets take a deeper look at the `b16_encode` function.
It converts the plaintext into number through the `ord` function, which turns 'a' into 97, 'b' into 98, etc.
It then converts the number into 8 bit binary, through the line `binary = "{0:08b}".format(ord(c))`.
next, it breaks the binary into 2 4 bits part, with the most significant 4 bits as the first char in the encoded output, and the least significant 4 bit as the second char (that is how it breaks the space of 26 alphabets into 16).

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/eab4b0e4-2d48-425c-9d26-19d9f186de4b)

To reverse this, we have to put 2 characters back together first. so we run through the cyphertext we shifted, and find the index of the characters in clusters of 2.
An example: shifted cypher = "abcd". index of 'a' in `ALPHABET` is 0, and 'b' in `ALPHABET` is indexed 1. so a and b would be 0 and 1 respectively.
Next, we convert those numbers into 4 bit binary. Taking the example above, 'a' and 'b' gives 0 and 1, so a give us 0000, and b would give us 0001.
We then put this 2 numbers together, with the first alphabet in front. With above example, we would get 0000 0001, which is (boringly) 1.
Finally, we convert that number back into characters, using `chr`. So `chr(1)` gave us (a terrible example) of \x01.

to run through the above with a different example, we take 2 characters: 'hg'.
```
h -> index 7 -> binary 0111
g -> index 6 -> binary 0110
put h and g together -> binary 0111 0110 -> decimal 118 -> chr(118) = v
Do this for the whole cyphertext
```

```
def b16_decode(cypher):
	plain = ""
	for c in range(0,len(cypher),2):
	    ch1 = ALPHABET.index(cypher[c])
	    ch2 = ALPHABET.index(cypher[c+1])
	    ch1 = "{0:04b}".format(ch1)
	    ch2 = "{0:04b}".format(ch2)
	    unenc = int(ch1 + ch2,2)
	    plain += chr(unenc)
	return plain
```

The full code looks like this:
```
import string

LOWERCASE_OFFSET = ord("a")
ALPHABET = string.ascii_lowercase[:16]

enc_flag = 'mlnklfnknljflfmhjimkmhjhmljhjomhmmjkjpmmjmjkjpjojgjmjpjojojnjojmmkmlmijimhjmmj'

def b16_decode(cypher):
	plain = ""
	for c in range(0,len(cypher),2):
	    ch1 = ALPHABET.index(cypher[c])
	    ch2 = ALPHABET.index(cypher[c+1])
	    ch1 = "{0:04b}".format(ch1)
	    ch2 = "{0:04b}".format(ch2)
	    unenc = int(ch1 + ch2,2)
	    plain += chr(unenc)
	return plain



def unshift(c):
    for unkey in range(16):
	    new = ord(c)- LOWERCASE_OFFSET - unkey
	    unshifted[unkey] += (ALPHABET[new])
    return unshifted

unshifted = [""]*16
decoded = []

for c in enc_flag:
    unshift(c)

for i in unshifted:
    b16 = b16_decode(i)
    print(num, b16)
    decoded.append(b16)
```

and running this we got... a bunch of very weird output.

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/fef624fc-1cdb-4503-bfec-e77ca0ffc79e)

However looking through this, there is a string that look possible: `et_tu?_a2da1e18af49f649806988786deb2a6c`. It looks like it is in the format of the flag, and "et tu?" is french for "and you?"
So... trying that i input that as the flag, and it actually was the flag!
