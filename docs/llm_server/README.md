
```python
from flask import Flask, jsonify
import whisper
from transformers import AutoTokenizer, AutoModelForCausalLM, pipeline

app = Flask(__name__)

# Whisper 로드
whisper_model = whisper.load_model('small')

# SLLM 로드 (예: TinyLlama)
tokenizer = AutoTokenizer.from_pretrained('TinyLlama/TinyLlama-1.1B-Chat-v1.0')
llm = AutoModelForCausalLM.from_pretrained('TinyLlama/TinyLlama-1.1B-Chat-v1.0')
llm_pipe = pipeline('text-generation', model=llm, tokenizer=tokenizer)


# 오디오 처리 함수
@app.route('/process_audio', methods=['GET'])
def process_audio():
    # 1. 오디오 파일 가상 녹음 (테스트용)
    audio_path = 'sample.wav'  # 실제로는 마이크로 입력된 파일을 사용

    # 2. Whisper STT
    stt_result = whisper_model.transcribe(audio_path, fp16=False, language='ko')
    raw_text = stt_result['text']

    # 3. SLLM으로 문장 정리
    prompt = f"다음 문장을 공손하고 이해하기 쉽게 정리해줘: {raw_text}"
    llm_result = llm_pipe(prompt, max_length=100, temperature=0.5)
    clean_text = llm_result[0]['generated_text'].split(':')[-1].strip()

    return jsonify({'raw_text': raw_text, 'clean_text': clean_text})


if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0', port=5000)
```


```python 
from flask import Flask, jsonify
import whisper
from transformers import AutoTokenizer, AutoModelForCausalLM, pipeline

app = Flask(__name__)

# Whisper 로드
whisper_model = whisper.load_model('small')

# SLLM 로드 (예: TinyLlama)
tokenizer = AutoTokenizer.from_pretrained('TinyLlama/TinyLlama-1.1B-Chat-v1.0')
llm = AutoModelForCausalLM.from_pretrained('TinyLlama/TinyLlama-1.1B-Chat-v1.0')
llm_pipe = pipeline('text-generation', model=llm, tokenizer=tokenizer)


# 오디오 처리 함수
@app.route('/process_audio', methods=['GET'])
def process_audio():
    # 1. 오디오 파일 가상 녹음 (테스트용)
    audio_path = 'sample.wav'  # 실제로는 마이크로 입력된 파일을 사용

    # 2. Whisper STT
    stt_result = whisper_model.transcribe(audio_path, fp16=False, language='ko')
    raw_text = stt_result['text']

    # 3. SLLM으로 문장 정리
    prompt = f"다음 문장을 공손하고 이해하기 쉽게 정리해줘: {raw_text}"
    llm_result = llm_pipe(prompt, max_length=100, temperature=0.5)
    clean_text = llm_result[0]['generated_text'].split(':')[-1].strip()

    return jsonify({'raw_text': raw_text, 'clean_text': clean_text})


if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0', port=5000)
```