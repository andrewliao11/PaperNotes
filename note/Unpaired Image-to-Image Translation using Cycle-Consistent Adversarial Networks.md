# Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks (CycleGAN)
The author aims to do the image2image task in a unsupervised fashion (unlike their previous work: pix2pix, 
which need paired data). Usupervised iamge2image task learns the G(x)->y, or G'(y)->x without (x,y) data. This 
work make no assumption that implicit (x,y) paired data exist in the training set. (not sure if other concurrent works 
make this assumption or not). 

The intuition of this work lies in the cycle relation between paired data (x,y). if G(x)≈y, we can also learn a auxiliary
model tha F(G(x))≈x, which naturally forms a cycle between (x,y).

## compared to others' topics
- neural style transfer: neural style transfer usually paint the image by matching Gram matrix statistics, 
and only focus on **single image pair**. instead, this paper focus on convert one image from one domain to
another domain.

## keypoints/notes
- aside from adversarial loss from two domains, this paper also use L_{cyc} which explained above
- some training details: 
  - replace the negative-log-likelihood in L_{gan} with least square loss errors
  - update the discriminator using history of generated images
  - patchGAN as discriminator; generator follows the Johnson's neural style transfer
- performing well in color/texture changes, while the **limitations on geometric change(cat->dog) needs to
be improved** :point_right: have many usage in robotics

## question
- many image have one-to-more tranformation relation, whil this model can only perform one-to-one relation. 
Isn't it be more exciting to learn one-to-more translation?

## concurrent work
- Unsupervised Image-to-Image Translation Networks
- Learning to Discover Cross-Domain Relations with Generative Adversarial Networks
