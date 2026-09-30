<h1 align="center">Awesome Audio Editing</h1>

<h2 align="center">Audio Editing in the Era of Foundation Models: A Survey</h2>

<p align="center">
  <b>AACL-IJCNLP 2026</b>
</p>

<p align="center">
  Changhao Pan<sup>1,*</sup>, Yifei Fan<sup>1,*</sup>, Fan Zhuo<sup>1,*</sup>, Yifu Chen<sup>1</sup>, Wenxiang Guo<sup>1</sup>,<br/>
  Yu Zhang<sup>2</sup>, Ruiqi Li<sup>2</sup>, Zhiyuan Zhu<sup>1</sup>, Rui Yang<sup>1</sup>, Shengpeng Ji<sup>3</sup>,<br/>
  Chenyuhao Wen<sup>1</sup>, Jiayang Xu<sup>1</sup>, Ke Lei<sup>1</sup>, Xiaoda Yang<sup>1</sup>, Jingyu Lu<sup>1</sup>, Zhou Zhao<sup>1,†</sup>
</p>

<p align="center">
  <sup>1</sup>Zhejiang University &nbsp;&middot;&nbsp;
  <sup>2</sup>ByteDance &nbsp;&middot;&nbsp;
  <sup>3</sup>Hunyuan Team, Tencent
</p>

<p align="center">
  <sup>*</sup>Equal contribution &nbsp;&middot;&nbsp;
  <sup>†</sup>Corresponding author
</p>

<p align="center">
  <a href="https://arxiv.org/abs/2606.23139"><img src="https://img.shields.io/badge/arXiv-2606.23139-b31b1b.svg" alt="arXiv"></a>
  <a href="#whats-new"><img src="https://img.shields.io/badge/Venue-AACL--IJCNLP%202026-4b8bbe.svg" alt="AACL-IJCNLP 2026"></a>
  <a href="https://david-pigeon.github.io/audioeditsurvey_project/"><img src="https://img.shields.io/badge/Project-Page-1f9c5a.svg" alt="Project Page"></a>
  <a href="https://github.com/MM-Speech/AudioEditSurvey/stargazers"><img src="https://img.shields.io/github/stars/MM-Speech/AudioEditSurvey?style=social" alt="GitHub stars"></a>
</p>

### 🌐 Languages

[English](README.md) · [简体中文](readme_zh.md) · [한국어](readme_kr.md)

<a id="quick-start"></a>

# 🚀 빠른 시작

이 저장소는 **`AACL-IJCNLP 2026`**에 채택된 서베이 논문 **Audio Editing in the Era of Foundation Models: A Survey**의 공식 저장소입니다.

- **음성, 음악, 일반 오디오**를 아우르는 **음향·의미·인스턴스 편집**의 통합 분류 체계를 제시합니다. 각 작업이 바꾸어야 할 요소와 보존해야 할 요소를 명확히 하여 서로 다른 편집 목표를 일관되게 비교할 수 있도록 합니다.
- **파운데이션 모델 아키텍처**와 **학습 패러다임**을 중심으로 주요 오디오 편집 기술을 정리하고, 핵심 원리와 다양한 편집 상황에서의 적합성을 살펴봅니다.
- **(최근 업데이트)** **공개된 오디오 편집 모델**을 모아 지원 작업과 주요 장점을 정리하고, 독자가 적합한 모델을 찾을 수 있도록 합니다.
- **(최근 업데이트)** 오디오 편집을 위한 **공개 데이터셋, 데이터 구축 도구, 평가 벤치마크 및 지표**를 정리하고, 각 자원이 다루는 오디오 영역, 편집 범주, 평가 차원을 소개합니다.

<a id="whats-new"></a>

# 🔥 새로운 소식

- 📦 **[2026/09] 원활한 유지·관리를 위해 저장소를 [`MM-Speech/AudioEditSurvey`](https://github.com/MM-Speech/AudioEditSurvey)로 이전했습니다.**
- 🏆 **[2026/09] 논문이 AACL-IJCNLP 2026에 채택되었습니다!**
- 🎉 **[2026/06] 오디오 편집 모델 서베이 저장소를 공식 공개했습니다. 논문 프리프린트는 [arXiv](https://arxiv.org/abs/2606.23139)에서 확인할 수 있습니다.**

## 목차

1. [소개](#introduction)
2. [개요](#overall)
   - [분류 체계 개요](#taxonomy-overview)
   - [분류 체계 상세](#taxonomy-details)
   - [대표적인 오디오 편집 방법](#representative-audio-editing-methods)
     - [Unified](#methods-unified) · [Speech](#methods-speech) · [Music](#methods-music) · [Audio](#methods-audio)
3. [학습 기반 오디오 편집](#training-based-audio-editing)
4. [추가 학습 없는 오디오 편집](#training-free-audio-editing)
   - [대표적인 추가 학습 없는 편집 방법](#representative-training-free-methods)
5. [자원](#resources)
   - [공개 데이터셋](#available-datasets)
     - [음성](#speech) · [음악](#music) · [일반 오디오](#audio) · [통합](#unified)
   - [데이터 도구](#data-tools)
   - [평가 벤치마크](#benchmarks)
   - [평가 지표](#evaluation-metrics)
6. [과제와 향후 연구 방향](#challenges-and-future-directions)
7. [인용](#citation)
8. [기여하기](#contributing)

---

<a id="introduction"></a>

## 📌 소개

**Awesome Audio Editing**은 **음성, 음악, 일반 오디오**를 아우르는 파운데이션 모델 기반 오디오 편집 연구와 자원을 모은 저장소입니다. 우리의 [서베이 논문](https://arxiv.org/abs/2606.23139)을 바탕으로 편집 작업, 모델 설계, 학습 전략, 실용적인 자원을 연결합니다.

- **작업 분류 체계.** **음향·의미·인스턴스 편집**을 통합된 체계로 분류하여, 각 작업에서 수정할 대상과 보존할 내용을 명확히 합니다.
- **모델 아키텍처.** **오디오 코덱 언어 모델, 확산 모델, 플로 매칭 모델**을 정리하고, 오디오 표현과 생성 메커니즘이 어떤 편집 연산을 지원하는지 살펴봅니다.
- **학습 방법.** 데이터에서 편집 능력을 배우는 **학습 기반 방법**과 파라미터 업데이트 없이 추론 시 사전학습 생성 모델을 제어하는 **추가 학습 없는 방법**을 구분하고, 핵심 기술 메커니즘에 따라 대표 연구를 정리합니다.
- **공개 자원.** **공개된 편집 모델, 데이터셋, 데이터 생성·주석 도구, 평가 벤치마크 및 지표**를 모아 자원 링크와 지원 기능을 소개하며, 연구와 구현을 돕습니다.

---

<a id="overall"></a>

## 🧭 개요

<a id="taxonomy-overview"></a>

### 🗂️ 분류 체계 개요

![오디오 편집 작업 분류 체계](assets/taxonomy_overview.png)

*그림 1: 오디오 편집 작업 분류 체계.*



<a id="taxonomy-details"></a>

### 🧩 분류 체계 상세




| 범주 | 정의 | 대표 편집 목표 |
| --- | --- | --- |
| 음향 편집 | 원본 오디오의 전체 구조와 음원 특성을 보존하면서 저수준 지각 속성을 수정합니다. | 복원, 잔향 편집, 음량·믹싱 제어, 이퀄라이징, 스펙트럼 질감 편집 |
| 의미 편집 | 작업과 무관한 속성을 유지하면서 오디오가 전달하는 고수준의 해석 가능한 정보를 수정합니다. | 언어 내용 편집, 표현 편집, 스타일 편집 |
| 인스턴스 편집 | 장면의 나머지 요소와 음원 간 관계를 보존하면서 식별 가능한 오디오 개체를 조작합니다. | 교체, 삭제·추출, 삽입, 오버레이·리믹싱 |

<a id="representative-audio-editing-methods"></a>

### 📚 대표적인 오디오 편집 방법

편집 구현과 모델 가중치가 공개된 대표 연구를 정리했습니다. 각 프로젝트의 라이선스가 적용됩니다. 편집 유형은 본 서베이의 [분류 체계](#taxonomy-details)를 따르며, **Unified**는 여러 오디오 유형을 지원하는 편집 모델을 모으며, 지원 유형은 표에 명시합니다. **기반 모델** 링크는 편집기에 사용하는 사전학습 백본을, **어댑터** 링크는 추가로 학습한 가중치를 가리킵니다.

<a id="methods-unified"></a>

#### 통합 모델 (Unified)

| 모델 | 오디오 유형 | 편집 유형 | 모델 구조 | 논문 | 코드 | 모델 가중치 |
| --- | --- | --- | --- | --- | --- | --- |
| Audio-Omni | Speech; Music; Audio | 인스턴스: 추가·삭제·추출·음원 변환 | MLLM + Rectified Flow DiT | <a href="https://arxiv.org/abs/2604.10708"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ZeyueT/Audio-Omni"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 가중치](https://huggingface.co/HKUSTAudio/Audio-Omni) |
| AudioMorphix | Speech; Music; Audio | 의미: 음높이·시간 신축<br>인스턴스: 추가·삭제·교체·시간 이동 | 확산 U-Net(Tango / AudioLDM) | <a href="https://arxiv.org/abs/2505.16076"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://huggingface.co/spaces/JinhuaL1ANG/AudioMorphix/tree/main"><img height="20" src="https://img.shields.io/badge/HuggingFace-Code-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Code"></a> | [🤗 기반 모델(Tango 2)](https://huggingface.co/declare-lab/tango2-full)<br>[🤗 기반 모델(AudioLDM)](https://huggingface.co/cvssp/audioldm-l-full) |
| AuK / AuK-Flash | Speech; Music | 음향: 복원·음량<br>의미: 단어·가사·표현<br>인스턴스: 음색·음원 추출 | MLLM + Rectified Flow DiT | <a href="https://arxiv.org/abs/2609.08936"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/Tencent-Hunyuan/AuK"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 AuK](https://huggingface.co/tencent/AuK)<br>[🤗 Flash](https://huggingface.co/tencent/AuK-Flash) |
| Vevo2 | Speech; Music | 의미: 내용·가사·운율·스타일<br>인스턴스: 화자·가수 변환 | 코덱 언어 모델 + 플로 매칭 디코더 | <a href="https://arxiv.org/abs/2508.16332"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/open-mmlab/Amphion/tree/main/models/svc/vevo2"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 가중치](https://huggingface.co/RMSnow/Vevo2) |
| DirectAudioEdit | Music; Audio | 인스턴스: 텍스트 기반 이벤트 교체·추가·삭제 | 확산 U-Net(Tango 2 / AudioLDM2) | <a href="https://arxiv.org/abs/2606.07356"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/NiuTrans/DirectAudioEdit"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 기반 모델(Tango 2)](https://huggingface.co/declare-lab/tango2-full)<br>[🤗 기반 모델(일반 오디오)](https://huggingface.co/cvssp/audioldm2) |
| DDPM Inversion (ZETA) | Music; Audio | 의미: 음악 스타일<br>인스턴스: 악기·소리 이벤트 변경 | 확산 U-Net(AudioLDM2) | <a href="https://arxiv.org/abs/2402.10009"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/HilaManor/AudioEditingCode"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 기반 모델(일반 오디오)](https://huggingface.co/cvssp/audioldm2)<br>[🤗 기반 모델(음악)](https://huggingface.co/cvssp/audioldm2-music) |

<a id="methods-speech"></a>

#### 음성 모델 (Speech)

| 모델 | 편집 유형 | 모델 구조 | 논문 | 코드 | 모델 가중치 |
| --- | --- | --- | --- | --- | --- |
| Ming-UniAudio-Edit | 음향: 잡음 제거·음량<br>의미: 내용·운율·감정·방언 | 연속 토큰 언어 모델 + 확산 헤드 | <a href="https://arxiv.org/abs/2511.05516"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/inclusionAI/Ming-UniAudio"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 가중치](https://huggingface.co/inclusionAI/Ming-UniAudio-16B-A3B-Edit) |
| Step-Audio-EditX | 의미: 감정·발화 스타일·준언어적 단서·발음 | 코덱 언어 모델 + 플로 매칭 디코더 | <a href="https://arxiv.org/abs/2511.03601"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/stepfun-ai/Step-Audio-EditX"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 가중치](https://huggingface.co/stepfun-ai/Step-Audio-EditX) |
| CosyEdit | 의미: 단어 삽입·삭제·교체 | 코덱 언어 모델 + 플로 매칭 디코더 | <a href="https://arxiv.org/abs/2601.05329"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/CJY1018/CosyEdit"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 가중치](https://huggingface.co/CJY/CosyEdit) |
| VoiceCraft-X | 의미: 다국어 내용 편집 | 코덱 언어 모델(자기회귀 인필링) | <a href="https://arxiv.org/abs/2511.12347"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/zszheng147/VoiceCraft-X"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 가중치](https://huggingface.co/zhisheng01/VoiceCraft-X) |
| VoiceCraft | 의미: 단어 삽입·삭제·교체 | 코덱 언어 모델(자기회귀 인필링) | <a href="https://arxiv.org/abs/2403.16973"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/jasonppy/VoiceCraft"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 가중치](https://huggingface.co/pyp1/VoiceCraft) |
| SSR-Speech | 의미: 단어 삽입·삭제·교체 | 코덱 언어 모델(자기회귀 인필링) | <a href="https://arxiv.org/abs/2409.07556"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/WangHelin1997/SSR-Speech"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 영어](https://huggingface.co/westbrook/SSR-Speech-English)<br>[🤗 중국어](https://huggingface.co/westbrook/SSR-Speech-Mandarin) |
| F5-TTS | 의미: 국소 내용 교체·인필링 | 플로 매칭 DiT | <a href="https://arxiv.org/abs/2410.06885"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/SWivid/F5-TTS/blob/main/src/f5_tts/infer/speech_edit.py"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 가중치](https://huggingface.co/SWivid/F5-TTS) |
| FluentSpeech | 의미: 내용 편집·말더듬 및 비유창성 교정 | 확산 모델(문맥 인식 잡음 제거기) | <a href="https://arxiv.org/abs/2305.13612"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/Zain-Jiang/Speech-Editing-Toolkit"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [📁 가중치](https://drive.google.com/drive/folders/1saqpWc4vrSgUZvRvHkf2QbwWSikMTyoo) |
| EdiTTS | 의미: 합성 음성의 내용·음높이 편집 | 스코어 기반 확산(Grad-TTS) | <a href="https://arxiv.org/abs/2110.02584"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/neosapience/editts"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [📦 기반 모델](https://github.com/neosapience/editts/tree/master/checkpts) |

<a id="methods-music"></a>

#### 음악 모델 (Music)

| 모델 | 편집 유형 | 모델 구조 | 논문 | 코드 | 모델 가중치 |
| --- | --- | --- | --- | --- | --- |
| YingMusic-Singer-Plus | 의미: 가사<br>인스턴스: 가수 음색 교체 | 플로 매칭 DiT | <a href="https://arxiv.org/abs/2603.24589"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ASLP-lab/YingMusic-Singer-Plus"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 가중치](https://huggingface.co/ASLP-lab/YingMusic-Singer-Plus) |
| ACE-Step 1.5 | 의미: 스타일·국소 리페인팅<br>인스턴스: 트랙 추출·추가(base 버전) | 언어 모델 + 플로 매칭 DiT | <a href="https://arxiv.org/abs/2602.00744"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ace-step/ACE-Step-1.5"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 Turbo](https://huggingface.co/ACE-Step/Ace-Step1.5)<br>[🤗 Base 버전](https://huggingface.co/ACE-Step/acestep-v15-base) |
| Instruct-MusicGen | 인스턴스: 스템 추가·삭제·추출 | 코덱 언어 모델(MusicGen) + 어댑터 | <a href="https://arxiv.org/abs/2405.18386"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ldzhangyx/instruct-MusicGen"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 공개 데이터 재학습 버전](https://huggingface.co/ldzhangyx/instruct-MusicGen) |
| MusicGen-Stem | 인스턴스: 스템 교체·추가(베이스·드럼·기타 음원) | 다중 스트림 코덱 언어 모델 | <a href="https://arxiv.org/abs/2501.01757"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/simonrouard/audiocraft/tree/multistem"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 가중치](https://huggingface.co/facebook/musicgen-stem-6cb) |
| MelodyFlow | 의미: 장르·분위기·스타일<br>인스턴스: 악기 구성 | 플로 매칭 DiT | <a href="https://arxiv.org/abs/2407.03648"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://huggingface.co/spaces/facebook/MelodyFlow/tree/main"><img height="20" src="https://img.shields.io/badge/HuggingFace-Code-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Code"></a> | [🤗 가중치](https://huggingface.co/facebook/melodyflow-t24-30secs) |
| AP-Adapter | 의미: 장르·스타일 변환<br>인스턴스: 악기 교체 | 확산 U-Net + 오디오 프롬프트 어댑터 | <a href="https://arxiv.org/abs/2407.16564"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/fundwotsai2001/AP-adapter"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [📁 어댑터](https://drive.google.com/drive/folders/1LkIe3-_4nqvDJQqEgglbyj9AMFkn0TLd)<br>[🤗 기반 모델](https://huggingface.co/cvssp/audioldm2-large) |
| AnchorSteer | 의미: 장르·스타일<br>인스턴스: 악기 변경 | 확산 DiT + 구조·개념 어댑터 | <a href="https://arxiv.org/abs/2605.31053"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/hengtsune1024/AnchorSteer"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 개념 가중치](https://huggingface.co/heng1024/AnchorSteer-weights)<br>[📁 구조 어댑터](https://drive.google.com/drive/folders/1Q9B333jcq1czA11JKTbM-DHANJ8YqGbP)<br>[🤗 기반 모델(약관 동의)](https://huggingface.co/stabilityai/stable-audio-open-1.0) |

<a id="methods-audio"></a>

#### 일반 오디오 모델 (Audio)

| 모델 | 편집 유형 | 모델 구조 | 논문 | 코드 | 모델 가중치 |
| --- | --- | --- | --- | --- | --- |
| MMEdit | 음향: 음량<br>인스턴스: 이벤트 추가·삭제·교체·순서 변경 | 오디오 언어 모델 + 확산 MMDiT | <a href="https://arxiv.org/abs/2512.20339"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ty0402/MMEdit"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 가중치](https://huggingface.co/CocoBro/MMEdit) |
| SAO-Instruct | 음향: 필터링·잡음 제거·복원<br>의미: 음높이·속도<br>인스턴스: 이벤트 조작 | 확산 DiT(Stable Audio Open) | <a href="https://arxiv.org/abs/2510.22795"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ETH-DISCO/sao-instruct"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 가중치](https://huggingface.co/disco-eth/sao-instruct) |
| SmartDJ-Editor | 음향: 음량·잔향·스펙트럼 색채<br>인스턴스: 이벤트 추가·삭제·추출·위치 변경 | 확산 Transformer(U-DiT) | <a href="https://arxiv.org/abs/2509.21625"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/penn-waves-lab/SmartDJ"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 편집기 가중치](https://huggingface.co/ztlan/SmartDJ) |
| AudioEditor | 인스턴스: 이벤트 추가·삭제·교체 | 확산 U-Net(Auffusion) | <a href="https://arxiv.org/abs/2409.12466"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/NKU-HLT/AudioEditor"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 기반 모델](https://huggingface.co/auffusion/auffusion-full-no-adapter) |
| CoherentAVEdit | 인스턴스: 비디오 조건부 소리 이벤트 교체 | 플로 매칭 Transformer(MMAudio) | <a href="https://arxiv.org/abs/2512.07209"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/SonyResearch/CoherentAVEdit"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 가중치](https://huggingface.co/masato-a-ishii/CoherentAVEdit) |

---

<a id="training-based-audio-editing"></a>

## 🧪 학습 기반 오디오 편집

학습 기반 오디오 편집 방법은 추론 전에 지도 학습용 쌍, 의사 쌍 또는 지시 기반 삼중항으로 편집 동작을 학습합니다. 편집 목표, 조건 준수, 보존 제약을 명시적으로 최적화하여 안정적이고 제어 가능한 편집을 구현합니다. 본 서베이는 감독 신호와 조건화 방식에 따라 기존 연구를 세 범주로 나누고 핵심 방법과 적용 범위를 논의합니다.

<p align="center">
  <img src="assets/train-based.png" alt="학습 기반 오디오 편집 방법 개요" width="900">
</p>

<p align="center">
  <em>그림 2: 학습 기반 오디오 편집 방법 개요.</em>
</p>


| 패러다임 | 설명 | 대표 적용 범위 |
| --- | --- | --- |
| 작업 특화 학습 | 미리 정의된 편집 기능이나 영역에 맞춰 모델을 최적화합니다. | 텍스트 기반 음성 편집, 운율 교정, 음원 분리, 음악 스템 분리 |
| 참조·속성 기반 학습 | 참조 오디오, 스타일 예시 또는 속성 레이블로 편집 방향을 지정합니다. | 음성 변환, 음색 전이, 감정 편집, 믹싱 스타일 전이 |
| 지시 조건 학습 | 지시–입력–출력 삼중항을 통해 자연어 편집 요청을 따르도록 학습합니다. | 추가, 삭제, 교체, 인페인팅, 초해상도, 음악 리믹싱, 표현 개선 |


---

<a id="training-free-audio-editing"></a>

## 🪄 추가 학습 없는 오디오 편집

추가 학습이 필요 없는 오디오 편집 방법은 모델 파라미터를 갱신하지 않고 사전 학습된 오디오 생성 모델을 편집에 활용합니다. 역변환, 어텐션 제어, 프롬프트·가이던스 조정, 마스크 기반 제약 등 추론 단계의 메커니즘을 조작합니다. 기존 방법을 다음과 같은 메커니즘으로 나누며, 이들은 위치 지정, 보존 성능, 제어 가능성을 높이기 위해 함께 사용되기도 합니다. 토큰 기반 자기회귀 모델은 추가 학습 없는 편집에 상대적으로 덜 적합하므로, 이 절에서는 비자기회귀 패러다임, 특히 확산 기반 파운데이션 모델에 초점을 맞춥니다.

<p align="center">
  <img src="assets/train-free.png" alt="추가 학습 없는 오디오 편집 방법 개요" width="900">
</p>

<p align="center">
  <em>그림 3: 추가 학습 없는 오디오 편집 방법 개요.</em>
</p>



| 패러다임 | 설명 | 대표 적용 범위 |
| --- | --- | --- |
| 역변환 기반 편집 | 원본 오디오를 사전 학습된 생성 모델의 잠재·잡음·궤적 공간으로 역매핑한 후 조건이나 샘플링 궤적을 수정하여 편집합니다. | DDPM/DDIM 역변환, 잠재 공간 역변환, 플로 기반 역변환, 음성·음악 복원 및 편집 |
| 어텐션 제어 편집 | 파라미터를 갱신하지 않고 내부 어텐션 패턴을 수정하거나 재사용하여 사전 학습된 생성 모델을 유도합니다. | 교차 어텐션 기반 이벤트 위치 지정, 자기 어텐션 기반 보존, 프롬프트 수준 조작 |
| 마스크·구간 유도 편집 | 파형, 스펙트로그램, 잠재 표현 또는 음원 성분 공간에서 편집할 영역과 보존할 영역을 지정합니다. | 국소 편집, 인페인팅, 복원, 음원 단위 조작 |
| 코덱 모델을 이용한 토큰 단위 편집 | 추론 시 마스킹, 빈 구간 채우기, 이어 생성 또는 선택적 재생성으로 이산 오디오 토큰을 조작합니다. | 음성 인필링, 국소 재합성, 코덱 토큰 편집 |

<a id="representative-training-free-methods"></a>

### 대표적인 추가 학습 없는 편집 방법

| 모델 | 학회 / 학술지 | 오디오 유형 | 편집 유형 | 모델 구조 | 논문 | 코드 | 모델 가중치 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| DirectAudioEdit | - | Music; Audio | 인스턴스: 텍스트 기반 이벤트 교체·추가·삭제 | 확산 U-Net(Tango 2 / AudioLDM2) | <a href="https://arxiv.org/abs/2606.07356"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/NiuTrans/DirectAudioEdit"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 기반 모델(Tango 2)](https://huggingface.co/declare-lab/tango2-full)<br>[🤗 기반 모델(일반 오디오)](https://huggingface.co/cvssp/audioldm2) |
| AudioMorphix | - | Speech; Music; Audio | 의미: 음높이·시간 신축<br>인스턴스: 추가·삭제·교체·시간 이동 | 확산 U-Net(Tango / AudioLDM) | <a href="https://arxiv.org/abs/2505.16076"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://huggingface.co/spaces/JinhuaL1ANG/AudioMorphix/tree/main"><img height="20" src="https://img.shields.io/badge/HuggingFace-Code-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Code"></a> | [🤗 기반 모델(Tango 2)](https://huggingface.co/declare-lab/tango2-full)<br>[🤗 기반 모델(AudioLDM)](https://huggingface.co/cvssp/audioldm-l-full) |
| AudioEditor | ICASSP 2025 | Audio | 인스턴스: 이벤트 추가·삭제·교체 | 확산 U-Net(Auffusion) | <a href="https://arxiv.org/abs/2409.12466"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/NKU-HLT/AudioEditor"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 기반 모델](https://huggingface.co/auffusion/auffusion-full-no-adapter) |
| MelodyFlow | NeurIPS 2024<br>Audio Imagination Workshop | Music | 의미: 장르·분위기·스타일<br>인스턴스: 악기 구성 | 플로 매칭 DiT | <a href="https://arxiv.org/abs/2407.03648"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://huggingface.co/spaces/facebook/MelodyFlow/tree/main"><img height="20" src="https://img.shields.io/badge/HuggingFace-Code-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Code"></a> | [🤗 기반 모델](https://huggingface.co/facebook/melodyflow-t24-30secs) |
| DDPM Inversion (ZETA) | ICML 2024 | Music; Audio | 의미: 음악 스타일<br>인스턴스: 악기·소리 이벤트 변경 | 확산 U-Net(AudioLDM2) | <a href="https://arxiv.org/abs/2402.10009"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/HilaManor/AudioEditingCode"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 기반 모델(일반 오디오)](https://huggingface.co/cvssp/audioldm2)<br>[🤗 기반 모델(음악)](https://huggingface.co/cvssp/audioldm2-music) |
| EdiTTS | INTERSPEECH 2022 | Speech | 의미: 합성 음성의 내용·음높이 편집 | 스코어 기반 확산(Grad-TTS) | <a href="https://arxiv.org/abs/2110.02584"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/neosapience/editts"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [📦 기반 모델](https://github.com/neosapience/editts/tree/master/checkpts) |

---

<a id="resources"></a>

## 📦 자원

<a id="available-datasets"></a>

### 📊 공개 데이터셋

오디오 편집과 제어 가능한 오디오 생성을 위한 공개 데이터셋을 주요 오디오 영역별로 정리했습니다.

이 목록은 모든 데이터셋을 망라하지 않으며, 오디오 편집에 적합하거나 널리 사용되는 데이터셋을 선별한 것입니다. 저장소 관리자가 모든 항목의 이용 가능 여부를 확인했습니다.

**쌍 제공**은 원본–목표 오디오, 혼합 오디오–스템의 대응 관계 또는 제어 조건·연주 기법이 명시적으로 짝지어진 녹음이 공개되었음을 뜻합니다(✅ / ❌). 전사문 공유, 오디오–텍스트 정렬, 오디오–MIDI 정렬만으로는 쌍으로 간주하지 않습니다. **†**는 직접적인 편집 감독 데이터가 아니라 작업 구성이나 변형이 필요한 활용 방식을 나타냅니다. 편집 유형은 본 서베이의 **음향 / 인스턴스 / 의미** 분류를 따릅니다.

길이는 근삿값이며, 동일 자료의 다른 모달리티나 혼합 오디오의 스템 길이를 중복 합산하지 않습니다. **텍스트**는 전사문, 캡션 또는 지시를 뜻하며, 레이블만 포함한 메타데이터는 **주석** 열에 설명합니다.

<a id="speech"></a>

#### 음성 (Speech)

| 이름 | 논문 | 데이터셋 / 코드 | 길이 | 쌍 제공 | 편집 유형 | 주석 | 모달리티 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| VoiceBank+DEMAND (28-spk) | <a href="https://www.pure.ed.ac.uk/ws/portalfiles/portal/26377240/Interspeech2016_Cassia_1.pdf"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://datashare.ed.ac.uk/handle/10283/2791"><img height="20" src="https://img.shields.io/badge/DataShare-Data-2E8B57" alt="DataShare Data"></a> | ≈10 h | ✅ 잡음 포함 / 클린 | 음향 | 전사문; 잡음·SNR 조건 | 오디오, 텍스트 |
| LibriTTS-R | <a href="https://arxiv.org/abs/2305.18802"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://www.openslr.org/141/"><img height="20" src="https://img.shields.io/badge/OpenSLR-Restored-2E8B57" alt="OpenSLR Restored"></a><br><a href="https://www.openslr.org/60/"><img height="20" src="https://img.shields.io/badge/OpenSLR-Original-2E8B57" alt="OpenSLR Original"></a> | ≈585 h | ✅ 원본 / 복원 | 음향; 의미† | 전사문; 화자 레이블; 모델로 복원한 오디오 | 오디오, 텍스트 |
| LibriSpeech | <a href="https://www.danielpovey.com/files/2015_icassp_librispeech.pdf"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://www.openslr.org/12/"><img height="20" src="https://img.shields.io/badge/OpenSLR-Data-2E8B57" alt="OpenSLR Data"></a> | ≈1,000 h | ❌ | 의미†; 인스턴스† | 전사문; 화자·챕터 레이블 | 오디오, 텍스트 |
| VCTK v0.92 | <a href="https://doi.org/10.7488/ds/2645"><img height="20" src="https://img.shields.io/badge/Dataset-Record-brightgreen" alt="Dataset Record"></a> | <a href="https://datashare.ed.ac.uk/handle/10283/3443"><img height="20" src="https://img.shields.io/badge/DataShare-Data-2E8B57" alt="DataShare Data"></a> | ≈44 h | ❌ | 인스턴스†; 의미† | 전사문; 화자·억양 레이블 | 오디오, 텍스트 |
| AISHELL-3 | <a href="https://arxiv.org/abs/2010.11567"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://www.openslr.org/93/"><img height="20" src="https://img.shields.io/badge/OpenSLR-Data-2E8B57" alt="OpenSLR Data"></a> | ≈85 h | ❌ | 의미†; 인스턴스† | 중국어 표준어 전사문; 발음 기호 전사; 화자 레이블 | 오디오, 텍스트 |
| Hi-Fi TTS | <a href="https://arxiv.org/abs/2104.01497"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://www.openslr.org/109/"><img height="20" src="https://img.shields.io/badge/OpenSLR-Data-2E8B57" alt="OpenSLR Data"></a> | ≈292 h | ❌ | 의미†; 인스턴스† | 전사문; 화자 레이블 | 오디오, 텍스트 |
| LJSpeech v1.1 | <a href="https://keithito.com/LJ-Speech-Dataset/"><img height="20" src="https://img.shields.io/badge/Dataset-Release-brightgreen" alt="Dataset Release"></a> | <a href="https://data.keithito.com/data/speech/LJSpeech-1.1.tar.bz2"><img height="20" src="https://img.shields.io/badge/Download-Data-007EC6" alt="Download Data"></a> | ≈24 h | ❌ | 의미† | 전사문; 정규화된 텍스트 | 오디오, 텍스트 |
| RAVDESS (음성) | <a href="https://doi.org/10.1371/journal.pone.0196391"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://zenodo.org/records/1188976"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈1.7 h | ❌ | 의미† | 레이블: 감정, 강도, 화자; 고정 전사문 | 오디오, 텍스트, 비디오 |
| CREMA-D | <a href="https://pmc.ncbi.nlm.nih.gov/articles/PMC4313618/"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://github.com/CheyneyComputerScience/CREMA-D"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://gitlab.com/cs-cooper-lab/crema-d-mirror"><img height="20" src="https://img.shields.io/badge/GitLab-Mirror-FC6D26?logo=gitlab&amp;logoColor=white" alt="GitLab Mirror"></a> | ≈5.3 h | ❌ | 의미† | 레이블: 감정·강도; 지각 평가 점수; 고정 전사문 | 오디오, 텍스트, 비디오 |

<a id="music"></a>

#### 음악 (Music)

| 이름 | 논문 | 데이터셋 / 코드 | 길이 | 쌍 제공 | 편집 유형 | 주석 | 모달리티 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| GTSinger | <a href="https://arxiv.org/abs/2409.13832"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/AaronZ345/GTSinger"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://huggingface.co/datasets/AaronZ345/GTSinger"><img height="20" src="https://img.shields.io/badge/HuggingFace-Dataset-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Dataset"></a><br><a href="https://drive.google.com/drive/folders/1xcdvCxNAEEfJElt7sEP-xT8dMKxn1_Lz"><img height="20" src="https://img.shields.io/badge/Google_Drive-Data-4285F4?logo=googledrive&amp;logoColor=white" alt="Google Drive Data"></a> | 가창 ≈80.6 h<br>+음성 16.2 h | ✅ 제어 조건 / 병렬 녹음 | 의미; 인스턴스† | 레이블: 기법·스타일; 정렬된 가사·음소; 악보 | 오디오, 텍스트, MusicXML |
| Slakh2100 | <a href="https://arxiv.org/abs/1909.08494"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ethman/slakh-utils"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://zenodo.org/records/4599666"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈145 h | ✅ 혼합 오디오 / 스템 | 인스턴스 | 레이블: 악기; 정렬된 MIDI; 스템 메타데이터 | 오디오, MIDI |
| MUSDB18-HQ | <a href="https://arxiv.org/abs/1804.06267"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/sigsep/sigsep-mus-db"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://zenodo.org/records/3338373"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈10 h | ✅ 혼합 오디오 / 스템 | 인스턴스 | 레이블: 보컬, 드럼, 베이스, 기타 소리 | 오디오 |
| MAESTRO v3 | <a href="https://arxiv.org/abs/1810.12247"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://magenta.tensorflow.org/datasets/maestro"><img height="20" src="https://img.shields.io/badge/Project-Page-007EC6" alt="Project Page"></a><br><a href="https://storage.googleapis.com/magentadata/datasets/maestro/v3.0.0/maestro-v3.0.0.zip"><img height="20" src="https://img.shields.io/badge/Download-Data-007EC6" alt="Download Data"></a> | ≈199 h | ❌ | 의미† | 정렬된 MIDI: 음높이, 타이밍, 벨로시티, 페달; 곡 메타데이터 | 오디오, MIDI |
| NSynth | <a href="https://arxiv.org/abs/1704.01279"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://magenta.tensorflow.org/datasets/nsynth"><img height="20" src="https://img.shields.io/badge/Project-Page-007EC6" alt="Project Page"></a> | ≈340 h | ❌ | 인스턴스†; 의미† | 레이블: 악기, 음높이, 벨로시티, 음색 특성 | 오디오 |
| Groove MIDI Dataset | <a href="https://arxiv.org/abs/1905.06118"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://magenta.tensorflow.org/datasets/groove"><img height="20" src="https://img.shields.io/badge/Project-Page-007EC6" alt="Project Page"></a><br><a href="https://storage.googleapis.com/magentadata/datasets/groove/groove-v1.0.0.zip"><img height="20" src="https://img.shields.io/badge/Download-Data-007EC6" alt="Download Data"></a> | ≈13.6 h | ❌ | 의미† | 정렬된 MIDI; 템포·스타일 레이블; 연주 타이밍·벨로시티 | 오디오, MIDI |
| MusicCaps | <a href="https://arxiv.org/abs/2301.11325"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://huggingface.co/datasets/google/MusicCaps"><img height="20" src="https://img.shields.io/badge/HuggingFace-Metadata-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Metadata"></a> | ≈15.3 h | ❌ | 의미†; 인스턴스† | 캡션; 음악적 속성 레이블 | 오디오, 텍스트 |
| MTG-Jamendo | <a href="https://sites.google.com/view/ml4md2019/program"><img height="20" src="https://img.shields.io/badge/Publication-Record-brightgreen" alt="Publication Record"></a> | <a href="https://github.com/MTG/mtg-jamendo-dataset"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://github.com/MTG/mtg-jamendo-dataset#downloading-the-data"><img height="20" src="https://img.shields.io/badge/Download-Data-007EC6" alt="Download Data"></a> | ≈3,770 h | ❌ | 의미†; 인스턴스† | 레이블: 장르, 악기, 분위기·주제 | 오디오 |
| FMA (large) | <a href="https://arxiv.org/abs/1612.01840"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/mdeff/fma"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://os.unil.cloud.switch.ch/fma/fma_large.zip"><img height="20" src="https://img.shields.io/badge/Download-Data-007EC6" alt="Download Data"></a> | ≈888 h | ❌ | 의미† | 레이블: 장르 계층; 곡·아티스트 메타데이터 | 오디오 |

<a id="audio"></a>

#### 일반 오디오 (Audio)

| 이름 | 논문 | 데이터셋 / 코드 | 길이 | 쌍 제공 | 편집 유형 | 주석 | 모달리티 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| FUSS | <a href="https://arxiv.org/abs/2011.00803"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/google-research/sound-separation/tree/master/datasets/fuss"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://zenodo.org/records/3743844"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | 혼합 오디오 ≈61 h | ✅ 혼합 오디오 / 음원; 무잔향 / 잔향 | 인스턴스; 음향 | 음원·시간 메타데이터; 믹싱 파라미터; 이벤트 레이블 없음 | 오디오 |
| AudioSet | <a href="https://research.google/pubs/audio-set-an-ontology-and-human-labeled-dataset-for-audio-events/"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://research.google.com/audioset/download.html"><img height="20" src="https://img.shields.io/badge/Dataset-Metadata-007EC6" alt="Dataset Metadata"></a> | ≈5,790 h | ❌ | 인스턴스† | 레이블: 소리 이벤트 온톨로지; 클립 단위 다중 레이블 | 오디오, 비디오(원본 출처) |
| AudioCaps v1 | <a href="https://aclanthology.org/N19-1011/"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://github.com/cdjkim/audiocaps/tree/master/dataset"><img height="20" src="https://img.shields.io/badge/GitHub-Metadata-181717?logo=github&amp;logoColor=white" alt="GitHub Metadata"></a> | ≈143 h | ❌ | 인스턴스†; 의미† | 캡션: 클립당 설명 1개 또는 5개 | 오디오, 텍스트 |
| Clotho v2.1 | <a href="https://arxiv.org/abs/1910.09387"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://zenodo.org/records/4783391"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈37 h<br>(주석이 있는 클립 5,929개) | ❌ | 인스턴스†; 의미† | 캡션: 클립당 5개; Freesound 키워드 | 오디오, 텍스트 |
| WavCaps | <a href="https://arxiv.org/abs/2303.17395"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/XinhaoMei/WavCaps"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://huggingface.co/datasets/cvssp/WavCaps"><img height="20" src="https://img.shields.io/badge/HuggingFace-Dataset-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Dataset"></a> | ≈7,568 h | ❌ | 인스턴스†; 의미† | LLM 보조 캡션; 원본 설명·메타데이터 | 오디오, 텍스트 |
| FSD50K | <a href="https://arxiv.org/abs/2010.00475"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://zenodo.org/records/4060432"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈108 h | ❌ | 인스턴스† | 레이블: 소리 이벤트 200종; 클립 단위 다중 레이블 | 오디오 |
| ESC-50 | <a href="https://www.karolpiczak.com/papers/Piczak2015-ESC-Dataset.pdf"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://github.com/karolpiczak/ESC-50"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | ≈2.8 h | ❌ | 인스턴스† | 레이블: 환경음 50종 | 오디오 |
| UrbanSound8K | <a href="https://drive.google.com/file/d/0B2SQvWn0_78BX2wtbWZLVnRhSDg/view?usp=sharing"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://urbansounddataset.weebly.com/urbansound8k.html"><img height="20" src="https://img.shields.io/badge/Project-Page-007EC6" alt="Project Page"></a><br><a href="https://zenodo.org/records/1203745"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈8.8 h | ❌ | 인스턴스† | 레이블: 도시 소리 10종; 두드러짐; 원본 타임스탬프 | 오디오 |
| VGGSound | <a href="https://arxiv.org/abs/2004.14368"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/hche11/VGGSound/tree/master/data"><img height="20" src="https://img.shields.io/badge/GitHub-Metadata-181717?logo=github&amp;logoColor=white" alt="GitHub Metadata"></a> | ≈550 h | ❌ | 인스턴스† | 레이블: 시청각 이벤트 범주; 비디오 타임스탬프 | 오디오, 비디오(원본 출처) |

<a id="unified"></a>

#### 통합 (Unified)

이 코퍼스들은 음성, 음악, 일반 소리를 함께 포함합니다.

| 이름 | 논문 | 데이터셋 / 코드 | 길이 | 쌍 제공 | 편집 유형 | 주석 | 모달리티 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| AudioEdit (Audio-Omni) | <a href="https://arxiv.org/abs/2604.10708"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ZeyueT/Audio-Omni"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://huggingface.co/datasets/HKUSTAudio/AudioEdit"><img height="20" src="https://img.shields.io/badge/HuggingFace-Dataset-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Dataset"></a> | ≈2,686 h<br>(작업 쌍 966,794개) | ✅ 원본 / 편집 목표 | 인스턴스 | 지시: 추가, 제거, 추출, 음원 변환 | 오디오, 텍스트 |
| Divide and Remaster v2 | <a href="https://arxiv.org/abs/2110.09958"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/darius522/dnr-utils"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://zenodo.org/records/6949108"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈81 h | ✅ 혼합 오디오 / 스템 | 인스턴스 | 전사문; 음악 장르; 소리 레이블·타임스탬프 | 오디오, 텍스트 |
| MUSAN | <a href="https://arxiv.org/abs/1510.08484"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://www.openslr.org/17/"><img height="20" src="https://img.shields.io/badge/OpenSLR-Data-2E8B57" alt="OpenSLR Data"></a> | ≈109 h | ❌ | 음향†; 인스턴스† | 레이블: 음성·음악·잡음; 음성 및 음악 메타데이터 | 오디오 |

<a id="data-tools"></a>

### 🛠️ 데이터 도구

편집 데이터를 구축하거나 기존 녹음에 주석을 부여하는 오픈소스 도구입니다. **지원 작업 유형**은 본 서베이의 **음향 / 의미 / 인스턴스** 분류를 따르며, 각 도구로 구축할 수 있는 편집 감독 신호의 유형을 나타냅니다. **통합(Unified)**에는 음성, 음악, 일반 오디오 전반에 적용할 수 있는 도구를 포함합니다.

#### 데이터 생성 도구

합성, 음원 분리, 믹싱, 신호 처리를 통해 오디오 샘플과 원본–목표 오디오 쌍을 구축합니다.

##### 음성 (Speech)

| 도구 | 지원 작업 유형 | 생성 내용 | 제어 단위 | 코드 | 모델 |
| --- | --- | --- | --- | --- | --- |
| Qwen3-TTS | 의미; 인스턴스 | 지시로 발화 방식 또는 참조 화자를 제어하는 텍스트 정렬 음성. | 발화 단위 | <a href="https://github.com/QwenLM/Qwen3-TTS"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/Qwen/Qwen3-TTS-12Hz-1.7B-Base"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Base-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Base"></a><br><a href="https://huggingface.co/Qwen/Qwen3-TTS-12Hz-1.7B-CustomVoice"><img height="20" src="https://img.shields.io/badge/Hugging_Face-CustomVoice-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face CustomVoice"></a> |
| CosyVoice3 | 의미; 인스턴스 | 음성 복제와 프롬프트 기반 언어·감정·발화 방식 제어를 지원하는 텍스트 정렬 음성. | 발화; 발음 단위 | <a href="https://github.com/QwenAudio/CosyVoice"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/FunAudioLLM/Fun-CosyVoice3-0.5B-2512"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |
| MaskGCT | 의미; 인스턴스 | 참조 음색과 설정 가능한 전체 길이를 갖춘 텍스트 조건 음성. | 발화; 전체 길이 | <a href="https://github.com/open-mmlab/Amphion/tree/main/models/tts/maskgct"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/amphion/MaskGCT"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |
| Seed-VC | 인스턴스 | 화자·음색 교체를 위해 원본 음성과 쌍을 이루는 음성 변환 녹음. | 발화 / 원본 녹음 | <a href="https://github.com/Plachtaa/seed-vc"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/Plachta/Seed-VC"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |
| AuK | 음향; 의미; 인스턴스 | 내용, 발화 방식, 음색, 음질 개선, 목표 화자 작업을 위한 지시 기반 편집 음성. | 발화; 텍스트로 지정한 단어·구 | <a href="https://github.com/Tencent-Hunyuan/AuK"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/tencent/AuK"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |

##### 음악 (Music)

| 도구 | 지원 작업 유형 | 생성 내용 | 제어 단위 | 코드 | 모델 |
| --- | --- | --- | --- | --- | --- |
| MusicGen | 의미 | 스타일·내용을 제어하는 샘플을 위한 텍스트·멜로디 조건 음악 클립과 이어 생성 결과. | 클립; 멜로디 시퀀스 | <a href="https://github.com/facebookresearch/audiocraft"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/facebook/musicgen-melody"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Melody-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Melody"></a> |
| Demucs | 인스턴스 | 추출·제거·리믹싱 쌍을 구성하기 위한 보컬, 드럼, 베이스 및 기타 스템 추정치. | 스템 / 트랙 | <a href="https://github.com/facebookresearch/demucs"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://dl.fbaipublicfiles.com/demucs/hybrid_transformer/955717e8-8726e21a.th"><img height="20" src="https://img.shields.io/badge/Model-Checkpoint-2E8B57" alt="Model Checkpoint"></a> |
| Spleeter | 인스턴스 | 음원 제거·추출·리믹싱을 위한 2·4·5개 스템 분리 추정치. | 스템 / 트랙 | <a href="https://github.com/deezer/spleeter"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://github.com/deezer/spleeter/releases/tag/v1.4.0"><img height="20" src="https://img.shields.io/badge/GitHub-Checkpoints-181717?logo=github&amp;logoColor=white" alt="GitHub Checkpoints"></a> |
| FluidSynth | 의미; 인스턴스 | MIDI와 SoundFont로 렌더링하며 음표, 벨로시티, 악기 배정과 정렬된 오디오. | 음표; MIDI 제어 이벤트 / 트랙 | <a href="https://github.com/FluidSynth/fluidsynth"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |

##### 일반 오디오 (Audio)

| 도구 | 지원 작업 유형 | 생성 내용 | 제어 단위 | 코드 | 모델 |
| --- | --- | --- | --- | --- | --- |
| AudioLDM 2 | 인스턴스 | 삽입·교체 샘플의 음원 소재로 사용할 텍스트 조건 소리 클립. | 클립 | <a href="https://github.com/haoheliu/AudioLDM2"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/cvssp/audioldm2"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |
| AudioSep | 인스턴스 | 추출·제거 쌍을 구성하기 위해 혼합 오디오에서 텍스트로 선택한 음원의 추정치. | 설명으로 지정한 음원 / 클립 | <a href="https://github.com/Audio-AGI/AudioSep"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/spaces/Audio-AGI/AudioSep/tree/main/checkpoint"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Checkpoints-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Checkpoints"></a> |
| Scaper | 음향; 인스턴스 | 이벤트 레이블, 시작·종료 시각, SNR 및 선택적인 개별 이벤트 트랙을 포함하는 합성 사운드스케이프. | 이벤트; 시작 시각 / 길이 / SNR | <a href="https://github.com/justinsalamon/scaper"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |
| SpatialScaper | 음향; 인스턴스 | 이벤트 활동, 음원 궤적, 실내 응답 조건을 포함하는 공간 사운드스케이프. | 이벤트 / 궤적 / 장면 | <a href="https://github.com/marl/SpatialScaper"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |

##### 통합 (Unified)

| 도구 | 지원 작업 유형 | 생성 내용 | 제어 단위 | 코드 | 모델 |
| --- | --- | --- | --- | --- | --- |
| SAM-Audio | 인스턴스 | 추출·제거·리믹싱 샘플을 위해 프롬프트로 선택한 목표 오디오와 잔여 오디오. | 음원; 시간 구간 프롬프트 | <a href="https://github.com/facebookresearch/sam-audio"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/facebook/sam-audio-large"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a><br>접근 신청 필요 |
| Audiomentations | 음향; 의미 | 잡음, 게인, 필터링 등의 변환으로 클린·열화 쌍과 음높이·템포 대비 쌍을 만드는 증강 오디오. | 클립; 슬라이싱으로 선택한 구간 | <a href="https://github.com/iver56/audiomentations"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |
| Pedalboard | 음향 | EQ, 게인, 압축, 왜곡, 잔향 효과로 드라이·웨트 또는 클린·열화 쌍을 구성하는 오디오. | 클립 / 처리 블록 | <a href="https://github.com/spotify/pedalboard"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |
| Pyroomacoustics | 음향; 인스턴스 | 배치된 음원으로부터 생성한 실내 임펄스 응답과 마이크 혼합 오디오. 무잔향·잔향 쌍 포함. | 장면 / 음원 위치 | <a href="https://github.com/LCAV/pyroomacoustics"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |

#### 데이터 주석 도구

기존 오디오에서 내용, 속성, 시간 정보를 추출하거나 주석을 작성하는 도구입니다.

##### 음성 (Speech)

| 도구 | 지원 작업 유형 | 주석 내용 | 주석 단위 | 코드 | 모델 |
| --- | --- | --- | --- | --- | --- |
| Montreal Forced Aligner (MFA) | 의미 | 음성과 주어진 전사문·발음 사전을 정렬하여 얻은 단어·음소 경계. | 단어 / 음소 | <a href="https://github.com/MontrealCorpusTools/Montreal-Forced-Aligner"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://mfa-models.readthedocs.io/en/latest/acoustic/index.html"><img height="20" src="https://img.shields.io/badge/Model-Acoustic%20models-2E8B57" alt="Model Acoustic models"></a> |
| WhisperX | 의미 | 언어별 정렬 모델로 얻은 단어 타임스탬프를 포함하는 ASR 전사문. | 발화 / 단어 | <a href="https://github.com/m-bain/whisperX"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/Systran/faster-whisper-large-v3"><img height="20" src="https://img.shields.io/badge/Hugging_Face-ASR-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face ASR"></a><br><a href="https://huggingface.co/facebook/wav2vec2-large-960h-lv60-self"><img height="20" src="https://img.shields.io/badge/Hugging_Face-EN%20aligner-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face EN aligner"></a> |
| Qwen3-ASR + ForcedAligner | 의미 | 공개 ASR·강제 정렬 모델로 얻은 전사문, 언어 레이블, 텍스트 단위 타임스탬프. | 발화 / 단어 | <a href="https://github.com/QwenLM/Qwen3-ASR"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/Qwen/Qwen3-ASR-1.7B"><img height="20" src="https://img.shields.io/badge/Hugging_Face-ASR-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face ASR"></a><br><a href="https://huggingface.co/Qwen/Qwen3-ForcedAligner-0.6B"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Aligner-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Aligner"></a> |
| pyannote.audio | 인스턴스 | 화자 레이블이 있는 발화 턴과 겹치는 화자의 활동. | 화자 턴 / 구간 | <a href="https://github.com/pyannote/pyannote-audio"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/pyannote/speaker-diarization-community-1"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Community--1-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Community-1"></a><br>이용 약관 동의 필요 |
| Silero VAD | 인스턴스 | 음성·비음성 확률과 검출된 음성 시작·종료 시각. | 프레임 / 음성 구간 | <a href="https://github.com/snakers4/silero-vad"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://github.com/snakers4/silero-vad/tree/master/src/silero_vad/data"><img height="20" src="https://img.shields.io/badge/GitHub-Weights-181717?logo=github&amp;logoColor=white" alt="GitHub Weights"></a> |
| emotion2vec+ | 의미 | 음성 감정 레이블과 점수, 선택적으로 추출하는 학습된 감정 표현. | 발화(레이블); 프레임(특징) | <a href="https://github.com/ddlBoJack/emotion2vec"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/emotion2vec/emotion2vec_plus_large"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Large-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Large"></a> |
| FunASR / SenseVoiceSmall | 의미; 인스턴스 | 전사문, 언어·감정 태그, 웃음·박수 등의 소리 이벤트 태그. | 발화 / VAD 구간 | <a href="https://github.com/modelscope/FunASR"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/FunAudioLLM/SenseVoiceSmall"><img height="20" src="https://img.shields.io/badge/Hugging_Face-SenseVoiceSmall-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face SenseVoiceSmall"></a> |
| Praat / Parselmouth | 음향; 의미 | 음높이, 포먼트, 강도 궤적; Praat에서 수동으로 정의한 TextGrid 시점과 구간. | 프레임; 단어 / 음소 / 구간(수동) | <a href="https://github.com/praat/praat.github.io"><img height="20" src="https://img.shields.io/badge/GitHub-Praat-181717?logo=github&amp;logoColor=white" alt="GitHub Praat"></a><br><a href="https://github.com/YannickJadoul/Parselmouth"><img height="20" src="https://img.shields.io/badge/GitHub-Parselmouth-181717?logo=github&amp;logoColor=white" alt="GitHub Parselmouth"></a> |  |

##### 음악 (Music)

| 도구 | 지원 작업 유형 | 주석 내용 | 주석 단위 | 코드 | 모델 |
| --- | --- | --- | --- | --- | --- |
| RMVPE | 의미 | 다성 음악에서 추출한 보컬 기본 주파수(F0) 궤적. | 프레임 | <a href="https://github.com/Dream-High/RMVPE"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://drive.google.com/file/d/1JNtNT37KiLq9uFQqHk7JFs-3trxd3bRh/view"><img height="20" src="https://img.shields.io/badge/Google_Drive-ROSVOT%20bundle-4285F4?logo=googledrive&amp;logoColor=white" alt="Google Drive ROSVOT bundle"></a> |
| CREPE | 의미 | 단선율 오디오의 F0 추정치와 신뢰도. | 프레임 | <a href="https://github.com/marl/crepe"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://github.com/marl/crepe/tree/models"><img height="20" src="https://img.shields.io/badge/GitHub-Weights-181717?logo=github&amp;logoColor=white" alt="GitHub Weights"></a> |
| ROSVOT | 의미 | 가창 음표의 음높이와 시작·종료 시각, RWBD 구성 요소로 얻은 단어 경계. | 음표 / 단어 | <a href="https://github.com/RickyL-2000/ROSVOT"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://drive.google.com/file/d/1JNtNT37KiLq9uFQqHk7JFs-3trxd3bRh/view"><img height="20" src="https://img.shields.io/badge/Google_Drive-Checkpoints-4285F4?logo=googledrive&amp;logoColor=white" alt="Google Drive Checkpoints"></a> |
| Basic Pitch | 의미 | MIDI로 내보내는 다성 음표 이벤트와 피치 벤드. 한 번에 한 악기를 처리할 때 가장 효과적. | 음표; 프레임 단위 음높이 곡선 | <a href="https://github.com/spotify/basic-pitch"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://github.com/spotify/basic-pitch/tree/main/basic_pitch/saved_models"><img height="20" src="https://img.shields.io/badge/GitHub-Weights-181717?logo=github&amp;logoColor=white" alt="GitHub Weights"></a> |
| All-In-One Music Structure Analyzer | 의미 | 템포, 박·마디 첫 박 타임스탬프, 벌스·코러스·브리지 등의 구간 레이블. | 박 / 마디 첫 박 / 구간 | <a href="https://github.com/mir-aidj/all-in-one"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/taejunkim/allinone"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Models-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Models"></a> |
| Music Flamingo | 의미; 인스턴스 | 악기 구성, 화성, 분위기, 구조, 가사에 관한 음악 캡션과 질의응답 주석. | 클립 / 전체 트랙(자유 형식 텍스트) | <a href="https://github.com/NVIDIA/audio-flamingo/tree/music_flamingo"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/nvidia/music-flamingo-hf"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |

##### 일반 오디오 (Audio)

| 도구 | 지원 작업 유형 | 주석 내용 | 주석 단위 | 코드 | 모델 |
| --- | --- | --- | --- | --- | --- |
| PANNs | 인스턴스 | 공개된 결정 수준 검출 모델로 얻은 소리 이벤트 범주 점수와 프레임별 활동. | 클립 / 프레임 | <a href="https://github.com/qiuqiangkong/audioset_tagging_cnn"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://zenodo.org/records/3987831"><img height="20" src="https://img.shields.io/badge/Zenodo-Models-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Models"></a> |
| HTS-AT | 인스턴스 | 소리 이벤트 태그와 위치 추정 모드에서의 시간별 클래스 활성화 추정치. | 클립 / 프레임 | <a href="https://github.com/RetroCirce/HTS-Audio-Transformer"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://drive.google.com/drive/folders/1f5VYMk0uos_YnuBshgmaTVioXbs7Kmz6?usp=sharing"><img height="20" src="https://img.shields.io/badge/Google_Drive-Models-4285F4?logo=googledrive&amp;logoColor=white" alt="Google Drive Models"></a> |
| YAMNet | 인스턴스 | 겹치는 오디오 창에서 예측한 521개 소리 이벤트 범주의 점수. | 0.96 s 창; 0.48 s 이동 간격 | <a href="https://github.com/tensorflow/models/tree/master/research/audioset/yamnet"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://storage.googleapis.com/audioset/yamnet.h5"><img height="20" src="https://img.shields.io/badge/Model-Checkpoint-2E8B57" alt="Model Checkpoint"></a> |

##### 통합 (Unified)

| 도구 | 지원 작업 유형 | 주석 내용 | 주석 단위 | 코드 | 모델 |
| --- | --- | --- | --- | --- | --- |
| Qwen3-Omni Captioner | 음향; 의미; 인스턴스 | 음성, 음악, 소리 이벤트, 음향 특성을 다루는 상세 오디오 캡션. | 클립 / 녹음(자유 형식 텍스트) | <a href="https://github.com/QwenLM/Qwen3-Omni"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/Qwen/Qwen3-Omni-30B-A3B-Captioner"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Captioner-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Captioner"></a> |
| Audio Flamingo 3 | 의미; 인스턴스 | 프롬프트에 따라 생성한 전사문, 캡션, 이벤트 설명, 오디오 질의응답 주석. | 클립 / 녹음(자유 형식 텍스트) | <a href="https://github.com/NVIDIA/audio-flamingo/tree/audio_flamingo_3"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/nvidia/audio-flamingo-3-hf"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |
| Label Studio | 음향; 의미; 인스턴스 | 설정 가능한 오디오 템플릿으로 사람이 작성한 클립 레이블, 시간 구간 레이블, 전사문. | 클립 / 수동 선택 구간 | <a href="https://github.com/HumanSignal/label-studio"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |

<a id="benchmarks"></a>

### 🧪 평가 벤치마크

오디오 편집을 위한 공개 평가 자원입니다. **편집 범주**는 본 서베이의 **음향 / 의미 / 인스턴스 / 복합** 분류를 따르며, **복합**은 하나의 요청에 서로 다른 편집 범주가 함께 포함되는 경우를 뜻합니다. **평가 방식**은 점수 산출 방식을 나타내며, **전문 모델**, **MLLM**, **Hybrid(혼합형, 에이전트 기반 평가 포함)**로 구분합니다.


#### MMAE

- **요약:** **2,000개 사례(≈8.0 h)**, 6개 난이도 수준, **17,741개 검증 기준**으로 음성·음악·일반 소리 및 혼합 환경에서의 지시 준수와 내용 보존을 평가합니다.
- **논문:** [arXiv](https://arxiv.org/abs/2606.07229); **코드:** [GitHub](https://github.com/ddlBoJack/MMAE); **데이터셋:** [Hugging Face](https://huggingface.co/datasets/BoJack/MMAE).
- **오디오 모달리티:** 음성; 음악; 일반 오디오.
- **편집 범주:** 음향; 의미; 인스턴스; 복합.
- **평가 방식:** **MLLM** — Qwen3-Omni가 개별 기준을 판정하고 다수결로 지시 준수율(IFR), 일관성 비율(CR), 완전 일치율(EMR)을 산출합니다.
- **보고된 최고 성능:**
  - **단일 모델:** [원래 비교](https://arxiv.org/pdf/2606.07229)의 전체 벤치마크에서 **Step-Audio-EditX**는 IFR(**44.86%**)과 CR(**58.88%**)이, **Ming-UniAudio**는 EMR(**3.20%**)이 가장 높습니다. **Audio-Omni**는 별도의 **801개 사례, ≤10 s** 부분집합에서 **EMR 4.99%**를 기록했습니다. 더 최근의 [Prompt Enhancer 없는 AuK 베이스라인](https://github.com/Audio-Editing-Challenge/Audio-Editing-Challenge-Baseline#results)은 **1,003개 단일 연산 사례 부분집합**에서 **EMR 7.58%**를 보고했습니다.
  - **에이전트 / LLM 보조 시스템:** LLM 라우터, DSP, SAM-Audio, AuK를 결합한 [챌린지 에이전트 베이스라인](https://github.com/Audio-Editing-Challenge/Audio-Editing-Challenge-Baseline#results)은 **전체 2,000개 사례**에서 **EMR 7.45%, IFR 44.06%, CR 74.63%**를 보고했습니다. 별도로 [Prompt Enhancer를 사용한 AuK-Flash](https://arxiv.org/html/2609.08936v1#A1.T7)는 **MMAE-Speech에서만 EMR 13.85%**를 기록했습니다. 평가 범위가 달라 직접 비교할 수 없습니다.

#### SpeechEditBench

- **요약:** **4,700개 사례(≈9.4 h)**로 2개 언어의 음성 편집에서 편집 성공과 언어 내용 보존을 분리해 평가하며, 7개 단일 속성과 다중 속성 지시를 다룹니다.
- **논문:** [arXiv](https://arxiv.org/abs/2606.01804); **코드:** [GitHub](https://github.com/daxintan-cuhk/SpeechEditBench); **데이터셋:** [Hugging Face, v1.1](https://huggingface.co/datasets/DiscreteSpeech/SpeechEditBench/tree/v1.1).
- **오디오 모달리티:** 음성.
- **편집 범주:** 음향; 의미; 인스턴스; 복합.
- **평가 방식:** **Hybrid(혼합형)** — ASR, 화자 검증, 음향·운율 측정, Gemini 오디오 판정기를 결합하여 목표 달성, 내용 보존, 두 조건의 동시 성공률을 계산합니다.
- **보고된 최고 성능:**
  - **단일 모델:** 작업별로 [GPT-Realtime](https://arxiv.org/html/2606.01804v3#S5)은 **내용 96.67%, 스타일 68.67%, 준언어적 표현 47.00%**의 동시 성공률을 기록했습니다. Gemini-Live는 **감정 27.79%, 조합 작업 11.00%**를 달성했습니다. 더 최근의 [AuK 비교](https://arxiv.org/html/2609.08936v1#S7.SS3)는 **운율 동시 성공률 71.33%**를 보고했지만, 5개 작업 유형만 다룹니다.

#### Ming-Freeform-Audio-Edit

- **요약:** **약 3.3k개 지시 사례**로 타임스탬프 없이 지시에 따라 수행하는 음성 편집을 평가하며, 중국어·영어 Basic/Full 어휘 편집과 5개 속성 제어 작업을 다룹니다.
- **논문:** [arXiv](https://arxiv.org/abs/2511.05516); **코드:** [GitHub](https://github.com/inclusionAI/Ming-Freeform-Audio-Edit); **데이터셋:** [Hugging Face](https://huggingface.co/datasets/inclusionAI/Ming-Freeform-Audio-Edit-Benchmark); **프로젝트 페이지:** [Ming-UniAudio](https://xqacmer.github.io/Ming-Unitok-Audio.github.io/).
- **오디오 모달리티:** 음성.
- **편집 범주:** 음향; 의미.
- **평가 방식:** **Hybrid(혼합형)** — Whisper/Paraformer와 WavLM으로 전사와 화자 보존을 측정하고, 신호 측정으로 속도·음량 제어를 평가하며, 오디오를 처리하는 판정기로 감정·방언 변환을 평가합니다.
- **보고된 최고 성능:**
  - **단일 모델:** [AuK](https://arxiv.org/html/2609.08936v1#S7.SS3)는 **Full 중국어 / 영어**에서 삭제·삽입·치환을 평균했을 때 **WER 3.09% / 3.96%**, **편집 정확도 91.47% / 85.25%**를 보고했으며, 확인한 어휘 편집 비교에서 가장 좋은 결과를 보였습니다.

#### Step-Audio-Edit-Benchmark

- **요약:** **화자 8명과 텍스트 프롬프트 8,800개**로 감정, 발화 스타일, 준언어적 표현의 편집 및 반복 편집을 평가합니다. 참조 음성을 공개했으며, **출력 길이는 합성 결과에 따라 달라집니다**.
- **논문:** [arXiv](https://arxiv.org/abs/2511.03601); **코드:** [GitHub](https://github.com/stepfun-ai/Step-Audio-Edit-Benchmark); **데이터셋:** [Prompt texts](https://github.com/stepfun-ai/Step-Audio-Edit-Benchmark/tree/main/data) · [Reference audio](https://github.com/stepfun-ai/Step-Audio-Edit-Benchmark/tree/main/prompt_audios); **프로젝트 페이지:** [Step-Audio-EditX](https://stepaudiollm.github.io/step-audio-editx/).
- **오디오 모달리티:** 음성.
- **편집 범주:** 의미.
- **평가 방식:** **MLLM** — Gemini-2.5-Pro로 감정·스타일 분류 정확도를 측정하고 준언어적 표현의 구현 정도를 1–3점으로 평가합니다.
- **보고된 최고 성능:**
  - **단일 모델:** 공개된 원래 입력 조건의 비교에서 [Step-Audio-EditX](https://arxiv.org/html/2511.03601v2#S5)는 **3회 편집 반복** 후 **감정 정확도 71.0%, 스타일 정확도 66.2%**를, 1회 반복 후 **준언어적 표현 점수 2.89/3**을 보고했습니다.

#### LyricEditBench (INTERSPEECH 2026)

- **요약:** **2개 언어의 사례 7,200개에 각각 ≤15 s의 멜로디 참조**를 사용하여, 6개 가사 편집 시나리오와 동일 음색·교차 음색 설정에서 멜로디를 보존하는 가사 수정을 평가합니다.
- **논문:** [arXiv](https://arxiv.org/abs/2603.24589); **코드:** [GitHub](https://github.com/ASLP-lab/YingMusic-Singer-Plus); **데이터셋:** [Hugging Face](https://huggingface.co/datasets/ASLP-lab/LyricEditBench); **프로젝트 페이지:** [YingMusic-Singer-Plus](https://aslp-lab.github.io/YingMusic-Singer-Plus-Demo/).
- **오디오 모달리티:** 음악.
- **편집 범주:** 의미; 인스턴스; 복합(교차 음색 설정에서 가사 수정과 가수 정체성 전이를 함께 수행).
- **평가 방식:** **전문 모델** — 가창 ASR의 음소 오류율(PER), WavLM의 화자 유사도, RMVPE의 F0 상관계수, VocalVerse2의 보컬 품질을 사용하며 사람의 청취 평가를 보완적으로 수행합니다.
- **보고된 최고 성능:**
  - **단일 모델:** 공개된 비교에서 [YingMusic-Singer](https://arxiv.org/html/2603.24589v3#S4)는 가사 명료도, 멜로디 준수, 보컬 품질에서 Vevo2보다 우수했습니다. **중국어 부분 치환·동일 음색** 설정에서 **PER 2.14%, F0 상관계수 0.9615**를 기록했습니다. 이 설정의 화자 유사도는 Vevo2가 더 높습니다.

#### ZoME-Bench (ACM MM 2025)

- **요약:** 악기, 장르, 분위기, 리듬, 멜로디, 배경 변경을 다루는 **음악 편집 사례 1,100개(각 10 s, 사례별 합산 ≈3.1 h)**를 제공합니다. 캡션과 지시를 포함하여 프롬프트 기반·지시 기반 평가를 모두 지원합니다.
- **논문:** [MEDIC](https://arxiv.org/abs/2407.13220); **코드:** [MEDIC 저장소](https://github.com/liuhuadai/MEDIC)(구현 미공개) · [후속 평가 코드](https://github.com/hengtsune1024/AnchorSteer/tree/master/eval); **데이터셋:** [Hugging Face 메타데이터](https://huggingface.co/datasets/liuhuadai/ZoME-Bench)(원본 오디오는 MusicCaps/YouTube에서 별도 확보); **프로젝트 페이지:** [MEDIC](https://medic-edit.github.io/).
- **오디오 모달리티:** 음악.
- **편집 범주:** 의미; 인스턴스.
- **평가 방식:** **전문 모델** — CLAP, LPAPS, 크로마 유사도 등 오디오–텍스트 정렬, 지각·구조 지표를 사용하고 사람의 평가 점수를 함께 활용합니다.
- **보고된 최고 성능:**
  - **단일 모델 / 비에이전트 편집기:** 후속 [AnchorSteer 악기 편집 비교](https://brianchen1120.github.io/project/anchorsteer/)에서 조건부 변형이 비교 대상 중 가장 높은 **CLAP(0.395)**와 **GAP(0.279)**를 기록했습니다. 무조건부 변형은 구조를 더 잘 보존했습니다(**크로마 유사도 0.470**, 조건부 변형은 **0.238**).

#### MelodiaEdit (AAAI 2026)

- **요약:** 합성 음악과 실제 음악을 결합하여, **공개 원본 클립 180개(중복을 제외한 오디오 ≈0.86 h)에서 구성한 편집 쌍 2,015개**로 음악 구조를 보존하는 악기·장르·분위기 변경을 평가합니다.
- **논문:** [AAAI 논문집](https://ojs.aaai.org/index.php/AAAI/article/view/37204); **코드:** [GitHub](https://github.com/YiYang-SCUT/Melodia)(데이터 공개, 평가 구현 미공개); **데이터셋:** [오디오와 프롬프트](https://github.com/YiYang-SCUT/Melodia/tree/main/MelodiaEdit/MelodiaEdit); **프로젝트 페이지:** [Melodia](https://melodia-edit.github.io/).
- **오디오 모달리티:** 음악.
- **편집 범주:** 의미; 인스턴스.
- **평가 방식:** **전문 모델** — CLAP, LPAPS, 크로마 유사도, FAD, 준수·보존 통합 점수를 사용하며 사람의 청취 평가를 보완적으로 수행합니다.
- **보고된 최고 성능:**
  - **단일 모델:** [공개된 비교](https://ojs.aaai.org/index.php/AAAI/article/download/37204/41166)에서 **Melodia**는 MelodiaEdit에서 가장 높은 **CLAP(0.39)**와 가장 낮은 **LPAPS(3.11)**를 기록했습니다. **MusicMagus**는 **크로마 유사도(0.73)**와 **FAD(0.57)**에서 앞서, 목표 정렬과 내용 보존 사이의 절충을 보여줍니다.

#### AvED-Bench (WACV 2026)

- **요약:** VGGSound에서 선별한 **시청각 클립 110개(각 10 s, ≈18.3 min)**와 원본·목표 설명을 이용하여 소리 이벤트와 시각적 개체의 동기화된 교체를 평가합니다.
- **논문:** [arXiv](https://arxiv.org/abs/2503.20782); **코드:** [GitHub](https://github.com/GenjiB/AVED); **데이터셋:** [벤치마크 CSV](https://genjib.github.io/project_page/AVED/assets/avedit_dataset_v3.csv)(원본 클립은 VGGSound/YouTube에서 별도 확보); **프로젝트 페이지:** [AvED](https://genjib.github.io/project_page/AVED/index.html).
- **오디오 모달리티:** 일반 오디오(비디오 입력 포함).
- **편집 범주:** 인스턴스. 비디오와 소리를 함께 편집한다는 사실만으로 복합 오디오 편집에 해당하지는 않습니다.
- **평가 방식:** **전문 모델** — 임베딩 기반 오디오–텍스트·오디오–비디오 정렬과 지각적 보존 지표를 사용하고 사람의 판단을 함께 활용합니다.
- **보고된 최고 성능:**
  - **단일 모델 / 비에이전트 시스템:** 후속 [CoherentAVEdit 비교](https://arxiv.org/html/2512.07209v2#S4)에서 **VACE → CoherentAVEdit**는 **비디오 6개로 구성된 주관 평가 부분집합**에서 가장 높은 청취 평가 결과를 보고했습니다. **오디오–텍스트 충실도 3.7/5, 시청각 정렬 3.8/5, 구조 보존 3.9/5**입니다. 이는 순차적인 비에이전트 파이프라인이며, 단일 결합 모델이나 전체 데이터셋의 종합 순위를 의미하지 않습니다.

#### AVE-Compass

- **요약:** 28개 편집 연산을 다루는 **원본 비디오 145개(최대 10 s), 지시 196개, 체크리스트 항목 2,688개**로 자유 형식 시청각 편집의 지시 준수와 보존 성능을 진단합니다.
- **논문:** [arXiv](https://arxiv.org/abs/2607.24821); **코드:** [GitHub](https://github.com/NJU-LINK/AVE-Compass); **데이터셋:** [Hugging Face](https://huggingface.co/datasets/NJU-LINK/AVE-Compass); **프로젝트 페이지:** [AVE-Compass](https://ave-compass.github.io/).
- **오디오 모달리티:** 음성; 음악; 일반 오디오(비디오 입력 포함).
- **편집 범주:** 음향; 의미; 인스턴스; 복합(오디오 편집 요청 자체가 서로 다른 범주에 걸치는 경우).
- **평가 방식:** **Hybrid(혼합형)** — 체크리스트 기반 MLLM 판정과 전문 모델을 결합하여 오디오 품질, 시청각·입술 동기화, 시각적 보존을 평가합니다.
- **보고된 최고 성능:**
  - **단일 모델:** [공식 리더보드](https://github.com/NJU-LINK/AVE-Compass#leaderboard)에서 **Wan2.7**은 전체 편집 의도 점수 **42.4/100**(**오디오: 24.8**)으로 가장 높습니다. 등재된 단일 모델 중 오디오 편집 의도 점수는 **LTX2**가 **26.4/100**으로 가장 높습니다.
  - **에이전트:** 같은 리더보드에서 **AVE-Agent (Wan)**이 **전체 편집 의도 59.8/100**, **오디오 편집 의도 50.2/100**으로 앞섭니다.

<a id="evaluation-protocols-and-benchmarks"></a>
<a id="evaluation-metrics"></a>

### 📏 평가 지표

지표는 본 서베이의 네 가지 평가 차원에 따라 분류했습니다. **↑ / ↓**는 각각 높을수록 / 낮을수록 좋음을 뜻합니다. **참조 정보 / 입력**은 편집 결과 외에 필요한 정보를 나타냅니다.

#### 지시 준수

| 지표 | 측정 대상 | 오디오 모달리티 | 참조 정보 / 입력 | 논문 / 표준 | 코드 / 모델 |
| --- | --- | --- | --- | --- | --- |
| WER / CER ↓ | 목표 단어·문자에 대한 ASR 전사 오류율. | 음성 | 목표 전사문; 편집 결과의 ASR 전사문. | <a href="https://arxiv.org/abs/2212.04356"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/jitsi/jiwer"><img height="20" src="https://img.shields.io/badge/GitHub-JiWER-181717?logo=github&amp;logoColor=white" alt="JiWER"></a><br><a href="https://github.com/openai/whisper"><img height="20" src="https://img.shields.io/badge/GitHub-ASR-181717?logo=github&amp;logoColor=white" alt="ASR"></a> |
| 감정 분류 정확도 ↑ | 예측 감정과 요청된 감정 레이블의 일치도. | 음성 | 목표 감정 레이블; 동일한 레이블 체계를 사용하는 감정 분류기. | <a href="https://arxiv.org/abs/2312.15185"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/ddlBoJack/emotion2vec"><img height="20" src="https://img.shields.io/badge/GitHub-emotion2vec-181717?logo=github&amp;logoColor=white" alt="emotion2vec"></a> |
| CLAP 오디오–텍스트 유사도 ↑ | 출력 오디오와 원하는 오디오 설명 사이의 코사인 유사도. | 음악; 일반 오디오 | 원하는 결과를 설명하는 캡션; 지정된 CLAP 체크포인트. | <a href="https://arxiv.org/abs/2211.06687"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/LAION-AI/CLAP"><img height="20" src="https://img.shields.io/badge/GitHub-CLAP-181717?logo=github&amp;logoColor=white" alt="CLAP"></a> |
| 이벤트 출현 점수(EOS) ↑ | 텍스트 유도 음원 분리 후 이벤트별 CLAP 유사도의 최솟값. 요청된 이벤트의 포함 여부를 평가. | 일반 오디오 | 원하는 이벤트 설명; 이벤트 분해 결과와 분리된 이벤트 트랙. | <a href="https://aclanthology.org/2025.acl-long.1147/"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper"></a> |  |

#### 내용 보존과 국소성

국소 편집에서는 변경되지 않아야 하는 구간이나 음원을 비교합니다.

| 지표 | 측정 대상 | 오디오 모달리티 | 참조 정보 / 입력 | 논문 / 표준 | 코드 / 모델 |
| --- | --- | --- | --- | --- | --- |
| 화자 임베딩 코사인 유사도 ↑ | 편집된 음성에서 화자 정체성이 보존되는 정도. | 음성 | 원본 화자의 오디오; 두 녹음에 동일하게 적용한 화자 검증 인코더. | <a href="https://arxiv.org/abs/2005.07143"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://huggingface.co/speechbrain/spkrec-ecapa-voxceleb"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="HF Model"></a> |
| 다중 해상도 STFT 거리 ↓ | 여러 시간·주파수 해상도에서의 스펙트럼 수렴도와 로그 크기 차이. | 음성; 음악; 일반 오디오 | 편집하지 않은 구간에서 정렬된 원본·출력 오디오. | <a href="https://arxiv.org/abs/1910.11480"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/csteinmetz1/auraloss"><img height="20" src="https://img.shields.io/badge/GitHub-auraloss-181717?logo=github&amp;logoColor=white" alt="auraloss"></a> |
| CLAP 오디오–오디오 유사도 ↑ | 원본·편집 오디오 임베딩의 의미적 유사도. 전반적인 보존의 대리 지표. | 음악; 일반 오디오 | 원본 오디오; 국소 비교 시 대응하는 비대상 구간 또는 스템. | <a href="https://arxiv.org/abs/2507.11096"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/LAION-AI/CLAP"><img height="20" src="https://img.shields.io/badge/GitHub-CLAP-181717?logo=github&amp;logoColor=white" alt="CLAP"></a> |
| LPAPS 거리 ↓ | 사전 학습된 특징 네트워크가 추출한 오디오 표현 간 지각적 거리. | 음악; 일반 오디오 | 원본 오디오; 국소 비교 시 정렬된 비편집 구간. | <a href="https://arxiv.org/abs/2402.10009"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/HilaManor/AudioEditingCode#evaluation"><img height="20" src="https://img.shields.io/badge/GitHub-LPAPS-181717?logo=github&amp;logoColor=white" alt="LPAPS"></a> |

#### 시간적·구조적 일관성

| 지표 | 측정 대상 | 오디오 모달리티 | 참조 정보 / 입력 | 논문 / 표준 | 코드 / 모델 |
| --- | --- | --- | --- | --- | --- |
| 경계 오차 ↓ | 예측한 음성 구간 경계의 절대 시간 오차 평균 또는 중앙값. | 음성 | 동일한 시간 단위의 수동 경계 주석과 예측 경계. | <a href="https://eprints.whiterose.ac.uk/id/eprint/210215/"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper"></a> |  |
| 단어 단위 동적 시간 정합(WDTW) ↓ | 원본·편집 음성의 대응 단어 구간에서 길이로 정규화한 DTW 거리. | 음성 | 원본·편집 음성; 두 음성의 전사문과 단어 단위 강제 정렬 결과. | <a href="https://arxiv.org/abs/2604.16056"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> |  |
| 멜로디 정확도 ↑ | 참조·편집 음악에서 지배적인 음높이 클래스의 프레임별 일치도. | 음악 | 참조 멜로디·오디오; 정렬된 음높이 클래스 시퀀스. | <a href="https://arxiv.org/abs/2507.11096"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/billsioros/EditGen/tree/master/notebooks/evaluation"><img height="20" src="https://img.shields.io/badge/GitHub-EditGen-181717?logo=github&amp;logoColor=white" alt="EditGen"></a> |
| F0 피어슨 상관계수 ↑ | 참조·출력 보컬의 음높이 곡선 간 상관관계. | 음악(보컬) | 참조 보컬 오디오; 동일한 모델로 추출하고 정렬한 F0 곡선. | <a href="https://arxiv.org/abs/2603.24589"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Dream-High/RMVPE"><img height="20" src="https://img.shields.io/badge/GitHub-RMVPE-181717?logo=github&amp;logoColor=white" alt="Pitch extractor"></a><br>음높이 추출기 |
| 크로마 유사도 / 크로마 DTW 유사도 ↑ | 음높이 클래스 분포의 유사도 또는 DTW 정렬 후의 프레임별 유사도. | 음악 | 원본·참조 음악; 동일한 방식으로 추출한 크로마그램. | <a href="https://arxiv.org/abs/2512.14629"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Yashvishe13/MuseCPEval/blob/main/musecpeval/metrics/harmony_tonality.py"><img height="20" src="https://img.shields.io/badge/GitHub-MuseCPEval-181717?logo=github&amp;logoColor=white" alt="MuseCPEval"></a> |
| 비트 F1 ↑ | 70 ms 허용 오차 내에서 박 타임스탬프를 매칭한 정밀도와 재현율의 조화 평균. | 음악 | 참조·출력의 박 타임스탬프. | <a href="https://arxiv.org/abs/2512.14629"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Yashvishe13/MuseCPEval/blob/main/musecpeval/metrics/rhythm_meter.py"><img height="20" src="https://img.shields.io/badge/GitHub-MuseCPEval-181717?logo=github&amp;logoColor=white" alt="MuseCPEval"></a> |
| 다이내믹스 상관계수 ↑ | 참조·출력 음량 궤적의 프레임별 피어슨 상관계수. | 음악 | 참조 다이내믹스·오디오; 정렬된 음량 궤적. | <a href="https://arxiv.org/abs/2507.11096"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/billsioros/EditGen/tree/master/notebooks/evaluation"><img height="20" src="https://img.shields.io/badge/GitHub-EditGen-181717?logo=github&amp;logoColor=white" alt="EditGen"></a> |
| 구조 쌍별 F-점수 / ARI ↑ | 음악 구간 배정의 일치도. ARI는 우연에 의한 일치를 보정. | 음악 | 공통 시간축의 원본·참조 및 출력 구간 분할. | <a href="https://arxiv.org/abs/2512.14629"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Yashvishe13/MuseCPEval/blob/main/musecpeval/metrics/structural_form.py"><img height="20" src="https://img.shields.io/badge/GitHub-MuseCPEval-181717?logo=github&amp;logoColor=white" alt="MuseCPEval"></a> |
| 이벤트 순서 점수(ESS) ↑ | 설명된 이벤트 순서와 검출된 순서 간 Kendall 방식의 순위 일치도. | 일반 오디오 | 원하는 이벤트 순서; 분리된 이벤트 트랙의 시작 시각 추정치. | <a href="https://aclanthology.org/2025.acl-long.1147/"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper"></a> |  |

#### 오디오 품질과 자연스러움

| 지표 | 측정 대상 | 오디오 모달리티 | 참조 정보 / 입력 | 논문 / 표준 | 코드 / 모델 |
| --- | --- | --- | --- | --- | --- |
| MOS / CMOS ↑ | 출력 품질 또는 다른 녹음 대비 상대적 품질에 대한 사람의 평가. | 음성; 음악; 일반 오디오 | 청취자와 작업별 평가 프로토콜; CMOS는 비교 오디오 추가 필요. | <a href="https://www.itu.int/rec/T-REC-P.800/en"><img height="20" src="https://img.shields.io/badge/ITU-Standard-brightgreen" alt="Standard"></a> | <a href="https://github.com/microsoft/P.808"><img height="20" src="https://img.shields.io/badge/GitHub-P.808-181717?logo=github&amp;logoColor=white" alt="Speech listening tests"></a><br>음성 청취 평가 |
| MOSNet 예측 MOS ↑ | 음성 변환을 위해 개발된 음성 자연스러움 점수의 자동 예측. | 음성 | 편집된 음성. | <a href="https://arxiv.org/abs/1904.08352"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/lochenchou/MOSNet"><img height="20" src="https://img.shields.io/badge/GitHub-MOSNet-181717?logo=github&amp;logoColor=white" alt="MOSNet"></a> |
| UTMOSv2 예측 MOS ↑ | 고품질 합성 음성을 위해 개발된 자연스러움 MOS 예측값. | 음성 | 편집된 음성. | <a href="https://arxiv.org/abs/2409.09305"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/sarulab-speech/UTMOSv2"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a><br><a href="https://huggingface.co/sarulab-speech/UTMOSv2"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="HF Model"></a> |
| SpeechJudge-GRM (쌍별 평가) | 두 후보의 자연스러움 점수와 선호도 및 생성된 설명. | 음성 | 목표 전사문과 동일한 텍스트에 대한 두 후보 음성. | <a href="https://arxiv.org/abs/2511.07931"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/AmphionTeam/SpeechJudge"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a><br><a href="https://huggingface.co/RMSnow/SpeechJudge-GRM"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="HF Model"></a> |
| DNSMOS P.835 ↑ | 음성 신호, 배경 잡음, 전체 품질의 예측 점수. | 음성 | 편집된 음성. | <a href="https://arxiv.org/abs/2110.01763"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/microsoft/DNS-Challenge/tree/master/DNSMOS"><img height="20" src="https://img.shields.io/badge/GitHub-DNSMOS-181717?logo=github&amp;logoColor=white" alt="DNSMOS"></a> |
| NISQA ↑ | 전체 음성 품질과 열화 차원의 예측값. NISQA-TTS는 합성 음성의 자연스러움을 평가. | 음성 | 편집된 음성; 적절한 NISQA 체크포인트. | <a href="https://arxiv.org/abs/2104.09494"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/gabrielmittag/NISQA"><img height="20" src="https://img.shields.io/badge/GitHub-NISQA-181717?logo=github&amp;logoColor=white" alt="NISQA"></a> |
| PAM ↑ | 오디오–언어 모델과 긍정·부정 품질 프롬프트의 대비를 이용한 무참조 오디오 품질 평가. | 음성; 음악; 일반 오디오 | 편집된 오디오; 고정 품질 프롬프트와 PAM 구현의 MS-CLAP 백본. | <a href="https://arxiv.org/abs/2402.00282"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/soham97/PAM"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a> |
| PESQ ↑ | 열화 또는 복원된 음성의 참조 기반 지각 품질. | 음성 | 대응하는 클린 목표 음성; 8 kHz 협대역 또는 16 kHz 광대역 모드. | <a href="https://www.itu.int/rec/T-REC-P.862/en"><img height="20" src="https://img.shields.io/badge/ITU-Standard-brightgreen" alt="Standard"></a> | <a href="https://github.com/ludlows/PESQ"><img height="20" src="https://img.shields.io/badge/GitHub-PESQ-181717?logo=github&amp;logoColor=white" alt="PESQ"></a> |
| STOI ↑ | 열화 또는 개선된 음성의 명료도 추정값. | 음성 | 시간 정렬된 클린 목표 음성. | <a href="https://sps.ewi.tudelft.nl/pubs/Taal2010.pdf"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper"></a> | <a href="https://github.com/mpariente/pystoi"><img height="20" src="https://img.shields.io/badge/GitHub-pystoi-181717?logo=github&amp;logoColor=white" alt="pystoi"></a> |
| SI-SDR ↑ | 전체 스케일 차이를 보정한 목표 신호 복원 충실도. | 음성; 음악; 일반 오디오 | 시간 정렬된 목표 파형 또는 분리된 목표 음원. | <a href="https://arxiv.org/abs/1811.02508"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Lightning-AI/torchmetrics/blob/master/src/torchmetrics/functional/audio/sdr.py"><img height="20" src="https://img.shields.io/badge/GitHub-TorchMetrics-181717?logo=github&amp;logoColor=white" alt="TorchMetrics"></a> |
| NOMAD 거리 ↓ | 학습된 임베딩 공간에서 측정한 음성의 지각적 열화. | 음성 | 클린 참조 음성; 언어 내용이 같을 필요는 없음. | <a href="https://arxiv.org/abs/2309.16284"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/alessandroragano/nomad"><img height="20" src="https://img.shields.io/badge/GitHub-NOMAD-181717?logo=github&amp;logoColor=white" alt="NOMAD"></a> |
| SpeechBERTScore ↑ | 자기지도 음성 특징의 탐욕적 매칭을 이용한 참조 기반 음성 품질 대리 지표. | 음성 | 자연스러운 참조 음성; 고정된 인코더·레이어와 정밀도·재현율·F1 변형. | <a href="https://arxiv.org/abs/2401.16812"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Takaaki-Saeki/DiscreteSpeechMetrics"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a> |
| 프레셰 오디오 거리(FAD) ↓ | 출력·참조 오디오 임베딩 분포 간 거리. | 음악; 일반 오디오 | 참조 오디오 집합; 동일한 임베딩 백본과 전처리. | <a href="https://arxiv.org/abs/1812.08466"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/microsoft/fadtk"><img height="20" src="https://img.shields.io/badge/GitHub-FADtk-181717?logo=github&amp;logoColor=white" alt="FADtk"></a> |

#### 다차원 평가 모델

편집 결과와 오디오의 미적 품질을 여러 차원에서 평가할 수 있는 재사용 가능한 모델과 도구 모음입니다.

| 평가 모델 | 오디오 모달리티 | 평가 차원 | 참조 정보 / 입력 | 논문 | 코드 / 모델 |
| --- | --- | --- | --- | --- | --- |
| AuditEval (SSL / LLM) | 일반 오디오 | 품질, 편집 관련성, 원본에 대한 충실도. | 원본·편집 오디오; 원래 설명과 목표 설명. | <a href="https://arxiv.org/abs/2508.11966"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/NKU-HLT/AuditEval"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a><br><a href="https://modelscope.cn/models/YuhangJia/AuditEval/summary"><img height="20" src="https://img.shields.io/badge/ModelScope-Models-624AFF" alt="ModelScope"></a> |
| MuseCPEval | 음악 | 화성, 리듬, 구조, 멜로디 보존. 도구 모음에 음색 지표도 포함. | 원본·편집 음악; 보존할 음악 속성. | <a href="https://arxiv.org/abs/2512.14629"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Yashvishe13/MuseCPEval"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a> |
| MMAE 평가 기준 판정기 (Qwen3-Omni) | 음성; 음악; 일반 오디오 | 지시 준수율(IFR), 일관성 비율(CR), 완전 일치율(EMR). | 원본·출력 오디오, 편집 지시, 샘플별 MMAE 평가 기준. | <a href="https://arxiv.org/abs/2606.07229"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/ddlBoJack/MMAE/tree/main/eval"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a> |
| Audiobox Aesthetics | 음성; 음악; 일반 오디오 | 콘텐츠 즐거움(CE), 콘텐츠 유용성(CU), 제작 복잡도(PC), 제작 품질(PQ). | 편집된 오디오만 필요. | <a href="https://arxiv.org/abs/2502.05139"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/facebookresearch/audiobox-aesthetics"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a><br><a href="https://huggingface.co/facebook/audiobox-aesthetics"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="HF Model"></a> |
| SongEval 점수 모델 | 음악(노래) | 전체 일관성, 기억에 남는 정도, 보컬 호흡·프레이징의 자연스러움, 구조적 명확성, 전반적인 음악성. | 보컬과 반주를 포함하는 전체 길이의 노래 오디오. | <a href="https://arxiv.org/abs/2505.10793"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/ASLP-lab/SongEval"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a><br><a href="https://github.com/ASLP-lab/SongEval/tree/main/ckpt"><img height="20" src="https://img.shields.io/badge/GitHub-Weights-181717?logo=github&amp;logoColor=white" alt="Weights"></a> |
| MuseCritic | 음악(노래) | 일관성, 음악성, 기억에 남는 정도, 구조적 명확성, 보컬 자연스러움. 점수와 자연어 평론을 출력. | 전체 길이의 노래 오디오; 공개된 미적 평가 기준. | <a href="https://arxiv.org/abs/2608.11755"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/WuqnEl/MuseCritic"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a><br><a href="https://huggingface.co/WuqnEl/MuseCritic"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="HF Model"></a> |

---

<a id="challenges-and-future-directions"></a>

## 🔮 과제와 향후 연구 방향

파운데이션 모델 기반 오디오 편집에는 다음과 같은 시스템 수준의 과제가 남아 있습니다.

1. **복잡한 편집.**  
   실제 오디오에는 의미적 이벤트, 화자 정체성, 음향 속성, 배경 분위기, 리듬, 공간 단서, 잔향이 복잡하게 얽혀 있습니다. 향후 시스템은 음성, 음악, 일반 오디오 전반에서 음원·이벤트의 정확한 위치 지정, 속성 단위 수정, 비대상 내용의 안정적인 보존을 지원해야 합니다.
2. **개방형 환경에서의 견고성.**  
   편집 모델은 잡음, 잔향, 겹치는 음원, 긴 문맥, 모호한 지시가 있는 상황에서도 신뢰할 수 있어야 합니다. 지시와 오디오 내용의 연결을 정교화하고, 긴 문맥 모델링, 반복적 개선, 자기 검증을 발전시키는 것이 실제 환경에서 견고한 편집을 구현하기 위한 중요한 방향입니다.
3. **충실하고 편집에 특화된 평가.**  
   기존 평가는 생성 품질과 편집 품질을 혼용하는 경우가 많습니다. 향후 벤치마크는 편집 대상, 연산, 보존 구간, 관련 제어 신호를 명시적으로 주석 처리하여 편집 성공과 비대상 내용 보존을 별도로 평가할 수 있어야 합니다.
4. **안전, 저작권, 오용 방지.**  
   현대 편집 시스템은 발화 내용, 화자 정체성, 감정, 환경음, 음악을 사실적으로 바꿀 수 있습니다. 따라서 실제 배포에는 출처 추적, 워터마킹, 조작 오디오 탐지, 책임 있는 데이터 라이선스 활용 등 상호 보완적인 장치가 필요합니다.

---

<a id="citation"></a>

## 인용

본 서베이나 저장소가 연구에 도움이 되었다면 아래 논문을 인용해 주세요.

```bibtex
@article{pan2026audio,
  title={Audio Editing in the Era of Foundation Models: A Survey},
  author={Pan, Changhao and Fan, Yifei and Zhuo, Fan and Chen, Yifu and Guo, Wenxiang and Zhang, Yu and Li, Ruiqi and Zhu, Zhiyuan and Yang, Rui and Ji, Shengpeng and others},
  journal={arXiv preprint arXiv:2606.23139},
  year={2026}
}
```

<a id="contributing"></a>

## 기여하기

이 저장소는 지속적으로 업데이트됩니다. 누락된 오디오 편집 모델, 데이터셋 또는 벤치마크가 있다면 [이슈](https://github.com/MM-Speech/AudioEditSurvey/issues)나 풀 리퀘스트를 보내 주세요.

---

<a id="license"></a>

## 📄 라이선스

아래에 별도로 명시한 경우를 제외하고, 이 저장소에서 작성한 원본 콘텐츠에는 [MIT 라이선스](LICENSE)가 적용됩니다.

[서베이 논문](https://arxiv.org/abs/2606.23139)과 논문에서 재사용하거나 각색한 콘텐츠(`assets/taxonomy_overview.png`, `assets/train-based.png`, `assets/train-free.png` 포함)에는 계속 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)이 적용됩니다. MIT 라이선스가 이러한 자료의 기존 라이선스를 변경하지는 않습니다.

연결된 제3자 논문, 코드, 모델, 모델 가중치, 데이터셋, 도구에는 각각의 라이선스가 적용됩니다.
