# Agent 

## LLM Agent 

- 합의된 기준은 없음
- 회사마다, 사람마다 정의가 다름  
- 현재 조금씩 그 개념과 정의가 Tech 기업 사이에서 논의되고 있음

### Builing effective agents 

- 워크 플로우 : 사전에 정의한 코드 흐름에 따라 LLM과 도구가 사용되는 시스템 
  - Workflow 
    - Prompt Chaining 
  - Routing 
    - LLM Call Router
  - Parellization 
    - 병렬적으로 수행함 
- 에이전트 : LLM이 직접 흐름이나 도구 사용 여부를 결정하고 어떻게 목표를 달성할지 관리하는 시스템 
  - 목표를 달성하기 위한 흐름을 LLM이 결정 


### OpenAI Swarm 

Agent : 일련의 명령(지시) + 명령을 완료하기 위한 도구 -> 시스템 프롬프트 + 도구 

### Google 

Agent : 세상을 관찰하고 자신이 가진 도구를 사용하여 목표를 달성하려고 시도하는 애플리케이션

### Langchain 

Agent : 애플리케이션의 작업 흐름을 선택할 때 LLM을 활용하는 시스템 

### Hugging Face 


> https://huggingface.co/blog/smolagents

