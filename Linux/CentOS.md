CentOS 7.0
=====================
### ● ip 설정
#### 네트워크 설정파일 수정
#### vi /etc/sysconfig/network-scripts/ifcfg-eth0 (ifcfg-eth0의 경우 eth의 뒤에 숫자는 다를 수 있음)

```
네트워크 디바이스 설정

 DEVICE=eth0
 HWADDR=HWADDR
 TYPE= Ethernet
 UUID=UUID-UUID-UUID-UUID
 ONBOOT=yes
 NM_CONTROLLED="yes"
 BOOTPROTO=static
 IPADDR=IPADDR
 NETMASK=255.255.255.0
 GATEWAY=GATEWAY
 DNS1=DNS_ADDR(8.8.8.8)
```
selinux

### ● /usr/local/lib과 /usr/lib의 차이점
  
/usr/local/lib 은 사용자가 직접 설치 (컴파일)한 libs를 의미한다.
/usr/lib 은 배포판에서 제공하는 라이브러리 용이다.

 ● VIM Editor
 ========================
 한 페이지씩 이동 : ctrl + u, ctrl + d (u = up | d = down)
 이전 작업으로 이동 : u
 
### - Apache 자식 프로세서 생성 이유

reference : https://byd0105.tistory.com/24
