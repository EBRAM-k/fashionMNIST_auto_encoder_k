# Image Colorization using Autoencoder on CIFAR-100
![download](https://github.com/user-attachments/assets/4800ed0d-47da-43c5-ad77-e5ee8f07947d)



This repository contains an implementation of an Autoencoder model to convert grayscale images into color images. The model is trained on the CIFAR-100 dataset using a combination of Convolutional Neural Networks (CNN) and Fully Connected layers.

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Architecture](#architecture)
- [Requirements](#requirements)
- [Usage](#usage)
- [Results](#results)
- [References](#references)

## Introduction

Autoencoders are a type of neural network used to learn efficient codings of input data, primarily for the purpose of dimensionality reduction or feature learning. In this project, we utilize an Autoencoder to perform image colorization, transforming grayscale images into their colored counterparts.

The CIFAR-100 dataset, which consists of 60,000 32x32 color images in 100 classes, is used for training and evaluation. The grayscale images are generated by converting the original color images, and the model is trained to recover the color from these grayscale inputs.

## Dataset

The CIFAR-100 dataset contains 100 classes with 600 images each. The dataset is divided into 50,000 training images and 10,000 test images. Each image is 32x32 pixels and has three color channels (RGB).

### Data Preprocessing

- Convert RGB images to grayscale by averaging the color channels.
- Normalize the pixel values to the range [0, 1].
- The model takes grayscale images as input and outputs the colorized images.

## Architecture

The Autoencoder consists of two main parts:

1. **Encoder**: 
   - Convolutional layers to extract features from the grayscale image.
   - Fully connected layers to further reduce the dimensionality and capture the essential features.

2. **Decoder**:
   - Fully connected layers to expand the encoded representation.
   - Deconvolutional layers (transposed convolutional layers) to reconstruct the color image from the encoded features.

### Encoder Architecture
- Several convolutional layers followed by batch normalization and ReLU activation functions.
- Flattening and fully connected layers to obtain a compact representation of the image.

### Decoder Architecture
- Fully connected layers to expand the compact representation.
- Deconvolutional layers to reconstruct the 32x32 RGB image.

## Requirements

To run this code, you need the following libraries:

- Python 3.x
- TensorFlow 2.x
- Keras
- NumPy
- Matplotlib

You can load model by:

```bash
autoencoder = load_model('my_model.h5')
