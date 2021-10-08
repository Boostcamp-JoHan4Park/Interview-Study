### 딥러닝은 무엇인가요? 딥러닝과 머신러닝의 차이는?

- Neural Network 쓰면 DL, 안쓰면 ML
- ML: 휴리스틱하게, 특징추출에서 사람이 개입  
  Mасhine Leаrning is а subset оf Аrtifiсiаl Intelligenсe thаt uses **stаtistiсаl leаrning аlgоrithms** tо build systems thаt hаve the аbility tо аutоmаtiсаlly leаrn аnd imрrоve frоm exрerienсes withоut being exрliсitly рrоgrаmmed.  
  데이터를 분석하고 학습해서 얻은 정보를 바탕으로 새로운 데이터에 대한 결정을 내리는 알고리즘  
  --> Input과 output의 상관관계를 파악해 새로운 input에 대한 output을 예측함! 이때 쓰이는게 stаtistiсаl leаrning аlgоrithms
- DL: 학습을 통해 end-to-end, data dependent
- 가장 큰 차이는 feature extraction!!

### Cost Function과 Activation Function은 무엇인가요?

- Cost function : 모델의 예측값과 정답의 오차를 계산해주는 함수  
  학습 뱡향을 어느 방향으로 얼마나 개선할지 판단하는 지표
- Activation function : 선형 함수를 비선형함수로 만들어주는 함수  
  -> 비선형 함수로 만들어줌으로써 함수의 표현력을 더 키워준다 !

### Tensorflow, PyTorch 특징과 차이가 뭘까요?

- Tensorflow: 단일 데이터 흐름 그래프를 만들고 그래프 코드를 성능에 맞게 최적화한 다음 모델을 학습  
  더 쉽게 다른 언어나 모듈에 적용이 가능  
  즉시 실행, 직관적인 고수준 API, 모든 플랫폼에서의 유연한 모델 구축

- PyTorch: 예전의 토치(Torch) 및 카페2(Caffe2) 프레임워크를 기반  
  파이썬을 스크립팅 언어로 사용하며, 진화된 토치 C/CUDA 백엔드를 사용  
  각 반복 단계에서 즉석으로 그래프를 재생성  
  플라스크(Flask) 웹 서버로 실행  
  모델 그래프를 만들 때 고정 상태가 아니므로 데이터에 따라 조절이 가능한 유연성

### Data Normalization은 무엇이고 왜 필요한가요?

- $x={x−x_{min}}/{x_{max}−x_{min}}$
- 입력 data의 scale(규모, 폭)에 따라 weight가 bias되는 것을 방지하기 위해 0~1 사이로 값의 scale을 비슷하게 줄여줌
- Train에도 도움됨
- 참고: https://skyil.tistory.com/50

- Standardization: $ z(x) = {x-m\over\delta} $ 를 벗어나는 값을 지워서 ML 모델이 일반적인 경우에 집중해 올바를 결과를 내게 도와줌

### 알고있는 Activation Function에 대해 알려주세요. (Sigmoid, ReLU, LeakyReLU, Tanh 등)

![](https://images.velog.io/images/hanlyang0522/post/345ef903-f85e-43c1-9b42-55886bc18ce0/image.png)

- Sigmoid: output값을 0에서 1사이로 만들어준다. 데이터의 평균은 0.5를 갖게된다.  
  위 그림에서 시그모이드 함수의 기울기를 보면 알 수 있듯이 input값이 어느정도 크거나 작으면 기울기가 아주 작아진다.  
  이로인해 생기는 문제점은 vanishing gradient현상이 있다.

- Tanh: 그림에서 보면 알 수 있듯이 시그모이드 함수와 거의 유사하다.  
  차이는 -1~1값을 가지고 데이터의 평균이 0이라는 점이다. 데이터의 평균이 0.5가 아닌 0이라는 유일한 차이밖에 없지만 대부분의 경우에서 시그모이드보다 Tanh가 성능이 더 좋다. --> tanh의 기울기가 더 높기 때문에 train에서 성능이 더 좋음
  그러나 시그모이드와 마찬가지로 Vanishing gradient라는 단점이 있다.

- ReLU: 대부분의 경우 일반적으로 ReLU의 성능이 가장 좋기때문에 ReLU를 사용한다.  
  대부분의 input값에 대해 기울기가 0이 아니기 때문에 학습이 빨리 된다.  
  학습을 느리게하는 원인이 gradient가 0이 되는 것인데 이를 대부분의 경우에서 막아주기 때문에 시그모이드, Tanh같은 함수보다 학습이 빠르다.
  그림을 보면 input이 0보다 작을 경우 기울기가 0이기 때문에 대부분의 경우에서 기울기가 0이 되는것을 막아주는게 납득이 안 될수 있지만 실제로 hidden layer에서 대부분 노드의 z값은 0보다 크기 때문에 기울기가 0이 되는 경우가 많지 않다.  
  단점으로는 위에서 언급했듯이 z가 음수일때 기울기가 0이라는 것이지만 실제로는 거의 무시할 수 있는 수준으로 학습이 잘 되기 때문에 단점이라 할 수도 없다.

- leaky ReLU: ReLU와 유일한 차이점으로는 max(0, z)가 아닌 max(0.01z, z)라는 점  
  즉, input값인 z가 음수일 경우 기울기가 0이 아닌 0.01값을 갖게 된다.  
  leaky ReLU를 일반적으로 많이 쓰진 않지만 ReLU보다 학습이 더 잘 되긴 한다.

- 참고: https://ganghee-lee.tistory.com/32

### 오버피팅일 경우 어떻게 대처해야 할까요?

오버피팅: train loss는 줄지만, eval loss는 안 줄때

1. 데이터 양 늘리기  
   데이터의 양이 적을 경우, 해당 데이터의 특정 패턴이나 노이즈까지 쉽게 암기하기 되므로 과적합 현상이 발생할 확률이 늘어납니다.
2. ~~모델 복잡도 줄이기~~  
   ~~복잡도: 은닉층(hidden layer)의 수나 매개변수의 수~~
   --> 오히려 모델의 크기를 키우는게 답일수도
3. Regularization 사용
4. Dropout 사용
5. Norm penalty 적용

### 하이퍼 파라미터는 무엇인가요?

Keyword: 직접 세팅
Answer: learning rate나 SVM에서의 C, sigma 값, KNN에서의 K값 등 모델링할 때 사용자가 직접 세팅해주는 값

- A model hyperparameter is a configuration that is external to the model and whose value cannot be estimated from data.

### Weight Initialization 방법에 대해 말해주세요. 그리고 무엇을 많이 사용하나요?

Keyword: Gaussian sampling, LeCun init, Xavier init, He init  
Answer: Gaussian sampling하거나, 이전 node 수에 영향을 받는 LeCun init, 다음 node 수에도 영향을 받고 uniform/normal 분포를 따르는 Xavier init, He init 등이 있다  
Activation function이 sigmoid, tanh일 경우 Xavier init을, ReLU일 경우 He init을 사용함

---

### 요즘 Sigmoid 보다 ReLU를 많이 쓰는데 그 이유는?

- Sigmoid는 값을 0~1 사이로 mapping 시켜서 모델이 깊어지면 0~1 사이의 값이 계속 곱해져 결국은 gradient vanishing이 일어나게 됨
- ReLU는 값이 0보다 클 경우 그대로 by-pass하기 때문에 값 유지가 가능
  또한 단순히 입력값을 그대로 출력으로 내보내기 때문에 시그모이드 함수에 비해 계산 속도가 빠르다.

### Non-Linearity라는 말의 의미와 그 필요성은?

- 데이터가 복잡해지고, feature들의 차원이 증가하면서 데이터의 분포가 선형적이지 않고 비선형적으로 나타나면서 단순한 선형의 boundary로는 표현이 불가능하기 때문에 비선형의 boundary가 필요하기 때문에 non-linear가 필요합니다.
  Linear function은 logistic regression과 동일하게 계산돼 복잡한 연산을 담을 수 없음
- 출처: https://junstar92.tistory.com/122 [별준 코딩]
