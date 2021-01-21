# Ubuntu
- ### VMware에서 

-------------------------------------------------------

## 방화벽(UFW)
   
   우분투의 기본적인 방화벽은 UFW입니다. 이는 iptables를 좀더 쉽게 설정할 수 있도록 한 것인데 간단한 방화벽 구성에는 문제가 없지만 수준 높은 방화벽 구성에는 iptables 룰을 직접 사용해야 한다.
   
   - ### UFW 사용법
   
      - #### UFW활성화/비활성화
        UFW는 기본 비활성화 상태이기에 이를 활성화 한다.
        ```
        # sudo ufw enable
        ```
      - #### UFW 비활성화
        ```
        # sudo ufw disable
        ```
      - #### UFW 상태확인
        ```
        # sudo ufw status verbose
        ```        
        
   - ### UFW 기본 룰   
     
     UFW에 설정되어 있는 기본 룰은 다음과 같다.
     
     들어오는 패킷에 대해서는 전부 거부(deny)   
     나가는 패킷에 대해서는 전부 허가(allow) 
      
      - #### 기본 룰 확인
        ```
        # sudo ufw show raw
        ```
      - #### 기본 정책 차단
        ```
        # sudo ufw default deny
        ```
      - #### 기본 정책 허용
        ```
        # sudo ufw default allow
        ```
        
   - ### UFW 기본 룰
     
      - #### UFW 허용
        
        sudo ufw allow <port>/<optional:protocoal>
        
        ```
        ex) SSH 22 port allow (tcp/udp 22번 포트를 모두 허용)
        # sudo ufw allow 22
        
        ex) 22 port tcp allow (ssh의 경우 tcp 22번 포트만 여는게 맞다)
        # sudo ufw allow 22/tcp
        
        ex) 22 port udp allow
        # sudo ufw allow 22/udp
        ```   
        
     - #### UFW 차단   
       
       sudo ufw allow <port>/<optional:protocoal>
       
       ```
       ex) SSH 22 port allow (tcp/udp 22번 포트를 모두 허용)
       # sudo ufw allow 22
       
       ex) 22 port tcp allow (ssh의 경우 tcp 22번 포트만 여는게 맞다)
       # sudo ufw allow 22/tcp
       
       ex) 22 port udp allow
       # sudo ufw allow 22/udp
       ```   
     - #### UFW rule 삭제
       ```
       # sudo ufw delete deny 22/tcp
       ```
       
--------------------------------------------------------------      
      
## Apache
  - ### Apache SSL 적용
    >- #### 인증서(전자서명)   
    >
    >  
    >  인증 기관(CA)에서 발행한 전자서명을 이용하려면 금전과 도메인에 대한 제약이 있다. 여기서는 자가서명인증(openssl 이용)을 하여 SSL을 적용할 것이다.   
    >  자가서명인증을 하면 경고메세지는 뜨나 무료로 사용이 가능하다. (기능적으로 같으나 CA기관이 인증하지 않아 브라우저에서 경고를 출력
    >  
    >- #### 자가서명 인증서 만들기
    >   - #### openssl 설치
    >  ```
    >  # sudo apt-get install openssl
    >  ``` 
    >
    >  - #### CA 인증서 생성 (CA-서버의 개인키 생성)
    >  자가서명이므로 자신이 인증기관이다.
    >  ```
    >  # openssl genrsa -des3 -out server.key 2048
    >  ```
    >
    >  - #### 서버 인증서 발급을 위한 요청 파일인 CSR(Certificate Sinning Request - 인증서 서명 요청) 생성
    >  ```
    >  # openssl req -new -days 365 -key server.key -out server.csr
    >  ```
    >
    >  - #### 개인키 암호 제거 (편의상)
    >  ```
    >  # cp server.key server.key.org
    >  # openssl rsa -in server.key.org -out server.key
    >  ```
    >  
    >  - #### 자가 서명 인증서를 생성
    >  서버 개인키와 CSR을 사용해서 인증서에 서명
    >  ```
    >  # openssl x509 -req -days 365 -in server.csr -sighnkey server.key -out server.crt
    >  ```
    >
    >  - #### 인증서 인코딩 포멧 변경
    >  openssl 이 생성하는 인증서의 인코딩은 발급 시 옵션을 주지 않으면 디폴트가 PEM (base64 encoding)이다. Java 등에서 사용하기 위한 DER 포맷(바이너리)으로 변경은 다음과 같이 수행한다.
    >  ```
    >  # openssl x509 -in ca.crt -out ca.der -outform DER
    >  ```
    >
    >  - #### 인증서 내용 보기
    >  PEM 포맷인 경우
    >  ```
    >  # openssl x509 -in ca.crt -text
    >  ```   
    >
    >  DER 포맷인 경우
    >  ```
    >  # openssl x509 -in ca.der -inform DER -text
    >  ```
    >
    >  (인증서 인코딩 포맷 변경은 수행하지 않았다.)  
    >
    >
    >- #### Apache 적용
    >  - #### Apache의 SSL 모듈 활성화
    >  ```
    >  # sudo a2enmod ssl
    >  ```
    >  
    >  - #### Apache 재시작
    >  ```
    >  # sudo service apache2 restart
    >  ```
    >  
    >  - #### 관리를 위한 SSL 인증서 디렉토리 생성
    >  ```
    >  # sudo mkdir /etc/apache2/ssl
    >  ```
    >  
    >  - #### 인증서 파일 이동
    >  ```
    >  # mv server.* /etc/apache2/ssl
    >  ```
    >  
    >  - #### 보안을 위해 디렉토리와 파일의 소유권 조정
    >  ```
    >  # sudo chown -R root:root /etc/apache2/ssl
    >  ```
    >  
    >  - #### 파일 권한 변경
    >  ```
    >  # sudo chmod 600 /etc/apache2/ssl/*.*
    >  ```
    >  
    >  - #### 디렉토리의 권한 변경
    >  ```
    >  # sudo chmod 700 /etc/apache2/ssl
    >  ```
    >  
    >  - #### VirtualHost(가상호스트) 설정
    >  (default-ssl.conf) 파일을 복사해서 (사용할 도메인명.conf)으로 변경 (default-ssl.conf를 사용해도 무방)
    >  ```
    >  # sudo cp /etc/apache2/sites-avaliable/default-ssl /etc/apache2/sites-available/example.com
    >  ```
    >  
    >  - #### 파일 수정
    >  ```
    >  # sudo vi /etc/apache2/sites-available/example.com
    >  
    >  SSLEngine on
    >  SSLCertificateFile      /etc/apache2/ssl/server.crt
    >  SSLCertificateKeyFiile  /etc/apache2/ssl/server.key
    >  ```
    >  
    >  - #### 사이트 활성화
    >  ```
    >  sudo a2ensite example.com
    >  ```
    >  
    >  - #### Apache 재시작
    >  ```
    >  sudo service apache2 restart
    >  ```
    >  출처 : https://webdir.tistory.com/228 [WEBDIR]
    
<br>

  - ### Apache 다음 내용 
------------------------------------------------------------------    

## Next Parts
