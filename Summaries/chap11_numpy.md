# 📊 NumPy & Matplotlib 핵심 정리 가이드

파이썬 데이터 분석의 기초가 되는 **NumPy**와 시각화 도구 **Matplotlib**의 핵심 내용을 정리한 문서입니다.

---

## 🔢 1. NumPy (Numerical Python) 기초

NumPy는 대규모 다차원 배열과 행렬 연산에 최적화된 라이브러리입니다.

### 💡 주요 특징
**동종 데이터(Homogeneous)**: 배열 내 모든 원소는 같은 자료형이어야 합니다. 
**연속적 메모리**: 데이터가 메모리에 연속적으로 배치되어 리스트보다 연산 속도가 압도적으로 빠릅니다.
**벡터화 연산(Vectorized Operation)**: 반복문 없이 배열 전체에 대한 산술 연산이 가능합니다.

### 🏗️ 배열 생성 및 구조
`np.array([1, 2, 3])`: 리스트를 ndarray로 변환 
`np.arange(start, stop, step)`: 규칙적인 산술 진행을 가지는 배열 생성 
`np.linspace(start, stop, num)`: 지정된 구간을 균등하게 나눈 배열 생성
`a.shape`: 배열의 크기(형태) 확인 
`a.reshape(row, col)`: 데이터는 유지하면서 배열의 차원 구조 변경 

### 🔍 인덱싱과 슬라이싱
**슬라이싱**: `a[0:2, 1:3]` 처럼 행과 열의 범위를 지정하여 부분 추출
**불리언 인덱싱**: `a[a > 5]` 와 같이 조건에 맞는 데이터만 필터링 

---

## 📊 2. Matplotlib 데이터 시각화

데이터를 직관적으로 이해하기 위해 그래프로 표현하는 라이브러리입니다.

### 📈 기본 그래프 그리기 단계
1. **데이터 준비**: NumPy를 사용하여 x, y축 데이터 생성
2. **그래프 생성**: `plt.plot(x, y)` 호출 
3. **데코레이션**: `plt.xlabel()`, `plt.ylabel()`, `plt.title()` 등으로 설명 추가
4. **출력**: `plt.show()`로 화면에 표시 

### 🎨 주요 그래프 종류
**선 그래프(Line Plot)**: 데이터의 변화 추이를 볼 때 사용 
**막대 그래프(Bar Chart)**: 항목별 수치를 비교할 때 사용 
**히스토그램(Histogram)**: 데이터의 분포(빈도)를 확인할 때 사용

---

## 🛠️ 3. 활용 예제: 함수 그래프 비교

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0, 10, 100)
plt.plot(x, x, label='linear')
plt.plot(x, x**2, label='quadratic')
plt.legend()
plt.show()
[cite_start]```
---
