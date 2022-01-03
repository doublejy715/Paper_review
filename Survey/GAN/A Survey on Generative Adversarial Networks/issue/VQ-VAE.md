[VQ-VAE-2 paper review](https://greeksharifa.github.io/discrete%20representation/2021/11/26/VQVAE2/)

### Abstract
- 단순한 feed-forward encoder와 decoder를 사용하였음
- GAN과 비슷한 성능을 보이면서 mode collapsing 같은 GAN의 문제를 겪지 않도록 한다.
### 1. Introduction
- GAN이 minimax 방식을 사용하여 현실적인 이미지를 생성하였지만 실제 세상의 이미지 분포를 그대로 따라가지 못함
- 계층적 구조의 latent map을 사용하여 SOTA GAN과 비슷한 수준의 이미지 생성 결과를 보여줌.