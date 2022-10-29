---
layout: page
title: Publications
subtitle: Scientific articles I wrote during my M.Sc. in Information Systems Engineering
---

## [EEGNAS: Neural Architecture Search for Electroencephalography Data Analysis and Decoding](https://link.springer.com/chapter/10.1007/978-981-15-1398-5_1)
### November 10, 2019  
#### Elad Rapaport, Oren Shriki, Rami Puzis  
![EEG photo](/assets/img/clinical-test-3171456.jpg)
*photo by [@shironosov](https://www.freeimages.com/photographer/shironosov-85416)*  
Abstract:   
EEG, Electroencephalography, is the acquisition and decoding of electric brain signals. The data acquired from EEG scans can be put to use in many fields, including seizure prediction, treatment of mental illness, brain-computer interfaces (BCIs) and more. Recent advances in deep learning (DL) in fields of image classification and natural language processing have motivated researchers to apply DL for classification of EEG signals as well. One major caveat in DL is the amount of human effort and expertise required for the development of efficient and effective neural network architectures. Neural architecture search algorithms are used to automatically find good enough neural network architectures for a problem and dataset at hand. In this research, we employ genetic algorithms for optimizing neural network architectures for multiple tasks related to EEG processing while addressing two unique challenges related to EEG: (1) small amounts of labeled EEG data per subject, and (2) high diversity of EEG signal patterns across subjects. Neural network architectures produced during this study successfully compete with state of the art architectures published in the literature. Particularly successful are architectures optimized for all (human) subjects, with evolution and training performed on a mixed dataset including all subjects’ data.

---

## [Spillover Today? Predicting Traffic Overflows on Private Peering of Major Content Providers](https://ieeexplore.ieee.org/document/9609013)
### November 9, 2021  
#### Elad Rapaport, Ingmar Poese, Polina Zilberman, Oliver Holschke, Rami Puzis  
![Internet photo](/assets/img/pexels-pixabay-159304.jpg)
*photo by [Pixabay](https://www.pexels.com/photo/white-switch-hub-turned-on-159304/)*  
Abstract:   
Large content providers and content distribution network operators usually connect with large Internet service providers (eyeball networks) through dedicated private peering. The capacity of these private network interconnects is provisioned to match the volume of the real content demand by the users. Unfortunately, in cases in which there is a surge in traffic demand, (e.g., due to trending content or massive software updates) the capacity of the private interconnect may deplete, requiring the content provider/distributor to reroute the excess traffic through transit providers. Although such overflow events are rare, they negatively impact content providers, Internet service providers, and end-users. Such impact includes unexpected delays and disruptions that reduce the quality of the user experience, as well as direct costs paid by the Internet service provider to the transit providers. In this article, we examine the problem of predicting an overflow event in order to enable content and Internet service providers to handle the excess traffic in a timely manner. We propose an ensemble of deep learning models trained to predict overflow events over a short-term horizon of 2–4 hours and predict the specific interconnections through which the excess traffic will enter the Internet service provider. Evaluated with 2.5 years (2017-2019) of traffic measurement data from a large European Internet service provider, the models were shown to successfully recall 65% of the events with precision of 51% on average. While the lockdowns imposed by the COVID-19 pandemic reduced the overflow prediction accuracy, the pandemic’s impact on the accuracy was temporary. Although the lockdown continued on and off, the performance of models trained before the pandemic regained their performance during April-May 2020.