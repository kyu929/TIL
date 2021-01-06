CentOS 7.0
=====================

----------------------------------------------------------------------------------------
## CentOS 초기설정

- ### ip 설정
#### 네트워크 설정파일 수정

```
$ vi /etc/sysconfig/network-scripts/ifcfg-eth0 (ifcfg-eth0의 경우 eth의 뒤에 숫자는 다를 수 있음)

네트워크 디바이스 설정

 TYPE= Ethernet
 PROXY_METHOD=none
 BROWSER_ONLY=no
 BOOTPROTO=static
 DEFROUTE=yes
 IPV4_FAILURE_FATAL=no
 IPV6INIT=no
 IPV6_AUTOCONF=yes
 IPV6_DEFROUTE=yes
 IPV6_FAILURE_FATAL=no
 IPV6_ADDR_GEN_MODE=stable-privacy
 NAME=ens160
 UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
 DEVICE=ens160 
 ONBOOT=yes
 IPADDR=xxx.xx.xxx.xx(IP_ADDRESS)
 NETMASK=255.255.255.0
 GATEWAY=GATEWAY
 DNS1=DNS_ADDR(8.8.8.8)
 
$ systemctl restart NetworkManager
```

   - ### Update
   ```
   $ yum update
   
   $ sudo yum update (root권한이 아닐 경우)
   ```


selinux

---------------------------------------------

- ### /usr/local/lib과 /usr/lib의 차이점

/usr/local/lib 은 사용자가 직접 설치 (컴파일)한 libs를 의미한다.
/usr/lib 은 배포판에서 제공하는 라이브러리 용이다.

-------------------------------------------------

 - ### VIM Editor

 한 페이지씩 이동 : ctrl + u, ctrl + d (u = up | d = down)
 이전 작업으로 이동 : u
 
-------------------------------------------------
 
- ### Apache 자식 프로세서 생성 이유

reference : https://byd0105.tistory.com/24

------------------------------------------------

- ### Apache

80port 또는 443port가 열려 있음과 동시에 설정이 잘 되어 있어도 서버 접속이 되지 않는다면 방화벽을 한 번 확인하자 방화벽이 동작 중이면 접속이 안 될 수도 있다.

방화벽을 끄던지 방화벽에서 port를 열어준다.

- 방화벽 port열기
```
$ firewall-cmd --permanent --zone=public --add-port=80/tcp
$ firewall-cmd --reload
```
---------------------------------------------------

- ### Command

--------------------------------------------------

- ### What is remirepo

