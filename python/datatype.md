# 데이터 타입
파이썬의 데이터는 여러가지의 형태로 존재한다.

## # 데이터 타입
  - 문자형 : str
  - 숫자형 : int(정수), float(실수), complex(복소수)
  - boolean(참, 거짓)
  - 자료형
    - list
    - tuple
    - set
    - dict


> type() : 데이터 타입을 확인 할 수 있는 함수
```py
# 데이터 타입

v_str1 = 'Niceman'
v_bool = True
v_str2 = 'Goodboy'
v_float = 10.3
v_int = 7
v_dict = {
    'name' : 'Kim',
    'age' : 25
}
v_list = [3, 5, 7]
v_tuple = (3, 5, 7)
v_set = {7, 8, 9}

print(type(v_tuple))
print(type(v_set))
print(type(v_float))
print(type(v_str1))
print(type(v_str2))
print(type(v_bool))
print(type(v_dict))
print(type(v_int))
print(type(v_list))
```
```
<class 'tuple'>
<class 'set'>
<class 'float'>
<class 'str'>
<class 'str'>
<class 'bool'>
<class 'dict'>
<class 'int'>
<class 'list'>
```

## # 데이터 형변환
파이썬은 데이터 타입을 바꾸는 `형변환`이 가능하다.
```py

result2 = 9.0
c = 10

print(int(result2))
print(float(c))
print(complex(3))
print(int(True))
print(int(False))
print(int('3'))
print(complex(False))
```
```
9
10.0
(3+0j)
1
0
3
0j
```
