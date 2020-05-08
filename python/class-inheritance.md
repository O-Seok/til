# 클래스 상속 (inheritance)

class는 상속을 받아 부모 class의 속성과 메소드들을 사용 할 수 있다.  

## # 상속

부모 class 를 정의 한다.
```py
class Car:
  """Parent Class"""
  def __init__(self, tp, color):
    self.type = tp
    self.color = color

  def show(self):
    return 'Car Class "Show Method!"'
```


`super()`: 상속 받은 class(부모)의 속성이나 메소드를 호출 할 때 사용한다.


클래스를 선언 하고 **상속받을 class를 인자**로 주어 상속을 받는다. 
```py
class BmwCar(Car):
  """Sub Class"""
  def __init__(self, car_name, tp, color):
    super().__init__(tp, color)
    self.car_name = car_name

  def show_model(self) -> None:
    return "Your Car Name: %s" %self.car_name
```

### **상속받은 class**
```py
# 일반 사용
model1 = BmwCar('520d', 'sedan', 'red')

print(model1.color)     # super
print(model1.type)      # super
print(model1.car_name)  # sub
print(model1.show())    # super
print(model1.show_model()) # sub
print(model1.__dict__)
```
```
red
sedan
520d
Car Class "Show Method!"
Your Car Name: 520d
{'type': 'sedan', 'color': 'red', 'car_name': '520d'}
```

## # 오버라이딩
부모의 메소드 함수와 **똑같은 이름의 메소드를 정의** 하고 **원하는 동작형태로 다시 작성하여 사용** 하는 것을 말한다.  

부모 class
```py
class Car:
  """Parent Class"""
  def __init__(self, tp, color):
    self.type = tp
    self.color = color

  def show(self):
    return 'Car Class "Show Method!"'
```

상속을 받고, 부모의 메소드 show(self)를 재정의 하여 선언한다.

```py
class BenzCar(Car):
  """Sub Class"""
  def __init__(self, car_name, tp, color):
    super().__init__(tp, color)
    self.car_name = car_name

  def show_model(self) -> None:
    return "Your Car Name: %s" %self.car_name

  def show(self):
    print(super().show())
    return 'Car Info : %s %s %s' %(self.car_name, self.type, self.color)
```

비교를 위해 자식이 오버라이딩한 메소드에 원래 부모의 메소드도 호출 하였다.  

```py
model3 = BenzCar('350s', 'sedan', 'silver')
print(model3.show())
```

자식 메소드에서 오버라이딩이 일어난 것을 볼 수 있다.
```
# 부모 show()
Car Class "Show Method!"

# 오버라이딩 show()
Car Info : 350s sedan silver
```

## # 다중상속
상속은 여러번 일어나게 할 수 있다.   
무분별한 다수의 상속은 후에 수정 보완할 때 큰 어려움을 겪을 수 있다.

`mro()`: 상속 관계를 나타내주는 함수

```py
class X:
  pass

class Y:
  pass

class Z:
  pass

class A(X, Y):
  pass

class B(Y, Z):
  pass

class M(B, A, Z):
  pass
```

A의 상속 관계
```py
print(A.mro())
```
```
[<class '__main__.A'>, <class '__main__.X'>, <class '__main__.Y'>, <class 'object'>]
```

M의 상속 관계
```py
print(M.mro())
```
```
[<class '__main__.M'>, <class '__main__.B'>, <class '__main__.A'>, <class '__main__.X'>, <class '__main__.Y'>, <class '__main__.Z'>, <class 'object'>]
```

복잡하다....🤮


