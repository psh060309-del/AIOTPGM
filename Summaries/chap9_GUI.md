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

### pack()

* 위에서 아래로 자동 배치

```python
widget.pack()
```

### grid()

* 행(row), 열(column) 기반 배치

```python
widget.grid(row=0, column=1)
```

⚠️ **같은 컨테이너에서 pack과 grid 혼용 불가**

---

## 9️⃣ 변수 클래스 (StringVar, IntVar)

```python
name = tk.StringVar()
entry = tk.Entry(window, textvariable=name)

print(name.get())
name.set("Kim")
```

---

## 🔟 이벤트 바인딩 (bind)

```python
def key_event(event):
    print(event.char)

window.bind("<Key>", key_event)
```

---

## 1️⃣1️⃣ 프레임(Frame)

위젯들을 그룹화하는 컨테이너

```python
frame = tk.Frame(window)
frame.pack()
```

---

## 1️⃣2️⃣ GUI 프로그래밍 필수 패턴

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
```

---

## 📌 Chap 9 필수 체크리스트

✅ Tk() / mainloop()
✅ Label / Button / Entry
✅ command 이벤트 처리
✅ pack vs grid
✅ StringVar / IntVar
✅ 클래스 기반 GUI 구조

👉 **이 정도면 GUI 과제·시험 충분히 커버 가능**
