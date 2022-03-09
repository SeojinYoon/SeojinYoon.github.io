---
title: "해마체 연구, behaviour"
date: 2022-01-20T19:18:00
---

이번 포스팅은 기억 연구에 관한 실험 설계 방법과 행동 분석 결과를 다뤄보고자 합니다.

# Reference

다음 그림은 이 연구를 시작할 떄 주요하게 참고했던 논문입니다. 이 논문을 간략히 설명하자면, Motor Sequence Task를 학습할 때 각 Trial마다 쉬는 시간을 삽입해주면 빠르게 motor sequence를 배운다는 내용입니다. 이를 fMRI와 DWI를 통해 보았더니 Rest 상태에서 hippocampus와 precunues 쪽에서의 발견되었다는 내용입니다.(*fMRI를 통해서는 functional change를 볼 수 있고 DWI를 통해서는 structural change를 볼 수 있습니다) Jacobacci, Florencia & Armony, Jorge & Yeffal, Abraham & Lerner, Gonzalo & Amaro, Edson & Jovicich, Jorge & Doyon, Julien & Della-Maggiore, Valeria. (2020). Rapid hippocampal plasticity supports motor sequence learning. Proceedings of the National Academy of Sciences. 117. 10.1073/pnas.2009576117. 

![alt text]({{ "/assets/2022-01-20-behaviour/Reference.png" | absolute_url }})

# Experiment design

저의 실험 디자인도 이 논문을 기반으로 피험자가 Motor sequence task를 하게 하였으며, 중간 중간에 쉬는 시간을 배치하였습니다. 
한 Trial은 Sequence를 수행하는 시간 10초와 쉬는 시간 20초로 구성하였습니다. 시퀀스를 총 4개 이용하였는데, 저의 실험은 decoding을 주요한 분석 기법으로 사용하고자 하였기 때문에 이전 연구와 비교하여 더 많은 시퀀스를 이용하였습니다. 또한 이로 인해 피험자가 더 느리게 Motor sequence를 학습하도록 유도하였습니다. 

Decoding analysis를 주기법으로 하고자 하였기 때문에, 최대한 많은 데이터가 필요하였습니다. 이로 인해 Trial의 개수가 많아졌습니다. 한개의 Run당 24개의 Trial을 구성하였으며, 같은 Sequence의 반복횟수는 6으로 설정하였고 피험자가 어떤 시퀀스를 할지 예측하는 것을 방지하기 위해 Pseudo-random하게 시퀀스를 배치하였습니다. 피험자의 예상으로 인한 effect를 줄이고자 한것이죠. 가운데 그림에 맨 위에 표현된 6초의 빨간색 선은 6초 동안에 얻은 fMRI 데이터를 날리기 위해 삽입하였습니다. 그 이유는 혹시라도 있을 Run 시작 시점의 effect를 제거하기 위함입니다.

![alt text]({{ "/assets/2022-01-20-behaviour/exp_design.png" | absolute_url }})

위와 같은 Run을 4번 배치하여 총 48분 24초동안 Task를 수행하도록 하였으며 실험 시작과 끝에 Rest 시간을 두었습니다. 총 실험시간은 64분 24초 입니다.

![alt text]({{ "/assets/2022-01-20-behaviour/exp_run.png" | absolute_url }})

# Individual Analysis

위 논문에서는 Intertap-interval로 피험자가 얼마나 시퀀스를 빨리 누르는지를 측정하였습니다. Intertap-interval이란 피험자가 Sequence를 완성하고자 할 때 버튼을 누르게 되는데 그 중 정확히 누른 버튼을 고려했을 때 버튼 사이의 간격이 어떻게 되는지 측정한 것입니다.  
만약 A-B-C라는 시퀀스가 있는데, A를 0초에 누르고 B를 0.2초에 눌렀고 C를 0.5초에 눌렀으면 A-B 사이의 간격은 0.2초이고 B-C 사이의 간격은 0.3초가 됩니다. 이를 평균하면 A-B-C라는 sequence를 누를때의 intertap-interval은 (0.2 + 0.3) / 2가 되지요. 다음 그림은 한명의 피험자에 대하여 Intertap-interval을 측정한 결과입니다. 각 Point는 하나의 Sequence를 완성할 때, intertap-interval의 평균을 나타낸 것이고, 이러한 포인트는 한 Trial에 여러번 나타날 수 있습니다. 한 Trial에 Sequence를 여러번 맞출 수 있기 때문이죠. 빨간색 포인트는 여러개의 Sequence intertap interval을 평균한 값입니다.

![alt text]({{ "/assets/2022-01-20-behaviour/HP01_mean_intertap_perSeq.png" | absolute_url }})

다음 그림은 한 Sequence를 완성할 때 Speed를 표현한 그래프입니다. intertap-interval에 역수를 취한 값으로, 속력 = 거리 / 시간 이라는 공식을 이용하였습니다. 거리는 1로 두고(한 Sequence를 완성하는 것을 1로 생각한것입니다.) 시간은 intertap-interval로 설정하였습니다.
점점 intertap interval이 내려가긴 하지만 미세하게 내려가는 것을 볼 수 있습니다.

![alt text]({{ "/assets/2022-01-20-behaviour/HP01_mean_speed_perSeq.png" | absolute_url }})

다음 그림은 Run당 몇개의 Sequence를 맞췄는지 표현한 그래프입니다.  
Run이 거듭될 수록 Sequence를 맞추는 개수가 늘어나는 것을 볼 수 있습니다.

![alt text]({{ "/assets/2022-01-20-behaviour/HP01_correct_cnt_perRun.png" | absolute_url }})

다음 그림은 Trial당 몇개의 Sequence를 맞췄는지 표현한 그래프입니다.  
Trial이 거듭 될 수록 Sequence를 맞추는 개수가 늘어났고 최소 2개, 최대 6개까지 맞췄다는 것을 확인할 수 있습니다. 그래프에서 Step 간의 간격이 큰 부분이 있는데 이는 Run이 바뀐 것을 표현한 것입니다. 첫번째 Run에서 최대 5개의 Sequence를 맞췄지만 마지막 Run에서 최대 6개의 Sequence를 맞췄습니다. Motor sequence task performance가 상승한 것으로 볼 수 있으나, 상승의 효과가 미미한 것으로 보입니다. 왜냐하면 피험자가 너무 빨리 학습하여 asymptotic performance에 빨리 도달했기 때문입니다.

![alt text]({{ "/assets/2022-01-20-behaviour/HP01_correct_cnt_perStep.png" | absolute_url }})

다음 그림은 Sequence 별로 intertap interval이 어떻게 변화했는지 표현한 그래프입니다. iteration은 Sequence를 반복한 횟수입니다.  
iteration간의 intertap interval의 차이가 크지 않은 것을 볼 수 있습니다.

![alt text]({{ "/assets/2022-01-20-behaviour/HP01_intertap_cond_iteration.png" | absolute_url }})

# Group Analysis

다음은 Group 분석 결과입니다. 피험자마다 Sequence를 배치하는 방식을 Random하게 하였기 때문에 앞서 그림과 같이 표현할 수 없었습니다. 그러므로 각 시퀀스를 반복했을 때 어떻게 performance가 변화했는지를 그래프로 나타냈습니다. 그 결과, performance의 상승이 미미해보입니다.

![alt text]({{ "/assets/2022-01-20-behaviour/Group_mean_seqs_intertap_interval.png" | absolute_url }})

![alt text]({{ "/assets/2022-01-20-behaviour/Group_mean_seqs_speed.png" | absolute_url }})

# 문제점

현재 이 실험의 문제점은 Motor Sequence learning이 너무 빨리 일어나 sequence가 반복될 수록 performance가 개선되는 효과가 미미하다는 것입니다. 이로 인해 performance 개선의 효과를 brain의 activity 상태와 어떻게 연결시킬지 잘 모르겠네요.




