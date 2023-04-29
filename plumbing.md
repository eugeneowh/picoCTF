Title: plumbing

Points: 200 points

Source: picoCTF2019 General Skills

![image](https://user-images.githubusercontent.com/91729496/235316318-2c76a354-0f6a-4b2a-bbab-c9e57c0ce298.png)

Using nc to connect to the given address, it give a bunch of lines of text

![image](https://user-images.githubusercontent.com/91729496/235316377-44b93265-95ca-4b2c-84a4-fd5d36cd5eaf.png)

lets try putting all those through grep to see if we can find our flag `nc jupiter.challenges.picoctf.org 4427 | grep "picoCTF"`

yep! got the flag.

![image](https://user-images.githubusercontent.com/91729496/235316460-f77f3078-61c0-4060-a527-5c3197e570a1.png)
