# Deep Learning
## Questions  
* [딥러닝은 무엇인가요? 딥러닝과 머신러닝의 차이는?](#1)  
* [Cost Function과 Activation Function은 무엇인가요?](#2)  
* [Tensorflow, PyTorch 특징과 차이가 뭘까요?](#3)  
* [Data Normalization은 무엇이고 왜 필요한가요?](#4)  
* [알고있는 Activation Function에 대해 알려주세요. (Sigmoid, ReLU, LeakyReLU, Tanh 등)](#5)
* [오버피팅일 경우 어떻게 대처해야 할까요?](#6)
* [하이퍼 파라미터는 무엇인가요?](#7)
* [Weight Initialization 방법에 대해 말해주세요. 그리고 무엇을 많이 사용하나요?](#8)
* [볼츠만 머신은 무엇인가요?](#9)
* [TF, PyTorch 등을 사용할 때 디버깅 노하우는?](#10)
* [뉴럴넷의 가장 큰 단점은 무엇인가? 이를 위해 나온 One-Shot Learning은 무엇인가?](#11)
* [요즘 Sigmoid 보다 ReLU를 많이 쓰는데 그 이유는?
    Non-Linearity라는 말의 의미와 그 필요성은?
    ReLU로 어떻게 곡선 함수를 근사하나?
    ReLU의 문제점은?
    Bias는 왜 있는걸까?](#12)
* [Gradient Descent에 대해서 쉽게 설명한다면?
    왜 꼭 Gradient를 써야 할까? 그 그래프에서 가로축과 세로축 각각은 무엇인가? 실제 상황에서는 그 그래프가 어떻게 그려질까?
    GD 중에 때때로 Loss가 증가하는 이유는?
    Back Propagation에 대해서 쉽게 설명 한다면?](#13)
* [Local Minima 문제에도 불구하고 딥러닝이 잘 되는 이유는?
    GD가 Local Minima 문제를 피하는 방법은?
    찾은 해가 Global Minimum인지 아닌지 알 수 있는 방법은?](#14)
* [Training 세트와 Test 세트를 분리하는 이유는?
    Validation 세트가 따로 있는 이유는?
    Test 세트가 오염되었다는 말의 뜻은?
    Regularization이란 무엇인가?](#15)


## Answers  
### #1
딥러닝은 신경망을 사용해서 머신러닝 학습을 수행하는 것으로, 머신러닝과는 다르게 데이터를 스스로 학습할 수 있습니다.  

### #2
Cost Function은 데이터 셋과 어떤 가설 함수와의 오차를 계산하는 함수입니다. Cost Function의 궁극적인 목표는 Global Minimum을 찾는 것입니다. Activation Function이란 신경망의 output을 결정하는 식으로 데이터를 비선형적으로 바꿉니다.  

### #3
**Pytorch**
- Dynamic Computation Graph(동적그래프) : 동작시 매번 새로운 그래프를 만들게 되어 다양한 조건에 대해 대응이 가능하다.  
- Define by Run : 실행을 하면서 그래프를 정의  
- 코드를 깔끔하고 직관적으로 작성 가능하고, 텐서는 정의 후 값을 넣은 다음에야 디버깅이 가능한데 파이토치는 중간중간 바로 디버깅 가능하다는 장점이 있다.   
  
**TensorFlow**
- Stactic Computation Graph(정적그래프) : 동작시 기존에 구축된 정적인 동일한 연산그래프를 사용하여, 그래프에 대한 최적화를 할 수 있다. 
- Define and Run : 실행 전 그래프를 정의후 실행시점에서 데이터를 feed  
- Production과 scalability에 장점이 있다.  
![image](https://user-images.githubusercontent.com/49435163/134613605-ad0b6bbd-fa19-482c-82ac-fc7b7b58db77.png)

### #4
정규화는 학습과정에서 scale이 큰 feature가 다른 feature를 지배하는 것을 막기위해 데이터 분포를 고르게 만들어 줍니다. 데이터 정규화를 통해 학습을 더 빨리하고 Local Minima에 빠지게 될 가능성을 줄일 수 있습니다.   
- Min-Max Normalization  
- Z-Score Normalization  

### #5

![image](https://user-images.githubusercontent.com/49435163/137356616-916ba810-2ba8-4a61-9f2c-defc32ac8e08.png)  

- sigmoid : saturation problem, not zero centered  
- tanh : zero centered / saturation problem  
- ReLU : not saturate, efficietnt, convergence faster / not zero centered  
- LeakyReLU 
- ELU  

### #6
Regularization  
- Early stopping  
- Parameter norm penalty  
- Data Augmentation  
- DropOut  
- Label Smoothing  
- Batch Normalization  
 
### #7
하이퍼 파라미터는 모델링할 때 최적의 모델을 구현하기 위해서 모델에 설정하는 변수로, 사용자가 직접 세팅해주는 것을 의미합니다. 사용자가 직접 설정하면 하이퍼 파라미터, 모델 혹은 데이터에 의해 결정되면 파라미터입니다.  
- 학습률  
- 손실 함수  
- 미니배치 크기  
- 에포크 수  

### #8
- Xavier Initialization  
- He Initialization  
  
### #9
Boltzmann Machine은 마르코프 모델의 일종으로, visible layer와 hidden layer가 양방향으로 전부 연결되어 있는(fully-connected) 얕은 두 층으로 이루어진 확률론적인 모델이다. 하지만 BM은 학습이 어려워 거의 사용하지 않고, RBM을 사용한다.  

### #10
파이썬 파일을 디버깅하는 방법과 유사하게 디버깅을 한다. 함수로 넘어가는 부분이나, 중요한 지점에 중단점을 두고 변화되는 값들을 확인하며 디버깅한다.   

### #11

### #12

### #13  
- Gradiennt Descent는 딥러닝을 학습시킬때 손실 함수의 기울기를 구하여 기울기가 낮은 쪽으로 계속 이동 시키면서 최적값을 찾는 방법이다.   
- GD중 local minimum에 빠졌다가 나오는 순간 때때로 loss가 증가하게 된다.  
- Back Propagation이란, 궁극적으로 예측값과 실제값의 오차에 관여하는 모든 노드들의 weight와 bias를 수정하는 것으로, 이때 오차를 줄이는 방향으로 반복적으로 수정하게 됩니다.   
역전파는 순전파와 반대로 출력층에서 입력층 방향으로 loss애 대한 입력값의 기울기를 계산하며 가중치를 업데이트 합니다. 이 과정에서 chain rule이 사용되게 됩니다.   

### #14
Local Minima 문제에도 불구하고 딥러닝이 잘 되는 이유
- local Minima문제를 해결할 수 있는 Optimizer들이 많이 나왔기 때문
  - GD가 Local Minima 문제를 피하기 위해서는 Momentum 사용(Momentum, RMSprop, Adam등)  
  Momentum은 이전의 방향을 기억하여 관성처럼 추가적인 이동을 하기에 학습속도를 빠르게 하고, local minima를 벗어나게 도와줌
- weight와 bias를 잘 초기화 시키는 weight initialization 방법들이 나왔기 때문
찾은 해가 Global Minimum인지 아닌지 알 수 있는 방법은 모르겠....weight initialize를 다르게 여러번 한 후 확인하기?
### #15
- Training 세트와 Test 세트를 분리하는 이유는 오버피팅을 방지하기 위해서 이다. 현실세계에서는 처음보는 이미지에 대해서도 모델이 잘 작동해야하고, 모델이 잘 학습되었는지 성능을 판단하기 위해서 학습 시 보지 못했던 이미지로 테스트 하기 위해 train과 test데이터를 나누게 됩니다. 
- Validation 세트는 데이터를 traing하는 과정에서 train이 잘 되고 있는지 확인하고 검증하며 파라미터 튜닝을 하기 위해서 존재합니다. 
- Test 세트가 오염되었다는 말은 test 세트가 train 세트가 비슷하다는 뜻입니다. test데이터가 train데이터와 비슷할 시 제대로 된 모델 성능 평가를 할 수 없기 때문이다. 
- Regularization이란 overfitting을 방지하기 위해 모델이 학습이 잘 안되도록 모델에 일부러 제약을 주는 테크닉을 추가해서 처음 보는 데이터와 실환경에서도 잘 작동되도록 하는 것이다. 