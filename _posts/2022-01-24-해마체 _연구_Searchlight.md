---
title: "해마체 연구-3, Searchlight"
date: 2022-01-19T19:18:00
---

이번 글은 제가 가지고 있는 운동학습에 대한 가설과 그 분석방법에 대해서 써보고자 합니다.

## Searchlight study in Move

본격적으로 해마체에 대한 연구를 하기에 앞서 Data quality check를 해야합니다. Data quality check를 통해 내가 실험을 잘 했는지를 알 수 있고 내가 작성한 코드가 문제없이 돌아가는지를 알 수 있습니다. Data quality check를 하는 방법은 다양하겠지만, 저는 운동과 관련된 실험을 하고 있으므로 motor cortex가 얼마나 sequence 정보를 잘 표현하고 있는지 보고자 했으며 이를 위해 decoding analysis를 진행하였습니다. 만약 motor cortex가 sequence 정보를 분리하여 표현하고 있다면 decoding analysis를 수행할 때 높은 accuracy가 나타날 것입니다. 이를 위해 움직일 때의 brain activity에 대한 각 sequence의 beta값을 뽑아냈습니다. 어떤 특정한 sequence와 beta값이 쌍을 이루게끔 한 것이죠. 그리고 SVM Linear model을 사용하였고, input은 beta값 label은 sequence로 하여 beta 값이 input으로 들어왔을때 SVM model이 잘 분류를 수행할 수 있는지를 파악했습니다. 그리고 cross-validation을 위하여 K-fold로 decoding accuracy를 구했습니다.

Searchlight는 fMRI study에서 널리 사용되는 방법이며 SVM model을 이용합니다. Searchligth는 어떤 특정한 반경의 가상 구체를 만들어 뇌 전체의 각 부분을 그 가상의 구체로 들여다 보는 방법이죠. 가상의 구체를 렌즈로 하여 뇌를 세밀하게 본다고 생각하면 좋습니다. 이 방법을 통하여 뇌의 어떤 부분이 sequence를 잘 분류할 수 있는지 알 수 있습니다. 보통 운동과 관련된 과제를 수행하면 motor cortex 부위와 소뇌 부분의 decoding acccuracy가 높게 나옵니다. 즉, 그 지역들이 운동과 관련된 condition을 seperable하게 표현한다는 것이죠. 이와 마찬가지로 제가 실험을 통해 얻은 데이터 또한 motor cortex 부위와 소뇌 부분의 decoding accuracy가 높게 나왔습니다. Data quality check가 잘 되었다는 의미이죠. 

이러한 분석을 개인별로 진행할 수도 그룹으로 진행할 수도 있습니다. 만약 그룹별로 이러한 분석을 진행한후, 개인 별로 수행한 결과를 평균하면 individual-difference가 제거 된 결과를 얻게 되겠죠. 저 또한 그룹으로 분석하였으며, 동일한 결과를 얻을 수 있었습니다.

## Searchlight study in Rest

그렇다면 아무런 운동 없이 쉬고 있는 상태에서의 brain activity는 어떻게 될까요? 저의 가설에 의하면, Hippocampus replay가 일어나기 때문에 fMRI 신호 또한 높게 나와야 합니다. Hippocampus replay가 일어나면 Hippocampus 부근에서의 뉴런들이 서로 상호작용을 할 것이고 이는 전기적인 신호를 통해 이루어집니다. 이러한 전기적인 신호가 Hemodynamic response 값의 증가를 유발시킨다는 것입니다. 그러나 Searchlight 분석을 한 결과 해마체 주변에서 decoding이 잘 되는 것 같으면서도 안되는 것 같은 경계에 놓여있었습니다. 제 가설이 맞다고 주장하기에는 조금 민망한 상황인것이죠. 

다음 그림은 lss 분석을 이용하여 각 Trial별로 뽑아낸 rest 상태의 beta값을 가지고 searchlight decoding analysis를 수행한 것입니다. model은 SVM이며 radius는 6을 이용하였습니다. 뽑아낸 decoding accuracy를 이용하여 모든 피험자들에대해 t-test를 수행하였고, Cluser size는 30, p-value는 0.03으로 설정하였을때의 결과는 다음과 같습니다. 여러가지 brain region이 통계적으로 유의미하다라는 결과가 나왔지만 이 결과를 신뢰하기가 어렵습니다. 그 이유는 제가 설정한 p-value 때문이죠. p-value를 0.05 이하의 값을 설정하였지만, fMRI 이미지 분석에서 이는 아주 느슨한 값입니다. 왜냐하면 P-value가 0.05라는 의미는 0.05의 확률로 False positive가 나타나는 것을 허용한다는 의미가 됩니다. 만약 하나라도 false-postivie가 나타난다면 false-positive로 판정하는 multiple-comparision에서는 분석 대상의 수가 많으면 많을수록 false-posivie가 나타나는 확률이 커지게 됩니다. 따라서 아주 많은 분석 대상을 가지는 Whole-brain analysis에는 보통 0.05보다 더 적은 p-value를 사용하여 false-positive voxel을 최대한도로 줄이게 되므로, 0.03라는 값은 아주 느슨한 threshold입니다. 이보다 적은 p-value를 이용하면 반응을 보이는 voxel의 개수가 급격히 떨어져 클러스터가 보이지 않았습니다.


![alt text]({{ "/assets/2022-01-24-해마체_연구_Searchlight/lss_none_rest.png" | absolute_url }})

## Beta값에 대한 의문점

제가 위에서 언급하지 않았지만 제가 GLM을 통해 beta값을 얻은 방식은 LSS 방식이었습니다. LSS 방식이란 Least Square Single의 줄임말로 Single trial에 대한 beta값을 뽑는 방식을 의미합니다.(Mumford JA, Turner BO, Ashby FG, Poldrack RA. Deconvolving BOLD activation in event-related designs for multivoxel pattern classification analyses. Neuroimage. 2012 Feb 1;59(3):2636-43. doi: 10.1016/j.neuroimage.2011.08.076. Epub 2011 Sep 5. PMID: 21924359; PMCID: PMC3251697.) 이 방식은 여러가지 regressor를 함께 사용하는 것이 아닌 하나의 trial에 대한 regressor만 사용하고 나머지는 Nuisance로 처리함으로써 design matrix의 collinearity를 없애는 방법입니다. 만약 collinearity가 높다면 베타값을 구할 때 분산이 매우 커지게 되어 매우 불안정한 Beta값을 얻게 되죠. 자세한 사항은 논문에 언급되어 있습니다.

이러한 방식으로 Single trial에 대한 beta값을 얻을 수 있었기 때문에, 여러가지 trial에 대한 beta값을 input으로 넣어서 decoding analysis를 진행할 수 있었습니다. 그러나 여기서 제가 가진 의문점은 다음과 같습니다. 

** Hippocampus replay는 어느 시점에 많이 일어나는가? **

앞선 연구에 따르면 Hippocampus replay는 early learning일 때 더 자주 일어난다고 합니다.(The Architecture of Human Memory: Insights from Human Single-Neuron Recordings) 그리고 다음 논문은 weakly learn, 즉, 많이 배우지 않았을 때 Hippocampus replay가 더 많이 필어난다고 보고하고 있습니다.(Human hippocampal replay during rest prioritizes weakly learned information and predicts memory performance) 다시 말해서, Hippocampus replay는 도움이 필요한 memory에서 더 많이 일어난다는 이야기입니다. 

만약 Hippocampus replay가 condition마다 다르게 일어난다면, 이러한 현상은 기본적인 LSS로 포착할 수 없을 것입니다. 그래서 제가 생각한 가설은 Hippocampus replay가 어떠한 특정한 행동으로 인해 modulation 된다는 것입니다. 우리는 기억할 만한 것을 기억하고 기억할 필요 없는 것은 기억하지 않습니다. 만약 sequence를 굉장히 빠르게 누른 순간이 있다면 뇌는 그 순간만을 기억하고 나머지는 별로 기억하지 않는다는 뜻입니다. 저는 이를 분석하기 위해 Parametric modulation이라는 방법을 가지고 Prioritize Hippocampus replay를 관찰하기로 하였습니다. 



