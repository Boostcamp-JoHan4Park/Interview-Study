# Statistics/Math

## Questions

- [고유값(eigen value)와 고유벡터(eigen vector)에 대해 설명해주세요. 그리고 왜 중요할까요?](#1)
- [샘플링(Sampling)과 리샘플링(Resampling)에 대해 설명해주세요. 리샘플링은 무슨 장점이 있을까요?](#2)
- [확률 모형과 확률 변수는 무엇일까요?](#3)
- [누적 분포 함수와 확률 밀도 함수는 무엇일까요? 수식과 함께 표현해주세요.](#4)
- [조건부 확률은 무엇일까요?](#5)
- [공분산과 상관계수는 무엇일까요? 수식과 함께 표현해주세요.](#6)
- [신뢰 구간의 정의는 무엇인가요?](#7)
- [p-value를 모르는 사람에게 설명한다면 어떻게 설명하실 건가요?](#8)
- [R square의 의미는 무엇인가요?](#9)
- [평균(mean)과 중앙값(median)중에 어떤 케이스에서 뭐를 써야할까요?](#10)  
- [중심극한정리는 왜 유용한걸까요?](#11)  
- [엔트로피(entropy)에 대해 설명해주세요. 가능하면 Information Gain도요.](#12)
- [어떨 때 모수적 방법론을 쓸 수 있고, 어떨 때 비모수적 방법론을 쓸 수 있나요?](#13)
- [“likelihood”와 “probability”의 차이는 무엇일까요?](#14)
- [통계에서 사용되는 bootstrap의 의미는 무엇인가요.](#15)
- [모수가 매우 적은 (수십개 이하) 케이스의 경우 어떤 방식으로 예측 모델을 수립할 수 있을까요?](#16)
- [베이지안(Bayesian approach)과 프리퀀티스트(frequentist approach) 간의 입장차이를 설명해주실 수 있나요?](#17)
- [검정력(statistical power)은 무엇일까요?](#18)
- [missing value가 있을 경우 채워야 할까요? 그 이유는 무엇인가요?](#19)

---

### #1
Q : 고유값(eigen value)와 고유벡터(eigen vector)에 대해 설명해주세요. 그리고 왜 중요할까요?
<details><summary> Keyword : 정방행렬, PCA </summary>
∟ A : 행렬은 선형변환을 위해서 많이 사용되게 하는데, 이 행렬이 방향에 대한 부분을 변환하지 못하는 벡터가 존재하는데 그 벡터가 고유벡터이다. 행렬로 인해 늘어난 상수 배수가 그 행렬의 고유벡터에 의한 고유값이라고 한다. 고유값이나 고유벡터는 정방행렬에서 사용하게 되고 이를 정방행렬이 아닌 mxn 행렬에서 적용할 수 있는것에 특이값 분해 방법이 있다. 이를 활용할 수 있는 것은 PCA(주성분 분석)에 사용하여 고차원의 벡터를 저차원의 벡터로 치환하여 사용할 수 있도록 한다.
주성분 분석(PCA), 특이값 분해(SVD), 유사 역행렬(Pseudo Inverse Matrix)_무어펜로즈

</details>
<br>

### #2
Q : 샘플링(Sampling)과 리샘플링(Resampling)에 대해 설명해주세요. 리샘플링은 무슨 장점이 있을까요?
<details><summary> Keyword : 표본추출, 모집단 추론, k-fold 교차 검증, 부트스트래핑 </summary>

∟ A : 샘플링은 표본추출을 통해 만들어진 표본집단이다. 하여 모집단의 특징을 보여줄 수는 있지만, 모집단과의 차이는 존재하게 된다. 하여 신뢰구간을 사용하여 모수(모집단의 평균, 분산 등 모집단을 표현하는 방식)의 범위를 추측할 수 있다. 리샘플링은 샘플링을 통하여 뽑아진 표본집단의 부분집합을 뽑아내어 통계량의 변동성을 확인하는 것으로, K-fold, 부트스트래핑을 예로들수 있다. 

K-fold : 샘플을 k개의 집합으로 나눠서 표본집단 내에서도 샘플링을 진행하여 통계량의 변동성을 확인할 수 있다. 머신러닝에서는 K-1개를 학습에 사용하고, 1개를 Test set으로 사용하여 검증하는 방법으로 많이 사용된다. 

부트스트래핑 : 표본집단에서 복원추출을 통하여 샘플을 꺼내어 하나의 부분집합을 만드는 방식이다.

</details>
<br>

### #3
Q : 확률 모형과 확률 변수는 무엇일까요?
<details><summary>Keyword : Event, 이산, 연속, 분포 근사, 모수 추정, 가우시안 정규 분포</summary>

∟ A : 우선 확률이란, 실생활에서 일어나는 불확실성에 대해 표현하는 수단입니다. 이런 불확실성을 숫자로 표현하여 접근하고 계산할 수 있도록 만든 것입니다. 여기서 **확률 변수**는 어떤 사건(event)가 발생했을때, 어떤 값을 확률로 표현할지 정해야하는 데, 아직 정해지지 않고 다양하게 정의할 수 있기 때문에 변수라 불립니다. 그렇기에 확률 변수는 하나의 함수처럼 보여질 수도 있습니다. 

X : 주사위를 던져서 나온 눈
X : 주사위의 눈이 1이 나올때까지 던진 횟수

위와 같이 주사위의 경우는 각 변수 값이 양의 정수로만 이뤄져있는데, 이렇게 값이 떨어져 있는 경우를 **이산 확률 변수**라고하고, 실수로 연속된 값을 갖게 되면 **연속 확률 변수**라고 합니다.

**확률 모형**은 확률 변수를 선정하고, 데이터를 수집한 이후 데이터의 발생 분포를 잘 근사하기 위한 수학적 모델링입니다. 일반적으로 $p(x|\theta)$로 사용되며, 샘플링된 데이터를 활용하여 모수를 추정하여 분포를 예측하게 됩니다. 가장 많이 사용되는 것은 가우시안 정규 분포가 많이 사용되고 있습니다.

</details>
<br>

### #4
Q : 누적 분포 함수와 확률 밀도 함수는 무엇일까요? 수식과 함께 표현해주세요.
<details><summary>Keyword : 확률밀도함수(PDF), 누적분포함수(CDF), 미분, 적분</summary>

∟ A : 
확률 변수 x가 임의의 실수 집합 B에 포함되는 사건의 확률이 음이 아닌 함수 $f$의 적분으로 주어진다고 할때, 이 때의 X를 연속확률변수라고 하며, 함수 $f(x)$를 **확률밀도함수(PDF, Probability Density Function)** 이라고 합니다. 단 실수 집합 B가 실수 전체일경우 실수 전체에 대한 확률밀도함수의 적분은 1을 만족해야 합니다.
![](https://i.imgur.com/AO6i6Sy.png)
![](https://i.imgur.com/vY6Abm1.png)

**누적분포함수(Cumulative Distribution Function, CDF)** 는 확률변수가 특정 값보다 작거나 같을 확률을 나타내는 함수입니다. 특정 값을 $a$라고 할때, 누적 분포 함수는 다음과 같이 나타낼 수 있습니다.

확률 밀도 함수와 누적 분포 함수는 미분과 적분의 관계를 갖습니다. 확률 밀도 함수를 음의 무한대에서 특정값 a 까지 적분을 하면, a 에 대한 누적 분포 함수를 얻을 수 있습니다. 반대로 누적 분포 함수를 미분하면 확률 밀도 함수를 얻을 수 있습니다.

![](https://i.imgur.com/gRG5l05.png)

</details>
<br>

### #5
Q : 조건부 확률은 무엇일까요?
<details><summary>Keyword : ~가 일어났을때 ~가 일어날 확률 </summary>

∟ A : 조건부 확률은 사건 A 가 일어났다는 전제 하에 사건 B 가 일어날 확률이다. 이는 $P(B|A) = P(B∩A) / P(A)$ 로 표현 가능하다. 이는 베이즈 정리로도 이어지게 된다. 

베이즈 정리는 사전확률과 사후확률의 관계에 대해서 서술한 것으로 새로운 증거로 갱신되는 새로운 주장에 대한 신뢰도를 의미한다. 베이즈 정리를 활용하여 시계열 추론에도 사용하였다.
이는 기존 확률론의 연역적 추론 방법에서 귀납적 추론 방법으로의 패러다임 변화를 만들었다. 

<img src="https://user-images.githubusercontent.com/77658029/149715435-2b38dfa4-2a03-4b7a-bd9a-b00a6860b5d6.png"  width="50%" height="50%"/>

</details>
<br>

### #6
Q : 공분산(Covariance)과 상관계수(Correlation)는 무엇일까요? 수식과 함께 표현해주세요. 
<details><summary>Keyword : </summary>

∟ A :
공분산은 확률변수 X의 편차와 확률변수 Y의 편차를 곱한것의 평균 값으로 두 변수간에 양의 상관관계가 있는지 음의 상관관계를 확인할 수 있다. 하지만, 공분산의 경우 변수의 크기에 따라서 값이 크게 차이나기 때문에 상관 정도를 확인하기 어렵다. 이런 부분을 개선하여 변수의 절대적 크기를 단위화 시켜서 비교한 것이 상관계수이다. 공분산에 각 확률변수의 분산을 나누어주었다. 상관계수는 그 상관성이 얼마나 큰지도 알려준다. -1 또는 1에 가까울수록 상관성이 크고 0에 가까울수록 상관성이 작은 것이다.  
![](./images/2021-09-30-13-18-01.png)
![](./images/2021-09-30-13-24-35.png)

</details>
<br>

### #7
Q : 신뢰 구간의 정의는 무엇인가요?
<details><summary>Keyword : 모집단과 표본집단, 무작위 추출, 중심극한정리</summary>

∟ A : 대부분의 경우 모집단 전체를 조사하는 것은 어렵기 때문에 표본집단을 뽑아 모집단의 특징을 추론하게 된다. 이때 확률분포의 모양과 상관없이 중심극한정리가 성립되게 되는데, 중심극한정리는 모집단에서 임의의 샘플링을 무작위로 진행하여 평균을 추출하여 그 평균값으로 분포를 나타내면 가우시안 정규 분포로 나타나게 된다. 이러한 성질을 이용해 모집단의 모수가 특정 범위안에 들어올 확률을 나타내게 되는데 그것을 신뢰구간이라고 한다. 여기서 표준정규분포에서 사용하는 Z-score를 많이 사용하게 되고,Z-score는 1.96일때 신뢰구간 95%로 많이 사용한다.

출처 : 
https://angeloyeo.github.io/2020/09/15/CLT_meaning.html
https://angeloyeo.github.io/2021/01/05/confidence_interval.html

</details>
<br>

### #8
Q : p-value를 모르는 사람에게 설명한다면 어떻게 설명하실 건가요?
<details><summary>Keyword : 유의 확률, 귀무가설(영가설), 극단적인 결과 관찰</summary>

∟ A : 
처음 가설을 설정하고 그 가설이 맞는지 확인하는 값으로 p-value를 사용해,

우선 동전에서 앞면과 뒷면의 확률이 5:5 라는 가설을 세우고 이 가정이 맞다고 생각하는거야
동전 100개를 던졌을때 모두 앞면이 나올 확률은 정말 낮겠지(1/2^100)

여기서 100개의 동전 던지는 행위를 무수히 많이 실행했을때, 모두 앞면이 나올 확률이 있을거 아니야 이 확률을 p-value라고해 
처음 가정에서는 p-value가 낮은 확률이라고 가정했는데, 이 확률이 큰 값을 가지게되면(기본적으로 0.05, 0.1 이상) 우리가 처음한 가정이 틀린거지, 만약 그 확률이 작다고 하면 그 가정은 유의미한 가정인거야

</details>
<br>

### #9
Q : R square의 의미는 무엇인가요?
<details><summary>Keyword : 결정계수, SSD, RSS, 예측 모형 설명력</summary>

∟ A : 독립변수가 종속변수에 대해 얼마만큼의 설명력을 가지게 되는지 나타내는 수치로, 평균과 비교해서 예측한 모형이 얼마나 잘 예측하는지를 나타내며 **결정계수**라고 불립니다. 예측한 모델과 실제 값들의 차이를 잔차(resudial)라고 하는데, 잔차의 제곱합을 RSS라고 하고 실제 값들의 평균과 값의 차이를 제곱하여 더한 값이 RSS라고 합니다. 수식으로 나타내면 $R^2 = (SSD - RSS)/(SSD) = 1 - RSS/SSD$
SSD(Sum of Squares of Deviations), RSS(Residiul Sum of Squares)
<img src="https://user-images.githubusercontent.com/77658029/149724023-3b98fbca-ff45-4d22-9bd2-3f20df01bd16.png"  width="50%" height="50%"/>

출처 :
https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=victoria1590&logNo=220635485424

</details>
<br>

### #10
Q : 평균(mean)과 중앙값(median)중에 어떤 케이스에서 뭐를 써야할까요?
<details><summary>Keyword : Outlier</summary>

∟ A : 대체적으로 평균을 많이 사용하지만 극단적인 값으로 인해서 평균값이 크게 움직이게 된다면 평균보단 중앙값을 사용하는 것이 더 분포를 잘 설명할 수 있다. 

만약 회사에 11명의 사람이 있는데 평균연봉을 확인할때, 제일 많이 받는 사람이 6억을 받고 나머지 사람들이 5천만원을 받는다고 했을때, 평균 연봉은 1억이 된다. 하지만 90% 이상의 사람이 5천만원을 받고 있기 때문에, 평균보단 중앙값이 더 좋은 표현력을 가진다고 할 수 있다. 

하지만 반대로 이런 극단적인 경우가 없는 경우는 평균값이 분포를 더 잘 표현할 수 있다.

</details>
<br>

### #11
Q : 중심극한정리는 왜 유용한걸까요?
<details><summary>Keyword : 통계적 유의성 검정, 신뢰구간 추론</summary>

∟ A : 표본의 크기가 커질수록 표본 평균의 분포는 모집단의 분포 모양과는 관계없이 정규분포에 가까워진다는 정리로, 서로 독립(i.i.d.)가정이 성립하고, 평균과 표준편차만 알고 있으면 분포에 대한 어떤 정보가 없더라도, 표본평균의 분포가 "어떤 모양"을 가지고 수렴하는지 알 수 있다.
중심극한정리는 통계적 유의성 검정을 위한 이론적 토대가 되어 신뢰구간을 확보해 전체 집단을 대략적으로 추론해 볼 수 있고, 어떤 가정의 유의성을 검증할 수 있다. 

출처 : 
https://namu.wiki/w/%EC%A4%91%EC%8B%AC%EA%B7%B9%ED%95%9C%EC%A0%95%EB%A6%AC

</details>
<br>

### #12
Q : 엔트로피(entropy)에 대해 설명해주세요. 가능하면 정보량(Information Gain)도요.
<details><summary>Keyword : 무질서도, 희소성과 유용성</summary>

∟ A : 엔트로피는 열역학 제2법칙으로 무질서도가 커지는 방향으로 변화한다는 이론입니다. 여기서 무질서도는 일을 할 수 있는 유용한 에너지가 없는 상태를 의미합니다. 하여 유용한 에너지가 높으면 엔트로피가 작고, 쓸모 없는 에너지가 높으면 엔트로피가 높은 상황입니다. 엔트로피를 정보/통계적으로 적용시켜봤을때, 정보가 가지는 유용성과 희소성의 관계로 비교해볼 수 있는데, 정보의 희소성이 높으면 그 정보가 가지는 유용성이 높아지게 되는 것 입니다. 수식으로 표현하면 $I(x_i) = -ln(p(x_i))$ 와 같습니다. 

예를 들어 100원짜리 동전을 모델에 학습시킨다고 했을 때, 데이터가 앞면과 뒷면의 데이터의 비율이 9:1비율로 있다고 하면 앞면 데이터의 유용성은 떨어지게 되고, 뒷면 데이터의 유용성은 증가할 것 입니다.

출처 : 
https://code13.tistory.com/253
https://bskyvision.com/389

</details>
<br>

### #13
Q : 어떨 때 모수적 방법론을 쓸 수 있고, 어떨 때 비모수적 방법론을 쓸 수 있나요?
<details><summary>Keyword : 모수(모집단 통계량), 중심극한정리, </summary>

∟ A : 
통계적 의미
모수적 추론 : 미지의 모수가 특정한 분포 함수식이 있다고 가정하고, 모수에 대해서 추론하는 방법(a branch of statistics that assumes data has come from a type of probability distribution)
비모수적 추론 : 모집단에 대한 가정을 특정한 분포 함수의 모수형으로 하지 않는 추론

Model 적인 의미
Parametric model: The model has a fixed number of parameters. 모델의 파라미터 수가 정해져 있다.
Non-parametric model: The number of parameters grow with the amount of training data. 파라미터의 수가 학습 데이터의 크기에 따라 달라진다. 

Parametric model: Linear regression, Logistic regression, Bayesian inference, Neural network(CNN, RNN 등) 등. 모델이 학습해야 하는 것이 명확히 정해져 있기 때문에 속도가 빠르고, 모델을 이해하기가 쉽다는 장점이 있다. 하지만 데이터의 분포가 특정한 분포를 따른다는 가정을 해야 하기 때문에 flexibility가 낮고, 간단한 문제를 푸는 데에 더 적합하다는 단점을 가진다. 

Non-parametric model: Decision tree, Random forest, K-nearest neighbor classifier 등. 데이터가 특정한 분포를 따른다는 가정을 하지 않기 때문에 더 flexible하다는 장점이 있다. 하지만 속도가 느린 경우가 많고, 더 큰 데이터를 필요로 하는 경우가 있으며 모델이 왜 그런 형태가 되었는지에 대한 명확한 설명을 하기가 쉽지 않다. 


출처 : 
https://zzanhtt.tistory.com/18 -> 통계
https://immunologystudyroom.tistory.com/46 -> 통계
https://brunch.co.kr/@seoungbumkim/7#comment 
https://process-mining.tistory.com/131 -> ML 쪽

</details>
<br>

### #14
Q : “likelihood”와 “probability”의 차이는 무엇일까요?
<details><summary>Keyword : </summary>

∟ A : 확률은 하나의 고정된 분포에서 특정 변수가 관측될 가능성을 나타내는 것이고, 가능도는 관측된 변수들이 분포의 변화에 따라 바뀌는 확률값을 가능도라고 하고 그 분포에서의 가능도는 그 가능도를 모두 곱한 값으로 사용한다. 이것은 분포가 변화함에 따라 분포에서 보여지는 확률값을 나타내지만 가능도는 확률이 아니기 때문에 넓이가 1이 될 수 있고, 값이 1보다 커질 수 있다.
하지만 대부분 소수점 자리로, 변수들이 많아지게 되면 너무 작은 값들의 곱이 계속되기 때문에 컴퓨터 연산에서의 오차가 크게 작용하게 되어 Log를 취해 더하는 방식으로 많이 사용된다.

확률 대신 가능도를 썼을때의 장점 : 
확률밀도함수에서 범위가 아닌 데이터가 주어졌을 때에 적절한 모수를 구할 수 있음
모집단에 대한 정확한 분포를 알 수 없을 때, 여러 모수로 비교하여 그 순간에 최적의 모수를 구할 수 있음

확률 : 
이항분포에서 보면 아래와 같이 발생할 확률이 주어지고, 10번 시행시 k값 즉 몇번 이기는지, 동전의 앞면이 몇번 나왔는지를 알면 그 갯수에 따른 확률을 알 수가 있다. 이것이 확률의 개념이고.
$p = p^k * (1 - p)^{(10-k)}$

가능도 : 
확률에서 정해진 모수를 Theta로 잡고(이항분포에서 평균은 np), k값을 임의의 실수로 정해져 있다고 하면 가능도 함수가 그려지고, 이때의 값이 최대가 되게 하는 Theta값을 구하게 되면, 0.3의 값이 나오게 된다. 이 값은 10번 시행했을때 앞면이 3번 나오고, 뒷면이 7번 나오는 확률을 가장 높게 만드는 $\theta$값이 나오게 되는데, 이 개념이 가능도이다.
$Likelihood = \theta^k * (1 - \theta)^{(n-k)}$ → $Likelihood = \theta^3 * (1 - \theta)^{(10-3)}$

</details>
<br>

### #15
Q : 통계에서 사용되는 bootstrap의 의미는 무엇인가요.
<details><summary>Keyword : resampling, 복원추출</summary>

∟ A : Resampling의 개념으로 표본이 주어졌을때 모수의 분포를 추정하는 강력한 방법으로 표본에서 복원추출하는 방식이다.

출처 : https://bkshin.tistory.com/entry/DATA-12

</details>
<br>

### #16
Q : 모수가 매우 적은 (수십개 이하) 케이스의 경우 어떤 방식으로 예측 모델을 수립할 수 있을까요?
<details><summary>Keyword : 오버샘플링, Augmentation</summary>

∟ A : resample의 복원추출 방식(oversampling)방식을 사용하여 Data의 수를 늘려주거나, 이미지의 경우 Data Augmentation 진행할 수 있다.

</details>
<br>

### #17
Q : 베이지안(Bayesian approach)과 프리퀀티스트(frequentist approach) 간의 입장차이를 설명해주실 수 있나요?
<details><summary>Keyword : 베이지안 - 확률분포 갱신, 프리퀀티스트 - 하나의 확률분포</summary>

∟ A : 프리퀀티스트의 경우 특정 정해진 확률값을 검증하기 위해 실험하고, 오차가 커질 경우 그 가설을 기각하는 방식으로 추로하는 방식을 하는 사람들을 얘기하고,
베이지안의 경우 실험을 통해 처음 예측한 확률값을 검증하는 것이 아닌 갱신하는 방식으로 분포를 추론하는 방식을 취하는 사람을 의미합니다. 

이 두 입장을 ML 관점에서 생각해 봤을때. 프리퀀티스트는 전체데이터를 한번에 학습시켜 가중치를 구한 경우, 베이지안의 경우 Minibatch를 통하여 가중치를 업데이트하는 방식으로 생각해봤습니다.

출처 :
https://www.ibric.org/myboard/read.php?id=19818&Page=&Board=SORI&FindIt=&FindText
https://www.notion.so/006-7b93d4275e1c45388227c8fbcec16550

</details>
<br>

### #18
Q : 검정력(statistical power)은 무엇일까요?
<details><summary>Keyword : </summary>

∟ A : 


</details>
<br>

### #19
Q : missing value가 있을 경우 채워야 할까요? 그 이유는 무엇인가요?
<details><summary>Keyword : </summary>

∟ A : 


</details>
<br>

+
무어-펜로즈 유사역행렬 : 특이값 분해를 통해 계산할 수 있고, 가역행렬의 역행렬 구하는 방식의 일반화된 방법이다
