## **Part1**

### **[Statistics/Math](https://github.com/Boostcamp-JoHan4Park/Interview-Study/blob/master/answers/statistics-math.md)**

- 고유값(eigen value)와 고유벡터(eigen vector)에 대해 설명해주세요. 그리고 왜 중요할까요?
- 샘플링(Sampling)과 리샘플링(Resampling)에 대해 설명해주세요. 리샘플링은 무슨 장점이 있을까요?
- 확률 모형과 확률 변수는 무엇일까요?
- 누적 분포 함수와 확률 밀도 함수는 무엇일까요? 수식과 함께 표현해주세요.
- 조건부 확률은 무엇일까요?
- 공분산과 상관계수는 무엇일까요? 수식과 함께 표현해주세요.
- 신뢰 구간의 정의는 무엇인가요?
- p-value를 모르는 사람에게 설명한다면 어떻게 설명하실 건가요?
- R square의 의미는 무엇인가요?
- 평균(mean)과 중앙값(median)중에 어떤 케이스에서 뭐를 써야할까요?
- 중심극한정리는 왜 유용한걸까요?
- 엔트로피(entropy)에 대해 설명해주세요. 가능하면 Information Gain도요.
- 어떨 때 모수적 방법론을 쓸 수 있고, 어떨 때 비모수적 방법론을 쓸 수 있나요?
- “likelihood”와 “probability”의 차이는 무엇일까요?
- 통계에서 사용되는 bootstrap의 의미는 무엇인가요.
- 모수가 매우 적은 (수십개 이하) 케이스의 경우 어떤 방식으로 예측 모델을 수립할 수 있을까요?
- 베이지안과 프리퀀티스트 간의 입장차이를 설명해주실 수 있나요?
- 검정력(statistical power)은 무엇일까요?
- missing value가 있을 경우 채워야 할까요? 그 이유는 무엇인가요?
    
    결측치가 있으면 학습이 잘 안되지 않나..?
    

### **[Deep Learning](https://github.com/Boostcamp-JoHan4Park/Interview-Study/blob/master/answers/deep-learning.md)**

- 딥러닝은 무엇인가요? 딥러닝과 머신러닝의 차이는?
    
    keyword : feature selection
    
    딥러닝과 머신러닝의 가장 큰 차이점은 사람이 직접 feature selection을 하는지 안하는지의 차이인 것 같습니다.
    
    머신러닝의 경우 사람이 직접 유의미한 feature를 고르는 feature selection 과정을 거치지만 딥러닝은 사람이 직접 그러한 과정이 없습니다.
    
- Cost Function과 Activation Function은 무엇인가요?
    
    cost function : 모델이 목적함수에 다다르기 위해 사용하는 함수입니다. 예측값과 정답을 통한 cost function의 값을 최소화 하는 방식으로 모델이 학습을 진행합니다.
    
    activation function : 층을 더 깊게 쌓을 수 있게 해주어 모델의 표현력을 더 길러주기 위한 함수입니다 비선형 함수를 사용하고 sigmoid, relu 등의 함수가 있습니다.
    
    모델의 표현력 ? 선형 함수를 아무리 깊게 쌓아도 한 층의 선형 함수로 표현할 수 있습니다. 비선형 함수를 사용함으로써 층을 더 깊게 쌓을 수 있게 해주어 함수의 표현력을 증가시킵니다.
    
- Tensorflow, PyTorch 특징과 차이가 뭘까요?
    
    구동 방식에 차이점이 있습니다.
    
    Tensorflow : Define and run
    
    PyTorch : Define with run ? 아마 그럴걸..?
    
- Data Normalization은 무엇이고 왜 필요한가요?
    
    keyword : scale
    
    data의 scale을 맞춰주는 방식이라고 생각하면 될 것 같습니다.
    
    feature마다 크기가 다른데 그 scale을 맞춰줘서 동일한 크기의 중요도를 가질 수 있도록 해줍니다.
    
- 알고있는 Activation Function에 대해 알려주세요. (Sigmoid, ReLU, LeakyReLU, Tanh 등)
    
    기존에 많이 사용되었던 sigmoid와 현재 많이 사용되고 있는 ReLU에 대해 설명드리겠습니다.
    
    sigmoid= 1/(1+ e^-x) 라는 수식을 가지고 있고 모든 값을 0~1로 normalization 해주는 역할을 하고 있습니다. sigmoid는 양쪽 방향으로 saturation이 된다는 단점이 있습니다. 
    
    다음으로 ReLU입니다. max(0, x)라는 수식을 가지고 있고 sigmoid와 같이 지수연산이 없으므로 보다 빠르다는 장점을 가지고 있습니다. sigmoid에 비해 덜 saturation 되긴 하지만 음수쪽에서 dead nueron이 된다는 단점이 존재합니다.
    
    dead neruon : gradient가 0이 되어 더이상 가중치가 업데이트 되지 않는 현상
    
    → 여기서 현재는 sigmoid 대신에 왜 ReLU를 쓰는가에 대한 질문에 대한 답변
    
    1. 빠르다
    2. saturation 2 곳 → 1 곳
    3. zero-centered 문제 또한 한 쪽에만 있어서 덜 지그재그..
- 오버피팅일 경우 어떻게 대처해야 할까요?
    
    다양한 regularization 기법들을 사용합니다. 
    
    regularization 기법으로는 early stopping, dropout, label smoothing, noise robustness, batch normalization 등이 있습니다.
    
    early stopping은 train loss는 줄어들지만 validation loss가 줄어들지 않는다면 일정 시점에서 학습을 멈추는 기법입니다.
    
    dropout은 학습 시에 일정 확률로 뉴런의 연결을 끊어 학습하는 기법입니다. 학습시마다 무작위로 연결을 끊어 조금씩 다른 구조로 모델이 학습하게 됩니다. 그럼으로써 어느정도 앙상블의 효과를 가진다고 알고 있습니다. 
    
    label smoothing은 정확하지 않은 label에 대해 label을 여러 개로 주는 방법으로 .. cutmix, cutout 등이 있습니다.
    
    noise robustness는 noise를 임의로 주어 학습을 하여 강건한 모델을 만들 수 있도록 합니다.
    
    batch normalization은 각 batch마다 평균은 0, 분산은 1로 normalization을 해주는 기법으로 ... 까먹음
    
- 하이퍼 파라미터는 무엇인가요?
    
    사용자가 직접 지정해주는 파라미터입니다. 
    
- Weight Initialization 방법에 대해 말해주세요. 그리고 무엇을 많이 사용하나요?
    
    가중치 초기화 기법으로는 Lecun,  xavior, kaming he initialize 기법이 있습니다.
    
- 볼츠만 머신은 무엇인가요?
    
    visible layer와 hidden layer로 구성되어 있는 완전그래프 형태의 network입니다.
    
    제한된 볼츠만 머신의 경우 layer층으로 연결되어 있어 우리가 알고 있는 NN과 비슷한 형태를 띄고 있습니다.
    
- TF, PyTorch 등을 사용할 때 디버깅 노하우는?
    
    디버깅을 할 경우에 에러가 나는 부분과 중요한 변수 선언 전으로 디버깅을 진행하고 있습니다. 물론 디버깅을 통해 에러를 잡는 것도 중요하지만 코드를 작성하기 전 주의해야 할 부분에 대해 remind를 진행한 다음 코딩을 하고 있습니다. 
    
- 뉴럴넷의 가장 큰 단점은 무엇인가? 이를 위해 나온 One-Shot Learning은 무엇인가?
    
    NN의 경우에는 학습할 데이터가 적으면 학습이 잘 안된다는 단점을 가지고 있습니다. 그러한 문제를 해소하고자 One-shot, Zero-shot, Few shot learning이 나왔습니다.
    
    one-shot learning의 경우 사전에 거대한 데이터로 학습이 된 Pretrained 된 모델을 이용하여 데이터가 적더라도 괜찮은 성능을 낼 수 있는 학습 방법입니다.
    
- 요즘 Sigmoid 보다 ReLU를 많이 쓰는데 그 이유는?
    
    Sigmoid의 다양한 문제점을 ReLU가 개선되었기 때문이라고 생각합니다.
    
    1. Saturation 현상을 완화시킨다.
    2. 속도가 빠르다
    3. zero-centered 하지 않지만 덜 지그재그의 개형을 그리고 있어 더 효율적으로 목적지를 탐색할 수 있다.
    
    - Non-Linearity라는 말의 의미와 그 필요성은?
        
        비선형성이라는 말입니다. 선형 layer를 여러 층을 쌓을 경우 하나의 선형 layer로 표현할 수 있습니다. non-linearity한 layer를 쌓음으로써 그러한 문제를 해소하고 층을 보다 깊게 쌓을 수 있습니다.
        
        이를 통해 network의 표현력을 더 좋게 만들 수 있습니다. 표현력이 더 좋다는 말은.. 복잡한 목적함수에 접근하도록 network가 될 수 있는 느낌..?
        
    - ReLU로 어떻게 곡선 함수를 근사하나?
        
        ReLU에서 꺾인 부분을 이용하면 특정 부분에서 각도를 구부릴 수 있습니다. 이러한 방식으로 곡선 함수에 근사 시킬 수 있습니다.
        
    - ReLU의 문제점은?
        1. 0이하인 부분에서 graident가 0이 되어 update되지 않는 dead nueron 현상
        2. 양수 범위에서 값이 계속 커지므로 값이 exploding하는 현상
        3. zero-centered 하지 않다 → gradient가 항상 양수나 음수 방향으로 움직일 수 있다는 점.. → 비효율적인 탐색
        
    - Bias는 왜 있는걸까?
        
        weight는 기울기를 조정하는 거라면 bias는 평행이동하는 것이라고 보시면 좋을 것 같습니다. 그래서 필요합니다.
        
- Gradient Descent에 대해서 쉽게 설명한다면?
    
    
    - 왜 꼭 Gradient를 써야 할까? 그 그래프에서 가로축과 세로축 각각은 무엇인가? 실제 상황에서는 그 그래프가 어떻게 그려질까?
    - GD 중에 때때로 Loss가 증가하는 이유는?
    - Back Propagation에 대해서 쉽게 설명 한다면?
- Local Minima 문제에도 불구하고 딥러닝이 잘 되는 이유는?
    
    고차원을 표현하게 되면 완벽한 local minima는 찾기 쉽지 않다. 대부분 saddle point나 그런 것이 다반사다. 그럼으로 딥러닝 학습에서 local minima에 빠지는 것은 희박하므로 괜찮다.
    
    - GD가 Local Minima 문제를 피하는 방법은?
        
        momentum 같은 다양한 Optimizer 기법을 사용하여 문제를 피할 수 있습니다.
        
        momentum 같은 경우는 이전에 gradient가 흐르던 방향으로 어느 정도 흘러 갈 수 있도록 momentum 상수를 주어 조절하는 방법이다.
        
    - 찾은 해가 Global Minimum인지 아닌지 알 수 있는 방법은?
        
        확실하게 없다 !
        
- Training 세트와 Test 세트를 분리하는 이유는?
    
    학습하지 않은 데이터로 학습된 모델의 성능을 측정하기 위해서.
    
    - Validation 세트가 따로 있는 이유는?
        
        test set과 목적이 다르기에 사용합니다. 
        
        학습 진행 과정에서 모델이 학습이 잘 되고 있는지를 판단하기 위해 사용합니다.
        
        test set의 경우에는 모델이 학습된 다음 최종적으로 모델의 일반화 성능을 측정하기 위해 사용합니다.
        
    - Test 세트가 오염되었다는 말의 뜻은?
        
        학습 과정에서 test set과 똑같거나 유사한 데이터가 들어가는 경우를 뜻합니다.
        
    - Regularization이란 무엇인가?
        
        학습 과정을 방해하여 일반화 성능을 높이려는 기법입니다.
        
        대표적으로 early stopping, dropout 등의 기법이 있습니다.
        
- Batch Normalization의 효과는?
    - Dropout의 효과는?
        
        학습을 방해하여 일반화 성능을 높이는 regularization 효과를 얻을 수 있습니다.
        
    - BN 적용해서 학습 이후 실제 사용시에 주의할 점은? 코드로는?
        
        학습 시에는 batch마다 평균과 분산을 계산해서 적용을 하지만, inference과정에서는 학습 데이터 전체의 평균을 계산하여 적용을 해주어야합니다. 이유는 사용자가 설정한 batch 크기에 따라 추론 결과가 바뀔 수도 있기 떄문입니다.
        
    - GAN에서 Generator 쪽에도 BN을 적용해도 될까?
        
        GAN에서 일반적으로 generator의 출력층에만 BN을 적용하지 않는다.! generator가 만든 이미지에 BN을 적용하면 실제 이미지와 값의 범위가 달라지기 때문이다.
        

### **[Machine Learning](https://github.com/Boostcamp-JoHan4Park/Interview-Study/blob/master/answers/machine-learning.md)**

- 알고 있는 metric에 대해 설명해주세요. (ex. RMSE, MAE, recall, precision ...)
    
    metric은 크게 회귀를 위한 metric과 분류를 위한 metric으로 나눌 수 있습니다. 
    
    회귀 관련 metric에는 MSE, MAE가 있습니다. MSE는 실제값과 예측값의 오차를 제곱의 평균입니다.
    
    분류 관련한 metric으로는 Accuracy, Precision, Recall 등이 있다.
    
    Accuracy는 정답과 예측값의 일치하는 정도를 나타내는 metric입니다.
    
    Precision은 예측한 값들 중에 긍정으로 분류한 것 중 맞춘 개수를 나타냄..! → TP / (TP+ FP)
    
    Recall은 정답 중에 긍정으로 예측하여 맞춘 개수를 나타냄..! TP / (TP+ FN)
    
    TP FN : 맞다고 예측했는데 맞고 틀렸다 예측을 했는데 틀린 애들 : 정답 들
    
    TP FP 맞은데 맞다고 예측한 애들 틀린데 맞다고 예측한 애들 binary니까..! → predict 값
    
- 정규화를 왜 해야할까요? 정규화의 방법은 무엇이 있나요?
    
    normalization이라고 이해를 하고 설명 드리겠습니다. 
    
    다양한 feature들이 있을텐데 feature들마다 scale이 다를 수 있습니다. 이대로 들어가게 되면 scale이 큰 feature의 영향이 크게 되는데 normalization을 통해 feature들의 scale을 조절해주어 동일한 중요도를 가질 수 있도록 해줍니다.
    
    방법으로는 min-max normalization으로 최소가 0, 최대가 1이 되도록 변환을 하는 방법이 있습니다.
    
- Local Minima와 Global Minima에 대해 설명해주세요.
    
    저희의 궁극적인 목표는 cost function의 global minima, cost가 최소화 되는 지점를 찾는 것입니다. local minima는 에러가 최소가 될 수 있는 후보군 중 global minima를 뺀 나머지를 의미합니다.
    
    local minima가 아닌 global minima에 도달하기 위해 momentum과 같은 최적화 알고리즘을 사용하거나 lr을 잘 조절합니다.
    
- 차원의 저주에 대해 설명해주세요.
    
    차원의 저주란 데이터 차원이 증가할수록 해당 공간의 크기가 기하급수적으로 증가하여 데이터 간의 거리가 기하급수적으로 멀어져 희소한 구조를 갖게 되는 현상을 말합니다.
    
    이를 해결하기 위해 차원을 증가시킨 만큼 더 많은 데이터를 추가하거나 PCA, LDA같은 차원 축소 알고리즘으로 차원을 줄여 해결합니다.
    
- dimension reduction 기법으로 보통 어떤 것들이 있나요?
    
    feature selection 방법과 feature extraction 방법으로 나눌 수 있습니다. feature selection 방법에는데이터의 특징을 잘 표현하는 주요 feature만 선택하는 것을 말합니다. 
    
    feature extraction 방법은 기존 feature를 저차원의 feature로 압축하여 feature를 함축적으로 잘 설명할 수 있도록 하는 방법을 말합니다. 대표적으로 PCA, SVD 등의 기법이 있습니다.
    
- PCA는 차원 축소 기법이면서, 데이터 압축 기법이기도 하고, 노이즈 제거기법이기도 합니다. 왜 그런지 설명해주실 수 있나요?
    
    PCA는 입력 데이터의 공분산 행렬을 기반으로 고유 벡터를 생성하고 이렇게 구한 고유 벡터에 입력 데이터를 선형 변환하여 차원을 축소하는 방법. → 차원은 곧 입력 데이터의 feature를 뜻하므로 데이터 압축 기법으로 볼 수 있다.
    
    또한 PCA는 고유값이 가장 큰, 즉 데이터의 분산이 가장 큰 순으로 주성분 벡터를 추출하는데 가장 나중에 뽑힌 벡터보다 가장 먼저 뽑힌 벡터가 데이터를 더 잘 설명할 수 있기 떄문에 노이즈 제거 기법이라고도 불린다.
    
- LSA, LDA, SVD 등의 약자들이 어떤 뜻이고 서로 어떤 관계를 가지는지 설명할 수 있나요?
    
    PCA는 정방 행렬에 대해서만 행렬을 분해할 수 있는데 반해 SVD는 행과 열의 크기가 다른 행렬에도 적용이 가능하다.
    
    LSA는 Latent Semantic Analysis의 약자로 잠재 의미 분석을 말한다. 주로 토픽 모델링에 자주 사용되는 기법이다. LSA는 DTM이나 TF-IDF 행렬에 truncated SVD를 적용하여 차원을 축소시키고 단어들의 잠재적인 의미를 이끌어낸다. 
    
    Truncated SVD는 SVD와 똑같으나 상위 n개의 특이값만 사용하는 기법이다. → 원 행렬로 복원할 수 없다.
    
    LDA는 Latent Dirichlet Allocation 혹은 Linear Discriminant Analysis의 약자이다. 전자는 토픽모델링에 사용되는 기법 중 하나로 LSA와는 달리 단어가 특정 토픽에 존재할 확률과 문서에 특정 토픽이 존재할 확률을 결합확률로 추정하여 토픽을 추정하는 기법이다.
    
    후자는 차원축소기법 중 하나로 분류하기 쉽도록 클래스 간 분산을 최대화하고 클래스 내부의 분산을 최소화 하는 방식을 말한다 !
    
- Markov Chain을 고등학생에게 설명하려면 어떤 방식이 제일 좋을까요?
    
    markov chain : markov 성질을 지닌 이산 확률 과정
    
    이전 상태를 통해 현재 상태를 결정하는 기법
    
    1차 마코프 체인은 n번째 상태만을 통해 n+1번째 상태를 결정한다..!
    
    1차 마코프 체인을 설명하자면 어제 날씨에만 의존해서 오늘 날씨를 예측하는 것이라고 설명을 하면 좋을 것 같다.
    
- 텍스트 더미에서 주제를 추출해야 합니다. 어떤 방식으로 접근해 나가시겠나요?
    
    말뭉치로부터 토픽을 추출하는 토픽 모델링 기법 중 하나인 LDA를 사용할 것 같습니다.
    
    ref
    
    [https://ratsgo.github.io/from frequency to semantics/2017/06/01/LDA/](https://ratsgo.github.io/from%20frequency%20to%20semantics/2017/06/01/LDA/)
    
- SVM은 왜 반대로 차원을 확장시키는 방식으로 동작할까요? SVM은 왜 좋을까요?
    
    비선형 분류를 할 때 저차원보다는 고차원에서 maximum hyper plane을 구하기 쉽기 때문에 차원을 확장시키는 방식으로 동작합니다.
    
    margin을 최대화 하도록 구성..
    
    커널 함수를 이용해 차원 공간을 고차원 공간으로 매핑해준다 !
    
    장점 
    
    - 분류와 회귀에 모두 사용이 가능
    - overfitting 정도가 nn에 비해 낮다.
    - 예측의 정확도가 높은편..  + 저차원 고차원 데이터에 모두 잘 작동
    
    단점 
    
    예측의 해석이 어렵다.
    
    대용량 데이터에 대해 모델 속도가 느리고 메모리 할당량도 크다 !
    
- 다른 좋은 머신 러닝 대비, 오래된 기법인 나이브 베이즈(naive bayes)의 장점을 옹호해보세요.
    
    나이브 베이즈 알고리즘
    
    데이터에서 변수들에 대한 조건부 독립을 가정하는 알고리즘. 클래스에 대한 사전 정보와 데이터로부터 추출된 정보를 결합하고.. 베이즈 정리를 이용하여 어떤 데이터가 특정 클래스에 속하는지 분류하는 알고리즘
    
    장점 
    
    단순하고 빠르며 효과적임
    
    노이즈와 결측치가 있어도 잘 수행
    
    단점
    
    모든 속성이 동등하게 중요하고 독립적이라는 가정에 의존
    
    수치 속성으로 구성된 많은 데이터셋에 대해 이상적이지 않다..?
    
- 회귀 / 분류시 알맞은 metric은 무엇일까?
    
    회귀 : MSE, MAE / 오차 제곱의 평균, 절댓값 오차의 평균
    
    분류 : CrossEntropy → log Binary CrossEntropy , Categorical CrossEntropy
    
- Association Rule의 Support, Confidence, Lift에 대해 설명해주세요.
    
    연관성 분석은 비지도 학습으로 label이 없는 상태에서 데이터에 숨겨진 패턴을 찾는 분석 기법이다. 얼마나 자주 함께 발생할지를 측정할 수 있는 3가지 척도로 support, confidence, lift가 있다..
    
    support : 전체 경우의 수에서 두 아이템이 같이 나오는 비율
    
    confidence : X가 나온 경우 중 X와 Y가 함께 나올 비율
    
    lift: X와 Y가 같이 나오는 비율을 X가 나올 비율과 Y가 나올 비율의 곱으로 나눈 값
    
- 최적화 기법중 Newton’s Method와 Gradient Descent 방법에 대해 알고 있나요?
    
    newton method의 경우는 해당 x값에서 접선을 그었을 때 x축과 만나는 지점으로 값을 이동하며 탐색하는 최적화 기법 → 초기값을 잘주면 금방 해를 찾을 수 있지만 잘못 주면 시간이 오래걸리거나 찾지 못할 수도 있음..
    
    gradient descent : loss function의 값을 최소화 시키기 위한 파라미터를 gradient를 통해 찾아가는 기법
    
    loss function의 1차 미분 함수에서 현재 x값을 대입 ! → 그 값을 lr을 곱해서 뺸 값으로 점진적으로 이동하는 함수..
    
- 머신러닝(machine)적 접근방법과 통계(statistics)적 접근방법의 둘간에 차이에 대한 견해가 있나요?
    
    머신러닝적 접근 방법과 통계적 접근 방법의 차이는 두 방법의 목적이 다릅니다.
    
    머신러닝적 접근 방법은 모델의 성능을 올리는 것이 목적입니다.
    
    즉 모델의 신뢰도나 정교한 가정보다는 다양한 feature를 사용하여 높은 예측률을 달성하고자 함 !
    
    통계적 접근 방법의 경우 분포의 가정을 통해 신뢰 가능하고 정교한 모델을 만드는 것을 목적 → 모형을 복잡하지 않고 단순하게 만들고, 어떤 feature가 어떤 원인을 주는지도 알 수 있도록..!
    
    REF
    
    [https://medium.com/@hyunseok/머신러닝과-전통적-통계학의-차이-a560f0708db0](https://medium.com/@hyunseok/%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D%EA%B3%BC-%EC%A0%84%ED%86%B5%EC%A0%81-%ED%86%B5%EA%B3%84%ED%95%99%EC%9D%98-%EC%B0%A8%EC%9D%B4-a560f0708db0)
    
- 인공신경망(deep learning이전의 전통적인)이 가지는 일반적인 문제점은 무엇일까요?
    
    선형적인 모델이었기 때문에 복잡한 문제를 풀 수 없었다.. ex) XOR
    
    하지만 sigmoid 같은 비선형 함수를 추가해 복잡한 문제를 해결하고, chain rule을 적용한 BP를 통해 모델을 업데이트 하면서 발전하였다.
    
- 지금 나오고 있는 deep learning 계열의 혁신의 근간은 무엇이라고 생각하시나요?
    
    하드웨어의 발전
    
    품질이 좋은 데이터
    
- ROC 커브에 대해 설명해주실 수 있으신가요?
    
    binary classification model의 성능을 나타내는 지표
    
    FPR이 변할 때 TPR이 어떻게 변하는지를 나타내는 곡선이다. TPR이 recall인듯..!
    
    FPR은 임계값을 변경함으로써 움직일 수 있다. FPR
    
    ROC curve가 좌상단과 가까울수록 좋은 모델이라고 판단할 수 있다 !
    
    여기서 찍히는 점은 임계값을 조절할 수 있는 점
    
    Recall이 안에 포함되어 있고.. Precision이 없을걸 ?
    
- 여러분이 서버를 100대 가지고 있습니다. 이때 인공신경망보다 Random Forest를 써야하는 이유는 뭘까요?
    
    랜덤포레스트는 decision tree를 앙상블하여 하나의 모델로 구성하는 방법이다. random forest는 각 서버를 모델의 특성을 이해하는 decision tree로 병렬적이게 구성할 수 있다 ! 
    
    그에 반면 NN은 직렬적인.. 느낌이라
    
    Random forest가 낫다고는 하는데
    
    나는 여러 모델을 쓸 것 같음..! 이 데이터에 다양한 모델을 적용해서.. 실험적으로 맞는 모델을 찾을 것 같습니다.
