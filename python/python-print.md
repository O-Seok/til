# print() / 나도 'Hello World!'  👏🏼

## # print()
파이썬의 print() 함수는 `출력` 함수이다.  
간단히 문자열을 출력해본다.  
그 유명한 Hello World 를... 😁

### 기본출력
```py
print('Hello World!')
```
```
Hello World!
```
문자열은 다음과 같이도 출력 가능하다.
```py
print('Hello World!')
print("Hello World!")
print("""Hello World!""")
print('''Hello World!''')
```
```
Hello World!
Hello World!
Hello World!
Hello World!
```

> Escape 코드
> |코드|특징|
> |--|--|
> |\n| 개행|
> |\t| 탭|
> |\\\ |문자|
> |\\' |문자|
> |\\"  |문자|
> |\r |캐리지 리턴|
> |\f |폼 피드|
> |\a | 벨 소리|
> |\b |백 스페이스|
> |\000 |널 문자|

```py
print("'you'")
print('\'you\'')
print('"you"')
print("""'you'""")
print('\\you\\')
print('\\you\\\n\n\n')
print('test')
print('\t\t\ttest')
```
```
'you'
'you'
"you"
'you'
\you\
\you\



test
                        test
```
---

## # 옵션
print()함수는 출력 값에 다양한 옵션을 줄 수 있다.
  - separator  
    값들 사이에 옵션을 넣어줄 수 있다.
```py
# Separator 옵션 사용
print('T', 'E', 'S', 'T', sep='')
print('2019', '02', '19', sep='-')
print('niceman', 'google.com', sep='@')
```
```
TEST
2019-02-19
niceman@google.com
```

  - end
    값 끝에 옵션을 줄 수 있다.
```py
# End 옵션 사용
print('welcome to', end=' ')
print('the black parade', end=' ')
print('piano notes')
print('testtest')
```
```
welcome to the black parade piano notes
testtest
```

  - format
    format 옵션을 이용하여 다양하게 특정한 출력 값들을 매칭 시켜줄 수 있다.
```py
# format 사용 [] , {}, ()
print('{} and {}'.format('You', 'me'))
print('{0} and {1}, and {0}'.format('You', 'me'))
print('{a} are {b}'.format(a='you', b='me'))
```
```
You and me
You and me, and You
you are me
```
> %s : 문자,  %d = 정수,  %f = 실수
```py
# %s : 문자, %d = 정수, %f = 실수
print("%s's favorite number is %d" %('Cluad', 3))

print("Test1: %5d, price: %4.2f" %(776, 6534.123))
print("Test1: {0: 5d}, pricce: {1: 4.2f}".format(776, 6534.123))
print("Test1: {a: 5d}, pricce: {b: 4.2f}".format(a=776, b=6534.123))
```
```
Cluad's favorite number is 3
Test1:   776, price: 6534.12
Test1:   776, pricce:  6534.12
Test1:   776, pricce:  6534.12
```
