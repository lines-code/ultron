# Llama 3.1 의 파라미터 개수 

- 405B 
  - Meta에 따르면 공개적으로 사용 가능한 세계 최대의 [대규모 언어 모델(LLM)](https://aws.amazon.com/what-is/large-language-model/)입니다. 이 모델은 AI의 새로운 표준을 제시하며 엔터프라이즈급 애플리케이션 및 연구 개발(R&D)에 적합합니다. 모델의 출력을 사용하여 소규모 Llama 모델 및 [모델 증류](https://en.wikipedia.org/wiki/Knowledge_distillation)를 개선하여 405B 모델에서 더 작은 규모의 모델로 지식을 전달할 수 있는 [합성 데이터 생성](https://aws.amazon.com/what-is/synthetic-data/)과 같은 태스크에 이상적입니다. 이 모델은 일반 지식, 롱폼(long-form) 텍스트 생성, 다국어 번역, 기계 번역, 코딩, 수학, 도구 사용, 향상된 컨텍스트 이해, 고급 추론 및 의사 결정에서 성능을 탁월합니다. 
- 70B 
  - 콘텐츠 제작, 대화형 AI, 언어 이해, R&D, 엔터프라이즈 애플리케이션에 적합합니다. 이 모델은 텍스트 요약 및 정확성, 텍스트 분류, 감정 분석 및 뉘앙스 추론, 언어 모델링, 대화 시스템, 코드 생성, 명령 준수에서 성능이 탁월합니다. 
- 8B 
  - 제한된 컴퓨팅 파워 및 리소스에 가장 적합합니다. 이 모델은 텍스트 요약, 텍스트 분류, 감정 분석, 지연 시간이 짧은 추론을 요구하는 언어 번역에서 성능이 탁월합니다  

# 기능 

- Tool use(도구 사용): 사용자가 원하는 여러가지 도구들을 제공합니다. 아래와 같이 어떤 데이터를 분석하고 이를 그래프로 나타내어줍니다. 
- Multi-lingual agents(다국어 에이전트): 영어뿐만 아니라 다른 언어들도 이해할 수 있는 Multi-lingual agents 기능이 있습니다. 아래와 같이 스페인어로 번역도 잘하는 것을 확인할 수 있습니다
- Complex reasoning(복잡한 추론): 사람이 잘 하는 복잡한 추론 문제도 풀 수 있습니다. 다음과 같이 휴가 때 입을 옷에 대해 문의를 하면, 이를 분석해서 최적의 답을 찾아줍니다.
- Coding assistants(코딩 조수): 많은 시간이 들어가는 코딩을 요구사항만 명확히 프롬프트로 전달해주면, 코드를 작성해 줍니다.  

# 성능 

Llama 3.1에 대한 성능은 다음과 같습니다. 먼저 Llama 3.1 405B 모델의 경우 아래 그래프와 같이 여러가지 성능지표에서, 경쟁 모델 Nemotron 4, GPT-4, GPT-4o(Omni), Claude 3.5 Sonnet들 보다 우수한 성능을 보였습니다. Llama 3.1는 특히 8B와 70B와 같은 작은 모델에서 두각을 드러냈는데, 아래와 같이 비슷한 크기의 Gemma 2, Mistral, Mixtral, GPT 3.5 모델에 비해 성능이 월등히 높은 것을 확인할 수 있습니다. 

# Llama SetUp

- https://github.com/ggerganov/llama.cpp 

```
git clone https://github.com/ggerganov/llama.cpp.git
cd llama.cpp
```

```
mkdir build
cd build
cmake ..
make
```

```
./main -m models/llama-11.9B.bin -p "your prompt here"
```

```
./main -m models/llama-11.9B.bin -p "your prompt here" -t
```

# Python based for llama.cpp 

- https://github.com/abetlen/llama-cpp-python 


```python
from llama_cpp import Llama

llm = Llama(
      model_path="./models/7B/llama-model.gguf",
      # n_gpu_layers=-1, # Uncomment to use GPU acceleration
      # seed=1337, # Uncomment to set a specific seed
      # n_ctx=2048, # Uncomment to increase the context window
)
output = llm(
      "Q: Name the planets in the solar system? A: ", # Prompt
      max_tokens=32, # Generate up to 32 tokens, set to None to generate up to the end of the context window
      stop=["Q:", "\n"], # Stop generating just before the model would generate a new question
      echo=True # Echo the prompt back in the output
) # Generate a completion, can also call create_completion
print(output)
```


# 각 LLM별 비교군 

![image](https://github.com/user-attachments/assets/27e28e06-2668-490b-977b-d13fdbf509ad)

# Cuda 설치를 위한 NVIDIA 설치 가이드 

만약 GPU를 사용하고자 한다면 CUDA가 설치되어 있어야 합니다. NVIDIA GPU가 있다면 다음 명령으로 CUDA를 설치합니다.

- CUDA 및 cuBLAS 설치

```
sudo apt install nvidia-cuda-toolkit
```

- https://docs.nvidia.com/cuda/cuda-installation-guide-linux/  

# 참조 

> https://brunch.co.kr/@sparta/92     
> https://chatgpt.com/share/6775ffc4-5888-8005-988a-3734bbaf466d    
> https://chatgpt.com/share/6775ffe0-8a64-8005-8ac9-d25048eeb11b    