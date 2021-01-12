# Ubuntu
- ### VMware에서 

- ### ubuntu 방화벽(UFW) 설정
   
   우분투의 기본적인 방화벽은 UFW입니다. 이는 iptables를 좀더 쉽게 설정할 수 있도록 한 것인데 간단한 방화벽 구성에는 문제가 없지만 수준 높은 방화벽 구성에는 iptables 룰을 직접 사용해야 한다.
   
   - #### UFW 사용법
   
      - #### UFW활성화/비활성화
        UFW는 기본 비활성화 상태이기에 이를 활성화 한다.
        ```
        sudo ufw enable
        ```
      - #### UFW 비활성화
        ```
        sudo ufw disable
        ```
      - #### UFW 상태확인
        ```
        sudo ufw status verbose
        ```
        
