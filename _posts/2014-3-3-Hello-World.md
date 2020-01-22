---
layout: post
title: Neural Architecture Search for EEG classification
---

In this post I will cover what has been a major part of my thesis, Neural architecture search, and specifically its implication on EEG data classification.

![_config.yml]({{ site.baseurl }}/images/neurons.jpg)

First things's first, what is neural architecture search?  
Deep learning has been gaining major traction in the past couple of years, especially thanks to AlexNet, the CNN architecture created by Krishevsky et al. which dominated the 2012 ImageNet competition, bringing Convolutional neural nets into research spotlight. Since then the best of minds have been creating new and improved deep learning architectures, be it VGGNet or ResNet which re-defined network depth, or GoogLeNet which brought the reusable "inception" module.  
  
Despite all of these improvements, the outcome is always a single neural architecture. The question that should be asked, though, is - "Does a single architecture fit all?", and "Will an architecture that plays well on benchmark datasets work equally well on real-world datasets"?  
 
 ![The AlexNet architecture]({{ site.baseurl }}/images/alexnet.png)
*The seminal AlexNet architecture by Kriscevsky et al.* 

My conjecture to these questions of course is "No!". Why should a single architecture, aimed to reach high benchmark scores, work well on various datasets? For this reason I got into the field of Neural architecture search (NAS). NAS is a means of creating neural network architecture automatically, given a dataset and a specific problem. NAS isn't a new topic and dates back to the late 80's with articles such as ... and ....  
Recent advances in NAS (mainly by Google) have brought it to global research focus as well.  
  
In my thesis I decided to combine my interest in Neuroscience and deep learning to create an EEG classifier, tailor made for each dataset. How did I do that? Let's dive in!  
 
----

I chose to implement a simple NAS algorithm, which turned out to work quite well on various EEG datasets. I created a genetic algorithm, which evolves CNN architectures from scratch, and returns the most competent architecture (tested on a hold-out validation set). The architectures evolved by this algorithm are simple series of layers, where layers can be either: Convolution, Dropout, BatchNorm, ELU activation function, MaxPooling or Identity.
