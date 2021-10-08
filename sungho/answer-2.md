* 뮤텍스와 세마포어의 차이를 설명해주세요.  
Keyword: critical section, lock, 접근 가능 수

뮤텍스는 반드시 해당 section에 접근 중인 프로세스/스레드가 lock을 해제해야 한다.

세마포어는 세마포어의 변수만큼 프로세스/스레드가 접근 가능해서, 다른 프로세스/스레드가 lock을 해제할 수 있다.

ref: [Blog](https://junghyun100.github.io/Semaphore&Mutex/)

* 스케줄러가 무엇이고, 단기/중기/장기로 나누는 기준에 대해 설명해주세요.  
Keyword: long/medium/short term scheduler, swap, ready queue

스케쥴러: 어떤 프로세스에 자원을 할당할지 결정하는 커널 모듈

단기 스케쥴러(short term scheduler): CPU 스케쥴러. 준비 상태의 프로세스들 중 실행 상태로 변경할 프로세스 결정

중기 스케쥴러(medium term scheduler): 메모리에 탑재되는 프로세스 수를 조절하는 스케쥴러. Swap 대상이 되는 프로세스를 결정한다.

장기 스케쥴러(long term scheduler): 작업 스케쥴러. 현대 시분할 시스템을 채택하는 대부분의 OS에는 없는 개념. 

ref: [Blog](https://kosaf04pyh.tistory.com/191)