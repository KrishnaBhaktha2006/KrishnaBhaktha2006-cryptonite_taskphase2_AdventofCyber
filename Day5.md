# SOC-mas XX-what-ee

*Flag1:* THM{Brut3f0rc1n6_mY_w4y}
*Flag2:* THM{m4y0r_m4lw4r3_b4ckd00rs}

How you approached the challenge:

- step 1: Like the name says XML External Entity (XXE)  i have done a challenge on this topic from pico. 

![image](https://github.com/user-attachments/assets/06376a94-222e-4392-8122-7119514b6638)

Like this page shows we can add stuff to our wishlist. So then We move on to our wishing list and proceed to checkout. Before this if we use burpsuite and do the following stuff we get this

![image](https://github.com/user-attachments/assets/4398c200-4a44-4c08-a213-c0803c8db0b6)

Well when we continue stuff it says we cant access the info on wish21 since its admins.

- step 2: So i inserted the xxe in burpsuite for response.

![81f05af273084c34ba058affdfa68454 1](https://github.com/user-attachments/assets/5cf86100-1a26-49a4-9de9-650566a9e90c)

And ye i thought i thought i got the flag but no i didnt so i thought it is in one of the txt files so i thought of bruteforcing using burpsuite. 

![4af0b5dce7454b4b8855da88532d717b 1](https://github.com/user-attachments/assets/2c1b5abd-32f0-43e1-a6ac-f0dbb3fe532a)

And then out of all the responses i checked the odd one out there was one with 452 length when others are near 410. and it showed this

![74bf36c9134f4d3284dccb7dc93f83db 1](https://github.com/user-attachments/assets/e62a5574-03dd-4b80-8d77-ecb944cca2bb)

And then for the second flag i couldnt really figure out how to do this so i saw the youtube video.

What you learned through solving this challenge:

1. About XXE

Other incorrect methods you tried:

- No incorrect methods tried.

References

- https://www.youtube.com/watch?v=w7aAinxT1pE
