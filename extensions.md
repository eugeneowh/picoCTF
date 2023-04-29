Title: extensions

Points: 150 points

Source: picoCTF2019 Forensics

![image](https://user-images.githubusercontent.com/91729496/235289143-3a09cf40-f6d3-4ead-bf25-42a595ae0845.png)

First as always, download the given file. It gives a flag.txt file that cannot be opened. Taking a hint from the title, lets try using the `file` command to see if it is a differnt type of file: `file flag.txt`

![image](https://user-images.githubusercontent.com/91729496/235289197-5717d01c-4499-48e6-b627-c95d592209d3.png)

It revealled that it is a .png file. in that case we can change the extension, then try opening it again, revealling the flag.

![image](https://user-images.githubusercontent.com/91729496/235289256-f87c4322-9d6d-4de4-8b3f-2fbc3a774a95.png)
