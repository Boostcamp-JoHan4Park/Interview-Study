# OS

## CPU 스케줄러인 FCFS, SJF, SRTF, Priority Scheduling, RR에 대해 간략히 설명해주세요.

- CPU 스케줄러란 ?

    ![](https://i.imgur.com/zVRR4my.png)


    - 다중 프로그램 OS의 기본으로, 여러 프로세스듣ㄹ이 CPU를 교환하며 보다 생산적으로 동작합니다.
    
    - CPU를 선점한 프로세스가 대기하는 시간을 보다 효율적으로 사용하기 위하여 사용합니다.

    - 기본적으로 다음에 실행될 프로세스를 정하고, 프로세스들을 실행가능한 상태로 만듭니다.

- 비선점 vs 선점 스케줄링
    - 스케줄링은 다음과 같은 때에 일어납니다.
    
    1. Running -> Waiting 상태 : (ex. I/O 요청, 자식프로세스 종료 - wait() 요청을 통해 종료)
    
    2. Running -> Terminate 상태 : (ex. 부모프로세스의 종료)
    
    3. Running -> Ready 상태 : (ex. 인터럽트 발생)
    4. Waiting -> Ready 상태 : (ex. I/O 완료)

    - **비선점 스케줄링**

        ![](https://i.imgur.com/JufxAGB.png)

        - Time-slice가 없는 스케줄링
        - CPU를 사용중인 프로세스가 자율적으로 반납하도록 하는 방식
        - 따라서 프로세스가 자율적으로 CPU를 반납하는 시점에서 사용합니다. [1, 2 시점]

    - **선점 스케줄링**
        
        ![](https://i.imgur.com/4qaKhAk.png)


        - 낮은 우선순위를 가진 프로세스보다 높은 우선순위를 가진 프로세스가 CPU를 선점하는 방식
        - OS가 스케줄링의 알고리즘에 따라 적당한 프로세스에게 CPU를 할당하고, 필요시에는 회수하는 방식
        - 일반적으로 3,4 시점에서 사용하지만, 상황에 따라 1,2 에서도 스케줄링이 가능합니다.

- CPU 스케줄링 알고리즘의 목적

    - 일반적인 시스템에서는 다음과 같은 목적을 공통적으로 지닌다.
        - No starvation : 각각의 프로세스들이 오랜시간동안 CPU를 할당받지 못하는 상황이 없도록 합니다.
        - Fairness : 각각의 프로세스에 공평하게 CPU를 할당해줍니다.
        - Balance : Keeping all parts of the system busy

    - Batch System [일괄처리 시스템]
        
        : 온라인처럼 일에 대한 요청이 발생했을 때, 즉각적으로 처리하는 것이 아닌 일정기간 또는 일정량을 모아뒀다가 한번에 처리하는 방식
        
        - Throughput : 시간당 최대의 작업량을 냅니다.
        
        - Turnaround Time : 프로세스의 생성부터 소멸까지의 시간을 최소화합니다.

        - CPU utilization : CPU가 쉬는 시간이 없도록 합니다.

    - Interative System [대화형 시스템]
        
        : 온라인과 같이 일에 대한 요청에 대해 즉각적으로 처리하여 응답을 받을 수 있는 시스템
        
        - Response time : 즉각적으로 처리해야하는 시스템이므로 요청에 대한 응답시간을 줄이는 게 중요합니다.

    - Time Sharing System

        : 각 프로세스에 CPU에 대한 일정시간을 할당하여 주어진 시간동안 프로그램을 수행할 수 있게하는 시스템
        
        - Meeting deadlines : 데이터의 손실을 피하며, 끝내야하는 시간 안에 도달해야 합니다.
        - Predictability : 멀티미디어 시스템에서의 품질이 저하되는 부분을 방지해야 합니다.

- ### 스케줄링 알고리즘

    - 비선점 스케줄링 [Non-preemptive scheduling]
        - FCFS(First Come First Served)
            - 먼저 CPU를 요청하는 프로세스를 먼저 처리하는 방식

        - SJF (Shortest Job First)
            - 평균 waitng time 을 최소화하기 위해 사용하는 방식
            - 버스트 시간이 짧은 프로세스부터 CPU를 할당합니다.

     - 선점 스케줄링 [Preempitive scheduling]
        - 선점 스케줄링에는 몇가지 룰이 있습니다.
            - 높은 우선순위를 가지는 프로세스는 항상 먼저 스케줄되어야 합니다.
                - Dynamic priority scheme : 커널안에서 프로세스의 우선순위는 지속적으로 변합니다 (Fixed priority scheme)

            - I/O-bound process는 CPU-bound process보다 반드시 높은 우선순위에 있어야 합니다.
            - Time slice의 양은 CPU burst time보다 조금만 더 많아야 합니다.
                - time slice가 더 적을 경우, 불필요한 context swith가 많이 일어납니다.
                - time slice가 훨씬 큰 경우, I/O가 일어날 때에 CPU를 반납하거나, 다른 프로세스는 CPU에 굶주리는 현상이 일어날 수 있습니다.

            - Real-time 프로세스는 다른 프로세스에 비해 매우 높은 우선순위를 갖습니다.

        - SRT(Shortest Remaining Time)
            - 최단 잔여시간을 우선으로 하는 스케줄링.
            - 진행 중인 프로세스가 있어도, 최단 잔여시간인 프로세스를 위해 sleep시키고 짧은 프로세스를 먼저 할당합니다.
            - 선점형 SJF 스케줄링이라 불립니다.

        - RR(Round Robin)
            - TIme Sharing System을 위해 설계된 스케줄링
            - 모든 프로세스가 같은 우선순위를 가지고, Time slice를 기반으로 스케줄링을 합니다.
            - Time slice burst가 일어나면 해당 프로세스는 스케줄링 큐의 끝으로 이동합니다.

            - 알고리즘의 성능은 Time slice 크기와 같아집니다.
                - Time slice가 심하게 크면 FCFS와 다를게 없습니다.
                - Time slice가 너무 작다면 불필요한 COntext Switch가 많이 일어납니다.

        - Priority Scheduling (우선 순위 스케줄링)
            - 우선 순위가 높은 프로세스에 CPU를 우선 할당하는 방식의 스케줄링
            - 우선 순위는 시간 제한, 메모리 요구량, 프로세스의 중요성, 자원사용 비용 등에 따라 달라질 수 있습니다.
            - 우선 순위가 같을 경우, FCFS와 다를게 없습니다. (비선점, 선점 둘다 사용됩니다.)



## 동기와 비동기의 차이를 알려주세요.

### 1. 동기 (synchronous : 동시에 일어나는)

- 동기는 말 그대로 도잇에 일어난다는 뜻입니다. 요청과 그 결과가 동시에 일어난다는 약속으로 바로 요청을 하면 시간이 얼마나 걸리던지 요청한 자리에서 결과가 주어져야 합니다.

- **동기 방식**은 설계가 매우 간단하고 직관적이지만 결과가 주어질 때까지 아무것도 못하고 대기해야 하는 단점이 있습니다.


### 2. 비동기 (Asynchronous : 동시에 일어나지 않는)

- 비동기는 동시에 일어나지 않는다는 의미입니다. 요청한 결과는 동시에 일어나지 않을거라는 약속입니다.

- 요청한 그 자리에서 결과가 주어지지 않습니다.
- 노드 사이의 작업 처리 단위를 동시에 맞추지 않아도 됩니다.

- **비동기 방식**은 동기보다 복잡하지만 결과가 주어지는데 시간이 걸리더라도 그 시간 동안 다른 작업을 할 수 있으므로 자원을 효율적으로 사용할 수 있는 장점이 있습니다.

