---
layout: post
title: "[Python] 기초 개념: 변수"
date: 2020-10-31 11:00:00 +0930
categories: 
 - 컴퓨터 프로그래밍
badges:
 - type: primary
   tag: 프로그래밍의 개념
 - type: success
   tag: 해보면서 깨달아야 합니다.
---

최근 가장 각광받는 프로그래밍 언어는 파이썬입니다. 파이썬을 통해 기본적인 프로그래밍의 개념을 알아봅시다.

<!--more-->

### 변수(variable)

- 프로그래밍에 있어 가장 기초가 되는 개념이 무엇이냐고 물어본다면, 저는 **변수(variable)**라고 하겠습니다.
- 변수는 값(value)을 저장합니다.

```python
# name 이라는 변수에 '김동현' 이라는 값을 저장
name = 'barkle'
# age 라는 변수에 42 라는 값을 저장
age = 42
# isMarried 라는 변수에 True 값을 저장
isMarried = True
```

- 변수에 값이 저장되면 변수를 통해 값을 사용할 수 있습니다.

```python
print(name)
print(age)
print(isMarried)
```

- 여러 값들을 저장할 수 있는 변수들도 있습니다.
1. 리스트
2. 튜플
3. 딕셔너리

```python
# 리스트
movie_list = ['광해', '태극기 휘날리며', '베테랑', '엑시트', '부산행']
# 튜플
actor_tuple = ('현빈', '손예진', '원빈', '이나영', '장동건', '고소영')
# 딕셔너리
sportstar_dictionary = { '축구':'손흥민', '야구':'류현진', '배구':'김연경', '농구':'김선형'}
```

- 나아가 변수의 형태를 직접 정의하거나, 다른 라이브러리에서 만든 변수를 사용하는 것도 가능합니다.

```python
import pandas as pd

friend_dict_list = [
  {'name': 'John', 'age':25, 'job': 'student'},
  {'name': 'Nate', 'age':30, 'job': 'teacher'}
]
df = pd.DataFrame(friend_dict_list)
df
```

### 변수의 의미
- 변수의 종류나 형태, 사용방법을 외우는 것도 중요하지만, 더 중요한 것은 변수가 어떤 역할을 하는지 파악하는 것입니다.
- 결국 **프로그램은 원하는 변수에 원하는 값을 입력하는 행위**입니다.
- 변수에는 다양한 값들이 들어갈 수 있다는 전제 하에 변수를 활용하여 원하는 값을 얻어낼 수 있는 과정을 설계해야 합니다.

### 예제: 구구단
- 다음 프로그램은 아주 간단한 형태를 가지고 있습니다.
  1. 원하는 값을 number라는 변수에 입력하고,
  2. 그 값을 이용하여 구구단을 계산하고,
  3. 그 값을 출력합니다.
  
```python
number = input('숫자를 입력하시오:')
for i in range(1,10):
  print(number, "*", i, "=", int(number)*i)
```

위 프로그램들을 실행해보려면 아래 파일을 [Google Colab](https://colab.research.google.com){:target='_blank'} 사이트에서 불러오면 됩니다.

[Python_Basic_Variable.ipynb]({{ site.url }}/assets/reference/Python_Basic_Variable.ipynb)
