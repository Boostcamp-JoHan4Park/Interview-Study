* 어떨 때 모수적 방법론을 쓸 수 있고, 어떨 때 비모수적 방법론을 쓸 수 있나요?  

[ref](https://zzanhtt.tistory.com/18)
키워드: 표본의 개수, 정규성  
짧은 답: 표본의 개수가 작아서 정규성을 갖지 못한다면 비모수적 방법, 갖는다면 모수적 방법을 쓴다.  


* “likelihood”와 “probability”의 차이는 무엇일까요?  

[ref](http://rstudio-pubs-static.s3.amazonaws.com/204928_c2d6c62565b74a4987e935f756badfba.html)

키워드: 연속함수, discrete
짧은 답: 연속함수에서 둘은 다르지만 discrete 함수에서는 같다.


* Gradient Descent에 대해서 쉽게 설명한다면?  
답: 목적함수를 최소화하기 위해 목적함수의 미분값을 사용해 parameter를 조정
  * 왜 꼭 Gradient를 써야 할까? 그 그래프에서 가로축과 세로축 각각은 무엇인가? 실제 상황에서는 그 그래프가 어떻게 그려질까?  
  답: 목점함수의 gradient를 계산해서 parameter를 업데이트할 수 있기 때문이다. parameters에 대한 목점함수의 그래프는 y축: cost, x축: parameters가 된다.
  실제로는 convex function의 형태를 가질 것이다.

  * GD 중에 때때로 Loss가 증가하는 이유는?  
  답: 목적함수를 최소화하는 과정에서 cost를 최소화하지 못하고 늘리는 경우가 발생했을 때, loss가 증가한다.

  * Back Propagation에 대해서 쉽게 설명 한다면? 
  model에 값을 통과시켜서 model의 출력값을 얻는 과정을 forward propagation이라고 한다. gradient descent를 통해 parameter를 업데이트해야하는데, Loss를 parameter에 대해 미분해서 gradient를 구할 수 있고, 이를 통해 parameters를 업데이트할 수 있다.

  * Association Rule의 Support, Confidence, Lift에 대해 설명해주세요.  
  - support: 두 사건이 함계 발생할 비율
  - confidence: X가 발생할 경우, X와 Y가 함께 나올 비율
  - lift: X와 Y가 나오는 비율을 X, Y가 각각 나올 비율의 곱으로 나눈 값
  
* 최적화 기법중 Newton’s Method와 Gradient Descent 방법에 대해 알고 있나요?  
[ref](https://astralworld58.tistory.com/86)  
Newton's method: f(x)의 해를 찾는 방법. 임의의 x에서 f(x)에 대한 접선이 x축과 만나는 지점을 다음 x로 설정해서 해를 찾는다. 해를 찾는 수렴속도가 빠르고, 해 근처에서 수렴속도가 느려진다.

gradient descent: f`(x)의 해를 찾는 방법. 모든 차원과 공간에서 활용가능하며 미분의 극소값을 찾는다. 해에 근접할수록 기울기가 0에 가까워지기 때문에 수렴속도가 느려진다.