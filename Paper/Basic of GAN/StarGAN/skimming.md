# Abstruct
 하나의 Generator와 Discriminator로 다양한 dataset에 대해 image-to-image translation을 하는 starGAN model에 대해 살펴본다.

# 1. Introduction

기존 연구들은 다양한 domain에 대해 image translation 하는 것이 매우 비효율 적이었다.
generator들은 2개의 domain만을 사용할 수 있었다. 그렇기에 multi-domain을 이용한 모델을 만들고 싶을 때 여러 generator를 만들어야 한다.(k개의 domain을 이용하기 위해서는 k(k-1)의 generator가 필요)

StarGAN은 기존 모델의 문제점을 개선하여 한 모델이 여러 domain을 이용하도록 함.
> StarGAN은 하나의 generator 만으로 여러 domain을 mapping 가능하므로 효율적인 학습이 가능하다.  
> 모든 domain의 정보(label)들을 control할 수 있도록 **mask vector**를 사용한다.

# 2. Related Work
## Generated Adversarial Networks
- GAN
## Conditionals GANs
- CGAN
- Generative Adversarial Text to Image Synthesis

## Image-to-Image Translation
- Pix2Pix
- SPADE
- CycleGAN
- CoGAN
- DiscoGAN

# 3. Star Generative Adversarial Networks
## 3.1 Multi-Domain Image-to-Image Translation
논문의 목적은 한 Generator G에 여러 domain을 mapping 하는 것이다.

### Training Discriminator
실제 / 가짜 이미지를 판별하고, 실제 이미지는 대응되는 domain으로 분류한다.
**ACGAN과 유사하게 Auxiliary Classifier**를 사용한다.
- Auxiliary Classifier는 하나의 discriminator로 여러 domain을 control한다.
> **THINK**  
> 여러 요소를 한번에 판별할 수 있다?  
> fake or real / label

### Training Generator
original image와 target domain을 input으로 넣어주면 Generator는 fake image를 생성한다.
fake image는 original image를 target domain으로 보내면 생성되는 가짜 이미지이다.

> target domain을 image와 concatrate하기 위해서 one-hot label을 여러개 복제하여 image size와 동일한 사이즈를 가질 수 있도록 복제한다.

fake image를 original domain과 concatrate하여 Generator에 넣어주면 원래 domain 이미지(original image)를 생성하도록 한다.

생성된 fake image는 Discriminator에 넣어줘서 진짜인지 가짜인지 구분과 어떤 domain에 존재하는 사진인지 판별하게 된다.

## 3.2 Loss
### Adversairal Loss
$
\begin{aligned}
\mathcal{L}_{a d v}=& \mathbb{E}_{x}\left[\log D_{s r c}(x)\right]+\mathbb{E}_{x, c}\left[\log \left(1-D_{s r c}(G(x, c))\right)\right]
\end{aligned}
$

### Domain Classification Loss
domain classification loss를 D의 최상단에 auxiliary classifier를 추가하였음.

**In real image**
original domain c'로 real image x를 분류하도록 한다.
$
\mathcal{L}_{c l s}^{r}=\mathbb{E}_{x, c^{\prime}}\left[-\log D_{c l s}\left(c^{\prime} \mid x\right)\right]
$

**In fake image**
target domain c에 따라 이미지를 생성하도록 이 loss function을 minimize하는  방향으로 훈련한다.
$
\mathcal{L}_{c l s}^{f}=\mathbb{E}_{x, c}\left[-\log D_{c l s}(c \mid G(x, c))\right]
$

### Reconstruction Loss
위 두 Loss만 사용하면 domain을 변화시키면서 attirbute를 변화시킬 때 input image의 content가 훼손될 수 있음. 변화시킬때 원본 이미지의 특성이 남을 수 있도록 cycle-consistency loss를 사용한다.

$
\mathcal{L}_{r e c}=\mathbb{E}_{x, c, c^{\prime}}\left[\left\|x-G\left(G(x, c), c^{\prime}\right)\right\|_{1}\right]
$

> **THINK**  
> generator의 bottle neck구간에는 모든 domain에도 공통되는 input image의 특성이 저장되나????

## 3.3 Training with Multiple Datasets
서로 다른 domain을 가진 dataset을 통합할 수 있음. 그러나 각 dataset마다 다른 Label 정보를 가지고 있거나 없는 경우가 발생한다. 다음 같은 문제가 발생할 수 있음.

(CelebA의 얼굴을 웃는 표정을 변화시킨 후 다시 이를 슬픈 표정으로 복원시키려고 할 때, 기존의 CelebA dataset은 머리색, 주근깨 등의 label만 있으므로 슬픈얼굴 c′에 대해 복원하기가 어려움)

> **THINK**  
> 모든 dataset을 통합한 label이 있어야 한다. 그러나 cost가 많이 들지도..?

### Mask Vector
이를 위해서 Mask vector를 도입하여 잘 모르는 label에 대해서는 무시하도록 하였다.(one hot vecotr에서 0으로 기록한다.)

label이 있는 dataset만 이용하고 없으면 그냥 m을 이용
$
\tilde{c}=\left[c_{1}, \ldots, c_{n}, m\right]
$

## 3.4  Training Strategy

Discriminator는 CelebA와 RaFD를 번갈아가며 학습을 해서 두 dataset의 feature들을 골고루 학습하도록 한다. 반면, Generator는 모든 dataset에 대한 label을 제어하도록 학습한다.

# 4. Implementation
## Improved GAN Training

학습을 안정화하고, 더 좋은 quality의 이미지를 만들기 위해 gradient penalty($\lambda_{g p}=10$)와 Wasserstein GAN의 objective function을 사용하였다.

$$
\begin{aligned}
\mathcal{L}_{a d v}=& \mathbb{E}_{x}\left[D_{s r c}(x)\right]-\mathbb{E}_{x, c}\left[D_{s r c}(G(x, c))\right] \\
&-\lambda_{g p} \mathbb{E}_{\hat{x}}\left[\left(\left\|\nabla_{\hat{x}} D_{s r c}(\hat{x})\right\|_{2}-1\right)^{2}\right]
\end{aligned}
$$

## Network ArchitecturePermalink
CycleGAN의 architecture를 baseline으로 사용한다.

