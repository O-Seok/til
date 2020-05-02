# 파이썬의 mutable / immutable 👏🏼
## 변수
변수는 객체를 가리킨다.
```py
num1 = 10
```
위와 같이 변수 num1 = 10 으로 선언했다면, 컴퓨터 메모리에 10이라는 값이 저장 된다. 이때 num1은 10이 저장된 메모리의 위치를 가리킨다.  
즉, 10이라는 정수형 객체를 num1이라는 변수가 가리키고 있는 것이다.

## mutable, immutable

>mutable : 값이 변한다.  
>immutable: 값이 변하지 않는다.

데이터 타입마다 각각 다른 특성을 가지고 있다.
  
|mutable|immutable|
|-------|---------|
|리스트 (List) | 숫자형 ( Number )|
|딕셔너리 (dict) | 문자형 ( String)|
|셋 (Set)| 튜플 ( Tuple )|
|*| Boolean |

### mutable
  - list
<img src="../image/mutable_list.png">
  - dictionary
<img src="../image/mutable_dict.png">

### immutable
  - number
<img src="../image/immutable_number.png">
  - string
<img src="../image/immutable_string.png">
  - tuple
<img src="../image/immutable_tuple.png">


`변수가 함수의 매개변수로 전달될 때 원래 입력 변수값이 변경되는지 안되는지는 중요하기 때문에 immutable, mutable 특성은 매우 중요하다.  
`