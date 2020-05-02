# 문자열
파이썬 데이터 타입 중 문자열에 대해서 정리해보자.
> 문자열은 수정이 불가능한 immutable 속성을 가지고 있다.  
> [참고: mutable & immutable](../python/mutable-immutable.md)

## # 문자열 생성
다음과 같이 문자열을 생성 할 수 있다.  
`str()` 함수를 이용하여 문자열로 형변환 가능하다.  
> `len()` 함수를 사용하여 문자열의 길이를 알 수 있다.  

```py
str1 = "I am boy."
str2 = 'NiceMan'
str3 = ' '
str4 = str('')
print(len(str1), len(str2), len(str3), len(str4))
```
```
9 7 1 0
```

### Escape 문자
```py
escape_str1 = "Do you have a \"big collection\""
print(escape_str1)
escape_str2 = "Tab\tTab\tTab"
print(escape_str2)
```
```
Do you have a "big collection"
Tab     Tab     Tab
```


### 멀티라인
줄이동 하게 되는 경우, 문자열 선언 앞에 \ 를 붙여서 멀티라인 문자열을 생성할 수 있다.
```py
multi2 = \
"""
문자열

멀티라인

테스트
"""
print(multi2)
```
```
문자열

멀티라인

테스트
```


### Raw String
주로 경로같은 경우에 사용한다.  
문자열 앞에 r 을 붙여준다.
```py
raw_s1 = r'C:\Programs\Test\Bin'
print(raw_s1)
raw_s2 = r"\\a\\a"
print(raw_s2)
```
```
C:\Programs\Test\Bin
\\a\\a
```

## # 문자열 연산
파이썬 특징 중 문자열을 연산 할 수 있다.
```py
str_o1 = '*'
str_o2 = 'abc '
str_o3 = "def "
str_o4 = "Niecman"

print(str_o1 * 100)
print(str_o2 + str_o3)
print(str_o1 * 3)
```
```
****************************************************************************************************
abc def 
***
```

### 문자열 형 변환 연산
> type() : 타입을 확인 할 수 있는 함수
```py
print(type(str(77)))
print(str(19.4) + 's')
```
```
<class 'str'>
19.4s
```

## # 문자열 함수
문자열을 다양하게 처리할 수 있는 함수들이 많다.  
< [참고 : w3school](https://www.w3school.com/python/python_ref_string.asp) >

```py
a = 'niceman'
b = 'orange'

print(a.islower())
print(a.isupper())
print(b.endswith('e'))
print(a.capitalize())
print(a.replace('nice', 'Good'))
print(list(reversed(b)))
```
```
True
False
True
Niceman
Goodman
['e', 'g', 'n', 'a', 'r', 'o']
```

## # 슬라이싱
문자열은 `immutable` 특성을 가지고 있기 때문에  
**`슬라이싱`을 통해 원하는 값을 처리**한다.

```py
# 슬라이싱 처리
a = 'niceman'
b = 'orange'

print(a[0:3])
print(a[0:4])
print(a[0:len(a)])
print(a[:4])
print(a[:])

# 인덱스 0부터 4전까지 출력하되, 2개씩 점프!
print(b[0:4:2])  

# 인덱스 1 부터 끝에서 2번째 인덱스까지
print(b[1:-2])

# 인덱스 처음부터 다 출력하되, 거꾸로 출력하시오.
print(b[::-1])
```
```
nic
nice
niceman
nice
niceman
oa
ran
egnaro
```

