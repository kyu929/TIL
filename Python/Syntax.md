Python Syntax
==================================
### 1. JSON 인코딩  

Python Object (Dictionary, List, Tuple 등) 를 JSON 문자열로 변경하는 것을 JSON Encoding이라 부른다.  JSON 인코딩을 위해서는 json.dumps() 메서드를 써서 Python Object 문자열로
변환하면 된다. json.dumps()로 옵션 없이 인코딩하게 되는 경우 JSON 문자열이 한 줄로 길게 표현된다. "indent" 옵션을 지정하게 되면 JSON 문자열을 깔끔하게 표현할 수 있다.


### 2. 'is' and '==' operators

'is' 연산자는 두 객체의 identity를 비교하는 반면에 '==' 연산자는 두 객체의 값을 비교한다. 'is' 연산자는 연산자 양쪽에 있는 변수가 동일한 객체를 가리키면 True를 반환하고 그렇지 않으면 
False를 반환한다.
'==' 연산자는 두 피연산자의 값이 같을 때, 조건이 True가 된다.
  
example
```
list_1 = ['a', 'b', 'c']
list_2 = list_1
list_3 = list(list_1)
print(list_1)
print(list_2)
print(list_3)
 
print(list_1 == list_2)
print(list_1 == list_3)
 
print(list_1 is list_2)
print(list_1 is list_3)
```
output
```
['a', 'b', 'c']
['a', 'b', 'c']
['a', 'b', 'c']
 
True
True
 
True
False
```
