# keygenme-py
## GOAL

## WRITE UP

In the code it is given that 

```c
key_part_static1_trial = "picoCTF{1n_7h3_|<3y_of_"
```
it is half of the flag , we need to find the next part of the flag that is `key_part_dynamic1_trial = "xxxxxxxx"` using the code.

After analysing the code we understand that each of the digits of xxxxxxx are hashed as follows

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/23d3abe4-3f37-41e0-8a69-a74f590ec0e9)

The no of if commands matches with the number of characters needed for the key.

> Note:- the i here is being rewritten and added with 1 to replace the next place.

To retrieve the key i typed the following code.

```c
import hashlib

username_trial = "GOUGH"



print(hashlib.sha256(username_trial.encode('utf-8')).hexdigest()[4])

print(hashlib.sha256(username_trial.encode('utf-8')).hexdigest()[5])

print(hashlib.sha256(username_trial.encode('utf-8')).hexdigest()[3])

print(hashlib.sha256(username_trial.encode('utf-8')).hexdigest()[6])

print(hashlib.sha256(username_trial.encode('utf-8')).hexdigest()[2])

print(hashlib.sha256(username_trial.encode('utf-8')).hexdigest()[7]) 

print(hashlib.sha256(username_trial.encode('utf-8')).hexdigest()[1])

print(hashlib.sha256(username_trial.encode('utf-8')).hexdigest()[8])

```
we get the output as `f911a486` 

Thus the flag is ,

FLAG:- **picoCTF{1n_7h3_|<3y_of_f911a486}**




