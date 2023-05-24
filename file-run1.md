Title: file-run1

Points: 100 points

Source: picoCTF2022 Reverse Engineering

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/e853ab44-de22-49d3-87bc-b402618b741e)

the challenge asked what happens if we run the file. lets try that. first we change the permission of the downloaded file (named run) to give it execute permission `chmod +x run`, then we run it! `./run`

It immediately gave us our flag!

![image](https://github.com/eugeneowh/picoCTF/assets/91729496/bc910d61-2b87-4e2a-81cb-0a21c565155c)
