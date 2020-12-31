Letter S
==========

### ● SAML(Security Assertion Markup Language)
```
인증 정보 제공자(identity provider)와 서비스 제공자(service provider) 간의 인증 및 인가 데이터를 교환하기 위한 XML 기반의 개방형 표준
데이터 포맷이다. 보안 어서션 마크업 언어, 보안 추가 마크업 언어라고도 한다. SAML이 기술하는 가장 중요한 요구사항은 웹 브라우저 통합 인증
(SSO)이다.

---SAML과 OAUTH의 차이---
OAUTH는 구글과 트위터에서 공동으로 개발한 SMAL보다 다소 새로운 표준이다. OAUTH는 모바일 플랫폼에서 SAML의 결함을 보완하기 위해 개발됐으
며, XML이 아닌 JSON을 기반으로 한다. 모바일 지원 외에 이 둘의 차이점은 SAML 표준은 공급자가 인증 및 권한 부여 서비스를 제공할 수 있는 
방법을 정의한다. 오쓰는 권한 부여만 처리한다. OpneID Connect는 2014년에 개발된 더욱 새로운 표준으로 인증 서비스를 제공하며 오쓰 위에 놓
이게 된다.
 또 다른 주요 차이점은 사용 사례다. SAML은 이론적으로 개방형 인터넷에 사용하도록 설계됐지만, 실제로는 SSO를 위해 엔터프라이즈 네트워크
내에서 배포된다. 반면 OAUTH는 Google과 Twitter에서 인터넷 규모로 설계됐다.
reference : http://www.itworld.co.kr/news/108736
```

### ● Session
```
웹 사이트의 여러 페이지에 걸쳐 사용되는 사용자 정보를 저장하는 방법을 의미합니다. 사용자가 브라우저를 닫아 서버와의 연결을 끝내는 시점까지
를 세션이라고 합니다.
쿠키는 클라이언트 측의 컴퓨터에 모든 데이터를 저장합니다. 하지만 세션은 서비스가 돌아가는 서버 측에 데이터를 저장하고, 세션의 키값
만을 클라이언트 측에 남겨둡니다. 브라우저는 필요할 때마다 이 키값을 이용하여 서버에 저장된 데이터를 사용하게 됩니다.
세선은 보안에 취약한 쿠키를 보완해주는 역할을 하고 있습니다.
```

### ● Servlet(Java Servlet)
```
웹프로그래밍에서 클라이언트의 요청을 처리하고 그 결과를 다시 클라이언트에게 전송하는 Servlet 클래스의 구현 규칙을 지킨 자바 프로그래밍 
기술
자바를 사용하여 웹페이지를 동적으로 생성하는 서버측 프로그램 혹은 그 사양을 말하며, 흔히 '서블릿'이라 불린다. 자바 서블릿은 웹 서버의 성능
을 향상하기 위해 사용되는 자바 클래스의 일종이다. 서블릿은 JSP와 비슷한 점이 있지만, JSP가 HTML 문서 안에 Java코드를 포함하고 있는 반면, 
서블릿은 자바 코드 안에 HTML을 포함하고 있다는 차이점이 있다.
```

### ● Singleton Pattern
```
소프트웨어 디자인 패턴에서 싱글턴 패턴을 따르는 클래스는, 생성자가 여러 차례 호출되더라도 실제로 생성되는 객체는 하나이고 최초 생성 이후에
호출된 생성자는 최초의 생성자가 생성한 객체를 리턴한다. 이와 같은 디자인 유형을 싱글턴 패턴이라고 한다. 주로 공통된 객체를 여러개 생성해서
사용하는 DBCP(DataBase Connection Pool)와 같은 상황에서 많이 사용된다.
```

### ● SESSION
```
HTTP 세션은 해당 서버에 접근한 클라이언트를 식별하는 방법입니다. 세션은 클라이언트를 식별하기 위해 세션 ID라는 것을 사용합니다. 인증된 
클라이언트에게만 발급되는 열쇠이다. 브라우저가 세션 ID를 가지고 있지 않은 상태에서 서버에 HTTP 요청을 보내면, 서버는 세션 ID를 새로 생성하고,
이 세션 ID를 쿠키에 담아 응답합니다. 브라우저는 쿠키로 전송된 세션 ID를 저장하고, 저장된 세션 ID 쿠키를 담아 HTTP를 요청하기 시작합니다.
세션은 클라이언트의 요청에 담긴 세션 ID를 확인하고 인증된 브라우저일 경우 응답해 줍니다.
  
모든 정보들을 클라이언트에 저장하는 쿠키와 달리, 세션 방식은 서버에 저장해 둡니다. 대신 서버에 저장되어 있는 정보에 접근할 수 있는지 확인하는
세션 ID를 클라이언트에 발급해 줄 뿐이다. 클라이언트는 열쇠만 가지고 있다가 정보가 필요할 때 가지고 있던 열쇠를 이용해 서버에 저장된 정보에 접근하는
방식이다. 
  
세션의 특징
 ● 따로 용량의 제한이 없다. (서버의 능력에 따라 달라진다)
 ● 서버에 세션 객체를 생성하고 클라이언트마다 고유한 세션 ID를 부여한다.
 ● 쿠키를 사용하여 세션 ID 값을 클라이언트에 전송한다.
 ● 웹 브라우저가 종료되면 세션 쿠키를 삭제한다.
```

### ● Suspense
```
Suspense lets your components "wait" for something before they can render. In this example, two components wait for an asynchronous
API call to fetch some data
```

- ### Symbolic link
```
Apache Config 중 
<Directory />
    Options FollowSymLinks
    Require all granted
</Directory>
에서 FollowSymLinks 검색 도중 SymLinks가 무엇인지 궁금하여 찾아 보게됨.

In computing, a symbolic link(also symlink or soft link) is a term for any file that contains a reference to another file or directory
in the form of an absolute or relative path and that affects pathname resolution.

```
