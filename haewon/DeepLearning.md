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
![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/3a7abd61-108b-4b6b-8443-177ff86db53b/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20211014%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20211014T162937Z&X-Amz-Expires=86400&X-Amz-Signature=e9a1f8e1f4d8fe94ba78d3cfbe59738f0a2cd32ea49f32281823c5515cc4011c&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)
Boltzmann Machine은 마르코프 모델의 일종으로, visible layer와 hidden layer가 양방향으로 전부 연결되어 있는(fully-connected) 얕은 두 층으로 이루어진 확률론적인 모델이다. 하지만 BM은 학습이 어려워 거의 사용하지 않고, RBM을 사용한다.

https://medium.com/@ahnchan2/%EC%B4%88%EB%B3%B4%EC%9E%90%EC%9A%A9-rbm-restricted-boltzmann-machines-%ED%8A%9C%ED%86%A0%EB%A6%AC%EC%96%BC-791ce740a2f0
https://www.whydsp.org/283
### #10
파이썬 파일을 디버깅하는 방법과 유사하게 디버깅을 한다. 함수로 넘어가는 부분이나, 중요한 지점에 중단점을 두고 변화되는 값들을 확인하며 디버깅한다. 
