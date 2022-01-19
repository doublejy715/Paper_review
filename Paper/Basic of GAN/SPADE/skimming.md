# 1. Introduction
이전까지는 Semantic Image to photorealistic image task에서 Convolution, normalization, nonlinearity layer로 구정된 deep network를 사용하였음.

위 방식을 사용하면 normalization 과정에서 semantic 정보가 사라지는 문제가 발생한다.

> **THINK**  
> normalization은 nonlinearity layer의 activation input 범위에 들어갈 수 있도록 neural node 결과를 평균과 분산을 조절해 준다고 알고 있음.
> 한편 style 정보는 평균과 분산에 담겨 있다고 함(???)
> 뭔가 normalization을 통해서 평균과 분산을 조절하면 기존의 semantic 정보를 잃어버릴 만함.
> [나중 참조할 설명](https://re-chill.tistory.com/entry/I2I-CondNorm)

이 문제를 해결하기 위해 spatially-adaptive normalization을 제안한다.

# 2. Related Word
## 2.1 Conditional image synthesis
이미지를 생성할 때 conditional information을 주면 **더 빠르고 현실적인** 이미지가 생성된다.

## 2.2 Unconditional normalization layers
-Batch Norm
Channel에 대해서 