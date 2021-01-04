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

'''python
# name 이라는 변수에 '김동현' 이라는 값을 저장
name = '김동현'
# age 라는 변수에 42 라는 값을 저장
age = 42
# isMarried 라는 변수에 True 값을 저장
isMarried = True
'''

- 저장된 값은 다시 불러서 사용할 수 있습니다.

'''python
print(name)
print(age)
print(isMarried)
'''

> 김동현
> 42
> True





[Python_Basic_Variable.ipynb]({{ site.url }}/assets/reference/Python_Basic_Variable.ipynb)
