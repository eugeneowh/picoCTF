Title: Tab, Tab, Attack

Points: 20 points

Source: picoCTF2021 General Skills

![image](https://user-images.githubusercontent.com/91729496/236811202-96b61188-4c97-4cdc-9dbe-1681b8d20a70.png)

It gives us a zip file. Unzipping it gives us a folder, which nest a whole bunch of folders, and finally, a binary file. To open it, we can just go ahead with the title's suggested approach: using tab to autofill the name of the folders.
`unzip Add... <<tab>>` then `cd Add <<tab>> <<tab>> ... <<tab>>` until you reach the last folder. Alternatively (if using a gui based system), we can just click on the folders and drag the last file into the terminal to get the file location.

![image](https://user-images.githubusercontent.com/91729496/236816781-77d6269f-3180-4652-b3c3-0ae663a70863.png)

OR

![image](https://user-images.githubusercontent.com/91729496/236816895-c9c5ba84-f7e1-41a8-b4de-c805a5f69f7e.png)

and just run the file, to get the flag

![image](https://user-images.githubusercontent.com/91729496/236817106-a195ada9-9784-4c91-9424-96784a727bf7.png)
