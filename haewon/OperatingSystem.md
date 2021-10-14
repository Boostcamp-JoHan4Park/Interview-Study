# Operatimg System

## Questions  
* [프로세스와 스레드의 차이(Process vs Thread)를 알려주세요.](#1)  
* [멀티 프로세스 대신 멀티 스레드를 사용하는 이유를 설명해주세요.](#2)  
* [캐시의 지역성에 대해 설명해주세요.](#3)  
* [Thread-safe에 대해 설명해주세요. (hint: critical section)](#4) 
* [뮤텍스와 세마포어의 차이를 설명해주세요.](#5)  
* [스케줄러가 무엇이고, 단기/중기/장기로 나누는 기준에 대해 설명해주세요.](#6)  

## Answers  
### #1
  
프로세스는 운영체제로 부터 시스템 자원을 할당받은 __작업의 단위__ 로, 각 프로세스는 각각 독립된 메모리 영역을 할당 받습니다. 
하지만, 스레드는 프로세스가 할당받은 자원을 이용하는 __실행(흐름)의 단위__ 로, 프로세스 내 하나 이상 존재하며, stack 메모리 영역외의 다른 메모리 영역(data, code, heap)은 다른 스레드와 공유합니다.

더 나아가 각 프로세스는 별도의 주소 공간에서 실행되어서 한 프로세스는 다른 프로세스의 변수나 자료구조에 접근할 수 없기에, 한 프로세스가 다른 프로세스의 자원에 접근하려면 IPC(inter-process-communication)를 사용해야 합니다. 

### #2
__KeyWord__ : Context switching 오버헤드    

![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/c7e4a03d-d255-442b-a412-8e83d9f4d8bb/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210929%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210929T162222Z&X-Amz-Expires=86400&X-Amz-Signature=072e951ddf13f6cde8be9621758d062fc498962b0974d6323912262029f9e676&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)
![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/350a598f-6615-4bd6-a91b-1f3d37db0e55/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210929%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210929T162400Z&X-Amz-Expires=86400&X-Amz-Signature=eecd0be0aedd8c8cebf2ec9e100a240612635825c8c89e80e49d26c135dd3d7d&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)
- 멀티 프로세스 : 하나의 프로그램을 여러개의 프로세스로 구성하여, 각 프로세스가 하나의 작업을 처리하는 것
    
    +) 독립된 구조이므로 하나의 프로세스가 잘못되어도 프로그램은 작동함
    
    -) Context switching 비용 발생 → 동작중인 프로세스가 대기를 하면서 해당 프로세스의 상태를 보관하고 대기하고 있다가 다시 실행시 복구하는 비용
    
- 멀티 스레드 : 프로그램을 여러개의 스레드로 구성하고, 각 스레드가 작업을 처리하는 것
    
    +) 시스템 자원 소모 감소, 처리비용 감소, 스레드간 자원공유
    
    -) 디버깅 어려움, **동기화 이슈발생,** 하나의 스레드의 오류로 전체 프로세스에 문제


### #3

**캐시메모리는 속도가 빠른 장치와 느린 장치간의 속도 차에 따른 병목 현상을 줄이기 위한 범용 메모리이다.**  이러한 역할을 수행하기 위해선 CPU가 어떤 데이터를 원할 것인가를 어느 정도 예측할 수 있어야 한다.  이때, **적중률(cache hit rate)을 극대화 시키기 위해서 데이터 지역성(Locality)의 원리를 사용한다.** 

프로그램은 모든 코드나 데이터를 균등하게 access하지 않고, 어느 한 순간에 특정 부분을 집중적으로 참조한다는 것이 캐시의 지역성의 전제이다. 지역성은 대표적으로 시간 지역성과 공간지역성으로 나뉨.

- 시간 지역성: 최근에 참조된 주소의 내용은 곧 다음에 다시 참조되는 특성
- 공간 지역성: 대부분의 실제 프로그램이 참조된 주소와 인접한 주소의 내용이 다시 참조되는 특성

### #4
스레드 안전(thread safety)은 멀티 스레드 프로그래밍에서 일반적으로 어떤 함수나 변수, 혹은 객체가 여러 스레드로부터 동시에 접근이 이루어져도 수행 결과가 올바르게 나오고, 프로그램의 실행에 문제가 없는 것을 말합니다.  Thread-safe하기 위해서는 공유 자원에 접근하는 임계영역(critical section)을 동기화 기법으로 잘 제어해주어야 합니다. 

**Thread-safe를 지키기 위한 방법**

1. Re-entrancy

thread에서 동작하는 코드가 동일 thread에서 재수행되거나, 다른 thread에서 해당 코드를 동시에 수행해도 **동일한 결과값**을 얻을 수 있도록 코드를 작성합니다. 

2. Thread-local storage

**특정 thread에만 접근 가능한 저장소**를 만듭니다. 공유 자원의 사용을 최대한 줄여 각각의 특정 스레드에서만 접근 가능한 저장소들을 사용함으로써 동시 접근을 막는다. 이 방식은 동기화 방법과 관련되어 있고, 또한 공유상태를 피할 수 없을 때 사용하는 방식이다.

3. **Mutual exclusion ⇒ 통상적으로 Mutual Exclusion(상호배제) 방식을 이용한 Critical Section 처리가 자주 사용되는 편**

공유 자원을 꼭 사용해야 할 경우 해당 자원의 접근을 세마포어 등의 lock으로 하나의 thread만 접근 가능하게 통제한다.

여기서 임계영역이란 멀티 스레드에 의해 공유자원이 서로 참조될 수 있는 코드의 범위를 말하고, 멀티 스레드 프로그램에서 임계영역을 제대로 처리하지 못하는 경우 심각한 문제가 발생할 수 있기 때문에, **동기화 기법(MUtex, Semaphore)** 으로 이 문제를 해결합니다. 

4. Atomic operations

공유 자원에 접근할 때 원자 연산을 이용하거나 '원자적'으로 정의된 접근 방법을 사용함으로써 상호 배제를 구현할 수 있다.

5. Immutable Object 

객체 생성 이후에 값을 변경할 수 없도록 만듭니다.


