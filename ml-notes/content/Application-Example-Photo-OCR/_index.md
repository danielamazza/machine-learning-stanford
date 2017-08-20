+++
title = "Application Example: Photo OCR"
description = ""
date = "2017-08-18T22:21:24+02:00"
weight = 110
+++

This chapter deals with a complex, end-to-end application of machine learning, the **Photo OCR (=Optical Character Recognition)**. Identifying and recognizing objects, words, and digits in an image is a challenging task. We discuss about building a pipeline to tackle this problem and how to analyze and improve the performance of such a system.

## Problem description and pipeline

This problem permits:

* to put together various aspects of the machine learning theory;

* to describe the use of a **pipeline**;

* to introduce the **computer vision** and **artificial data synthesis**.

The problem regarding the recognition of text in images consists of:

1. detect where there is text in the picture;

2. look at each text region and read the text. 

OCR of scanned text is today easier that OCR of text in images. It regards a lot of important applications, as supporting blind people, help car navigation systems. The steps are:

1. Text detection
2. Character segmentation
3. Character classification

There could be also a sort of spelling correction *(for example c1eaning --> cleaning)*.

The three steps above form a pipeline:

IMAGE --> Text Detection --> Character segmentation --> Character Recognition

In many complex machine learning systems, these sorts of pipelines are common.

## Sliding Windows

**Text detection** is an unusual problem in computer vision. Areas containing text are rectangular portion of different sizes. We can think before at a simpler detection problem, regarding **pedestrians**. It is simpler because of the similar aspects ratio (ratio between the heigt and the width of the rectangles) of pedestrians.

### Supervised learning for pedestrian detection ###

We can choose a standard size, i.e. 36x82 pixel and use a neural network model to learn if an image contains a pedestrian (y = 1) or not (y = 0).

Then we apply the algorithm at the image in wich we want to detect algorithm, **sliding the window  36x82 all over the image**. The parameter of sliding is called **step-size**. If the slide-step is small, i.e. 1 pixel, then the algorithm is accurated but it is computation expensive. 

Then we take a larger image patches, to detect bigger pedestrians.

In a similar way, for text detection, we make the training considering a portion of a certain size with positive and negative examples.
Then we use an **expansion operator**, grouping all the close positive regions together.

We use a similar operaration of training the classifier for the **character segmentation** and for the **character classification**.


## Getting Lots of Data and Artificial Data

Artificial Data can be a an easy way to get a huge training set to give to your learning algorithm. 
For example, you can take characters from different fonts and paste these characters against different random backgrounds.

The other main approach to artificial data synthesis is to take real examples and to create additional data for amplifying the training set, introducing distortion. We can do this in text images but also, for example, in audio speeches introducing some background sounds. 

## Ceiling Analysis: What Part of the Pipeline to Work on Next

Considering the pipeline process, how to allocate resources for don't waste time?

The ceiling analysis is based on the measure of how the improvement of each part of the system can influence on the overall system. 




