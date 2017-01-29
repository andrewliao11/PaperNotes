# Professor Forcing: A New Algorithm for Training Recurrent Networks
Exposure bias is a great issue in RNN generation task. The previous work like schedule sampling make migitate this issue, while this paper aims to solve it with the discriminator in GAN architecture.   

### what is exposure bias?
In rnn generation task, the rnn will be fed the ground truth every time step. However, in inference stage, the rnn have to generate the sequence in the absence of any ground truth signal, which brings out the gap between training and testing process.


## keypoints
- discriminator to disciminate teacher mode(all ground truth) and self-generated mode(all free generated) 

## notes
