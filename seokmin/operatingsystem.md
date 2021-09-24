# Operating System  

## Questions  
* [프로세스와 스레드의 차이(Process vs Thread)를 알려주세요.](#1)  
* [멀티 프로세스 대신 멀티 스레드를 사용하는 이유를 설명해주세요.](#2)  
* [캐시의 지역성에 대해 설명해주세요.](#3)  
* [Thread-safe에 대해 설명해주세요. (hint: critical section)](#4)  

## Answers
### #1
### #2
### #3

캐시는 주기억장치에서 자주 사용하는 데이터들을 캐시에 올려 사용하여 빠르게 처리하는 것이 목적이다. 어떠한 데이터가 필요할지 Hit율을 극대화시키기 위해 지역성의 원리를 사용한다. 지역성은 기억 장치 내의 정보를 균일하게 access하는게  아닌 특정 부분을 집중적으로 참고하는 특성이다. 이러한 지역성을 캐시에 적용한 것으로 대표적으로 시간 지역성, 공간 지역성이 있다.

시간 지역성 : 최근에 참조된 주소의 내용은 곧 다음에 다시 참조되는 특성

공간 지역성 : 대부분의 실제 프로그램이 참조된 주소와 인접한 주소의 내용이 다시 참조되는 특성



REF

https://k39335.tistory.com/38



### #4

Thread safe는 멀티 스레드 프로그래밍에서 일반적으로 어떤 함수나 변수, 객체가 여러 스레드로부터 동시에 접근이 이루어져도 프로그램의 실행에 문제가 없음을 뜻함.

주로 Mutual Exclusion 방식을 이용한 Critical Section 처리가 자주 사용되는 편이다. 

Mutual Exclusion : 한 Thread가 자원에 접근할 때 다른 Thread의 접근을 막는 것 / semaohore등의 lock으로 통제



REF

https://gompangs.tistory.com/entry/OS-Thread-Safe%EB%9E%80