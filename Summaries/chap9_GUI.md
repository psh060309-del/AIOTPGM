# 📂 [Chap 9] GUI 프로그래밍 (Tkinter)

## 1️⃣ GUI란?

GUI(Graphical User Interface)는 **마우스, 버튼, 창** 등을 통해 사용자와 상호작용하는 프로그램입니다.

파이썬에서는 기본 라이브러리인 **Tkinter**를 가장 많이 사용합니다.

```python
import tkinter as tk
```

---

## 2️⃣ 기본 창 만들기

```python
import tkinter as tk

window = tk.Tk()          # 메인 윈도우 생성
window.title("My App")   # 창 제목
window.geometry("300x200")  # 창 크기

window.mainloop()         # 이벤트 루프 시작
```

📌 `mainloop()`가 있어야 창이 유지됨

---

## 3️⃣ 위젯(Widget)

위젯은 GUI를 구성하는 **부품**입니다.

### 주요 위젯

* Label : 텍스트 표시
* Button : 버튼
* Entry : 한 줄 입력창
* Text : 여러 줄 입력창
* Checkbutton / Radiobutton

---

## 4️⃣ Label

```python
label = tk.Label(window, text="Hello Tkinter")
label.pack()
```

---

## 5️⃣ Button & 이벤트 처리

```python
def click():
    print("버튼 클릭됨")

btn = tk.Button(window, text="클릭", command=click)
btn.pack()
```

📌 `command`에는 **함수 이름만** 전달 (괄호 ❌)

---

## 6️⃣ Entry (입력창)

```python
entry = tk.Entry(window)
entry.pack()

value = entry.get()   # 입력값 가져오기
entry.delete(0, tk.END)  # 입력값 삭제
```

---

## 7️⃣ 메시지 박스

```python
from tkinter import messagebox

messagebox.showinfo("알림", "완료되었습니다")
messagebox.showwarning("경고", "주의하세요")
messagebox.showerror("에러", "오류 발생")
```

---

## 8️⃣ 배치 관리자 (Layout Manager)

GUI에서 위젯을 **어디에, 어떤 방식으로 배치할지 결정**하는 기능입니다.

Tkinter에는 대표적으로 `pack()`, `grid()`, `place()`가 있지만, 수업과 시험에서는 주로 **pack과 grid**를 사용합니다.

---

### 🔹 pack()

* 위젯을 **위에서 아래 방향**으로 자동 배치
* 간단한 GUI에 적합

```python
widget.pack()
```

📌 특징

* 코드가 간단함
* 세밀한 위치 조정은 어려움

---

### 🔹 grid()

* **행(row), 열(column)** 구조로 배치
* 표 형태 레이아웃에 적합

```python
widget.grid(row=0, column=1)
```

📌 특징

* 위치 제어가 정확함
* 입력창 + 버튼 구성에 자주 사용

⚠️ **같은 컨테이너(Frame, window) 안에서는 pack과 grid를 절대 섞어 쓰면 안 됨**

---

## 9️⃣ 변수 클래스 (StringVar, IntVar)

Tkinter 전용 변수로, **GUI 위젯과 파이썬 변수를 자동으로 연결**해 줍니다.

* Entry, Label, Checkbutton 등과 함께 사용
* 값이 바뀌면 서로 자동 반영됨

```python
name = tk.StringVar()
entry = tk.Entry(window, textvariable=name)
```

```python
print(name.get())  # 값 가져오기
name.set("Kim")   # 값 설정하기
```

📌 왜 쓰나?

* `entry.get()`을 매번 호출하지 않아도 됨
* GUI 상태 관리가 쉬워짐

````

---

## 🔟 이벤트 바인딩 (bind)
마우스 클릭, 키보드 입력 같은 **사용자 행동(이벤트)**을 감지하는 방법입니다.

```python
def key_event(event):
    print(event.char)

window.bind("<Key>", key_event)
````

📌 설명

* `<Key>` : 키보드 입력 이벤트
* `event` 객체 안에 입력된 키 정보가 들어 있음

📌 `command` vs `bind`

* `command` : 버튼 클릭 전용
* `bind` : 키보드, 마우스 등 다양한 이벤트 처리 가능

window.bind("<Key>", key_event)

````

---

## 1️⃣1️⃣ 프레임 (Frame)
프레임은 **위젯들을 묶는 상자(컨테이너)**입니다.

- GUI 구조를 깔끔하게 나눌 때 사용
- 프레임 단위로 `pack` 또는 `grid` 사용 가능

```python
frame = tk.Frame(window)
frame.pack()
````

📌 언제 쓰나?

* 영역별로 버튼 / 입력창을 구분하고 싶을 때
* 복잡한 GUI에서 필수

````

---

## 1️⃣2️⃣ GUI 프로그래밍 필수 패턴 (클래스 기반)
GUI를 **클래스로 설계하는 방식**으로, 과제·실무에서 가장 많이 사용됩니다.

```python
class App:
    def __init__(self, window):
        self.entry = tk.Entry(window)
        self.entry.pack()

        self.btn = tk.Button(window, text="출력", command=self.print_text)
        self.btn.pack()

    def print_text(self):
        print(self.entry.get())

root = tk.Tk()
app = App(root)
root.mainloop()
````

📌 핵심 포인트

* `__init__` : 위젯 생성
* 메소드 : 이벤트 처리
* `self` : 위젯을 클래스 안에서 공유

👉 **Chap 8 클래스 개념이 여기서 바로 쓰임**

```


