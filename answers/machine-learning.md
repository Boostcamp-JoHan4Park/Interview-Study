# Machine Learning  

## Questions  
* [알고 있는 metric에 대해 설명해주세요. (ex. RMSE, MAE, recall, precision ...)](#1)  
* [정규화를 왜 해야할까요? 정규화의 방법은 무엇이 있나요?](#2)  
* [Local Minima와 Global Minima에 대해 설명해주세요.](#3)  
* [차원의 저주에 대해 설명해주세요.](#4)  

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