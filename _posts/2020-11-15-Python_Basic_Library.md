---
layout: post
title: "[Python] 기초 개념: 모듈, 라이브러리"
date: 2020-11-15 11:00:00 +0930
categories: 
 - 컴퓨터 프로그래밍
badges:
 - type: primary
   tag: 프로그래밍의 개념
 - type: success
   tag: 변수, 함수 < 클래스 < 모듈 < 라이브러리
---

변수, 함수, 클래스를 한데 모으면 모듈이 되고, 비슷한 모듈을 모으면 라이브러리가 됩니다.

<!--more-->

### 모듈(Module), 라이브러리(Library)

- 모듈은 변수·함수·클래스 등이 담겨있는 파일입니다.
- 라이브러리는 비슷한 모듈을 모아놓은 것입니다.
  - 모듈이 1개인 라이브러리로 있을 수 있으니, 모듈과 라이브러리는 구분없이 사용되기도 합니다.
- 서로 관계없는 변수·함수·클래스를 모아놓으면 쓸모가 없기 때문에, 비슷한 필요한 변수·함수·클래스를 모아서 라이브러리를 만듭니다.
- 수학 계산을 위해 Numpy 라이브러리를 만들고, 데이터 분석을 위해 Pandas라는 라이브러리를 만들고, 인공지능 학습을 위해 Tensorflow라는 라이브러리를 만드는 식입니다.

### 라이브러리의 장점

- 라이브러리가 좋은 이유는 다른 훌륭한 프로그래머들이 만든 라이브러리를 자유롭게 사용할 수 있기 때문입니다.
- 천재 프로그래머가 만든 라이브러리를 사용하면 적은 노력으로 훌륭한 프로그램을 만들 수 있습니다.
- 파이썬에서 자주 사용되는 라이브러리에는 [tensorflow]](https://www.tensorflow.org/?hl=ko){:target='_blank'}, [beautifulsoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/){:target='_blank'}, [selenium](https://www.selenium.dev/){:target='_blank'}, [numpy](https://numpy.org/){:target='_blank'}, [pandas](https://pandas.pydata.org/){:target='_blank'}, [pyQt](https://www.riverbankcomputing.com/static/Docs/PyQt4/){:target='_blank'}, [plotly](https://plotly.com/python/){:target='_blank'}, [seaborn](https://seaborn.pydata.org/){:target='_blank'}, [matplotLib](https://matplotlib.org/){:target='_blank'}, [openpyxl](https://openpyxl.readthedocs.io/en/stable/){:target='_blank'}, [opencv](https://opencv.org/){:target='_blank'} 등이 있습니다.
  - 유명한 라이브러리의 경우 별도로 소개하는 책이 나오기도 합니다.
  - 라이브러리의 사용법을 알기 위해서는 해당 라이브러리의 Document를 읽는 것이 가장 좋습니다.(저자 직강!)
- 라이브러리는 누구나 무료로 사용할 수 있습니다.
  - 왜인지 모르겠지만, 힘들게 라이브러리를 만드는 사람 중 누구도 라이브러리를 유료로 팔아야겠다는 생각을 하지 않습니다.