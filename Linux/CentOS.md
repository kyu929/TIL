CentOS
=====================
* ip 설정
네트워크 설정파일 수정 
vi /etc/sysconfig/network-scripts/ifcfg-eth0

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
```
