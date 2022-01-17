# 1. Introduction
GAN - minimax two player game
- GAN은 주어진 입력 데이터와 유사한 데이터를 생성하는 것을 목표로 한다.
- 두 모델이 경쟁하며 성능을 높여나간다.
    - Generator : 가짜를 잘 생성하도록 학습한다.
    - Discriminator : 가짜와 진짜를 잘 분간하도록 학습한다.

# 2. Adversarial Nets
> G는 그럴싸한 생성 이미지를 만들어서 D를 속이려고 하고, D는 진짜 이미지를 찾아내도록 적대적인 network를 구성한다.
## Generator
- Goal : data x의 distribution 학습

## Discriminator
- Fake image와 Real image를 따로 input으로 받은 후 discriminator를 거쳐 0과 1사이의 값을 출력한다.

# 3. Theoretical Results
- Generator가 진짜라고 판단하는 확률분포가 존재함
- Discriminator가 만들어내는 이미지의 확률분포가 존재함

- 학습 초기에는 Generator와 Discriminator의 확률분포가 서로 일치하지 않음.
- 학습이 진행될수록 generator의 생성 확률분포와 Discriminator의 진실 판단분포의 확률분포가 일치된다.