###  딥러닝은 무엇인가요? 딥러닝과 머신러닝의 차이는?
   - Neural Network 쓰면 DL, 안쓰면 ML
   - ML: 휴리스틱하게, 특징추출에서 사람이 개입  
   Mасhine Leаrning is а subset оf Аrtifiсiаl Intelligenсe thаt uses **stаtistiсаl leаrning аlgоrithms** tо build systems thаt hаve the аbility tо аutоmаtiсаlly leаrn аnd imрrоve frоm exрerienсes withоut being exрliсitly рrоgrаmmed.   
   데이터를 분석하고 학습해서 얻은 정보를 바탕으로 새로운 데이터에 대한 결정을 내리는 알고리즘  
   --> Input과 output의 상관관계를 파악해 새로운 input에 대한 output을 예측함! 이때 쓰이는게 stаtistiсаl leаrning аlgоrithms
   - DL: 학습을 통해 end-to-end, data dependent


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
   - 참고: https://skyil.tistory.com/50



---
###  요즘 Sigmoid 보다 ReLU를 많이 쓰는데 그 이유는?
   - Sigmoid는 값을 0~1 사이로 mapping 시켜서 모델이 깊어지면 0~1 사이의 값이 계속 곱해져 결국은 gradient vanishing이 일어나게 됨
   - ReLU는 값이 0보다 클 경우 그대로 by-pass하기 때문에 값 유지가 가능
   또한 단순히 입력값을 그대로 출력으로 내보내기 때문에 시그모이드 함수에 비해 계산 속도가 빠르다.

### Non-Linearity라는 말의 의미와 그 필요성은?
   - 데이터가 복잡해지고, feature들의 차원이 증가하면서 데이터의 분포가 선형적이지 않고 비선형적으로 나타나면서 단순한 선형의 boundary로는 표현이 불가능하기 때문에 비선형의 boundary가 필요하기 때문에 non-linear가 필요합니다.
   Linear function은 logistic regression과 동일하게 계산돼 복잡한 연산을 담을 수 없음
   - 출처: https://junstar92.tistory.com/122 [별준 코딩]