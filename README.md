Paper Review
============

Words
-----

[Dictionary Link](https://github.com/doublejy715/Paper_review/issues/1)

Survey Github Homepage
----------------------

awesome gan-inversion [Link](https://github.com/weihaox/awesome-gan-inversion)

Model_ZOO / pre-trained model(PGGAN,StyleGAN,StyleGAN2) [Link](https://github.com/genforce/genforce/blob/master/MODEL_ZOO.md)

Thesis reading orther
----------------------
[논문 읽기 시작](https://gradschoolstory.net/tag/%EB%85%BC%EB%AC%B8-%EC%9D%BD%EA%B8%B0/)  
[1. Link](https://media-ai.tistory.com/7)  
[2. Link](https://karl6885.github.io/data_science/2020/06/24/Andrew-Ng-%EB%85%BC%EB%AC%B8-%EC%9D%BD%EB%8A%94-%EB%B2%95-ML-%EC%BB%A4%EB%A6%AC%EC%96%B4-%EC%A1%B0%EC%96%B8/)  

### Skimming
0. 여러번 읽고, 읽는 범위를 늘려나간다.  
1. title, abstract, figure를 먼저 보기  
  - figure : 설명 부분을 읽는다.
  - 논문의 기본적인 컨셉과 아이디어를 파악한다.
> 노트를 통해서 title, abstract, figure 부분의 중요한 부분을 밑줄친다.
> 요약 부분을 발최하고 그래프로 만들어 놓는다.
2. introduction, conclusion, figure 읽기  
  - introduction, conclusion : 왜 자신의 논문이 게재 승인되어야 하는지를 파악한다.
  - 관련된 다른 연구에 대한 부분은 가능하면 생략
> 노트를 이용해서 해당 부분에서 승인 이유, 논문 내용 요약 부분을 찾아낸다.
> (1),(2) issue에 기록한다.
> 모르는 단어를 기록하고 설명을 덧붙인다.
3. 수식은 일단 생략
> skimming issue를 작성한다.

### Reading
4. 이해가 안되는 부분은 뺴고 전체적으로 읽기
  - 처음 볼 때 완벽하게 이해하지 못해도 된다.
> github issue로 전제적인 내용 '해석' 한다.
> 너무 어려우면 내용을 패스한다.(노트에 빨강색으로 highlight한다.)
5. 스스로 질문의 시간을 가진다.  
  5.1 저자가 뭘 해내고 싶어했는가?  
  5.2 이 연구의 접근에서 중요한 요소는 무엇인가?  
  5.3 당신은 스스로 이 논문을 이용할 수 있는가?  
  5.4 당신이 참고하고 싶은 다른 레퍼런스에는 어떤 것이 있는가?  
> summary issue를 작성한다. 마지막에 요약을 추가한다.
### 더 자세히 이해하기
1. 수식 이해하기
  - 밑바닥부터 직접 연산해 보기.
2. 코드 연습하기
  - 오픈소스를 다운받아서 실행해 본다.
  - 밑바닥부터 직접 구현해본다.

Investigation About...
---------------
## 1. Arcface
[Link 1.](https://tech.kakaoenterprise.com/63)  
- 얼굴 인식 단계별 설명
- 소프트맥스 손실 함수
- 거리기반 손실 함수
- 앵귤러 마진 기반 손실 함수

[Link 2. Arcface paper review](https://soobarkbar.tistory.com/60)
- 논문 전체적인 설명

[Link 3. Arcface logic 1](https://butter-shower.tistory.com/237)  
[Link 4. Arcface logic 2](https://hongl.tistory.com/189)  

## 2. Face Super Resolution
- [Link 0. Survey](https://github.com/topics/face-super-resolution)
- [Link 1. Face-Super-Resolution](https://github.com/ewrfcas/Face-Super-Resolution)
- [Link 2. SPARNet: Learning Spatial Attention for Face Super-Resolution in PyTorch](https://github.com/chaofengc/Face-SPARNet)
- [Link 3. Progressive Face Super-Resolution](https://github.com/DeokyunKim/Progressive-Face-Super-Resolution)

Papers
---------------

No | Title | Conference | Year | Link | Code | Skimming | Summary |  
------------ | ------------- |----------|----------|----------|----------|----------|----------|  
1 | Analyzing and Improving the Image Quality of StyleGAN(StyleGAN2) |CVPR |2019 |[arXiv](https://arxiv.org/abs/1912.04958)|[Code](https://github.com/NVlabs/stylegan2)||[Summary](https://github.com/doublejy715/Paper_review/issues/3)|  
2 | Training Generative Adversarial Networks with Limited Data(StyleGAN2-ada) | CVPR | 2020 | [arXiv](https://arxiv.org/abs/2006.06676v1)|[Code](https://github.com/NVlabs/stylegan2-ada-pytorch)||[Summary]() |  
3 | A Style-Based Generator Architecture for Generative Adversarial Networks(StyleGAN) | CVPR | 2019 | [arXiv](https://arxiv.org/abs/1812.04948) | [Code](https://github.com/NVlabs/stylegan) || [Summary](https://github.com/doublejy715/Paper_review/issues/2)|  
4 | Image2StyleGAN: How to Embed Images Into the StyleGAN Latent Space? | CVPR | 2019 | [arXiv](https://arxiv.org/abs/1904.03189) | None || [Summary](https://github.com/doublejy715/Paper_review/issues/4) |
5 | Arbitrary Style Transfer in Real-time with Adaptive Instance Normalization(AdaIN) | CVPR | 2017 | [arXiv](https://arxiv.org/abs/1703.06868) | [Code](https://github.com/xunhuang1995/AdaIN-style) || [Summary](https://github.com/doublejy715/Paper_review/issues/5) |
7 | InterFaceGAN: Interpreting the Disentangled Face Representation Learned by GANs | CVPR | 2020 | [arXiv](https://arxiv.org/abs/2005.09635) | [Code](https://github.com/genforce/interfacegan) | |[Summary](https://github.com/doublejy715/Paper_review/issues/7)|
8 | Fine-Tuning StyleGAN2 For Cartoon Face Generation | CVPR | 2021 | [arXiv](https://arxiv.org/abs/2106.12445) | [Code](https://github.com/happy-jihye/Cartoon-StyleGan2) ||[Summary](https://github.com/doublejy715/Paper_review/issues/8) |
9 | Encoding in Style: a StyleGAN Encoder for Image-to-Image Translation(pSp) | CVPR | 2020 | [arXiv](https://arxiv.org/abs/2008.00951v1) | [Code](https://github.com/eladrich/pixel2style2pixel) | |[Summary](https://github.com/doublejy715/Paper_review/issues/10) |
10 | Animating Arbitrary Objects via Deep Motion Transfer | CVPR | 2019 | [arXiv](https://arxiv.org/abs/1812.08861) | [Code](https://github.com/AliaksandrSiarohin/monkey-net) || [Summary](https://github.com/doublejy715/Paper_review/issues/11) |
11 | First Order Motion Model for Image Animation | CVPR | 2020 | [arXiv](https://arxiv.org/abs/2003.00196)| [Code](https://github.com/AliaksandrSiarohin/first-order-model) | |[Summary](https://github.com/doublejy715/Paper_review/issues/12) |
12 | Controllable Person Image Synthesis with Attribute-Decomposed GAN(ADGAN) | CVPR | 2020 | [arXiv](https://arxiv.org/abs/2003.12267)| [Code](https://github.com/menyifang/ADGAN) | |[Summary](https://github.com/doublejy715/Paper_review/issues/13) |
13 | StyleFlow: Attribute-conditioned Exploration of StyleGAN-Generated Images using Conditional Continuous Normalizing Flows | CVPR | 2020 | [arXiv](https://arxiv.org/abs/2008.02401) | [Code](https://github.com/RameenAbdal/StyleFlow) || [Summary](https://github.com/doublejy715/Paper_review/issues/14) |
14 | Closed-Form Factorization of Latent Semantics in GANs | CVPR | 2019 | [arXiv](https://arxiv.org/abs/2007.06600v1) | [Code](https://paperswithcode.com/paper/closed-form-factorization-of-latent-semantics) | |[Summary](https://github.com/doublejy715/Paper_review/issues/16) |
15 | StyleSpace Analysis : Disentangled Controls for StyleGAN Image Generation ✅ | CVPR | 2020 |[arXiv](https://arxiv.org/abs/2011.12799v1)| [Code](https://github.com/betterze/StyleSpace) | |[Summary](https://github.com/doublejy715/Paper_review/issues/17) |
16 | StyleMapGAN: Exploiting Spatial Dimensions of Latent in GAN for Real-time Image Editing | CVPR | 2021 | [arXiv](https://arxiv.org/abs/2104.14754) | [Code](https://github.com/naver-ai/StyleMapGAN) || [Summary](https://github.com/doublejy715/Paper_review/issues/18) |
17 | Freeze the Discriminator: a Simple Baseline for Fine-Tuning GANs V1 | CVPR | 2020 | [arXiv](https://arxiv.org/abs/2002.10964v1)| [Code](https://github.com/sangwoomo/freezeD)||[Summary](https://github.com/doublejy715/Paper_review/issues/19)|
18 | pix2pix : Image-to-Image Translation with Conditional Adversarial Networks | CVPR | 2016 | [arXiv](https://arxiv.org/abs/1611.07004v1) | [Code](https://github.com/phillipi/pix2pix) | |[Summary](https://github.com/doublejy715/Paper_review/issues/22) |
19 | e4e : Designing an Encoder for StyleGAN Image Manipulation | CVPR | 2021 | [arXiv](https://arxiv.org/abs/2102.02766) | [Code](https://github.com/omertov/encoder4editing) | [Skimming]() | [Summary]() |
20 | In-domain gan inversion for real image editing | CVPR | 2020 | [arXiv](https://arxiv.org/abs/2004.00049) | [Code](https://github.com/genforce/idinvert)| [Skimming](https://github.com/doublejy715/Paper_review/issues/24)| [Summary]() |
21 | StyleClip : Text-Driven Manipulation of StyleGAN Imagery | CVPR | 2021 | [arXiv](https://arxiv.org/abs/2103.17249) | [Code](https://github.com/orpatashnik/StyleCLIP)| [Skimming](https://github.com/doublejy715/Paper_review/issues/25)| [Summary](https://github.com/doublejy715/Paper_review/issues/26) |

To Do List
------------
No | Title | Conference | Year | Link | Code | Skimming | Summary |  
------------ | ------------- |----------|----------|----------|----------|----------|----------|  
1 | Image Style Transfer Using Convolutional Neural Network | CVPR, IEEE | 2016 | [IEEE](https://ieeexplore.ieee.org/document/7780634) | [Practice](https://github.com/ShaharAssenheim/Image-Style-Transfer-Using-Convolutional-Neural-Network) || [Summary](https://github.com/doublejy715/Paper_review/issues/6)|
2 | StyleRig : Rigging stylegan for 3d control over portrait images | CVPR | 2020 | [arXiv](https://arxiv.org/abs/2004.00121) | None || [summary]() |
3 | Ganspace : Discovering interpretable gan controls | CVPR | 2020 | [arXiv](https://arxiv.org/abs/2004.02546) | [Code](https://github.com/harskish/ganspace)| | [Summary]() |
4 | In-domain gan inversion for real image editing | CVPR | 2020 | [arXiv](https://arxiv.org/abs/2004.00049) | [Code](https://github.com/genforce/idinvert)| | [Summary]() |
5 | BicycleGAN : Toward Multimodal Image-to-Image Translation | CVPR | 2017 | [arXiv](https://arxiv.org/abs/1711.11586) | [Code](https://github.com/junyanz/BicycleGAN) | |[Summary]() |
6 | MaskGAN : Batter Text Generation Via Filling In the _____ | ICLR | 2018 | [arXiv](https://arxiv.org/abs/1801.07736v1) | None | |[Summary]() |
7 | GANspace |  |  | |  |  ||
8 | PGGAN |  |  | |  |  ||
9 | BigGAN |  |  | |  |  ||
10 | SPADE : Semantic Image Synthesis with Spatially-Adaptive Normalization | CVPR | 2019 | [arXiv](https://arxiv.org/abs/1903.07291) | [Code](https://github.com/NVlabs/SPADE) || [Summary](https://github.com/doublejy715/Paper_review/issues/21) |
11 | Interpreting the latent space of gans for semantic face editing | CVPR | 2020 | [arXiv](https://arxiv.org/abs/1907.10786)| None | | [Summary](https://github.com/doublejy715/Paper_review/issues/20) |
12 | CycleGAN : Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks | CVPR | 2017 | [arXiv](https://arxiv.org/abs/1703.10593v1) | [Code-pytorch](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix) || [Summary](https://github.com/doublejy715/Paper_review/issues/23)
23 | pix2pixHD : High-Resolution Image Synthesis and Semantic Manipulation with Conditional GANs | CVPR | 2017 | [arXiv](https://arxiv.org/abs/1711.11585v1) | [Code](https://github.com/NVIDIA/pix2pixHD) | |[Summary]() |
