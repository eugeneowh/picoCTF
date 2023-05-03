Title: Nice netcat...

Points: 15 points

Source: picoCTF2021 General Skills

![image](https://user-images.githubusercontent.com/91729496/235916082-5f975722-5f8f-45fb-8877-d2263514fa68.png)

lets try connecting to the given address using netcat. It returns a bunch of numbers. possible the flag, encoded with something. lets copy it into cyberchef `www.cyberchef.org` and see if it can make sense of it.

![image](https://user-images.githubusercontent.com/91729496/235916762-18f49882-09b0-4b1e-a681-361734d4c37c.png)

As each line is separated by a newline, we could either remove them manually, or we could use a command to remove all these newlines and before input to cyberchef
`nc mercury.picoctf.net 43239 | tr -d '\n'`.

![image](https://user-images.githubusercontent.com/91729496/235918015-bfa3cb68-bff0-4f0b-a7e6-b84471aa5228.png)

And that gave us the flag! it was a simple decimal to ascii encoding

![image](https://user-images.githubusercontent.com/91729496/235918245-1ff45022-63f3-4ed1-af00-ac7eb23d6c73.png)
