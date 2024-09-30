# 2024년 9월 27일 금요일 / AI Conference의 내용 

## Embodied AI = 로봇 + AI

- 잔디깍기
- 청소로봇
- 배달로봇
- 경비로봇
- 농기계
- 등등 

> [좋은 예시 기업 - 긴트](http://www.gintlab.com/)

## 파운데이션 모델 

- [파운데이션 모델의 정의](https://aws.amazon.com/ko/what-is/foundation-models/)
  - 고객 지원
  - 언어 번역
  - 콘텐츠 생성
  - 카피라이팅
  - 이미지 분류
  - 고해상도 이미지 생성 및 편집
  - 문서 추출
  - 로보틱스
  - 의료 서비스
  - 자율 주행 차량 

- 생성형 AI 시대가 다가 아닌 파운데이션 모델로 확장되는 시대
  - 공장내 부품 조림을 대체하는 [Figure AI](https://www.figure.ai/)
  - AI를 통해 제작비 0원, 3일 만에 상업용 영화를 완성


## On-Device Conversation AI

- STT - LLM - TTS : Zero Latency로 구성하는 것이 현재 중요한 Challenge가 될 것이다. 

## On-Device AI 

- Edge Device 에서의 LLM 활용 
  - Cloud LLM와 Edge Device 내의 Local LLM의 Hybrid로 구성된 서비스 제공 
- SLLM 의 커버가 가능한 범위가 어디 까지인가?
- 가전제품 안애 On-Device AI를 넣는 것

## On-Premise LLM 

- 기업형 OnPremise 기반의 LLM 서비스를 제공하는 것 
  - 도메인에 특화된 LLM 기반의 데이터 맞춤/제공형 서비스가 확장될 것이다.  
- Nvidia A100 두 장을 이용해서 라마 3.1이 잘 동작할 수 있다. 

## 개념적으로 세상을 이해하는 범용 AI (Semantic AI) 

- GPT는 일반적인 답변에는 잘 대답할 수 있지만, 해당 지역, 나라의 실정에 맞는 답변은 정확도가 떨어질 수 밖에 없다. 
  - 풀파인튜닝과 프롬프트 엔지니어링이 적절하게 적용되어야만 원하는 결과에 근접할 수 있다. 
  - RAG도 같이 사용되어야 하지만, RAG 이전에 모델 자체를 파인튜닝하는 것이 더 중요하다. 
- Fine Tunning 없이 Prompt Engineering 으로 도메인 확장 
- 도메인 기반 학습을 통해서 Agent LLM을 확장할 수 있는 구조로 만들어져야함


> [Open AI의 ChatGPT를 Fine-Tunning 하기](https://wikidocs.net/200282)   
> [Llama Fine Tuning](https://www.llama.com/docs/how-to-guides/fine-tuning/)

