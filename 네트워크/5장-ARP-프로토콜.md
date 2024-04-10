### [ARP 프로토콜](https://youtu.be/LDsp-Xb168E?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)
(컴퓨터가 계속해서 사용하는 프로토콜)
- 같은 네트워크 대역에서 통신을 하기 위해 필요한 MAC 주소를 IP주소를 이용해서 알아오는 프로토콜
- 같은 네트워크 대역에서 통신을 한다고 하더라고 데이터를 보내기 위해서는 7계층부터 캡슐화를 통해 데이터를 보내기 때문에 IP주소와 MAC주소가 모두 필요하다. 이 때 IP 주소는 알고 MAC주소는 모르더라도 ARP를 통해 통신이 가능

### ARP 프로토콜의 통신 과정

- a > c로 보내야할때 a에서는 일단 같은 통신망 내에 있는 모든 컴퓨터에 신호를 다 보낸 뒤 일치하는 곳에서 응답이 오게 통신함

### ARP 테이블

- 나와 통신했던 컴퓨터들이다.
- 통신 했던 컴퓨터들의 주소는 ARP 테이블에 남는다

### [ARP 프로토콜 실습](https://youtu.be/-M_S50Ga384?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

- cmd에서 arp -a 를 입력하면 나의 컴퓨터와 통신했던 주소들을 확인해볼 수 있다.
