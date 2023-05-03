Title: Serpentine

Points: 100 points

Source: Beginner picoMini2022 General Skills

![image](https://user-images.githubusercontent.com/91729496/235884265-60521bfe-b7d2-4dd1-8eb5-c99fa9ccdc4c.png)

Running the file given gave us 3 options, and selecting print flag tells us that the flag is misplaced. lets check the source code for it

![image](https://user-images.githubusercontent.com/91729496/235884469-ec2e4475-5f42-4745-aed2-433e90741bd8.png)

Looking at the source code, there is a print flag function, but it was never called.

![image](https://user-images.githubusercontent.com/91729496/235885406-9bb972a9-829d-4477-adc0-d93fd2776dfd.png)

Lets replace the print, and call the `print_flag` function instead

![image](https://user-images.githubusercontent.com/91729496/235885608-9e49204c-d61f-4650-973a-35e44ec35033.png)

running it now gives the flag!

![image](https://user-images.githubusercontent.com/91729496/235885906-d657e3ed-78e8-4af2-b15e-3c70e2dd660a.png)
