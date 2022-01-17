# 1. Introduction
## 의의
- GAN이 불안정하게 training 되었음.
- 종종 generator의 무의미한 output을 만들어 내는 모습을 보임

- GAN에 Convolutional layer를 적용하여 training을 안정화 하였음.

# 2. Architecture
- 일반적인 CNN을 사용한다.
## use Conv layer
- Transposed Conv 사용한다.
- max-pooling function을 없애고, strided conv layer를 사용하였다.
    - generator : fractional strided convolutions 사용(transposed Conv)
    - discriminator : strided convolutions 사용


[transposed Conv 설명](https://zzsza.github.io/data/2018/06/25/upsampling-with-transposed-convolution/)

> 최근 들어서는 DCGAN의 transposed Conv보다는 Resized Conv를 쓰는 추세라 한다.


## Global Average Pooling(GAP)
- fully connected layer는 CNN과 비교하여 더 많은 parameter를 가진다. 이로 인해서 연산도 오래 걸리면 feature의 위치 정보들도 사라지는 단점이 있음.
- 더 깊은 네트워크를 위해서 fully connected layer를 삭제함. 대신 GAP 사용.

[GAP 란?](https://jetsonaicar.tistory.com/16)


## Batch Normalization
- Mode Collapsing의 해결 방법이다.
- activation 결과값들이 나오면 결과값들을 unit gaussian으로 만들어주기 위해 사용.

[Training Neural networks](https://happy-jihye.github.io/cs231n/cs231n-6/#4-batch-normalization)

## Activation Function
- output 빼고 generator의 모든 layer에 ReLu activation을 적용하였음
- discriminator의 모든 layer에 LeakyReLU activation을 적용하였음