# 네트워크 참조 모델
통신이 일어나는 각 과정을 계층으로 나눈 구조를 네트워크 참조 모델이라 한다.
계층으로 표현한다는 점에서 네트워크 모델이라고도 한다.

1. 네트워크 구성과 설계가 용이하다
각 계층이 수행해야 할 역할이 정해져 있으므로 계층의 목적에 맞게 프로토콜과 네트워크 장비를 계층별로 구성할 수 있다.


2. 네트워크 문제 진단과 해결이 용이하다
통신 과정에서 문제가 발생해도 문제의 원인을 계층별로 진단하기 수월하다.


## OSI 모델
![OSI 모델](https://velog.velcdn.com/images%2Fcgotjh%2Fpost%2F52907c8c-c149-4943-ad21-3996f44f912f%2F995EFF355B74179035.jpg)

OSI 모델은 국제 표준화 기구 ISO에서 만든 네트워크 참조 모델이다.

1. 물리 계층, Physical Layer
- OSI 최하단 계층이며 1과 0으로 표현되는 비트 신호를 주고 받는 계층
- 가장 근원적인 통신이 이루어진다
- 주로 전기적, 기계적, 기능적인 특성을 이용해 데이터를 전송
- 데이터 전달의 역할을 할 뿐이라 알고리즘, 오류제어 기능이 없다
- 장비로는 케이블, 리피터, 허브 등이 있다.

2. 데이터 링크 계층, Data-Link Layer
- 물리적인 연결을 통해 인접한 두 장치 간의 신뢰성있는 정보 전송을 담당, Point-To-Point 전송
- 안전한 정보 전송이라는 것은 오류나 재전송하는 기능이 존재
- MAC 주소를 통해 통신
- 데이터 링크 계층에서의 단위는 '프레임'(frame)
- 장비로는 브리지, 스위치가 있다.

3. 네트워크 계층, Network Layer
- 중계 노드를 통해 전송하는 경우 어떻게 중계할 것 인지를 규정한다
- 라우팅 기능을 맡고 있는 계층으로 목적지까지 가장 안전하고 빠르게 데이터를 보내는 기능을 한다, 즉 최적의 경로를 설정할 수 있다.
- 컴퓨터에게 데이터를 전송할지 주소를 갖고 있어 통신가능 (IP주소가 Network 계층에 속한다)
- 네트워크 계층의 단위는 '패킷'(packet)
- 장비로는 라우터, L3 스위치가 있다.

4. 전송 계층, Transport Layer
- 종단 간 신뢰성이 있고 정확한 데이터 전송을 담당한다.
- 송신자와 수신자 간의 신뢰성있고 효율적인 데이터를 전송하기 위해 오류검출 및 복구, 흐름제어와 중복검사를 담당
- 데이터 전송을 위해 Port 번호를 사용한다. (대표적으로 TCP와 UDP 프로토콜이 있다)
- 전송 계층의 단위는 '세그먼트'(segment)

5. 세션 계층, Session Layer
- 통신 장치 간의 상호작용 및 동기화를 제공
- 연결 세션에서의 데이터 교환과 에러 발생 시의 복구 관리

6. 표현 계층, Presentation Layer
- 데이터를 어떻게 표현할지 정하는 역할의 계층
- 송신자에게서 온 데이터를 해석하기 위한 응용 계층 데이터 부호화, 변화
- 수신자에서 데이터의 압축을 풀 수 있는 방식으로 된 데이터 압축
- 데이터의 암호화와 복호화

7. 응용 계층, Application Layer
- 사용자가 이용하는 응용 프로그램과 가장 밀접한 게층
- 응용 프로세스 간의 정보 교환을 담당


# TCP/IP 모델
![참고자료](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FzHY0n%2FbtsFeFXz9Gt%2F6sFyMfC050SgLkQNeLjz9k%2Fimg.png)

TCP/IP 모델은 이론보다는 구현에 중점을 둔 네트워크 참조 모델이다
OSI 모델의 목적이 '이상적 설계'에 가깝다면, TCP/IP 모델은 '실용적 구현'에 가깝다.

![OSI/TCP](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcJ4NW7%2FbtrNvrXRIJv%2FWa6HK1SZq8b67Lo6ytyIS1%2Fimg.png)

1. 네트워크 인터페이스 계층 || 네트워크 계층 || 링크 계층
- OSI 모델의 데이터 링크 계층과 유사 

2. 인터넷 계층, Internet Layer
- OSI의 네트워크 계층과 유사하다

3. 전송 계층, Transport Layer
- OSI모델의 전송 계층과 유사

4. 응용 계층, Application Layer
- OSI 모델의 세션, 표현, 응용 계층을 합친것과 유사하다

![확장형](https://velog.velcdn.com/images%2Fjwkim%2Fpost%2F1a15f96e-6644-4527-a97d-50aa7be8b1ac%2Fimage.png)

# 캡슐화 역캡슐화
패킷은 송신 과정에서 캡슐화가 이루어지고 수신 과정에서 역캡슐화가 이루어진다.

![과정](https://velog.velcdn.com/images%2Fqmasem%2Fpost%2F95b1f952-96d9-4c2a-89b5-b9feefc02c65%2Fimage.png)

## 캡슐화, Encapsultaion
![캡슐화](https://velog.velcdn.com/images%2Fqmasem%2Fpost%2Ffa686116-bcda-49f0-929c-d2553fc7deb8%2Fimage.png)

참고: https://velog.io/@qmasem/TIL-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EC%BA%A1%EC%8A%90%ED%99%94-%EC%97%AD%EC%BA%A1%EC%8A%90%ED%99%94-encapsulation-decapsulation

> 역캡슐화란 이 과정을 물리계층부터 응용계층까지 올라가면서 메시지를 받는 과정을 말한다.

한단계 아래 계층은 바로 위의 계층으로부터 받은 패킷에 헤더 및 트레일러를 추가해 나간다
이렇게 송신 과정에서 헤더 및 트레일러를 추가해 나가는 과정을 캡슐화라 한다.


## 역캡슐화, Decapsulation
메시지를 수신할 때 캡슐화 과정에서 붙었던 헤더 및 트레일러를 각 계층에서 확인한 뒤 제거한다.

# PDU
각 계층에서 송수신되는 메시지의 단위를 PDU, Protocol Data Unit이라 한다.
즉 상위 계층에서 받은 데이터에 현재 계층의 프로토콜 헤더(및 트레일러)를 추가하면 현재 계층의 PDU가 된다.

![PDU](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8d/OSI_Model_v1.svg/870px-OSI_Model_v1.svg.png)

- 참고: https://velog.io/@hidaehyunlee/%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8-%ED%8C%A8%ED%82%B7-%ED%97%B7%EA%B0%88%EB%A6%B4-%EB%95%90-PDU%EB%A5%BC-%EC%95%8C%EC%95%84%EB%B3%B4%EC%9E%90

PDU는주로 전송 계층 이하의 메세지를 구분하기 위해 사용된다.

> '패킷'이란 용어는 패킷 교환 네트워크에서 쪼개어져 전송되는 단위를 통칭하기 위한 일반적인 용어로 사용되지만, 혼동 방지를 위해 네트워크 계층의 PDU는 'IP 패킷'이라 지칭한다.


