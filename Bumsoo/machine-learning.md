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
  - Filtering : leave out dimenstions that do not help much
  - Wrapper : use an external heuristic to select dimensions
  - Embedded : put feature selection into the loss function

### PCA는 차원 축소 기법이면서, 데이터 압축 기법이기도 하고, 노이즈 제거기법이기도 합니다. 왜 그런지 설명해주실 수 있나요?

- PCA: 여러개의 feature 중에서 가장 중요한 feature만 선택하는 기법
- 결국은 feature(dimension)의 수를 줄이기 때문에 모든 효과가 발생

- 참고: https://bkshin.tistory.com/entry/%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D-9-PCA-Principal-Components-Analysis

---

### 좋은 모델의 정의는 무엇일까요?

- 데이터의 패턴을 잘 학습한 모델 --> robust한 모델?
- outlier를 잘 걸러내고, 새로운 data에 대해서도 성능이 좋은 모델?
