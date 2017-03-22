# Generating Sentences from a Continuous Space
The author applies VAE on text generation task(A model that encodes useful information in the 
latent variables will have a non-zero kl divergence term and a relatively small cross entropy 
term.) This causes the model to initially learn to ignorez and go after low hanging fruit, explaining 
the data with the more easily optimized decoder.

## keypoints
- straighforwardly use VAE in language modeling is prone to zero KL divergence(degenerate to autoencoder)
- to tackle the zero kl divergenece :point_right: KL cost annealing

## note/question
