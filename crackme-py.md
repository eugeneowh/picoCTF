Title: crackme-py

Points: 30 points

Source: picoCTF2021 Reverse Engineering

![image](https://user-images.githubusercontent.com/91729496/236834663-3d15acb2-41d5-466b-90de-f173f9098f06.png)

running the file given asks for 2 numbers, then returns the one with the biggest positive magnitude

![image](https://user-images.githubusercontent.com/91729496/236846623-86bd9c6b-a5ee-4f8d-b2ad-3eb556d4cbd6.png)

Lets check the source code. On top of the number thingy above, it has another function looks like it is an encoded stuff!

![image](https://user-images.githubusercontent.com/91729496/236847322-48199099-33ed-4cdb-94b7-727db19eb769.png)

Lets try adding the decode secret function into the code, with the secret that is stated at the top of the file

![image](https://user-images.githubusercontent.com/91729496/236847744-3f45782a-7cef-4816-824e-eef7459a5905.png)

Yep running that gave us the flag!

![image](https://user-images.githubusercontent.com/91729496/236847909-ef1310e7-2475-44b6-a26d-bbf37ddd0f3f.png)
