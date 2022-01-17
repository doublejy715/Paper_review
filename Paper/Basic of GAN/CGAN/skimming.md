# 1. Introduction
- 기존의 GAN에 conditional information(class label,image,text descriptions)를 추가하였다.

# 2. Conditional Adversarial Nets
- latent vactor z를 one-hot vector로 embedding한 후, 이를 class label y와 concatenation 해줬다.

# 3. Experiment Results
## 3.1 Unimodal
- dataset : MNIST
- z : 100차원 noise prior

# 4. Code
## Discriminator
- valid : input image shape와 같고, 내용은 1로 채운다.
- discriminator(fake_imgs),valid : 