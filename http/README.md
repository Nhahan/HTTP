#### IP(Internet Protocol)

![image](https://user-images.githubusercontent.com/81916648/208331182-cede0663-19ff-4744-b8c4-7a5706c196a2.png)

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

## UDP 특징 (User Datagram Protocol) 사용자 데이터그램 프로토콜

- handshake, 신뢰성, 데이터 전달 보장, 순서보장 다 없지만 빠름
- 즉, IP와 거의 같지만 PORT와 체크섬 정도가 추가

### DNS

- IP 주소는 알기 어렵다. (172.27.84.254...)
- IP 주소는 바뀔 수 있다.
