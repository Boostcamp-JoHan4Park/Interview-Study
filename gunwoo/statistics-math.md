# Statistics/Math  

## Questions  
* [고유값(eigen value)와 고유벡터(eigen vector)에 대해 설명해주세요. 그리고 왜 중요할까요?](#1)  
* [샘플링(Sampling)과 리샘플링(Resampling)에 대해 설명해주세요. 리샘플링은 무슨 장점이 있을까요?](#2)  
* [확률 모형과 확률 변수는 무엇일까요?](#3)  
* [누적 분포 함수와 확률 밀도 함수는 무엇일까요? 수식과 함께 표현해주세요.](#4)  

## Answers  
### #1 

Keyword : 정방행렬, PCA, SVD

n*n 정방행렬 A에 대해 Av = λv 를 만족하는 0이 아닌 열벡터 v를 **고유벡터**라 하고 상수 λ를 **고유값**이라 한다.

고유벡터나 고유값을 기반으로 **특이값 분해(SVD), 주성분 분석(PCA), 유사 역행렬(Pseudo Inverse Matrix)** 등 에 활용하기 때문에 중요하다.

### #2

Keyword : 표본추출, 모집단 추론, k-fold 교차 검증, 부트스트래핑

**샘플링은 모집단에서 임의의 smapling을 뽑아내는 것으로 표본추출을 의미**한다. 모집단 전체에 대해 조사하는게 어렵기 때문에 sampling을 통하여 모집단을 **추론**하는 것이다.

**리샘플링은 가지고 있는 샘플에서 다시 샘플 부분집합을 뽑아서 통계량의 변동성을 확인하는 것**이다.


### #3

Keyword : 분포함수, 밀도함수, 이산확률변수, 연속확률변수, 모수

확률 모형은 분포함수(distribution funtion) 또는 밀도함수(density funtion)라고 불리우는 미리 정해진 함수의 수식을 사용하여 분포의 모양을 정의하는 방법이다. 이 때 분포의 모양을 결정하는 함수의 계수를 분포의 모수(parameter)라고 부른다.

확률변수란 표본공간의 각 단위 사건에 실수 값을 부여하는 함수이다. 무작위 실험을 했을 때, 특정확률로 발생하는 각각의 결과를 수치적 값으로 표현하는 변수이다.

### #4

Keyword : 확률밀도함수(PDF), 누적분포함수(CDF), 미분, 적분

누적 분포 함수란 랜덤 변수 X에 대하여 정의된 확률을 P_x라고 할 때, 다음과 같이 정의되는 함수를 누적 분포 함수(Cumulative Distribution Function, CDF) 라고 한다.

![image](https://user-images.githubusercontent.com/61610411/134526265-aa184286-05e8-464e-8f4a-b18055541726.png)

확률 밀도 함수란 확률 변수의 분포를 나타내는 함수로 확률 밀도 함수 f(x)와 구간 [a,b]에 대해서 확률변수 x가 구간에 포함될 확률 P(a<= X <= b)는 

![image](https://user-images.githubusercontent.com/61610411/134526579-df75bf05-caf7-4879-a98d-6263e935798b.png)

확률 밀도 함수와 누적 분포 함수는 미분과 적분의 관계를 갖는다. 확률 밀도 함수를 음의 무한대에서 특정값 a 까지 적분을 하면, a 에 대한 누적 분포 함수를 얻을 수 있다. 반대로 누적 분포 핫무를 미분하면 확률 밀도 함수를 얻을 수 있다.