Title: Wave a flag

Points: 10 points

Source: picoCTF2021 General Skills

![image](https://user-images.githubusercontent.com/91729496/235912669-cbecf40b-1db1-48cd-8bc9-8b0981bfe46c.png)

downloading the file `warm`, we check what file type it is using file `file warm`. it states that it is an 64 bit executable. lets try executing it then.
First, we change its permission to grant it executable right `chmod +x warm`, then try running it `./warm`(also not wise in from a security perspective....)

![image](https://user-images.githubusercontent.com/91729496/235913229-f4d37ef4-8926-4370-93b0-20953904e732.png)

It tells us to pass an argument `-h` into its execution. lets try that. `./warm -h`

![image](https://user-images.githubusercontent.com/91729496/235913509-07d0894a-e893-4265-8f46-7f2030e3c2a4.png)

it tells us the flag!
