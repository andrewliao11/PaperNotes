# Generating Text via Adversarial Training
The common problem in using AE or VAE to generate text is that sentences may often occupy a **small**
region in the hidden space. This paper aims to generate text from continuous latent space in an adversarial 
fahsion. 

## keypoint
- use feature matching (from improved_gan: minimizing the distance btn the f(generated) and 
the f(real data), where f(.) is the intermediate layer output)
- using autoencoder to pretrained generator
- do on large corpus :point_right: works after this can follow the tricks here

## note/question
- no comparison btn the pretrained and adv trained model
- "disentangle the latent representations for different writing style in an unsupervised manner" :point_right: this will be 
a good research topic
