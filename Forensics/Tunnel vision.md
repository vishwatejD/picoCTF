# Tunnel vision
## Goal
We found this file. Recover the flag.
## write up
When we try to open the file given we get the following output.

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/a748a970-f2e8-4f3b-87b3-35991a2a7ee0)

This lets us know that the given file is corrupted and is a bitmap file with corrupted header.

Now change the extension of the file as `.bmp`

To know whats the mistake in the header we can take sample files from the internet.

We can download them from this [site](https://filesamples.com/formats/bmp)

Open the smaple file and the given file simultanoeusly in [hexed.it](https://hexed.it/)

Now by comparing the headers and changing the corrupted parts and saving it, we can now open the file to get the following output.

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/27737d45-a17b-4ef9-b395-8b2cb7d36c46)

Now we save it and open the file once again.

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/ec342bf5-582e-44aa-a5d2-529daf4176b3)

The image we get is actually cropped. so we need to change the height/ pixels of the image.

``` formula for no of pixels = (no.of bytes * 8)/bit depth```
We can know these properties by running the exiftool command in tthe terminal for this file.

NOTE: if the command doesnot exist for the computer we can install it by using `sudo apt install exiftool`

![image](https://github.com/vishwatejD/picoCTF/assets/141154035/741109a1-2f2a-48d5-af80-fc3a63af545b)

Now, if we check the number of pixels using the formula, it must be `964466` bytes. But it is only `1134*306 =347004` pixels.

If we examine the image we can understand that the image height is cropped up.

Thus we have to change the image height. 

 ``` 964466/ 1134 = 850.499 ~ 850```

 Now to change the cell which maps to the image height we first convert 850 to hex.
 Which is `0x352`

 ![image](https://github.com/vishwatejD/picoCTF/assets/141154035/f9f44dcb-6bfe-4f4f-bb6e-d9b7edfd4cd1)

 we now save the file and open it . we get the full image and the flag.
 
![image](https://github.com/vishwatejD/picoCTF/assets/141154035/762d72a2-d8ff-4e85-a479-4c9b18ce1461)

