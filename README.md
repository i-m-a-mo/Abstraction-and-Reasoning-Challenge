# Abstraction and Reasoning Challenge
a challenge hosted on [Kaggle](https://www.kaggle.com/c/abstraction-and-reasoning-challenge/) 

&rarr; for a quick overview of the problem at hand and my approach have a look at [Final_Project_Presentation.pdf](/Final_Project_Presentation.pdf)

## Table of contents
* [The Problem](#the-problem)
* [My Approach](#my-approach)
* [Results](#results)

## The Problem:
* Create an AI capable of solving reasoning tasks it has never seen before
* Dubbed "The *hardest* Kaggle Challenge"
* The challenge consists of 400 tasks and each task consists of:
  * Training pairs (Input & output)
  * Test input
  * Test output 
<img src="/images/Example1.png" height="200" align="left"/>
<br><br><br><br><br><br><br><br><br>

* on the basis of the training pairs the AI (or human user) is meant to recognize a pattern that can be applied to the test input to generate the test output 

<img src="/images/Example2.png" height="200" align="left">
<br><br><br><br><br><br><br><br><br>
This pattern recognition is relatively easy for the human eye. Not so much for an algorithm, computer or AI. What’s even harder is that it's not always the same pattern, but 400 tasks that follow their own logic and pattern.
<img src="/images/Problems.png">

* Each task has different shapes:
  * Within each task the inputs and/or outputs can differ in size
  * and they can be different to each other
&rarr; harder for the algorithm to predict the correct size of the test output

<img src="/images/Example3.png" height="150" align="left"/>
<span style="float:middle;"><img src="/images/Example4.png" height="150" ></span>
<span style="float:right;"><img src="/images/Example5.png" height="150" ></span>




## My Approach
**_Convolutional autoencoder with data augmentation_**

### Data Augmentation
* Each tasks presents with varying input and output dimensions
  * Rather small pictures: median around 15 pixels for length and width
* They come with varying numbers of training input-output pairs; most of the time it’s one test input
* Each Task itself doesn’t provide a whole lot of data for the algorithm to learn from

### Convolutional Autoencoder
Convolutional Part (Encoder):
* Takes an image, passes it into a set convolutional layer and MaxPool Layers
* Convolutional Layers are used to identify patterns and save the weights in a new matrix
* Then, maxpool is applied on it to shorten its size 
* This process repeats until we have a small matrix with the information needed to identify the images.

Deconvolutional Part (decoder):
* Second part of the Auto Encoder
* Opposite of the Encoder's work: It takes in an image and does some operations on it to increase its size/dimensions


## Results
*tbd*