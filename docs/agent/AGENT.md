# Agent 

Agent는 LLM의 판단이 시스템에 반영되는 것   

Agent는 제품의 관점에서는 비서와 같은 역할을 하는 것인데, 어떻게 정의되는 것이 좋은 것인지!?

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


# 언제 사용하면 좋을까? 

작업과 입력범위에 따라서 달라질 것이다.   

- 사용자에게 얼마나 입력을 받아야 하는지에 따라서 
  - 워크플로우
    - 작업과 입력 범위가 모두 좁을 때 적합합니다.  
  - 에이전트 with 시스템 프롬프트 
    - 입력 범위가 넓고 작업 범위가 좁을 때 유용합니다. 
    - 시스템 프롬프트에 의해서 작업 단계를 정의 한다. 
  - 에이전트 with 계획 
    - 작업 범위가 넓을 때 필요합니다. 

# LLM 에이전트의 구성 요소 

## CoALA : 메모리 + 행동 + 의사결정 

> [LLM 에이전트의 구성 요소 출처](https://lilianweng.github.io/posts/2023-06-23-agent/)

### 장기 기억을 세 가지로 구분 

- Procedural 
  - 작업 흐름
- Semantic 
  - 지식/사실 
- Episodic 
  - 대화 내용 

> [Cognitive Architecture For Launguage Agents](https://arxiv.org/abs/2309.02427)

## Google 

- 모델 + 도구 + 오케스트레이션 레이어 

> [Agent 출처](https://www.kaggle.com/whitepaper-agents)

## Antropic, OpenAI, LangGraph 

- System Prompt + Tools  

> [Agent 출처](https://www.anthropic.com/research/building-effective-agents)

## Hugging Face - SmolAgent 

- Code 생성
  - 코드 작성 능력 
  - 범용성 
  - 조합 가능 
  - 결과/데이터 활용 용이 
  
# 세부 구성 요소 

## LLM 

- 프롬프트 
  - 입력의 다양성 
  - In Context Learning
  - 입력에 따른 품질의 다양성
- LLM 
- 생성 결과 
  - 결과의 다양성 
  - 시스템 통합에 어려운 점이 잇음 

## Structured Output (+ Tool use )

- 특정한 출력 형식에 맞추도록 
- 제공한 Tool Schema에 맞추도록 

## Tools 

- 외부 정보 추가 ( Grounding )
- LLM이 잘 못하는 영역 지우너 (계산, 정확성이 요구되는 작업)

## LLM의 추론 능력 

- https://openai.com/index/learning-to-reason-with-llms/ 

## Open Model 실험 By Hugging Face 

Llama 3.2 1b 모델로 Llama 3.2 8b 모델을 넘어설 정도로 성능이 올라갔다고 하는 실험이 존재함. 

- https://huggingface.co/spaces/HuggingFaceH4/blogpost-scaling-test-time-compute


## Memory 기본 구분 

- 기본 구분 
  - 단기 기억 
  - 장기 기억 
- 성격에 따른 구분 
- 중요도에 따른 구분 
  - MemGPT 
    - 프롬프트에 포함된 CoreMemory  


## Orchestration 

- Planning 
- Workflow(Router)
- Agent(Loop, Cycle)
- HandOff(Multi Agent)
  - 한 에이전트에서 다른 에이전트로 흐름을 넘기는 동작 


# LLM 에이전트 프레임워크 

## GUI

- Flowise 
- Langflow 
- Dify 

## Code

- Langraph
- Llamaindex Workflows 
- Crew AI 
- Pydantic AI
- AutoGen 




# 출처 

> https://www.youtube.com/watch?v=zb3v45ik9KI 