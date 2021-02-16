# WSGI(Web Server Gateway Interface)
웹서버와 웹 애플리케이션의 인터페이스를 위한 파이썬 프레임워크이다.

Python에서 Application, 즉 Python Script(Web Application)가 Web Server와 통신하기 위한 Interface이다. 프로토콜 개념으로 이해할 수도 있다.
WSGI는 서버와 앱 양단을 나뉘어져 있다. WSGI Request를 처리하려면 서버에서 환경정보와 콜백함수를 앱에 제공해야 한다. 앱은 그 요청을 처리하고 콜백함수를 통해
서버에 응답합니다.

- ### 방식
```
요청 -> 웹서버 -> WSGI Server(middleware) -> WSGI를 지원하는 웹 어플리케이션(Django, flask 등)
```

- ### WSGI Server(middleware)
웹 서버와 WSGI를 지원하는 웹 어플리케이션 사이에서 동작
+ 환경변수가 바뀌면 타켓URL에 따라서 request의 경로를 지정해줌
+ 같은 프로세스에서 여러 애플리케이션과 프레임워크가 실행
+ XSLT 스타일시트를 적용하는 것과 같이 전처리함   
WSGI Server(middleware)는 mod_wsgi, uwsgi, gunicorn, twisted.web, tornado
