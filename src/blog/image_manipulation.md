---
title: "Manipulating Images in Python: An Experiment"
time:
  epoch: 1488937979
  utcoffset: "UTC-0"
author: "Jackie Meggesto"
categories:
  - python
  - images
  - image manipulation
  - experimentation
---

# A Curiosity Becomes A Challenge

***Disclaimer: I have zero clue what I'm doing here but it was fun as heck)**

I was browsing Facebook when I came across this image:

<img src = '/images/color.png' alt = "A picture of a cake topped with strawberries. The red in the image has been severely washed out."></img>

As the [article about this image claims]():

> 


Naturally, I was curious about whether or not the claim of "not containing any red pixels" was actually accurate. A few questions sprang to mind:

*    Does this mean that the image contains no red channel? 
*    What are the actual RGB values of the component pixels? 
*    Would the component pixels of the image appear red to a person if they were contextually dissociated from strawberries, which our brains associate with the color red?

These three questions formed the basis of my curiosity on this topic, Naturally, I decided to use code to see what I could discover, and what answers might exist for this questions.

# Discovering Scikit-Image

For this task, I installed [scikit-image](), an image manipulation library written in Python. I'm not sure if that was *necessarily* the best choice - I think scikit and derivatives are much more oriented towards scientific tasks than artistic ones - but it was what showed up when searching on StackOverflow, and it provides the bare minimum for what I need to accomplish this task. I'll touch briefly on what I learned about the library itself.

If I understand it correctly, color images in scikit-image are represented as three-dimensional arrays: the outer layer of arrays allows for access of pixels in a (row, column) fashion, and the inner elements are the representations of the pixels themselves, arrays of length 3 with red/green/blue values. It's an easy enough format to work with and understand, so I started playing around.

# Data About The Image Itself

Initially, my first instinct was to just print every pixel in the array. That was a wholly silly idea, of course, because the image, at 857px x 857px, contains 734,449 pixels. Nevertheless, it did reveal the answer to my first question immediately.

<img src="" 
