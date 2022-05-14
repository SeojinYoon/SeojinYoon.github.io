---
title: "해마체 연구, Hippocampal sequential replay"
date: 2022-05-14T13:10:00
---

# Place cell

Hippocampus의 기능 중, memory consolidation이라는 기능이 있습니다. 이는 기억을 다시 불러일으킴으로써 그 기억을 좀 더 공고히 하는 것을 의미합니다. 이에 대한 연구는 주로 쥐를 대상으로 수행되으며 이 연구를 이해하려면 place cell이라는 hippocampus 안에 있는 cell의 역할에 대해 이해할 필요가 있습니다. 앞서 말했듯 Hippocampus 안에는 place cell이 존재합니다. 이 cell은 어떠한 장소에 sensitive한 반응을 보인다고 하여 place cell이라는 이름이 붙었습니다. (O'Keefe 1976) 연구자들은 이 cell 집합의 반응을 통해 쥐가 어떤 경로로 돌아다녔는지 확인할 수 있었습니다. 

다음 그림은 쥐가 미로를 돌아다닐때 place cell들의 반응을 기록한 것입니다. 각기 다른 색상의 점은 다른 종류의 place cell을 의미하며, 쥐가 처음 미로에 들어섰을 때는 분홍색에 대응되는 place cell이 활성화 되고, 그 이후 연초록, 초록색에 대응되는 place cell 순으로 반응합니다. 
이 그림을 통해 알 수 있는 점은 특정한 place cell가 특정한 place를 mapping하고 있다는 것이며, 이러한 mapping들을 통하여 공간을 지도화 한다는 것입니다.

![alt text]({{ "/assets/2022-05-14-해마체_연구_Hippocampal_sequential_replay/Place_cell.png" | absolute_url }})

# Hippocampal Sequential Replay

앞서 말했듯 Hippocampus에 존재하는 place cell들은 공간을 mapping 합니다. 연구자들은 쥐가 돌아다닐때 place cell의 반응을 연구했을 뿐만 아니라, 쥐가 멈춰있을 때의 반응을 연구했습니다. 그런데 신기한 것은 쥐가 멈춰있을 때도 hippocampus place cell의 반응이 관찰되었으며, 이러한 반응은 Sequential한 형태로 나타났다는 것입니다. Sequential한 반응이란 미로를 돌아다닐 때, 미로의 각 지점에 대응되는 place cell이 순차적으로 반응했듯이, 쉴때도 마찬가지로 순차적으로 반응했다는 것입니다. (Karlsson 2009) 이 데이터를 바탕으로 연구자들은 쥐가 쉬고있을 때 이전에 했던 기억이 재생되어 place cell이 반응한 것이라는 이론을 세웠습니다. 이것이 바로 memory consolidation 이며, 이를 Hippocampal Sequential Replay라고 합니다. 

# Hippocampal Sequential replay, Human memory

Hippocampal sequential replay는 장소에 대한 기억에 대해서만 일어날까요?  
연구자들은 Decision making task를 구성하여 fMRI에서 이를 테스트 해보았습니다. Decision making을 했던 경험이 hippocampus 내에서 다시 재생되는지 확인한 것이죠. (Schuck, 2019)

아래 그림은 이 연구에 대한 분석에 대한 설명을 나타내며, Decision making task를 수행한 후, Rest 상태에서 뇌에 어떠한 일이 발생하는지 MVPA를 통해 분석했습니다. 이 분석을 통해 brain에서 non-spatial 정보에 대해서도 또한 Hippocampal Sequential replay가 발생한다는 것을 통계적으로 보였습니다.

![alt text]({{ "/assets/2022-05-14-해마체_연구_Hippocampal_sequential_replay/Schuck_2019.png" | absolute_url }})

# Sequential replay, Motor

Motor memory에 대해서도 위와 비슷한 연구가 진행되었습니다. (Albouy 2008)

# Summary

Hippocampal sequential replay는 여러 domain에서 관찰되었습니다.

reference:  
https://en.wikipedia.org/wiki/Place_cell  
O'Keefe 1976, Place units in the hippocampus of the freely moveing rat  
Karlsson 2009, Awake replay of remote experiences in the hippocampus  
Schuck 2019, Sequential replay of nonspatial task states in the human hippocampus  
Albouy 2008, Both the Hippocampus and Striatum Are Involved in Consolidation of Motor Sequence Memory  