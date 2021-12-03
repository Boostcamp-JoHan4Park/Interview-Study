### 고유값(eigen value)와 고유벡터(eigen vector)에 대해 설명해주세요. 그리고 왜 중요할까요?

- SVD, PCA에서 자주 쓰이는 개념! 벡터/기하학적 의미를 DL과 연관시켜 설명하는 것이 중요할듯
- A가 주어져있고, 람다와 x를 찾는게 목적
- 참고: https://darkpgmr.tistory.com/105

### 샘플링(Sampling)과 리샘플링(Resampling)에 대해 설명해주세요. 리샘플링은 무슨 장점이 있을까요?

- K-fold, Cross Validation, Bootstrapping
- 샘플링 = 표본추출
- 리샘플링은 모분포의 형태를 알 수 없을때 사용
- 복원/비복원추출의 차이
- 참고: https://cnp-0717.tistory.com/7

### 확률 모형과 확률 변수는 무엇일까요?

- 확률변수: 확률로 표현하기 위한 event를 정의하는 것  
  어떤 것을 확률로 표현할 것인지에 대해 다양하게 정의가 가능하므로 변수라는 용어를 사용
  - 확률함수(확률분포함수): 확률이 정의된 Sample space 내에서, 이러한 확률변수를 0과 1사이의 확률로 mapping하는 함수
- 확률모형: 확률은 불확실성을 표현하는 수단이라고 했는데, 이러한 불확실성을 확률로써 계량화하기 위해 우리가 앞서 다룬 확률함수로써 수학적으로 만든 모형
  - 모수: 함수에 쓰인 계수
- 참고: https://sumniya.tistory.com/24

### 누적 분포 함수와 확률 밀도 함수는 무엇일까요? 수식과 함께 표현해주세요.

- 둘 다 확률 변수의 분포 즉, 확률 분포를 수학적으로 정의하기 위한 수식
  - 확률분포: 어떤 사건에 어느 정도의 확률이 할당되었는지를 묘사한 것  
    확률 분포를 묘사하기 위해서는 모든 사건(event)들을 하나 하나 제시하고 거기에 할당된 숫자를 보여야 하기 때문에 확률 분포의 묘사는 결코 쉽지 않은 작업
- 누적 분포 함수: $$ F(x) = P(\{X < x\}) = P(X < x)$$  
  구간의 시작을 나타내는 숫자를 모두 같은 숫자인 음수 무한대($-\infty$)로 통일
- 확률 밀도 함수: $$ \dfrac{dF(x)}{dx} = f(x) $$, $$ F(x) = \int\_{-\infty}^{x} f(u) du $$
누적 분포 함수가 표현하는 사건이 음수 무한대를 시작점으로 하고 변수 $x$를 끝점으로 하는 구간이다보니 분포의 형상을 직관적으로 이해하기는 힘든 단점이 있다.  
   다시 말해서 어떤 확률 변수 값이 더 자주 나오는지에 대한 정보를 알기 힘들다는 점  
   절대적인 확률이 아닌 상대적인 확률 분포 형태만을 보기 위한 확률 밀도 함수  
   확률 밀도 함수는 특정 확률 변수 구간의 확률이 다른 구간에 비해 상대적으로 얼마나 높은가를 나타내는 것이며 그 값 자체가 확률은 아니다
- 참고: https://notebook.community/kimkipyo/dss_git_kkp/%ED%86%B5%EA%B3%84%2C%20%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D%20%EB%B3%B5%EC%8A%B5/160523%EC%9B%94_6%EC%9D%BC%EC%B0%A8_%EA%B8%B0%EC%B4%88%20%ED%99%95%EB%A5%A0%EB%A1%A0%202%20-%20%ED%99%95%EB%A5%A0%20%EB%B6%84%ED%8F%AC%20Probability%20Distribution/6.%EB%88%84%EC%A0%81%20%EB%B6%84%ED%8F%AC%20%ED%95%A8%EC%88%98%EC%99%80%20%ED%99%95%EB%A5%A0%20%EB%B0%80%EB%8F%84%20%ED%95%A8%EC%88%98

### 조건부 확률은 무엇일까요?

- 주어진 사건이 일어났다는 가정 하에 다른 한 사건이 일어날 확률  
  확률 함수를 $Pr$ 라고 할 때, 사건 $B$ 가 일어났다는 가정 하에 사건 $A$ 가 일어날 조건부 확률은 $Pr (A|B)$ 로 표기
- $P(A∣B)=P(A∩B)/P(B)$

### 공분산과 상관계수는 무엇일까요? 수식과 함께 표현해주세요

![](https://images.velog.io/images/hanlyang0522/post/c3a5b52b-884c-4a12-b5c3-8d868c3335b6/image.png)  
(마지막은 $X, Y$가 독립일 경우 공분산 = 0)

- 공분산 Covariance: 각 확률변수들이 어떻게 퍼져있는지를 나타내는 것
  - Cov(X, Y) > 0: X가 증가 할 때 Y도 증가한다.
  - Cov(X, Y) < 0: X가 증가 할 때 Y는 감소한다.
  - Cov(X, Y) = 0: 공분산이 0이라면 두 변수간에는 아무런 선형관계가 없으며 두 변수는 서로 독립적인 관계에 있음을 알 수 있다.  
    그러나 두 변수가 독립적이라면 공분산은 0이 되지만, 공분산이 0이라고 해서 항상 독립적이라고 할 수 없다.

![](https://images.velog.io/images/hanlyang0522/post/0e91d436-44b8-40b9-b1a2-eb10f879e442/image.png)

- 상관계수 Correlation: 확률변수의 절대적 크기에 영향을 받지 않도록 단위화시킴
  - 상관계수의 절대값은 1을 넘을 수 없다.
  - 확률변수 X, Y가 독립이라면 상관계수는 0이다.
  - X와 Y가 선형적 관계라면 상관계수는 1 혹은 -1이다.  
    양의 선형관계면 1, 음의 선형관계면 -1

### 신뢰 구간(Confidence Interval;CI)의 정의는 무엇인가요?

Keyword: 모수, 예측범위
Answer: 내가 추출한 표본평균이 관측될만한 범위, 모수가 실제로 포함될 것으로 예측되는 범위

- 모수가 실제로 포함될 것으로 예측되는 범위 --> 내가 추출한 표본평균이 이 범위에 ~% 확률로 들어온다
- 집단 전체를 연구하는 것은 불가능하므로, 샘플링된 데이터를 기반으로 모수의 범위를 추정하기 위해 사용됨  
  따라서 신뢰 구간은 샘플링된 표본이 연구중인 모집단을 얼마나 잘 대표하는지 측정하는 방법
- 신뢰구간(CI)에 모집단 실제 평균값이 포함될 확률을 CI의 신뢰수준(Confidence Level)이라함  
  전체적으로 95% 신뢰수준이 사용됨

- 참고: https://angeloyeo.github.io/2021/01/05/confidence_interval.html

### p-value를 모르는 사람에게 설명한다면 어떻게 설명하실 건가요?

Keyword: 귀무가설, 확률
Answer: 귀무가설을 전제로, 그 가설이 맞는다는 가정 하에, 표본에서 실제로 관측된 통계치와 '같거나 더 극단적인' 통계치가 관측될 확률

- 귀무가설(null hypothesis, H0)이 맞다는 전제 하에, 통계값(statistics)이 실제로 관측된 값 이상일 확률을 의미  
  혹은, 귀무가설(Null hypothesis)이 맞는다고 가정할 때 얻은 결과보다 극단적인 결과(관측 결과)가 나타날 확률

- 귀무가설: 새로운 사실은 없다라는 가정

- 참고: https://www.insilicogen.com/blog/341  
  https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=hsj2864&logNo=221225950532
  https://data-make.tistory.com/114
  https://datascienceschool.net/02%20mathematics/09.04%20%EA%B2%80%EC%A0%95%EA%B3%BC%20%EC%9C%A0%EC%9D%98%ED%99%95%EB%A5%A0.html#:~:text=%EC%9C%A0%EC%9D%98%ED%99%95%EB%A5%A0%EC%9D%80%20%ED%99%95%EB%A5%A0%EB%B6%84%ED%8F%AC,%ED%95%98%EB%8A%94%20%EC%98%81%EC%97%AD%EC%9D%98%20%EB%A9%B4%EC%A0%81%EC%9D%B4%EB%8B%A4

### R square의 의미는 무엇인가요?

Keyword:
Answer: Regression line이 어떻게 그려지냐에 따라 data의 성질을 잘 표현하는지 아닌지

- 참고: https://heung-bae-lee.github.io/2020/01/09/machine_learning_03/

### 평균(mean)과 중앙값(median)중에 어떤 케이스에서 뭐를 써야할까요?

Keyword: Outlier
Answer: 값이 한쪽으로 치우친 경우 평균도 왜곡될 가능성이 있어서 중앙값을 씀
중앙값은 관측값들의 변화에 민감하지 않고, outlier에 영향받지 않음

### 중심극한정리는 왜 유용한걸까요?

Keyword: 정규분포, 표본의 크기가 클것
Answer: 중심극한정리를 통해 모집단이 어떤 분포를 갖고있든 표본의 크기가 충분히 크다면, 표본평균의 분포는 정규분포를 이룬다는 점을 이용해 특정 사건(내가 수집한 표본의 평균)이 일어날 확률값을 계산할 수 있습니다

- 표본평균분포(Sampling distribution of sample mean): 모집단에서 표본크기가 n인 표본을 여러번 반복해서 추출했을때, 각각 표본 평균들이 이루는 분포  
  표본크기 n이 커질수록 표본 평균들이 이루는 분포가 '평균이 $\mu$고 표준편차가 $\sigma /\sqrt{n}$인 정규분포'에 가까워짐

- 중심극한정리(Central limit theorem): 모집단이 '평균이 $\mu$고 표준편차가 $\sigma$인 임의의 분포'를 이룬다고 할 때,  
  이 모집단으로부터 추출된 표본의'표본의 크기 n이 충분히 크다'면 표본 평균들이 이루는 분포는 '평균이 $\mu$고 표준편차가 $\sigma /\sqrt{n}$인 정규분포'에 근접한다

- 중심극한정리를 통해 모집단이 어떤 분포를 갖고있든 표본의 크기가 충분히 크다면, 표본평균의 분포는 정규분포를 이룬다는 점을 이용해 특정 사건(내가 수집한 표본의 평균)이 일어날 확률값을 계산할 수 있음

- 참고: https://drhongdatanote.tistory.com/57

![](https://images.velog.io/images/hanlyang0522/post/5aa967d6-ba90-4957-b38f-874e2ea7fde0/image.png)

### 엔트로피(entropy)에 대해 설명해주세요. 가능하면 Information Gain도요.

Keyword: Purity  
Answer: Entropy는 0~1 사이의 값으로 주어진 데이터 집합의 혼잡도를 의미하며, information gain은 어떤 속성을 선택함으로써 얻게되는 entropy 감소량을 말합니다.

- entropy: sample의 purity를 보여줌
- info gain: 전체 S가 특징 A에 의해 구분된 후 감소된 entropy, 클수록 구분을 잘한다

### 어떨 때 모수적 방법론을 쓸 수 있고, 어떨 때 비모수적 방법론을 쓸 수 있나요?

Keyword: 정규성 검정, 표본 개수  
Answer: 모수적 방법론은 일반적으로 표본당 30개 이상으로 구성될 경우 정규분포를 따른다고 가정해 사용
비모수적 방법론은 정규성 검정에서 정규분포를 따르지 않는다고 증명되거나, 표본의 개수가 10개 미만일 때 사용

- 모수적 방법론(Parametic method): 모수를 함수형태의 분포를 가정하여 접근하는 방법  
  연속형 확률분포(정규분포, 감마분포 등), 이산형 확률분포(베르누이분포, 이항분포 등)

- 비모수적 방법(Non-parametic method): 모집단의 분포를 가정하지 않고 접근하는 방법
  정규분포를 따르지 않아 평균, 분산 같은 모수가 존재하지 않음

- 정규성 검정: 데이터셋 분포가 정규분포를 따르는지 검정
  Shapri-Wilks test, Kolmogorove-Smirnov test, Quntile-Qunatile plot 등이 있음

### “likelihood”와 “probability”의 차이는 무엇일까요?

Keyword:  
Answer: 확률probability은 어떤 시행(trial, experiment)에서 특정 결과(sample)가 나올 가능성. 즉, 시행 전 모든 경우의 수의 가능성은 정해져 있으며 그 총합은 1(100%)
우도likelihood는 어떤 시행(trial, experiment)을 충분히 수행한 뒤 그 결과(sample)를 토대로 경우의 수의 가능성을 도출하는 것. 아무리 충분히 수행해도 어디까지나 추론(inference)이기 때문에 가능성의 합이 1이 되지 않을 수도 있다.

- 참고: https://yjam.tistory.com/38

### 통계에서 사용되는 bootstrap의 의미는 무엇인가요.

Keyword: 복원 추출, 모수 추정
Answer: 현재 있는 표본에서 추가적으로 표본을 복원 추출하고 각 표본에 대한 통계량을 다시 계산해 모수의 분포를 정확하게 추정함

- 부트스트랩: 현재 있는 표본에서 추가적으로 표본을 복원 추출하고 각 표본에 대한 통계량을 다시 계산하는 것
- Bootstrap aggregating (Bagging)이란, 하나의 original data가 있을 때, B번의 bootstrap sampling을 통해 B개의 데이터를 새로 만들고, 이를 이용하여 B개의 classifier를 만들고 합치는 것을 말한다

- 참고: https://bioinfoblog.tistory.com/entry/%ED%86%B5%EA%B3%84-%EA%B8%B0%EC%B4%88-Bootstrap-%EB%B6%80%ED%8A%B8%EC%8A%A4%ED%8A%B8%EB%9E%A9  
  https://bkshin.tistory.com/entry/DATA-12

### 모수가 매우 적은 (수십개 이하) 케이스의 경우 어떤 방식으로 예측 모델을 수립할 수 있을까요?

Keyword: 비모수 검정
Answer: 모집단 수가 매우 적은 경우 표본평균의 분포가 정규분포를 따른다고 가정할 수 없으므로 비모수적 방법을 사용하여 예측모델을 수립

![](https://images.velog.io/images/hanlyang0522/post/aecfaa5e-6b50-4920-ae43-638995c51ea1/image.png)

- 비모수적 검정을 사용?

### 베이지안과 프리퀀티스트 간의 입장차이를 설명해주실 수 있나요?

Keyword: 객관과 주관의 차이
Answer: 프리퀀티스트는 정해진 모수가 있다고 가정 후 검증하고, 베이지안은 현재까지의 관측값을 바탕으로 가정하기 때문에 새로운 데이터가 들어오면 모수를 업데이트함

- 확률을 객관적으로 발생하는 현상의 빈도수에 대한 기술로 보느냐 VS 현상에 대한 관찰자의 주관적인 믿음의 체계로 보느냐

- 참고: https://freshrimpsushi.github.io/posts/bayesian-paradigm/

### 검정력(statistical power)은 무엇일까요?

Keyword: 귀무가설을 기각
Answer: 검정이 귀무 가설을 올바르게 기각하는 확률

- 검정력(檢定力, statistical power)는 대립가설이 사실일 때, 이를 사실로서 결정할 확률
  혹은 검정이 귀무 가설을 올바르게 기각하는 확률

- 참고: https://support.minitab.com/ko-kr/minitab/19/help-and-how-to/statistics/power-and-sample-size/supporting-topics/what-is-power/  
  https://deep-learning-study.tistory.com/91

### missing value가 있을 경우 채워야 할까요? 그 이유는 무엇인가요?

Keyword: bias, underfit
Answer: 누락값이 많은 데이터셋으로 모델을 학습시키면 bias, underfit 등 성능에 많은 영향을 미치기 때문

- 참고: https://dining-developer.tistory.com/19
  https://subinium.github.io/missing-data-handling/
