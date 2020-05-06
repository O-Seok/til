# 조건문 if
어떠한 데이터 처리를 할 때, 조건을 걸어서 원하는 데이터 값을 처리할 수 있다.

## # if

```py
# 기본 구조
if (조건): 
  (원하는 조건의 동작)
else:
  (위의 원하는 조건이 충족하지 못할 시 동작)
```

```py
print(type(True), type(False))
print('boolean')
# example 1
if True:
  print('Yes')

# example 2
if False:
  print('No')

# example 3
if False:
  print('No')
else:
  print('Yes')
```
```
<class 'bool'> <class 'bool'>
boolean
Yes
Yes
```

### **관계연산자 조건출력**

```py
# 관계연산자
# >, >=, <, <=, ==, !=
a = 10
b = 0

print(a == b)
print(a != b)
print(a > b)
print( a >= b)
print(a < b)
print( a<= b)
```
```
False
True
True
True
False
False
```

### **True, False**
`Ture`: "내용", [내용], (내용), {내용}, 1, True  
`False`: "", [], (), {}, 0, False

```py
city = ""
if city:
  print("True")
else:
  print("False")
```
```
False
```

## # 논리 연산자
and, or, not

```py
a = 100
b = 60
c = 15

print('and : ', a > b and b > 3)
print('or : ', a > b or c > b)
print('not : ', not a > b)
print(not False)
print(not True)
```
```
and :  True
or :  True
not :  False
True
False
```

### **연산자 우선순위**
산술 > 관계 > 논리  순서로 적용
```py
print('ex1 : ', 5 + 10 > 0 and not 7 + 3 == 10)
```
```
ex1 : False
```
```py
score1 = 90
score2 = 'A'

if score1 >= 90 and score2 == 'A':
  print('합격 하셨습니다.')
else:
  print('죄송합니다. 불합격입니다.')
```
```
합격 하셨습니다.
```

## # 다중 조건문
여러가지 조건을 줄 때 사용한다.  
`elif`  
```py
num = 70

if num >= 90:
  print('num 등급 A', num)
elif num >= 80:
  print('num 등급 B', num)
elif num >= 70:
  print('num 등급 C', num)
else:
  print('꽝')
```
```
num 등급 C 70
```

## # 중첩 조건문
조건문 안에 조건문을 더 넣어 줄 수 있다.  
```py
age = 27
height = 175

if age >= 20:
  if height >= 170:
    print('A지망 지원 가능')
  elif height >= 160:
    print('B지망 지원 가능')
  else:
    print('지원 불가')
else:
  print('20세 이상 지원 가능')
```
```
A지망 지원 가능
```
