# for
for문은 제어문에서 반복문이다.  
범위를 주어주고 범위동안 반복하면서 데이터 처리를 할 때 사용한다.

### **기본형식**
```py
for () in (조건범위):
  (범위동안 반복하면서 처리하는 동작)
```
간단한 예를 보면
```py
# 0 ~ 9 까지 반복을 하고 싶다면,
for v2 in range(10):
  print('v2 is : ',v2)
```
```
v2 is :  0
v2 is :  1
v2 is :  2
v2 is :  3
v2 is :  4
v2 is :  5
v2 is :  6
v2 is :  7
v2 is :  8
v2 is :  9
v3 is :  1
v3 is :  2
v3 is :  3
v3 is :  4
v3 is :  5
v3 is :  6
v3 is :  7
v3 is :  8
v3 is :  9
```

```py
# 1부터 100까지의 합
print()
print('1부터 100까지의 합 구하기 ( for문 이용 )')
score = 0
for num in range(1, 101):
  score += num  

print(score)
```
```
5050
```

## # 시퀀스 (순서가 있는) 자료형 반복
문자열, 리스트, 튜플, 집합, 딕셔너리

### **리스트**
```py
names = ['Kim', 'Park', 'Cho', 'Yoo', 'Choi']

for v in names:
  print('You are : "', v)
```
```
You are : " Kim
You are : " Park
You are : " Cho
You are : " Yoo
You are : " Choi
```

### **문자열**
```py
word = "dreams"

for s in word:
  print('word : "', s)
```
```
word : " d
word : " r
word : " e
word : " a
word : " m
word : " s
```

### **딕셔너리**
```py
my_info = {
  'name': 'Kim',
  'age': 33,
  'city': 'Seoul' 
}
```
```py
# 기본 값은 키를 리턴한다.
for key in my_info:
  print('my_info', key)
```
```
my_info name
my_info age
my_info city
```
```py
# 값
for value in my_info.values():
  print('my_info_value', value)
```
```
my_info_value Kim
my_info_value 33
my_info_value Seoul
```
```py
# 키
for key in my_info.keys():
  print('my_info_key', value)
```
```
my_info_key Seoul
my_info_key Seoul
my_info_key Seoul
```

```py
# 키 + 값
for item in my_info.items():
  print('my_info_item', item) 
```
```
my_info_item ('name', 'Kim')
my_info_item ('age', 33)
my_info_item ('city', 'Seoul')
```

## # break
for문 안에서 사용된다.  
내가 찾고자 하는 값이 반복문으로 돌아가는 중간에 있다면?   
내가 의도하는, 원하는 조건, 값이 나왔을 때 반복문에서 나올 때 사용한다.

```py
numbers = [14, 3, 4, 7, 10, 24, 17, 2, 33, 15, 34, 44, 38]

for num in numbers:
  if num == 33:
    print('found : 33 !')
    break
  else:
    print('not found : 33 !!')
```
```
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
found : 33 !
```

## # for - else
for 문을 다 실행하고 마지막에 else가 실행이 된다.  
for 문 안에 break 구문이 작동이 되었다면, else 구문이 실행이 안된다.  
break문이 작동되지 않았다면 마지막에 else 구문이 작동된다.

```py
numbers2 = [14, 3, 4, 7, 10, 24, 17, 2, 37, 15, 34, 44, 38]

for num in numbers2:
  if num == 33:
    print('found : 33 !')
    break
  else:
    print('not found : 33 !!')
else:
  print('not found 33 ..............')
```
```
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found : 33 !!
not found 33 ..............
```

## # continue
for문 안에 사용된다.  
continue를 만나면 그 값은 넘어가고 다음 순서대로 간다.  
조건문이 아닌 for문, 반복문으로 간다.

```py
lt = ['1', 2, 5, True, 4.3, complex(4)]

for v in lt:
  if type(v) is float:
    continue
  print('타입 : ', type(v))
else:
  print('End')
```
```
타입 :  <class 'str'>
타입 :  <class 'int'>
타입 :  <class 'int'>
타입 :  <class 'bool'>
타입 :  <class 'complex'>
End
```