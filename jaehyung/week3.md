# Week3  
<br>

## Statistics/Math  
* 조건부 확률은 무엇일까요?  
**Keyword** : ~가 일어났을때 ~가 일어날 확률  
조건부 확률은 사건 A 가 일어났다는 전제 하에 사건 B 가 일어날 확률이다. 이는 P(B|A) = P(B∩A) / P(A) 로 표현 가능하다. ![](./images/2021-09-30-12-10-06.png)  
조건부 확률은 베이즈 정리와도 이어진다.  
![](./images/2021-09-30-12-08-44.png)
* 공분산과 상관계수는 무엇일까요? 수식과 함께 표현해주세요.  
**Keyword** : 공분산, 상관계수, 단위크기, 단위화
공분산은 확률변수 X의 편차와 확률변수 Y의 편차를 곱한것의 평균 값이다. 두 변수간에 양의 상관관계가 있는지 음의 상관관계가 있는지는 알지만 상관관계가 얼마나 큰지는 모른다.  
![](./images/2021-09-30-13-18-01.png)  
공분산의 문제는 확률변수의 단위 크기에 영향을 많이 받는다.  
상관계수는 확률변수의 절대적 크기에 영향을 받지 않도록 공분산을 단위화 시킨 것이다. 공분산에 각 확률변수의 분산을 나누어주었다. 상관계수는 그 상관성이 얼마나 큰지도 알려준다. -1 또는 1에 가까울수록 상관성이 크고 0에 가까울수록 상관성이 작은 것이다.
![](./images/2021-09-30-13-24-35.png)

## Deep Learning  
* 알고있는 Activation Function에 대해 알려주세요. (Sigmoid, ReLU, LeakyReLU, Tanh 등)  
* 오버피팅일 경우 어떻게 대처해야 할까요?  

## Machine Learning  
* dimension reduction기법으로 보통 어떤 것들이 있나요?  
* PCA는 차원 축소 기법이면서, 데이터 압축 기법이기도 하고, 노이즈 제거기법이기도 합니다. 왜 그런지 설명해주실 수 있나요?  

## Network
* TCP와 UDP의 헤더를 비교해주세요.  
* TCP의 3-way-handshake와 4-way-handshake를 비교 설명해주세요.  

## Operating System  
* 뮤텍스와 세마포어의 차이를 설명해주세요.  
* 스케줄러가 무엇이고, 단기/중기/장기로 나누는 기준에 대해 설명해주세요.  

## Database  
* key 정리
    * Candidate Key  
    * Primary Key  
    * Alternate Key  
    * Super Key  
    * Foreign Key  
* SQL Join (join이란? join 종류)

## Algorithm  
* 시간, 공간 복잡도  
* Sort Algorithm  
    * Bubble Sort  
    * Selection Sort  
    * Insertion Sort  
    * Merge Sort  
    * Heap Sort  
    * Quick Sort  
    * Counting Sort  
    * Radix Sort  