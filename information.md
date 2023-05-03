Title: information

Points: 10 points

Source: picoCTF2021 Forensics

![image](https://user-images.githubusercontent.com/91729496/235913703-02743d7f-b446-4396-bd2d-33c54b97c97d.png)

it gives a picture of a cute cat! but not flag. lets try examining the metadata using exiftool `exiftool cat.jpg`

![image](https://user-images.githubusercontent.com/91729496/235914180-c843cad4-3ec3-46fc-affd-194197727d1c.png)

seemingly nothing important... but lets try putting some random strings into cyberchef `www.cyberchef.org` to be decoded. we first tried decoding the current IPTC Digest, but got nothing.
Then we decoded the License (using magic). it gave is the flag!

![image](https://user-images.githubusercontent.com/91729496/235915638-4e47d302-7007-4263-ab02-1431da0c83be.png)

it was encoded in base64 format
