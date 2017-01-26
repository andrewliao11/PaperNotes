# Adversarial Learning for Neural Dialogue Generation
This paper shows that adversarial learning can be applied to dialogue generation and further test their 
discriminator in some well-define cases (note that these two part is almost **independent**. Namely the author 
didn't show that the **best generator can result in best performance in the later case**). Just like SeqGAN, the author 
incorporate policy gradient(to tackle discrete action space) and discriminator(to recognize the real response from the 
fake one).    
Some tricks are used, like REINFORCE with bariance reduction, teacher forcing, eliminate the response less that 
5 words as oracle response

## keypoints
- model architecture: G:seq2seq with attention; D:hierarchical encoder
- first work on dialogue generation with adversarial learning
- incorporate the discriminator into REINFORCE algo (as reward) like SeqGAN
- adversarial evaluation is a quite important characteristic for GAN architecture; however, the method to evaluate this 
paper proposed still can't surve as a good solution


## note/question
- the author claimed that dialogue trained with adversarial learning can generate more interesting, non-repetitive response
- the related work have done a thorough survey on dialogue generation; check out if you're new to it.
- the author complain for the time-comsuming training process if using MC search. 
Can we apply some other mehtod in RL to migitate this issue? (eg. TD-error :point_right: without serious thinking)
-  the author proposed a method to speedup the training process: sec3.2 REGS. however, it didn't get comparable performance
- I think they still need to report BLEU, METEOR, etc, though the author emphasize that "the adversarial learning is more beneficial to tasks in which there is a big discrepancy between the distributions of the generated sequences and the reference target sequences"
