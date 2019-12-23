# ganail-fashion
nail design using generative adversarial networks - fashion

![image](https://user-images.githubusercontent.com/53864655/71340062-ebd3bb80-2598-11ea-86f3-f633500d8b41.png)

## 사용 기술 - GAN(Generative Adversarial Networks)
Generator와 Discriminator로 구성되며 Generator는 특정 도메인의 샘플을 생성하고 Discriminator는 샘플이 Generator로부터 생성된 데이터인지 실제 샘플인지를 판별한다. Generator와 Discriminator는 이와 같은 과정을 통하여 학습하며 상호간에 성능을 향상시킨다. 
이 연구에서는 SK T-Brain에서 발표되서 인정받고 있는 Learning to Discover Cross-Domain Relations with Generative Adversarial Networks(DiscoGAN)을 사용하였다. DiscoGAN은 서로 다른 두 도메인간의 이미지 스타일 전이를 위한 GAN 기반의 학습 기법으로 Training Data가 unpaired dataset이라도 학습이 가능하며 간단한 네트워크 구조를 사용한다. 

## 환경 설정
* Python 2.7
* PyTorch
* Numpy/Scipy/Pandas
* Progressbar
* OpenCV
* Linux 16.04
* Cuda 8.0

## Data Set
* 네일 디자인 
![image](https://user-images.githubusercontent.com/53864655/71340605-add79700-259a-11ea-8d6d-6c8bf3ce5973.png)
* 액세서리

