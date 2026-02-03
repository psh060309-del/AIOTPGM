---

### 📄 chap6.md (리스트)



```markdown
# 📂 [chap 6] 리스트 (List)

### 1. 리스트의 특징 📋
- 항목들이 순서를 가지고 저장되는 컨테이너입니다.
- 어떤 타입의 항목(숫자, 문자열 등)이라도 저장할 수 있습니다.

### 2. 주요 함수와 메소드 비교
- **메소드 (객체 전용)**: `list.append()`, `list.sort()`, `list.pop()`
- **내장함수 (독립적)**: `len(list)`, `max(list)`, `zip(list1, list2)`

### 3. 리스트 활용 기술
- **슬라이싱**: `list[start:stop:step]`
    - `list[:]`: 깊은 복사 (새로운 주소에 복제)
    - `list[::-1]`: 역순 나열
- **리스트 함축 (List Comprehension)**: `[수식 for 변수 in 리스트 if 조건]`
    - 예: `[x**2 for x in range(5)]` -> `[0, 1, 4, 9, 16]`

### 4. 복사 방식 🖇️
- **얕은 복사**: `values = temps` (주소만 공유하여 한쪽을 바꾸면 같이 바뀜)
- **깊은 복사**: `values = list(temps)` 또는 `temps.copy()` (서로 독립된 객체 생성)
