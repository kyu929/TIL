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

방화벽을 끄던지 방화벽에서 port를 열어준다.

- 방화벽 port 추가 및 서비스 추가
```
# 80 포트 추가
$ firewall-cmd --permanent --zone=public --add-port=80/tcp

# http 서비스 추가
$ firewall-cmd --reload
$ systemctl restart firewalld

# 방화벽 설정 목록
$ firewall-cmd --list-all
```
---------------------------------------------------

- ### Command

--------------------------------------------------

- ### What is remirepo

--------------------------------------------------

- ### yum

    - #### 설치 list 확인
    ```
    yum list installed
    ```
    ```
    분할 검색
    터미널 하단에 more라고 보여지고 키입력 대기상태가 된다.
    스페이스바를 누르면 페이지 단위로, 엔터를 누르면 한줄씩 패키지를 확인을 할 수 있다.
    
    
    yum list installed | more
    ```
    ```
    특정 키워드 검색
    grep 파라미터로 입력한 검색어가 포함된, 패키지 목록을 보여준다.
    yum list installed | grep 검색어입력
    ```
    
    ```
    more, grep은 linux 기본 명령어이다. 검색시에 상황에 맞게 어디서나 사용하면 된다.
    ```   
