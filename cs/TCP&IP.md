# TCP/IP 프로토콜

## TCP/IP 프로토콜이란?

**인터넷에서 데이터를 전송 시 사용되는 일련의 통신 규약**

- TCP/IP 모델은 데이터 통신을 위한 4계층으로 구성되어 있으며, 위 계층들은 각각의 고유한 역할을 가진다.

<br />

## TCP/IP 4계층

### 1. 응용 계층 (Application Layer)

- 사용자가 네트워크에 접근할 수 있게 해주는 계층
- HTTP, FTP, SMTP와 같은 프로토콜이 해당 계층에 속한다.
- 사용자의 요청을 받아 다른 계층으로 전달하는 역할을 한다.

### 2. 전송 계층 (Transport Layer)

- 데이터 전송을 담당하는 계층
- TCP/UDP 프로토콜이 해당 계층에 속한다.
- TCP는 신뢰성 있는 데이터전송을 보장하지만 UDP는 빠른 전송을 목적으로하며, 신뢰성이 낮아진다.

### 3. 인터넷 계층 (Internet Layer)

- 데이터 패킷이 목적지까지 올바르게 도달하도록 경로를 설정하는 역할을 하는 계층
- IP 프로토콜이 이 계층에 속하며, IP 주소를 통해 데이터 패킷을 전송한다.

### 4. 링크 계층 (Link Layer)

- 물리적 네트워크 장비간의 데이터 전송을 담당하는 계층
- 해당 계층은 네트워크 카드와 같은 하드웨어 주소를 통해 데이터를 전송한다.