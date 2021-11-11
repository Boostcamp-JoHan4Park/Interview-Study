# Machine Learning

## Questions  
* [알고 있는 metric에 대해 설명해주세요.](#1)  
* [Cost Function과 Activation Function은 무엇인가요?](#2)  
* [Tensorflow, PyTorch 특징과 차이가 뭘까요?](#3)  
* [Data Normalization은 무엇이고 왜 필요한가요?](#4)  
* [Local Minima와 Global Minima에 대해 설명해주세요.](#5)
* [차원의 저주에 대해 설명해주세요.](#6)
* [dimension reduction기법으로 보통 어떤 것들이 있나요?](#7)
* [PCA는 차원 축소 기법이면서, 데이터 압축 기법이기도 하고, 노이즈 제거기법이기도 합니다. 왜 그런지 설명해주실 수 있나요?](#8)
* [LSA, LDA, SVD 등의 약자들이 어떤 뜻이고 서로 어떤 관계를 가지는지 설명할 수 있나요?](#9)
* [Markov Chain을 고등학생에게 설명하려면 어떤 방식이 제일 좋을까요?](#10)
* [텍스트 더미에서 주제를 추출해야 합니다. 어떤 방식으로 접근해 나가시겠나요?](#11)
* [SVM은 왜 반대로 차원을 확장시키는 방식으로 동작할까요? SVM은 왜 좋을까요?](#12)
* [다른 좋은 머신 러닝 대비, 오래된 기법인 나이브 베이즈(naive bayes)의 장점을 옹호해보세요.](#13)
* [회귀 / 분류시 알맞은 metric은 무엇일까?](#14)
* [Association Rule의 Support, Confidence, Lift에 대해 설명해주세요.](#15)
* [최적화 기법중 Newton’s Method와 Gradient Descent 방법에 대해 알고 있나요?](#16)
* [머신러닝(machine)적 접근방법과 통계(statistics)적 접근방법의 둘간에 차이에 대한 견해가 있나요?](#17)
* [인공신경망(deep learning이전의 전통적인)이 가지는 일반적인 문제점은 무엇일까요?](#18)
* [지금 나오고 있는 deep learning 계열의 혁신의 근간은 무엇이라고 생각하시나요?](#19)


## Answers  
### #1
- *Classification Metrics (accuracy, precision, recall, F1-score, ROC, AUC)*
- *Regression Metrics (MSE, MAE)*
- *Ranking Metrics (MRR, DCG, NDCG)*
- *Statistical Metrics (Correlation)*
- *Computer Vision Metrics (PSNR, SSIM, IoU)*
- *NLP Metrics (Perplexity, BLEU score)*
- *Deep Learning Related Metrics (Inception score, Frechet Inception distance)*
---
- MSE(평균 제곱 오차) : 
  오차에 제곱이 되기 때문에 이상치(outlier)를 잡아내는 데 효과적
- MAE(평균 절대값 오차) : 
  변동치가 큰 지표와 낮은 지표를 같이 예측하는 데 효과적
- RMSE : MSE값에 루트
- RMAE : MAE값에 루트
- Accuracy, Recall, Precision

    Accuracy : 올바르게 예측된 데이터의 수를 전체 데이터의 수로 나눈 값

    Recall : 실제로 True인 데이터를 모델이 True라고 인식한 데이터의 수

    Precision : 모델이 True로 예측한 데이터 중 실제로 True인 데이터의 수

![image](https://user-images.githubusercontent.com/49435163/134614742-e666d846-18c3-4d6f-b21a-5b46d7a256ad.png)

- F1 score  :  
  precision 과 recall의 조화평균  

### #2
정규화는 학습과정에서 scale이 큰 feature가 다른 feature를 지배하는 것을 막기위해 데이터 분포를 고르게 만들어 줍니다. 데이터 정규화를 통해 학습을 더 빨리하고 Local Minima에 빠지게 될 가능성을 줄일 수 있습니다.   

- Min-Max Normalization  
- Z-Score Normalization  
- 
### #3
많은 local minimum들 중 loss가 가장 최소가 되는 부분이 global minimum이다. 즉 최적의 파라미터를 찾는데 있어서 local minima에 빠지게 되면 global minima를 찾기 힘들어지게 된다.  
![image](https://user-images.githubusercontent.com/49435163/134620219-69dc81ba-9093-45ad-8456-f5f6bb58f3f8.png)  


### #4
차원이 커질수록 데이터가 상대적으로 희박해지는 문제로 KNN분류 알고리즘에서 흔하게 발생하는 문제이다. 이를 해결하기 위해 차원 축소 알고리즘을 사용한다.    
![image](https://user-images.githubusercontent.com/49435163/134620157-31a9c51c-4e08-4a2c-acfa-2e7fb2019361.png)


### #5  
- PCA
- SVD
- LSA
- LDA
- NMF
- t-SNE  

### #6  
PCA는 고유값이 가장 큰, 즉 데이터의 분산이 가장 큰 순으로 주성분 벡터를 추출함으로써, 가장 먼저 뽑힌 벡터가 데이터를 더 잘 표현할 수 있기 때문에 노이즈 제거 기법이라고도 불릴 수 있다.    

### #7  

### #8  
![image](https://sites.google.com/site/machlearnwiki/_/rsrc/1388728400812/RBM/markov-chain/markov%20chain%20picture.PNG?height=232&width=400)   
마르코프 체인이란 마르코프 성질을 가진 이산확률과정을 의미하는데, 여기서 마르코프 성질이란 특정 상태의 확률을 오직 과거의 상태에 의존한다 라는 것이다.   

### #9  
Topic Modeling
- LSA
- LDA
  
### #10  
서포트 벡터 머신(이하 SVM)은 결정 경계(Decision Boundary), 즉 분류를 위한 기준 선을 정의하는 모델이다.  
SVM은 초평면으로 나눌 수 없는 Nonlinear dataset을 해결하기 위해서 데이터를 고차원으로 확장하면서 데이터의 분포를 단순화하고, 초평면을 찾습니다.  
SVM은 과적합 괴는 경우가 적고 사용하기 쉽다는 장점이 있습니다.  

### #11
### #12  
### #13  
### #14  

### #15
Association Rule이란 데이터 상호간의 연관 규칙을 찾아내는 것입니다. Association Rule에는 사건이 얼마나 자주 방생하는 지를 측정할 수 있는 3가지 척도가 있습니다.  
- Support : 전체 경우의 수에서 두 아이템이 같이 나오는 비율 (=전체에서 X,Y를 같이 산 사람들의 비율)  
![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fer9hMT%2Fbtqw7O3ffQ1%2F3cxMHPPhKCp6U51cyStQck%2Fimg.jpg)
- Confidence : X가 나온 경우 중 X, Y가 함께 나온 비율 (=X를 산 사람들 중 Y도 같이 사는 사람의 비율)  
![image](https://blog.kakaocdn.net/dn/kFskg/btqxaEytiZm/vUqKuw60D4OB4Kl6c5Tt00/img.jpg)
- Lift : X와 Y가 같이 나오는 비율을 X와 Y가 나올 비율의 곱으로 나눈 값으로 Lift값이 1보다 높을 때 관계가 의미있다고 한다.  
![image](https://blog.kakaocdn.net/dn/bqOVoo/btqw7QGNgig/40UC3ukZfcpo8EZv3995Ik/img.jpg)

### #16    
- Newton’s Method  
  뉴턴-랩슨법은 f(x)=0의 해를 근사적으로 찾을 때 사용하는 방법이다.   
  먼저 현재 x값에서 접선을 그리고 접선이 x축과 만나는 지점으로 x를 이동시켜 가면서 점진적으로 해를 찾는다.  
![image](https://t1.daumcdn.net/cfile/tistory/012E143E517A0BBD36)  

- Gradient Descent  
  경사하강법은 f'(x)=0의 해를 근사적으로 찾을 때 사용하는 방법이다. 

### #17
- 머신러닝은 데이터의 패턴을 분석하여 예측의 __성공률을 높이는데__ 목적이 있다. 따라서 모델의 신뢰도나 정교한 가정 보다는 오버 피팅을 감안하더라도 여러 인자를 사용해 예측을 수행한다.  
- 통계학은 단순성을 추구하고, 정해진 분포나 가정을 통해서 __실패 확률을 줄여__ 모델의 신뢰도를 확보하는데 목적이 있다. 
-  또 인자(parameter)의 해석가능성과, 모델링과 샘플링의 가정(assumption)에 강조를 한다. 머신러닝과 전통적 통계학은 차이점도 있지만 많은 공통점 또한 공유하고 있다.

### #18 
deep learning 이전의 전통적인 인공신경망인 퍼셉트론은 퍼셉트론의 한계는 선형으로 분류를 할 수 있지만 XOR와 같이 선형 분류만 가능하며 비선형 분류는 불가능하다는 한계가 존재했다. 

### #19
지금 나오고 있는 deep learning 계열의 혁신의 근간
- 기존 딥러닝의 한계점들을 극복한 점들 : 과적합 문제 해결
- 하드웨어의 발전
- 빅데이터 : 딥러닝의 성능은 데이터의 수에 비례