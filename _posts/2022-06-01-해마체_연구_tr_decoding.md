---
title: "해마체 연구, TR decoding"
date: 2022-06-01T15:17:00
---

이 포스터는 SVM을 이용하여 fMRI data를 decoding 하였을때의 결과를 보여줍니다. 
fMRI 실험을 할 때의 TR은 2초 였습니다. 즉, 2초마다 brain activity를 기록하였으며, 한 trial은 10초 동안 sequence를 입력하는 부분과 20초 동안 쉬는 부분으로 구성되었습니다. 한 Trial 마다 15개의 fMRI image data가 기록되었습니다.

한 Trial은 4개의 Sequence 중 하나의 Sequence 동작을 수행해야 하였습니다. 따라서 decoding accuracy의 threshold는 0.25 입니다. 데이터 셋은 특정한 TR에 대응하는 데이터를 Trial 마다 습득된 데이터로부터 추출하였습니다. 예를 들어, 한 Trial의 fMRI 데이터 중 관심 대상이 10초에 대응하는 fMRI 데이터만 관심이 있다면, 10초에 대응하는 데이터만 뽑아내었고, 이를 전체 Trial마다 반복하여 총 96개의 데이터를 추출하였습니다. 1개의 Sequence당 24개의 데이터를 가집니다.

추출된 데이터를 가지고 SVM model을 이용하여 decoding 분석을 하였습니다. 만약 특정한 시간에 brain activity가 Sequence를 분류할 수 있는 정보를 많이 포함한다고 가정했을 때, 그 시점의 decoding accuracy가 높을 것입니다.

이러한 분석 방법을 여러개의 ROI 마다 적용하였으며, 모든 시간마다 적용하였습니다.  
또한 모든 피험자의 데이터를 평균화하여 결과를 나타내었습니다.

# Cross validation mean accuracy, ROI 별 분석 결과

이 연구는 총 4번의 Run으로 구성되어 있었기 때문에, cross-validation을 이용하여 하나의 런은 Test set으로 사용하고 나머지 세개의 Run은 Training 데이터로 사용하였으며, cross-validation을 통하여 noise로 인한 효과를 줄였습니다.

0 ~ 10초 구간에 대응되는 하얀색 배경을 가진 부분은 피험자가 움직일 때의 시간을 표현한 것이며, 회색 영역은 피험자가 쉴 때의 시간을 표현한 것입니다.

Hippocampus right rostral의 경우, 4초에 대응하는 데이터에서 decoding accuracy가 조금 높은 것을 볼 수 있었으며, Hippocampus left의 경우 16초에 대응하는 데이터에서 decoding accuracy가 조금 높은 것을 볼 수 있었습니다.

하지만, 전체적으로 decoding accuracy가 높지 않은 것으로 보입니다. 이는 Hippocampus 영역에서 decoding이 잘 되지 않는다는 것을 뜻하며, hippocampus에서는 sequence를 특정하게 표현한다기 보다는 뭉뚱그려서 표현한다고 볼 수 있을것 같습니다.

![alt text]({{ "/assets/2022-06-01-해마체_연구_tr_decoding/Group_tr_hippocampus_acc_mean_accuracy.png" | absolute_url }})

다음은 Hippocampus와 관련된 영역인 entorhinal cortex를 ROI로 삼아 분석한 결과이며, 16초 대에 left entorhinal의 decoding accuracy가 상승한것을 볼 수 있지만, 미미해보입니다.

![alt text]({{ "/assets/2022-06-01-해마체_연구_tr_decoding/Group_tr_entorhinal_acc_mean_accuracy.png" | absolute_url }})

다음은 precentral과 inferior parietal cortex에 대한 결과입니다.  
precentral cortex의 경우 10초대에 큰 decoding accuracy를 보였으며 inferior parietral도 대체적으로 비슷한 결과를 보입니다.  
그 이유는 이 두 영역이 서로 인접한 영역이며, motor area이기 때문입니다.

M1 영역이라고도 부르는 precentral cortex는 논란이 있는 부분입니다. 논란의 주제는 이 영역이 motor learning으로 인하여 brain activity가 바뀌는 영역인지 아니면 움직임 그 자체를 표현하고 있는 부분인지 잘 모르겠다는 것입니다. Diedrichsen 그룹은 이 영역이 learning으로 인하여 바뀌지 않는다고 하였으며 (Berlot, Diedrichsen 2020, A critical re-evaluation of fMRI signatures of motor sequence learning), Hamano는 이 영역이 motor sequence에 대한 engram을 가지고 있으며 brain은 motor sequence를 하기 전에 이 영역에서 sequence에 대한 정보를 찾는 ecphory가 이루어진다고 보고하고 있습니다. (Hamano 2021, The integrative role of the M1 in motor sequence learning) Diedrichsen은 해당 논문에서 motor sequence learning으로 인하여 brain activity가 바뀌는 부분은 parietal lobe 쪽이라고 보고하였습니다.

사실이 어떻든 간에, 이 두 영역이 움직임과 관련된 부분임에는 분명한 듯 합니다.

![alt text]({{ "/assets/2022-06-01-해마체_연구_tr_decoding/Group_tr_precentral_acc_mean_accuracy.png" | absolute_url }})

![alt text]({{ "/assets/2022-06-01-해마체_연구_tr_decoding/Group_tr_inferior_parietal_acc_mean_accuracy.png" | absolute_url }})

다음은 감각과 연관이 있는 postcentral 쪽 결과입니다. 이 영역도 또한 motor movement와 관련이 있는데, 기대했던것과는 달리 decoding accuracy가 크지 않았습니다.

![alt text]({{ "/assets/2022-06-01-해마체_연구_tr_decoding/Group_tr_postcentral_acc_mean_accuracy.png.png" | absolute_url }})

# 첫번째 run을 test set으로 사용하였을 때, ROI 별 분석 결과

이는 첫번째 Run만 test set으로 사용하고, 나머지 Run은 training set으로 사용한것 입니다.  
이러한 분석의 가정은 Hippocampus replay 현상이 early learning stage에서 두드러지게 나타난다는 background에 기반한 것이며, Sequence를 학습한 초기 시점을 주요한 관심 대상으로 삼은 것입니다.

첫번째 run에서의 Hippocampus right rostral 부분의 decoding accuracy가 움직이는 시점에서 크게 나왔습니다.  
또한, entorhinal left 쪽에서는 쉴때 decoding accuracy가 크게 나왔습니다.

![alt text]({{ "/assets/2022-06-01-해마체_연구_tr_decoding/Group_tr_hippocampus_acc_0.png" | absolute_url }})

![alt text]({{ "/assets/2022-06-01-해마체_연구_tr_decoding/Group_tr_entorhinal_acc_0.png" | absolute_url }})

반면, 움직임과 연관된 영역인 precentral과 inferior parietal 쪽에서의 decoding accuracy는 작았습니다.

![alt text]({{ "/assets/2022-06-01-해마체_연구_tr_decoding/Group_tr_precentral_acc_0.png" | absolute_url }})

![alt text]({{ "/assets/2022-06-01-해마체_연구_tr_decoding/Group_tr_inferior_parietal_acc_0.png" | absolute_url }})

첫번째 Run에서는 post central의 decoding accuracy가 큰듯 보입니다.

![alt text]({{ "/assets/2022-06-01-해마체_연구_tr_decoding/Group_tr_postcentral_acc_0.png.png" | absolute_url }})

# Summary

전체적으로 종합하였을 때, 학습이 진행되어 고착화가 된 경우에 precentral과 inferior parietal 쪽에서의 sequence 표현이 좀 더 고유하게 변하는 것 같으며, early learning stage에서 hippocampus의 sequence 표현이 움직일 때 좀 더 두드러지는 것 같습니다.
다만, 쉴 때의 decoding accuracy가 증가하지 않는 것으로 보아 이를 hippocampal replay의 증거로 생각할 수는 없지만, hippocampus와 관련된 영역인 entorhinal 쪽에서 rest 시에 decoding accuracy가 큰것으로 보아 그 쪽에서 어떤 일이 일어나지 않나 생각 되기도 합니다.


