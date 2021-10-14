# Deep Learning

## Questions

- [딥러닝은 무엇인가요? 딥러닝과 머신러닝의 차이는?](#1)
- [Cost Function과 Activation Function은 무엇인가요?](#2)
- [Tensorflow, PyTorch 특징과 차이가 뭘까요?](#3)
- [Data Normalization은 무엇이고 왜 필요한가요?](#4)
- [알고있는 Activation Function에 대해 알려주세요. (Sigmoid, ReLU, LeakyReLU, Tanh 등)](#5)
- [오버피팅일 경우 어떻게 대처해야 할까요?](#6)
- [하이퍼 파라미터는 무엇인가요?](#7)
- [Weight Initialization 방법에 대해 말해주세요. 그리고 무엇을 많이 사용하나요?](#8)

## Answers

### #1

**Keyword**: Neural network(인공신경망), Feature extraction(특징 추출)

딥러닝은 머신러닝의 하위분야로, **인공신경망**을 이용한 머신러닝 기법입니다.  
딥러닝과 머신러닝의 가장 큰 차이점은 **특징 추출**의 사용 유무입니다.  
머신러닝은 특징추출의 방법을 사람이 직접 분석하고 판단하는 반면 딥러닝은 학습을 통해 end-to-end하게 작용하며 머신러닝보다 더 복잡하고 다양한 task를 수행할 수 있게 됐습니다.

### #2

**Keyword**: Loss, 비선형

Cost function은 모델의 예측값과 정답의 **오차(loss)를 계산**해주는 함수로, 학습 뱡향을 어느 방향으로 얼마나 개선할지 판단하는 지표입니다.  
Activation function은 **선형함수를 비선형함수로** 만들어주는 함수로, 비선형성을 키워 모델이 복잡한 데이터와 연산도 고려할 수 있게 해줍니다

### #3

**Keyword**: Define and Run, Define by Run

Tensorflow는 **define and run** 방식으로, 세션을 미리 만들어 placeholder를 선언하고 코드를 실행하는 시점에 데이터를 넣는 반면,  
PyTorch는 **define by run** 방식으로, 그래프를 만들면서 동시에 값을 할당하기 때문에 코드를 직관적이고 깔끔하게 작성할 수 있습니다.

### #4

**Keyword**: Data의 scale을 비슷하게  
Data Normalization은 입력 data의 scale(규모, 폭)을 0~1 사이로 비슷하게 줄여줌으로써 각 data가 비슷한 중요도를 갖고 학습할 수 있습니다 또한 더 작은 scale을 가짐으로써 빠르게 수렴하고 gradient exploding을 방지할 수 있습니다.

### #5

**Keyword** : Sigmoid, ReLU, Tanh, ELU

1. **Sigmoid function** 은 Logistic 함수라고 불리기도 하며 미분이 되지않는 계단 함수를 미분 가능하도록 곡선화를 적용한 함수입니다.

   ![](https://i.imgur.com/CAPApz8.png)

2. **ReLU function(Rectified Linear Unit)** 이란 $f(x) = max(0,x)$ 함수로, 정의해보면 "어떤 $x$가 0보다 크면 $x$를 출력, 0보다 작으면 0으로 출력"하는 함수를 의미 합니다.

   ![](https://i.imgur.com/q9yS0mL.png)

3. **Leaky ReLU** 는 ReLU가 갖는 **Dying ReLU** 를 해결하기 위해 나온 함수입니다.

- Dying ReLU : 음의 값을 가지면 전부 0으로 출력하기 때문에 몇몇 weight들이 업데이트 되지 않는 현상

  ![](https://i.imgur.com/dyQ6UVQ.png)

4. **tanh function** 은 sigmoid function의 함수 값의 중간이 0이 아니라서 학습이 느리다는 단점을 극복한 함수입니다. tanh 함수는 입력을 -1 ~ 1 사이의 값으로 바꿔줍니다.

   ![](https://i.imgur.com/ua5y2m5.png)

5. **Maxout**은 앞서 나온 activation function과는 다른 성격의 함수입니다. Saturated Regime이 없으며 gradient가 0이 되는 지점이 없다는 장점이 있습니다. 하지만 parameter 수가 두배가 된다는 단점이 있습니다.

   ![](https://i.imgur.com/RVQ36kg.png)

### #6

**Keyword** : Data augmentation, Dropout, parameter Norm Penalties, Batch Normalization, Early stopping

1. Data augmentation

   training data의 개수를 인위적으로 늘려 data의 양을 늘리는 기법입니다. 데이터의 특징을 고려해 사용해야 합니다.

2. parameter Norm penalties

   cost function에 제곱을 더하거나 ($L2$) 절대값을 더하여 ($L1$) weight의 크기에 제한을 줍니다.

   - L2 weight decay(제곱값) : $L2$ parameter 는 ridge 회귀분석 또는 tikhonv 정규화로 알려져있습니다.

   - L1 weight decay(절대값) : LASSO는 선형모델의 $L1$패널티와 최소제곱법(LSM)을 합친 모델입니다.

3. Dropout

   계층마다 일정 비율의 뉴런을 랜덤하게 골라 drop 시키고 나머지 뉴런을 학습하는 방법입니다. dropout을 통해 앙상블 학습처럼 마치 여러 모델을 학습시킨 것과 같은 효과를 주어 오버피팅을 해결할 수 있습니다.

   ![](https://i.imgur.com/zVHFTkS.png)

4. Noise Rubustness

   노이즈나 이상치(outlier) 같은 엉뚱한 데이터가 들어와도 흔들리지 않는 모델(=강건성 있는 모델)을 만들기 위한 방법으로 일부러 노이즈를 주는 방법입니다.

   ![](https://i.imgur.com/at6Z46N.png)

5. Batch Normalization
   계층마다 일정 비율의 뉴런을 랜덤하게 골라 drop 시키고 나머지 뉴런을 학습하는 방법입니다. dropout을 통해 앙상블 학습처럼 마치 여러 모델을 학습시킨 것과 같은 효과를 주어 오버피팅을 해결할 수 있습니다.

   ![](https://i.imgur.com/zVHFTkS.png)

6. Batch Normalization

   활성화 값이 적절하게 분포되도록 하는 값을 좋은 가중치의 초기 값으로 봅니다.
   가중치의 초기값에 의존하지 않고 활성화 값을 강제로 적절히 분포되도록 하는 것을 **배치 정규화(Batch Normalization)** 이라고 합니다.

   ![](https://i.imgur.com/jPnToAx.png)

7. Early stopping

   Epoch가 늘어날수록 Training Error는 줄어들지만, Testing Error는 증가하며 overfitting이 발생할 수 있습니다. 따라서 이전 Epoch에 비해 오차(Error)가 증가하면 오버피팅이 발생하기 전에 학습을 멈추는 방법입니다.

   ![](https://i.imgur.com/lHlJQH7.png)

### #7

**keyword** : 사용자가 직접 조절할 수 있는 파라미터

모델에 설정해줘야하는 파라미터 중 사용자가 직접 조절할 수 있는 파리미터를 의미합니다.

### #8
