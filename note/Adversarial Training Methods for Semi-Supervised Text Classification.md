# Adversarial Training Methods for Semi-Supervised Text Classification
by Takeru Miyato, Andrew M. Dai, Ian Goodfellow

## Overview

Many other work have shown that our state-of-the-art model can't recognize the adversarial example from the original example. To tackle this problem, adversarial training rises up. With adversarial training, model can obtain generalization performance for the original data. This work is the first one to use adversarial training on text classification. 

## Methods
Since the most popular way to represent the word is one-hot vector, adding perturbations on one-hot vector may lose the spirit of adversairal examples(too easy to recognize). This work add perturbations on the embedding vectors. **Though it deviates the one of the motivation: preventing malicious input, it can still help the generalization on this task.**   
note: the embedding matrix here is standard normalized to prevent the model encourage the embedding matrix generate huge values.
note: adversarial training can prevent early overfitting problem

### Adversarial training
The objective function is look like below:   
<img src="./images/AD_train.png" width="600" align="center">   
We first train our model(log(y|x;θ)) to recognize the Radv, and linearize the log(y|x;θ) to find the R***adv***, which can break the model the most. ε is the hyperparameter of the scale of perturbations   
note: the R***adv*** can be iteratively trained to break the model the most.

### Virtual adversarial training => semi-supervised learning
The concept of virtual adersarial training is constraining the output distribution of the adversarail input similar to unmodified input. We use the KL divergence to measure the similarity of the two distribution. This constrainst makes the output distribution smooth, which can be considered as making the classifier resistant to perturbations in directions to which it is most sensitive on the current model p(y|x;θ)

### **Important concept**
A common misconception is that adversarial training is equivalent to training on noisy examples. Noise is actually a far weaker regularizer than adversarial perturbations because, in high dimensional input spaces, an average noise vector is approximately orthogonal to the cost gradient

## Comments
- Is there any other elegant perturbations mathod on dicrete input (e.g text)?
- This paper have very comprehensive experiments, and have clarify some valuable concepts.
