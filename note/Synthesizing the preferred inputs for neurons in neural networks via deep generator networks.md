# Synthesizing the preferred inputs for neurons in neural networks via deep generator networks

## Abstract
This work aims to analyzing the activation of DNN. The previous work searches in the image space(RGB) and
tries to maximize the activation in the last layer. The network is fixed and we just optimize the input image, 
making it maximizing the activation. This kind of method is called **"activation maximization"**.   
A main problem is that the result image seems to be nosense to human beings. This paper aims at generating realistic 
image and maximize the activation, called DGN-AM.   

***Main Contributions***

- Use DGN in activation maximization 
- Restricted the search to only set of images that are drawn from the priors
- Many interesting results to show the robust of this structure
$ note that ***prior*** refer mentioned here is the bias from the pretrained DGN

## Method
The whole architecture is like the below figure:    
<p><img src="./images/DGN_AM.png" align="center" width="800"></p>

- DGN: Based on CaffeNet feature and take the fc6 as code. The model combine the concept of VAE and GAN, It'll compare the pixel-wise ,feature-wise loss, and descriminator loss.   
<p><img src="./images/DGN.png" align="center" width="400"></p>

- DNN to be visualized: can be any DNN network
- tricks: 
  - clip the code value: the maximization process may result in extremely large values. 

## Experiments

1. Comparison between priors trained to invert features from different layers   
  Compare using conv3,conv4.....fc6,fc7,fc8 as code. Found that the fc layer generate better results since it contains 
  more abstract concept.
2. 


## Comments
