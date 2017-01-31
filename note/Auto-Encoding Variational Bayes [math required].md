# Auto-Encoding Variational Bayes [math required]

The author proposed a classic mehtod for variational inference, which include two stages: generating ```z``` from ```x```, generating ```x``` from ```z```.   
In section 2.2, the author use the lower bound of the marginal probability to make the whole process tractable. However, directly do optimization on varionational parameter(the parameter of encoder) is with high variance if using MC gradient estimator. So the author proposed the so-called VAE:   
- set the prior of decoder(```q```) to be unit gaussian   
- the decoder only output the mu and sigma of gaussian, which forms the ```z```

## problem senario:   
- for dataset X consisting N i.i.d. samples, 
	- assume all data are generated from the process invloving random variable ```z```	
	- the process contains: (1) ```z``` is generated from prior probability, p(z); (2) ```x``` is generated from likelihood probability, p(x|z)


## keypoints
- strong theoretical advantages
- good at generate disentangled representation


## note
- the notation in this paper is super clean :metal:


## background
- notation: ***x*** is the event, ***z*** is the latent code   
	- likelihood probability: p(x|z)   
	- posterior probability: p(z|x)   
	- prior probability: p(z)   
	- and **```p(z|x)=p(x|z)*p(z)/p(x) ```**   
- marginal inference: the task of inferring the probability of one variable with a particular value
- [marginalized likihood](https://en.wikipedia.org/wiki/Marginal_likelihood): some parameter variables (eg. ```z```) have been marginalized out


## implementation code
here's my implementation code in Tensorflow, [link](https://github.com/andrewliao11/VAE-tensorflow.git)

