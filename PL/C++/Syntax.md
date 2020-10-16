C++
======================================
### 1. switch 문 (switch statement)

#### &nbsp; (1) switch 개념

> switch 표현식이 값을 평가하고, 각 case 레이블의 값과 '같은'지 테스트한다. 레이블의 값과 같으면 레이블 뒤의 명령문을 실행한다.
일치하는 레이블이 없으면 default 뒤의 명령문을 실행한다. (존재하는 경우)

#### &nbsp; (2) Switch execution and fall-through

> switch 문의 주의점 중 하나는 switch 표현식의 값과 일치 할 때 실행이 진행되는 방식이다. 값이 일치하는 case 레이블을 만나거나 default case 문이
실행되면 해당 레이블 다음의 첫 번째 명령문에서 실행이 시작되고, 다음과 같은 종료 조건 중 하나가 충족 될 때까지 실행이 계속된다.
>> * ```switch``` 블록의 끝에 도달할 경우
>> * ```return``` 문이 발생할 경우
>> * ```goto``` 문이 발생할 경우
>> * ```break``` 문이 발생할 경우
>> * 뭔가 다른 것이 프로그램의 정상적인 흐름을 방해할 경우 (Ex. exit() 호출, 예외 발생 등)



reference : https://boycoding.tistory.com/186
