1. 요즘 Sigmoid 보다 ReLU를 많이 쓰는데 그 이유는?
   Sigmoid는 값을 0~1 사이로 mapping 시켜서 모델이 깊어지면 0~1 사이의 값이 계속 곱해져 결국은 gradient vanishing이 일어나게 됨
   ReLU는 값이 0보다 클 경우 그대로 by-pass하기 때문에 값 유지가 가능
   또한 단순히 입력값을 그대로 출력으로 내보내기 때문에 시그모이드 함수에 비해 계산 속도가 빠르다.

2. Non-Linearity라는 말의 의미와 그 필요성은?
   데이터가 복잡해지고, feature들의 차원이 증가하면서 데이터의 분포가 선형적이지 않고 비선형적으로 나타나면서 단순한 선형의 boundary로는 표현이 불가능하기 때문에 비선형의 boundary가 필요하기 때문에 non-linear가 필요합니다.
   Linear function은 logistic regression과 동일하게 계산돼 복잡한 연산을 담을 수 없음

출처: https://junstar92.tistory.com/122 [별준 코딩]

3. 딥러닝은 무엇인가요? 딥러닝과 머신러닝의 차이는?
   NN 쓰면 DL, 안쓰면 ML
   ML은 휴리스틱하게, 특징추출에서 사람이 개입
   DL은 학습을 통해 end-to-end로, data dependency

4. Cost Function과 Activation Function은 무엇인가요?
   cost:
