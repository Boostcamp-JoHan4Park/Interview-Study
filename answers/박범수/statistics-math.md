1. 평균(mean)과 중앙값(median)중에 어떤 케이스에서 뭐를 써야할까요?
   값이 한쪽으로 치우친 경우 평균도 왜곡될 가능성이 있어서 중앙값을 씀
   보통은 중앙값 계산하는게 프로그래밍적으로 복잡해서 평균을 쓸듯?
   중앙값은 관측값들의 변화에 민감하지 않고, outlier에 영향받지 않음

2. 엔트로피(entropy)에 대해 설명해주세요. 가능하면 Information Gain도요.
   entropy: sample의 purity를 보여줌
   info gain: 전체 S가 특징 A에 의해 구분된 후 감소된 entropy, 클수록 구분을 잘한다

3. 고유값(eigen value)와 고유벡터(eigen vector)에 대해 설명해주세요. 그리고 왜 중요할까요?
   SVD, PCA에서 자주 쓰이는 개념! 벡터/기하학적 의미를 DL과 연관시켜 설명하는 것이 중요할듯
   A가 주어져있고, 람다와 x를 찾는게 목적
   https://darkpgmr.tistory.com/105

4. 샘플링(Sampling)과 리샘플링(Resampling)에 대해 설명해주세요. 리샘플링은 무슨 장점이 있을까요?
   K-fold, Cross Validation, Bootstrapping
   샘플링 = 표본추출
   리샘플링은 모분포의 형태를 알 수 없을때 사용
   복원/비복원추출의 차이
   https://cnp-0717.tistory.com/7
