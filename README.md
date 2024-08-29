# Toon Generative Adversarial Network(GAN)
The aim of this project is to utilize a pytorch-based Generative Adversarial Network(GAN) to generate cartoon faces. The developed model takes random noise and generates 128X128 pixeled images. The model was trained on GPUs offered by Google on the Google Colab environment and I would recommend that the files be run there for consistent results.

## Table of Contents
- Introduction
- Model Architecture
- GAN Training
- GAN results
- Sources

## Introduction
Generative Adversarial Networks(GANs) are a type of neural network that can be used to create novel, never-before-seen, data samples given a training dataset of samples. It is made up of two sub-models.
1. The Generator, which performs the function of generating new data samples.
2. The Discriminator, which performs the function of discriminating between real and fake images(made by the generator).
During the training protocol, the generator and discriminator work against each other such that the generator is penalized if it is not able to deceive the discriminator, while the discriminator is penalized if it is not able to distinguish the fake images created by the generator. Over time, this leads to better images from the generator that look real.
The GAN in this project was trained on Google's toon dataset(Link: https://google.github.io/cartoonset/index.html) which contains 100000 images of different cartoon faces. The GPU used to train was Google's A100, however, other non-paid options are also available on Google Colab.

## Model Architecture
For this model, I had to find a balance between complexity, and resource availability. My initial plan was for the model to have the first hidden layer contain 64X64 pixels, however, that seemed to require significantly more resources than available. Because of this, I lowered the number of neurons. The final generator had six layers, each with a decreasing number of neurons from the one preceding it for the most part. The final layer outputted a 128X128X3 tensor, representing the output image.
The discriminator takes a sample 128X128 image, passes it through five hidden layers, each with an increasing number of neurons than the one preceding, and outputs a binary prediction value that would identify the inputted image as either real or fake. 

## GAN Training
The training protocol is outlined in the this_toon_does_not_exist.py file. The script was made on the Google Colab environment, however, it could be slightly modified to run on a local GPU if one is available. By default, the training is done for 15 epochs, which takes some time. This could be increased for better results as outlined in the this_toon_does_not_exist.py file. The generator model can be downloaded after the protocol is completed for future use. 

## GAN Results
Loading and visualizing the results could be done using the loading_toon_models.py file. I have provided a model trained for 110 epochs that could be loaded to visualize the results, however, I encourage you to try training your own model and visualize the results using the mentioned file after uploading on Google Colab. 
The network showed relevant results as the smaller details like the eyes and nose were visible in the generated images. 




## Sources
This project was inspired in part by the viral GAN-assisted face generator, this-person-does-not-exist(link: https://this-person-does-not-exist.com). I wanted to try the same concept on a smaller scale and decided to use Google's toon-face dataset(Link: https://google.github.io/cartoonset/index.html). Finally, another inspiration was the publication by Aston Zhang and collegues(Link: chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://classic.d2l.ai/d2l-en-pytorch.pdf). The dive-into-deep-learning tools training of GAN for pokemon images was used as an inspiration. 
