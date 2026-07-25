# Image Colorization Using Deep Convolutional GANs

> **An undergraduate project exploring automatic image and video colorization using Deep Convolutional Generative Adversarial Networks (DCGANs).**

---

## Repository Note

This project was originally completed as part of my undergraduate (Bachelor's) studies as an early exploration of generative adversarial networks (GANs) for image colorization. While the original implementation is no longer available, this repository documents the project's methodology, architecture, experimental approach, and key lessons learned.

The project also explored extending the trained model to colorize videos by processing individual frames and reconstructing the output sequence.

---

# Project Summary

Automatic image colorization is the task of predicting realistic colors for grayscale images. Since a grayscale image may correspond to many possible color combinations, image colorization is considered an ill-posed computer vision problem.

This project explored the use of a Deep Convolutional Generative Adversarial Network (DCGAN) to learn color mappings from paired grayscale and color images. The trained model generated plausible color information while preserving the structural content of the original image.

As an extension, the same approach was applied to videos by extracting individual frames, colorizing each frame independently, and reconstructing the processed frames into a colorized video.

---

# Key Highlights

- Explored automatic image colorization using GANs.
- Developed a DCGAN-inspired architecture for grayscale-to-color image translation.
- Trained the model using paired grayscale and RGB images from a public Kaggle dataset.
- Learned color distributions from visually similar scenes.
- Extended the approach to colorize videos frame by frame.
- Reconstructed processed frames into a colorized video.

---

# Research Motivation

Colorization has applications in restoring historical photographs, enhancing archived videos, and improving visual content for media and entertainment.

The goal of this project was to explore whether a generative adversarial network could learn realistic color mappings from grayscale images without manually defining color rules.

---

# Research Question

**Can a Deep Convolutional GAN learn realistic color representations from grayscale images and extend the same approach to video colorization?**

---

# Methodology

The project followed the workflow below:

```text
Color Image Dataset
        ↓
Convert Images to Grayscale
        ↓
Create Paired Training Data
        ↓
Train DCGAN
        ↓
Generate Colorized Images
        ↓
Evaluate Visual Quality
```

For video processing:

```text
Input Video
      ↓
Extract Individual Frames
      ↓
Colorize Each Frame
      ↓
Reconstruct Video
      ↓
Colorized Video
```

---

# Model Overview

The project used a Deep Convolutional Generative Adversarial Network (DCGAN) consisting of:

- Generator Network
- Discriminator Network
- Adversarial Training Process

The generator learned to predict realistic colors from grayscale images, while the discriminator learned to distinguish generated images from real color images.

---

# Video Colorization Extension

To explore whether the trained image colorization model could be applied beyond static images, the project also experimented with video colorization.

The process involved:

- Extracting frames from an input video.
- Applying the trained image colorization model to each frame independently.
- Reconstructing the processed frames into a video sequence.

Although each frame was colorized successfully, maintaining perfectly consistent colors across consecutive frames remained a challenge due to the absence of temporal modeling.

---

# Key Findings

- GANs can generate visually plausible colorizations from grayscale images.
- Structural information in grayscale images provides useful guidance for predicting colors.
- Extending image colorization to videos introduces additional challenges related to temporal consistency.
- Generative models offer a flexible approach to image-to-image translation problems.

---

# Limitations

- Visual quality was evaluated qualitatively rather than with quantitative metrics.
- Multiple realistic color solutions may exist for the same grayscale image.
- Video frames were processed independently without temporal awareness.
- More recent techniques such as conditional GANs and diffusion models were not explored.

---

# Future Improvements

Possible future extensions include:

- Pix2Pix conditional GANs
- Diffusion-based image colorization
- Temporal consistency using optical flow
- Video-aware GAN architectures
- Quantitative evaluation using SSIM, PSNR, and FID

---

# What I Learned

This project introduced me to generative adversarial networks and computer vision. It was one of my first experiences building a deep learning model capable of generating new visual content rather than simply classifying images.

Working on both image and video colorization helped me understand the challenges of adversarial training, image-to-image translation, and extending computer vision models to sequential data. Looking back, this project provided a strong foundation for my later work in deep learning, natural language processing, and speech recognition.

---

# Technologies Used

- Python
- TensorFlow / Keras
- OpenCV
- NumPy
- Matplotlib
- Kaggle Dataset

---

# References

- Goodfellow, I., et al. (2014). *Generative Adversarial Nets.*
- Radford, A., Metz, L., & Chintala, S. (2016). *Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks.*
- Isola, P., et al. (2017). *Image-to-Image Translation with Conditional Adversarial Networks.*
- Iizuka, S., et al. (2016). *Let There Be Color!: Joint End-to-End Learning of Global and Local Image Priors for Automatic Image Colorization.*
- Zhang, R., Isola, P., & Efros, A. A. (2016). *Colorful Image Colorization.*
