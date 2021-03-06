# Machine Learning

## Questions

- [알고 있는 metric에 대해 설명해주세요. (ex. RMSE, MAE, recall, precision ...)](#1)
- [정규화를 왜 해야할까요? 정규화의 방법은 무엇이 있나요?](#2)
- [Local Minima와 Global Minima에 대해 설명해주세요.](#3)
- [차원의 저주에 대해 설명해주세요.](#4)
- [dimension reduction기법으로 보통 어떤 것들이 있나요?](#5)
- [PCA는 차원 축소 기법이면서, 데이터 압축 기법이기도 하고, 노이즈 제거기법이기도 합니다. 왜 그런지 설명해주실 수 있나요?](#6)
- [LSA, LDA, SVD 등의 약자들이 어떤 뜻이고 서로 어떤 관계를 가지는지 설명할 수 있나요?](#7)
- [Markov Chain을 고등학생에게 설명하려면 어떤 방식이 제일 좋을까요?](#8)
- [텍스트 더미에서 주제를 추출해야 합니다. 어떤 방식으로 접근해 나가시겠나요?](#9)
- [SVM은 왜 반대로 차원을 확장시키는 방식으로 동작할까요? SVM은 왜 좋을까요?](#10)
- [다른 좋은 머신 러닝 대비, 오래된 기법인 나이브 베이즈(naive bayes)의 장점을 옹호해보세요.](#11)
- [회귀 / 분류시 알맞은 metric은 무엇일까?](#12)

## Answers

### #1

**Keyword** : MSE : 오차 제곱의 합의 평균 / MAE에 비해 이상치에 민감함

대표적으로 MSE가 있습니다. MSE는 오차를 제곱하여 평균을 낸 metric입니다. 오차에 제곱을 하여 연산을 하기 때문에 MAE에 비해 이상치(outlier)에 민감합니다.

### #2

**Keyword** : 동일한 정도의 스케일(중요도)로 반영해주는 것이 목적 / 예시로 MinMaxScaler

정규화는 모델에 들어가는 모든 데이터가 동일한 정도의 중요도로 반영되도록 하기 위해 사용합니다. 방법에는 모든 feature에 대해 0과 1 사이의 값으로 변환하는 MinMaxScaler가 있습니다.

++ **정규화에는 다양한 정의**가 있는 것 같다. 아래 사이트에서 말한 것에 따르면 Normalization과 Standardization 관점에서 조사를 했던 것 같다.

https://realblack0.github.io/2020/03/29/normalization-standardization-regularization.html

### #3

**Keyword** : local minima는 특정 범위 내의 최소값, global minima는 전 구간에서의 최소값

말 그대로 local minima는 특정 범위 내의 최소값, global minima는 전 구간에서의 최소값이다. 우리는 학습을 진행할 때 local minima에 빠지지 않고 global minima를 찾는 것을 목적으로 한다.

### #4

**Keyword** : 차원이 커질수록 데이터가 상대적으로 희박해지는 문제

데이터 학습을 위한 차원이 증가하면서, 차원의 수에 비해 데이터가 희박해져 성능이 저하되는 현상을 말합니다.

주로 KNN알고리즘에서 발생합니다.

### #5

**Keyword** : 특징 추출, 특징 선택

dimension reduction 기법은 특징 추출(feature extraction)과 특징 선택(feature selection)으로 나눌 수 있습니다. feature selection은 데이터의 경향을 잘 표현하지 못하는 차원을 소거해나가면서 진행할 수 있고, feature extraction의 경우에는 PCA, SVD, NMF와 같은 차원 축소 기법들을 활용해 차원을 줄일 수 있습니다.

- PCA(Principal component analysis, 주성분 분석)
- SVD(Singular Value Decomposition, 특이값 분해)
- NMF(Non-negative Matrix Factorization, 음수 미포함 행렬 분해)

### #6

**keyword** : 대표 축, 주성분

PCA는 각 차원의 분산을 최대로 갖는 분포를 설명할 수 있는 대표 축을 뽑는 과정이고, 높은 주성분들만 선택하면 노이즈로 구성된 차원이 배제되기 때문에 노이즈 제거 기법이라 불리기도 합니다.

### #7

**keyword** : 토픽 모델링

**LDA(latent dirtchlet allocation)** 이란 지도 학습에서 적용되는 차원 축소 기법이며 입력 데이터의 정답을 최대한 분리할 수 있는 축을 찾는 기법입니다

**LSA(Latent Semantic Analysis)** 는 잠재 의미 분석을 뜻하며, 주로 토픽 모델링에 자주 사용되는 기법입니다. LSA는 DTM(Document-Term Matrix)이나 TF-IDF(Term Frequency-Inverse Document Frequency)행렬에 Truncated SVD를 적용하여 차원을 축소시키고, 단어들의 잠재적인 의미를 이끌어냅니다.

**SVD** 는 PCA와 유사한 행렬 분해 기법을 사용하나 정방행렬을 분해하는 PCA와 달리 행과 열의 크기가 다른 행렬에도 적용할 수 있습니다.

### #8

**keyword** : 날씨

내일의 날씨를 예측해야 할 때, 오늘의 날씨 상태만을 가지고서 확률적으로 예측을 하는 방법이에요.

마르코프 체인(Markov chain)의 정의란 마르코프 성질을 가진 이산 확률 과정을 뜻합니다. 여기서 마르코프 성질은 '특정 상태의 확률은 오직 과거의 상태에 의존한다'라는 것 입니다.

![](https://i.imgur.com/2HVWWFJ.png)

### #8

### #9

**keyword** : LDA 방법  
LDA 방법  
문서의 집합에서 토픽을 찾아내는 대표적인 알고리즘. 문서들은 토픽들의 혼합으로 구성되어 있고 토픽들은 확률분포에 기반하여 단어들을 생성한다고 가정. 데이터가 주어지면 LDA는 토픽을 문서가 생성되던 과정을 역추적. 각 문서의 토픽 분포와 각 토픽 내의 단어 분포를 추정

### #10

### #11

**keyword** : 단순하고, 빠르고, 정확함, 적은 예제
나이브 베이즈 분류는 feature들의 상관관계가 없다고 간주하고 분류하기 때문에 computational cost가 작아 단순하고 빠르지만 정확하며 훈련에 필요한 예제가 상대적으로 적은 편입니다. 또한 대용량 데이터에 대한 속도도 빠른 편입니다.

### #12
