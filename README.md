
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

## 2. Training Datasets

아래 표는 MLLM의 사전학습(Pre-training) 및 명령어 튜닝(Instruction Tuning)을 위해 사용된 주요 데이터셋을 정리한 것입니다. 각 데이터셋의 모달리티, 설명, 크기, 출처, 사용 단계가 포함되어 있습니다.

| Dataset       | Modalities                | Description                                                   | Size           | Source                        | Link                                                                                 | Phase                               |
|:--------------|:--------------------------|:--------------------------------------------------------------|:---------------|:------------------------------|:-------------------------------------------------------------------------------------|:------------------------------------|
| :------------ | :------------------------ | :------------------------------------------------------------ | :------------- | :---------------------------- | :----------------------------------------------------------------------------------- | :---------------------------------- |
| CASIA-HWDB    | Handwritten Characters    | 중국어 손글씨 문자 인식용 대규모 데이터셋                     | Unknown        | Chinese Academy of Sciences   | https://www.nlpr.ia.ac.cn/databases/handwriting/Home.html                            | Pre-training                        |
| CCpdf         | PDF-Text                  | 웹에서 수집된 PDF 문서를 기반으로 한 대규모 데이터셋          | Unknown        | Hugging Face                  | https://huggingface.co/datasets/ccpdf                                                | Pre-training                        |
| ChartQA       | Chart-Text                | 차트 이미지로부터 정보를 추출하고 질문에 답하는 QA 데이터셋   | 20K QA pairs   | UW                            | https://github.com/vis-nlp/ChartQA                                                   | Pre-training / Instruction Tuning   |
| DeepForm      | Form-Text                 | 문서 폼 인식을 위한 시각적-텍스트 데이터셋                    | Unknown        | NVIDIA                        | https://github.com/NVIDIA/DeepForm                                                   | Pre-training / Instruction Tuning   |
| DocVQA        | Document QA               | 문서 이미지로부터 QA를 수행하는 시각적 문서이해 데이터셋      | 50K+           | Microsoft                     | https://docvqa.org/                                                                  | Pre-training / Instruction Tuning   |
| DVQA          | BarChart QA               | 막대 차트를 기반으로 한 자동 질문응답 데이터셋                | 300K           | Rochester                     | https://www.cs.rochester.edu/u/eakbas/dvqa/                                          | Pre-training / Instruction Tuning   |
| FigureQA      | Chart-QA                  | 도형 차트를 활용한 시각적 QA용 합성 데이터                    | 100K+          | Maluuba                       | https://datasets.maluuba.com/FigureQA                                                | Pre-training                        |
| InfoVQA       | Infographic QA            | 인포그래픽 기반 복잡한 시각 정보 질의응답                     | Unknown        | Chan et al.                   | https://github.com/Chan1121/InfoVQA                                                  | Pre-training / Instruction Tuning   |
| KLC           | Chart-Text                | 차트 이미지와 대응하는 설명 생성 및 QA                        | Unknown        | Salesforce                    | https://github.com/salesforce/KLC                                                    | Pre-training / Instruction Tuning   |
| OCRVQA        | OCR-QA                    | OCR 결과와 결합된 QA용 시각문서 데이터셋                      | 1M             | IIT                           | https://rrc.cvc.uab.es/?ch=13&com=introduction                                       | Pre-training                        |
| PlotQA        | Plot-QA                   | 플롯 이미지로부터 정보 추출을 위한 QA                         | 224K           | UW                            | https://github.com/vis-nlp/PlotQA                                                    | Pre-training                        |
| PubTabNet     | Table OCR                 | 표 구조를 인식하고 재구성하기 위한 OCR 데이터                 | 500K           | IBM                           | https://github.com/ibm-aur-nlp/PubTabNet                                             | Pre-training                        |
| RVL-CDIP      | Document Classification   | 문서 유형 분류를 위한 다양한 스캔 문서                        | 400K           | CMU                           | https://www.cs.cmu.edu/~aharley/rvl-cdip/                                            | Pre-training                        |
| SCUT-HCCDoc   | Document Layout           | 문서 레이아웃 분석을 위한 구조적 데이터                       | Unknown        | SCUT                          | https://github.com/SCUT-HCCDoc/Document_Image_Understanding                          | Pre-training                        |
| SynthDog      | Synthetic OCR             | 문서 OCR을 위한 합성 데이터셋                                 | Unknown        | CLOVA AI                      | https://github.com/clovaai/synthdog                                                  | Pre-training                        |
| TAT-QA        | Table QA                  | 표 데이터를 기반으로 수치적 질의응답을 수행하는 데이터셋      | 16K            | NExT++                        | https://github.com/NExTplusplus/TAT-QA                                               | Pre-training / Instruction Tuning   |
| VisualMRC     | Multimodal RC             | 문서 이미지와 텍스트 기반 다중모달 머신 독해                  | Unknown        | Yahoo Japan                   | https://github.com/yoheikikuta/visualmrc                                             | Pre-training / Instruction Tuning   |
| WildReceipt   | Receipt OCR               | 영수증 이미지의 OCR 및 정보 추출                              | 25K            | Alibaba                       | https://github.com/AlibabaResearch/AdvancedLiterateMachinery/tree/main/WildReceipt   | Pre-training / Instruction Tuning   |
| DocILE        | Document Layout           | 문서의 필드 인식 및 구조적 태깅을 위한 벤치마크               | Unknown        | Rossum                        | https://github.com/rossumai/docile                                                   | Instruction Tuning                  |
| InsuranceQA   | FAQ QA                    | 보험 관련 FAQ에 대한 질의응답 데이터셋                        | 27K            | Studio Ousia                  | https://github.com/shuzi/insuranceQA                                                 | Instruction Tuning                  |
| OCR-TROSD     | OCR                       | 텍스트 인식을 위한 중국어 OCR 데이터                          | Unknown        | Tianchi                       | https://tianchi.aliyun.com/competition/entrance/531937/introduction                  | Instruction Tuning                  |
| WTQ           | Table QA                  | 웹 테이블을 이용한 복잡한 질의응답 데이터셋                   | 22K            | Stanford                      | https://nlp.stanford.edu/software/sempre/#wtq                                        | Instruction Tuning                  |

---

## 3. Benchmarks

| Benchmark | Description | Task Type | Link |
|-----------|-------------|-----------|------|
| MMMU | Multimodal Math & Science Reasoning | Multi-choice QA | [MMMU](https://mmmu-benchmark.github.io/) |
| MathVista | Math Diagrams + QA | Diagram QA | [MathVista](https://mathvista.github.io/) |
| ChartQA | Chart Image Comprehension | Visual QA | [ChartQA](https://github.com/vis-nlp/ChartQA) |
| ScienceQA | Multimodal Science QA | Multichoice Reasoning | [ScienceQA](https://github.com/lupantech/ScienceQA) |
| MathBench | Text + Diagram + Equation Reasoning | Mixed | [MathBench](https://mathbench.github.io/) |

---

## 4. Leaderboards

- [LLaVA Leaderboard](https://llava-vl.github.io/)
- [MMMU Leaderboard](https://mmmu-benchmark.github.io/)
- [ChartQA Leaderboard](https://chartqa.github.io/)
- [HuggingFace Open LLM Leaderboard](https://huggingface.co/spaces/HuggingFaceH4/open-llm-leaderboard)

---

## 5. Related Open-Source Projects

- [LLaVA](https://github.com/haotian-liu/LLaVA)
- [MiniGPT-4](https://github.com/Vision-CAIR/MiniGPT-4)
- [mPLUG-Owl2](https://github.com/X-PLUG/mPLUG-Owl)
- [OpenFlamingo](https://github.com/mlfoundations/open_flamingo)
- [GPT4-Vision-Adapter](https://github.com/Adapter-Hub/GPT4-Vision-Adapter)

---

## 6. References

- Papers with Code: [https://paperswithcode.com/](https://paperswithcode.com/)
- HuggingFace Model Zoo: [https://huggingface.co/models](https://huggingface.co/models)
- ArXiv MLLM Trackers: [https://www.arxiv-sanity.com/](https://www.arxiv-sanity.com/)

---

💡 *이 저장소는 지속적으로 업데이트됩니다.*
