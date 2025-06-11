
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
| ChartQA(train) | 차트 이미지로부터 정보를 추출하고 질문에 답하는 QA 데이터셋          | 28,299 QA pairs / 18,317 images | https://huggingface.co/datasets/ahmed-masry/ChartQA                               |
| DeepForm      | 문서 폼 인식을 위한 시각적-텍스트 데이터셋                    | Unknown        | https://github.com/NVIDIA/DeepForm                                                 |
| DocVQA | 문서 이미지로부터 QA를 수행하는 시각적 문서이해 데이터셋. | <br>Train: 39,463 Q / 10,194 img<br>Val: 5,349 Q / 1,286 img<br>Test: 5,188 Q / 1,287 img | https://docvqa.org/ |
| DVQA          | 막대 차트를 기반으로 한 자동 질문응답 데이터셋                | 300K           | https://www.cs.rochester.edu/u/eakbas/dvqa/                                        |
| FigureQA      | 도형 차트를 활용한 시각적 QA용 합성 데이터                    | 100K+          | https://datasets.maluuba.com/FigureQA                                              |
| InfoVQA       | 인포그래픽 기반 복잡한 시각 정보 질의응답                     | Unknown        | https://github.com/Chan1121/InfoVQA                                                |
| KLC           | 차트 이미지와 대응하는 설명 생성 및 QA                        | Unknown        | https://github.com/salesforce/KLC                                                  |
| OCRVQA        | OCR 결과와 결합된 QA용 시각문서 데이터셋                      | 1M             | https://rrc.cvc.uab.es/?ch=13&com=introduction                                     |
| PlotQA        | 플롯 이미지로부터 정보 추출을 위한 QA                         | 224K           | https://github.com/vis-nlp/PlotQA                                                  |
| PubTabNet     | 표 구조를 인식하고 재구성하기 위한 OCR 데이터                 | 500K           | https://github.com/ibm-aur-nlp/PubTabNet                                           |
| RVL-CDIP      | 문서 유형 분류를 위한 다양한 스캔 문서                        | 400K           | https://www.cs.cmu.edu/~aharley/rvl-cdip/                                          |
| SCUT-HCCDoc   | 문서 레이아웃 분석을 위한 구조적 데이터                       | Unknown        | https://github.com/SCUT-HCCDoc/Document_Image_Understanding                        |
| SynthDog      | 문서 OCR을 위한 합성 데이터셋                                 | Unknown        | https://github.com/clovaai/synthdog                                                |
| TAT-QA        | 표 데이터를 기반으로 수치적 질의응답을 수행하는 데이터셋      | 16K            | https://github.com/NExTplusplus/TAT-QA                                             |
| VisualMRC     | 문서 이미지와 텍스트 기반 다중모달 머신 독해                  | Unknown        | https://github.com/yoheikikuta/visualmrc                                           |
| WildReceipt   | 영수증 이미지의 OCR 및 정보 추출                              | 25K            | https://github.com/AlibabaResearch/AdvancedLiterateMachinery/tree/main/WildReceipt |
| DocILE        | 문서의 필드 인식 및 구조적 태깅을 위한 벤치마크               | Unknown        | https://github.com/rossumai/docile                                                 |
| InsuranceQA   | 보험 관련 FAQ에 대한 질의응답 데이터셋                        | 27K            | https://github.com/shuzi/insuranceQA                                               |
| OCR-TROSD     | 텍스트 인식을 위한 중국어 OCR 데이터                          | Unknown        | https://tianchi.aliyun.com/competition/entrance/531937/introduction                |
| WTQ           | 웹 테이블을 이용한 복잡한 질의응답 데이터셋                   | 22K            | https://nlp.stanford.edu/software/sempre/#wtq                                      |



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
