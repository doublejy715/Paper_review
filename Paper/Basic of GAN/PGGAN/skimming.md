- layer를 점진적으로 쌓아 고해상도의 이미지를 생성하는 model이다.
- 하나의 training 기법이라 보면 좋을듯.

# 1. Introduction
- Autoregressive model : sharp images, slow to evalutate, no latent space
- VAE : fast to train, blurry images
- GANS : sharp image, low resolution, limited variation, unstabble training

# 2. Challenge
GAN에서 고해상도 이미지를 생성하기 위해서 해결해야 할 문제점들
1. generated distribution과 training distribution들이 겹치는 부분(overlap)이 적다면, 이 분포들 간의 거리를 측정할 때 gradient를 random한 방향을 가리킬 수 있다.
    - 분포 간 거리를 측정하는 여러 방법이 있음
    - 최근에는 Least squares나 Wasserstein distance 등의 metric을 사용

2. mode collapse : generated distribution이 실제 데이터의 분포를 모두 커버하지 못하고 다양성을 잃어버리는 현상. 하나의 데이터만 생성하게 되는 경우

3. High-resolution의 image를 생성할 수록, 가짜 이미지라고 판별하기 쉬워진다.

4. High-resolution의 이미지를 만들기 위해서는 memory constraint 때문에 더 작은 minibatch를 사용해야 하고, training stability 역시 떨어진다.

> 이러한 문제점을 해결하기 위해서 Generator와 Discriminator를 점진적으로 학습시킨다. 만들기 쉬운 low-resolution 부터 시작해서 새로운 layer를 조금씩 추가하고 higher-resolution의 detail들을 생성한다.

# 3. Progressive Growing of GANs
- 점차 layer를 추가하면서 high-resolution을 학습하게된다.
- discriminator의 구조는 generator와 대칭 형태를 이루고 있다.

## 장점
1. Stable
- low-resolution의 이미지를 학습하면 class information도 적고 mode도 몇 없기 때문에 안정적이다. -> 학습이 잘 된다.
2. Reduced training time
- PGGAN은 lower resolution에서 비교하여 학습을 하기 때문에 학습속도가 2~6배나 빨라진다.
- 전 resolution에서 비교하여 학습하였기 때문에 잔차학습처럼 학습속도가 빨라진다 생각한다.

## Fading in higher resolution layers
G와 D의 resolution을 upsampling할 때, PGGAN은 새로운 layer에 "fade in" 하는 방식을 사용한다.

### 순서
#### (1) stabilize
(16x16x512) -> to RGB -> (16x16x1) -> from RGB -> 16x16x512
- WHY?

#### (2) fade in method
layer를 추가할 때 바로 추가하는 것이 아니라 residual block을 적용하는 중간 단계를 거친다.
- 처음 $\alpha$ 를 0으로 초기화 해주고 학습을 진행할 수록 $\alpha$ 를 1로 증가시켜가며 큰 해상도에 대해 생성한 값을 불러오도록 한다.

#### (3) stabilize
resolution을 높이면서(32x32) 학습을 진행할 때, 기존에 학습했던 이미지에 대한 정보(16x16)을 잊어버릴 수도 있으니까 residual block을 이용하여 한번 더 더해주는 것이다. 해상도를 줄이는 경우도 마찬가지의 이유로 Fade in을 해준다.


'''{math}
test^{x}
'''
