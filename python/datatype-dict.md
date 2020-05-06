# 딕셔너리 (dict)
> 딕셔너리는 `mutable` 속성을 가진다.  
> 중복 X (key: 중복 X, value: 중복 O), 순서 X, 수정 O, 삭제 O

## # 딕셔너리 선언
딕셔너리는 다음과 같은 방법으로 선언 해줄 수 있다.
```PY
a = {'name': 'Jeong', 'phone': '010-9999-9999', 'birth': '890928'}
b = {0: 'Hello Python', 1: 'Hello Coding'}
c = {'arr':[1, 2, 3, 4, 5]}

print(type(a))
print(a)
print(b)
print(c)
```
```
<class 'dict'>
{'name': 'Jeong', 'phone': '010-9999-9999', 'birth': '890928'}
{0: 'Hello Python', 1: 'Hello Coding'}
{'arr': [1, 2, 3, 4, 5]}
```

## # 딕셔너리 출력
특정 key를 선택하여 value 값을 출력 할 수도  
get() 함수로 key를 지정하여 또는 슬라이싱을 통해서 값을 출력 할 수도 있다.
```py
print(a['name'])
print(a.get('name'))
print(a.get('address'))
print(c.get('arr'))
print(c.get('arr')[1:3])
```
```
Jeong
Jeong
None
[1, 2, 3, 4, 5]
[2, 3]
```

boolean 출력 값을 출력 할 수도 있다.
```py
print(2 in b)
print(2 not in b)
print('name' in a)
```
```
False
True
True
```
## # 딕셔너리 추가
직관적으로 추가를 할 수 있다.
```py
a['address'] = 'Seoul'
print(a)
a['rank'] = [1, 2, 3]
a['rank2'] = (1, 2, 3,)
print(a)
```
```
{'name': 'Jeong', 'phone': '010-9999-9999', 'birth': '890928', 'address': 'Seoul'}
{'name': 'Jeong', 'phone': '010-9999-9999', 'birth': '890928', 'address': 'Seoul', 'rank': [1, 2, 3], 'rank2': (1, 2, 3)}
```

## # keys(), values(), items()

### **keys(), values()**
딕셔너리에서 값들을 처리할 때,  
`keys()`: key 값들만 list의 형태로 값을 반환  
`values()`: value 값들만 list의 형태로 값을 반환  

> ⚠️ keys(), values() 값들은 list 형태의 값으로 출력 되지만, 출력 된 값들을 사용하려면 list() 함수를 이용하여 list로 형변환 하여 데이터 처리를 한다.

```py
print(a.keys())           
print(list(a.keys()))
```
```
dict_keys(['name', 'phone', 'birth', 'address', 'rank', 'rank2'])
['name', 'phone', 'birth', 'address', 'rank', 'rank2']
```

list로 형변환 이후 데이터 처리를 할 수 있다.

```py
temp = list(a.keys())
print(temp[1:3])
```
```
['phone', 'birth']
```

### **items()**
items()는 key와 value를 한 쌍으로 갖는 튜플 형식으로 값을 반환한다.
```py
print(a.items())
```
```
dict_items([('name', 'Jeong'), ('phone', '010-9999-9999'), ('birth', '890928'), ('address', 'Seoul'), ('rank', [1, 2, 3]), ('rank2', (1, 2, 3))])
```
list로 형변환을 해준 후
```py
print(list(a.items()))
```
```
[('name', 'Jeong'), ('phone', '010-9999-9999'), ('birth', '890928'), ('address', 'Seoul'), ('rank', [1, 2, 3]), ('rank2', (1, 2, 3))]
```
원하는 데이터 처리를 할 수 있다.
```py
tems =  list(a.items())
print(tems[0])
print(tems[0][0])
print(tems[0][0][:2])
```
```
('name', 'Jeong')
name
na
```