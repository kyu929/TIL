# MySQL
 
- ### root 계정 비밀번호 확인
  ```
  # cat /var/log/mysql.log | grep 'temporary password'

  or

  # cat /var/log/mysqld.log | grep 'temporary password'

  로그인 후 패스워드 변경 필요 ( 패스워드 변경 후 정상적으로 사용가능)

  mysql> ALTER USER 'root'@'localhost' IDENTIFIED BY 'password'
  (password의 경우 대문자, 소문자, 숫자, 특수문자를 포함 길이가 8자 이상이여야 한다.)
  ```

- ### MySQL 접속
  ```
  # mysql -u root -p
  Enter passwor:
  ```

- ### CREATE DATABASE
  ```
  CREATE {DATABASE | SCHEMA} [IF NOT EXIST] db_name [create_option] . . .
  
  mysql> CREATE DATABASE db_name 
  ```

스토리지 엔진
