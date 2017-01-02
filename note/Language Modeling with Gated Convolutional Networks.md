# Language Modeling with Gated Convolutional Networks

## Abstract
This work aims at model **long-term** dependencies on text and reaches stae-of-the-art at [WikiText-103](http://metamind.io/research/the-wikitext-long-term-dependency-language-modeling-dataset/) and Google Billion Word benchmark. Besides their better performance, they also emphasize the higher throughput. 

***Main Contributions***
- Use gated CNN to achieve state-of-the-art performance

note: the concept of gate in CNN have been proposed in [here](https://arxiv.org/abs/1511.05622), while the previous work suffer from graident vanishing, due to non-linear function like signoid and tanh.

## Method

###What gate did they use? and why?
This work used **output gate** for their gated CNN. In LSTM, forget gate is important for the information flow. However, from the empirical result, CNN structure doesn't suffer this problem so it doesn't need forget gate.

### What's the advantage of this method?
- The convolutional neural network is good for handling hierarchical concept. So, here they stack multiple layers of Conv layer with the proposed gated linear unit.   
- CNN can be operated in a parallel way, which increase the throughput.


## Comments
- This task emphasizes the long-term understanding. RNN-based methods(including lstm and g-rnn) are feed forward in a sequestial fashion, which may suffer information lose is the paragraph is way too long. The CNN-based method may partially solve this problem (I doubted).
- This model still need to prove whether they can achieve the same performance as RNN-based method in other senario, e.g dialogue.