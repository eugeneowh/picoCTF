Title: Static ain't always noise

Points: 20 points

Source: picoCTF2021 General Skills

![image](https://user-images.githubusercontent.com/91729496/236796635-10788517-d989-4691-927f-78c708afea3f.png)

We get a bash script and a binary file named static. lets try running the bash script. first we need to give it execute permission `chmod +x ltdis.sh` then run it with `./ltdis.sh`

![image](https://user-images.githubusercontent.com/91729496/236797081-c09e00b4-3592-4941-847d-7de889279b92.png)

It tells us to run the programme with the static file `./ltdis.sh static`. Running that gave us 2 output file: `static.ltdis.x86_64.txt` and `static.ltdis.strings.txt`.
looking at the x86 file, it is a bunch of assembly code. lets ignore that for now. then we look at strings, and found the flag there!

![image](https://user-images.githubusercontent.com/91729496/236801224-af880d74-a30e-431a-b06b-424481bdbdb8.png)
