Title: Client-side-again

Points: 200 points

Source: picoCTF2019 Web Exploitation

![image](https://user-images.githubusercontent.com/91729496/235333189-3b750e05-ab24-4b55-9de4-759a86279f72.png)

Going to the site, it looks like we need to key in a password again? Inspecting it gives what looks like a password comparision, scrambled up again

![image](https://user-images.githubusercontent.com/91729496/235333846-431c2fc6-9e0e-40d8-90c6-2445a1761d25.png)

So we copied it and tried to make it look more presentable.

![image](https://user-images.githubusercontent.com/91729496/235334149-8fb9c525-3650-4e42-b212-b850769dff38.png)

Still messy. lets take a look at the bunch of code in a piecewise manner: First, this function

![image](https://user-images.githubusercontent.com/91729496/235338248-f6c5b0e4-1042-48a3-addd-73b90cf95d82.png)

it basically takes the var `_0x5a46`, and cycles the 0th element to the last element 436 times. after cycling it, we have 
`_0x5a46 = ['getElementByID', 'value', 'substring', 'picoCTF{', 'not_this', 'f49bf}', '_again_e', 'this', 'Password Verified', 'Incorrect password']`.
The next function also basically tells us that when `_0x4b5b` is called with an int argument, it would take on the value of `_0x5a46` at index of the argument.

![image](https://user-images.githubusercontent.com/91729496/235338439-d8043570-162f-4a34-b858-61804a906d0c.png)

The last function is the one we are interested in. First half is gets the password from a document, to be used later for comparing, and defining the size of the term "split" as 4.

![image](https://user-images.githubusercontent.com/91729496/235338480-39b1a1b9-6c00-4722-a858-e7e95db13642.png)

very lastly, each checkpass "if" tells us the value of the password at certain positions, as indicated in the comments below. Finally we find our flag!

![image](https://user-images.githubusercontent.com/91729496/235338555-8a0544f0-0d61-42ea-a6a0-f3c9b5daeaab.png)
