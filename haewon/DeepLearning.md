# Deep Learning
## Questions  
* [딥러닝은 무엇인가요? 딥러닝과 머신러닝의 차이는?](#1)  
* [Cost Function과 Activation Function은 무엇인가요?](#2)  
* [Tensorflow, PyTorch 특징과 차이가 뭘까요?](#3)  
* [Data Normalization은 무엇이고 왜 필요한가요?](#4)  


  
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
