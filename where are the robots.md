Title: where are the robots

Points: 100 points

Source: picoCTF2019 Web Exploitation

![image](https://user-images.githubusercontent.com/91729496/235206574-66d770e7-5a75-455c-923d-6ecf740ab928.png)

Let's go to the website first:

![image](https://user-images.githubusercontent.com/91729496/235206631-6d67d9e2-6df7-41dc-b3f7-749bde833a3e.png)

As with the title of this challenge, it ask where are the robots. robots.txt files , as quoted from google: `A robots.txt file tells search engine crawlers which URLs the crawler can access on your site. This is used mainly to avoid overloading your site with requests; it is not a mechanism for keeping a web page out of Google. To keep a web page out of Google, block indexing with noindex or password-protect the page.`
simply, to find the robots.txt, just append it to the end of any website that you are visiting `https://jupiter.challenges.picoctf.org/problem/56830/robots.txt`

![image](https://user-images.githubusercontent.com/91729496/235206994-96f8a45b-9397-413f-8b4d-c38561c6fcbd.png)

Since it gave us an html extension, lets try it `https://jupiter.challenges.picoctf.org/problem/56830/1bb4c.html`

![image](https://user-images.githubusercontent.com/91729496/235207201-06fd3c78-0f7f-4f01-a679-2785ada59d58.png)

Found it!
