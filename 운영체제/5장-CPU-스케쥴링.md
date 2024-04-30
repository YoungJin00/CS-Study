## [CPU 스케쥴링 #1](https://core.ewha.ac.kr/publicview/C0101020140328151311578473?vmode=f)

### CPU and I/O Bursts in Program Execution

- I/O와 CPU의 작업이 반복됨
- CPU를 누구한테 줄 것인가, 맡긴 후 계속 쓰게 할 것인가의 두 가지 고민이 필요함

### CPU-burst Time의 분포

- cpu를 연속적으로 쓰는 시간. 짧은 경우가 빈번함(I/O 가 끼어드는 경우)
- CPU bound job: 짧은 경우 = 사람과 interaction 하는 경우
- 여러 종류의 job(process)이 섞여 있기 때문에 cpu 스케줄링 필요.
- Interactive job에게 적절한 response 제공 요망

### 프로세스의 특성 분류
4장 참고.
- IO-bound process
- CPU-bound process

### CPU Scheduler & Dispatcher

- CPU Scheduler:
- Dispatcher: 
- nonpreemptive(비선점형): cpu 자진반납
- preemptive: 강제로 빼앗기

### 스케쥴링 성능 척도(Scheduling Criteria)

시스템 입장(하나로 일 많이 시키는게 좋음) - 사장
- 이용률: cpu가 일한 시간/전체시간
- 처리량: 주어진 시간 동안 몇 개의 일을 처리했는가
---
프로그램 입장(cpu를 빨리 얻어서 빨리 끝나는게 좋음) - 고객
- Turnaround Time(소요 시간): cpu를 쓰러 들어와서 다 쓰고 나갈 때까지 걸린 시간
  - 시간==cpu관점이기 때문에 프로세스 시작~종료 시간이 아님
- 대기 시간: ready queue에서 기다린 시간의 총 합
- 응답 시간: 처음으로 cpu를 얻기 까지 걸린 시간
  - time sharing환경에선 사용자 응답과 관련해서 중요하기 때문
- 선점형인 경우 응답시간과 대기시간이 다를 수 있다.

### 스케쥴링 알고리즘

- FCFS(First-Come First-Served): 먼저 온 순서대로 처리, 비선점형, 썩 좋은 방법은 아님
  - 먼저 온 프로세스의 길이가 짧으면 Waiting time이 짧아짐
  - Convoy effect: 긴 프로세스 뒤에 짧은 프로세스들이 지나치게 오래 기다려야하는 현상
- SJF(Shortest-Job-First): 각 프로세스의 다음번 CPU burst time을 가지고 스케줄링에 활용
  - Nonpreemptive: 현재 수행중인 프로세스가 cpu 사용
      - 사용 후 나가는 시점에 판단
  - Preemptive: 현재 수행중인 프로세스의 burst time 보다 더 짧은 cpu burst time을 가지는 새로운 프로세스가 도착하면 CPU를 빼앗김
      - SRTF(Shortest-Remaining-Time-First)라고 도 부름
      - 새로운 프로세스 도착 시점에 판단
  - 최소 Average waiting time 보장(SRTF)
  - 문제점
      - Starvation: burst time이 긴 프로세스는 영원히 cpu를 못 받을 수 도 있음
      - cpu 사용시간을 미리 알 수 없음. 과거의 burst time을 이용한 추정만 가능함 (exponential averaging)
- Priority Scheduling: 우선순위가 가장 높은 프로세스에게 CPU 할당, 선점/비선점형이 있음
  - 보통 정수값으로 표현, 대부분 작은 숫자가 우선순위가 높다.
  - 문제: Starvation
  - 해결: Aging - 시간이 지나면 우선순위가 높아지도록 함
- Round Robin (RR): 각 프로세스는 동일한 크기의 할당 시간(time quantum)을 가짐, 선점형
  - 시간이 끝나면 대기 큐의 마지막으로 가서 줄선다.
  - 응답 시간이 빨라짐
  - 어떤 프로세스도 (n-1)q time unit 이상 기다리지 않음
  - q가 너무 작으면 context switch: 오버헤드가 커짐
  - (특이한 경우) 동일한 시간의 프로세스들이 있다면 안좋을 수도 있다. => time quantum을 길게 잡으면 됨

## [CPU 스케쥴링 #2](https://core.ewha.ac.kr/publicview/C0101020140401134252676046?vmode=f)

### 스케쥴링 알고리즘 (복수개)

-

### 스케쥴링 알고리즘 평가 

-
