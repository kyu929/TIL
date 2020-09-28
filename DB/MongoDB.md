MongoDB
======================
MongoDB
mongod 서버 시작
mongo shell start
mongo   


* mongodb find 조회

 
collection 전체 조회  
```db.colecction_name.find({})```

ObjectId로 조회  
```db.getCollection('collection_name').find({_id:ObjectId('5bee16exampleexample')})``` (이후 정확한 명칭으로 변경)

특정 값 조회  
```db.getCollection('collection_name').find({"korean":"사이즈"})```   (이후 정확한 명칭으로 변경)
  
조건 여러개로 조회  
```db.getCollection('collection_name').find({"korean":"사이즈", "english":"size"})```  (이후 정확한 명칭으로 변경)

   
* authorization 추가  
vi /etc/mongod.conf
```
security:
    authorization
```
관리자 계정 생성하기  
MongoDB Shell에 접속  
admin 데이터베이스에 접속 -> use admin  
db.createUser()로 사용자 추가 사용자 권한은 https://docs.mongodb.com/manual/reference/built-in-roles/ 에서 확인가능.
```
#example
관리자 계정 및 권한 추가
use admin
db.createUser({user:'username', pwd:'pwd', roles:['userAdminAnyDatabase', 'dbAdminAnyDatabase', 'readWriteAnyDatabase']})

사용자 계정 및 권한 추가
use database
db.createUser({user:'username', pwd:'pwd', roles:['dbAdmin', 'readWrite'})
```   
* MongoDB 원격 접속 설정  
MongoDB 설정 파일에서 접속 허용 아이피 변경  
vi /etc/mongod.conf (CentOS)  
bind_ip=127.0.0.1 -> bind_ip=ip_addr1, ip_addr2 or bind_ip=0.0.0.0 (외부 ip 모두 허용)  
mongod 재실행  
netstat -tnlp로 포트 바인딩 확인
  
* MongoDB Index  
MongoDB에서 Index는 쿼리의 효율적인 실행을 지원한다. 인덱스가 없으면 MongoDB는 쿼리문과 일치하는 문서를 선택하기 위해 컬렉션 스캔, 즉 컬렉션의 모든 문서를 스캔해야합니다.
쿼리에 적합한 인덱스가 있는 경우 MongoDB는 인덱스를 사용하여 검사해야하는 문서 수를 제한할 수 있습니다. 인덱스는 컬렉션 데이터 세트의 작은 부분을 탐색하기 쉬운 형식으로 저장하는
특수 데이터 구조입니다.
  
  
reference : docs.mongodb.com/manual
