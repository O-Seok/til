# 함수 (function)
어떠한 반복적이고 중복되는 프로그래밍을 피할 수 있다.  
하나의 기능을 하는 함수를 만들어야 좋다.  
> ⚠️ 함수 선언 위치  
> 함수를 사용할 위치보다 위에서 선언을 해주고, 선언한 위치보다 아래에서 사용한다.

## # 정의 방법
```py
def 함수명(parameter):
  (실행할 코드)
```

## # 함수 호출
`함수명()`  
`함수(parameter)`

### **간단한 호출**
```py
def hello(word):
  print('Hello ', word)

hello('Python!')
hello(7777)
```
```
Hello  Python!
Hello  7777
```

### **리턴이 있는 함수**
```py
def hello_return(word):
  val = "Hello " + str(word)
  return val

str = hello_return("python!!!!!!!")
print(str)
```
```
Hello python!!!!!!!
```

### **다중리턴**
```py
def func_mul(x):
  y1 = x * 100
  y2 = x * 200
  y3 = x * 300
  return y1, y2, y3

val1, val2, val3 = func_mul(100)
print(type(val1), val2, val3)
```
```
<class 'int'> 20000 30000
```

### **다중리턴 (데이터타입 변환)**
```py
def func_mul2(x):
  y1 = x * 100
  y2 = x * 200
  y3 = x * 300
  return [y1, y2, y3]

lt = func_mul2(100)
print(lt, type(lt))
```
```
[10000, 20000, 30000] <class 'list'>
```

### ***args**
`매개변수가 몇개가 넘어올지 모를 때`   
다양한 매개변수 형태를 받아서 함수의 흐름이 바뀌는 기능을 원할 때  
`리턴 값`은 `튜플` 형태로 나온다.

```py
def args_func(*args):
  print(args)

args_func('kim')
args_func('kim','park')
```
```
('kim',)
('kim', 'park')
```

```py
def args_func2(*args):
  for t in args:
    print(t)

args_func2('kim')
args_func2('kim','park')
```
```
kim
kim
park
```

> ! enumerate()  
> 인덱스와 값을 같이 출력 해준다.
> ```py
> def args_func3(*args):
>   for i, v in enumerate(*args):
>     print(i, v)
>args_func3('kim', 'park')
>```
>
>```
> # 결과값
>0 kim
>1 park
>```
  
    

### ****kwrags**
딕셔너리형태로 인자로 받을 수 있고, 출력을 딕셔너리형태로 반환한다.  

```py
def kwargs_func(**kwargs):
  print(kwargs)

kwargs_func(name1='kim', name2='Park', name3='Lee')
```
```
{'name1': 'kim', 'name2': 'Park', 'name3': 'Lee'}
```

dic에서 items()로 반복문을 사용하여 key와 value를 각각 출력 가능하다.

```py
def kwargs_func2(**kwargs):
  for k, v in kwargs.items():
    print(k, v)

kwargs_func2(name1='kim', name2='Park', name3='Lee')
```
```
name1 kim
name2 Park
name3 Lee

```

### **전체 혼합**
혼합해서 사용 할 때  
arg1, arg2 : 필수인자  
*args, **kwargs : 가상인자

```py
def example_mul(arg1, arg2, *args, **kwargs):
  print(arg1, arg2, args, kwargs)

example_mul(10, 20)
example_mul(10, 20, 'park', 'kim', age1=24, age2=34)
```
```
10 20 () {}
10 20 ('park', 'kim') {'age1': 24, 'age2': 34}
```
---

## # 힌트 함수
인자를 어떤 타입을 받는지, 출력 값은 어떠한 데이터 타입인지 설명해주는 함수  

```py
def func_mul3(x : int) -> list:
  y1 = x * 100
  y2 = x * 200
  y3 = x * 300
  return [y1, y2, y3]

print(func_mul3(5))
```
```
[500, 1000, 1500]
```
---

## # 중첩함수
함수 안의 함수  
참고 : [데코레이터오 클로저](http://schoolofweb.net/blog/posts/%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EB%8D%B0%EC%BD%94%EB%A0%88%EC%9D%B4%ED%84%B0-decorator/)

```py
def nested_func(num):
  def function_in_func(num):
    print('>>>', num)
  print('in function')
  function_in_func(num + 1000)

nested_func(10000)
```
```
in function
>>> 11000
```