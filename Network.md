Network 
=================================================================================================================================================================

## OSI 7 Layer (Open Systems Interconnection Reference Model)

- ## HTTP   
   하이퍼 텍스트 전송 프로토콜(HTTP, Hyper Text Transport Protocol) 통신을 사용하면 클라이언트와 서버간에 두 가지 유형의 메시지 (HTTP 요청 및 HTTP 응답)를 전송할 수 있다.  
   클라이언트/브라우저가 요청을 서버로 보내고 서버가 브라우저로 응답을 보낸다. 두 메시지는 공통 포맷을 가지고 있고, HTTP 헤더와 HTTP 본문을 포함한다.  

   - ### HTTP Header  
      HTTP Header는 HTTP 본문 (body) 및 요청/응답에 대한 정보를 포함한다.
      본문에 대한 정보는 본문 컨텐츠 길이 등 본문 컨텐츠와 관련이 있다.  
      요청/응답에 대한 정보는 요청/응답에 대한 일반 정보를 포함한다.(ex. 요청 시간, 요청에 사용된 브라우저 등)   
      헤더의 프로퍼티는 이름-값(Name-Value) 쌍으로 설정되며, 콜론 ':' 으로 구분된다.  
  
   - ### HTTP Header 유형   
      1. General Header
      2. Request / Response Header
      3. Entity Header

>1. 전송되는 HTTP 본문 컨텐츠와 관련없고, 요청 / 응답이 생성된 날짜 및 시간 등과 같은 HTTP 통신에 대한 일반적인 정보가 포함된다. General Header는 HTTP 요청과 응답 메시지에 공통
으로 사용된다.

>2. 서버에 요청하면 request header 가 있고 서버가 클라이언트/브라우저로 응답을 다시 보낼 때 response header가 있다. request header는 요청한 URL, 메소드(GET, POST, HEAD), 요청 생성에
사용 된 브라우저 및 기타 정보와 같은 요청에 대한 정보가 포함된다.  
브라우저라는 용어는 사용자 에이전트(User Agent)라고도 한다. 따라서 페이지에 대한 간단한 요청조차도 사용중인 브라우저 및 운영 체제에 대한 정보를 전송해야 한다.  
response header는 사용자가 특정 페이지 또는 리소스에 대한 요청을 보낸 후 서버에서 브라우저에 의해 수신되며 컨텐츠에 사용 된 인코딩, 서버 시스템에서 응답을 생성하는 데 사용되는 서버 소프트웨어 및 기타 정보를 포함한다.

>3. 실제 메시지 또는 전송중인 HTTP 본문에 대한 정보가 포함된다. 컨텐츠 길이, 컨텐츠 언어, 인코딩, 만료 날짜 및 기타 중요한 정보와 같은 정보.

   - ### HTTP 본문

      실제 가져올 실제 데이터 컨텐츠 / 메시지 본문이 나타난다. 콘텐츠에는 요청한 리소스에 따라 HTML 코드, 이미지, CSS 스타일 시트 또는 JavaScript 파일이 포함될 수 있다.

   - ### GET Method vs POST Method
      * Get은 데이터를 가져와서 보여주기 위함일 때, 데이터 및 서버에 대한 상태 변화가 없을 때
      * Post는 데이터를 새로 입력할 때, 변경할 때,

   - ### HTTP response status codes
      1. Informational responses(100-199)
      2. Successful responses(200-299)
      3. Redirects(300-399)
      4. Client errors(400-499)
      5. Server errors(500-599)
