# 📂 [Chap 6] 리스트 (List)

## 1️⃣ 리스트란?

리스트는 여러 항목을 **순서 있게 저장**하는 컨테이너입니다.

* 어떤 타입의 항목이라도 저장 가능
* 인덱스를 사용해 요소 접근 가능

```python
리스트이름 = [요소1, 요소2, ...]
```

### 인덱스

* 앞에서부터: `0, 1, 2, 3, ...`
* 뒤에서부터: `..., -4, -3, -2, -1`

---

## 2️⃣ zip() 함수

두 개 이상의 리스트를 받아 같은 인덱스의 요소를 묶어줍니다.

```python
questions = ["name", "quest", "color"]
answers = ["Kim", "파이썬", "blue"]

for q, a in zip(questions, answers):
    print(f"What is your {q}? it is {a}")
```

**출력 결과**

```
What is your name? it is Kim
What is your quest? it is 파이썬
What is your color? it is blue
```

---

## 3️⃣ 메소드(method) vs 내장 함수(built-in function)

### 🔹 메소드 (method)

* 특정 자료형(객체)에 포함된 기능
* 사용법: `데이터.메소드()`

예) `append()`, `sort()`, `split()`

### 🔹 내장 함수 (built-in function)

* 객체에 소속되지 않은 파이썬 기본 함수
* 사용법: `함수이름(데이터)`

예) `zip()`, `len()`, `max()`

---

## 4️⃣ 리스트 메소드

```python
list.pop(index)        # index 위치 요소 삭제
list.sort()            # 리스트 정렬
list.index(value)      # value가 있는 위치 반환
list.append(value)     # 리스트 끝에 요소 추가
list.remove(value)     # value 삭제 (첫 번째만)
list.extend(otherlist) # 다른 리스트 이어 붙이기
list.insert(index, value) # 원하는 위치에 삽입
list.clear()           # 리스트 비우기
list.count(value)      # 특정 값 개수 세기
list.reverse()         # 순서 뒤집기
list.copy()            # 새로운 리스트 복사
```

📌 `y = x` → 같은 리스트 참조
📌 `y = x.copy()` → 서로 독립된 리스트

---

## 5️⃣ 리스트에서 사용하는 내장 함수

### 1. 수치 및 통계 관련

```python
sum(list)
max(list)
min(list)
len(list)
round(number, ndigits)
```

### 2. 논리 및 상태 확인

```python
all(list)
any(list)
```

### 3. 데이터 변형 및 필터링

```python
filter(function, list)
map(function, list)
sorted(list)
ord(char)
```

### 4. 반복 및 누적 관련

```python
enumerate(list)
accumulate(list)   # from itertools import accumulate
reduce(function, list)  # from functools import reduce
```

### 5. 랜덤 선택

```python
import random
numberList = [1,2,3,4,5,6,7,8,9,10]
print("랜덤하게 선택한 항목=", random.choice(numberList))
```

---

## 6️⃣ filter() 예제

```python
numbers = [5, 12, 7, 18, 24, 2]
result = filter(lambda x: x > 10, numbers)
print(list(result))
# 결과: [12, 18, 24]
```

---

## 7️⃣ map() 예제

```python
numbers = [1, 2, 3, 4, 5]
result = map(lambda x: x**2, numbers)
print(list(result))
# 결과: [1, 4, 9, 16, 25]
```

---

## 8️⃣ 얕은 복사 vs 깊은 복사

```python
temps = [28,31,33,35,27,26,25]

values = temps          # 얕은 복사
values = list(temps)    # 깊은 복사
```

---

## 9️⃣ 슬라이싱

```python
리스트[start:stop]   # stop 미포함
```

```python
리스트[:]        # 깊은 복사
리스트[::-1]     # 역순
리스트[::2]      # 간격 슬라이싱
```

```python
리스트[::2] = [99, 99, 99, 99]
```

---

## 🔟 문자열과 리스트

문자열은 문자들이 모인 리스트처럼 다룰 수 있습니다.

---

## 1️⃣1️⃣ 리스트 함축 (List Comprehension)

```python
[수식 for 변수 in 리스트 if 조건]
```

```python
prices = [135, -545, 922, 356, -992, 217]
mprices = [i if i > 0 else 0 for i in prices]
```

```python
words = ["All", "good", "things", "must", "come", "to", "an", "end."]
letters = [w[0] for w in words]
```

```python
numbers = [x+y for x in ['a','b','c'] for y in ['x','y','z']]
```

---

## 1️⃣2️⃣ 2차원 리스트와 리스트 함축

```python
rows, cols = 3, 4
grid = [[0 for _ in range(cols)] for _ in range(rows)]
```

**결과**

```python
[[0, 0, 0, 0],
 [0, 0, 0, 0],
 [0, 0, 0, 0]]
```
