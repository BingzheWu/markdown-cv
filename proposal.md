
## Single Image Resolution via Learnable Percptual Loss

We plan to implement the single image super resolution(SISR) based GAN.
Many previous works have studies on this problem. We are planing to
extend the ideas of [1] and [2] based on tensorflow. Now we already
have write a basic version in .

Next, we'll introduce our core ideas.

## Motivation

The traditional  pixel-wise mean square error (MSE) is not suit for the SISR task for
the reason that natural image distribution is not in a Eculidean space , they
are at a low-dimensional manifold. The reconstruction image from the MSE based methods
is tend to blur and not natural. We address this problem by introducing percptual loss.

In [2], the authors use a pretrained VGG16 model to get the features of two images that be
to compared. Then the authors replace the MSE with the MSE in feature space.

We notice that the feature space buided by VGG16 network is not trained for your
own train dataset. This may leads to the feature extracted by vgg16 is not suit for
your own dataset.

We want to use a sparse auto encoder to build the feature space. And then we can
evaluate the similarity between raw image and the reconstruction image. Further more,
we could add a distance network to learn a distance in traning iamge space.

## Method
  We can formulate a optimization problem based on the perceptual loss. We propose a
  GAN based method to solve this optimization problem. To overcome the difficulties appearing
  in the GAN traning phase, we plan to use the combination of WGAN [3] and EBGAN [4].
## Ref

[1] EnhanceNet: Single Image Super-Resolution through Automated Texture Synthesis, Mehdi S. M. Sajjadi et al.

[2] Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network, Christian Ledig et al.

[3] Wasserstein GAN

[4] Energy-Baed Generative Adversarial Networks
