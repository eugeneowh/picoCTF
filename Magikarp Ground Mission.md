Title: Magikarp Ground Mission

Points: 30 points

Source: picoCTF2021 General Skills

![image](https://user-images.githubusercontent.com/91729496/236863689-f4312863-88f4-4171-a4e9-31a0cda696d0.png)

Lets launch the instance and connect to it with the given IP address `ssh ctf-player@venus.picoctf.net -p 55785`, with the given password `6d448c9c`.

![image](https://user-images.githubusercontent.com/91729496/236864142-dc81be3a-d416-468b-9f36-f2af68bf9673.png)

and we are in. lets see what files are inside using `ls`, as advised in the challenge.

![image](https://user-images.githubusercontent.com/91729496/236864266-50478ffe-3878-4035-8faf-7a5b8cf946fc.png)

It tells us the first 3rd of the flag, and how to get to the 2nd part. `cat 1of3.flag.txt`, and `cat instructions-to-2of3.txt`

![image](https://user-images.githubusercontent.com/91729496/236864395-c84c46a1-23a8-411c-b233-6387f58d6b0f.png)

![image](https://user-images.githubusercontent.com/91729496/236864628-ad400b15-0693-4721-bc34-68a35bb57dbd.png)

To go to the root, we can use `cd /` to get to the root folder.

![image](https://user-images.githubusercontent.com/91729496/236865879-f7b2735f-5ee9-4d0c-8bd4-13b861ceae4a.png)

we got the second part of the flag, and the instruction to the 3rd `cat 2of3.flag.txt`, and `cat instructions-to-3of3.txt`

![image](https://user-images.githubusercontent.com/91729496/236865206-4e5a423b-55f0-4194-9f9b-4c8bf59d3cf5.png)

![image](https://user-images.githubusercontent.com/91729496/236865433-4d19f6cc-239e-48b3-90a1-0df9fcfd7bb4.png)

To get to home, we use `cd ~` and we got the 3rd part! `cat 3of3.flag.txt`

![image](https://user-images.githubusercontent.com/91729496/236866217-839b996a-0c55-487d-a9dc-2ebe2567fd52.png)

![image](https://user-images.githubusercontent.com/91729496/236865656-eb64fab4-93f8-414c-b37a-fb1614a895c8.png)

piece the 3 parts together to form the complete flag!
