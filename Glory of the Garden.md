Title: Glory of the Garden

Points: 50 points

Source: picoCTF2019 Forensics

![image](https://user-images.githubusercontent.com/91729496/235194761-1f2d1692-33ec-4d75-9b56-52d0d0c1c7bf.png)

Lets download the file and see what it is. Opening it gives a `garden.jpg` file.
![image](https://user-images.githubusercontent.com/91729496/235195072-021a0b50-7fed-4ba1-bb0f-4c47fab44645.png)

Lets try exiftool to see if there are any clues in the metadata. `exiftool garden.jpg`
![image](https://user-images.githubusercontent.com/91729496/235195613-b4a92810-bf09-47d7-9f1f-1dcab48d4833.png)

Nothing important was found. maybe try binwalk? `binwalk garden.jpg`
![image](https://user-images.githubusercontent.com/91729496/235196423-a8616f10-c900-4769-a861-4b7adb7849b6.png)

Still nothing. Maybe hexdump then? `hexdump -C garden.jpg`
![image](https://user-images.githubusercontent.com/91729496/235196902-eef77dd9-76dc-483e-ba77-e3d4c8db4be4.png)

Thankfully it revealed the flag in the last new lines!
