# 🎨 Generative Adversarial Network (GAN) for Image Generation 🤖✨

## 📝 Overview 🎯🔥
This project implements a Generative Adversarial Network (GAN) using TensorFlow and Keras to generate images from random noise. 🎨 The generator and discriminator networks are trained in an adversarial manner to improve the quality of generated images. 🤖⚡

## 🌟 Features 🚀🎭
- Implements a GAN model with a generator and discriminator.
- Uses LeakyReLU activations and UpSampling for image generation.
- Trains on the Fashion MNIST dataset.
- Generates 28x28 grayscale images.
- Includes training pipeline with caching, shuffling, and prefetching for efficient processing.

## 🏗️ Model Architecture 🖼️🔍
### 🎨 Generator 🏗️🛠️
- Input: 128-dimensional random noise vector.
- Transformed into a 7×7×128 feature map.
- UpSampling and Conv2D layers progressively increase spatial resolution.
- Outputs a 28×28×1 grayscale image.

### 🛡️ Discriminator 🎯📉
- Input: 28×28×1 grayscale image.
- Convolutional layers extract features.
- Fully connected layers classify real vs. fake images.
- Outputs a probability score.

## 🏋️ Training Process 🤖⚔️🎭
- The generator creates fake images from random noise.
- The discriminator distinguishes between real and fake images.
- Both networks compete in a minimax game, improving their performance over time. 🔄⚡

4. Generate images using the trained model. 🎨📸

## 📊 Results 📈✨
- The model need further training to generate more realistic images (limited resources T-T).
- The model learns to generate realistic 28x28 grayscale images similar to the training dataset.
- Improvements can be made by fine-tuning hyperparameters and training for more epochs. 🔍🚀

