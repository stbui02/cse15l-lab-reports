# Lab Report 5
## 1. Original Post

Hello everyone,

I've been working on this Java program, ProductCalculator, and I'm encountering an issue.
When I run the program, it gives me an unexpected result for the product of the numbers.
I think there might be a bug in my calculateProduct method because the product is always coming out as zero, even though the numbers in the input file are not all zeros.
I'm not sure what's causing this. I'll paste some images of the output below. Any help would be appreciated!

![Image](Lab5 Report 1.PNG)
![Image](Lab5 Report 1-2.PNG) 

Thanks!

## 2. TA's Response

Hey there!

Thanks for reaching out. If the code for the multiplication is correct then you may be initializing a variable to 0 in your calculateProduct method or the method you are using to generate numbers is creating 0's. 
Multiplying any number by 0 will always result in 0. You may have to check for mathematical or initializing errors in your calculateProduct method.

## 3. Bug Fix and Original Poster Response

Hello [TA],

Thank you for your suggestion! I originally initialized product to 0 and implemented the change of initializing product to 1 instead.
The product is now calculated correctly, and I'm no longer getting a result of 0. I'll add some screenshots of the result after the changes below.

![Image](Lab5 Report 1 Fixed 1.PNG)
![Image](Lab5 Report 1 Fixed 2.PNG) 

Thank you!
