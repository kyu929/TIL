# CentOS_Error_Solved

- ### bash-4.2$ 현상
   계정 생성 후 변경 작업 후에 나타날 수 있는 현상이다. 오류까진 아니지만 해결 방법을 적어놓겠다.   
   해당 계정 홈 directory[cd ~]에 .bash_profile / .bashrc / .bash_logout file이 없어서 나타나는 현상이다.   
   
   ```
   # 계정생성
   root$ groupadd dba
   root$ useradd -g dba tibero
   
   # tibero 계정접속
   root$ su tibero
   
   # 명령어 창에 계정 이름 대신 bash-4.2가 나타남.
   bash-4.2$
   bash-4.2$ exit
   
   # /etc/skel/ 에서 .bash file들을 복사한다.
   # -rp 옵션을 주어 디렉토리 전체를 복사한다.
   root$ cp -rp /etc/skel /home/tibero
   root$ chown -R tibero.dba /home/tibero (root$ chown -R USER.USERGROUP /home/directory)
   
   # 다시 계정에 접속하면 bash-4.2가 안나타나지만 간혹 계속 나타날 경우
   bash-4.2$ cd /home/tibero/skel
   bash-4.2$ mv .bash_profile .bashrc .bash_logout /home/tibero
   
   #이후 다시 root로 변경 후 해당 계정에 접속하면 bash-4.2가 나타나지 않는다
   ```
