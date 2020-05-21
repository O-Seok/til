# DB 수정, 삭제
등록되어 있는 데이터들을 수정, 삭제 해본다.

users 데이터:

<img src="../image/db_GUI.png">

## # DB파일 조회(없으면 새로 생성)

```py
import sqlite3

conn = sqlite3.connect('/Users/claudjung/Documents/dev/python_basic/resource/database.db')
```
**`connect()`** 로 DB파일 위치와 파일 이름을 조회해보고, 없으면 생성해준다.

## # 커서 바인딩
```py
c = conn.cursor()
```

**`cursor()`**  
기본적으로 데이터의 마지막 부분을 가리키고 있다.  
현재 커서 위치의 상태를 기억한다.

## # 데이터 수정 (UPDATE)
데이터 수정은 어떠한 속성을 어떠한 값으로 수정 해주해야 한다 느낌!  
수정할 위치값과 수정값이 필요하다.

### **튜플**
```py
c.execute("UPDATE users SET username = ? WHERE id =?", ('niceman', 2))
```

### **딕셔너리**
```py
c.execute("UPDATE users SET username = :name WHERE id = :id", {'name':'Goodman', 'id': 5 })
```

### **format 스타일**
```py
c.execute("UPDATE users SET username = '%s' WHERE id = '%s'" % ('badboy', 3))
```

현재의 데이터 값들을 조회 해보면, 위의 수정사항들이 적용된 것을 알 수 있다.

```py
for user in c.execute("SELECT * FROM users"):
  print(user)
```
```
(1, 'Jeong', 'totkfa789@gmail.com', '010-0000-0000', 'Jeong.com', '2020-05-21 12:18:07')
(2, 'niceman', 'Park@gmail.com', '010-1111-1111', 'Park.com', '2020-05-21 12:18:07')
(3, 'badboy', 'leenave.com', '010-2222-2222', 'Lee.com', '2020-05-21 12:18:07')
(4, 'Cho', 'Cho@.com', '010-3333-3333', 'Cho.com', '2020-05-21 12:18:07')
(5, 'Goodman', 'You@.com', '010-4444-4444', 'You.com', '2020-05-21 12:18:07')
```

## # 데이터 삭제 (DELETE)
데이터 삭제도 마찬가지로 어떤 위치의 어떠한 값을 삭제한다 느낌이다.  
또한 모두 삭제도 있다.

### **1개의 튜플 숫자**
```py
c.execute("DELETE FROM users WHERE id = ?", (2,))
```

### **딕셔너리**
```py
c.execute("DELETE FROM users WHERE id = :id", {"id": 5})
```

### **format 스타일**
```py
c.execute("DELETE FROM users WHERE id = '%s'" % 4 )
```

현재의 데이터 값들을 조회 해보면, 위의 삭제사항들이 적용된 것을 알 수 있다.

```py
for user in c.execute("SELECT * FROM users"):
  print(user)
```
```
(1, 'Jeong', 'totkfa789@gmail.com', '010-0000-0000', 'Jeong.com', '2020-05-21 12:18:07')
(3, 'badboy', 'leenave.com', '010-2222-2222', 'Lee.com', '2020-05-21 12:18:07')
```

### **전체삭제**
```py
print(conn.execute("DELETE FROM users"))
```


## # 키워드
  - sqlite3
  - connect()
  - cursor()
  - execute()
  - "UPDATE users SET username = ? WHERE id= ? "
  - "DELETE FROME users WHERE id = ?"
  - "DELETE FROME users"