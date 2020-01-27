---
layout: post
title: Deep learning for time series classification
---

In this post I will cover a research project comparing different time series classification methods using deep learning models.

![_config.yml]({{ site.baseurl }}/images/stock_market.jpg)  

Time series classification is a widely used task and has many practical applications, such as medical diagnoses of vital signs, brain wave classification, stock market analysis, network traffic analysis and prediction and more...  
  
Fawaz et al. inspected the performance of several deep learning models on the classification of various time series datasets - <https://github.com/hfawaz/dl-4-tsc/>. I took this study and expanded it to a larger multivariate time series dataset, and added my own favorite Neural architecture search (NAS) algorithms to the study.  
  
Perhaps the most popular classical, non-DL method for TSC is the combination of Dynamic time warping (DTW) with K-nearest neighbors. This works by calculating the similarity between the currently tested sample and all samples in the training set using DTW, and assigning the tested sample the label of the closest training sample (or an aggregation of K labels if K>1).  
Another popular non-DL approach is the manual extraction of features from time series samples. These are static properties, such as skewness, variance, seasonality rate and more. All of these are fed into a traditional classifier, such as a decision tree, which makes the decision based on the aggregated information received as the features.
These baselines have been shown to be a pretty hard baseline to beat and we will test several DL algorithms to see how they match up to the task.  
  
The TSC methods tested are:  
  * **Residual convolutional neural network (Resnet)**: defined by the residual skip connections going from lower to higher layers in the network.
  * **Multilayer perceptron (MLP)**: A simple neural network contaitning three fully connected layers.
  * **Fully convolutional neural network (FCN)**: Three successive convolutional layers with Batchnorm and dropout between each layer. Ended by a global pooling layer + softmax for final classification
  * **Time LeNet (tlenet)**: A simple CNN architecture resembling LeNet by Lecunn et al. They used several data augmentation techniques to artificially increase the amount of training data.
  * **Multi-scale CNN (MCNN)**: A simple CNN architecture with an integral pre-processing stage in the form of frequency smoothing and sub-sampling.
  * **Multi-channel deep CNN (MCDCNN)**: A CNN for multivariate TSC. The first layer consists of different convolutional filters applied separately to each input channel. The outputs of these filters are later concatenated and fed through another convolutional layer, followed by a softmax activation function.
  * **Convolutional neural network (CNN)**: Similar to MCDCNN, but here the first convolutional layer receives all input variables as input, thus creating a weighted sum of the input (instead of receiving each input variable separately). 
  * **LSTNet** - an MTS forecasting method, which I tweaked to perform classification instead of forecasting. This method utilizes Gated recurrent units (GRU) as well as convolutional layers in order to extract short and long-term intervariate dependecies in the data.
  * **EEGNAS** - A neural architecture search algorithm designed by myself. Given data and a task, the output of this algorithm is a CNN architecture.
  * **NSGA-Net** - Another neural architecture search algorithm, designed for and tested on image data. This algorithm has been shown to reach state-of-the-art results for the CIFAR10 image classification benchmark dataset.  
   
To test all of the above approaches, I conducted a large-scale comparison using 22 multivariate time series classification datasets.  These are some statistics regarding the data:  

![TS_datasets]({{ site.baseurl }}/images/TS_datasets.png)  

And below are the results for the different algorithms applied on classification of the different datasets. Shown are rankings of each algorithm compared to the others, for each dataset. Additionally shown is a critical different diagram, created by calculating the wilcoxon-holms post-analysis test for each pair of classifiers, with \(alpha=0.05\).

![TS_rankings]({{ site.baseurl }}/images/TS_rankings.png)  
![TS_rankings]({{ site.baseurl }}/images/critical_diff.png)  
  
To conclude this study, I clearly showed the power of automatic neural architecture search. Using the SOTA NAS method for image classification (NSGA-Net), I showed that NAS is applicable to the time series domain as well. In addition, because of the fact that the architectures created in NSGA-Net contain basic building blocks which were shown to work well in the field of image classification, I conclude that these building blocks are successful for classifying time series data as well.
The relative success of EEGNAS, the simple NAS method developed in my thesis, also shows the power of NAS. A 10-layer CNN automatically generated in about 1 GPU day was able to outperform almost all of the hand-designed TSC models created in the past years.

The poor performance of the LSTNet, the time series forecasting model, shows us that the tasks of classification and forecasting in time series are not necessarily interchangeable and different approaches may be needed for each task. I also conclude that not enough large TSC benchmark datasets exist, and that effort should be put in the creation of these datasets. With larger datasets the power of the complex LSTNet model might have been apparent. 
