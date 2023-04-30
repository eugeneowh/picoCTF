Title: PW Crack 2

Points: 100 points

Source: Beginner picoMini2022 General Skills

![image](https://user-images.githubusercontent.com/91729496/235368742-a94bdade-a1fa-4d72-8fb8-50d09c3e2735.png)

Similar to PW Crack 1, it gives a password checker and an encrpyted flag.

![image](https://user-images.githubusercontent.com/91729496/235368794-78d9847a-9663-4e52-b346-c43d6db0fd97.png)

Again similar to PW Crack 1, the password is given inside. Only difference is that it is encrypted as hex values! reference an ascii table, we can easily recover the password.
However, i got lazy this time and decide to just dump it into cyberchef `www.cyberchef.org` and use the from hex recipe for the answer.

![image](https://user-images.githubusercontent.com/91729496/235368925-707e80f3-6aa0-4b4b-a5d8-74575bf0a1f3.png)

running the file `python3 level2.py` and giving the password `39ce` returns the flag!

![image](https://user-images.githubusercontent.com/91729496/235368969-50e69eeb-4dbe-4fde-aeef-05d483fe1449.png)
