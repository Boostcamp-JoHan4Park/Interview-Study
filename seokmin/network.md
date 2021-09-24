# Network  

## Questions  
* [TCP/IP의 각 계층을 설명해주세요.](#1)  
* [OSI 7계층와 TCP/IP 계층의 차이를 설명해주세요.](#2)  
* [Frame, Packet, Segment, Datagram을 비교해주세요.](#3)  
* [TCP와 UDP의 차이를 설명해주세요.](#4)

## Answers
### #1
### #2
### #3

데이터 자체는 동일하지만 각 레이어를 거치면서 헤더 정보가 추가되면서 이름이 달라집니다.

사용자 - Datagram

TCP - Segment

IP - Packet

DataLink - Frame



### #4

TCP와 UDP 모두 transmission layer에 사용되는 프로토콜입니다.

UDP에 비해 TCP는 handshaking과정을 통해 신뢰성을 높였지만, 느리다는 단점이 있습니다. 이러한 이유로 목적에 따라 TCP는 HTTP, Email 등에, UDP는 스트리밍 서비스 등에서 사용이 되고 있습니다.