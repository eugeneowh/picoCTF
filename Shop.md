Title: Shop

Points: 50 points

Source: picoCTF2021 Reverse Engineering

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/a68dd85e-78f8-4d55-a189-09ac86a39bff)

Connecting to the server gaves us a "market", where we can buy and sell stuff. The item of interest would probably be the "fruitful flag". We were given 40 coins at the start, but the flag cost 100 coins.
 
![image](https://github.com/eugeneowh/picoCTF/assets/91729496/860b24ee-095a-4b3b-9de2-bb80409e7e41)

Trying to sell something that we do not have result in it being blocked. lets look at the source code to figure out what is going on. We were given an executable file as the source code. we can use ida free to open it `https://hex-rays.com/ida-free/#download`

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/bc8236d6-b052-488c-ad20-b796d7443b23)

After fumbling around with the source code for awhile, i decided to keep it simple and try to buy something. -ve number of something. In this case, i bought -10 of average apple. and it "refunded" coin to me!

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/027db57b-10e6-481b-8482-751ac612ef0a)

With those coin, i purchased the fruitful flag, which gave me a bunch of numbers as a list

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/cf24280a-e4ae-4994-a52e-fba76edfd7c4)

Lets try converting those number into letters using cyberchef `www.cyberchef.org`, giving us the flag!

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/a538d782-4012-43b3-a0f8-90ca07e21472)
