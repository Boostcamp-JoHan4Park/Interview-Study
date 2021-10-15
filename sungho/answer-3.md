### [Statistics/Math](./answers/statistics-math.md)  

* 신뢰 구간의 정의는 무엇인가요?  
* p-value를 모르는 사람에게 설명한다면 어떻게 설명하실 건가요?  
* R square의 의미는 무엇인가요?  
키워드: MSE, Regression line  
짧은 답: Regression line이 데이터에 fit하다면 R square는 1에 가깝다. Regression line이 데이터에 fit하지 못하다면 R square는 0에 가깝다.
이유: R square의 정의가 $$1 - {MSE\ of\ Regression\ line} / {MSE\ of\ the\ average\ of\ the\ data}$$이기 때문이다.


* 평균(mean)과 중앙값(median)중에 어떤 케이스에서 뭐를 써야할까요?  
키워드: 표본들의 격차, 분산  
짧은 답: 분산을 유지해야 하고 outlier가 없다면 평균을 쓴다. 표본들의 격차가 너무 크다면 중앙값을 쓴다.

### [Deep Learning](./answers/deep-learning.md)  

* 하이퍼 파라미터는 무엇인가요?  
* Weight Initialization 방법에 대해 말해주세요. 그리고 무엇을 많이 사용하나요?  
* 볼츠만 머신은 무엇인가요?  
[ref](https://idplab-konkuk.tistory.com/14)  
키워드: neural network  
짧은 답: ???

* TF, PyTorch 등을 사용할 때 디버깅 노하우는?  
키워드: IDE  
짧은 답: IDE Debugger를 적극적으로 활용하고 모델의 차원 수에 대해서 정확히 알아두자.  
이유: Deep learning framework 디버깅은 보통 모델 디버깅이다. 경험 상 대부분의 트러블 슈팅은 일치하지 않는 차원 수와 layer 출력의 잘못된 이해에서 비롯됐다. 이를 염두하고 디버깅하도록 하자.

### [Machine Learning](./answers/machine-learning.md)  

* LSA, LDA, SVD 등의 약자들이 어떤 뜻이고 서로 어떤 관계를 가지는지 설명할 수 있나요?  
* Markov Chain을 고등학생에게 설명하려면 어떤 방식이 제일 좋을까요?  
* 텍스트 더미에서 주제를 추출해야 합니다. 어떤 방식으로 접근해 나가시겠나요?  
키워드: Seq2Seq  
짧은 답: Context와 summarization을 포함하고 있는 dataset을 통해 Seq2Seq 모델을 학습할 것이다.  
이유: 머신러닝적인 관점에서 TextRank와 같은 방법을 사용할 수 있다. 하지만 HuggingFace와 같이 high level framework가 매우 잘 돼있기 때문에 굳이 transformer를 사용하지 않을 이유가 없다. RNN이든 transformer든 Seq2Seq 모델을 사용하는 것이 가장 성능이 좋을 것이다.

* SVM은 왜 반대로 차원을 확장시키는 방식으로 동작할까요? SVM은 왜 좋을까요?  
[ref1](https://darkpgmr.tistory.com/145)  
[ref2](https://bioinformaticsandme.tistory.com/304)  
키워드: 경계평면(thresholding hyoperplane), 차원 확장  
짧은 답: 현재 차원에서 선형적으로 분류하기 힘들 때 차원 확장을 하기 때문이다.   SVM은 예측 변수가 많을 때도 쉽게 hyperplane을 찾아주기 때문에 좋다.    
이유: SVM은 임의의 hyperplane을 설정하고 margin을 조정하는 방식으로 쵲거의 hyperplane을 학습한다. 따라서 예측변수가 많은 분류 문제에 대해서도 효율적으로 작동할 수 있다.
<br>