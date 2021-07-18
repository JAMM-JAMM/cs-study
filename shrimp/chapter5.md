### 프로세스와 스케줄러의 이해

#### 프로세스의 이해

- 프로세스 : 메인 메모리로 이동하여 실행중인 프로그램 (일반적인 정의)
  - 범위 : 메모리 구조 + 레지스터 set
  - 프로세스 별 독립적인 대상은 프로세스 범주에 포함 가능
  - RAM보다 더 큰 메모리 공간을 할당받았을 경우, 가상 메모리까지 사용
  - 멀티스레드, 멀티프로세스 환경에서 성능을 높이기 위한 기법 있음 (프로세스에게 각 레지스터 셋을 할당 → 컨텍스트 스위칭이 일어날 때 레지스터 셋 바꿀 필요 X )

#### 프로레스 스케줄러

윈도우즈 운영체제에서 제공하는 소프트웨어적으로 구현되어있는 장치(Block)

- 기능 : 둘 이상의 프로세스가 적절히 실행되도록 컨트롤 (CPU는 하나, 여러개의 프로세스 실행해야될때, 한순간에 하나의 프로세스만 실행 가능함으로 스케줄러가 CPU에게 순서를 정해줌, 정책을 결정하고 그대로 관리)
- 스케줄러도 하나의 프로세스, 스케줄러가 적게 작동하면 좋은 운영체제(OS)
- 방법 : 스케줄링 알고리즘에 따라 다양

#### 프로세스 상태
![image](https://user-images.githubusercontent.com/59052290/126061772-639a00c1-a0ca-41b4-9bea-050672eb910b.png)
- Ready

  - Running 전 상태
  - 스케줄러가 실행시켜주기 전까지 대기

- Running

  - CPU에 의해 실행중인 상태 (cpu가 하나, 맥시멈으로 동작되는 프로세스 개수 하나)

- Blocked

  - I/O 연산이 머무르다가 완료되면 Ready 상태로 전환(다시 실행시킬 수 있게 하기위해)
  - I/O 연산과 ALU 연산(사칙연산)의 병행을 위해 존재

  *I/O 연산 : CPU에 의존적이지 않은 연산, 컴퓨터와 데이터를 주고받는 연산이나, 프로그램 또는 장치

  *ALU 연산 : CPU에 의존적


#### 컨텍스트 스위칭

둘 이상의 프로세스가 실행될 때 메모리와 레지스터 셋에 들어가는 데이터를 전환하는 작업

컨텍스트 스위칭을 하는 대상이 많을수록 부담