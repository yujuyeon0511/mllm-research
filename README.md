
# MLLM Research Repository

본 리포지토리는 Multimodal Large Language Models (MLLMs)에 대한 핵심 연구 논문, 학습 데이터셋, 벤치마크 정보를 정리한 자료입니다.

---

## 📄 Contents

- [1. Key Papers](#1-key-papers)
- [2. Training Datasets](#2-training-datasets)
- [3. Benchmarks](#3-benchmarks)
- [4. Leaderboards](#4-leaderboards)
- [5. Related Open-Source Projects](#5-related-open-source-projects)
- [6. References](#6-references)

---

## 1. Key Papers

| Year | Title | Model | Institution | Link |
|------|-------|-------|-------------|------|
| 2023 | LLaVA: Visual Instruction Tuning | LLaVA | Microsoft, UIUC | [arXiv](https://arxiv.org/abs/2304.08485) |
| 2023 | MiniGPT-4 | MiniGPT-4 | Vision-CAIR | [arXiv](https://arxiv.org/abs/2304.10592) |
| 2024 | mPLUG-Owl2 | mPLUG-Owl2 | DAMO Academy | [arXiv](https://arxiv.org/abs/2308.12966) |
| 2023 | Kosmos-2 | Kosmos | Microsoft | [arXiv](https://arxiv.org/abs/2306.14824) |
| 2024 | Gemini 1.5 | Gemini | Google DeepMind | [blog](https://deepmind.google/technologies/gemini/gemini-15/) |

---

## 2. Training Datasets for Document Understanding

아래 표는 MLLM의 사전학습(Pre-training) 및 명령어 튜닝(Instruction Tuning)을 위해 사용된 주요 데이터셋을 정리한 것입니다. 각 데이터셋의 모달리티, 설명, 크기, 출처, 사용 단계가 포함되어 있습니다.

| Dataset       | Description                                                   | Size           | Link                                                                                 |
|:--------------|:--------------------------------------------------------------|:---------------|:-------------------------------------------------------------------------------------|
| CCpdf         | 웹에서 수집된 PDF 문서를 기반으로 한 다국어 대규모 데이터셋          | Unknown        | https://github.com/applicaai/CCpdf                                                  |
| ChartQA(train) | 차트 이미지로부터 정보를 추출하고 질문에 답하는 QA 데이터셋          | 28,299 QA / 18,317 img | https://huggingface.co/datasets/ahmed-masry/ChartQA                               |
| DeepForm      | 문서 폼 인식을 위한 시각적-텍스트 데이터셋                    | Unknown        | https://github.com/NVIDIA/DeepForm                                                 |
| DocVQA | 문서 이미지로부터 QA를 수행하는 시각적 문서이해 데이터셋. | Train: 39,463 QA / 10,194 img<br>Val: 5,349 QA / 1,286 img<br>Test: 5,188 QA / 1,287 img | https://www.docvqa.org/datasets/docvqa |
| DVQA          | 막대 차트를 기반으로 한 자동 질문응답 데이터셋                | Train: 2,325,316 QA / 200,000 img<br>Test-Familiar: 580,557 QA / 50,000 img<br>Test-Novel: 581,321 QA / 50,000 img           | https://github.com/kushalkafle/DVQA_dataset?tab=readme-ov-file                                       |
| FigureQA      | 도형 차트를 활용한 시각적 QA용 합성 데이터                    | Train: 1,300,000 QA / 100,000 img<br>Test-Familiar: 250,000 QA / 20,000 img<br>Test-Novel: 250,000 QA / 20,000 img          | https://www.microsoft.com/en-us/research/project/figureqa-dataset/downloads/                                              |
| InfoVQA       | 인포그래픽 기반 복잡한 시각 정보 질의응답                     | Train: 23946 QA / 4406 img<br>Val: 2801 QA / 500 img<br>Test: 3288 QA / 579 img        | https://github.com/Chan1121/InfoVQA                                                |
| KLC           | 차트 이미지와 대응하는 설명 생성 및 QA                        | Unknown        | https://github.com/salesforce/KLC                                                  |
| OCRVQA        | OCR 결과와 결합된 QA용 시각문서 데이터셋                      | 1,002,146 QA / 207,572 img             | https://ocr-vqa.github.io/                                     |
| PlotQA        | 플롯 이미지로부터 정보 추출을 위한 QA                         | Train: 20,249,479 QA / 157,070 img<br>Val: 4,360,648 QA / 33,650 img<br>Test: 4,342,514 QA / 33,657 img           | https://github.com/NiteshMethani/PlotQA                                                 |
| PubTabNet     | 표 구조를 인식하고 재구성하기 위한 OCR 데이터                 | Unknown           | https://github.com/ibm-aur-nlp/PubTabNet                                           |
| RVL-CDIP      | 문서 유형 분류를 위한 다양한 스캔 문서                        | Train: 320,000 QA / 320,000 img<br>Val: 40,000 QA / 40,000 img<br>Test: 40,000 QA / 40,000 img           | https://huggingface.co/datasets/aharley/rvl_cdip                                          |
| SynthDog      | 문서 OCR을 위한 합성 데이터셋(영어)                                 | 65,983 QA / img         | https://huggingface.co/datasets/naver-clova-ix/synthdog-en                                                |
| SynthDog-ko      | 문서 OCR을 위한 합성 데이터셋(한국어)                                 | 65,983 QA / img        | https://huggingface.co/datasets/naver-clova-ix/synthdog-ko                                                |
| TAT-QA        | 표 데이터를 기반으로 수치적 질의응답을 수행하는 데이터셋      | Train: 13215 QA / 2201 Doc<br>Val: 1668 QA / 278 Doc<br>Test: 1669 QA / 278 Doc            | https://nextplusplus.github.io/TAT-QA/                                            |
| TAT-DQA        | 재무 보고서 데이터를 기반으로 수치적 질의응답을 수행하는 데이터셋      | Train: 13251 QA / 2207 Doc<br>Val: 1663 QA / 277 Doc<br>Test: 1644 QA / 274 Doc            | https://nextplusplus.github.io/TAT-DQA/                                             |
| VisualMRC     | 문서 이미지와 텍스트 기반 다중모달 머신 독해                  | Unknown        | https://github.com/yoheikikuta/visualmrc                                           |
| WildReceipt   | 영수증 이미지의 OCR 및 정보 추출                              | Unknown            | https://paperswithcode.com/dataset/wildreceipt |
| DocILE        | 문서의 필드 인식 및 구조적 태깅을 위한 벤치마크               | Unknown        | https://docile.rossum.ai/                                                 |
| WTQ           | 웹 테이블을 이용한 복잡한 질의응답 데이터셋                   | Unknown            | https://ppasupat.github.io/WikiTableQuestions/                                      |
| askchart                    | 다양한 차트 기반 시각적 질문 응답 태스크를 위한 instruction tuning용 QA 데이터셋           | 2000 QA / 2000 img                                              | https://github.com/yuchenlin/Ask-Chart                                                                  |
| chart2code                  | 차트 이미지를 분석하여 대응되는 코드(JSON, Vega 등)를 생성하는 차트 리버스엔지니어링 데이터셋 | 163189 QA / 163189 img                                             | https://github.com/vis-nlp/Chart2Code                                                                    |
| chartinstruction            | 차트 QA 모델 학습을 위한 instruction-following 스타일의 시각적 질문 응답 데이터셋            | 105112 QA                                             | https://huggingface.co/datasets/lewy666/ChartInstructionData                                           |
| chartmoe                    | 다양한 멀티모달 차트 QA 태스크를 위한 mixture-of-experts 프롬프트 기반 데이터셋             | chartgemma: 163240 QA<br>chart2code: 898609 QA<br>chart2json: 898609 QA<br>chart2table: 898609 QA<br>chart2qa: 30219 QA                                             | https://huggingface.co/datasets/Coobiw/ChartMoE-Data                                                                    |
| deeprule                    | 수학적·논리적 규칙 기반 차트 질의응답 태스크를 위한 고난도 차트 QA 데이터셋                 | barchart(Train/Val/Test): 173249 / 6935 / 6970 img<br>cls: 115776 / 3695 / 3773 img<br>piedata: 73075 / 1924 / 1923 img                                            | https://huggingface.co/datasets/niups/DeepRuleDataset                                                                   |
| novachart                   | 차트 이미지와 다양한 복합 질의 응답을 포함하는 instruction fine-tuning용 차트 QA 데이터셋     | Unknown                                             | https://huggingface.co/datasets/ympan/novachar                                                     |
| chart2textpew               | Pew Research 기반 차트로부터 자연어 질문·응답을 구성한 QA 데이터셋                          | Two: 5092 QA<br>Multi: 26476 QA                     | https://huggingface.co/datasets/mPLUG/TinyChartData                                                                |
| chart2textstatista          | Statista 차트를 기반으로 다양한 단일·복합 질의를 포함한 QA 데이터셋                         | Two: 47404 QA<br>Multi: 11774 QA                    | https://huggingface.co/datasets/mPLUG/TinyChartData                                                                |
| chart2textstatista-table    | Statista 테이블 기반 질의응답 데이터셋 (표로부터 직접 질의하는 QA)                          | Two: 23702 QA<br>Multi: 5887 QA                     | https://huggingface.co/datasets/mPLUG/TinyChartData                                                                 |
| chart2text-8k               | 다양한 웹 차트로부터 생성된 단일·다중 질의응답을 포함한 차트 QA 데이터셋                     | Single: 6415 QA<br>Multi: 1447 QA                   | https://huggingface.co/datasets/mPLUG/TinyChartData                                                                 |
| chart2text-8k-table         | chart2text-8k의 테이블 기반 질의응답 확장 버전                                               | Single: 6763 QA<br>Multi: 1542 QA                   | https://huggingface.co/datasets/mPLUG/TinyChartData                                                                 |
| chartllama                  | LLaMA 기반 차트 QA 모델 학습을 위한 instruction fine-tuning 데이터셋                        | Train: 148398 QA                                    | https://huggingface.co/datasets/mPLUG/TinyChartData                                                 |
| chartsumm                   | 차트를 요약한 문장 기반 QA 쌍을 포함하는 multi-source chart summarization 데이터셋          | TrainK: 34702 QA / TrainS: 32186 QA<br>ValK: 4338 QA / ValS: 4092 QA | https://huggingface.co/datasets/mPLUG/TinyChartData                                                                  |
| opencqa                     | 다양한 차트 형태와 복합 reasoning이 포함된 open-ended 차트 QA 데이터셋                       | Train: 4605 QA<br>Val: 983                          | https://huggingface.co/datasets/mPLUG/TinyChartData                                                                    |
| vistext                     | 차트 이미지와 텍스트 결합 기반의 시각 질문 응답 태스크용 차트 QA 데이터셋                   | Train: 9969 QA<br>Val: 1202                         | https://huggingface.co/datasets/mPLUG/TinyChartData                                                                    |
| chartqa2table               | 기존 ChartQA 데이터를 테이블 형태로 재구성한 차트 QA를 위한 정형화된 QA 데이터셋             | Train: 73268 QA<br>Val: 4224                        | https://huggingface.co/datasets/mPLUG/TinyChartData                                                               |
| ReachQA               | 기존 ChartQA 데이터를 테이블 형태로 재구성한 차트 QA를 위한 정형화된 QA 데이터셋             | Train: 73268 QA<br>Val: 4224                        | https://github.com/hewei2001/ReachQA                              |
| ReFocus               | 기존 ChartQA 데이터를 테이블 형태로 재구성한 차트 QA를 위한 정형화된 QA 데이터셋             | Train: 73268 QA<br>Val: 4224                        | https://github.com/zeyofu/ReFocus_Code |
| the_cauldron               | The Cauldron contains only the train split of each sub-datasets. On top of that, we removed the few examples containing an image also present in the test splits of MMMU, MathVista or MMBench.            |                         | https://huggingface.co/datasets/HuggingFaceM4/the_cauldron |
| LLaVA-OneVision-Data                | Dataset Card for LLaVA-OneVision            |                         | https://huggingface.co/datasets/lmms-lab/LLaVA-OneVision-Data |

## 3. LLaVA 모델 학습 데이터

LLaVA (Large Language and Vision Assistant)는 멀티모달 명령어 이해를 위해 다음과 같은 데이터셋을 사용하여 학습되었습니다.

### 1. Feature Alignment (사전학습) 단계

- **사용 데이터:** CC3M (Conceptual Captions 3M)에서 필터링된 약 595K 이미지-텍스트 쌍
- **학습 목적:** 비전 인코더의 출력을 언어 모델의 임베딩 공간에 정렬하기 위한 투영 행렬 학습
- **학습 방식:** 비전 인코더와 언어 모델은 고정, 투영 행렬만 학습

### 2. Visual Instruction Tuning (명령어 튜닝) 단계

- **사용 데이터:**
  - LLaVA-Instruct-150K: GPT-4로 생성된 약 150K 개의 시각 명령어-응답 쌍
  - 추가적으로 약 515K 개의 VQA 데이터 포함
- **학습 목적:** 다양한 시각 명령어에 따라 정밀한 응답을 생성하는 능력 강화
- **학습 방식:** 비전 인코더는 고정하고, 투영 행렬 및 언어 모델을 함께 미세 조정

**참고 링크:**
- GitHub: [haotian-liu/LLaVA](https://github.com/haotian-liu/LLaVA)
- 논문: [Visual Instruction Tuning](https://arxiv.org/abs/2304.08485)

## 4. Gemma 모델 학습 토큰 요약

Gemma 3 시리즈는 모델 규모에 따라 서로 다른 양의 토큰으로 학습되었습니다. 가장 큰 **Gemma 3 27B** 모델은 총 **14조(14T)** 토큰으로 학습되었으며, **Gemma 3 12B** 모델은 **12조(12T)** 토큰, **Gemma 3 4B** 모델은 **4조(4T)** 토큰, **Gemma 3 1B** 모델은 **2조(2T)** 토큰으로 각각 학습되었습니다. 이러한 차등적 학습 토큰 설계는 모델 크기에 따른 학습 효율성과 성능 균형을 고려한 구조입니다.

---

## 5. Benchmarks

| Benchmark | Description | Task Type | Link |
|-----------|-------------|-----------|------|
| MMMU | Multimodal Math & Science Reasoning | Multi-choice QA | [MMMU](https://mmmu-benchmark.github.io/) |
| MathVista | Math Diagrams + QA | Diagram QA | [MathVista](https://mathvista.github.io/) |
| ChartQA | Chart Image Comprehension | Visual QA | [ChartQA](https://github.com/vis-nlp/ChartQA) |
| ScienceQA | Multimodal Science QA | Multichoice Reasoning | [ScienceQA](https://github.com/lupantech/ScienceQA) |
| MathBench | Text + Diagram + Equation Reasoning | Mixed | [MathBench](https://mathbench.github.io/) |

---

## 6. Leaderboards

- [LLaVA Leaderboard](https://llava-vl.github.io/)
- [MMMU Leaderboard](https://mmmu-benchmark.github.io/)
- [ChartQA Leaderboard](https://chartqa.github.io/)
- [HuggingFace Open LLM Leaderboard](https://huggingface.co/spaces/HuggingFaceH4/open-llm-leaderboard)

---

## 7. Related Open-Source Projects

- [LLaVA](https://github.com/haotian-liu/LLaVA)
- [MiniGPT-4](https://github.com/Vision-CAIR/MiniGPT-4)
- [mPLUG-Owl2](https://github.com/X-PLUG/mPLUG-Owl)
- [OpenFlamingo](https://github.com/mlfoundations/open_flamingo)
- [GPT4-Vision-Adapter](https://github.com/Adapter-Hub/GPT4-Vision-Adapter)
- [Gemma](https://github.com/google/gemma)
- [DocKylin](https://github.com/ZZZHANG-jx/DocKylin)

---

## 8. References

- Papers with Code: [https://paperswithcode.com/](https://paperswithcode.com/)
- HuggingFace Model Zoo: [https://huggingface.co/models](https://huggingface.co/models)
- ArXiv MLLM Trackers: [https://www.arxiv-sanity.com/](https://www.arxiv-sanity.com/)

---

💡 *이 저장소는 지속적으로 업데이트됩니다.*
