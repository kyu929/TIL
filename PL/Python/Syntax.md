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

### 3. super()

서브 클래스에서 슈퍼 클래스의 메소드에 액세스 할 수 있습니다.

```
--------------------example------------------------
#Super Class Rectangle
class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width
    
    def area(self):
        return self.length * self.width
        
    def perimeter(self):
        return 2 * self.length + 2 * self.width

# Sub Class Squre
# Here we declare that the Square class inherits from the Rectangle class
class Squre(Rectangle):
    def __init__(self, length):
        super().__init__(length, length)
```
  
다른 객체 지향 언어와 마찬가지로 하위 클래스에서 슈퍼 클래스의 메서드를 호출 할 수 있습니다. 주요 사용 사례는 상속된 메서드의 기능을 확장하는 것입니다.
example. Sqaure에서 상속하는 Class Cube를 생성하여 .area()의 기능을 확장할 수 있다.
```
--------------------example------------------------
class Square(Rectangle):
    def __init__(self, length):
        super().__init__ (length, length)
        
class Cube(Squre):
    def surface_Area(self):
        face_Area = super().area()
        return face_area *6
        
    def volume(self):
        face_area = super().area()
        return face_Area * self.length
```

### 4. f-string

1. syntax
f-string 문은 두 부분으로 구성됩니다. 하나는 문자 f 또는 F이고 다음 부분은 형식화하려는 문자열 입니다. 문자열은 작은 따옴표, 큰 따옴표 또는 삼중 따옴표로 묶입니다.

```
example
f'string' or F'string' or f''string'' or f'''string'''
```

2. variables
str.format() 메서드를 사용하여 문자열 형식을 지정할 수도 있습니다. f-string으로 더 빠르게 문자열 형식을 지정할 수 있습니다.
변수의 경우 중괄호{} 안에 넣어 표시할 수 있습니다.

```
example
var1 = "variable"
var2 = 123
print(f"Hi {var1} today number {var2}")
```

3. expression
중괄호{} 안에 함수 호출도 가능하다.

```
example
def greet(name):
    return "Hello, " + name


name = "Name"
print(f"{greet(name)}")
```
같은 방식으로 미리 정의 된 메서드를 호출 할 수도 있습니다.

4. dictionaries
f-string 내부에 dictionary key를 사용할 때 서로 다른 따옴표를 사용해야 한다.
```
example
person = {"name": "John", "age": 19}
print(f"{person['name']} is {person['age']} years old.")
```

5. Copy

shallow copy  vs  deep copy


   ### 5. Descriptor in Python
   In general, a descriptor is an object atribute with "binding behavior", one whose attribute access has been overridden by methods in the descriptor protocol: __get__(), 
__set__(), and __delete__(). If any of those methods are defined for an object, it is said to be a descriptor.


   ### 6. self
   The word 'self' is used to represent the instance of a class. By using the "self" keyword we access the attributes and methods of the class in Python.
   
   #### __init__ method
   "__init__" is a reseved method in python classes. It is called as a constructor in object oriented terminology. This method is called when an object is created from a class
and it allows the class to initialize the attributes of the class.
   Example
```
   class Rectangle:
       def __init__(self, length, breadth, unit_cost=0):
           self.length = length
           self.breadth = breadth
           self.unit_cost = unit_cost
       def get_area(self):
           return self.length * self.breadth
       def cacluate_cost(self):
           area = self.get_area()
           return area * self.unit_cost
    # breadth = 120 units, length = 160 units, 1 sq unit cost = Rs 2000
    r = Rectangle(160, 120, 2000)
    print("Area of Rectangle: %s sq units" % (r.get_area()))
 ```
 Output    
 ```
    Area of Rectangle: 19200 sq units
    Cost of rectangular field: Rs.38400000
 ```
