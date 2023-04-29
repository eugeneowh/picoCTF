Title: picobrowser

Points: 200 points

Source: picoCTF2019 Web Exploitation

![image](https://user-images.githubusercontent.com/91729496/235292747-5945468a-2684-4f54-9f42-2350f2fa4593.png)

Going to the website and clicking on the only significant button "flag", it gives this:

![image](https://user-images.githubusercontent.com/91729496/235292778-525368ca-57aa-4769-b9b4-c6c1bc53e39d.png)

it seems like we need to trick the web think that we are launching this site from "picobrowser". We could do that with `curl`. the `-A` flag changes the user-agent,
so we can use `curl -A 'picobrowser' http://jupiter.challenges.picoctf.org:28921/flag`, giving us the flag!

![image](https://user-images.githubusercontent.com/91729496/235301699-ce729a62-fb50-4ed9-a46a-4a0391ca7284.png)
