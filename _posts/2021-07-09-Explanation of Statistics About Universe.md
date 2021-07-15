---
title: "통계가 설명하는 세상"
date: 2021-07-09T22:00:00
---

# 통계가 설명하는 세상
보통 처음에 확률을 배울때, 동전 던지기 과제를 통해 배운다.
동전 던지기 과제에서 앞면이 나올 확률은 0.5이고 뒷면이 나올 확률은 0.5이다.

앞면 혹은 뒷면이 나오지 않은 상태에서 앞면 혹은 뒷면이 나오는 상태로 이동하는 것은 무작위적으로 결정된다.
다시 말해서, 한 상태에서 다른 상태로의 이동이 인과적으로 발생하는 것이 아니라 무작위적으로 발생한다.

통계학은 이러한 무작위성을 다루는 학문이다.

## 인과관계
인과관계는 한 상태에서 다른 상태로의 이동이 필연적인 조건을 가지고 발생한다.
예를 들어, 괴로운 상태에서 행복한 상태로의 이동이 “돈”이라는 조건을 통해 발생한다고 했을때, 이는 인과관계이다.
반면, 확률은 인과관계를 다루지 않는다.
예를 들어, 괴로운 상태에서 행복한 상태로의 이동이 무작위적으로 일어난다.(행복의 정도가 무작위적으로 바뀜)
하지만 통계도 마찬가지로 어떤 상태에서 다른 상태로의 이동의 관한 “관계”를 다루고 싶을 것이다.
왜냐하면 우리는 복잡한 세상을 단순화하고 구조화시키고자 하는 욕망이 있기 때문이다.
그렇기 때문에 통계는 상관관계를 다룬다.

## 상관관계
상관관계는 한쌍의 변수(X1, X2)가 선형적으로 관련된 정도를 나타낸다.
예를 들어 (행복, 돈)이 한 쌍의 변수라고 한다면 
과거에서 지금까지의 행복과 평균적인 행복의 정도의 차이 * 과거에서 지금까지의 벌이와 평균적인 벌이의 차이를 계산한다.

(1월의 행복의 정도, 2월의 행복의 정도… - 평균적인 행복의 정도) * (1,2,3,4…월의 각 벌이 - 평균적인 월 벌이)
	
이렇게 해서 상관관계를 계산하는데, 만약 계산결과가 0보다 크게 되면(양수이면) 행복과 돈은 양의 상관관계를 갖는다.
이 의미는 다음과 같다. "돈이 많아질수록 더욱 행복해진다"
만약 음의 상관관계를 갖게 되면? "돈이 적어질수록 더욱 행복해진다"

## 정리
	
정리하자면 다음과 같다.
인과관계는 행복과 돈을 인과적으로 표현한다.
ex) 언어적으로 표현하면 다음과 같다. 돈이 있어야 행복하다.

상관관계는 돈과 행복을 상관적으로 표현한다.
ex) 언어적으로 표현하면 다음과 같다. 돈이 많을수록 행복하다.

결론적으로 확률에 기반반 분석은 인과적인 측면이 제거된 상관관계에 기반한 분석이다.