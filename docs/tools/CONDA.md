# VLLM on MacOS 

### Step 

- [Anaconda Site](https://www.anaconda.com/) 접근하여 본인의 OS 맞는 설치버전 다운로드하기 
- Conda 최신 버전 업그레이드 

```shell 
conda update -n base -c defaults conda
```

- Conda 버전 확인 

```shell 
conda --version
```

- Conda 환경 구성 

```shell
conda create -n llm_env python=3.12

# To activate this environment, use
#     $ conda activate llm_env
# To deactivate an active environment, use
#     $ conda deactivate
```

- Conda 환경 Activate 

```shell 
conda activate llm_env
```

- vLLM 설치 

```shell 
pip install vllm
```


> [vLLM Installation](https://docs.vllm.ai/en/stable/getting_started/installation.html)