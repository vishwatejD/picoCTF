# GDB baby step 1
## GOAL
Can you figure out what is in the eax register at the end of the main function? Put your answer in the picoCTF flag format: picoCTF{n} where n is the contents of the eax register in the decimal number base. If the answer was 0x11 your flag would be picoCTF{17}. Disassemble this.

## HINTS
1.gdb is a very good debugger to use for this problem and many others!
2.main is actually a recognized symbol that can be used with gdb commands

## WRITE UP

I downloaded the file and ran the ` $ file debugger0_a` command on the downloaded file.
It said it was
![image](https://github.com/vishwatejD/picoCTF/assets/141154035/53ca3e3a-7eed-43d4-ae6a-7958be0c5d20)

~~ first i ran the file on ghidra hoping to find any clues, but i didnt find any~~

Using the hint given i used the following command

`$ gdb debugger0_a`

Our ultimate goal is to reach the main function.

 Thus , i used `$ info functions`
 
>NOTE:- info functions prints the names and data types of all defined functions

Now I used `disassemble main`

As we see, we have 0x86342 beside eax register.

We convert this into decimal --------> according to the question.

> RESOURCE USED:- https://stackoverflow.com/questions/10680670/ask-gdb-to-list-all-functions-in-a-program

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/8b1b37e6-7843-41de-9acb-fb7c3aea75bb)

format for flag:- picoCTF{decimal}

FLAG:- **picoctf{549698}**

