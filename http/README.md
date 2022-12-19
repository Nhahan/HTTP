
# IP(Internet Protocol)

![image](https://user-images.githubusercontent.com/81916648/208331182-cede0663-19ff-4744-b8c4-7a5706c196a2.png)

<br>

### IP의 한계

- 비연결성
  - 패킷을 받을 대상이 없거나 서비스 불능 상태여도 패킷 전송
- 비신뢰성
  - 중간에 패킷이 사라지면?
  - 패킷이 순서대로 안오면?
- 프로그램 구분
  - 같은 IP를 사용하는 서버에서 통신하는 애플리케이션이 둘 이상이면?
- 패킷 전달 순서 문제 발생
  - 패킷이 일정 용량을 초과하면 (약 1500bytes) 쪼개져서 노드를 타게 되는데 이 때 다른 노드를 타게 되면 두 번째 패킷이 첫 번째 패킷보다 먼저 도착할 수 있다.
  
![image](https://user-images.githubusercontent.com/81916648/208330994-bacbc83b-b4e5-473c-ba24-d5c32e213e18.png)
  
<br><br>

### 이러한 IP의 한계를 해결해주는게 TCP, UDP

## TCP 특징 (Transmission Control Protocol) 전송 제어 프로토콜

- 연결지향: TCP 3 way handshake
- 데이터 전달 보증
- 순서 보장
- 대부분 TCP 사용

![image](https://user-images.githubusercontent.com/81916648/208333750-a8163311-93f0-4ec1-8254-a82a8a0ce568.png)

클라이언트가 SYN(접속요청)을 보내면 서버가 ACK(요청수락)을 하고 SYN을 보내면 클라가 ACK를 보낸다.

클라: 접속요쳥할게
서버: ㅇㅋ. 나도 할게
클라: ㅇㅋ (요즘은 최적화가 되어서 이 때 데이터도 같이 전송함)

![image](https://user-images.githubusercontent.com/81916648/208334149-f963f844-3220-48a8-bd69-4cc0c44170aa.png)

단순 (IP)Internet Protocol과 다르게 TCP는 여러가지 정보를 추가적으로 패킷에 담고 있다. 그렇기 때문에 데이터나 순서, 신뢰성들을 보장할 수 있는 것이다.

<br><br>

### UDP 특징 (User Datagram Protocol) 사용자 데이터그램 프로토콜

- handshake, 신뢰성, 데이터 전달 보장, 순서보장 다 없지만 빠름
- 즉, IP와 거의 같지만 PORT와 체크섬 정도가 추가

## DNS

- IP 주소는 알기 어렵다. (172.27.84.254...)
- IP 주소는 바뀔 수 있다.

![image](https://user-images.githubusercontent.com/81916648/208335597-45579399-c213-4ff3-b482-41d839a0a820.png)

<br><br><br>

# HTTP (HyperText Transfer Protocol)

- HTTP 1.1: 현대 HTTP의 기본
- HTTP2: 1.1의 개선버전
- HTTP3: UDP로 성능 개선

## HTTP 특징

그 전에 Stateless와 Stateful에 대해서 알아야한다.
Stateless는 상태유지를 하지 않기 때문에 서버를 수평적 확장하기 좋다.
Stateful은 확장이 힘들기 때문에 되도록 Stateless로 설계를 해야한다. 단, Stateless는 상태가 없어 정보를 알기 위해 데이터량이 커진다는 단점이 있다.

### 시작라인

Request
종류: GET, POST, PUT, DELETE... 

```
GET /search?query=검색어&lang=ko HTTP/1.1
HOST: www.naver.com
```

<hr>

Response

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Content=Length: 1234

<html>
  <body>...</body>
</html>
```

- HTTP Header: HTTP 전송에 필요한 모든 부가 정보
- HTTP Body: 실제 전송할 데이터(HTML 문서, 이미지, 영상 등등)
