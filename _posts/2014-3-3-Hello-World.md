---
layout: post
title: Neural Architecture Search for EEG classification
---

In this post I will cover what has been a major part of my thesis, Neural architecture search, and specifically its implication on EEG data classification.

![_config.yml]({{ site.baseurl }}/images/config.png)

First things's first, what is neural architecture search?  
Deep learning has been gaining major traction in the past couple of years, especially thanks to AlexNet, the CNN architecture created by Krishevsky et al. which dominated the 2012 ImageNet competition, bringing Convolutional neural nets into research spotlight. Since then the best of minds have been creating new and improved deep learning architectures, be it VGGNet or ResNet which re-defined network depth, or GoogLeNet which brought the reusable "inception" module.  
  
Despite all of these improvements, the outcome is always a single neural architecture. The question that should be asked, though, is - "Does a single architecture fit all?", and "Will an architecture that plays well on benchmark datasets work equally well on real-world datasets"?
