---
layout: post
title: "[Python] 기초 개념: 반복문"
date: 2020-11-07 11:00:00 +0930
categories: 
 - 컴퓨터 프로그래밍
badges:
 - type: primary
   tag: 프로그래밍의 개념
 - type: success
   tag: 반복되는 일을 반복문으로
---

반복작업이 싫다면 반복문을 사용하면 됩니다.

<!--more-->

### 반복문(Loop Statements)

- 프로그램을 업무에 사용할 때 가장 좋은 점은 반복되는 작업을 매우 빠르게 해결해준다는 점입니다.
- 반복문에는 for 문과 while 문이 있습니다.

### 반복문 활용 사례

- for 문은 list 안에 있는 값들을 차례대로 사용하여 반복문을 실행합니다.
- 예를 들어 list에 숫자들이 들어있다면, 그 숫자들을 차례대로 대입해줍니다.

```python
list_values = [1,2,3,4,5,6,7,8,9]
for i in list_values:
  print("반복문이 ", i,"번째 실행되었습니다.")
```

- for 문은 in 다음에 위치한 변수의 값이 for 문 다음에 오는 변수에 차례로 대입되도록 해줍니다.
- 반복문이지만, 변수의 값이 변하는 것을 이용해서 다양한 작업을 할 수 있습니다.

```python
nation_list = ['USA', 'UK', 'France', 'China', 'Indo', 'Korea']
city_list = ['LA', 'London', 'Paris', 'Shanghai', 'Mumbai', 'Busan']
num_list = [3,2,1,4,5,6]

for i in num_list:
  print(city_list[i-1], "는 ", nation_list[i-1], "에 속한 도시입니다.")  
```
- while 문은 for 문과는 약간 다른 형태의 반복문입니다.
- while 다음에 오는 조건이 참이면 끝나지 않고 반복해서 실행됩니다.

```python
a = 1
while a < 5:
  print(a)
  a = a+1
```

- continue와 break는 반복문을 사용할 때 자주 사용하는 명령어입니다.
- break는 반복문을 완전히 빠져나오고, continue는 반복문을 1회만 건너뜁니다.

```python
num_list = [1,2,3,4,5,6,7,8,9]
for i in num_list:
  if i == 3:
    continue
  if i == 7:
    break
  print(i)
```

### 반복문의 의미

- 반복문이지만, 모든 것이 완전히 동일한 상태에서 반복하는 경우는 거의 없습니다. 변수의 값이 약간씩 달라지면서 우리가 원하는 작업을 할 수 있게 됩니다.
- 만약 우리가 하는 일의 성격이 반복문과 비슷하다면 컴퓨터도 그 일을 할 수 있을 가능성이 높습니다.
  - 매번 비슷한 보고서를 쓰면서 통계만 최신의 통계로 바꾸는 일, 항상 똑같은 신청서를 매뉴얼에 따라 처리하는 업무가 바로 그렇습니다.
- 반복문으로 할 수 있는 일은 컴퓨터가 하도록 하고, 사람은 보다 창의적이고 새로운 문제를 해결하기 위해 노력해야 합니다.

위 프로그램들을 실행해보려면 아래 파일을 [Google Colab](https://colab.research.google.com){:target='_blank'} 사이트에서 불러오면 됩니다.

[Python_Basic_Loop.ipynb]({{ site.url }}/assets/reference/Python_Basic_Loop.ipynb)
