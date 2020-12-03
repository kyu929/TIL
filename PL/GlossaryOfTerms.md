GlossaryOfTerms
==================================================
# Interperter vs Compiler

### ● Interpreter
인터프리터(interpreter, 해석기)란 소스코드를 바로 실행하는 컴퓨터 프로그램 또는 환경을 말한다. 소스코드를 목적 코드로 옮기는 컴파일과 대비된다.   
인터프리터는 소스코드를 한줄 한줄 읽어들이면서 실행하는 프로그램이다.   
인터프리터에서는 번역과 실행이 동시에 이루어진다. 고로, 별도의 실행파일이 존재하지 않는다.   
   
인터프리터 언어의 종류
스크립트 언어가 대표적이다.
Javascript, HTML, actionscript, SQL, python, ruby 등

### ● Compile
컴파일(compile)이란 소스코드에서 목적코드로 옮기는 것을 말한다.   
컴파일을 하게 되면 실행가능한 파일(프로그램)이 생성된다. 이러한 프로그램을 목적프로그램이라고도 하고, 컴퓨터 하드웨어(cpu)가 알아 들을 수 있는 기계어로 번역되었다는 의미에서
바이너리 파일이라고도 한다.   
   
컴파일 언어의 종류   
C, C++, JAVA, C# 등

# parameter vs arguments

● ```Parameter``` is variable in the declaration of function.   
   
● ```Argument``` is the actual value of this variable that gets passed to function.

   # Overloading vs Overriding
   
   ### Overloading
   오버로딩은 같은 메소드라도 매개변수만 다르면 얼마든지 정의하고 사용할 수 있다.
   
   특징
   1) 메소드 이름이 같아야 한다.
   2) 리턴형이 같아도 되고 달라도 된다.
   3) 파라미터 개수가 달라야 한다.
   4) 파라미터 개수가 같을 경우, 데이터타입이 달라야 한다.
   
   ### Overriding
   상속 관계에 있는 클래스 간에 같은 이름의 메소드를 정의하는 기술이다.
   만약 자식클래스가 부모클래스에서 선언된 것과 같은 메소드를 가질 때, 메소드 오버라이딩이라고 한다.
   
   특징
   1) 오버라이드 하고자 하는 메소드가 상위 클래스에 존재해야 한다.
   2) 메소드 이름이 같아야 한다.
   3) 메소드 파라미터 개수, 파라미터의 자료형이 같아야 한다.
   4) 메소드 리턴형이 같아야 한다.
   5) 상위 메소드와 동일하거나 내용이 추가되어야 한다.
