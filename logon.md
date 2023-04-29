Title: logon

Points: 100 points

Source: picoCTF2019 Cryptography

![image](https://user-images.githubusercontent.com/91729496/235284557-4f85b9e8-59f4-406c-9ad7-90e085747e26.png)

first lets go to the link given:

![image](https://user-images.githubusercontent.com/91729496/235284593-baeb418a-4519-45ed-8fcc-d7f9e177248a.png)

inspecting the source did not give much information, less a comment, which may be helpful?

![image](https://user-images.githubusercontent.com/91729496/235284644-46d12a0e-da17-4230-97d5-2899781cf7be.png)

We can try to log in with a random username and password and see what the network returns.

![image](https://user-images.githubusercontent.com/91729496/235284679-ad0ce74c-d126-4a76-ad16-c083e9400f64.png)

Looking at the cookie that is returned when inspecting the network, we see an admin=False field.

![image](https://user-images.githubusercontent.com/91729496/235284960-8caad1d8-63a2-4e5a-8157-893e32da2d91.png)

Could we use burpsuite to simply change admin=True? Lets try. First, we turn on intercept and navigate to the initial link

![image](https://user-images.githubusercontent.com/91729496/235285143-3ded6891-0814-43ab-ba88-48692949ab6f.png)

it sends out a few request to the server. On the third packet it sends a GET request to /flag, and we can see that there is a field named: `admin=False`. changing that to `admin=True`

![image](https://user-images.githubusercontent.com/91729496/235285258-d1c6d385-563d-4c66-98f5-41986d4a62c3.png)

And the subsequent GET packet to /problem/44573/flag has the same field, lets change that too.

![image](https://user-images.githubusercontent.com/91729496/235285312-d4c2bea5-87b6-47e8-a052-f53022d3a682.png)

yields us the flag :D


... afternote... reading the question again, we are supposed to login as Joe. let us try to see if we could get anything if we input the username as Joe.

![image](https://user-images.githubusercontent.com/91729496/235285590-f9b3f89f-3650-4b1d-bd03-950902c9625c.png)

got lazy and decided to leave it as such. will see if there are any other methods if i have time.
