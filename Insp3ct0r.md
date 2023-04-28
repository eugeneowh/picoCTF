Title: Insp3ct0r

Points: 50 points

Source: picoCTF2019 Web Exploitation

![image](https://user-images.githubusercontent.com/91729496/235191346-ec754394-df66-48e9-b2c7-85fc551429e2.png)

going to the website given, we see the following:
![image](https://user-images.githubusercontent.com/91729496/235191491-c3c069e1-2046-421c-9cc6-e4d8e5c69ee3.png)

With the clue to inspect me written right at the top, as well as in the title of the challenge, lets inspect the website (right click -> inspect)
![image](https://user-images.githubusercontent.com/91729496/235191827-25831def-ddf7-455a-8a38-246c38fca901.png)

That gave us 1/3 of the flag! it seemed to give a hint as to where to find the next part: `html is neat.`

Looking at the "How" part of the website, it says that it used HTML, CSS, and JS to make this site:
![image](https://user-images.githubusercontent.com/91729496/235192399-9c7e4942-925f-4884-b2c3-bc1a2e6a1f58.png)

Since HTML was one of them, let's look at the CSS and JS files from source (right click -> inspect -> source)

indeed part 2 of the flag can be found in mycss.css:
![image](https://user-images.githubusercontent.com/91729496/235192801-6a3588b4-ba84-4218-a936-9b25140cbc0c.png)

and part 3 in myjs.js:
![image](https://user-images.githubusercontent.com/91729496/235193001-14251855-d96a-462f-9d04-db42ba225755.png)

piecing all 3 parts together gives the complete flag.
