# 에러 & 예외 처리
우리는 여러가지 이유로 에러를 발생시킨다.   
문법적인 에러가 없지만, 코드 실행(런타임) 프로세스에서 발생하는 예외 처리도 중요하다.  

## # 에러 종류

### **syntaxError**
잘못된 문법
```py
if True
  pass
```
```
    if True
          ^
SyntaxError: invalid syntax
```

### **NameError**
참조변수가 없을 때
```py
a = 10
b = 15
print(c)
```
```
NameError: name 'c' is not defined
```

### **ZeroDivisionError**
0 나누기 에러
```py
print(10 / 0)
```
```
ZeroDivisionError: division by zero
```

### **IndexError**
인덱스 범위 오버
```py
x = [10, 20, 30]
print(x[3])
```
```
IndexError: list index out of range
```

### **keyError**
```py
dic = {'name': 'Kim', 'Age': 33, 'City': 'Seoul'}
print(dic['hobby'])
```
```
KeyError: 'hobby'
```

### **AttributeError**
모듈, 클래스에 있는 잘못된 속성 사용시
```py
import time
print(time.month())
```
```
AttributeError: module 'time' has no attribute 'month'
```

### **ValueError**
참조 값이 없을 때 발생
```py
x = [1, 5, 9]
x.remove(10)
x.imdex(10)
```
```
ValueError: list.remove(x): x not in list
```

### **FileNotFoundError**
외부 파일 처리할 때 주로 발생
```py
f = open('text.txt','r')
```
```
FileNotFoundError: [Errno 2] No such file or directory: 'text.txt'
```

### **typeError**
```py
x = [1, 2]
y = (1, 2)
z = 'test'
print(x + y)
```
```
TypeError: can only concatenate list (not "tuple") to list
```

## # 예외 처리 기본

> ✔️ **EAFP** 코딩 스타일  
> 항상 예외가 발생하지 않을 것으로 가정하고 먼저 코딩  
> 그 후 런타임 예외 발생 시, 예외 처리 코딩 권장

`try`: 에러가 발생할 가능성이 있는 코드 실행  
`except`: 에러명1  
`except`: 에러명2  
`else`: 에러가 발생하지 않았을 경우 실행  
`finally`: 항상 실행

### **어떤 에러가 발생할 지 알고 있다면, except (에러종류):** 로 작성한다.

```py

name = ['Kim', 'Lee', 'Park']

try:
  z = 'Cho'
  x = name.index(z)
  print('{} Found it! in name'.format(z, x+1))
except ValueError:
  print('Not found it ! - Occurred ValueError')
else:
  print('OK! else')
```
```
Not found it ! - Occurred ValueError
```

### **에러가 발생하지 않는다면 else 구문이 실행된다.**
```py
name = ['Kim', 'Lee', 'Park']

try:
  z = 'Kim'
  x = name.index(z)
  print('{} Found it! in name'.format(z, x+1))
except ValueError:
  print('Not found it ! - Occurred ValueError')
else:
  print('OK! else')
```
```
Kim Found it! in name
OK! else
```

### **어떤 에러가 발생할 지 모를 때는, except: 혹은 except exception: 으로 작성한다.**
```py
try:
  z = 'Cho'
  x = name.index(z)
  print('{} Found it! in name'.format(z, x+1))
except :
  print('Not found it ! - Occurred Error')
else:
  print('OK! else')
```
```
Not found it ! - Occurred Error
```

### **finally는 에러가 발생하든 발생하지 않든 간에 실행된다.**
```py
try:
  # z = 'Kim'
  z = 'Cho'
  x = name.index(z)
  print('{} Found it! in name'.format(z, x+1))
except :
  print('Not found it ! - Occurred Error')
else:
  print('OK! else')
finally:
  print('finally OK!')
```
```
Not found it ! - Occurred Error
finally OK!
```

에러가 나더라도 무조건 실행시켜야 하는 경우가 있다면, finally을 맨 위에 배치해서 예외처리를 해준다.
```py
try:
  print('Try')
finally:
  print('OK Finally!!!!!')
```

### **계층적으로 에러를 잡을 수도 있다.**
단, `except:`, `except: exception`은 어떠한 에러든 잡기 때문에 맨 아래에 배치한다.

```py
try:
  z = 'Kim'
  # z = 'Cho'
  x = name.index(z)
  print('{} Found it! in name'.format(z, x+1))
except ValueError:
  print('Not found it ! - Occurred Error')
except IndexError:
  print('Not found it ! - Occurred Error')
except Exception:
  print('Not found it ! - Occurred Error')
else:
  print('OK! else')
finally:
  print('finally OK!')
```

### **예외 직접 발생**
`raise` 로 예외를 직접 발생 시킬 수 있다.

```py
try:
  a = '333'
  if a == 'Kim':
    print('ok 허가!')
  else:
    raise ValueError
except ValueError:
  print('문제 발생 !')
except Exception as f:
  print(f)
else:
  print('OK !')
```