### 알고 있는 metric에 대해 설명해주세요. (ex. RMSE, MAE, recall, precision ...)

- recall: GT 중에서 얼마나 재현했는가?
- precision: 예측한 값 중에서 GT를 얼마나 표현했는가?
- RMSE, MAE도 classify가 아닌 경우에 metric으로 사용할 수 있음

### 정규화를 왜 해야할까요? 정규화의 방법은 무엇이 있나요?

- Scale이 크게 차이가 나면 scale 자체도 feat이라고 생각하고 학습하기 때문에 normalize함

### Local Minima와 Global Minima에 대해 설명해주세요.

- Local Minima: 경사하강법을 사용할 때 경사도가 0이지만 최소점은 아닌 지점
  Global Minima: 경사하강법을 사용할 때 경사도가 0이고 최소점인 지점
  local minima 중 가장 낮은 cost function 리턴 값을 가지는 지점이 global minima
- lr이 작을 경우 local minima에 빠지기 쉽다는 단점이 있고, 이를 해결하기 위해 scheduler를 사용함

### 차원의 저주에 대해 설명해주세요.

![](https://images.velog.io/images/hanlyang0522/post/b90eafb0-de2e-44d5-b867-21385cc59446/image.png)

- data의 차원(feature, 고려해야될 정보, label)이 너무 많아져서 오히려 model의 성능이 떨어지는 현상
- 차원이 커지면 pattern을 찾기 어려워짐
- 차원을 줄이는 알고리즘 PCA, LDA, LLE, MDS 등을 사용

### dimension reduction기법으로 보통 어떤 것들이 있나요?

- 이유) Dimension이 늘어나면 차원에 저주에 걸릴 수 있음
- 피처 추출 (Feature Extration) : 높은 차원의 raw Feature들을 더 필요한 요소로 추출하는 기법
  - PCA(Principal component analysis)
  - LDA(Linear discriminant analysis)
  - NMF(Non-negativ matrix facotrization)
- 피처 선택 (Feature Selection) : 모든 Feature들 중 필요한 것들만 선택하는 기법  
  EDA 보고 사람이 휴리스틱하게 선택
  - Filtering : leave out dimenstions that do not help much
  - Wrapper : use an external heuristic to select dimensions
  - Embedded : put feature selection into the loss function
- 참고: https://wooono.tistory.com/249  
  https://wikidocs.net/16599

### PCA는 차원 축소 기법이면서, 데이터 압축 기법이기도 하고, 노이즈 제거기법이기도 합니다. 왜 그런지 설명해주실 수 있나요?

- PCA: 여러개의 feature 중에서 가장 중요한 feature만 선택하는 기법
- 결국은 feature(dimension)의 수를 줄이기 때문에 모든 효과가 발생

- 참고: https://bkshin.tistory.com/entry/%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D-9-PCA-Principal-Components-Analysis

### LSA, LDA, SVD 등의 약자들이 어떤 뜻이고 서로 어떤 관계를 가지는지 설명할 수 있나요?

Keyword: 행렬곱 분해, truncated SVD, 토픽 모델링
Answer: SVD(특이값 분해)는 A가 m\*n 행렬일 때 m\*m 직교행렬, n\*n 직교행렬, m\*n 직사각형렬의 행렬곱으로 분해하는 것
LSA(잠재 의미 분석)는 절단된 SVD(truncated SVD)를 이용해 차원을 축소시키고, 단어의 잠재적인 의미를 이끌어냄
LDA는 LSA의 단점을 개선하여 탄생한 알고리즘으로 토픽 모델링에 보다 적합한 알고리즘

- 직교행렬(orthogonal matrix): 자신과 자신의 전치 행렬(transposed matrix)의 곱 또는 이를 반대로 곱한 결과가 단위행렬(identity matrix)이 되는 행렬
- 대각행렬(diagonal matrix): 주대각선을 제외한 곳의 원소가 모두 0인 행렬
- LDA는 축을 찾는 기법

- 참고: https://wikidocs.net/24949

### Markov Chain을 고등학생에게 설명하려면 어떤 방식이 제일 좋을까요?

Keyword: 오늘 날씨, 어제 날씨  
Answer: 어제 날씨를 보고 오늘 날씨를 맞추듯, 바로 방금 전 상태만 보고 현재 상태를 맞추는 형태

- Markov Chain은 마르코프 성질을 가진 이산시간(discrete time) 확률과정(stochastic process)을 뜻하며,  
  마르코프 성질은 ‘과거 상태가 미래 상태에 전혀 영향을 미치지 않고, 오로지 현재 상태만 미래 상태에 영향을 미친다’라는 의미

### 텍스트 더미에서 주제를 추출해야 합니다. 어떤 방식으로 접근해 나가시겠나요?

Keyword: 잠재 디리클레 할당(Latent Dirichlet Allocation, LDA)
Answer:

- 참고: https://huidea.tistory.com/130

### SVM은 왜 반대로 차원을 확장시키는 방식으로 동작할까요? SVM은 왜 좋을까요?

Keyword:
Answer: Support Vector Machine(SVM)은 원 훈련(또는 학습)데이터를 비선형 매핑(Mapping)을 통해 고차원으로 변환

### 다른 좋은 머신 러닝 대비, 오래된 기법인 나이브 베이즈(naive bayes)의 장점을 옹호해보세요.

Keyword: Supervised Learning, 적은 train set
Answer: Supervised Learning에서 매우 효율적이며, 분류에 필요한 파라미터를 추정하기 위한 트레이닝 데이터의 양이 매우 적다

- 나이브 베이즈 분류는 베이즈 정리에 기반한 통계적 분류 기법, 가장 단순한 지도 학습 (supervised learning) 중 하나  
  나이브 베이즈 분류기는 빠르고, 정확하며, 믿을만한 알고리즘. 정확성도 높고 대용량 데이터에 대해 속도도 빠름.
  N-gram

### 회귀 / 분류시 알맞은 metric은 무엇일까?

Keyword:
Answer: 회귀엔 MSE, MAE, R2를 사용하고 분류엔 accuracy, precision, recall과 이를 조합한 F1 score를 사용

- RSS: 단순 오차 제곱 합
- MSE: L2 score, RSS의 평균
- MAE: L1 score, MSE보다 outlier에 robust
- RMSE: MSE에 루트 씌워서 outlier
- R2: 결정계수, 1-(RSS/전체 분산), 회귀 모델의 설명력을 표현하는 지표, 잘 예측할수록 1에 가까워짐

- Accuracy: (TP+TN) / (TP+TN+FP+FN), 분류 결과가 얼마나 True로 나왔느냐
- Precision: TP/(TP+FP), ‘모델이 P라고 분류한 데이터 중에서’ 실제로 P인 데이터의 비율
- Recall: TP/(TP+FN), ‘실제 P인 데이터 중에서’ 모델이 P라고 잘 예측한 데이터의 비율
- FPR: FP/(FP+TN), False Positive Rate, 실제로 N인 데이터 중에서 모델이 P라고 잘못 분류한 데이터의 비율
- F1 score: 정밀도와 재현율의 가중 조화평균

---

### 좋은 모델의 정의는 무엇일까요?

- 데이터의 패턴을 잘 학습한 모델 --> robust한 모델?
- outlier를 잘 걸러내고, 새로운 data에 대해서도 성능이 좋은 모델?

### Association Rule의 Support, Confidence, Lift에 대해 설명해주세요.

Keyword:
Answer: Support: 전체 경우의 수에서 두 아이템이 같이 나오는 비율
Confidence: X가 나온 경우 중 X와 Y가 함께 나올 비율
Lift: X와 Y가 같이 나오는 비율을 X가 나올 비율과 Y가 나올 비율의 곱으로 나눈 값
1보다 높을 때 positive correlation, 1일때 independent, 1 미만일 때 negatively correlation

- Assiciation rule: 어떤 사건이 얼마나 자주 함께 발생하는지, 서로 얼마나 연관돼있는지 표시하는 것

- 참고: https://process-mining.tistory.com/34

### 최적화 기법중 Newton’s Method와 Gradient Descent 방법에 대해 알고 있나요?

Keyword:
Answer: Newton's method: 방정식 f(x)=0의 해를 근사적으로 찾는 기법
Gradient Descent: f'(x) = 0이 되는 점을 찾는 기법

### 머신러닝(machine)적 접근방법과 통계(statistics)적 접근방법의 둘간에 차이에 대한 견해가 있나요?

Keyword: 성공확률, 신뢰도
Answer: 머신러닝은 예측의 성공확률을 높이는게 목적이고, 통계는 예측의 신뢰도를 중요하게 여김.

- 머신러닝 방법과 전통적 통계분석 방법은 사용 알고리즘, 방법론보다는 사용하는 목적에서 가장 큰 차이가 발생
- 머신러닝 방법은 예측의 성공 확률을 높이는 데에 목적, 따라서 모델의 신뢰도나 정교한 가정은 상대적으로 중요성이 낮아지며, 오버피팅은 어느 정도 감안하더라도 여러 인자를 사용해 예측을 수행한다.
- 전통적 통계분석 방법은 정해진 분포나 가정을 통해 실패 확률을 줄이는 데에 목적, 따라서 모형의 복잡성보다는 단순성을 추구하며, 신뢰도가 중요해진다. 해석 중점

### 인공신경망(deep learning이전의 전통적인)이 가지는 일반적인 문제점은 무엇일까요?

Keyword:
Answer: local minima, overfitting,

- 인공신경망에서 layer를 3개 이상 쌓으면 deep learning

### 지금 나오고 있는 deep learning 계열의 혁신의 근간은 무엇이라고 생각하시나요?

Keyword:
Answer: GPU 등 하드웨어의 발전?
