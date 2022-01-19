# Abstruct
- 대표적인 image-to-image를 수행하는 model
- input에서 output image로 mapping하는 Conditional Adversarial Networks
- mapping network 훈련에 사용되는 loss function 중요

# 1. Instruction
- CNN은 loss값을 최소화하도록 최적화된 network이기 때문에 loss function을 잘 디자인 해야 좋은 performance를 보인다.
- CNN은 predict와 ground truth의 pixel들 간의 Euclidean distance를 최소화 하도록 훈련이 되어서 생성된 이미지에 blurry한 결과를 보인다.(단점)

# 2. Related work
## 2.1 Structured losses for image modeling
- Q. structured losses?

## 2.2 Conditional GANs
- pix2pix에서는 Conditional GAN 이용

# 3. Method
> pix2pix에서는 generator로 U-Net 구조를, discriminator로는 PatchGAN을 사용한다.  
> U-Net구조는 skip connection을 통해 이미지의 맥락을 보존하는데 효과적이다.  

## 3.1 Objective
### cGAN Loss
- real 학습
input x와 GT 이미지 pair를 Depth-wise concatenate한다.  
discriminator가 real로 판단하도록 한다.

- fake 학습
input x와 생성된 이미지를 Depth-wise concatenate한다.  
discriminator가 fake로 판단하도록 한다.

- noise vector(z)를 사용하지 않음
대신 x라는 input image만 generator에 입력으로 들어간다.
(실험을 통해 z가 학습에 영향을 미치지 않음을 보임)

### L1 loss
- low frequency한 부분을 살리기 위해서 L1 loss가 사용된다.
- 생성된 이미지와 대응되는 진짜 이미지와의 거리를 loss에 추가
- 생성된 이미지가 진짜 이미지와 비슷할 수 있도록 학습

> low frequency한 부분을 학습함으로써 이미지 전체 구도를 비슷하게 생성하도록 유도한다.  

## 3.2 Network architectures
convolution-batchNorm-ReLU
- DCGAN의 G와 D를 baseline으로 사용

### Generator U-Net 구조 인용
input의 정보를 bottle netck 영역 이후에도 유지하는 것이 중요하다. 이를 위해서 skip connection을 추가한다.

### PatchGAN
high-frequency에 대해서 진짜와 비슷한 이미지를 생성해 주도록 하는 discriminator를 소개한다.

생성된 이미지의 일부(Patch/ NxN size)를 사용해서 몇번의 Conv layer를 거쳐 해당 patch에 대한 score(real or fake)를 뽑아낸다.

Discriminator에는 input으로 생성된 이미지의 일부만 들어가게 된다.

> **THINK**  
> 이미지의 일부를 사용할때 Patch를 grid로 나눠서 중복되는 영역이 존재하지 않는지, Conv의 slide 형식으로 나눠 중복되는 영역이 존재하는지는 잘 모르겠다.

해당 방식은 discriminator를 좀 더 약하게 만들어 준다고 볼 수 있다.

70x70 PatchGAN을 사용했을 때 가장 좋은 FCN-score를 얻었다.


> **THINK**  
> 아마 더 자세한 부분을 봐야하므로, 기존 Discriminator의 학습해야할 난이도 보다 더욱 어려워 졌기 때문에 아닐까 싶다.
