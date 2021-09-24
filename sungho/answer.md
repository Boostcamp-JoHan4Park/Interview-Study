## Part1  
### [Statistics/Math](./answers/statistics-math.md)  

* 고유값(eigen value)와 고유벡터(eigen vector)에 대해 설명해주세요. 그리고 왜 중요할까요?  
* 샘플링(Sampling)과 리샘플링(Resampling)에 대해 설명해주세요. 리샘플링은 무슨 장점이 있을까요?  
* 확률 모형과 확률 변수는 무엇일까요?  
* 누적 분포 함수와 확률 밀도 함수는 무엇일까요? 수식과 함께 표현해주세요.  

### [Deep Learning](./answers/deep-learning.md)  

* 딥러닝은 무엇인가요? 딥러닝과 머신러닝의 차이는?  
* Cost Function과 Activation Function은 무엇인가요?  
* Tensorflow, PyTorch 특징과 차이가 뭘까요?  
* Data Normalization은 무엇이고 왜 필요한가요?  

### [Machine Learning](./answers/machine-learning.md)  

* 알고 있는 metric에 대해 설명해주세요. (ex. RMSE, MAE, recall, precision ...)  
* 정규화를 왜 해야할까요? 정규화의 방법은 무엇이 있나요?  
* Local Minima와 Global Minima에 대해 설명해주세요.  
* 차원의 저주에 대해 설명해주세요.  

<br>

## Part2
### [Python](./answers/python.md)  

* What is the difference between list and tuples in Python?  
**Keyword: mutable, dictionary key, iteration, identity**
1. list는 mutable, 가변적이고 tuple은 immutable, 불가변적이다. 
2. list는 python dictionary의 key 값으로 사용 할 수 없고, tuple은 가능하다. immutable한 객체를 dictionary key로 사용할 수 있기 때문에 tuple이라 할지라도 list와 같은 mutable 객체를 포함하게 되면 dictionary의 key로 사용 불가능.
3. iteration 순환 속도는 tuple이 더 빠르다.
4. python의 identity 정책 상, tuple은 슬라이싱을 통해 복사하더라도 여전히 같은 객체를 가르킨다.  
list는 다른 객체를 가르키게 된다. 즉, 객체의 Identity가 달라진다.

ref
- list, tuple의 차이 https://itholic.github.io/python-list-tuple/
- identity, equality https://itholic.github.io/python-identity-equality/  
---

* What are the key features of Python?  
**Keyword: Dynamic typed language, Interpreted language, OOP, Portable language, Large standard library**  
면접에서는 5개의 feature들을 열거해서 말하고 더 설명할 시간이 있다면 간략하게 feature들의 부연설명을 추가해보자.
1. Dynamic typed language  
별도의 type 지정이 필요하지 않고 Interpreter로 실행되는 run time에서 변수의 type이 결정된다. 보통 type에 대한 지식이 필요하지 않아도 되지만, type에 대한 배경지식이 있다면 더욱 잘 사용할 수 있다.
2. Interpreted language  
Compiler와 다르게 보통 run time에서 한 줄씩 번역하면서 프로그램을 실행한다. 즉, 플랫폼에 종속된 Interpreter가 필요하기 때문에 Portable language의 특성을 생성해준다.  번역 시간이 compiler보다 짧다는 장점이 있지만 코드의 performance는 complier가 더 뛰어나다.  
JITC와 Adaptive JITC에 대해서도 설명할 수 있다면 좋을 것인데 내용이 살짝 길어질 수 있다.  Interpreter만을 순수하게 사용하지 않고 Interpreter 기반으로 compiler르 적용해 코드를 최적화하는 방법론이다.  
ref: https://meetup.toast.com/posts/77

3. Objected-Oriented language  
Python의 모든 구성요소들은 Object라는 객체로부터 상속되어서 구현된다. OOP(Object-Oriendted Progarmming)에 대한 질문이 있다면 OOP의 특징을 열거해서 설명하자.
- 캡슐화(Encapsulation)
- 상속(Inheritance)
- 추상화(Abstraction)
- 다형성(Polymorphism)

4. Portable language (Interpreted language의 특징이기 때문에 2번에 묶어서도 설명 가능)  
Interpreter에서 설명된 부분  
5. Large standard library
타 언어보다 Built-in library의 종류와 수가 많다. 

* What type of language is python? Programming or scripting?  
Keyword: compiler, interpreted

python은 Interpreter 기반의 언어이다. 따라서 run time에서 프로그램의 conditional(분기점)이 생성되며 변수들의 type들이 결정된다. 

대부분의 Interpreter 언어들이 속도 향상을 위해 JIT compiler를 도입하는데 python도 이를 도입한 체계가 존재한다.  
JIT compiler는 interpreter의 실시간 번역 기능을 base로 하여, 자주 사용되거나 반복되는 코드느 byte code를 compile해 native code로 caching하여 필요할 때마다 불러온다.  
ref: https://hamait.tistory.com/476

* Python an interpreted language. Explain.  

Keyword: compiler, interpreter, jit

혼용한다.

기본적으로 사용되는 Python은 CPython인데, 이는 코드를 바이트코드로 compile 후, C로 구현된 interpreter에서 interpreting한다. 

바이트코드: interpretrer만을 위한 명령어 set로 구성된 코드

compiler, interpreter에 대한 상세한 칼럼인데 python을 중심으로 설명됐다. 질문에 대한 답도 포함돼있다.

ref: https://soooprmx.com/%ED%8C%8C%EC%9D%B4%EC%8D%AC%EC%9D%80-%EC%9D%B8%ED%84%B0%ED%94%84%EB%A6%AC%ED%84%B0%EC%96%B8%EC%96%B4%EC%9E%85%EB%8B%88%EA%B9%8C/

<br>

## Part3
### [Network](./answers/network.md)  

* TCP/IP의 각 계층을 설명해주세요.  
* OSI 7계층와 TCP/IP 계층의 차이를 설명해주세요.  
* Frame, Packet, Segment, Datagram을 비교해주세요.  
* TCP와 UDP의 차이를 설명해주세요.  

### [Operating System](./answers/operatingsystem.md)  

* 프로세스와 스레드의 차이(Process vs Thread)를 알려주세요.  
* 멀티 프로세스 대신 멀티 스레드를 사용하는 이유를 설명해주세요.  
* 캐시의 지역성에 대해 설명해주세요.  
* Thread-safe에 대해 설명해주세요. (hint: critical section)  

### [Database](./answers/database.md)  

* DBMS를 정의하세요.
* RDBMS를 정의하고 장점에 대해 설명하세요.
<br>