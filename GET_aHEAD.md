Title: get aHEAD
Points: 20 points
Source: picoCTF2021 Web Exploitation

![image](https://user-images.githubusercontent.com/91729496/235187725-ae591b7d-c692-46f1-b897-d3811cefa040.png)

Going to http://mercury.picoctf.net:21939/, it showed this:
![image](https://user-images.githubusercontent.com/91729496/235187650-1328a73b-9776-488f-8496-38f78d0cb932.png)

As the name suggest looking at the headers, so using CURL:

`curl --head http://mercury.picoctf.net:21939/` returned the flag

![image](https://user-images.githubusercontent.com/91729496/235188514-28321be6-78d0-4b5a-9a0e-b79478d6c676.png)
