# 모델의 평가지표 

- 정확도 : 생성한 모델이 다른 상황에 대하여 얼마나 잘 맞는가? 
- Precision : 정밀도 - 특정 주제에 대해서 판단한 것 중에 얼마나 많이 맞았는지에 대한 지표  
- Recall : 재현율 - 실제 정답지인 경우 얼마나 잘 맞추었는지에 대한 지표 
- Threshold : 임계값 - 임계값을 낮춘다면 대부분의 경우가 정답으로 분류되기 때문에 Recal은 올라가지만 Precision은 떨어지게 됩니다. 반대로 임계값을 높인다면 Precision은 올라가겠지만, Recall 값은 떵어지게 됩니다. 둘 사이의 관계는 임계값에 따라서 trade-off의 관계를 보여주게 됩니다. 따라서 각각의 수치를 따로 판단하여 좋은 결과를 기대하기 어렵습니다. 두 개의 수치를 모두 사용하여 모델을 평가해야 좋은 성능을 낼 수 있게 됩니다. 


# Performance Metrics 

- BLEU (BiLingual evaluation understudy)
  - 주로 기계 번역 품질을 평가하기 위해 사용되며, LLM이 출력한 번역 결과와 레퍼런스 번역(대체로 사람이 직접 번역한 문장)이 얼마나 일치하는지를 평가하는 지표이다. BLEU Score가 높을수록 모델이 출력이 레퍼런스 번역과 유사한 정도가 높으므로 생성 품질이 더 좋다는 것을 의미한다. 하지만 BLEU Score는 단어의 표면적 일치 여부만 보기 때문에, 실제 번역의 의미나 문맥을 잘 반영하지 못한다는 한계가 있다.
- ROUGE (Recall-Oriented Understudy for Gisting Evaluation)
  - 주로 텍스트 요약을 평가할 때 사용되며, LLM이 출력한 요약 결과가 레퍼런스 요약(대체로 사람이 직접 요약한 문장)의 정보를 얼마나 충실히 반영하는지를 평가하는 지표이다. ROUGE Score가 높을수록 요약 결과가 레퍼런스 요약의 중요한 키워드를 잘 반영한다고 볼 수 있지만, BLEU Score와 마찬가지로 이 지표는 LLM 출력의 의미나 문맥을 잘 반영하지 못한다는 한계가 있다. 
- Perplexity
  - LLM이 텍스트의 샘플을 예측할 때 얼마나 잘 예측하는지를 측정하는 지표이다. 직관적으로는 LLM이 예측을 할 때 얼마나 혼동을 겪는지를 측정하는 것이다. Perplexity는 모델이 텍스트의 흐름을 얼마나 잘 따라가고 이해하는지를 정량적으로 측정하는 좋은 방법이지만 전체적인 텍스트의 질적인 측면은 평가하지 못한다는 한계가 있다.
- METEOR 
  - BLEU의 문제점 
    - BLEU Score 는 'recall' 보다 'precision'에 가까운 성격을 지닌다. BLEU Score 를 구할 땐, 예측값(prediction)이 정답(reference)에 포함되었는지 확인한다. 하지만 반대로, 모든 정답이 예측값에 반영되었는지를 묻지 않는다. 
    - BLEU Score 는 의미적 유사도를 반영하지 못한다. 즉, 완전히 정답과 같아야만(Exact Match) 점수를 준다. 예컨대, '노랗다'와 '누렇다'가 유사하다는 걸 전혀 모른다. 실제로 BLEU Score 를 구해보면은 '하늘이 노랗다.'가 정답이면, '하늘이 누렇다.'와 '하늘이 파랗다.' 모두 틀렸다고 본다.
    - words of cluster 를 잘 잡아내지 못한다. 보통 good match 인 경우, '정답으로 구성된 words of cluster' 와 '예측값으로 구성된 words of cluster'이 매우 근접하다고 한다. 근데, BLEU Score 는 그렇지 못하다.
  - Meteor Score는 Precision 뿐만 아니라 Recall을 반영한 지표이다.   

# Benchmarks 


# Human Evaluation 

# Model-based Evaluation 

# Evaluation Frameowork 


# 출처

> [가디의 tech 스터디:티스토리](https://gagadi.tistory.com/58)
> [모델 평가](https://cnu-jinseop.tistory.com/177)
> https://github.com/confident-ai/deepeval   