Title: buffer overflow 0

Points: 100 points

Source: picoCTF2022 Binary Exploitation

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/bb659110-dd28-4f06-9689-44bfc37c11dc)

We were given the source file, as well as the programme to test it out. 

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/f1f3242f-9bc8-4e00-87e6-519f676b4270)

The code tells us that the input has a buffer of 100 Bytes, and there is a segmentation error catch that prints the flag. so, we just have to overflow the input to get the flag.
I was lazy, so i printed 101 "A" using python, and pasted the output into the programme `print("A" * 101)`, and it returned the flag!

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/5ff9bd12-825b-409b-ad98-e4b560a4f5d7)
