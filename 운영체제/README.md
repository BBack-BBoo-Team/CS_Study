# 운영체제

### 목차
[1. 운영체제란](https://github.com/BBack-BBoo-Team/CS_Study/edit/master/%EC%9D%B4%EB%A1%A0%EC%A0%95%EB%A6%AC/%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/README.md#1-%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%EB%9E%80) <br>
[2. 메모리 구조](https://github.com/BBack-BBoo-Team/CS_Study/edit/master/%EC%9D%B4%EB%A1%A0%EC%A0%95%EB%A6%AC/%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/README.md#2-%EB%A9%94%EB%AA%A8%EB%A6%AC-%EA%B5%AC%EC%A1%B0ram-%EC%A3%BC%EA%B8%B0%EC%96%B5%EC%9E%A5%EC%B9%98) <br>
[3. 프로세스와 스레드](https://github.com/BBack-BBoo-Team/CS_Study/edit/master/%EC%9D%B4%EB%A1%A0%EC%A0%95%EB%A6%AC/%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/README.md#3-%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4%EC%99%80-%EC%8A%A4%EB%A0%88%EB%93%9C)<br>
[4. CPU스케줄러](https://github.com/BBack-BBoo-Team/CS_Study/edit/master/%EC%9D%B4%EB%A1%A0%EC%A0%95%EB%A6%AC/%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/README.md#4-cpu-%EC%8A%A4%EC%BC%80%EC%A4%84%EB%9F%AC)<br>
[5. 가상메모리](https://github.com/BBack-BBoo-Team/CS_Study/edit/master/%EC%9D%B4%EB%A1%A0%EC%A0%95%EB%A6%AC/%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/README.md#5-%EA%B0%80%EC%83%81-%EB%A9%94%EB%AA%A8%EB%A6%AC)<br>
[6. 데드락](https://github.com/BBack-BBoo-Team/CS_Study/edit/master/%EC%9D%B4%EB%A1%A0%EC%A0%95%EB%A6%AC/%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/README.md#6-%EB%8D%B0%EB%93%9C%EB%9D%BD)

---

## 1. 운영체제란?
* 시스템의 자원(CPU, 메모리 등)과 동작을 관리하는 소프트웨어
* 프로세스, 저장장치, 네트워킹, 사용자, 하드웨어 관리
<br>

## 2. 메모리 구조(RAM, 주기억장치)
* 메모리 공간 종류 4가지 : Code, Data, Heap, Stack
  * 코드 영역 : 실행할 프로그램의 코드
  * 데이터 영역 : 전역 변수, 정적 변수
  * 힙 영역 : 사용자의 동적 할당 - 런타임에 크기가 결정
  * 스택 영역 : 지역 변수, 매개 변수 - 컴파일 타임에 크기 결정
* [관련 링크](https://jinshine.github.io/2018/05/17/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B8%B0%EC%B4%88/%EB%A9%94%EB%AA%A8%EB%A6%AC%EA%B5%AC%EC%A1%B0/)

> 컴파일 : 프로그램을 배포할 때, 사람이 이해하는 언어를 컴퓨터가 이해할 수 있는 언어로 바꾸어 주는 과정 <br> 런타임 : 컴퓨터 프로그램이 실행되고 있는 동안의 동작

<br>

## 3. 프로세스와 스레드
* 프로세스 : 실행중인 프로그램
* 스레드 : 프로세스 내에서 실행되는 여러 흐름의 단위

### 3-1. 프로세스 특징
* 운영체제에는 여러 개의 프로세스가 들어감
* 프로세스는 각각 독립된 메모리 영역(Code, Data, Stack, Heap 구조)을 할당받음
* 기본적으로 프로세스당 최소 1개의 스레드(메인 스레드)를 가지고 있음
* 각 프로세스는 별도의 주소 공간에서 실행되며, 한 프로세스는 다른 프로세스의 변수나 자료구조에 접근할 수 없음
* 한 프로세스가 다른 프로세스의 자원에 접근하려면 프로세스 간의 통신(IPC, Inter-process communication)을 사용, Ex.파이프, 파일, 소켓 등을 이용한 통신 방법

### 3-2. 스레드 특징
* 스레드는 프로세스 내에서 각각 Stack 영역만 할당, Code, Data, Heap 영역은 서로 공유
* 스레드는 한 프로세스 내에서 동작되는 여러 실행의 흐름으로, 프로세스 내의 주소 공간이나 자원들을 같은 프로세스 내에 스레드끼리 공유하면서 실행
* 각각의 스레드는 별도의 레지스터와 스택을 갖고 있음

<br>

## 4. CPU 스케줄러(CPU Scheduler)
* CPU 할당하는 방법
* 운영체제는 __CPU 스케줄러__ 를 통해 준비 큐에 있는 프로세스 중 한 프로세스를 골라 다음에 실행

### 4-1 스케줄링 알고리즘
* 비선점 스케줄링(Non-preemptive scheduling)
  * FCFS(First Come First Served) : 먼저 CPU를 요청하는 프로세스를 먼저 처리하는 방식
  * SJF(Shortest Job First) : 버스트 시간이 짧은 프로세스부터 CPU 할당, 평균 waiting time 을 최소화하기 위해 사용
* 선점 스케줄링(Preemptive scheduling)
  * SRT(Shortest Remaining Time) : 최단 잔여시간을 우선으로 하는 스케줄링 -> 진행중인 프로세스가 있어도, sleep 시키고 짧은 프로세스를 먼저 할당
  * RR(Round Robin) : 모든 프로세스가 같은 우선순위를 가지고, time slice를 기반으로 스케줄링(동일하게 시간 사용) -> Context Switch 비용이 발생
  * Priority Scheduling(우선 순위 스케줄링) : 부여된 우선 순위가 높은 프로세스에 CPU를 우선 할당하는 방식

<br>

## 5. 가상 메모리
* 사용하는 부분만 메모리에 올리고, 나머지는 디스크에 보관

> Q. 가상 메모리가 무엇인가요? <br><br> A. 모든 프로세스에게 메모리를 할당하기에는 메모리의 크기가 한계가 있어서 사용하는 방법입니다. 프로세스에서 사용하는 부분만 메모리에 올리고, 나머지는 디스크에 보관하는 기법을 말합니다. 

## 6. 데드락
* 프로세스가 자원을 얻지 못해, 다음 작업을 하지 못하는 상태

### 6-1. 데드락 발생 조건
> 데드락은 아래 네 가지 조건이 동시에 필수로 성립 할 때 발생한다.

* 상호 배제(Mutual exclusion) : 자원은 한 번에 한 프로세스만이 사용할 수 있어야 한다.
* 점유 대기(Hold and wait) : 최소한 하나의 자원을 점유하고 있으면서 다른 프로세스에 할당되어 사용하고 있는 자원을 추가로 점유하기 위해 대기하는 프로세스가 있어야 한다.
* 비선점(No preemption) : 다른 프로세스에 할당된 자원은 사용이 끝날 때까지 강제로 빼앗을 수 없어야 한다.
* 순환 대기(Circular wait) : 프로세스의 집합 {P0, P1, .. Pn} 에서 P0는 P1이 점유한 자원을 대기하고 P1은 P2, Pn-1은 Pn이 점유한 자원을 대기하며, Pn은 P0가 점유한 자원을 요구한다.

> Q. 데드락이 무엇인가요? <br> A. 데드락은 프로세스가 자원을 얻지 못해 다음 작업을 하지 못하는 상황입니다. <br> 예를 들면, P1, P2가 각각 자원 A와 B를 얻어야 되는데 P1이 A를, P2이 B를 가지고 있어서, 서로 무한정 기다리는 상태들 데드락이라고 합니다. <br> 데드락은 다음의 네가지 조건이 동시에 발생해야 성립이 가능한데요. 그 네가지는 상호배제, 점유대기, 비선점, 순환대기 입니다.
