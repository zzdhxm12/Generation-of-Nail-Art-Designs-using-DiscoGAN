# Generation-of-Nail-Art-Designs-using-DiscoGAN

사용자의 패션 아이템에 적합한 네일 디자인을 자동으로 생성 및 추천하기 위한 DiscoGAN 기반의 네일아트 디자인 시스템을 제안한다. 또한, 핸드백 및 신발으로부터 네일아트 디자인을 생성하기 위한 실험 결과로부터 제안하는 기법의 가능성을 제시한다.


## Prerequisites
* Python 2.7
* PyTorch
* Numpy/Scipy/Pandas
* Progressbar
* OpenCV
* Ubuntu 16.04
* Cuda 8.0

## Dataset
* 네일 디자인 Data (약 1000개)

![image](https://user-images.githubusercontent.com/53864655/71340605-add79700-259a-11ea-8d6d-6c8bf3ce5973.png)
* 액세서리(가방/신발) Data (약 70만개)

![image](https://user-images.githubusercontent.com/53864655/71340653-db244500-259a-11ea-89b1-2d7f772e3539.png)

가방 dataset 다운로드 

```
$ python ./datasets/download.py edges2handbags
```

신발 dataset 다운로드 

```
$ python ./datasets/download.py edges2shoes
```



## Model - DiscoGAN
### Introduction
2014년에 이안 굿펠로우에 의해 발표된 GAN(Generative Adversarial Networks)는 Generator와 Discriminator로 구성되며 Generator는 특정 도메인의 샘플을 생성하고 Discriminator는 샘플이 Generator로부터 생성된 데이터인지 실제 샘플인지를 판별한다. Generator와 Discriminator는 이와 같은 과정을 통하여 학습하며 상호간에 성능을 향상시킨다. 

이 연구에서는 SK T-Brain에서 발표되서 인정받고 있는 Learning to Discover Cross-Domain Relations with Generative Adversarial Networks(DiscoGAN)을 사용하였다. DiscoGAN은 이전에 다른 모델들과 달리, 우리는 그 어떤 라벨도 없는 두 개의 도메인 데이터 셋을 pre-training없이 train한다. 또한, 서로 다른 두 도메인간의 이미지 스타일 전이를 위한 GAN 기반의 학습 기법으로 Training Data가 unpaired dataset이라도 학습이 가능하며 간단한 네트워크 구조를 사용한다. 

### Architecture
![image](https://user-images.githubusercontent.com/53864655/71340915-a06edc80-259b-11ea-85b2-f72aa106ffaf.png)

**1. 이미지 수집&전처리**

웹 크롤러를 통하여 네일아트 이미지를 수집한 뒤 이미지 전처리(세그멘테이션, edge detection 등)를 수행한다. 

**2. DiscoGAN Model 학습**

각 도메인 이미지들과 DiscoGAN을 바탕으로 이미지 생성 및 복원을 통한 상호 관계성 학습을 수행한다. 

**3. 이미지 후처리**

생성된 네일아트 이미지의 결과에 대해 필터 적용, 색감 및 모양 보정 등의 후처리 과정을 통하여 네일아트의 분위기를 강조하는 효과를 기대할 수 있다.


## Result

![image](https://user-images.githubusercontent.com/53864655/71340062-ebd3bb80-2598-11ea-86f3-f633500d8b41.png)




