# 람다식 (lambda)
한마디로 간결! 간단! 깔끔!  
메모리 절약, 가독성 향상, 코드 간결  
함수: 객체 생성 -> 리소스(메모리) 할당  
람다: 즉시 실행(heap 초기화) -> 메모리 초기화

### **일반적 함수**
```py
def mul_10(num: int) -> int:
  return num * 10

var_func = mul_10
print(var_func)
print(type(var_func))

print(var_func(10))
```
```
<class 'function'>
100
```

## # 람다식
```py
# x는 인자를 의미 한다.
lamda_mul_10 = lambda x: x * 10

print('>>>', lamda_mul_10(10))
```
```
>>> 100
```

### **람다식을 인자로 받을 수도, 리턴 값으로 줄 수도 있다.**
```py
def func_final(x, y, func):
  print( x * y * func(10))

func_final(10, 10, lamda_mul_10)
```
```
10000
```

### **즉석에서 만들어서 줄 수도 있다.**
```py
print(func_final(10, 10, lambda x : x * 1000))
```
```
1000000
```