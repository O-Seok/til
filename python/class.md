# class

class는 `객체의 구조와 행동을 정의` 한다.   
객체의 class는 초기화를 통해 제어 한다.  
class는 복잡한 문제를 다루기 쉽도록 한다.  

> ✔️ class, 객체(object), 인스턴스(instance)  
> **객체(object)** 는 소프트웨어 세계에 구현할 대상이고, 이를 구현하기 위한 설계도가 **class** 이며, 설계도에 따라 소프트웨어 세계에 구현된 실체가 **인스턴스(instance)** 이다. 보통 인스턴스를 객체라고도 부른다.

## # class 정의
`class` 키워드를 사용하여 새로운 class를 선언한다.  
파이썬 대부분이 네이밍컨벤션이 단어와 단어 사이에 `_`를 넣는다면 **class의 네이명 컨벤션은 CamelCase**로 한다.  

```py
class ClassInfo:
  def __init__(self):
    print("초기화")
```

### **생성자와 인스턴스**
`인스턴스`: 변수에 class를 할당 하는 것. 객체가 메모리상에 할당이 되는 것
`생성자`: 변수에 class를 할당할 때 쓰인다. 인스턴스화 할 때 사용하는 것

```py
class ClassInfo:
  def __init__(self):
    print("초기화")

cInfo = ClassInfo()
```
cInfo : 변수  
ClassInfo() : 생성자

  
### **초기화자**
객체(인스턴스)가 생성되고 나면 `__init__` 메소드를 호출하여 객체에서 사용할 초기값들을 초기화 한다.  

객체에 초기화된 변수들, `인스턴스 변수`들을 호출 할 수 있다.

```py
class UserInfo:

  def __init__(self, name, height, weight):
    self.name = name
    self.height = height
    self.weight = weight

user1 = UserInfo("Kim", 190, 80)

print(user1.name)
print(user1.height)
print(user1.weight)
```
```
Kim
190
80
```

### **self**
`self`를 인자로 받는 메소드(함수)는 인스턴스화 되었을 때 사용할 수 있는 `인스턴스 함수`이다.  
  
class함수: class 안의 함수 중 인자를 self로 받지 않는 함수  
인스턴스 함수: class 안의 함수 중 인자를 self로 받는 함수

```py
class SelfTest:
  def function1():
    print('function1 called!')
  def function2(self):
    print('function2 called!')
```

class 함수는 인스턴스화 시키지 않고도 외부에서 접근 할 수 있다. 

```py
SelfTest.function1()
```
```
function1 called!
```

self를 인자로 받는 인스턴스 함수는 인스턴스화 없이 사용이 불가능하다.  
```py
SelfTest.function2()
```
```
Traceback (most recent call last):
  File "/Users/claudjung/Documents/dev/python_basic/section07-1.py", line 91, in <module>
    SelfTest.function2()
TypeError: function2() missing 1 required positional argument: 'self'
터미널 프로세스가 종료 코드 1(으)로 종료되었습니다.
```
인스턴스화 시켜서 해야 실행 가능하다.
```py
test.function2()
```
```
function2 called!
```

### **네임 스페이스**
인스턴스가 가지고 있는 자기 자신의 저장공간  
인스턴스들의 네임스페이스들은 각자 독립적이다.  
`__dict__`: 네임스페이스를 알수 있는 함수

```py
class WareHouse:
  # 클래스 변수
  stock_num = 0
  def __init__(self, name):
    self.name = name
    WareHouse.stock_num += 1
  def __del__(self):
    WareHouse.stock_num -= 1

user1 = WareHouse('Kim')
user2 = WareHouse('Pard')
user3 = WareHouse('Lee')
```
각 인스턴스들의 네임 스페이스를 출력 해보면

```py
print(user1.__dict__)
print(user2.__dict__)
print(user3.__dict__)
```
```
{'name': 'Kim'}
{'name': 'Pard'}
{'name': 'Lee'}
```

`class 변수`: 직접 사용 가능, 객체 보다 먼저 생성, 공유 가능하다.  

이때, 인스턴스들이 가지고 있지 않은 인스턴스 변수 외의 class 변수 값을 호출 할 수도 있다.  

class변수인 stock_num은 user1, user2, user3 이 인스턴스화 되면서 각자의 초기화 함수를 통해 값이 3번 변하였다.  

```py
print(user1.stock_num)
print(user2.stock_num)
print(user3.stock_num)
```
```
3
3
3
```
인스턴스에 존재하지 않는 변수를 호출하면 **인스턴스 네임 스페이스에서 찾고, 없으면 마지막으로 클래스 네임스페이스**에서 찾아 호출한다.  

  

### **인스턴스 삭제**
```py
del (인스턴스)
```








