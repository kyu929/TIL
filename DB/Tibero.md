# Tibero

  
  - ## What is Tibero Database
    
    ```
    Tibero는 티맥스데이터사(티맥스소프트 관계회사) 에서 제작한 한국산 데이터베이스 관리 시스템(DBMS)이다. SQL 등을 포함,
    오라클의 제품과 거의 동일한 호환성을 제공함에 따라 오라클 데이터데이스의 대안으로도 간주된다.
    
    reference : https://ko.wikipedia.org/wiki/%ED%8B%B0%EB%B2%A0%EB%A1%9C
    ```
  
  - ## Tibero Command
    
    오라클의 제품과 거의 동일한 호환성을 제공함으로 query문의 경우 Oracle의 query문과 거의 동일하다.
  
    - ### Tibero Server connection
      ```
      # tbsql username/password
  
      SQL> conn username/password or conn username/password@SID
      ```
      
    - ### Tibero Table 정보 조회
      
      - #### Table Name 조회
        티베로 테이블명 조회
        ```
        SELECT * FROM ALL_TAB_COMMENTS;
        
        SELECT * FROM ALL_TAB_COMMENTS WHERE TABLE_NAME = 'TABLE_NAME';
        
        (ex) SELECT * FROM ALL_TAB_COMMENTS WHERE TABLE_NAME = 'USERS';
        ```
      - #### Table column Name 조회
        테이블명, 컬럼명, 컬럼 주석 확인 가능
        ```
        SELECT * FROM ALL_COL_COMMENTS WHERE TABLE_NAME = 'TABLE_NAME';
        ```
        
      - #### Table 상세정보 조회
        테이블명, 컬럼명, 데이터타입, 컬럼수정자, 컬럼의 데이터타입 오너, 데이터 길이, NULLABLE, 컬럼ID, 열의 기본값 길이 등 확인 가능
        ```
        SELECT * FROM ALL_TAB_COLUMNS WHERE TABLE_NAME = 'TABLE_NAME';
        ```
        reference : https://domoyosi.tistory.com/6
      
      
  - ## Tibero Server Installation

  - ## Tibero Client Installation

  - ## Oracle Database 용어 정리
    
    - ### SID(System Identifier)
      ```
      데이터베이스를 식별함에 있어 고유한 아이디를 말한다. SID명은 데이터베이스명과 일치해야 하며, DB연동을 위하여
      필요한 naming이다.
      
      reference : https://xxxq.tistory.com/39
      ```
  
  - ## Tibero Apache
  
    Tibero와 Apache 연동을 위해서 oci(Oracle Call Interface)를 사용하여 할 필요가 있다. (추후 검증 후 방법 작성)
  
  - ## Next
  
