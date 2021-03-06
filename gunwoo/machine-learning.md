# Machine Learning  

## Questions  
* [알고 있는 metric에 대해 설명해주세요. (ex. RMSE, MAE, recall, precision ...)](#1)  
* [정규화를 왜 해야할까요? 정규화의 방법은 무엇이 있나요?](#2)  
* [Local Minima와 Global Minima에 대해 설명해주세요.](#3)  
* [차원의 저주에 대해 설명해주세요.](#4)  
* [dimension reduction기법으로 보통 어떤 것들이 있나요?](#5)  
* [PCA는 차원 축소 기법이면서, 데이터 압축 기법이기도 하고, 노이즈 제거기법이기도 합니다. 왜 그런지 설명해주실 수 있나요?](#6)
## Answers
### #1

**Keyword** : MSE : 오차 제곱의 합의 평균 / 이상치를 잡아내는데 효과적

대표적으로 MSE가 있습니다. MSE는 오차를 제곱하여 평균을 낸 metric입니다. 오차에 제곱을 하여 연산을 하기 때문에 이상치(outlier)를 잡아내는데 효과적이라고 알고 있습니다.



### #2

**Keyword** : 동일한 정도의 스케일(중요도)로 반영해주는 것이 목적 / 예시로 MinMaxScaler

정규화는 모델에 들어가는 모든 데이터가 동일한 정도의 중요도로 반영되도록 하기 위해 사용합니다. 방법에는 모든 feature에 대해 0과 1 사이의 값으로 변환하는 MinMaxScaler가 있습니다. 



++ **정규화에는 다양한 정의**가 있는 것 같다. 아래 사이트에서 말한 것에 따르면 Normalization과 Standardization 관점에서 조사를 했던 것 같다.

https://realblack0.github.io/2020/03/29/normalization-standardization-regularization.html

### #3
### #4
### #5

**Keyword** : Feature Selection / Feature Extraction

- dimension reduction 기법은 feature selection 과 feature extraction으로 나눌 수 있습니다. 
feature selection은 데이터의 경향을 잘 표현하지 못하는 차원을 소거해나가면서 진행할 수 있고, 
feature extraction의 경우에는 PCA, SVD, NMF와 같은 차원 축소 기법들을 활용해 차원을 줄일 수 있습니다.


- PCA(주성분 분석)
- SVD(특이값 분해/Singular Value Decomposition)
- NMF(음수 미포함 행렬 분해/Non-negative Matrix Factorization)


### #6

**Keyword** : 

- PCA는 각 차원의 분산을 최대로 갖는 분포를 설명할 수 있는 대표 축을 뽑는 과정이고, 높은 주성분들만 선택하면 노이즈로 구성된 차원이
배제되기 때문에 노이즈 제거 기법이라 불리기도 합니다


