# Abstruct
- 이때까지 Image-to-image translation은 쌍이 있는 dataset에 대해서만 학습이 가능하였음.
- 실제로 많은 task에서는 pair 이미지 데이터셋이 존재하지 않음.
- 본 논문에서는 mapping network G : X -> Y / inverse mapping F : Y -> X 를 학습시켜 **unpaired training data에 대해서도 image-to-image가 가능하도록 하였다.**

- F(G(X)) ~ X 의 식이 만족하도록 cycle consistency loss를 도입하였음.

## 단점
- 결과물이 그렇게 좋지는 못함. 퀄리티
- 개선하는 방법이 연구되었고, StyleGAN이 나옴

# 1. Introduction
크게 다음을 다룬다.
> 1) image collection에서 특별한 특성을 capture 하는 방법  
> 2) paired training dataset이 없이도 이 특성을 다른 image collection으로 변환하는 방법


$G:X->Y$ 로 mapping 한 후, 생성된 이미지 $\hat{y} = G(x)$ 가 $y \epsilon Y$ 와 비슷하도록 학습을 하면 안된다.

> 대다수의 G가 하나의 $\hat{y}$ 로 mapping될 수 있어서 mode collapse에 빠질 수 있음

따라서 본 논문에서는 translation이 반드시 **Cycle consistent** 되어야만 한다는 특징을 추가하였음

> 영어를 독일어로 번역할 수 있으면, 독일어도 영어로 번역할 수 있어야 한다.

또한 $F(G(X)) \approx x, G(F(y)) \approx y$ 의 **cycle consistency loss**도 추가하였다.

# 2. Related Work
- Generative Adversarial networks(GANs)
- Image-to-image translation
- Unpaired Image-to-image Translation
- Cycle Consistency
- Neural Style Transfer

# 3.Formulation
## 3.1 Adversarial Losses
$
\begin{aligned}
\mathcal{L}_{\mathrm{GAN}}\left(G, D_{Y}, X, Y\right) &=\mathbb{E}_{y \sim p_{\text {data }}(y)}\left[\log D_{Y}(y)\right] \\
&+\mathbb{E}_{x \sim p_{\text {data }}(x)}\left[\log \left(1-D_{Y}(G(x))\right]\right.
\end{aligned}
$
- F에도 유사한 adversarial loss를 적용한다.

## 3.2 Cycle consistency loss
$
\begin{aligned}
\mathcal{L}_{\text {cyc }}(G, F) &=\mathbb{E}_{x \sim p_{\text {data }}(x)}\left[\|F(G(x))-x\|_{1}\right] \\
&+\mathbb{E}_{y \sim p_{\text {data }}(y)}\left[\|G(F(y))-y\|_{1}\right]
\end{aligned}
$

- G와 F가 잘 matching 되도록 학습시키는 loss. 단순히 adversarial loss만 사용하면 Mode collapse 문제가 발생할 수 있다.
- unpaired dataset에 대해서도 data들이 잘 mapping 되도록 cycle consistency loss(L1 loss)를 추가적으로 학습한다.
- 한쪽 방향 mapping만 학습하면 mode collapse 발생