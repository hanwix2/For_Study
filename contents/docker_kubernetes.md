# Docker/Kubernetes

'***시작하세요! 도커/쿠버네티스***' 기반으로 작성
> https://book.naver.com/bookdb/book_detail.nhn?bid=16850447

## :memo: Contents
- [도커란?](#도커란)

---

## 도커란?

### 도커(Docker)
- 리눅스 컨테이너에 여러 기능을 추가함으로써 애플리케이션을 컨테이너로서 좀 더 쉽게 사용할 수 있게 만들어진 오픈소스 프로젝트
- 도커는 GO 언어로 작성됨
- 가상 머신과는 달리 도커 컨테이너는 성능의 손실이 거의 없음
- 도커라고 하면 일반적으로 도커 엔진(Docker Engine)를 의미
    > **도커 엔진**: 컨테이너를 생성하고 제어 및 관리하는 주체.  
    > *도커 관련 프로젝트: Docker Compose, Private Registry, Docker Hub, Docker for Desktop ...*

<br>

### 가상 머신과 도커 컨테이너

<p align="center">
    <img src="./images/VM and Docker.png" alt="가상 머신과 도커 컨테이너의 구조" width="60%" height="60%"/>
    <br/>
    가상 머신과 도커 컨테이너의 구조
    </p>

- **기존의 가상화 기술 (가상 머신)**
    - 정의:
        - Hypervisor를 이용해 여러 개의 운영체제를 하나의 호스트에서 생성해 사용하는 방식
        - 여러 개의 운영체제는 **가상 머신**이라는 단위로 구별되고 각 운영체제는 게스트 운영체제(Guest OS)라고 함
        - 각 게스트 운영체제는 완전히 독립된 공간과 시스템 자원을 할당받아 사용
        - 대표적인 가상화 툴: VirtualBox, VMware 등
    - 장점:
        - 완벽한 운영체제를 생성 가능
    - 한계:
        - 각종 시스템 자원을 가상화하고 독입된 공간을 생성하는 작업은 하이퍼바이저를 반드시 거치기 때문에 일반 호스트에 비해 **성능의 손실** 발생
        - 가상 머신은 게스트 운영체제를 사용하기 위한 라이브러리, 커널 등을 전부 포함하기 때문에 가상 머신을 배포하기 위한 **이미지의 크기가 큼**
    
- **도커 컨테이너**
    - 가상화된 공간을 생성하기 위해 리눅스 자체 기능인 chroot, namespace, cgroup을 사용함으로써 프로세스 단위의 격리 환경을 만들기 때문에 **성능 손실이 거의 없음**
    - 컨테이너에 필요한 커널은 호스트의 커널을 공유해 사용
    - 컨테이너 안에는 애플리케이션을 구동하는 데 필요한 라이브러리 및 실행 파일만 존재
    - **컨테이너를 이미지로 만들어 배포하는 시간이 빠름**

<br>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#dockerkubernetes)  
> https://medium.com/@darkrasid/docker%EC%99%80-vm-d95d60e56fdd  

<br>