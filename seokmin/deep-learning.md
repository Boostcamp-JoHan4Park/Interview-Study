# Deep Learning  

## Questions  
* [딥러닝은 무엇인가요? 딥러닝과 머신러닝의 차이는?](#1)  
* [Cost Function과 Activation Function은 무엇인가요?](#2)  
* [Tensorflow, PyTorch 특징과 차이가 뭘까요?](#3)  
* [Data Normalization은 무엇이고 왜 필요한가요?](#4)  

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