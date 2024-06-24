
### 모델 선정 배경

- pre-trained model 의 
- baseline 모델을 만들어서 기준점 만들기
#### 평가 데이터셋
##### korean-hate-speech
[github](https://github.com/kocohub/korean-hate-speech)
- The data is comments from the Korean entertainment news aggregation platform

##### KLUE benchmark 

KLUE benchmark is composed of 8 tasks: ([paper](https://arxiv.org/pdf/2105.09680))

- **Topic Classification (TC)**
- Sentence Textual Similarity (STS)
- Natural Language Inference (NLI)
- Named Entity Recognition (NER)
- Relation Extraction (RE)
- (Part-Of-Speech) + Dependency Parsing (DP)
- Machine Reading Comprehension (MRC)
- *Dialogue State Tracking (DST)*




#### 한국어 텍스트 분류 모델의 종류
- [Ref](https://github.com/rurube/DLthon/blob/main/presentation.pptx) # 10
- [Ref2](https://github.com/hongseoi/DLTON/blob/main/DLTON%20AIFFEL%20ONLINE%205%EA%B8%B0%20NLP.pdf)

#### KoBert
- [github](https://github.com/SKTBrain/KoBERT)

- SKT에서 제공하는 한국어 BERT 모델로 한국어 텍스트 데이터를 기반으로 사전 훈련됨.
- 평가 결과: Naver Sentiment Analysis, Dataset: https://github.com/e9t/nsmc
    |Model|	Accuracy|
    |---|---|
    |BERT base multilingual cased| 0.875|
    |KoBERT| 0.901|
    |KoGPT2| 0.899|

#### **KLUE BERT**
[huggingface](https://huggingface.co/klue/bert-base), [github](https://github.com/KLUE-benchmark/KLUE)
- KLUE(Korean Language Understanding Evaluation) 프로젝트에서 제공하는 BERT 모델로 
- KLUE는 한국어 NLP에 대한 벤치마크 및 데이터셋을 제공하는 프로젝트이며, 
- 한국어 NLP 커뮤니티에서 널리 인정받으며 여러 모델 중높은 성능과 안정성을 제공하는 모델

- 평가 결과, 데이터셋: KLUE

| Model                    | TC    | STS   |       | NLI   | NER    |        | RE         |       | DP    |       | MRC   |       | DST   |       |
|--------------------------|-------|-------|-------|-------|--------|--------|------------|-------|-------|-------|-------|-------|-------|-------|
|                          | F1    | Pearsons' r | F1    | ACC   | entity F1 | char F1 | F1 | AUPRC | UAS   | LAS   | EM    | ROUGE | JGA   | Slot F1    |
| **mBERT-base** | 81.55 | 84.66 | 76.00 | 73.20 | 76.50 | 89.23 | 57.88 | 53.82 | 90.30 | 86.66 | 44.66 | 55.92 | 35.46 | 88.63 |
| **XLM-R-base**  | 83.52 | 89.16 | 82.01 | 77.33 | 80.37 | 92.12 | 57.46 | 54.98 | 89.20 | 87.69 | 27.48 | 53.93 | 39.82 | 89.61 |
| **XLM-R-large** | **86.06** | 92.97 | 85.86 | 85.93 | 82.27 | **93.22** | 58.39 | 61.15 | 92.71 | **88.70** | 35.99 | 66.77 | 41.20 | 89.80 |
||
| **KR-BERT-base**  | 84.58 | 88.61 | 81.07 | 77.17 | 74.58 | 90.13 | 62.74 | 60.94 | 89.92 | 87.48 | 48.28 | 58.54 | 45.33 | 90.70 |
| **koELECTRA-base** | 84.59 | _92.46_ | _84.84_ | _85.63_ | **_86.11_** | _92.56_ | 62.85 | 58.94 | 92.90 | 87.77 | 59.82 | 66.05 | 41.58 | 89.60 |
||
| **KLUE-BERT-base** | _85.73_ | 90.85 | 82.84 | 81.63 | 83.97 | 91.39 | 66.44 | 66.17 | 89.96 | 88.05 | 62.32 | 68.51 | 46.64 | 91.61 |
| **KLUE-RoBERTa-small** | 84.98 | 91.54 | 85.16 | 79.33 | 83.65 | 91.14 | 60.89 | 58.96 | 90.04 | 88.14 | 57.32 | 62.70 | 46.62 | 91.44 |
| **KLUE-RoBERTa-base** | 85.07 | 92.50 | 85.40 | 84.83 | 84.60 | 91.44 | _67.65_ | _68.55_ | _93.04_ | _88.32_ | _68.67_ | _73.98_ | _47.49_ | _91.64_ | 
| **KLUE-RoBERTa-large** | 85.69 | **93.35** | **86.63** | **89.17** | 85.00 | 91.86 | **71.13** | **72.98** | **93.48** | 88.36 | **75.58** | **80.59** | **50.22** | **92.23** |

#### Dialog-KoELECTRA
[github](https://github.com/SKplanet/Dialog-KoELECTRA)
- Dialog-KoELECTRA는 대화체에 특화된 언어 모델
- Fine-tuning 제공

#### ~~Ko-ELECTRA~~
[github](https://github.com/monologg/KoELECTRA)
- ELECTRA 모델의 한국어 버전으로, 한국어 데이터로 사전 훈련됨.


#### Ko-GPT2
[github](https://github.com/SKT-AI/KoGPT2)
- GPT 아키텍처를 기반으로 한 한국어 모델. 주로 생성 작업에 사용됨. 분류 작업에도 적용 가능
- 평가 결과: 데이터셋: NSMC

||**NSMC**(acc)	|KorSTS(spearman)|
|---|---|---|
|KoGPT2 2.0	|89.1	|77.8|

#### KoBART
[github](https://github.com/SKT-AI/KoBART)

||**NSMC**(acc)|
|---|---|
|KoGPT2 2.0	|90.24|

---

### 추가 학습 데이터

#### 1. [Korpora](https://ko-nlp.github.io/Korpora/ko-docs/corpuslist/nsmc.html)

#### 2. ref: https://github.com/SKplanet/Dialog-KoELECTRA
<table >
<thead>
  <tr>
    <th ></th>
    <th >corpus name</th>
    <th >size</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td  rowspan="5">대화체</td>
    <td ><a href="https://aihub.or.kr/aidata/85" target="_blank" rel="noopener noreferrer">Aihub Korean dialog corpus</a></td>
    <td  rowspan="4">7GB</td>
  </tr>
  <tr>
    <td ><a href="https://corpus.korean.go.kr/" target="_blank" rel="noopener noreferrer">NIKL Spoken corpus</a></td>
  </tr>
  <tr>
    <td ><a href="https://github.com/songys/Chatbot_data" target="_blank" rel="noopener noreferrer">Korean chatbot data</a></td>
  </tr>
  <tr>
    <td ><a href="https://github.com/Beomi/KcBERT" target="_blank" rel="noopener noreferrer">KcBERT</a></td>
  </tr>
  <tr>
    <td ><a href="https://github.com/e9t/nsmc" target="_blank" rel="noopener noreferrer">NSMC</a></td>
    <td> ? </td>
  </tr>
  <tr>
    <td  rowspan="2">문어체</td>
    <td ><a href="https://corpus.korean.go.kr/" target="_blank" rel="noopener noreferrer">NIKL Newspaper corpus</a></td>
    <td  rowspan="2">15GB</td>
  </tr>
  <tr>
    <td ><a href="https://github.com/lovit/namuwikitext" target="_blank" rel="noopener noreferrer">namuwikitext</a></td>
  </tr>
</tbody>
</table>

<br>

#### 3. AI hub
[주제별 텍스트 일상 대화 데이터](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=data&dataSetSn=543)
[한국어 멀티세션 대화](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=data&dataSetSn=71630)