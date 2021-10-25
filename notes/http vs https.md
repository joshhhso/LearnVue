## [10.25] Chekt Assignment

**How does HTTPS works?**

- HTTP (Hyper Text Transfer Protocol)
  - 개념
    - 서버 / 클라이언트 모델을 따라 데이터를 주고 받기 위한 프로토콜
    - 인터넷에서 하이퍼텍스트를 교환하기 위한 통신 규약
    - 모든 HTTP 서버는 80번 포트를 사용한다.
  - 구조
    - [애플리에키션 레벨](https://www.ibm.com/docs/ko/aix/7.1?topic=protocols-internet-application-level)의 프로토콜로 TCP/IP 위에서 작동
      - **TCP/IP 위에서 작동**
      - **Stateless 프로토콜이며 Method, Path, Version, Header, Body로 구성**
  - 문제점
    - 암호화 되지 않은 평문 데이터를 전송하는 프로토콜
    - HTTP로 비밀번호를 주고 받으면 3자가 정보를 조회 가능



- HTTPS (Hyper Text Transfer Protocol Secure)

  - 개념

    - HTTP에 데이터 암호화가 추가된 프로토콜
    - 443포트를 사용

  - TLS [ 따로 정리하면 링크걸기 ]

    - 다양한 종류의 보안 통신을 하기 위한 프로토콜
    - TLS 위에 프로토콜을 얹어 보안된 HTTP 통신이 HTTPS
    - SSL (Secure Sockets Layer)에 기반한 기술

  - **공개키 / 개인키 암호화 방식**

    ![image-20211025172708824](/Users/josh/Library/Application Support/typora-user-images/image-20211025172708824.png)

    - **HTTPS는 TLS (SSL 기반) 프로토콜을 사용하여 공개키/개인키 기반으로 암호화**

    - 서버는 클라이언트가 요청을 보낼 때, 암호화를 위해 공개키 생성 (handshake!)

      - 공개키는 인증된 기관(Certificate Authority)에 공개키를 전송해서 인증서를 발급받는다.

        1. A기업은 HTTP 기반의 애플리케이션에 HTTPS를 적용

        2. CA 기업에 돈을 지불, 공개키를 저장하는 인증서의 발급 요청

        3. CA 기업이 이름, 서버의 공개키, 정보 등을 기반으로 인증서 생성

        4. CA 기업의 개인키로 암호화하여 A기업에게 개인키를 제공

        5. A기업은 클라이언트에게 암호화된 인증서 제공

        6. 브라우저는 CA기업의 공개키를 미리 다운, 암호화된 인증서를 복호화

        7. 암호화된 인증서 복호화하여 얻은 A기업의 공개키로 데이터 암호화 

           ![image-20211025181116536](/Users/josh/Library/Application Support/typora-user-images/image-20211025181116536.png)

## TIL

- Linux 명령어들
- **OSI 7계층**
  - 
- MAC - IP - TCP - HTTP & HTTPS
  - **[MAC](https://namu.wiki/w/MAC#s-6) (Media Access Control Address) 주소**
    - MAC은 OSI 모델에서 데이터 링크 계층의 하위계층에 해당한다.
    - MAC 주소는 컴퓨터 내부의 [네트워크 카드](https://namu.wiki/w/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%20%EC%B9%B4%EB%93%9C)에 할당된 고유의 주소이다.
      - 해당 주소는 한정되어있어 기관에 의해 판매된다.
      - 변경 불가능하다.
    - MAC 주소와 IP 주소
      - IP 통신은 MAC 주소에 의존해서 통신한다.
      - 해당 통신은 ARP(Address Resolution Protocol)이라는 프로토콜 사용
      - ARP는 수신지의 IP주소를 바탕으로 MAC주소를 조사한다.
  - **IP (Internet Protocol)**

