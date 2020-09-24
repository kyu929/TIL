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
관리자 계정 생성하기  
MongoDB Shell에 접속  
admin 데이터베이스에 접속 -> use admin  
db.createUser()로 사용자 추가 사용자 권한은 https://docs.mongodb.com/manual/reference/built-in-roles/ 에서 확인가능.
   
* MongoDB 원격 접속 설정  
MongoDB 설정 파일에서 접속 허용 아이피 변경  
vi /etc/mongod.conf (CentOS)  
bind_ip=127.0.0.1 -> bind_ip=ip_addr1, ip_addr2 or bind_ip=0.0.0.0 (외부 ip 모두 허용)
