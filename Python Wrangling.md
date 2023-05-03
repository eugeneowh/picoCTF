Title: Python Wrangling

Points: 10 points

Source: picoCTF2021 General Skills

![image](https://user-images.githubusercontent.com/91729496/235889380-ac91ee03-6cd3-4cb5-a7c8-01dd1e2555b9.png)

it gives a script, a password, and a flag. lets download all of them. The password file gives a string of characters.

![image](https://user-images.githubusercontent.com/91729496/235889726-930f9fa6-fb26-45c2-9620-719bfe4c517f.png)

which running the python file tells you how to use it `python3 ende.py`. `-e` and `-d` seems to mean encode and decode.

![image](https://user-images.githubusercontent.com/91729496/235889858-83833fa0-ff00-41f5-a3da-ac2cd07684b6.png)

Lets run the python with -d and the encoded flag as the file `python3 ende.py -d flag.txt.en`. It ask for the password, which was found previously. entering the passwords returns the flag to us.

![image](https://user-images.githubusercontent.com/91729496/235890439-2c506516-e6fa-47e3-a60e-829a078bad6a.png)
