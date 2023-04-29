Title: Mr-Worldwide

Points: 200 points

Source: picoCTF2019 Cryptography

![image](https://user-images.githubusercontent.com/91729496/235314558-2df33d21-85ce-4074-8834-7fbd6d9f8aa0.png)

Looking at the message that the challenge gives, it seemed like it was a set of coordinates.

![image](https://user-images.githubusercontent.com/91729496/235314592-d0f9c1f4-d69b-41c7-a6d0-b52aa5166c4a.png)

Searching google for the locations, we got the following places. I tried separating them by country, city, etc.

![image](https://user-images.githubusercontent.com/91729496/235315814-58c434fa-fb92-4e52-b93c-49aa38ac6ed5.png)

taking the first letter/number of the country, city, etc, i got `2FQ2f4_2293Q6, KODFAK_ALANKB, NODHHR_KAM4KF` all which were not correct. the closest one seemed to be the second `KODFAK_ALASKB`.
Replacing F and K in `KODFAK`
```
Nakanocho,                                                            [K]amigyo Ward, Kyoto, 602-0958, Japan
Odesa,                                                                [O]dessa Oblast, Ukraine, 65000
                                                                      [D]ayton, OH 45402, United States
Hoca Paşa, 34110                                                      [F]atih/[İ]stanbul, Türkiye <- use I as in Istanbul instead
Hazza ' Bin Zayed The First St - Al Manhal -                          [A]bu Dhabi - United Arab Emirates
Room 11, Level 2, Bangunan Sulaiman, Jalan Sultan Hishamuddin, 50000  [K]uala Lumpur, Malaysia
```
we got `KODIAK_ALANKB`. Just looking at it, the second word seemed to look like it should be `ALASKA`.

```
Kirkos,                                             [A]ddis Ababa, Ethiopia
Av. Nueva Loja,                                     [L]oja, Ecuador
Martelaarsgracht 5, 1012 TM                         [A]msterdam, Netherlands
4 lighthouse landing, [S]leepy Hollow,              [N]Y 10591, United States <- use S as in Sleepy Hollow instead of New York
                                                    [K]odiak, AK 99615, United States
Faculty Of Engineering, Al Azaritah WA Ash Shatebi, [B]ab Sharqi, [A]lexandria Governorate 5423021, Egypt <- use A as in [A]lexandria instead of Bab Sharqi
```

Hence we can try the flag `KODIAK_ALASKA`
