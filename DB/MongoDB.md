MongoDB  
======================  

## MongoDB 서버 시작
1. mongod (mongodb 서버 실행)
2. mongo (mongo shell 실행)   


## mongodb find 조회

 
>collection 전체 조회  
>```db.colecction_name.find({})```
>
>ObjectId로 조회  
>```db.getCollection('collection_name').find({_id:ObjectId('5bee16exampleexample')})``` (이후 정확한 명칭으로 변경)
>
>특정 값 조회  
>```db.getCollection('collection_name').find({"korean":"사이즈"})```   (이후 정확한 명칭으로 변경)
>  
>조건 여러개로 조회  
>```db.getCollection('collection_name').find({"korean":"사이즈", "english":"size"})```  (이후 정확한 명칭으로 변경)
>
>Json Data안에 Data 죄회
>db.collection.find({"data.exp":{}})

   
## authorization 추가  
vi /etc/mongod.conf
```
security:
    authorization
```
  
## 관리자 계정 생성하기  
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
db.createUser({user:'username', pwd:'pwd', roles:['dbAdmin', 'readWrite']})
```  
## MongoDB Collection 수정  
```
db.collection.update(
  <query>,
  <update>
)

#example

db.test.update(
  {'sid': 's0'},
  {'sid': 's0000', 'score': 95}
);  

'sid'가 s0인 document를 찾아서, 'sid' 를 s0000으로 변경, 'score' field값을 95로 수정하라는 의미이다. 이때 기본적인 update 연
산은 해당 문서를 교체하는 것을 의미한다. 즉, 기존의 문서가 지워지고 <update> 매개변수에 작성한 문서가 대체됨을 나타낸다.

특정필드만 변경( $set)

#example
db.test.update(
  {'sid':'s1'},
  { $set : { 'socre': 100 } }
);

특정필드 제거( $unset )
db.test.update(
  {'sid': 's8'},
  { $unset: { 'score': 80 } }
);
```

## MongoDB 원격 접속 설정  
MongoDB 설정 파일에서 접속 허용 아이피 변경  
vi /etc/mongod.conf (CentOS)  
bind_ip=127.0.0.1 -> bind_ip=ip_addr1, ip_addr2 or bind_ip=0.0.0.0 (외부 ip 모두 허용)  
mongod 재실행  
netstat -tnlp로 포트 바인딩 확인
  
## MongoDB Index  
MongoDB에서 Index는 쿼리의 효율적인 실행을 지원한다. 인덱스가 없으면 MongoDB는 쿼리문과 일치하는 문서를 선택하기 위해 컬렉션 스캔, 즉 컬렉션의 모든 문서를 스캔해야합니다.
쿼리에 적합한 인덱스가 있는 경우 MongoDB는 인덱스를 사용하여 검사해야하는 문서 수를 제한할 수 있습니다. 인덱스는 컬렉션 데이터 세트의 작은 부분을 탐색하기 쉬운 형식으로 저장하는
특수 데이터 구조입니다.
  
  
reference : docs.mongodb.com/manual

## MongoDB Insert
db.collection.insert()
```
#example
db.collection.insert({"key":"value", "key":{"key":"value", "key":["1","2"]}});
```

## MongoDB Update
db.collection.update()
update시 $set을 쓰면 document 전체가 변경되지 않고 $set 부분만 변경 가능하다.
```
#example
> db.clients.insert( {"_id":123, "lookup_key":123, "data":{"Hello":"Hi", "Bye":"GoodBye"}, "data2":"Good Morning", "data3":"Good Afternoon"} )
{
    "_id" : 123,
    "lookup_key" : 123,
    "data" : {
                 "Hello" : "Hi",
                 "Bye" : "GoodBye",
    },
    "data2" : "Good Morning",
    "data3" : "Good Afternoon"
}
WriteResult({ "nInserted" : 1 })

> db.collection.update({"_id" : 123}, { $set : { "data.Hello" : "Bye", "data2" : Bye Bye" } } )
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModifed" : 1 })

> db.collection.find().pretty()

{
    "_id" : 123,
    "lookup_key" : 123,
    "data" : {
                 "Hello" : "Bye",
                 "Bye" : "GoodBye",
    },
    "data2" : "Bye Bye",
    "data3" : "Good Afternoon"
}
```
