# 📂 [Chap 8] 클래스 (Class)

## 1️⃣ 클래스란?

클래스는 **현실 세계의 개념을 코드로 표현한 설계도**입니다.

* 데이터(속성) + 기능(메소드)을 하나로 묶음
* 객체 지향 프로그래밍(OOP)의 핵심 개념

```python
class ClassName:
    pass
```

---

## 2️⃣ 객체(Object)와 인스턴스(Instance)

* **클래스**: 설계도
* **객체 / 인스턴스**: 설계도로 만든 실제 대상

```python
class Person:
    pass

p1 = Person()  # 객체 생성
```

---

## 3️⃣ 생성자 (**init**)

객체가 생성될 때 **자동으로 호출되는 메소드**입니다.

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
```

* `self` : 생성된 객체 자신을 의미

```python
p = Person("Kim", 20)
print(p.name, p.age)
```

---

## 4️⃣ 인스턴스 변수와 메소드

### 🔹 인스턴스 변수

* 객체마다 개별적으로 가지는 변수

```python
self.name
self.age
```

### 🔹 인스턴스 메소드

* 객체를 통해 호출되는 함수

```python
class Person:
    def greet(self):
        print(f"안녕하세요, 저는 {self.name}입니다")

p.greet()
```

---

## 5️⃣ 클래스 변수 (Class Variable)

모든 객체가 **공유**하는 변수

```python
class Person:
    species = "Human"  # 클래스 변수
```

```python
print(Person.species)
```

---

## 6️⃣ 접근 제어 (캡슐화)

| 표기     | 의미               |
| ------ | ---------------- |
| name   | public           |
| _name  | protected (관례)   |
| __name | private (이름 맹글링) |

```python
class Account:
    def __init__(self, balance):
        self.__balance = balance
```

---

## 7️⃣ getter / setter

```python
class Account:
    def __init__(self, balance):
        self.__balance = balance

    def get_balance(self):
        return self.__balance

    def set_balance(self, money):
        if money >= 0:
            self.__balance = money
```

---

## 8️⃣ 상속 (Inheritance)

기존 클래스를 확장해서 새로운 클래스를 만듦

```python
class Animal:
    def speak(self):
        print("소리낸다")

class Dog(Animal):
    def speak(self):
        print("멍멍")
```

---

## 9️⃣ 메소드 오버라이딩

부모 클래스의 메소드를 **재정의**

```python
d = Dog()
d.speak()  # 멍멍
```

---

## 🔟 super()

부모 클래스의 메소드를 호출

```python
class Dog(Animal):
    def __init__(self):
        super().__init__()
```

---

## 1️⃣1️⃣ 다형성 (Polymorphism)

같은 메소드 이름이 다른 동작 수행

```python
animals = [Dog(), Animal()]
for a in animals:
    a.speak()
```

---

## 1️⃣2️⃣ 특수 메소드 (Magic Method)

```python
__str__()
__len__()
__repr__()
__eq__()
```

```python
class Book:
    def __init__(self, title):
        self.title = title

    def __str__(self):
        return self.title
```

---

## 1️⃣3️⃣ @staticmethod / @classmethod

### staticmethod

객체, 클래스와 무관한 메소드

```python
class Math:
    @staticmethod
    def add(a, b):
        return a + b
```

### classmethod

클래스 자체를 다루는 메소드

```python
class Person:
    count = 0

    @classmethod
    def increase(cls):
        cls.count += 1
```

---

## 📌 Chap 8 코딩 필수 체크리스트

✅ class / object 개념
✅ __init__과 self
✅ 인스턴스 vs 클래스 변수
✅ 상속 / 오버라이딩 / super()
✅ 접근제어 (__private)
✅ staticmethod / classmethod

👉 **이 정도면 실무·시험·코딩 전부 커버 가능**
