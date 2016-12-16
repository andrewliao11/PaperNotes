# Semantic Segmentation using Adversarial Networks

- We train a convolutional semantic segmentation network along with an adversarial network that discriminates segmentation maps coming either from the ground truth or from the segmentation network. The motivation for our approach is that it can **detect and correct higher-order inconsistencies** between ground truth segmentation maps and the ones produced by the segmentation net.
- Despite many differences in the CNN architectures, a common property across all these approaches is that all label variables are predicted independently from each other. This is the case at least during training; various **post-processing approaches have been explored to reinforce spatial contiguity in the output label maps** since the independent prediction model does not capture this explicitly

My comment:   
Many people think GAN is better than VAE in producing plausible image since it can generate image with sharp edge. (VAE tends to generate blurring image :pensive:) So the motivation here is quite persuading.

## Overview
- the first application of adversarial training to semantic segmentation
- The adversarial training approach enforces long-range spatial label contiguity, without adding complexity to the model used at test time (w/o post processing)

## Method

Model architecture:   
<img src="https://github.com/andrewliao11/DeepLearningNotes/blob/master/images/semantic%20segmentation%20model.png?raw=true" width="600" align="center">   

Objective Function:   
<img src="https://github.com/andrewliao11/DeepLearningNotes/blob/master/images/semantic%20segmentation%20objective%20func.png?raw=true" width="600" align="center">   
The ***mce*** denotes for multi-class cross entropy; ***bce*** denotes for binary cross entropy.
Function ***a**** denotes the adversarial network, mainly based on the CNN. 

## Experiment
<img src="https://github.com/andrewliao11/DeepLearningNotes/blob/master/images/semantic%20segmentation%20exp.png?raw=true" width="600" align="center">   
Note that the adversarial strategy results in less overfitting, i.e. generating a regularization effect, resulting in improved accuracy on validation data.   
In general, for pixel acc. meanIoU have consist performance boost around 2%


## Comment

- Use **Adversarial Learning** to improve the current semantic segmentation task.
- Actually this concept can be generalized to many case. Built on the supervised model which is trained on some **hand-craft** loss function, we can use adversarial loss to produce even better results.
- ***Future work? Here we can see the adversarial loss as auxiliary loss. Can we do some other auxiliary loss? like edge prediction, intensity(black-white) prediction. Both auxiliary loss can used adversarial learning***
