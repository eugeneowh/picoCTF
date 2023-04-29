Title: So Meta

Points: 150 points

Source: picoCTF2019 Forensics

![image](https://user-images.githubusercontent.com/91729496/235287430-ae48df20-bb45-4109-9946-b36c46de21f9.png)

First, lets download the picture.

![image](https://user-images.githubusercontent.com/91729496/235287453-f9581cbc-8140-4c7b-97f2-734472c5fd9a.png)

It gives a .png image. Take the title as a clue, lets try inspecting the metadata from the file using exiftool `exiftool pico_img.png`

![image](https://user-images.githubusercontent.com/91729496/235287504-a2a717f9-77ce-4e2c-8825-6e9cb3cadadb.png)

We can see the flag in the Artist field!
