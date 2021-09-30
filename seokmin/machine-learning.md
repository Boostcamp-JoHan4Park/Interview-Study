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

말 그대로 local minima는 **특정 범위 내의 최소값**, global minima는 **전 구간에서의 최소값**입니다. 우리는 학습을 진행할 때 local minima에 빠지지 않고 **global minima를 찾는 것을 목적**으로 합니다.



### #4

데이터 학습을 위한 차원이 증가하면서, 학습 데이터 수가 차원의 수보다 적어져 성능이 저하되는 현상을 말합니다. KNN알고리즘에서 주로 발생합니다.



### #5

차원 축소 기법에는 feature selection과 feature extraction 두 가지 방식이 있습니다. Feature selection은 EDA를 통해 유의미한 Feature를 고르는 방식을 사용하고, feature extraction은 PCA 기반의 방법으로 유의미한 feature로 압축을 합니다.



### #6

cnn의 1x1 커널과 같이 차원을 축소시켜  불필요한 정보를 제거하여 유의미한 feature만 남도록 하는 방법론으로 이 때 노이즈가 제거된다고 생각합니다.

CNN에서 1x1 kernel의 역할과 비슷한지