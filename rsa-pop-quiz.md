Title: rsa-pop-quiz

Points: 200 points

Source: picoCTF2019 Cryptography

![image](https://user-images.githubusercontent.com/91729496/235319412-cd488003-86f3-4e16-802b-5cf3efac1228.png)

This is a painfully long quiz. I'll try to explain everything, but do have cyberchef `www.cyberchef.org` and online RSA cypher ready `https://www.dcode.fr/rsa-cipher#q2`, `https://www.dcode.fr/euler-totient`
(and a calculator). Thankfully the quiz does not change every try.

Question 1

![image](https://user-images.githubusercontent.com/91729496/235319509-fc26fd02-7249-4e95-aa9b-f2b404c4c49d.png)

yes it it feasible.
`n = p*q`. simple. just have to check that q and p are prime numbers (which they are), so n is easily calculated `n=4636878989`

Question 2

![image](https://user-images.githubusercontent.com/91729496/235319584-a1ab7575-e77a-4955-8a7f-edf636f7c485.png)

yes it is feasulble too.
`q = n/p`. same, we just have to check that p and q are both prime numbers (which they are again), so q is easily too `q = 93089`

Question 3

![image](https://user-images.githubusercontent.com/91729496/235319654-ea778d95-510b-4010-98ec-df3780d90651.png)

No. Given only e and n (which are the public keys in an RSA encryption), which should tell you that it is not feasible to find p and q from it. p and q are deliberately large and prime to ensure that n could not easily be broken back into p and q.

Question 4

![image](https://user-images.githubusercontent.com/91729496/235319777-45f5f265-fee9-40dd-ba92-0dc7a5071649.png)

Yes. totient is the number of numbers from 1 up till n that is prime relative to n (has no common factor except 1). it can be calculated by running all numbers from 1 to n-1 using gcd(i, n) and counting the total number.

![image](https://user-images.githubusercontent.com/91729496/235319851-a5dfb6f7-d5ca-4a81-a337-31e5f540873a.png)

or we can just an online solver. First we calculate `n=p*q=66347*12611=836702017`, then putting it on `https://www.dcode.fr/euler-totient`

![image](https://user-images.githubusercontent.com/91729496/235320022-9a2a6810-bc26-4e01-a84c-e376750480bf.png)

Question 5

![image](https://user-images.githubusercontent.com/91729496/235320039-504399c6-9bd8-4fd7-83c0-6403029df64f.png)

Yes. ciphertext can be calculated by `m^e mod n`, where m is the plain text, e and n are the public key, which are given. putting it through python `pow(m,e,n)` gives you `256931246631782714357241556582441991993437399854161372646318659020994329843524306570818293602492485385337029697819837182169818816821461486018802894936801257629375428544752970630870631166355711254848465862207765051226282541748174535990314552471546936536330397892907207943448897073772015986097770443616540466471245438117157152783246654401668267323136450122287983612851171545784168132230208726238881861407976917850248110805724300421712827401063963117423718797887144760360749619552577176382615108244813`

Question 6

![image](https://user-images.githubusercontent.com/91729496/235320240-3c130077-375a-405a-9ca3-e8e52e2b3cb3.png)

No. again, given that e and n are both public keys, it is infeasible to decypher the ciphertext using that (else RSA would have long been abandoned)

Question 7

![image](https://user-images.githubusercontent.com/91729496/235320293-422e9d38-1666-4d27-bb55-275afbd97020.png)

Yes. `d = e^-1 mod phi`, where `phi=(p-1)*(q-1)`. given p,q, and e, we can calculate phi, then use it to calculate.

Question 8

![image](https://user-images.githubusercontent.com/91729496/235320363-a915ba53-1c00-477e-b284-693200e9e7d8.png)

Yes. To get the plaintext, m: `m = c^d mod n`. given n and p, we can calculate `q=n/p`. with p and q, we can calculate `phi`, which can be used to calculate `d = e^-1 mod phi`
since c and n are both given, calculating m is then trivial. `m = 14311663942709674867122208214901970650496788151239520971623411712977120586163535880168563325`

Finally. using the plaintext calculated, we have to convert it to a hex number, then ascii, and we would get our flag!!!
At this point i got lazy, so i just went online and searched for a converter `https://www.rapidtables.com/convert/number/decimal-to-hex.html`

![image](https://user-images.githubusercontent.com/91729496/235320541-34b24193-c467-48e3-9d5d-22c2a1343446.png)

then `https://www.rapidtables.com/convert/number/hex-to-ascii.html`

![image](https://user-images.githubusercontent.com/91729496/235320583-db61f375-5480-41d3-872e-4787d1119378.png)
