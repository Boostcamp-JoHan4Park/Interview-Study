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
* [뉴럴넷의 가장 큰 단점은 무엇인가? 이를 위해 나온 One-Shot Learning은 무엇인가?](#11)
* [요즘 Sigmoid 보다 ReLU를 많이 쓰는데 그 이유는?](#12)
* [Gradient Descent에 대해서 쉽게 설명한다면?](#13)
*  





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

...



### #11

**keyword** : 데이터가 많아야 된다는 점, fine tuning 과정을 거치지 않고 바로 예측

NN의 가장 큰 단점은 데이터가 많아야 잘 학습이 된다는 점입니다. 하지만 현실에서는 그 정도의 데이터가 없습니다. 그래서 대량의 data로 pretrain된 모델을 task에 맞게 별도의 구조 변경과 fine tuning 과정을 거치지 않고 바로 예측을 하는 것을 one-shot learning이라고 합니다. GPT-2에서 one-shot learning의 가능성을 처음 보여준 것 같습니다.



### #12

**keyword** : 

Sigmoid보다 ReLU를 많이 쓰는데 그 이유는?

Sigmoid보다 ReLU

- Non-Linearity라는 말의 의미와 그 필요성은?

  비선형성, 선형 layer만 깊게 쌓으면 결국 다 똑같다 ! 선형 layer와 비선형 layer를 번갈아가며 쌓음으로써 함수의 표현력이 좋아지기에 필요합니다 !

- ReLU로 어떻게 곡선 함수를 근사하나?

  비선형 함수이기 때문에.. 선형함수와 ReLU를 여러겹 겹치면 곡선 함수에 근사하게 된다.

- ReLU의 문제점은?

  0 이상인 값들은 x 그대로의 값이 들어가게 되므로 Layer를 거치다보면 값이 exploding될 수 있다.

- Bias는 왜 있는걸까?

  학습이 진행되다보면 학습 결과가 한 쪽으로 기우는 경우가 있다. 이 경우 결과를 조금 균형 있게 잡아주기 위해 사용 





### #13

- Gradient Descent에 대해서 쉽게 설명한다면?

  우리가 원하고자 하는 목표에 도달하기 위해 방향을 설정하는 것

- 왜 꼭 Gradient를 써야 할까? 그 그래프에서 가로축과 세로축 각각은 무엇인가? 실제 상황에서는 그 그래프가 어떻게 그려질까?

  방향을 설정하는 것이기 때문에.. 우리가 물리시간에 배웠던.. 이동량, 속도, 가속도 개념과 같이 미분을 한 gradient를 사용하는 것 같음 ! 속도와 마찬가지로 1차 미분한 값인 gradient는 방향을 지정해주기에 사용 n차 미분 값을 사용할수도 있지만 사용하기에는 cost가 너무 많이 들기 때문에 gradient를 사용한다.

  세로축은 우리가 원하고자 하는 목표인 cost, 가로축은 가중치들을 의미한다.

  실제로는 local minimum이 많이 굴곡이 많게 그려질 것 같다.

- GD 중에 때때로 Loss가 증가하는 이유는?

  learning rate에 따라 gradient 방향으로 일정 거리를 이동하는 방식으로 최적의 값을 탐색하는데.. 이 때 최적값을 지나치게 되면 loss가 증가할 수도 있다 !

- Back Propagation에 대해서 쉽게 설명 한다면?

  우리가 원하는 함수에 도달하기 위해 가중치를 조정하는 과정

  input을 통한 output이 나왔다면,,! 그 output과 정답을 통해 loss를 계산한 뒤 그 정도에 따라 layer 순서로 가중치를 조절해주는 작업

  

### 
