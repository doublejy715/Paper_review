Paper Review
============

Words
-----

[Dictionary Link](https://github.com/doublejy715/Paper_review/issues/1)

Survey Github Homepage
----------------------

awesome gan-inversion [Link](https://github.com/weihaox/awesome-gan-inversion)

Model_ZOO / pre-trained model(PGGAN,StyleGAN,StyleGAN2) [Link](https://github.com/genforce/genforce/blob/master/MODEL_ZOO.md)

A Survey on Generative Adversarial Networks : Variants, Applications, and Training

Background
-----------
|#|Subject|Pub|Year|
|:------:|---|:---:|:---:|
|1 |Autoencoder(AE)|||
|2 |Variational Autoencoder(VAE)|||
|3 |Generatrivve Adversarial Networks(GAN)|||
|4 | Vector Quantized Variational AutoEncoder-2(VQ-VAE-2)|||

Extented papers from GAN
------------------------
|#|Subject|Pub|Year|
|:------:|---|:---:|:---:|
|1 |Conditional Generative Adversarial Networks (CGAN)|arXiv|2014|
|2 |Deep Convolution Generative Adversarial Networks (DCGAN)|CoRR|2015|
|3 |Laplacian Generative Adversarial Networks (LapGAN) |NIPS|2015|
|4 |Information Maximizing Generative Adversarial Networks (InfoGAN) |NIPS|2016|
|5 |Energy-Based Generative Adversarial Networks (EBGAN)|ICLR|2016|
|6 |Wasserstein Generative Adversarial Networks (WGAN)|ICML|2017|
|7 |Boundary Equilibrium Generative Adversarial Networks (BEGAN)|CSLG|2017|
|8 |Progressive-Growing Generative Adversarial Networks (PGGAN)|ICLR|2018|
|9 |Big Generative Adversarial Networks (BigGAN) |ICLR|2019|
|10 |Style-Based Generator Architecture for Generative Adversarial Networks(StyleGAN)|IEEE|2019|


Applications
-------------------

### 1. Image domain
#### 1.1 Hnad-written Chinese characters generation
|#|Subject|Pub|Year|
|:------:|---|:---:|:---:|
|1 |Conditional Least Square GAN(LSCGAN)|||

#### 1.2 Anime character generation

#### 1.3 Image blending

#### 1.4 Image in-painting

#### 1.5 Face aging

#### 1.6 Text-to-image synthesis

#### 1.7 Human pose synthesis

#### 1.8 Stenographic applications

#### 1.9 Image manipulation applications

#### 1.10 Visual saliency prediction

#### 1.11 Object detection

#### 1.12 3D image synthesis

#### 1.13 Facial makeup transfer

#### 1.14 Facial landmark detection

#### 1.15 Image super-resolution

#### 1.16 Texture synthesis

#### 1.17 Sketch synthesis

#### 1.18 Image-to image translation(I2I)

#### 1.19 Face frontal view generation

### 2. Audio domain
#### 2.1 Language and Speech Synthesis
#### 2.2 Music generation
#### 2.3 Others sequential domain applications

### 3. Video domain
#### 3.1 Video applications
#### 3.2 Others video domain applications

### 4. GAN training
#### 4.1. Problems with training GAN
- Nash equilibrium
- Internal coveriate shift
- Mode collapse
- Vanishing gradient
- Lack of proper evaluation metrics

#### 4.2 Analysis of GAN training obstacles
#### 4.3 Techniques to improve GAN training
- Feature matching
- Unrolled GAN(UGAN)
- Mini-batch discrimination(MBD)
- Historical averaging(HA)
- Two time-scale update rule(TTUR)
- Hybrid model
- Self-Attention GAN(SAGAN)
- Relativistic GAN(RGAN)
- One-sided label smoothing
- Sampling GAN
- Proper optimizer
- Normalization
  BN,VBN,LN,WN,IN,GN,BIN,SN
- Add instance noise
- Train with labels
- Alternative cost functions
- Gradient penalty(GP)
- Cycle-consistency loss

#### 4.4 Performance analysis
