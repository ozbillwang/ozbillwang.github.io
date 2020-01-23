---
layout: post
title: Deep learning for time series classification
---

In this post I will cover another major aspect of my work, time series classification using deep learning models.

![_config.yml]({{ site.baseurl }}/images/neurons.jpg)  

Time series classification is a widely used task and has many practical applications, such as medical diagnoses of vital signs, brain wave classification, stock market analysis, network traffic analysis and prediction and more...  
  
Fawaz et al. inspected the performance of several deep learning models on the classification of various time series datasets - <https://github.com/hfawaz/dl-4-tsc/>. I took this study and expanded it to a larger multivariate time series dataset, and added my own favorite Neural architecture search (NAS) algorithms to the study.  
  
Perhaps the most popular classical, non-DL method for TSC is the combination of Dynamic time warping (DTW) with K-nearest neighbors. This works by calculating the similarity between the currently tested sample and all samples in the training set using DTW, and assigning the tested sample the label of the closest training sample (or an aggregation of K labels if K>1).  
Another popular non-DL approach is the manual extraction of features from time series samples. These are static properties, such as skewness, variance, seasonality rate and more. All of these are fed into a traditional classifier, such as a decision tree, which makes the decision based on the aggregated information received as the features.
These baselines have been shown to be a pretty hard baseline to beat and we will test several DL algorithms to see how they match up to the task.  
  
The algorithms tested are:  
  * Residual convolutional neural network (Resnet): defined by the residual skip connections going from lower to higher layers in the network.
  * MLP (Multilayer perceptron): A simple neural network contaitning three fully connected layers.
  * FCN (Fully convolutional neural network):



