Title: Mind your Ps and Qs

Points: 30 points

Source: picoCTF2021 Reverse Engineering

![image](https://user-images.githubusercontent.com/91729496/236819924-82c0acf9-ea9d-45d4-9719-70cdb09f4440.png)

It gives us a python file, that runs a "trial" programme.

![image](https://user-images.githubusercontent.com/91729496/236820221-67fc8b91-9e33-453d-968c-3c82a1b2a8fa.png)

Looking at the code, it seems that getting the "license" is the key to this programme. The license consist of 3 parts: 2 static, 1 dynamic.

![image](https://user-images.githubusercontent.com/91729496/236820366-064aa0b9-bac0-448c-9b5a-72e207d0b601.png)

Looking at it, the first part of check_key function tells us that the static portion of the code is... static. we just have to copy it.

![image](https://user-images.githubusercontent.com/91729496/236820474-0dca1162-04d5-4f80-9ad8-7ab179c5076f.png)

decoding the dynamic portion of the code should give us the flag. the check for the dynamic part requires us to encode the username with the hashlib lib, with sha256 encoding.
as the trial username is `PRITCHARD`, we can open a python file and encode it.

![image](https://user-images.githubusercontent.com/91729496/236821016-c5acd543-0a41-4910-93aa-c8ba4dc0d02a.png)

To decode this, it is stated in the source code certain positions of the encoded binary to be used:

![image](https://user-images.githubusercontent.com/91729496/236821242-56e7af0d-dc5a-46a3-8b35-12b6f4f4ed3f.png)

it states the position to be used as 4,5,3,6,2,7,1,8. Lets find what what character those are:

![image](https://user-images.githubusercontent.com/91729496/236821437-23493706-ff1c-4eb3-9451-867ebcca484b.png)

Entering all these gives us the flag:

![image](https://user-images.githubusercontent.com/91729496/236821639-423be19c-4c7f-4480-8cbf-19314a9186fb.png)

it also unlocks the full version of the programme, which we can play around with for a bit if you want?
