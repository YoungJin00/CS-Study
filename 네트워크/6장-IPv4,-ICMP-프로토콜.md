### [IPv4 프로토콜](https://youtu.be/_i8O_o2ozlE?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)
: 네트워크 상에서 데이터를 교환하기 위한 프로토콜로 데이터가 정확하게 전달될 것을 보장하지 않는다.
: 중복된 패킷을 전달하거나 패킷의 순서를 잘못 전달할 가능성도 있다. (악의적으로 이용되면 DoS 공격이 된다)
: 데이터의 정확하고 순차적인 전달은 그보다 상위 프로토콜인 TCP에서 보장한다.

---
![](https://velog.velcdn.com/images/turtle_hw/post/bd2bf5c0-7619-4cf3-9633-4b6525af648a/image.png)
- IP option은 붙을 수도 있고 안붙을수도 있음(최대 10개 붙을 수 있음)
 	 - 옵션 하나씩 붙을때마다 4바이트씩 추가됨 
- 20바이트라고 생각하면 됨(총 60바이트까지 늘어날 수 있음)
- 보통은 옵션없이 사용해서 20바이트라고 생각하면 된다.
---
- Version = 버전 4가 온다고 생각하면 됨 16진수 하나가 4비트 (6이 오는 경우 없음/ 버전6은 이 모양자체가 아님) 
- IHL = 헤더의 길이
- identification과 flags(3비트)와 fragment offset(13비트)은 하나의 세트
- Flagment Offset = 첫 시작부분으로부터 떨어진 정도
- Time To Live(TTL) : 패킷이 존재할 시간을 지정. 오류로 특정 네트워크 대역에서 영원히 머물게되는 것을 방지함.
- Protocol : 상위 프로토콜의 타입을 알려준다. (ICMP : 1, 3계층, TCP : 6, 4계층, UDP: 17, 4계층)
- Header Checksum : 헤더에 오류가 있는지 비교해서 확인하는 파트 (손실 방지)
- Source IP Address : 출발지 IP주소
- Destination IP Address : 목적지 IP주소
 

### [ICMP 프로토콜](https://youtu.be/JaBCIUsFE74?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)
> Internet Control Message Protocol, 인터넷 제어 메시지 프로토콜
: 네트워크 컴퓨터 위에서 돌아가는 운영체제에서 오류 메시지를 전송받는 데 주로 쓰임
: 프로토콜 구조의 타입과 코드를 통해 오류 메시지를 전송받음

![](https://velog.velcdn.com/images/turtle_hw/post/a8e7150a-5050-4938-9c23-fb3464ee1d00/image.png)
- Type = 대분류  / Code = 소분류
---
![](https://velog.velcdn.com/images/turtle_hw/post/8f7b9fb3-5f0d-4804-b0d0-4161cdc56790/image.png)
> **[ Type ]**
0번, 8번 = 응답과 요청
3번, 11번 = 목적지 도달불가, 시간초과 / 3번은 아예 가지를 못한것 , 11번은 가긴했는데 응답을 못받는 것(ex. 상대방이 방화벽 켜둘 경우)
5번 = 원격지에 있는 상대방의 라우팅 테이블(지도)를 수정하는 것

---


### [라우팅 테이블](https://youtu.be/CjnKNIyREHA?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)
> 어디로 보내야 하는지 설정되어 있음 (내가 보낸 패킷은 어디로 갈까)

- 라우팅? 
    - 최적의 경로 = 주어진 데이터를 가장 짧거나 가장 빠른 시간 안에 전송할 수 있는 경로
    - 서로 다른 네트워크 대역에 있는 장치 간 통신을 할 때 최적의 경로를 통해 통신을 가능하게 해 주는 것

---

### [IPv4 조각화 이론](https://youtu.be/_AONcID7Sc8?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)
### 조각화란?
> 큰 IP 패킷들이 적은 MTU(Maximun Transmission Unit)를 갖는 링크를 통하여 전송되려면 여러 개의 작은 패킷으로 쪼개어/조각화 되어 전송되어야 함
즉, 목적지까지 패킷을 전달하는 과정에 통과하는 각 라우터마다 전송에 적합한 프레임으로 변환 필요

- 일단 조각화되면, 최종 목적지에 도달할 때까지 재조립되지 않는 것이 일반적
- IPv4에서는 발신지 뿐만 아니라 중간 라우터에서도 IP 조각화 가능
- IPv6에서는 IP 단편화가 발신지에서만 가능 / 재조립은 항상 최종 수신지에서만 가능함!!

---

### [IPv4 조각화 실습](https://youtu.be/QKEL9aBgHtg?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)
![](https://velog.velcdn.com/images/turtle_hw/post/f818970e-26f2-4cde-bff5-9d0a0e2d5732/image.png)

- 첫번째 패킷의 데이터 크기 = MTU(1500) - 20 = 1480 
- 마지막 패킷의 데이터 크기 = 4800 - 1480 - 1480 - 1480 = 360

