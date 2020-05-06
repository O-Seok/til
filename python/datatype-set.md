# 집합 (set)
> set은 `mutable` 속성을 가진다.  
> 순서 X, 중복 X, 수정 O, 삭제 O

## # set 선언
```py
a = set()
b = set([1, 2, 3, 4])
c = set([1, 4, 5, 6, 6])

print(type(a))
print(c)
```
```
<class 'set'>
{1, 4, 5, 6}
```

## # set 데이터 처리
set은 보통 list나 tuple로 형변환을 하여 데이터 처리를 한다.
```py
t = tuple(b)
print(t)
l = list(b)
print(l)
```
```
(1, 2, 3, 4)
[1, 2, 3, 4]
```

## # set 함수
```py
s1 = set([1, 2, 3, 4, 5, 6])
s2 = set([4, 5, 6, 7, 8, 9])
```

### **교집합**
```py
# 교집합
print(s1.intersection(s2))
print(s1 & s2)
```
```
{4, 5, 6}
{4, 5, 6}
```

### **합집합**
```py
# 합집합
print(s1 | s2)
print(s1.union(s2))
```
```
{1, 2, 3, 4, 5, 6, 7, 8, 9}
{1, 2, 3, 4, 5, 6, 7, 8, 9}
```

### **차집합**
```py
print(s1 - s2)
print(s1.difference(s2))
```
```
{1, 2, 3}
{1, 2, 3}
```

### **set 추가**
```py
s3 = set([7, 8, 9, 10, 15])
s3.add(18)
```
```
{7, 8, 9, 10, 15, 18}
```

### **set 제거**
```py
s3.remove(15)
print(s3)
```
```
{7, 8, 9, 10, 18}
```