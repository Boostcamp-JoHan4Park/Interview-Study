## 딥러닝은 무엇인가요? 딥러닝과 머신러닝의 차이는?

Keyword: Neural network, feature extraction  
Answer: 딥러닝은 neural network를 이용해 ML 학습을 수행하는 것으로, ML과의 가장 큰 차이점은 feature selection에 사람이 개입하지 않는다는 것입니다

- ML: 휴리스틱하게, 특징선택에서 사람이 개입  
  Mасhine Leаrning is а subset оf Аrtifiсiаl Intelligenсe thаt uses **stаtistiсаl leаrning аlgоrithms** tо build systems thаt hаve the аbility tо аutоmаtiсаlly leаrn аnd imрrоve frоm exрerienсes withоut being exрliсitly рrоgrаmmed.  
  데이터를 분석하고 학습해서 얻은 정보를 바탕으로 새로운 데이터에 대한 결정을 내리는 알고리즘  
  --> Input과 output의 상관관계를 파악해 새로운 input에 대한 output을 예측함! 이때 쓰이는게 stаtistiсаl leаrning аlgоrithms
- DL: 학습을 통해 end-to-end, data dependent
- 가장 큰 차이는 feature selection!!

<br/>

## Cost Function과 Activation Function은 무엇인가요?

Keyword: 오차 계산, 선형 to 비선형  
Answer: Cost function은 모델의 예측값과 오차를 계산해주는 함수로 학습 뱡향을 어느 방향으로 얼마나 개선할지 판단하는 지표가 됩니다. Activation function은 선형 함수를 비선형함수로 만들어 표현력을 더 키워주는 함수입니다.

- Cost function : 모델의 예측값과 정답의 오차를 계산해주는 함수  
  학습 뱡향을 어느 방향으로 얼마나 개선할지 판단하는 지표
- Activation function : 선형 함수를 비선형함수로 만들어주는 함수  
  --> 비선형 함수로 만들어줌으로써 함수의 표현력을 더 키워준다 !

<br/>

## Tensorflow, PyTorch 특징과 차이가 뭘까요?

Keyword: Define and/by run  
Answer: Tensorflow는 단일 데이터 흐름 그래프를 만들고 그래프 코드를 성능에 맞게 최적화한 다음 모델을 학습하므로 더 쉽게 다른 언어나 모듈에 적용이 가능합니다. PyTorch는 각 반복 단계에서 즉석으로 그래프를 재생성하므로 모델 그래프를 만들 때 고정 상태가 아니므로 데이터에 따라 조절이 가능한 유연성을 갖고 있습니다.

- Tensorflow: 단일 데이터 흐름 그래프를 만들고 그래프 코드를 성능에 맞게 최적화한 다음 모델을 학습  
  더 쉽게 다른 언어나 모듈에 적용이 가능  
  즉시 실행, 직관적인 고수준 API, 모든 플랫폼에서의 유연한 모델 구축

- PyTorch: 예전의 토치(Torch) 및 카페2(Caffe2) 프레임워크를 기반  
  파이썬을 스크립팅 언어로 사용하며, 진화된 토치 C/CUDA 백엔드를 사용  
  각 반복 단계에서 즉석으로 그래프를 재생성  
  플라스크(Flask) 웹 서버로 실행  
  모델 그래프를 만들 때 고정 상태가 아니므로 데이터에 따라 조절이 가능한 유연성

<br/>

## Data Normalization은 무엇이고 왜 필요한가요?

Keyword: weight bias 방지  
Answer: Data Normalization는 입력 data의 scale을 비슷한 크기로 맞춰줘 weight가 scale에 따라 bias되는 것을 방지합니다.

- $x={x−x_{min}}/{x_{max}−x_{min}}$
- 입력 data의 scale(규모, 폭)에 따라 weight가 bias되는 것을 방지하기 위해 0~1 사이로 값의 scale을 비슷하게 줄여줌
- Train에도 도움됨
- 참고: https://skyil.tistory.com/50

- Standardization: $ z(x) = {x-m\over\delta} $ 를 벗어나는 값을 지워서 ML 모델이 일반적인 경우에 집중해 올바를 결과를 내게 도와줌

<br/>

## 알고있는 Activation Function에 대해 알려주세요. (Sigmoid, ReLU, LeakyReLU, Tanh 등)

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

<br/>

## 오버피팅일 경우 어떻게 대처해야 할까요?

Keyword: 데이터 양 늘리기, regularization, dropout, norm penalty  
Answer: Overfitting이 일어날 경우에는 augmentation를 이용해 데이터의 절대적인 양을 늘리거나 regularization, dropout을 사용하고 norm penalty를 사용해 weight가 너무 커지지 않게 만듭니다.

- 오버피팅: train loss는 줄지만, eval loss는 안 줄때
  1. 데이터 양 늘리기  
     데이터의 양이 적을 경우, 해당 데이터의 특정 패턴이나 노이즈까지 쉽게 암기하기 되므로 과적합 현상이 발생할 확률이 늘어납니다.
  2. ~~모델 복잡도 줄이기~~  
     ~~복잡도: 은닉층(hidden layer)의 수나 매개변수의 수~~
     --> 오히려 모델의 크기를 키우는게 답일수도
  3. Regularization 사용
  4. Dropout 사용
  5. Norm penalty 적용

<br/>

## 하이퍼 파라미터는 무엇인가요?

Keyword: 직접 세팅  
Answer: learning rate나 SVM에서의 C, sigma 값, KNN에서의 K값 등 모델링할 때 사용자가 직접 세팅해주는 값을 말합니다.

- A model hyperparameter is a configuration that is external to the model and whose value cannot be estimated from data.

<br/>

## Weight Initialization 방법에 대해 말해주세요. 그리고 무엇을 많이 사용하나요?

Keyword: Gaussian sampling, LeCun init, Xavier init, He init  
Answer: Gaussian sampling하거나, 이전 node 수에 영향을 받는 LeCun init, 다음 node 수에도 영향을 받고 uniform/normal 분포를 따르는 Xavier init, He init 등이 있다.
Activation function이 sigmoid, tanh일 경우 Xavier init을, ReLU일 경우 He init을 사용함.

- Gaussian: normal distribution

<br/>

## 볼츠만 머신은 무엇인가요?

Keyword: 2 layer  
Answer: 볼츠만 머신(Boltzmann machine)은 볼 수 있는 층(visible layer)과 숨겨진 층(hidden layer)의 두 층으로 구성된 모델입니다. Layer의 모든 node들은 연결돼있습니다.

- 볼츠만 머신(Boltzmann machine)은 볼 수 있는 층(visible layer)과 숨겨진 층(hidden layer)의 두 층으로 구성된 그래픽 모델
- 이 모델에서 각 볼 수 있는 유닛은 숨겨진 유닛들과만 연결되고, 볼 수 있는 유닛들 사이에 그리고 숨겨진 유닛들 사이에는 서로 연결이 없을 때 이를 제한된 볼츠만 머신(RBM: restricted Boltzmann machine)이라 한다

<br/>

## TF, PyTorch 등을 사용할 때 디버깅 노하우는?

Keyword:  
Answer:

<br/>

## 뉴럴넷의 가장 큰 단점은 무엇인가? 이를 위해 나온 One-Shot Learning은 무엇인가?

Keyword: Distance 기반 learning  
Answer: Neural network의 가장 큰 단점은 data의 수가 적을 경우 사용하지 못한다는 점입니다. One-Shot Learning은 이를 개선하기 위해 각 class마다 1개의 image만 사용하고 input image를 각 class별 거리를 측정해 가장 가까운 class로 판정하는 기법입니다.

- Neural network의 단점은 data의 수가 적을 경우 사용하지 못한다는 점
- One-shot learning은 class당 1개의 image만 있고, input image를 각 class별 distance를 측정해 가장 가까운 class로 판별

<br/>

## 요즘 Sigmoid 보다 ReLU를 많이 쓰는데 그 이유는?

### Non-Linearity라는 말의 의미와 그 필요성은?

Keyword: feature의 차원 증가  
Answer: 데이터가 복잡해지고, feature들의 차원이 증가하면서 데이터의 분포가 선형적이지 않고 비선형적으로 나타나면서 단순한 선형의 boundary로는 표현이 불가능하기 때문에 비선형의 boundary가 필요하기 때문에 non-linear가 필요해졌습니다.

### ReLU로 어떻게 곡선 함수를 근사하나?

Keyword: 선형, 비선형의 결합  
Answer: ReLU는 선형(y=x)과 비선형(y=0)의 결합이기 때문에 ReLU가 반복 적용되면 선형부분의 결합으로 곡선 함수를 표현할 수 있습니다.

### ReLU의 문제점은?

Keyword: Input이 0보다 작을 경우  
Answer: Input이 0보다 작을 경우 gradient가 0이 됩니다.

### Bias는 왜 있는걸까?

Keyword: 평행이동  
Answer: 모델이 항상 원점을 기준으로 분포해있지는 않기 때문에 model이 data에 잘 fit하게 평행이동 시켜줍니다.

- Non-linearity: 데이터가 복잡해지고, feature들의 차원이 증가하면서 데이터의 분포가 선형적이지 않고 비선형적으로 나타나면서 단순한 선형의 boundary로는 표현이 불가능하기 때문에 비선형의 boundary가 필요하기 때문에 non-linear가 필요  
   Linear function은 logistic regression과 동일하게 계산돼 복잡한 연산을 담을 수 없음

- 함수를 근사 == 함수를 추정하여 동일한 input을 넣었을 때 output이 유사하게 나오도록 조정하는 과정  
   ReLU는 선형(y=x)과 비선형(y=0)의 결합이기 때문에 ReLU가 반복 적용되면 선형부분의 결합으로 곡선 함수를 표현할 수 있음

- input이 0보다 작을 경우 gradient가 0이 된다

- 모델이 항상 원점을 기준으로 분포해있지는 않기 때문에 model이 data에 잘 fit하게 평행이동 시켜줌

- Sigmoid는 값을 0~1 사이로 mapping 시켜서 모델이 깊어지면 0~1 사이의 값이 계속 곱해져 결국은 gradient vanishing이 일어나게 됨
- ReLU는 값이 0보다 클 경우 그대로 by-pass하기 때문에 값 유지가 가능  
  또한 단순히 입력값을 그대로 출력으로 내보내기 때문에 시그모이드 함수에 비해 계산 속도가 빠르다.

<br/>

## Gradient Descent에 대해서 쉽게 설명한다면?

### GD 중에 때때로 Loss가 증가하는 이유는?

Keyword: learning rate  
Answer: learning rate가 커서 순간적으로 발산하거나, local minimum을 빠져나오기 때문입니다.

### Back Propagation에 대해서 쉽게 설명 한다면?

Keyword: loss update  
Answer: Ground truth와 estimated output의 차이가 얼마나 나는지 구한 후 오차loss만큼 weight를 업데이트합니다.

<br/>

## Local Minima 문제에도 불구하고 딥러닝이 잘 되는 이유는?

Keyword: weight initialize, pre-train  
Answer: Weight을 단순히 zero initialize하는게 아니라 activation function에 따라 적절한 초기화 방법이 등장했고, pre-training을 통해 효과적으로 학습을 시킬 수 있게 됐습니다.

### GD가 Local Minima 문제를 피하는 방법은?

Keyword: Learning rate scheduler  
Answer: Learning rate scheduler 등을 통해 주기적으로 lr의 크기를 변경해 local minima를 빠져나가게 할 수 있음

### 찾은 해가 Global Minimum인지 아닌지 알 수 있는 방법은?

Keyword: 실험 반복  
Answer: 차원이 높을수록 local minima에 빠질 위험이 적기 때문에 차원을 높여서 실험, seed를 변경하며 여러번 실험합니다.

<br/>

## Training 세트와 Test 세트를 분리하는 이유는?

Keyword: Overfit  
Answer: Train에서 test 세트를 학습하면 모델이 추정하는 분포가 test에 overfit해 unseen data에 대한 성능이 떨어질 위험이 있기 때문입니다.

### Validation 세트가 따로 있는 이유는?

Keyword: 모델 성능 평가  
Answer: 모델의 성능을 평가하기 위해서 사용합니다.

### Test 세트가 오염되었다는 말의 뜻은?

Keyword: 테스트 데이터 분리 실패  
Answer: 테스트용으로 분리해야하는 데이터가 학습 데이터에 반영됐을 때 사용합니다.

### Regularization이란 무엇인가?

Keyword: penalty  
Answer: L1, L2 regularization처럼 모델에 penalty를 줘서 train data에 대한 perfect fit을 포기하는 대신 testing accuracy를 높이고자 하는 기법

<br/>

## Batch Normalization의 효과는?

Keyword: 학습 속도 개선, input data의 variance 조정  
Answer: Learning rate를 높일 수 있어 학습 속도를 개선하고, 학습할 때마다 출력값을 normalize하기 때문에 weight initialize에 대한 의존성이 적어진다. 가중치의 scale을 조정해 gradient exploding/vanishing을 방지한다

- 각 batch 단위로 평균과 분산을 이용해 입력 데이터의 분포의 차이(internal covariant shift)를 조정

- 참고: https://eehoeskrap.tistory.com/430
  https://m.blog.naver.com/laonple/220808903260

### Dropout의 효과는?

Keyword: co-adaptation 방지, 다양한 모델 학습  
Answer: 학습 데이터에 의해 각 node들이 co-adaptation 되는 현상을 방지하고 여러 개의 모델을 학습시키는 것과 같은 작용을 해 regularization 효과를 기대할 수 있다.

### BN 적용해서 학습 이후 실제 사용시에 주의할 점은? 코드로는?

Keyword: train/inference 구분, moving average 사용  
Answer: inference 시 입력되는 값을 통해 정규화를 하게 되면 모델이 학습을 통해 입력 데이터의 분포를 추정하는 의미 자체가 없어지기 때문에, inference 시에는 결과를 deterministic하게 만들기 위해 미리 저장해돈 mini-batch의 moving average를 이용해 정규화를 하게 됨.

### GAN에서 Generator 쪽에도 BN을 적용해도 될까?

Keyword:  
Answer: DCGAN generator의 마지막 layer와 dicsriminator의 첫번째 layer는 모델이 distribution에 대한 정확한 mean과 scale을 학습하기 위해 BN을 적용하지 않지만, 그 외의 대부분의 layer에는 BN을 적용함
하지만 mini-batch의 크기가 작을 경우 GAN이 생성하는 image가 z code보다 batch normalization의 fluctuation에 영향을 많이 받을 경우 batch간 correlation이 생기는 문제가 발생함.

- 참고: https://kakalabblog.wordpress.com/2017/07/27/gan-tutorial-2016/

## SGD, RMSprop, Adam에 대해서 아는대로 설명한다면?

![](https://images.velog.io/images/hanlyang0522/post/807cea1e-b014-42e2-9be0-156a7b9abcd2/image.png)

Keyword: 기울기를 업데이트 하는 방식  
Answer: SGD는 loss function을 계산할 때 전체 batch가 아니라 일부 데이터(mini-batch)만 사용해 같은 시간에 더 많은 step을 갈 수 있어 local minima에 빠지지 않고 더 좋은 방향으로 수렴할 가능성이 높다. RMSprop은 기울기를 단순 누적하지 않고 weighted moving average를 사용해 최신 기울기를 더 크게 반영하도록 한다. Adam은 momentum과 RMSprop을 결합해 스텝 방향과 사이즈 모두 고려함.

### SGD에서 Stochastic의 의미는?

Keyword: 확률론적인  
Answer: 확률론적인, 약간은 랜덤한 결과, 약간의 불확실성을 포함한 다양한 프로세스를 의미

### 미니배치를 작게 할때의 장단점은?

Keyword: 연산량을 줄임  
Answer: 연산량을 줄여 같은 시간에 더 많은 step을 나갈 수 있다

### 모멘텀의 수식을 적어 본다면?

![](https://images.velog.io/images/hanlyang0522/post/03b9292b-5ea4-494e-923b-69bcd0f6d7a0/image.png)

Keyword: 관성을 적용  
Answer: W를 업데이트 할 때 이전 단계의 업데이트 방향을 반영  
a는 learning rate, m은 모멘텀 계수

- 간단한 MNIST 분류기를 MLP+CPU 버전으로 numpy로 만든다면 몇줄일까?
  - 어느 정도 돌아가는 녀석을 작성하기까지 몇시간 정도 걸릴까?
  - Back Propagation은 몇줄인가?
  - CNN으로 바꾼다면 얼마나 추가될까?
