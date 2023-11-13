# MacroHard WeakEdge
## GOAL
I've hidden a flag in this file. Can you find it? Forensics is fun.pptm
## WRITE UP
If we download the file and open it, we get a powerpoint presentation which is empty. After searching in google for comands which help in finding hidden files inside a file, I found it is `$ binwalk` and to extract the files we do `$ binwalk -e filename `

Now we go to the terminal and dive into the directory which consists of the given file and run binwalk command.

`$ binwalk 'Forensics is fun.pptm'`

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/767f0585-16fb-4d3a-bcb5-6dd1778605d4)

Now we have found the hidden file, thus we have to extract these files.

`$ binwalk -e 'Forensics is fun.pptm'`  e -stands for extraction.

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/a6342cad-57b6-4c26-8fdb-30eca1564586)


Now it shows the file forensics is fun as a directory.

Now we can dive intoit using the cd command and run the cat command.

We get a string of characters which is in base 64 format. We can use this site to convert [base 64](https://www.base64decode.org/) to ascii.

We get the flag.

FLAG:- picoCTF{D1d_u_kn0w_ppts_r_z1p5}
