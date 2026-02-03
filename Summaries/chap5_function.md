# 📂 [Chap 5] 함수 (Functions)

## 1️⃣ 함수 정의

함수는 특정 작업을 수행하는 코드 묶음입니다.

```python
def 함수이름(매개변수1, 매개변수2, ...):
    명령문1
    명령문2
```

---

## 2️⃣ 함수 호출

정의된 함수를 실행할 때 사용합니다.

```python
함수이름(인수)
```

---

## 3️⃣ pass 키워드

함수의 내용을 나중에 작성하고 싶을 때 사용합니다.

```python
def myfunc():
    pass
```

---

## 4️⃣ 디폴트 인수 (Default Argument)

함수의 매개변수가 기본값을 가지는 경우입니다.

```python
def greet(name, msg="별일없죠"):
    print("안녕", name + ',' + msg)

greet("영희")  # msg를 지정하지 않으면 기본값 사용
```

**출력 결과**

```
안녕 영희,별일없죠
```

---

## 5️⃣ 키워드 인수 (Keyword Argument)

인수의 이름을 명시적으로 지정하여 값을 전달하는 방법입니다.

```python
def sub(x, y, z):
    print("x=", x, "y=", y, "z=", z)

sub(x=10, y=20, z=30)
```

---

## 6️⃣ 가변 인수 (*args)

매개변수의 개수가 변해도 사용할 수 있는 인수입니다.

```python
def varfunc(*args):
    print(args)

varfunc(10)
varfunc(10, 20, 30)
```

**출력 결과**

```
(10,)
(10, 20, 30)
```

---

## 7️⃣ 가변 길이 키워드 인수 (**kwargs)

키워드 인수를 딕셔너리 형태로 전달합니다.

```python
def myfunc(**kwargs):
    result = ""
    for arg in kwargs.values():
        result += arg
    return result

print(myfunc(a="Hi!", b="Mr.", c="Kim"))
```

**출력 결과**

```
Hi!Mr.Kim
```

---

## 8️⃣ * 연산자로 언패킹하기

* `*` : 모든 반복 가능한 객체를 언패킹
* `**` : 딕셔너리 객체를 언패킹

```python
numbers = [1, 2, 3]

def show_numbers(*args):
    for n in args:
        print(n)

show_numbers(numbers)
# args는 ([1, 2, 3],) 형태

show_numbers(*numbers)
# show_numbers(1, 2, 3) 과 동일
```
