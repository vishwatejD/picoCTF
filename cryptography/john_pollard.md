# John_pollard
## Goal 
Sometimes RSA certificates are breakable
>given a rsa certificate named as cert


### Write up

if we open the certificate we find this.
![image](https://github.com/vishwatejD/picoCTF/assets/141154035/90829e10-9c65-4e41-a620-9f06368389e4)

This doesnot give us any important information about the key.

Thus we ask it through the terminal.
when we go to the directory where **cert** is downloaded and run the command 
` $ cat cert` 

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/ca96d56e-e3f5-4878-84af-4a29bbbbd26e)

We now go to the website [decode.fr](https://www.dcode.fr/rsa-cipher)

There we go to the RSA certificate reader to get the required values.

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/339b41b8-773e-4000-b1e0-2d6ae1ea72d1)

From it we get the values of the modulus(n), e, and bits.

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/0d4f8744-99e6-4cd8-a4d6-b0e891430cdb)

To understand how Rsa certificate works I referred to https://sectigostore.com/page/what-is-an-rsa-certificate/

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/bb219e0c-702d-4693-a267-c5993a81dd03)

The hint also conveys that the flag is of the form picoCTF{p,q} where p, q are the factors.

Performing prime factorisation on the obtained n (modulus) we get the factors as 67867967 , 73176001

> the factorisation can be done using online calculators like factordb or through terminal using the command `$ yafu "factorise <modulus>"`

 **Flag:- picoCTF{73176001,67867967}**
