Python Syntax
==================================
1. JSON 인코딩  

Python Object (Dictionary, List, Tuple 등) 를 JSON 문자열로 변경하는 것을 JSON Encoding이라 부른다.  JSON 인코딩을 위해서는 json.dumps() 메서드를 써서 Python Object 문자열로
변환하면 된다. json.dumps()로 옵션 없이 인코딩하게 되는 경우 JSON 문자열이 한 줄로 길게 표현된다. "indent" 옵션을 지정하게 되면 JSON 문자열을 깔끔하게 표현할 수 있다.
