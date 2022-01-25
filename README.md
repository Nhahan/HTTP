# HTTP

<b>HTTP 스터디</b>

- 교재 : HTTP 완벽 가이드
<br>

<b>1장.</b> [HTTP 개관](https://github.com/Nhahan/HTTP/wiki/1%EC%9E%A5.-HTTP-%EA%B0%9C%EA%B4%80)

<b>2장.</b> [URL과 리소스](https://github.com/Nhahan/HTTP/wiki/2%EC%9E%A5.-URL%EA%B3%BC-%EB%A6%AC%EC%86%8C%EC%8A%A4)

<b>3장.</b> [HTTP 메시지](https://github.com/Nhahan/HTTP/wiki/3%EC%9E%A5.-HTTP-%EB%A9%94%EC%8B%9C%EC%A7%80)

<b>4장.</b> [커넥션 관리](https://github.com/Nhahan/HTTP/wiki/4%EC%9E%A5.-TCP-%EC%BB%A4%EB%84%A5%EC%85%98)

<b>5장.</b> [웹 서버](https://github.com/Nhahan/HTTP/wiki/5%EC%9E%A5.-%EC%9B%B9%EC%84%9C%EB%B2%84)

<br><br><br><br><br><br><br><br><br><br>

# 11장. 클라이언트 식별과 쿠키

<br>

## 사용자를 식별하는 방법

<br>

### HTTP 헤더

![image](https://user-images.githubusercontent.com/81916648/150960869-c00a0b1b-d08c-416f-b5ea-69a73e20dae8.png)

<hr>

- From 헤더는 사용자의 이메일 주소를 포함하는데 이상적으로는 각 사용자가 서로 다른 이메일 주소를 가지므로 사용자를 식별할 수 있지만, 악의적으로 이메일을 수집하는 경우가 있으므로 잘 사용하지 않는다.
- User-Agent는 특정 브라우저의 정보를 담고 있는데 사용자를 식별하는데는 큰 도움이 되지 않지만, 사용자마다 이용하고 있는 브라우저의 속성에 맞춰 컨텐츠를 제공하는데 쓰인다.
- Referer 헤더는 사용자가 현재 페이지로 유입하게 한 웹페이지의 URL을 가르키므로 사용자를 식별하는데 도움이 되지 않는다.
- Authorization는 로그인을 한다는 가정하에 사용자를 식별할 수 있다.
- Client-ip는 어느 정도 특정성을 가지지만 변동성이 크므로 쓰기엔 무리가 있다.
- X-Forwarded-For
- Cookie는 사용자를 식별하고 세션을 유지하는 방식 중에서 현재까지 가장 널리 사용하는 방식이다. 쿠키는 앞ㅇ서 설명한 기술들이 가지고 있던 문제점들을 겪지는 않지만 쿠키만으로 모든 것을 할 수 없으므로 앞서 설명한 기술들과 함께 사용하기도 한다.
    - Session Cookie(세션 쿠키)는 브라우저를 닫으면 사라진다.
    - Persistent Cookie(지속 쿠키)는 디스크에 저장되어 컴퓨터를 재시작해도 남아있다. 세션 쿠키와 지속 쿠키의 차이점은 지속 시간 뿐이다.
쿠키는 캐싱과 같이 사용한다면 거의 만능이라고 생각되고, 쿠키에 관련한 위험성을 잘 관리한다면 세션 조작이나 트랜잭션 상의 큰 편리함을 가져올 수 있을 것 같다.
