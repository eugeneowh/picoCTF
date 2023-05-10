Title: Wireshark doo dooo do doo...

Points: 50 points

Source: picoCTF2021 Forensics

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/c92846df-c501-449c-86b9-898c396bd39e)

It gives us a pcapng file. Lets open it with Wireshark.

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/bc868025-61fc-4cb2-b367-3f9cc8e2cb04)

We try following the TCP stream first. At stream 5, there is something that looks promising:

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/221c1e7e-5e7e-4b27-82af-df9f37e9d91e)

It has the format of the flag, so lets try putting it through cyberchef `www.cyberchef.org`, using magic

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/3f04331c-c785-4d63-9b11-681db0cbdaae)

It yields nothing. then we try using ROT, sucne it looks like it kept most of the format of the flag. ROT13 returned us the flag!

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/1af3748f-5edf-4306-9dee-6a17c2489927)
