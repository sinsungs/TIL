# WebSocket 웹 소켓 

## 웹 소켓 
실시간성을 보장하는 서비스 
게임, 채팅, 실시간 주식 거래 사이트 등등에 사용 

## 웹소켓 vs HTTP 
HTTP에서도 실시간성을 보장하는 기법이 존재한다.
하지만 HTTP는 요청과 응답이라는 구조로 통신이 이루어지므로, 실시간으로 바뀌는 정보에 대해서는 지속적으로 요청을 해야되는 불편함이 있다.
이런 식으로 매번 연결을 맺고 끊는 작업은 꽤나 많은 비용이 드는 작업으로 비효율적이다.

## 웹소켓을 지원하지 않는 환경에서는 ? 
웹소켓은 많은 환경에서 지원하지만 IE , Firefox , Safari 등에서 지원하지 않는 경우도 있다
- 해결 방안 
SockJs
Socket.io

## STOMP
Simple Text Oriented Messaging Protocol
메시지 브로커를 활용하여 쉽게 메세지를 주고 받을 수 있는 프로토콜 
웹소켓 위에 얹어 함께 사용할 수 있는 하위(서브) 프로토콜 

웹소켓만 사용 시 간단한 메세지가 요청 응답 되는데
STOMP 사용 시 간단한 메시지가 커맨드, 헤더, 바디를 만들어서 요청 응답 하게 됨 


## STOMP의 장점 
- 하위 프로토콜 혹은 컨벤션을 따로 정의할 필요 없다
- 연결 주소마다 새로 핸들러를 구현하고 설정해줄 필요가 없다
- Spring Security를 사용할 수 있다 

