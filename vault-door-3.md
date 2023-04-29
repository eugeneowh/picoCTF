Title: vault-door-3

Points: 200 points

Source: picoCTF2019 Reverse Engineering

![image](https://user-images.githubusercontent.com/91729496/235316712-a9ce2f61-bd5e-47c1-96a2-59547bac813a.png)

Looking at the course code given, it looks like a scrambling of password again.

![image](https://user-images.githubusercontent.com/91729496/235316743-25ea1566-a694-46a1-b7eb-537ab89e32aa.png)

Again learning from past experience, lets just decode this manually... It has the scrambled password of `jU5t_a_sna_3lpm12g94c_u_4_m7ra41`

```
for (i=0; i<8; i++) {
  buffer[i] = password.charAt(i);
}
```
This code suggest that the first 8 characters are in place. lets keep it in mind: `jU5t_a_s`

```
for (; i<16; i++) {
  buffer[i] = password.charAt(23-i);
}
```
as i has already been initialised previously and iterated to `i=8` from above, the next 8 chars would be determined by `23-i`th position of the password given.
looking at the password `jU5t_a_sna_3lpm12g94c_u_4_m7ra41`, the 23-8 =15th character is `m`. so the next 8 char would be `1mpl3_an`, forming `jU5t_a_s1mpl3_an`

```
for (; i<32; i+=2) {
  buffer[i] = password.charAt(46-i);S
}
```
for the next 16 characters, skipping 1 char each (every alternate char), it is determined by the password at position `46-i`. looking back at the original password,
`46-i(16)=30`th char is `4`. Taking every alt char for 8 char gives us `4-r-m-4-u-c-9-2`, giving us `jU5t_a_s1mpl3_an4-r-m-4-u-c-9-2`.
```
for (i=31; i>=17; i-=2) {
  buffer[i] = password.charAt(i);
}
```
the last 8 char that is in between is simply the password at index 31,29, ..., 17, giving us `g-4-_-_-_-7-a-1`, forming `jU5t_a_s1mpl3_an4gr4m_4_u_c79a21`

and that is the flag!
