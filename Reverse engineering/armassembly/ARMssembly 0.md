# ARMssembly 0
## GOAL
What integer does this program print with arguments 182476535 and 3742084308? File: chall.S Flag format: picoCTF{XXXXXXXX} -> (hex, lowercase, no 0x, and 32 bits. ex. 5614267 would be picoCTF{0055aabb})

# HOW ARM ASSEMBLY WORKS

I referred to these sites to know about ARM assembly

(https://azeria-labs.com/arm-instruction-set-part-3/)

(https://developer.arm.com/documentation/ddi0487/latest)

# WRITE UP

The file is written in ARM assembly language. To read this code we need a compiler.

> RESOURCE USED:- https://github.com/joebobmiles/ARMv8ViaLinuxCommandline

1.we now install a Cross Compiler
 `$ sudo apt install binutils-aarch64-linux-gnu`

2. Now Compiling ARMv8
 
 `aarch64-linux-gnu-as -o chall.o chall.S`
 
 `aarch64-linux-gnu-gcc -static -o chall chall.o`

we need to install a version of QEMU that runs statically in the background with the following command `sudo apt install qemu-user-static`. Now we can run ARM binaries without any issue.

Now running the program with given arguments, `./chall 182476535 3742084308`

>Result: 3742084308

convert this into hexadecimal using [decode.fr](https://www.dcode.fr/hexadecimal-system)

>Result: df0bacd4

**Given Flag format**: picoCTF{XXXXXXXX} -> (hex, lowercase, no 0x, and 32 bits

So,
FLAG :- **picoCTF{df0bacd4}**

