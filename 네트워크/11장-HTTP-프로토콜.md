### [HTTP 프로토콜](https://youtu.be/TwsQX1AnWJU?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### 1. 웹을 만들기 위해 사용되는 기술들 
![](https://velog.velcdn.com/images/turtle_hw/post/ac65f6d9-8771-4098-8f94-2fc279750783/image.png)

< 요 세가지는 한 묶음 => 웹 표준>
- `HTML` : 웹 페이지를 채울 내용
- `Javascript` : 웹 페이지에 들어갈 기능
- `CSS` : 웹 페이지를 예쁘게 꾸밀 디자인
> 공통점 = 클라이언트 컴퓨터에서 동작하는 코드들이다
저장은 서버쪽에 되어 있고, 그걸 받아와서 내 컴퓨터에서 실행시키는 것!
이거를 받아오는 프로토콜이 HTTP이다.(웹 표준 데이터를 받아오는 애다)

- ASP/JSP/PHP는 서버쪽에서 동작하는 애들이다


#### 2. HTTP 프로토콜의 특징 
- HyperText Transfer Protocol (하이퍼 텍스트 전송 프로토콜)
- www에서 쓰이는 핵심 프로토콜로 문서의 전송을 위해 쓰이며, 오늘날 거의 모든 웹 애플리케이션에서 사용되고 있다. -> 음성, 화상 등 여러 종류의 데이터를 MIME로 정의하여 전송 가능
- HTTP 특징
    - Request / Response(요청/응답) 동작에 기반하여 서비스 제공
    

#### 3. HTTP 프로토콜의 통신 과정

- v 1.0
![](https://velog.velcdn.com/images/turtle_hw/post/6308947c-e295-49cd-a297-97977031c018/image.png)
- 3Way Handshake 요청 후 HTTP 요청, 응답 하면 바로 연결 종료

- v 1.1
![](https://velog.velcdn.com/images/turtle_hw/post/a96c5c9d-660c-455f-bb0f-dd25758a7f69/image.png)

- 요청 받아갈거 다 받아가면 연결 종료



### [HTTP 요청 프로토콜](https://youtu.be/rxaBwwI_JnI?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

- HTTP Method 설명 중 GET, POST만 사용해야 한다고 하지만 개발자 입장에서 RESTful API 개발시 PUT, DELETE도 사용하는게 원칙임

#### 1. HTTP 요청 
![](https://velog.velcdn.com/images/turtle_hw/post/30798b14-ff44-4b90-821b-94eb285c2ca4/image.png)

#### 2. 프로토콜의 구조 
 ![](https://velog.velcdn.com/images/turtle_hw/post/0cf9e7e5-f5de-4248-8841-f907ef81c3c3/image.png)
- 제일 첫줄인 Request 라인이 가장 중요함
- 요청타입(중요) + 공백 + URI(중요) + 공백 + HTTP 버전 

#### 3. 요청타입 ( GET, POST 중요)
![](https://velog.velcdn.com/images/turtle_hw/post/eec9d5b3-3799-4b10-8c61-0ac92a4601d7/image.png)

- GET 방식은 중요하지 않은 정보를 URI에 같이 보내는 방식임

- POST 방식은 중요한 정보 ID, PW와 같은 정보를 body에 넣어보내는 방식임



### [URL, URI란?](https://youtu.be/2ikhZ_fNP5Y?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

- URI는 Uniform Resource Identifier 의 약자

![](https://velog.velcdn.com/images/turtle_hw/post/b60ce6a3-61d9-48c3-9129-23a1ca317bbe/image.png)

#### URI 구조
- scheme ://host[:port][/path][?query] (scheme 자리엔 7계층 프로토콜 형식지정하면 된다)

### [HTTP 요청 프로토콜 작성 실습](https://youtu.be/XbGJYsxed2w?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

- GET / HTTP/1.1 을 웹사이트에 요청보내면 요청은 다 감(근데 실습 어떻게 해야하는지 앞에 생략이 너무 되있어서 안됨니다)

### [URI 이해를 위한 실습](https://youtu.be/HBojczyd1Ac?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

- API 만들기

### [HTTP 응답 프로토콜](https://youtu.be/kuucNF4Zvbs?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

![](https://velog.velcdn.com/images/turtle_hw/post/4d491cb0-b5bf-4883-8a9e-cca825f977a7/image.png)

- 요청과 똑같음( 요청보다 간단함 )

![](https://velog.velcdn.com/images/turtle_hw/post/3568e6cd-9c26-49db-8cf7-63d27cc3a633/image.png)

#### 응답 프로토콜 구조
- HTTP 버전 + 공백 + 상태코드 + 공백 + 상태문구 
- ( 상태코드와 상태문구는 세트임 코드만 알아두자)
![](https://velog.velcdn.com/images/turtle_hw/post/00a20113-f267-470a-bb33-85e681f5813b/image.png)
- 100, 300번대는 몰라도 된다
- 200번대는 정상적인 통신을 완료했을때임 (정상)
![](https://velog.velcdn.com/images/turtle_hw/post/70e0165e-23a7-4b36-a0bb-8309ea69c844/image.png)

- 400번대는 클라이언트가 잘못한거임 
![](https://velog.velcdn.com/images/turtle_hw/post/5e9034c9-cf20-4697-9a4e-760e301b7760/image.png)

- 500번대는 서버가 잘못한거임
![](https://velog.velcdn.com/images/turtle_hw/post/84738f31-17e0-4064-86af-3176dd39d508/image.png)
- 개발 코드 잘못쳤을때 500번대 자주 나옴

### [HTTP 헤더 포맷](https://youtu.be/mQTGmxendk8?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### 헤더 종류
- 둘다 사용할수 있는 일반 헤더
- 각자 사용할 수 있는 요청 헤더와 응답 헤더 
- 특별한 경우에 사용하는 항목 헤더

#### 일반 헤더
![](https://velog.velcdn.com/images/turtle_hw/post/2d491799-a561-420b-8f3f-511c492e1441/image.png)

#### 요청 헤더
![](https://velog.velcdn.com/images/turtle_hw/post/aadf9c50-b65c-46ac-a704-d561ab6c68cc/image.png)

#### 응답 헤더
![](https://velog.velcdn.com/images/turtle_hw/post/7a13d675-1eef-4a89-85e3-a4c8adbe0bd4/image.png)



### [HTTP 프로토콜 분석 실습](https://youtu.be/dhMrKTwNI8U?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

- burpsuite 활용한 실습 
