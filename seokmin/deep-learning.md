# Deep Learning  

## Questions  
* [딥러닝은 무엇인가요? 딥러닝과 머신러닝의 차이는?](#1)  
* [Cost Function과 Activation Function은 무엇인가요?](#2)  
* [Tensorflow, PyTorch 특징과 차이가 뭘까요?](#3)  
* [Data Normalization은 무엇이고 왜 필요한가요?](#4)  
* [알고 있는 Activation Function에 대해 알려주세요.](#5)
* [오버피팅일 경우 어떻게 대처해야 할까요?](#6)
* [하이퍼 파라미터는 무엇인가요?](#7)
* [Weight Initialization 방법에 대해 말해주세요. 그리고 무엇을 많이 사용하나요?](#8)
* [볼츠만 머신은 무엇인가요?](#9)
* [TF, PyTorch 등을 사용할 때 디버깅 노하우는?](#10)





## Answers  
### #1

딥러닝은 선형 함수와 비선형 함수로 결합된 층을 깊게 쌓아 학습해나가는 방식이다.

머신 러닝은 데이터의 특징을 사람이 직접 분석하고 판단하지만 딥러닝은 기계가 자동으로 특징을 추출한다.

### #2

cost function는 모델의 예측값과 정답의 오차를 계산해주는 함수로 학습 방향을 판단하는 지표로 사용한다. activation function은 입력 신호의 총 합을 출력 신호로 변환하는 함수로 주로 비선형 함수를 사용하여 신경망의 표현력을 높여주기 위해 사용한다.

### #3

Tensorflow는 static하게 graph를 정의하고 실행 시점에서 실행이 되는데(Define and Run), PyTorch는 실행 시점에서 graph가 그려진다.(Dynamic Computation Graph)

### #4

Data를 일정 범위 내의 값으로 바꾸어주어 exploding이나 vanishing 현상을 막기 위해 사용한다.


### #5

주로 Activation Function은 비선형 함수를 사용합니다. ReLU가 대표적으로 있습니다. 0미만인 값은 0으로 0이상인 값은 x값으로 변형해주는 함수입니다.



### #6

오버 피팅의 경우 학습을 더 어렵게 하는 Regularization을 진행한다. 예시로 Data augmentation,dropout, BatchNormalization 등이 있다.



### #7

모델에 설정해 줘야하는 파라미터 중 **사용자가 직접 조절할 수 있는 파라미터**를 의미합니다



### #8

대부분 **uniform distribution이나 normal distribution**을 따르고 표준 편차를 input에 따라 다르게 조절하는 방식을 많이 사용합니다.

가중치 초기화 방법으로는 대표적으로 **kaiming he initialization** 가 있습니다. xavier initialization 방식에서 relu를 사용하면 0으로 출력값이 수렴하는 현상을 개선하였다. 정규분포와 균등 분포를 따르는 두 가지 방법론이 있다. 



다른 방법을 사용하게 되면에 대한 Issue

모든 값을 0으로 초기화하면 곱셈과정에서 학습이 진행이 안됨 !

가중치 초기화를 random하게 줄 경우 local minimum이나 over, underfitting 문제가 발생할 수도 있다 !



ref 

https://blog.naver.com/PostView.naver?blogId=handuelly&logNo=221831940317&parentCategoryNo=&categoryNo=31&viewDate=&isShowPopularPosts=true&from=search



### #9

확률적으로 순환하는 신경망 네트워크

DNN, CNN, RNN같은 deterministic model들과 다른 목표를 가지고 있다. Deterministic model들은 타겟과 가설 간의 차이를 줄여서 오차를 줄이는 것을 목표.., generative model (RBM)의 목표는 확률밀도함수를 모델링하는 데에 목적을 두고 있다.

### #10