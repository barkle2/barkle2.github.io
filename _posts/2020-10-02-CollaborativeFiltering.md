---
layout: post
title: "알기쉬운 IT 용어: 협업 필터링(Collaborative Filtering)"
date: 2020-10-02 10:00:00 +0930
categories: 
 - IT 이해하기
badges:
 - type: danger
   tag: 너랑 닮은 사람이 바로 너
 - type: success
   tag: 생각보다 훨씬 강력해
---

맞춤형 추천 서비스의 99%는 협업 필터링 방식을 활용한다고 봐도 됩니다. 그만큼 강력합니다.

<!--more-->

### **협업 필터링? 비슷한 사람 추천법!**

- 이 글에서 설명하려는 개념은 **Collaborative Filtering** 입니다.
- 그런데 이 개념을 **"협업 필터링"**이라고 하면 너무 이해하기가 어렵게 느껴집니다.
- 그래서 협업 필터링 대신 **비슷한 사람 추천법** 정도로 이름을 붙여보면 어떨까 합니다.

### **비슷한 사람 추천법의 기본 개념**

- 비슷한 사람 추천법의 접근 방식은 다음과 같습니다.
  - "어딘가 너와 비슷한 사람이 있다" → "네가 아직 보지 못한 상품을 그 사람이 좋아했다" → "그 상품을 너에게 추천한다"
- 간단하지 않습니까? 생각해보면 아주 당연한 이 방법이 요즘 가장 각광받는 추천 알고리즘입니다.

### **영화 추천과정을 알바봅시다**
- 7명의 친구가 있습니다.
  - 친구의 이름은 가람, 나래, 다솜, 라온, 마루, 빛솔, 새롬입니다.
  - 이 중에서 새롬에게 영화를 추천하려고 합니다.
- 먼저 7명의 친구에게 이미 관람한 영화의 선호도를 조사합니다.
  - 1:매우 싫음, 2:싫음, 3:보통, 4:좋음, 5:매우 좋음, 빈칸: 아직 보지않은 영화

|영화|가람|나래|다솜|라온|마루|빛솔|새롬|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|명량|2|4|5|4|2|5|4|
|극한직업||3||5|2|2||
|신과함께-죄와벌|5|3|2|4||1|2|
|국제시장|2|4|2|1|3|5||
|어벤저스-엔드게임|3|5|4|2|3|||
|겨울왕국2|4||4||2|4|5|
|베테랑||1|1|1|2|2||
|아바타|2|5|2||5|1|1|

- 유사도를 구하기 위해서 모든 점수에서 3점씩을 빼겠습니다.
  - 3점을 빼면 싫은 영화는 마이너스 값을 가지고, 보통 영화는 0점, 좋은 영화는 플러스 값을 가지게 됩니다.

|영화|가람|나래|다솜|라온|마루|빛솔|새롬|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|명량|-1|1|2|1|-1|2|1
|극한직업||0||2|-1|-1||
|신과함께-죄와벌|2|0|-1|1||-2|-1|
|국제시장|-1|1|-1|-2|0|2||
|어벤저스-엔드게임|0|2|1|-1|0|||
|겨울왕국2|1||1||-1|1|2|
|베테랑||-2|-2|-2|-1|-1||
|아바타|-1|2|-1||2|-2|-2|

- 그리고 새롬이와 친구들이 얼마나 비슷한지를 판단해야 합니다.
  - 얼마나 비슷한지는 두 사람이 공통으로 관람한 영화에 점수를 얼마나 비슷하게 주었는지로 판단합니다.
  - 판단 기준으로 코사인 유사도(cosine similarity)라는 지표를 사용하는데, 이 지표는 두 사람이 비슷한 값을 가질수록 1에 가까운 값을 가지고, 서로 반대되는 값을 가질수록 -1에 가까운 값을 가집니다.
- 친구들 사이의 코사인 유사도를 계산해보면 다음과 같습니다.

|유사도|가람|나래|다솜|라온|마루|빛솔|새롬|
|새롬|0.120|-0.548|0.837|0|-0.953|0.877|1|

- 이 표를 조금 더 살펴보겠습니다.
  - 새롬이와의 유사도가 가장 높은 친구는 빛솔이입니다.
  - 빛솔이와 새롬이의 유사도가 높은 이유는 함께 본 영화에 비슷한 점수를 주었기 때문입니다.
    - 각각 명량에 2점/1점, 신과함께-죄와벌에 -2점/-1점, 겨울왕국2에 1점/2점, 아바타에 -2점/-2점을 주었습니다. 영화취향이 꽤나 비슷하고, 그것이 유사도에 반영되었습니다.
  - 새롬이와의 유사도가 가장 낮은 친구는 마루입니다.
  - 마루와 새롬이의 유사도가 낮은 이유는 함께 본 영화에 반대의 점수를 주었기 때문입니다.
    - 각각 명량에 -1점/1점, 겨울왕국에 -1점/2점, 아바타에 2점/-2점을 주었습니다. 마루와 새롬이는 영화를 같이 보러가면 안되겠네요...
  - 새롬이와의 유사도가 0인 친구도 있습니다. 바로 라온입니다.
    - 라온이는 새롬이와 명량과 신과함께-죄와벌을 함께 보았는데, 라온이는 둘 다 1점을 주었고, 새롬이는 각각 1점과 -1점을 주었습니다.
    - 즉, 두 사람의 영화취향은 서로 상관관계가 없다고 볼 수 있습니다.

- 이제 마지막 단계입니다. 각 영화별로 추천값을 구하면 됩니다.
  - 영화에 대한 추천값은 (친구의 점수)×(친구의 유사도) 입니다. 
  - 새롬이가 아직 보지않은 영화는 극한직업, 국제시장, 어벤저스-엔드게임, 베테랑 입니다.

|영화|가람|나래|다솜|라온|마루|빛솔|합계|
|극한직업|0|0|0|0|0.953|-0.877|0.076|
|국제시장|-0.120|-0.548|-0.837|0|0|1.754|0.250|
|어벤저스-엔드게임|0|-1.095|0.837|0|0|0|-0.259|
|베테랑|0|1.095|-1.673|0|0.953|-0.877|-0.502|

- 새롬이에게 추천할 영화는 합계점수가 가장 높은 국제시장입니다.
  - 새롬이와 성향이 비슷한 빛솔이가 높은 점수를 준 것이 큰 영향을 미쳤습니다.
  - 새롬이와의 유사도가 0인 라온이는 영화추천에 영향을 주지 못합니다. 영화추천에 영향을 주려면 성향이 비슷하거나, 반대여야 합니다.

- 7명으로 간단히 사례를 만들어보았습니다만, 실제 추천 시스템은 몇백만명 단위의 추천을 하기 때문에 이것보다는 훨씬 더 복잡한 형태를 띄게 됩니다.
  - 그래도 이 내용을 이해한다면 협업 필터링, 비슷한 사람 추천하기의 기본적인 개념은 파악했다고 보실 수 있습니다.