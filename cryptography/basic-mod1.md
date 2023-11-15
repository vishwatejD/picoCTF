# basic-mod1
## GOAL
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message here. Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. picoCTF{decrypted_message})
## message
128 322 353 235 336 73 198 332 202 285 57 87 262 221 218 405 335 101 256 227 112 140 
## HINTS
1. Do you know what mod 37 means?
2. mod 37 means modulo 37. It gives the remainder of a number after being divided by 37.

## WRITE UP

 Do the modulus operation by using the following code
```c
x=128,322,353,235,336,73,198,332,202,285,57,87,262,221,218,405,335,101,256,227,112,140
y=37
c = [str(num % y) for num in x]
print (c)

```
we get the following output
output = `['17', '26', '20', '13', '3', '36', '13', '36', '17', '26', '20', '13', '3', '36', '33', '35', '2', '27', '34', '5', '1', '29']`

Now i manually coverted the numbers according to the conditions given in question.

Now i wrapped this text in picoCTF{}

FLAG :- picoCTF{R0UND_N_R0UND_79C18FB3}
