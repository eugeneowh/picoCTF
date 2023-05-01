Title: PW Crack 5

Points: 100 points

Source: Beginner picoMini2022 General Skills

![image](https://user-images.githubusercontent.com/91729496/235487133-6c239cea-f2fc-4237-8aeb-dbcd7857f1c0.png)

On top of the files given in PW Crack 4, it gave an additional dictionary.txt of possible passwords. probably just need to read the dictionary and do exactly the same steps as previously!
Lets open up the dictionary and `level5.py` to see what is inside.

The dictionary just contains "passwords" from `0000` to `ffff` (too long to screenshot here - total of 16^4 passwords)
The python file is exactly as before.

![image](https://user-images.githubusercontent.com/91729496/235487704-abc690da-3995-4db7-a472-f27cc7d2077b.png)

Lets add the file read from `dictionary.txt` and do exactly what we did for PW Crack 3 and 4

![image](https://user-images.githubusercontent.com/91729496/235488360-8f30cbef-2f98-42b4-ba3f-78916bbb79c2.png)

When running this, we realised that there were no matches for the password, so we printed the password it is checking for. and realised that it contained an additional newline in each line

![image](https://user-images.githubusercontent.com/91729496/235488506-4ceec2e9-2954-46e0-9ce2-ce19cb20518a.png)

We added a `.strip()` after readline()

![image](https://user-images.githubusercontent.com/91729496/235488773-793f60bb-1599-44bd-94bf-3785e844ca63.png)

and got the flag!

![image](https://user-images.githubusercontent.com/91729496/235488862-d666ce82-35d5-40a8-b6dc-72adbed62f2c.png)
