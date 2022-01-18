- ACGAN은 CGAN 이후에 나온 논문이다.
- Discriminator가 fake / real 판별하는 기능 외에 classification도 같이 학습한다.

# 1. Introduction
- 약 1000종류의 128x128 size 이미지를 생성해 내었음을 보인다.
- 생성된 이미지가 얼마나 정확하게 생성하는지 측정한다.(Section 4.1)
- perceptual variability와 'collapsing' 현상을 빠르고 쉽게 측정한다.(Section 4.2)
- 많은 수의 class를 생성하기 위한 해결책을 제시한다.(Section 4.6)
- 2016년 기준 최신 inception score metric을 소개한다.(Section 4.4)

# 2. AC-GANs(Auxiliaty Classifier GAN)
## Generator & Discriminator
- Generator
noise를 sampling할 때 class label도 같이 generator에 넣어준다.
$$
X_{fake} = G(c,z)
$$
- Discriminator
source와 class label의 확률 분포를 바탕으로 학습한다.
$$
P(S|X),P(C|X) = D(X)
$$

## Object function
- log likelihood of the correct source $L_{s}$
$$
L_{S}=E\left[\log P\left(S=\text { real } \mid X_{\text {real }}\right)\right]+E\left[\log P\left(S=\text { fake } \mid X_{\text {fake }}\right)\right]
$$
- log likelihood of the correct class $L_{c}$
$$
L_{C}=E\left[\log P\left(C=c \mid X_{\text {real }}\right)\right]+E\left[\log P\left(C=c \mid X_{\text {fake }}\right)\right]
$$
> D는 $L_{s} + L_{c}$를, G는 $L_{c}-L_{s}$를 최대화 하는 방향으로 학습한다.  
> real / fake 부분을 판별하는 $L_{s}$는 D와 G가 서로 적대적으로 학습  
> classification 부분은 적대적으로 학습하지 않는다.  

# 3. Propose
## MS-SSIM metric
- image discriminability를 측정하기 위한 metric