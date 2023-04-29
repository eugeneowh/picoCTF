Title: What Lies Within

Points: 150 points

Source: picoCTF2019 Forensics

![image](https://user-images.githubusercontent.com/91729496/235289525-d221cb19-6b1b-4acf-9e67-a59d945fadc8.png)

As always, download the file given. it give a nice looking building in a png file.

![image](https://user-images.githubusercontent.com/91729496/235289553-a48e0e4b-0c29-457a-981d-fa3744f0f20b.png)

going through `file` and `exiftool` did not show anything interesting. `binwalk` however, showed that there is a zip file hidden inside. lets extract the zip file with binwalk as well `binwalk -e buildings.png`

![image](https://user-images.githubusercontent.com/91729496/235289641-2849dcf7-976e-41df-9c3e-f51a81cc2ffc.png)

let unzip the extracted zip file with zlib. if you need help to install it, please refer to this `https://unix.stackexchange.com/questions/22834/how-to-uncompress-zlib-data-in-unix`. we used the command `zlib-flate -uncompress < 29.zlib > output`

![image](https://user-images.githubusercontent.com/91729496/235290095-92ea7bef-eecf-487a-9e45-cc76f91ecde2.png)

Next we find out what file type the output is, using `file`

![image](https://user-images.githubusercontent.com/91729496/235290124-02e0f273-2ae2-42a2-9118-76f0738a87d6.png)

Maybe we could trying using `strings` and `grep` to see if the flag is hidden inside. It revealled nothing `strings output | grep "picoCTF"`. Seems like we need to try something else. looking at the hint tells us that there are encoded data, and the decoder can be found online. after some searching, we try using zsteg, which gives us the flag. `zsteg buildings.png`

![image](https://user-images.githubusercontent.com/91729496/235291711-e004c7a8-cb60-4486-85c1-28cb9558fc1a.png)
