# 논문을 한글로 번역해주는 오픈 소스 활용해서 논문 공부하기

## 파이썬 지원 

```
Python installed (3.8 <= version <= 3.12)
```

## pip를 통한 설치 

```
pip install pdf2zh
```

## 실제 돌려보기 

### 아티클 다운로드 받기 : [샘플](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://arxiv.org/pdf/2307.06435)

### 다운 받은 파일을 아래와 같이 실행한다. 

- 기본적으로는 구글 Translator를 활용하기 때문에 구글에서 지원하는 언어코드 사용해서 돌릴 수 있음

```
pdf2zh --lang-out=ko  {pdf 파일 경로}
```

### 추가

- 모델을 이용해서 돌리는 것도 가능하고, 
- 본인 방식에 맞춰서 코드를 수정해서 입맞에 맞게 쓰기에 용이하다. 
- 좀 깨지는 부분들도 있지만 전반적으로는 pdf 한글 버전으로 보면 잘 정리되서 나온 것을 볼 수 있다. 


# 출처 

> https://github.com/Byaidu/PDFMathTranslate