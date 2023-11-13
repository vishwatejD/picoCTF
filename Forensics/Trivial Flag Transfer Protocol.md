# Trivial Flag Transfer Protocol
## GOAL
Figure out how they moved the flag.
## HINTS
What are some other ways to hide data?
## WRITE UP
If we download the given file we get a pcapng file.
```NOTE:- to read pcapng there is a program that can be used named as wireshark.If wireshark is not present install it.```
It can be downloaded by using the command `$ sudo apt install wireshark`
We then go to wireshark and open the file given.we will get an ouptut similar to the image given below.

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/168dff11-f65a-4bb7-a79a-f94fb207b5cc)

As the name of the challenge states we only need the TFTP files.

So we use the export objects option in the file menu to export the TFTP.

We get the following 5 files.

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/a21c3ae7-a9b6-4814-92b6-0c80e008e85e)

If we open the `instructions.txt` we find a string of text that doesnot make any sense, thus we have to decrypt it into readable form, I figured out that the possible forms of decryption are substitution, caesar, or rot13.

Trying each of them will finally give meaningful sentence for rot13.

### Instructions.txt and plan

Before :`GSGCQBRFAGRAPELCGBHEGENSSVPFBJRZHFGQVFTHVFRBHESYNTGENAFSRE.SVTHERBHGNJNLGBUVQRGURSYNTNAQVJVYYPURPXONPXSBEGURCYNA`

After  : `TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN`

After proper punctuation we get 
> TFTP DOESNT ENCRYPT OUR TRAFFIC SO WE MUST DISGUISE OUR FLAG TRANSFER. FIGURE OUT A WAY TO HIDE THE FLAG AND I WILL CHECK BACK FOR THE PLAN

Similarly for plan we get

> I USED THE PROGRAM AND HID IT WITH - DUEDILIGENCE.CHECKOUTTHEPHOTOS

It asks me to check out the photos and open the program file.

### program.dep

Running the file command for program.dep file we get
`$ file program.dep`

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/2b7be81d-4fbf-45ab-891d-78f44c47c459)

It says debian binary package.

If we open the file we find

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/b93c4585-adee-423d-ab69-7b3e4da989cc)

If we explore all the files in these folders. we notice there is a README.txt file which guides us what to do and we also notice that the word steghide is repeated many times.

Reading the README file we get to know how to extract the files.

>Note:- Steghide is a steganography program that is able to hide data in various kinds
of image- and audio-files. The color- respectivly sample-frequencies are not
changed thus making the embedding resistant against first-order statistical
tests.

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/f4196cd5-d97f-4bfc-aaf0-21dcea23600c)

By running that command with every picture.bmp file With the passcode `DUEDILIGENCE` 

>NOTE:- it was mentioned in the plan file that the files were hidden with DUEDILIGENCE

we Find the `flag.txt` file in picture3.bmp

> NOTE:- we must be in the directory where all these files are save to perform these actions.

Now we use the command `$ cat flag.txt `

FLAG : picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}



