# Lookey here
## goal
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it. Download the data here.
> given a file named anthem.flag .txt which contains the flag or information for the flag.

### Write up

The hint says to look up for known prefix of flag. The known prefix is picoCTF{XXXXXX}.

So we open the file and look up for the string picoCTF.

**Another method** is to use terminal to find the pattern of strings using the grep command.

We open the directory where the file is downloaded and use the following command.

`$ cat anthem.flag.txt | grep "picoCTF"`

The above command first reads the text file and then the grep command finds the picoCTF string and prints the line.

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/f3234183-c1e1-4a13-b039-a887e242c668)

FLAG:- picoCTF{gr3p_15_@w3s0m3_4c479940}
