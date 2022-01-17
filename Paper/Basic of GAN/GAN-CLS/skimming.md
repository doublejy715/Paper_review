# 1. Introduction
- text로 image를 생성하는 Generative Adversarial Text to Image Synthesis model을 소개한다.
- word나 charactor를 image pixel로 mapping한다.
    - text에서 중요한 visual details를 추출
    - 추출된 정보로부터 진짜같은 이미지를 합성

# 2. Related Work
- Multimodal Learning
- Deep convolution decoder network
- GAN

# 3. Background
## 3.1 Generative Adversarial Networks
$$
\begin{aligned}
\min _{G} \max _{D} V(D, G)=& \mathbb{E}_{x \sim p_{\text {data }}(x)}[\log D(x)]+ \mathbb{E}_{x \sim p_{z}(z)}[\log (1-D(G(z)))]
\end{aligned}
$$

## 3.2 Deep symmetric structed joint embedding
- text에서 visually-discriminative vector를 얻는 방식으로 DeepConvolutional and Recurrent Text Encoder를 사용함[Link](https://arxiv.org/abs/1605.05395)
- 

# 4. Method
## Generator
1. text encoder $\verphi$ 를 사용해서 text query t를 encoding한다.
2. encoding 결과 값 $\verphi(t)$ 를 FC layer에 넣어 compress한 후 Leaky-ReLU를 사용해서 128-dim 의 작은 차원으로 compression 한다.
3. 이 값을 noise vector z와 concate한 후 deconvolusional network를 통해 generate image를 얻는다.

## Discriminator
1. stride-2 convolution layer와 BN기법, leaky ReLU function을 이용하였다.
2. 1번의 과정을 4x4 conv layer가 될 때까지 반복
3. compressing된 embedding vector $\verphi$ 를 여러개 복사해서 conv layer뒤에 이어붙인다.
4. 1x1 conv layer가 되도록 연산을 한 수 final score를 얻는다.