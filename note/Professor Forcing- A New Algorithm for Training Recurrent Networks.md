# Professor Forcing: A New Algorithm for Training Recurrent Networks
Exposure bias is a great issue in RNN generation task. The previous work like schedule sampling have migitated this issue to some extent, while this paper aims to solve it with the discriminator via GAN architecture.   

### what is exposure bias?
In rnn generation task, the rnn will be fed the ground truth every time step. However, in inference stage, the rnn have to generate the sequence in the absence of any ground truth signal, which brings out the gap between training and testing process.

### what is the differene between professsor forcing and teacher forcing
actually, **teacher forcing** is the normal NLL, which the rnn is fed with the fround truth(teacher signal)   
While the **professor forcing** use adversarial learning to discriminate the input data from teacher signal and self-generated signal

## keypoints
- discriminator to disciminate teacher mode(all ground truth) and self-generated mode(all free generated) 
- can view professor forcing as regularizer(regularize the mode between teacher signal and self-generated signal)

