# Toon Generative Adversarial Network(GAN)
The aim of this project is to utalize a pytorch based Generative Adversarial Network(GAN) to develop a neural network capable of generating cartoon faces. The developed model takes random noise and generates 128X128 pixeled images. The model was trained on gpus offered by google on the googlecolab environment and I would recommend that the files be run there for consistent results.

## Table of Contents
- Introduction
- Model Architecture
- GAN Training
- GAN results
- Sources

## Introduction
Generative Adversarial Networks(GANs) are a type of neural networks that can be used to create novel, never before seen, samples of data given a training dataset of samples. It is made up of two sub-models.
1. The Generator, which performs the function of generating new data samples.
2. The Discriminator, which performs the function of discriminating between real and fake images(made by the generator).
During the training protocol, the generator and discriminator work against each other such that the generator is penalized if it is not able to decieve the discriminator, while the discriminator is penalized if it is not able to distinguish the fake images created by the generator. Over time, this leads to better images from the generator that look real.
The GAN in this project was trained on google's toon dataset(Link: https://google.github.io/cartoonset/index.html) which contains 100000 images of different cartoon faces. The gpu used to train was google's A100, however other non paid options are also available on google colab.

## Model Architecture
For this model, I had to find a balance between complexity, and resource availability. 