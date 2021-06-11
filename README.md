## Cartoon Image Generator with Deep Convolutional Generative Adversarial Networks

### DCGAN's training process step by step.
1. We take some noise from random (Gaussian) distribution, then we feed it to the Generator G (which is a Convolutional Neural Network) to produce the fake image instances x (label y=0) = (x,y) input-label pair.

2. We take this fake pair and the real pair x (label y=1) and feed it to the Discriminator D alternatively.

3. The discriminator D is a binary classification convolutional neural network so it calculates the loss for both fake x and real x and combine them as the final loss as D loss. The discriminator is trained on both batches of images separately , considering Generator frozen.

4. The generator G also calculates the loss from it's noise as G loss since each network has a different objective function. The generator is trained with ground truth label as 1 for all examples and considering discriminator frozen.

5. The two losses go back to their respective networks to learn from the loss (adjusting the parameters wrt the loss).

6. Apply any optimization algorithm (Grad descent, ADAM, RMS prop, etc..) Repeat this process for certain no of epochs or as long as you wish. Each network has conflicting goals so these two networks pit against each other during the training. The generator G gets stronger and stronger at generating the real type of results and the discriminator D also gets stronger and stronger at identifying which one is real, which one is fake.

### Arcitecture
![images](images/dcgan.png)

### Reference
https://gsurma.medium.com/image-generator-drawing-cartoons-with-generative-adversarial-networks-45e814ca9b6b



