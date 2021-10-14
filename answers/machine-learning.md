# Machine Learning  

## Questions  
* [알고 있는 metric에 대해 설명해주세요. (ex. RMSE, MAE, recall, precision ...)](#1)  
* [정규화를 왜 해야할까요? 정규화의 방법은 무엇이 있나요?](#2)  
* [Local Minima와 Global Minima에 대해 설명해주세요.](#3)  
* [차원의 저주에 대해 설명해주세요.](#4)  
* [dimension reduction기법으로 보통 어떤 것들이 있나요?](#5)  
* [PCA는 차원 축소 기법이면서, 데이터 압축 기법이기도 하고, 노이즈 제거기법이기도 합니다. 왜 그런지 설명해주실 수 있나요?](#6)  
* [LSA, LDA, SVD 등의 약자들이 어떤 뜻이고 서로 어떤 관계를 가지는지 설명할 수 있나요?](#7)  
* [Markov Chain을 고등학생에게 설명하려면 어떤 방식이 제일 좋을까요?](#8)  
* [텍스트 더미에서 주제를 추출해야 합니다. 어떤 방식으로 접근해 나가시겠나요?](#9)  
* [SVM은 왜 반대로 차원을 확장시키는 방식으로 동작할까요? SVM은 왜 좋을까요?](#10)  

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

**Keyword** :  local minima는 특정 범위 내의 최소값, global minima는 전 구간에서의 최소값

말 그대로 local minima는 특정 범위 내의 최소값, global minima는 전 구간에서의 최소값이다. 우리는 학습을 진행할 때 local minima에 빠지지 않고 global minima를 찾는 것을 목적으로 한다.



### #4

**Keyword** : 차원이 커질수록 데이터가 상대적으로 희박해지는 문제

데이터 학습을 위한 차원이 증가하면서, 차원의 수에 비해 데이터가 희박해져 성능이 저하되는 현상을 말합니다.

주로 KNN알고리즘에서 발생합니다.



### #5  
### #6  
### #7  
### #8  
### #9  
### #10  