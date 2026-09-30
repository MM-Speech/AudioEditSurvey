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

# 🚀 快速开始

本仓库是综述论文 **Audio Editing in the Era of Foundation Models: A Survey** 的官方仓库，论文已被 **`AACL-IJCNLP 2026`** 接收。

- 我们建立了覆盖**语音、音乐和通用音频**的**声学、语义和实例编辑**统一分类体系，明确各类任务需要修改和保留的内容，为不同编辑目标之间的一致比较提供依据。
- 我们从**基础模型架构**和**学习范式**出发，梳理主流音频编辑技术，重点介绍其核心机制及对不同编辑场景的适用性。
- **（近期更新）** 我们汇总了**公开可用的音频编辑模型**，归纳其支持的任务类别与主要优势，帮助读者选择合适的模型。
- **（近期更新）** 我们整理了音频编辑相关的**公开数据集、数据构建工具、评测基准和指标**，总结其覆盖的音频领域、编辑类别与评测维度。

<a id="whats-new"></a>

# 🔥 最新动态

- 📦 **[2026/09] 本仓库已迁移至 [`MM-Speech/AudioEditSurvey`](https://github.com/MM-Speech/AudioEditSurvey)，以便更好地维护与管理。**
- 🏆 **[2026/09] 我们的论文已被 AACL-IJCNLP 2026 接收！**
- 🎉 **[2026/06] 音频编辑模型综述仓库正式发布，论文预印本已在 [arXiv](https://arxiv.org/abs/2606.23139) 上公开。**

## 目录

1. [简介](#introduction)
2. [总览](#overall)
   - [分类体系概览](#taxonomy-overview)
   - [分类体系详解](#taxonomy-details)
   - [代表性音频编辑方法](#representative-audio-editing-methods)
     - [Unified](#methods-unified) · [Speech](#methods-speech) · [Music](#methods-music) · [Audio](#methods-audio)
3. [用于音频编辑的基础模型](#foundation-models-for-audio-editing)
4. [需要训练的音频编辑](#training-based-audio-editing)
5. [无需训练的音频编辑](#training-free-audio-editing)
6. [资源](#resources)
   - [可用数据集](#available-datasets)
     - [语音](#speech) · [音乐](#music) · [通用音频](#audio) · [跨领域](#unified)
   - [数据工具](#data-tools)
   - [评测基准](#benchmarks)
   - [评测指标](#evaluation-metrics)
7. [挑战与未来方向](#challenges-and-future-directions)
8. [引用](#citation)
9. [参与贡献](#contributing)

---

<a id="introduction"></a>

## 📌 简介

**Awesome Audio Editing** 汇集了基于基础模型的音频编辑研究与资源，覆盖**语音、音乐和通用音频**。本仓库以我们的[综述论文](https://arxiv.org/abs/2606.23139)为基础，串联编辑任务、模型设计、学习策略与实践资源：

- **任务分类。** 我们建立了**声学、语义和实例编辑**的统一分类体系，明确各类任务需要修改的目标与应当保留的内容。
- **模型架构。** 我们梳理了**音频编解码语言模型、扩散模型和流匹配模型**，分析其音频表示与生成机制如何支持不同编辑操作。
- **训练方法。** 我们区分从数据中学习编辑能力的**需要训练的方法**，以及不更新参数、在推理时控制预训练生成模型的**无需训练的方法**，并按核心技术机制组织代表性工作。
- **公开资源。** 我们整理了**公开可用的编辑模型、数据集、数据生成与标注工具、评测基准和指标**，提供资源链接与能力概览，支持研究与实践。

---

<a id="overall"></a>

## 🧭 总览

<a id="taxonomy-overview"></a>

### 🗂️ 分类体系概览

![音频编辑任务分类体系](assets/taxonomy_overview.png)

*图 1：音频编辑任务分类体系。*



<a id="taxonomy-details"></a>

### 🧩 分类体系详解




| 类别 | 定义 | 代表性编辑目标 |
| --- | --- | --- |
| 声学编辑 | 修改低层次感知属性，同时保留原始音频的整体结构与音源特征。 | 音频修复、混响编辑、响度／混音控制、均衡、频谱纹理编辑 |
| 语义编辑 | 修改音频传递的高层次可解释信息，同时维持与任务无关的属性。 | 语言内容编辑、表现力编辑、风格编辑 |
| 实例编辑 | 操作可辨识的音频实体，同时保留场景中的其余内容及音源关系。 | 替换、删除／提取、插入、叠加／重混音 |

<a id="representative-audio-editing-methods"></a>

### 📚 代表性音频编辑方法

本表收录已公开编辑实现与模型权重的代表性工作，各项目沿用其自身许可证。操作类别按本综述的[分类体系](#taxonomy-details)统一标注；**Unified** 收录支持多种音频模态的编辑模型，具体支持的模态在表中列明。**基础模型**链接指向编辑器使用的预训练骨干，**适配器**链接指向额外学习的权重。

<a id="methods-unified"></a>

#### 跨领域模型（Unified）

| 模型 | 音频模态 | 编辑类别 | 模型架构 | 论文 | 代码 | 模型权重 |
| --- | --- | --- | --- | --- | --- | --- |
| Audio-Omni | Speech; Music; Audio | 实例：添加、删除、提取、音源转换 | MLLM + 整流 DiT | <a href="https://arxiv.org/abs/2604.10708"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ZeyueT/Audio-Omni"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 权重](https://huggingface.co/HKUSTAudio/Audio-Omni) |
| AudioMorphix | Speech; Music; Audio | 语义：音高／时间伸缩<br>实例：添加、删除、替换、时间移动 | 扩散 U-Net（Tango / AudioLDM） | <a href="https://arxiv.org/abs/2505.16076"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://huggingface.co/spaces/JinhuaL1ANG/AudioMorphix/tree/main"><img height="20" src="https://img.shields.io/badge/HuggingFace-Code-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Code"></a> | [🤗 基础模型（Tango 2）](https://huggingface.co/declare-lab/tango2-full)<br>[🤗 基础模型（AudioLDM）](https://huggingface.co/cvssp/audioldm-l-full) |
| AuK / AuK-Flash | Speech; Music | 声学：修复、响度<br>语义：词语、歌词、表现力<br>实例：音色、音源提取 | MLLM + 整流 DiT | <a href="https://arxiv.org/abs/2609.08936"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/Tencent-Hunyuan/AuK"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 AuK](https://huggingface.co/tencent/AuK)<br>[🤗 Flash](https://huggingface.co/tencent/AuK-Flash) |
| Vevo2 | Speech; Music | 语义：内容、歌词、韵律、风格<br>实例：说话人／歌手转换 | 编解码语言模型 + 流匹配解码器 | <a href="https://arxiv.org/abs/2508.16332"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/open-mmlab/Amphion/tree/main/models/svc/vevo2"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 权重](https://huggingface.co/RMSnow/Vevo2) |
| DirectAudioEdit | Music; Audio | 实例：文本引导的事件替换／添加／删除 | 扩散 U-Net（Tango 2 / AudioLDM2） | <a href="https://arxiv.org/abs/2606.07356"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/NiuTrans/DirectAudioEdit"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 基础模型（Tango 2）](https://huggingface.co/declare-lab/tango2-full)<br>[🤗 基础模型（音效）](https://huggingface.co/cvssp/audioldm2) |
| DDPM Inversion (ZETA) | Music; Audio | 语义：音乐风格<br>实例：乐器／声音事件变更 | 扩散 U-Net（AudioLDM2） | <a href="https://arxiv.org/abs/2402.10009"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/HilaManor/AudioEditingCode"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 基础模型（音效）](https://huggingface.co/cvssp/audioldm2)<br>[🤗 基础模型（音乐）](https://huggingface.co/cvssp/audioldm2-music) |

<a id="methods-speech"></a>

#### 语音模型（Speech）

| 模型 | 编辑类别 | 模型架构 | 论文 | 代码 | 模型权重 |
| --- | --- | --- | --- | --- | --- |
| Ming-UniAudio-Edit | 声学：去噪、响度<br>语义：内容、韵律、情感、方言 | 连续 token 语言模型 + 扩散预测头 | <a href="https://arxiv.org/abs/2511.05516"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/inclusionAI/Ming-UniAudio"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 权重](https://huggingface.co/inclusionAI/Ming-UniAudio-16B-A3B-Edit) |
| Step-Audio-EditX | 语义：情感、说话风格、副语言线索、发音 | 编解码语言模型 + 流匹配解码器 | <a href="https://arxiv.org/abs/2511.03601"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/stepfun-ai/Step-Audio-EditX"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 权重](https://huggingface.co/stepfun-ai/Step-Audio-EditX) |
| CosyEdit | 语义：词语插入、删除、替换 | 编解码语言模型 + 流匹配解码器 | <a href="https://arxiv.org/abs/2601.05329"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/CJY1018/CosyEdit"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 权重](https://huggingface.co/CJY/CosyEdit) |
| VoiceCraft-X | 语义：多语言内容编辑 | 编解码语言模型（自回归填补） | <a href="https://arxiv.org/abs/2511.12347"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/zszheng147/VoiceCraft-X"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 权重](https://huggingface.co/zhisheng01/VoiceCraft-X) |
| VoiceCraft | 语义：词语插入、删除、替换 | 编解码语言模型（自回归填补） | <a href="https://arxiv.org/abs/2403.16973"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/jasonppy/VoiceCraft"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 权重](https://huggingface.co/pyp1/VoiceCraft) |
| SSR-Speech | 语义：词语插入、删除、替换 | 编解码语言模型（自回归填补） | <a href="https://arxiv.org/abs/2409.07556"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/WangHelin1997/SSR-Speech"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 英语](https://huggingface.co/westbrook/SSR-Speech-English)<br>[🤗 普通话](https://huggingface.co/westbrook/SSR-Speech-Mandarin) |
| F5-TTS | 语义：局部内容替换／填补 | 流匹配 DiT | <a href="https://arxiv.org/abs/2410.06885"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/SWivid/F5-TTS/blob/main/src/f5_tts/infer/speech_edit.py"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 权重](https://huggingface.co/SWivid/F5-TTS) |
| FluentSpeech | 语义：内容编辑、口吃与不流畅修正 | 扩散模型（上下文感知去噪器） | <a href="https://arxiv.org/abs/2305.13612"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/Zain-Jiang/Speech-Editing-Toolkit"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [📁 权重](https://drive.google.com/drive/folders/1saqpWc4vrSgUZvRvHkf2QbwWSikMTyoo) |
| EdiTTS | 语义：合成语音中的内容／音高编辑 | 基于分数的扩散模型（Grad-TTS） | <a href="https://arxiv.org/abs/2110.02584"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/neosapience/editts"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [📦 基础模型](https://github.com/neosapience/editts/tree/master/checkpts) |

<a id="methods-music"></a>

#### 音乐模型（Music）

| 模型 | 编辑类别 | 模型架构 | 论文 | 代码 | 模型权重 |
| --- | --- | --- | --- | --- | --- |
| YingMusic-Singer-Plus | 语义：歌词<br>实例：歌手音色替换 | 流匹配 DiT | <a href="https://arxiv.org/abs/2603.24589"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ASLP-lab/YingMusic-Singer-Plus"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 权重](https://huggingface.co/ASLP-lab/YingMusic-Singer-Plus) |
| ACE-Step 1.5 | 语义：风格／局部重绘<br>实例：音轨提取／添加（base 版本） | 语言模型 + 流匹配 DiT | <a href="https://arxiv.org/abs/2602.00744"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ace-step/ACE-Step-1.5"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 Turbo](https://huggingface.co/ACE-Step/Ace-Step1.5)<br>[🤗 Base 版本](https://huggingface.co/ACE-Step/acestep-v15-base) |
| Instruct-MusicGen | 实例：分轨添加、删除、提取 | 编解码语言模型（MusicGen）+ 适配器 | <a href="https://arxiv.org/abs/2405.18386"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ldzhangyx/instruct-MusicGen"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 公开数据重训版](https://huggingface.co/ldzhangyx/instruct-MusicGen) |
| MusicGen-Stem | 实例：分轨替换／添加（贝斯、鼓、其他） | 多流编解码语言模型 | <a href="https://arxiv.org/abs/2501.01757"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/simonrouard/audiocraft/tree/multistem"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 权重](https://huggingface.co/facebook/musicgen-stem-6cb) |
| MelodyFlow | 语义：流派、情绪、风格<br>实例：乐器配置 | 流匹配 DiT | <a href="https://arxiv.org/abs/2407.03648"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://huggingface.co/spaces/facebook/MelodyFlow/tree/main"><img height="20" src="https://img.shields.io/badge/HuggingFace-Code-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Code"></a> | [🤗 权重](https://huggingface.co/facebook/melodyflow-t24-30secs) |
| AP-Adapter | 语义：流派／风格转换<br>实例：乐器替换 | 扩散 U-Net + 音频提示适配器 | <a href="https://arxiv.org/abs/2407.16564"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/fundwotsai2001/AP-adapter"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [📁 适配器](https://drive.google.com/drive/folders/1LkIe3-_4nqvDJQqEgglbyj9AMFkn0TLd)<br>[🤗 基础模型](https://huggingface.co/cvssp/audioldm2-large) |
| AnchorSteer | 语义：流派／风格<br>实例：乐器变更 | 扩散 DiT + 结构／概念适配器 | <a href="https://arxiv.org/abs/2605.31053"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/hengtsune1024/AnchorSteer"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 概念权重](https://huggingface.co/heng1024/AnchorSteer-weights)<br>[📁 结构适配器](https://drive.google.com/drive/folders/1Q9B333jcq1czA11JKTbM-DHANJ8YqGbP)<br>[🤗 基础模型（需接受条款）](https://huggingface.co/stabilityai/stable-audio-open-1.0) |

<a id="methods-audio"></a>

#### 通用音频模型（Audio）

| 模型 | 编辑类别 | 模型架构 | 论文 | 代码 | 模型权重 |
| --- | --- | --- | --- | --- | --- |
| MMEdit | 声学：响度<br>实例：事件添加、删除、替换、重排 | 音频语言模型 + 扩散 MMDiT | <a href="https://arxiv.org/abs/2512.20339"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ty0402/MMEdit"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 权重](https://huggingface.co/CocoBro/MMEdit) |
| SAO-Instruct | 声学：滤波、去噪、修复<br>语义：音高／速率<br>实例：事件操作 | 扩散 DiT（Stable Audio Open） | <a href="https://arxiv.org/abs/2510.22795"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ETH-DISCO/sao-instruct"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 权重](https://huggingface.co/disco-eth/sao-instruct) |
| SmartDJ-Editor | 声学：音量、混响、频谱色彩<br>实例：事件添加、删除、提取、位置调整 | 扩散 Transformer（U-DiT） | <a href="https://arxiv.org/abs/2509.21625"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/penn-waves-lab/SmartDJ"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 编辑器权重](https://huggingface.co/ztlan/SmartDJ) |
| AudioEditor | 实例：事件添加、删除、替换 | 扩散 U-Net（Auffusion） | <a href="https://arxiv.org/abs/2409.12466"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/NKU-HLT/AudioEditor"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 基础模型](https://huggingface.co/auffusion/auffusion-full-no-adapter) |
| CoherentAVEdit | 实例：视频条件下的声音事件替换 | 流匹配 Transformer（MMAudio） | <a href="https://arxiv.org/abs/2512.07209"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/SonyResearch/CoherentAVEdit"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | [🤗 权重](https://huggingface.co/masato-a-ishii/CoherentAVEdit) |

---

<a id="foundation-models-for-audio-editing"></a>

## 🏗️ 用于音频编辑的基础模型

### 1. 早期神经编辑模型

在基础模型时代之前，早期神经音频编辑方法主要探索面向特定任务的生成模型，用于局部重建和属性控制。

### 2. 基于 token 的音频编解码语言模型

基于离散 token 的音频编解码语言模型，将音频编辑视为离散音频 token 上的条件生成。在连续音频被转换为紧凑的离散 token 序列后，模型根据上下文、提示或任务控制信号，通过自回归续写、片段填补或选择性重新生成来编辑目标区域。

### 3. 扩散与流匹配模型

扩散模型和流匹配模型将音频编辑表述为梅尔频谱或音频潜在表示等连续声学空间中的条件变换。它们通过条件去噪、潜在表示反演或连续流变换修改音频，而非填补离散 token，因此适用于复杂场景中的高保真重建、区域级精修和细粒度声学控制。

### 4. 音频编辑接口

指令条件接口和多模态接口为基于基础模型的音频编辑提供高层次控制。用户可以通过自然语言指令、任务提示、参考音频、时间区域或视觉线索表达编辑意图；系统再将这些输入转换为目标片段、任务嵌入、事件位置、说话人参考或保留约束。

---

<a id="training-based-audio-editing"></a>

## 🧪 需要训练的音频编辑

需要训练的音频编辑方法在推理前，利用有监督配对、伪配对或指令三元组学习编辑行为。这些方法显式优化编辑目标、条件遵循和保留约束，从而实现稳定、可控的编辑。我们根据监督信号与条件机制，将现有工作归纳为三类，并讨论其核心方法与功能范围。

<p align="center">
  <img src="assets/train-based.png" alt="需要训练的音频编辑方法概览" width="900">
</p>

<p align="center">
  <em>图 2：需要训练的音频编辑方法概览。</em>
</p>


| 范式 | 说明 | 代表性应用范围 |
| --- | --- | --- |
| 特定任务训练 | 针对预定义的编辑功能或领域优化模型。 | 基于文本的语音编辑、韵律修正、音源分离、音乐分轨分离 |
| 基于参考与属性的训练 | 通过参考音频、风格示例或属性标签指定编辑方向。 | 语音转换、音色迁移、情绪编辑、混音风格迁移 |
| 指令条件训练 | 从指令—输入—输出三元组中学习遵循自然语言编辑请求。 | 添加、删除、替换、音频补全、超分辨率、音乐重混音、表现力优化 |


---

<a id="training-free-audio-editing"></a>

## 🪄 无需训练的音频编辑

无需训练的音频编辑方法在不更新参数的情况下，将预训练音频生成模型用于编辑。它们通过反演、注意力控制、提示或引导调整，以及基于掩码的约束等推理时机制完成编辑。我们将现有方法归纳为三类常见机制，这些机制通常会组合使用，以提升定位、内容保留和可控性。由于基于 token 的自回归模型较难直接用于无需训练的编辑，本节主要聚焦非自回归范式，尤其是基于扩散的基础模型。

<p align="center">
  <img src="assets/train-free.png" alt="无需训练的音频编辑方法概览" width="900">
</p>

<p align="center">
  <em>图 3：无需训练的音频编辑方法概览。</em>
</p>



| 范式 | 说明 | 代表性应用范围 |
| --- | --- | --- |
| 基于反演的编辑 | 将源音频映射回预训练生成模型的潜在空间、噪声空间或轨迹空间，再通过修改条件或采样轨迹进行编辑。 | DDPM/DDIM 反演、潜在表示反演、基于流的反演、语音或音乐的重建与编辑 |
| 注意力控制编辑 | 在不更新参数的情况下，通过修改或复用内部注意力模式来引导预训练生成模型。 | 交叉注意力事件定位、自注意力内容保留、提示级操作 |
| 掩码与区域引导编辑 | 在波形、频谱、潜在表示或音源成分空间中，指定编辑区域与保留区域。 | 局部编辑、音频补全、修复、音源级操作 |
| 基于编解码模型的 token 级编辑 | 在推理时通过掩码、填补、续写或选择性重新生成来操作离散音频 token。 | 语音填补、局部重新合成、编解码 token 编辑 |



---

<a id="resources"></a>

## 📦 资源

<a id="available-datasets"></a>

### 📊 可用数据集

用于音频编辑与可控音频生成的公开数据集，按照主要音频领域分类。

本列表并非穷尽所有可用数据集，仅收录部分适配音频编辑任务或被广泛使用的数据集；仓库维护人员已验证所有条目的可用性。

**配对**表示已发布源音频与目标音频、混合音频与分轨的对应关系，或明确匹配控制条件／演奏技法的录音（✅ / ❌）；仅共享转录文本、音频与文本对齐或音频与 MIDI 对齐不计为配对。**†** 表示该编辑用途需要构建任务或进行适配，并非原生编辑监督。编辑类型遵循本综述的**声学／实例／语义**分类体系。

时长为近似值，不重复累加不同模态或混合音频的分轨。**文本**指转录、描述或指令；仅含标签的元数据在**标注**列中说明。

<a id="speech"></a>

#### 语音（Speech）

| 名称 | 论文 | 数据集／代码 | 时长 | 配对 | 编辑类型 | 标注 | 涉及模态 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| VoiceBank+DEMAND (28-spk) | <a href="https://www.pure.ed.ac.uk/ws/portalfiles/portal/26377240/Interspeech2016_Cassia_1.pdf"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://datashare.ed.ac.uk/handle/10283/2791"><img height="20" src="https://img.shields.io/badge/DataShare-Data-2E8B57" alt="DataShare Data"></a> | ≈10 h | ✅ 含噪／干净 | 声学 | 转录文本；噪声／信噪比条件 | 音频、文本 |
| LibriTTS-R | <a href="https://arxiv.org/abs/2305.18802"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://www.openslr.org/141/"><img height="20" src="https://img.shields.io/badge/OpenSLR-Restored-2E8B57" alt="OpenSLR Restored"></a><br><a href="https://www.openslr.org/60/"><img height="20" src="https://img.shields.io/badge/OpenSLR-Original-2E8B57" alt="OpenSLR Original"></a> | ≈585 h | ✅ 原始／修复 | 声学；语义† | 转录文本；说话人标签；模型修复音频 | 音频、文本 |
| LibriSpeech | <a href="https://www.danielpovey.com/files/2015_icassp_librispeech.pdf"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://www.openslr.org/12/"><img height="20" src="https://img.shields.io/badge/OpenSLR-Data-2E8B57" alt="OpenSLR Data"></a> | ≈1,000 h | ❌ | 语义†；实例† | 转录文本；说话人／章节标签 | 音频、文本 |
| VCTK v0.92 | <a href="https://doi.org/10.7488/ds/2645"><img height="20" src="https://img.shields.io/badge/Dataset-Record-brightgreen" alt="Dataset Record"></a> | <a href="https://datashare.ed.ac.uk/handle/10283/3443"><img height="20" src="https://img.shields.io/badge/DataShare-Data-2E8B57" alt="DataShare Data"></a> | ≈44 h | ❌ | 实例†；语义† | 转录文本；说话人／口音标签 | 音频、文本 |
| AISHELL-3 | <a href="https://arxiv.org/abs/2010.11567"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://www.openslr.org/93/"><img height="20" src="https://img.shields.io/badge/OpenSLR-Data-2E8B57" alt="OpenSLR Data"></a> | ≈85 h | ❌ | 语义†；实例† | 普通话转录文本；音标转录；说话人标签 | 音频、文本 |
| Hi-Fi TTS | <a href="https://arxiv.org/abs/2104.01497"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://www.openslr.org/109/"><img height="20" src="https://img.shields.io/badge/OpenSLR-Data-2E8B57" alt="OpenSLR Data"></a> | ≈292 h | ❌ | 语义†；实例† | 转录文本；说话人标签 | 音频、文本 |
| LJSpeech v1.1 | <a href="https://keithito.com/LJ-Speech-Dataset/"><img height="20" src="https://img.shields.io/badge/Dataset-Release-brightgreen" alt="Dataset Release"></a> | <a href="https://data.keithito.com/data/speech/LJSpeech-1.1.tar.bz2"><img height="20" src="https://img.shields.io/badge/Download-Data-007EC6" alt="Download Data"></a> | ≈24 h | ❌ | 语义† | 转录文本；规范化文本 | 音频、文本 |
| RAVDESS（语音） | <a href="https://doi.org/10.1371/journal.pone.0196391"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://zenodo.org/records/1188976"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈1.7 h | ❌ | 语义† | 标签：情绪、强度、说话人；固定转录文本 | 音频、文本、视频 |
| CREMA-D | <a href="https://pmc.ncbi.nlm.nih.gov/articles/PMC4313618/"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://github.com/CheyneyComputerScience/CREMA-D"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://gitlab.com/cs-cooper-lab/crema-d-mirror"><img height="20" src="https://img.shields.io/badge/GitLab-Mirror-FC6D26?logo=gitlab&amp;logoColor=white" alt="GitLab Mirror"></a> | ≈5.3 h | ❌ | 语义† | 标签：情绪／强度；感知评分；固定转录文本 | 音频、文本、视频 |

<a id="music"></a>

#### 音乐（Music）

| 名称 | 论文 | 数据集／代码 | 时长 | 配对 | 编辑类型 | 标注 | 涉及模态 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| GTSinger | <a href="https://arxiv.org/abs/2409.13832"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/AaronZ345/GTSinger"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://huggingface.co/datasets/AaronZ345/GTSinger"><img height="20" src="https://img.shields.io/badge/HuggingFace-Dataset-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Dataset"></a><br><a href="https://drive.google.com/drive/folders/1xcdvCxNAEEfJElt7sEP-xT8dMKxn1_Lz"><img height="20" src="https://img.shields.io/badge/Google_Drive-Data-4285F4?logo=googledrive&amp;logoColor=white" alt="Google Drive Data"></a> | ≈80.6 h 歌声<br>+16.2 h 语音 | ✅ 受控／平行录音 | 语义；实例† | 标签：技法／风格；对齐的歌词／音素；乐谱 | 音频、文本、MusicXML |
| Slakh2100 | <a href="https://arxiv.org/abs/1909.08494"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ethman/slakh-utils"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://zenodo.org/records/4599666"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈145 h | ✅ 混合音频／分轨 | 实例 | 标签：乐器；对齐的 MIDI；分轨元数据 | 音频、MIDI |
| MUSDB18-HQ | <a href="https://arxiv.org/abs/1804.06267"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/sigsep/sigsep-mus-db"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://zenodo.org/records/3338373"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈10 h | ✅ 混合音频／分轨 | 实例 | 标签：人声、鼓、贝斯、其他 | 音频 |
| MAESTRO v3 | <a href="https://arxiv.org/abs/1810.12247"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://magenta.tensorflow.org/datasets/maestro"><img height="20" src="https://img.shields.io/badge/Project-Page-007EC6" alt="Project Page"></a><br><a href="https://storage.googleapis.com/magentadata/datasets/maestro/v3.0.0/maestro-v3.0.0.zip"><img height="20" src="https://img.shields.io/badge/Download-Data-007EC6" alt="Download Data"></a> | ≈199 h | ❌ | 语义† | 对齐的 MIDI：音高、时序、力度、踏板；曲目元数据 | 音频、MIDI |
| NSynth | <a href="https://arxiv.org/abs/1704.01279"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://magenta.tensorflow.org/datasets/nsynth"><img height="20" src="https://img.shields.io/badge/Project-Page-007EC6" alt="Project Page"></a> | ≈340 h | ❌ | 实例†；语义† | 标签：乐器、音高、力度、音色特征 | 音频 |
| Groove MIDI Dataset | <a href="https://arxiv.org/abs/1905.06118"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://magenta.tensorflow.org/datasets/groove"><img height="20" src="https://img.shields.io/badge/Project-Page-007EC6" alt="Project Page"></a><br><a href="https://storage.googleapis.com/magentadata/datasets/groove/groove-v1.0.0.zip"><img height="20" src="https://img.shields.io/badge/Download-Data-007EC6" alt="Download Data"></a> | ≈13.6 h | ❌ | 语义† | 对齐的 MIDI；速度／风格标签；演奏时序／力度 | 音频、MIDI |
| MusicCaps | <a href="https://arxiv.org/abs/2301.11325"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://huggingface.co/datasets/google/MusicCaps"><img height="20" src="https://img.shields.io/badge/HuggingFace-Metadata-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Metadata"></a> | ≈15.3 h | ❌ | 语义†；实例† | 描述文本；音乐属性标签 | 音频、文本 |
| MTG-Jamendo | <a href="https://sites.google.com/view/ml4md2019/program"><img height="20" src="https://img.shields.io/badge/Publication-Record-brightgreen" alt="Publication Record"></a> | <a href="https://github.com/MTG/mtg-jamendo-dataset"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://github.com/MTG/mtg-jamendo-dataset#downloading-the-data"><img height="20" src="https://img.shields.io/badge/Download-Data-007EC6" alt="Download Data"></a> | ≈3,770 h | ❌ | 语义†；实例† | 标签：流派、乐器、情绪／主题 | 音频 |
| FMA (large) | <a href="https://arxiv.org/abs/1612.01840"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/mdeff/fma"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://os.unil.cloud.switch.ch/fma/fma_large.zip"><img height="20" src="https://img.shields.io/badge/Download-Data-007EC6" alt="Download Data"></a> | ≈888 h | ❌ | 语义† | 标签：流派层级；曲目／艺术家元数据 | 音频 |

<a id="audio"></a>

#### 通用音频（Audio）

| 名称 | 论文 | 数据集／代码 | 时长 | 配对 | 编辑类型 | 标注 | 涉及模态 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| FUSS | <a href="https://arxiv.org/abs/2011.00803"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/google-research/sound-separation/tree/master/datasets/fuss"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://zenodo.org/records/3743844"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈61 h 混合音频 | ✅ 混合音频／音源；无混响／有混响 | 实例；声学 | 音源／时间元数据；混音参数；无事件标签 | 音频 |
| AudioSet | <a href="https://research.google/pubs/audio-set-an-ontology-and-human-labeled-dataset-for-audio-events/"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://research.google.com/audioset/download.html"><img height="20" src="https://img.shields.io/badge/Dataset-Metadata-007EC6" alt="Dataset Metadata"></a> | ≈5,790 h | ❌ | 实例† | 标签：声音事件本体；片段级多标签 | 音频、视频（上游来源） |
| AudioCaps v1 | <a href="https://aclanthology.org/N19-1011/"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://github.com/cdjkim/audiocaps/tree/master/dataset"><img height="20" src="https://img.shields.io/badge/GitHub-Metadata-181717?logo=github&amp;logoColor=white" alt="GitHub Metadata"></a> | ≈143 h | ❌ | 实例†；语义† | 描述文本：每个片段一条或五条描述 | 音频、文本 |
| Clotho v2.1 | <a href="https://arxiv.org/abs/1910.09387"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://zenodo.org/records/4783391"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈37 h<br>（5,929 个已标注片段） | ❌ | 实例†；语义† | 描述文本：每个片段五条；Freesound 关键词 | 音频、文本 |
| WavCaps | <a href="https://arxiv.org/abs/2303.17395"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/XinhaoMei/WavCaps"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://huggingface.co/datasets/cvssp/WavCaps"><img height="20" src="https://img.shields.io/badge/HuggingFace-Dataset-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Dataset"></a> | ≈7,568 h | ❌ | 实例†；语义† | LLM 辅助描述；来源描述／元数据 | 音频、文本 |
| FSD50K | <a href="https://arxiv.org/abs/2010.00475"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://zenodo.org/records/4060432"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈108 h | ❌ | 实例† | 标签：200 类声音事件；片段级多标签 | 音频 |
| ESC-50 | <a href="https://www.karolpiczak.com/papers/Piczak2015-ESC-Dataset.pdf"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://github.com/karolpiczak/ESC-50"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | ≈2.8 h | ❌ | 实例† | 标签：50 类环境声音 | 音频 |
| UrbanSound8K | <a href="https://drive.google.com/file/d/0B2SQvWn0_78BX2wtbWZLVnRhSDg/view?usp=sharing"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper Link"></a> | <a href="https://urbansounddataset.weebly.com/urbansound8k.html"><img height="20" src="https://img.shields.io/badge/Project-Page-007EC6" alt="Project Page"></a><br><a href="https://zenodo.org/records/1203745"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈8.8 h | ❌ | 实例† | 标签：10 类城市声音；显著性；源片段时间戳 | 音频 |
| VGGSound | <a href="https://arxiv.org/abs/2004.14368"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/hche11/VGGSound/tree/master/data"><img height="20" src="https://img.shields.io/badge/GitHub-Metadata-181717?logo=github&amp;logoColor=white" alt="GitHub Metadata"></a> | ≈550 h | ❌ | 实例† | 标签：视听事件类别；视频时间戳 | 音频、视频（上游来源） |

<a id="unified"></a>

#### 跨领域（Unified）

这些语料同时包含语音、音乐和通用声音。

| 名称 | 论文 | 数据集／代码 | 时长 | 配对 | 编辑类型 | 标注 | 涉及模态 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| AudioEdit (Audio-Omni) | <a href="https://arxiv.org/abs/2604.10708"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/ZeyueT/Audio-Omni"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://huggingface.co/datasets/HKUSTAudio/AudioEdit"><img height="20" src="https://img.shields.io/badge/HuggingFace-Dataset-FFD21E?logo=huggingface&amp;logoColor=black" alt="HuggingFace Dataset"></a> | ≈2,686 h<br>（966,794 个任务配对） | ✅ 源音频／编辑目标 | 实例 | 指令：添加、移除、提取、音源变换 | 音频、文本 |
| Divide and Remaster v2 | <a href="https://arxiv.org/abs/2110.09958"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://github.com/darius522/dnr-utils"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a><br><a href="https://zenodo.org/records/6949108"><img height="20" src="https://img.shields.io/badge/Zenodo-Data-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Data"></a> | ≈81 h | ✅ 混合音频／分轨 | 实例 | 转录文本；音乐流派；声音标签／时间戳 | 音频、文本 |
| MUSAN | <a href="https://arxiv.org/abs/1510.08484"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv Paper"></a> | <a href="https://www.openslr.org/17/"><img height="20" src="https://img.shields.io/badge/OpenSLR-Data-2E8B57" alt="OpenSLR Data"></a> | ≈109 h | ❌ | 声学†；实例† | 标签：语音／音乐／噪声；语音和音乐元数据 | 音频 |

<a id="data-tools"></a>

### 🛠️ 数据工具

用于构建编辑数据和标注已有录音的开源工具。**支持的任务类型**遵循本综述的**声学／语义／实例**分类体系，表示各工具可帮助构建的编辑监督类型。**跨领域（Unified）**包含适用于语音、音乐和通用音频的工具。

#### 数据生成工具

通过合成、音源分离、混音和信号处理构建音频样本及源音频—目标音频对。

##### 语音（Speech）

| 工具 | 支持的任务类型 | 构建内容 | 控制粒度 | 代码 | 模型 |
| --- | --- | --- | --- | --- | --- |
| Qwen3-TTS | 语义；实例 | 与文本对齐的语音，可用指令控制表达方式或指定参考说话人。 | 句级 | <a href="https://github.com/QwenLM/Qwen3-TTS"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/Qwen/Qwen3-TTS-12Hz-1.7B-Base"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Base-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Base"></a><br><a href="https://huggingface.co/Qwen/Qwen3-TTS-12Hz-1.7B-CustomVoice"><img height="20" src="https://img.shields.io/badge/Hugging_Face-CustomVoice-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face CustomVoice"></a> |
| CosyVoice3 | 语义；实例 | 与文本对齐的语音，支持声音克隆，以及通过提示控制语言、情绪或表达方式。 | 句级；发音单元 | <a href="https://github.com/QwenAudio/CosyVoice"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/FunAudioLLM/Fun-CosyVoice3-0.5B-2512"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |
| MaskGCT | 语义；实例 | 以文本为条件、参考指定音色且总时长可配置的语音。 | 句级；总时长 | <a href="https://github.com/open-mmlab/Amphion/tree/main/models/tts/maskgct"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/amphion/MaskGCT"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |
| Seed-VC | 实例 | 与源语音配对的声音转换录音，用于说话人／音色替换。 | 句级／源录音 | <a href="https://github.com/Plachtaa/seed-vc"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/Plachta/Seed-VC"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |
| AuK | 声学；语义；实例 | 按指令编辑的语音，覆盖内容、表达方式、音色、增强和目标说话人任务。 | 句级；文本指定的词／短语 | <a href="https://github.com/Tencent-Hunyuan/AuK"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/tencent/AuK"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |

##### 音乐（Music）

| 工具 | 支持的任务类型 | 构建内容 | 控制粒度 | 代码 | 模型 |
| --- | --- | --- | --- | --- | --- |
| MusicGen | 语义 | 以文本或旋律为条件的音乐片段及续写，用于构建风格／内容可控的样本。 | 片段；旋律序列 | <a href="https://github.com/facebookresearch/audiocraft"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/facebook/musicgen-melody"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Melody-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Melody"></a> |
| Demucs | 实例 | 估计的人声、鼓、贝斯及其他分轨，用于构建提取、移除与重混音配对。 | 分轨／曲目 | <a href="https://github.com/facebookresearch/demucs"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://dl.fbaipublicfiles.com/demucs/hybrid_transformer/955717e8-8726e21a.th"><img height="20" src="https://img.shields.io/badge/Model-Checkpoint-2E8B57" alt="Model Checkpoint"></a> |
| Spleeter | 实例 | 估计的 2、4 或 5 分轨分解结果，用于音源移除、提取和重混音。 | 分轨／曲目 | <a href="https://github.com/deezer/spleeter"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://github.com/deezer/spleeter/releases/tag/v1.4.0"><img height="20" src="https://img.shields.io/badge/GitHub-Checkpoints-181717?logo=github&amp;logoColor=white" alt="GitHub Checkpoints"></a> |
| FluidSynth | 语义；实例 | 使用 MIDI 与 SoundFont 渲染的音频，与音符、力度和乐器分配对齐。 | 音符；MIDI 控制事件／轨道 | <a href="https://github.com/FluidSynth/fluidsynth"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |

##### 通用音频（Audio）

| 工具 | 支持的任务类型 | 构建内容 | 控制粒度 | 代码 | 模型 |
| --- | --- | --- | --- | --- | --- |
| AudioLDM 2 | 实例 | 以文本为条件生成声音片段，作为插入或替换样本中的音源素材。 | 片段 | <a href="https://github.com/haoheliu/AudioLDM2"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/cvssp/audioldm2"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |
| AudioSep | 实例 | 从混合音频中按文本选择的音源估计，用于构建提取与移除配对。 | 描述指定的音源／片段 | <a href="https://github.com/Audio-AGI/AudioSep"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/spaces/Audio-AGI/AudioSep/tree/main/checkpoint"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Checkpoints-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Checkpoints"></a> |
| Scaper | 声学；实例 | 包含事件标签、起止时间、信噪比及可选独立事件轨道的合成声景。 | 事件；起始时间／时长／信噪比 | <a href="https://github.com/justinsalamon/scaper"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |
| SpatialScaper | 声学；实例 | 包含事件活动、音源轨迹和房间响应条件的空间声景。 | 事件／轨迹／场景 | <a href="https://github.com/marl/SpatialScaper"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |

##### 跨领域（Unified）

| 工具 | 支持的任务类型 | 构建内容 | 控制粒度 | 代码 | 模型 |
| --- | --- | --- | --- | --- | --- |
| SAM-Audio | 实例 | 按提示选择的目标音频与残余音频，用于提取、移除与重混音样本。 | 音源；时间区间提示 | <a href="https://github.com/facebookresearch/sam-audio"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/facebook/sam-audio-large"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a><br>需申请访问 |
| Audiomentations | 声学；语义 | 利用噪声、增益、滤波等变换构建增强音频，用于干净／退化及音高／速度对照配对。 | 片段；通过切片选择的区间 | <a href="https://github.com/iver56/audiomentations"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |
| Pedalboard | 声学 | 通过均衡、增益、压缩、失真与混响处理音频，构建干声／湿声或干净／退化配对。 | 片段／处理块 | <a href="https://github.com/spotify/pedalboard"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |
| Pyroomacoustics | 声学；实例 | 根据音源位置生成房间脉冲响应和麦克风混合音频，包含无混响／有混响配对。 | 场景／音源位置 | <a href="https://github.com/LCAV/pyroomacoustics"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |

#### 数据标注工具

从已有音频中提取或创建内容、属性和时间标注的工具。

##### 语音（Speech）

| 工具 | 支持的任务类型 | 标注内容 | 标注粒度 | 代码 | 模型 |
| --- | --- | --- | --- | --- | --- |
| Montreal Forced Aligner (MFA) | 语义 | 将语音与给定转录及发音词典对齐，获得词与音素边界。 | 词／音素 | <a href="https://github.com/MontrealCorpusTools/Montreal-Forced-Aligner"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://mfa-models.readthedocs.io/en/latest/acoustic/index.html"><img height="20" src="https://img.shields.io/badge/Model-Acoustic%20models-2E8B57" alt="Model Acoustic models"></a> |
| WhisperX | 语义 | ASR 转录及由特定语言对齐模型提供的词级时间戳。 | 句级／词 | <a href="https://github.com/m-bain/whisperX"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/Systran/faster-whisper-large-v3"><img height="20" src="https://img.shields.io/badge/Hugging_Face-ASR-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face ASR"></a><br><a href="https://huggingface.co/facebook/wav2vec2-large-960h-lv60-self"><img height="20" src="https://img.shields.io/badge/Hugging_Face-EN%20aligner-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face EN aligner"></a> |
| Qwen3-ASR + ForcedAligner | 语义 | 利用公开的 ASR 与强制对齐模型生成转录、语言标签和文本单元时间戳。 | 句级／词 | <a href="https://github.com/QwenLM/Qwen3-ASR"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/Qwen/Qwen3-ASR-1.7B"><img height="20" src="https://img.shields.io/badge/Hugging_Face-ASR-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face ASR"></a><br><a href="https://huggingface.co/Qwen/Qwen3-ForcedAligner-0.6B"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Aligner-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Aligner"></a> |
| pyannote.audio | 实例 | 带说话人标签的发言轮次及重叠说话人活动。 | 说话轮次／片段 | <a href="https://github.com/pyannote/pyannote-audio"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/pyannote/speaker-diarization-community-1"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Community--1-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Community-1"></a><br>需接受访问条款 |
| Silero VAD | 实例 | 语音／非语音概率及检测到的语音起止时间。 | 帧／语音片段 | <a href="https://github.com/snakers4/silero-vad"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://github.com/snakers4/silero-vad/tree/master/src/silero_vad/data"><img height="20" src="https://img.shields.io/badge/GitHub-Weights-181717?logo=github&amp;logoColor=white" alt="GitHub Weights"></a> |
| emotion2vec+ | 语义 | 语音情绪标签与分数，并可输出学习得到的情绪表征。 | 句级（标签）；帧级（特征） | <a href="https://github.com/ddlBoJack/emotion2vec"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/emotion2vec/emotion2vec_plus_large"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Large-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Large"></a> |
| FunASR / SenseVoiceSmall | 语义；实例 | 转录、语言和情绪标签，以及笑声、掌声等声音事件标签。 | 句级／VAD 片段 | <a href="https://github.com/modelscope/FunASR"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/FunAudioLLM/SenseVoiceSmall"><img height="20" src="https://img.shields.io/badge/Hugging_Face-SenseVoiceSmall-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face SenseVoiceSmall"></a> |
| Praat / Parselmouth | 声学；语义 | 音高、共振峰与强度轨迹；Praat 中手动定义的 TextGrid 点与区间。 | 帧；词／音素／区间（手动） | <a href="https://github.com/praat/praat.github.io"><img height="20" src="https://img.shields.io/badge/GitHub-Praat-181717?logo=github&amp;logoColor=white" alt="GitHub Praat"></a><br><a href="https://github.com/YannickJadoul/Parselmouth"><img height="20" src="https://img.shields.io/badge/GitHub-Parselmouth-181717?logo=github&amp;logoColor=white" alt="GitHub Parselmouth"></a> |  |

##### 音乐（Music）

| 工具 | 支持的任务类型 | 标注内容 | 标注粒度 | 代码 | 模型 |
| --- | --- | --- | --- | --- | --- |
| RMVPE | 语义 | 从复调音乐中提取的人声基频（F0）轨迹。 | 帧 | <a href="https://github.com/Dream-High/RMVPE"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://drive.google.com/file/d/1JNtNT37KiLq9uFQqHk7JFs-3trxd3bRh/view"><img height="20" src="https://img.shields.io/badge/Google_Drive-ROSVOT%20bundle-4285F4?logo=googledrive&amp;logoColor=white" alt="Google Drive ROSVOT bundle"></a> |
| CREPE | 语义 | 单音音频的基频（F0）估计与置信度。 | 帧 | <a href="https://github.com/marl/crepe"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://github.com/marl/crepe/tree/models"><img height="20" src="https://img.shields.io/badge/GitHub-Weights-181717?logo=github&amp;logoColor=white" alt="GitHub Weights"></a> |
| ROSVOT | 语义 | 歌声音符的音高与起止时间，以及由 RWBD 组件获得的词边界。 | 音符／词 | <a href="https://github.com/RickyL-2000/ROSVOT"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://drive.google.com/file/d/1JNtNT37KiLq9uFQqHk7JFs-3trxd3bRh/view"><img height="20" src="https://img.shields.io/badge/Google_Drive-Checkpoints-4285F4?logo=googledrive&amp;logoColor=white" alt="Google Drive Checkpoints"></a> |
| Basic Pitch | 语义 | 以 MIDI 导出的复调音符事件与弯音；一次处理单一乐器时效果最佳。 | 音符；帧级音高曲线 | <a href="https://github.com/spotify/basic-pitch"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://github.com/spotify/basic-pitch/tree/main/basic_pitch/saved_models"><img height="20" src="https://img.shields.io/badge/GitHub-Weights-181717?logo=github&amp;logoColor=white" alt="GitHub Weights"></a> |
| All-In-One Music Structure Analyzer | 语义 | 速度、节拍／小节首拍时间戳，以及主歌、副歌、桥段等段落标签。 | 节拍／小节首拍／段落 | <a href="https://github.com/mir-aidj/all-in-one"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/taejunkim/allinone"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Models-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Models"></a> |
| Music Flamingo | 语义；实例 | 关于乐器配置、和声、情绪、结构与歌词的音乐描述和问答标注。 | 片段／完整曲目（自由文本） | <a href="https://github.com/NVIDIA/audio-flamingo/tree/music_flamingo"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/nvidia/music-flamingo-hf"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |

##### 通用音频（Audio）

| 工具 | 支持的任务类型 | 标注内容 | 标注粒度 | 代码 | 模型 |
| --- | --- | --- | --- | --- | --- |
| PANNs | 实例 | 使用公开的决策级检测模型，获得声音事件类别分数与逐帧活动。 | 片段／帧 | <a href="https://github.com/qiuqiangkong/audioset_tagging_cnn"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://zenodo.org/records/3987831"><img height="20" src="https://img.shields.io/badge/Zenodo-Models-1682D4?logo=zenodo&amp;logoColor=white" alt="Zenodo Models"></a> |
| HTS-AT | 实例 | 声音事件标签，以及定位模式下类别激活的时间分布估计。 | 片段／帧 | <a href="https://github.com/RetroCirce/HTS-Audio-Transformer"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://drive.google.com/drive/folders/1f5VYMk0uos_YnuBshgmaTVioXbs7Kmz6?usp=sharing"><img height="20" src="https://img.shields.io/badge/Google_Drive-Models-4285F4?logo=googledrive&amp;logoColor=white" alt="Google Drive Models"></a> |
| YAMNet | 实例 | 在重叠音频窗口上预测 521 类声音事件的分数。 | 0.96 s 窗口；0.48 s 步长 | <a href="https://github.com/tensorflow/models/tree/master/research/audioset/yamnet"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://storage.googleapis.com/audioset/yamnet.h5"><img height="20" src="https://img.shields.io/badge/Model-Checkpoint-2E8B57" alt="Model Checkpoint"></a> |

##### 跨领域（Unified）

| 工具 | 支持的任务类型 | 标注内容 | 标注粒度 | 代码 | 模型 |
| --- | --- | --- | --- | --- | --- |
| Qwen3-Omni Captioner | 声学；语义；实例 | 涵盖语音、音乐、声音事件与声学特征的详细音频描述。 | 片段／录音（自由文本） | <a href="https://github.com/QwenLM/Qwen3-Omni"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/Qwen/Qwen3-Omni-30B-A3B-Captioner"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Captioner-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Captioner"></a> |
| Audio Flamingo 3 | 语义；实例 | 根据提示生成转录、描述、事件说明与音频问答标注。 | 片段／录音（自由文本） | <a href="https://github.com/NVIDIA/audio-flamingo/tree/audio_flamingo_3"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> | <a href="https://huggingface.co/nvidia/audio-flamingo-3-hf"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="Hugging Face Model"></a> |
| Label Studio | 声学；语义；实例 | 通过可配置音频模板，人工编写片段标签、时间区域标签和转录。 | 片段／手动选定区间 | <a href="https://github.com/HumanSignal/label-studio"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub Code"></a> |  |

<a id="benchmarks"></a>

### 🧪 评测基准

公开的音频编辑评测资源。**编辑类别**遵循本综述的分类体系：**声学／语义／实例／复合**，其中**复合**指同一请求涉及不同编辑类别。**评测方法**描述评分方式：**专家模型**、**MLLM** 或 **Hybrid（混合式，包含基于智能体的评测）**。


#### MMAE

- **概述：** 包含**2,000 个样例（≈8.0 h）**、六个复杂度等级和 **17,741 条验证准则**，评估语音、音乐、通用声音及其混合场景下的指令遵循与内容保留。
- **论文：** [arXiv](https://arxiv.org/abs/2606.07229)；**代码：** [GitHub](https://github.com/ddlBoJack/MMAE)；**数据集：** [Hugging Face](https://huggingface.co/datasets/BoJack/MMAE)。
- **音频模态：** 语音；音乐；通用音频。
- **编辑类别：** 声学；语义；实例；复合。
- **评测方法：** **MLLM** — Qwen3-Omni 逐条判断评分准则，并通过多数投票计算指令遵循率（IFR）、一致性率（CR）和完全匹配率（EMR）。
- **已报告的最佳结果：**
  - **单模型：** 在[原始比较](https://arxiv.org/pdf/2606.07229)的完整基准上，**Step-Audio-EditX** 的 IFR（**44.86%**）和 CR（**58.88%**）最高，**Ming-UniAudio** 的 EMR（**3.20%**）最高；**Audio-Omni** 在单独的 **801 个样例、≤10 s** 子集上达到 **4.99% EMR**。较新的[不使用 Prompt Enhancer 的 AuK 基线](https://github.com/Audio-Editing-Challenge/Audio-Editing-Challenge-Baseline#results)在 **1,003 个样例的单操作子集**上报告 **7.58% EMR**。
  - **Agent／LLM 辅助系统：** [挑战赛 Agent 基线](https://github.com/Audio-Editing-Challenge/Audio-Editing-Challenge-Baseline#results)结合 LLM 路由器、DSP、SAM-Audio 与 AuK，在**全部 2,000 个样例**上报告 **7.45% EMR、44.06% IFR 和 74.63% CR**。另有[启用 Prompt Enhancer 的 AuK-Flash](https://arxiv.org/html/2609.08936v1#A1.T7)，在 **MMAE-Speech** 上达到 **13.85% EMR**；这些结果的评测范围不同，不能直接比较。

#### SpeechEditBench

- **概述：** 通过 **4,700 个样例（≈9.4 h）**，在双语语音编辑中分别评估编辑成功与语言内容保留，覆盖七种原子属性和多属性指令。
- **论文：** [arXiv](https://arxiv.org/abs/2606.01804)；**代码：** [GitHub](https://github.com/daxintan-cuhk/SpeechEditBench)；**数据集：** [Hugging Face, v1.1](https://huggingface.co/datasets/DiscreteSpeech/SpeechEditBench/tree/v1.1)。
- **音频模态：** 语音。
- **编辑类别：** 声学；语义；实例；复合。
- **评测方法：** **Hybrid（混合式）** — 结合 ASR、说话人验证、声学／韵律测量及 Gemini 音频评判器，计算目标达成、内容保留及二者联合成功率。
- **已报告的最佳结果：**
  - **单模型：** 按任务划分，[GPT-Realtime](https://arxiv.org/html/2606.01804v3#S5)的联合成功率在**内容、风格和副语言**任务上分别为 **96.67%、68.67% 和 47.00%**；Gemini-Live 在**情绪**和**组合**任务上分别达到 **27.79% 和 11.00%**。较新的 [AuK 比较](https://arxiv.org/html/2609.08936v1#S7.SS3)报告了 **71.33% 的韵律联合成功率**，但仅覆盖五种任务。

#### Ming-Freeform-Audio-Edit

- **概述：** 通过**约 3.3k 条指令样例**评估无需时间戳的指令式语音编辑，覆盖中英文 Basic／Full 词汇编辑及五种属性控制任务。
- **论文：** [arXiv](https://arxiv.org/abs/2511.05516)；**代码：** [GitHub](https://github.com/inclusionAI/Ming-Freeform-Audio-Edit)；**数据集：** [Hugging Face](https://huggingface.co/datasets/inclusionAI/Ming-Freeform-Audio-Edit-Benchmark)；**项目主页：** [Ming-UniAudio](https://xqacmer.github.io/Ming-Unitok-Audio.github.io/)。
- **音频模态：** 语音。
- **编辑类别：** 声学；语义。
- **评测方法：** **Hybrid（混合式）** — Whisper／Paraformer 与 WavLM 衡量转录和说话人保留，信号测量评估语速／音量控制，具备音频能力的评判器评估情绪／方言转换。
- **已报告的最佳结果：**
  - **单模型：** [AuK](https://arxiv.org/html/2609.08936v1#S7.SS3)在 **Full 中文／英文**上，按删除、插入和替换任务取平均后，报告 **3.09%／3.96% WER** 与 **91.47%／85.25% 编辑准确率**，在已核查的词汇编辑比较中领先。

#### Step-Audio-Edit-Benchmark

- **概述：** 使用 **8 名说话人与 8,800 条文本提示**评估情绪、说话风格和副语言表达的表现力编辑与迭代编辑，公开了参考音色，**输出时长取决于合成结果**。
- **论文：** [arXiv](https://arxiv.org/abs/2511.03601)；**代码：** [GitHub](https://github.com/stepfun-ai/Step-Audio-Edit-Benchmark)；**数据集：** [Prompt texts](https://github.com/stepfun-ai/Step-Audio-Edit-Benchmark/tree/main/data) · [Reference audio](https://github.com/stepfun-ai/Step-Audio-Edit-Benchmark/tree/main/prompt_audios)；**项目主页：** [Step-Audio-EditX](https://stepaudiollm.github.io/step-audio-editx/)。
- **音频模态：** 语音。
- **编辑类别：** 语义。
- **评测方法：** **MLLM** — Gemini-2.5-Pro 衡量情绪／风格分类准确率，并以 1–3 分评定副语言表达的实现程度。
- **已报告的最佳结果：**
  - **单模型：** 在已发表的原生输入比较中，[Step-Audio-EditX](https://arxiv.org/html/2511.03601v2#S5)经过**三次编辑迭代**后达到 **71.0% 情绪准确率**和 **66.2% 风格准确率**；一次迭代后的**副语言分数为 2.89/3**。

#### LyricEditBench (INTERSPEECH 2026)

- **概述：** 包含 **7,200 个双语样例，每个样例使用 ≤15 s 的旋律参考**，在六类歌词编辑场景及同音色、跨音色设置下，评估保留旋律的歌词修改。
- **论文：** [arXiv](https://arxiv.org/abs/2603.24589)；**代码：** [GitHub](https://github.com/ASLP-lab/YingMusic-Singer-Plus)；**数据集：** [Hugging Face](https://huggingface.co/datasets/ASLP-lab/LyricEditBench)；**项目主页：** [YingMusic-Singer-Plus](https://aslp-lab.github.io/YingMusic-Singer-Plus-Demo/)。
- **音频模态：** 音乐。
- **编辑类别：** 语义；实例；复合（跨音色设置中同时进行歌词修改与歌手身份迁移）。
- **评测方法：** **专家模型** — 使用歌声 ASR 计算音素错误率（PER）、WavLM 衡量说话人相似度、RMVPE 计算 F0 相关性、VocalVerse2 评估人声质量，并辅以人工听评。
- **已报告的最佳结果：**
  - **单模型：** 在已发表的比较中，[YingMusic-Singer](https://arxiv.org/html/2603.24589v3#S4)的歌词可懂度、旋律遵循和人声质量优于 Vevo2；在**中文局部替换、同音色**设置下，达到 **2.14% PER** 和 **0.9615 F0 相关系数**。Vevo2 在该设置的说话人相似度上仍具有优势。

#### ZoME-Bench (ACM MM 2025)

- **概述：** 提供 **1,100 个音乐编辑样例（每个 10 s，按样例计约 3.1 h）**，涵盖乐器、流派、情绪、节奏、旋律和背景修改，并通过描述与指令同时支持基于提示和基于指令的评测。
- **论文：** [MEDIC](https://arxiv.org/abs/2407.13220)；**代码：** [MEDIC 仓库](https://github.com/liuhuadai/MEDIC)（尚未发布实现）· [后续评测代码](https://github.com/hengtsune1024/AnchorSteer/tree/master/eval)；**数据集：** [Hugging Face 元数据](https://huggingface.co/datasets/liuhuadai/ZoME-Bench)（源音频需另行从 MusicCaps／YouTube 获取）；**项目主页：** [MEDIC](https://medic-edit.github.io/)。
- **音频模态：** 音乐。
- **编辑类别：** 语义；实例。
- **评测方法：** **专家模型** — 使用 CLAP、LPAPS、色度相似度等音频—文本对齐、感知与结构指标，并辅以人工评分。
- **已报告的最佳结果：**
  - **单模型／非 Agent 编辑器：** 在后续的 [AnchorSteer 乐器编辑比较](https://brianchen1120.github.io/project/anchorsteer/)中，条件版本在所比较方法中取得最高的 **CLAP（0.395）**和 **GAP（0.279）**；无条件版本则保留了更多结构（**色度相似度 0.470**，条件版本为 **0.238**）。

#### MelodiaEdit (AAAI 2026)

- **概述：** 基于 **180 个公开源片段（去重音频约 0.86 h）构建 2,015 个编辑对**，结合合成音乐与真实音乐，评估保留音乐结构的乐器、流派和情绪修改。
- **论文：** [AAAI 论文集](https://ojs.aaai.org/index.php/AAAI/article/view/37204)；**代码：** [GitHub](https://github.com/YiYang-SCUT/Melodia)（公开数据；尚未发布评测实现）；**数据集：** [音频与提示](https://github.com/YiYang-SCUT/Melodia/tree/main/MelodiaEdit/MelodiaEdit)；**项目主页：** [Melodia](https://melodia-edit.github.io/)。
- **音频模态：** 音乐。
- **编辑类别：** 语义；实例。
- **评测方法：** **专家模型** — 使用 CLAP、LPAPS、色度相似度、FAD 及综合遵循／保留分数，并辅以人工听评。
- **已报告的最佳结果：**
  - **单模型：** 在[已发表的比较](https://ojs.aaai.org/index.php/AAAI/article/download/37204/41166)中，**Melodia** 在 MelodiaEdit 上取得最高的 **CLAP（0.39）**和最低的 **LPAPS（3.11）**；**MusicMagus** 则在**色度相似度（0.73）**和 **FAD（0.57）**上领先，体现了目标对齐与内容保留之间的权衡。

#### AvED-Bench (WACV 2026)

- **概述：** 从 VGGSound 中筛选 **110 个视听片段（每个 10 s，约 18.3 min）**，提供源／目标描述，评估声音事件与视觉实体的同步替换。
- **论文：** [arXiv](https://arxiv.org/abs/2503.20782)；**代码：** [GitHub](https://github.com/GenjiB/AVED)；**数据集：** [基准 CSV](https://genjib.github.io/project_page/AVED/assets/avedit_dataset_v3.csv)（源片段需另行从 VGGSound／YouTube 获取）；**项目主页：** [AvED](https://genjib.github.io/project_page/AVED/index.html)。
- **音频模态：** 通用音频（附带视频输入）。
- **编辑类别：** 实例；同时编辑视频和声音，本身不构成复合音频编辑。
- **评测方法：** **专家模型** — 使用基于嵌入的音频—文本／音频—视频对齐及感知保留指标，并辅以人工判断。
- **已报告的最佳结果：**
  - **单模型／非 Agent 系统：** 后续的 [CoherentAVEdit 比较](https://arxiv.org/html/2512.07209v2#S4)中，**VACE → CoherentAVEdit** 在**六个视频的主观评测子集**上取得最好的听评结果：**音频—文本忠实度 3.7/5、视听对齐 3.8/5、结构保留 3.9/5**。这是顺序执行的非 Agent 流程，并非单一联合模型，也不代表完整数据集上的综合排名。

#### AVE-Compass

- **概述：** 通过 **145 个源视频（最长 10 s）、196 条指令和 2,688 个检查项**，覆盖 28 种编辑操作，分析自由形式视听编辑中的指令遵循与内容保留。
- **论文：** [arXiv](https://arxiv.org/abs/2607.24821)；**代码：** [GitHub](https://github.com/NJU-LINK/AVE-Compass)；**数据集：** [Hugging Face](https://huggingface.co/datasets/NJU-LINK/AVE-Compass)；**项目主页：** [AVE-Compass](https://ave-compass.github.io/)。
- **音频模态：** 语音；音乐；通用音频（附带视频输入）。
- **编辑类别：** 声学；语义；实例；复合（当音频编辑请求本身跨越不同类别时）。
- **评测方法：** **Hybrid（混合式）** — 将基于检查项的 MLLM 评判与专家模型结合，评估音频质量、视听／唇形同步及视觉保留。
- **已报告的最佳结果：**
  - **单模型：** [官方榜单](https://github.com/NJU-LINK/AVE-Compass#leaderboard)中，**Wan2.7** 的整体编辑意图分数最高，为 **42.4/100**（**音频：24.8**）；所列单模型中，**LTX2** 的音频编辑意图分数最高，为 **26.4/100**。
  - **Agent：** 同一榜单上，**AVE-Agent (Wan)** 以**整体编辑意图 59.8/100** 和**音频编辑意图 50.2/100** 领先。

<a id="evaluation-protocols-and-benchmarks"></a>
<a id="evaluation-metrics"></a>

### 📏 评测指标

指标按照本综述的四个评测维度组织。**↑ / ↓** 分别表示越高／越低越好。**参考信息／输入**列出了除编辑结果以外还需提供的信息。

#### 指令遵循

| 指标 | 衡量内容 | 音频模态 | 参考信息／输入 | 论文／标准 | 代码／模型 |
| --- | --- | --- | --- | --- | --- |
| WER / CER ↓ | ASR 转录相对于目标词或字符的错误率。 | 语音 | 目标转录文本；编辑结果的 ASR 转录。 | <a href="https://arxiv.org/abs/2212.04356"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/jitsi/jiwer"><img height="20" src="https://img.shields.io/badge/GitHub-JiWER-181717?logo=github&amp;logoColor=white" alt="JiWER"></a><br><a href="https://github.com/openai/whisper"><img height="20" src="https://img.shields.io/badge/GitHub-ASR-181717?logo=github&amp;logoColor=white" alt="ASR"></a> |
| 情绪分类准确率 ↑ | 预测情绪与目标情绪标签的一致程度。 | 语音 | 目标情绪标签；标签集匹配的情绪分类器。 | <a href="https://arxiv.org/abs/2312.15185"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/ddlBoJack/emotion2vec"><img height="20" src="https://img.shields.io/badge/GitHub-emotion2vec-181717?logo=github&amp;logoColor=white" alt="emotion2vec"></a> |
| CLAP 音频—文本相似度 ↑ | 输出音频与目标音频描述之间的余弦相似度。 | 音乐；通用音频 | 描述目标结果的文本；指定的 CLAP 权重。 | <a href="https://arxiv.org/abs/2211.06687"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/LAION-AI/CLAP"><img height="20" src="https://img.shields.io/badge/GitHub-CLAP-181717?logo=github&amp;logoColor=white" alt="CLAP"></a> |
| 事件出现分数（EOS）↑ | 文本引导音源分离后，事件级 CLAP 相似度的最小值；衡量所要求事件的覆盖情况。 | 通用音频 | 目标事件描述；事件分解及分离后的事件音轨。 | <a href="https://aclanthology.org/2025.acl-long.1147/"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper"></a> |  |

#### 内容保留与局部性

对于局部编辑，应比较需要保持不变的区域或音源。

| 指标 | 衡量内容 | 音频模态 | 参考信息／输入 | 论文／标准 | 代码／模型 |
| --- | --- | --- | --- | --- | --- |
| 说话人嵌入余弦相似度 ↑ | 编辑语音中说话人身份的保留程度。 | 语音 | 源说话人音频；两段录音使用相同的说话人验证编码器。 | <a href="https://arxiv.org/abs/2005.07143"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://huggingface.co/speechbrain/spkrec-ecapa-voxceleb"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="HF Model"></a> |
| 多分辨率 STFT 距离 ↓ | 多个时频分辨率下的频谱收敛度与对数幅度差异。 | 语音；音乐；通用音频 | 未编辑区域中对齐的源音频与输出音频。 | <a href="https://arxiv.org/abs/1910.11480"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/csteinmetz1/auraloss"><img height="20" src="https://img.shields.io/badge/GitHub-auraloss-181717?logo=github&amp;logoColor=white" alt="auraloss"></a> |
| CLAP 音频—音频相似度 ↑ | 源音频与编辑音频嵌入的语义相似度，作为整体内容保留的近似指标。 | 音乐；通用音频 | 源音频；局部比较时使用对应的非目标区域或分轨。 | <a href="https://arxiv.org/abs/2507.11096"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/LAION-AI/CLAP"><img height="20" src="https://img.shields.io/badge/GitHub-CLAP-181717?logo=github&amp;logoColor=white" alt="CLAP"></a> |
| LPAPS 距离 ↓ | 预训练特征网络所提取音频表征之间的感知距离。 | 音乐；通用音频 | 源音频；局部比较时使用对齐的未编辑区域。 | <a href="https://arxiv.org/abs/2402.10009"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/HilaManor/AudioEditingCode#evaluation"><img height="20" src="https://img.shields.io/badge/GitHub-LPAPS-181717?logo=github&amp;logoColor=white" alt="LPAPS"></a> |

#### 时间与结构一致性

| 指标 | 衡量内容 | 音频模态 | 参考信息／输入 | 论文／标准 | 代码／模型 |
| --- | --- | --- | --- | --- | --- |
| 边界误差 ↓ | 预测语音片段边界的绝对时间误差均值或中位数。 | 语音 | 采用相同时间单位的人工边界标注与预测边界。 | <a href="https://eprints.whiterose.ac.uk/id/eprint/210215/"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper"></a> |  |
| 词级动态时间规整（WDTW）↓ | 源语音与编辑语音中对应词片段之间，经过长度归一化的 DTW 距离。 | 语音 | 源语音与编辑语音；两者的转录及词级强制对齐结果。 | <a href="https://arxiv.org/abs/2604.16056"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> |  |
| 旋律准确率 ↑ | 参考音乐与编辑音乐中主导音高类别的逐帧一致程度。 | 音乐 | 参考旋律／音频；对齐的音高类别序列。 | <a href="https://arxiv.org/abs/2507.11096"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/billsioros/EditGen/tree/master/notebooks/evaluation"><img height="20" src="https://img.shields.io/badge/GitHub-EditGen-181717?logo=github&amp;logoColor=white" alt="EditGen"></a> |
| F0 Pearson 相关系数 ↑ | 参考人声与输出人声音高曲线的相关性。 | 音乐（人声） | 参考人声音频；使用同一模型提取并对齐的 F0 曲线。 | <a href="https://arxiv.org/abs/2603.24589"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Dream-High/RMVPE"><img height="20" src="https://img.shields.io/badge/GitHub-RMVPE-181717?logo=github&amp;logoColor=white" alt="Pitch extractor"></a><br>音高提取器 |
| 色度相似度／色度 DTW 相似度 ↑ | 音高类别分布的相似度，或经 DTW 对齐后的逐帧相似度。 | 音乐 | 源／参考音乐；使用一致方法提取的色度图。 | <a href="https://arxiv.org/abs/2512.14629"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Yashvishe13/MuseCPEval/blob/main/musecpeval/metrics/harmony_tonality.py"><img height="20" src="https://img.shields.io/badge/GitHub-MuseCPEval-181717?logo=github&amp;logoColor=white" alt="MuseCPEval"></a> |
| 节拍 F1 ↑ | 在 70 ms 容差内匹配节拍时间戳，综合精确率与召回率。 | 音乐 | 参考与输出的节拍时间戳。 | <a href="https://arxiv.org/abs/2512.14629"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Yashvishe13/MuseCPEval/blob/main/musecpeval/metrics/rhythm_meter.py"><img height="20" src="https://img.shields.io/badge/GitHub-MuseCPEval-181717?logo=github&amp;logoColor=white" alt="MuseCPEval"></a> |
| 力度变化相关性 ↑ | 参考与输出响度轨迹的逐帧 Pearson 相关系数。 | 音乐 | 参考力度变化／音频；对齐的响度轨迹。 | <a href="https://arxiv.org/abs/2507.11096"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/billsioros/EditGen/tree/master/notebooks/evaluation"><img height="20" src="https://img.shields.io/badge/GitHub-EditGen-181717?logo=github&amp;logoColor=white" alt="EditGen"></a> |
| 结构成对 F 值／ARI ↑ | 音乐段落划分的一致程度，其中 ARI 校正偶然一致的影响。 | 音乐 | 共享时间轴上的源／参考与输出段落划分。 | <a href="https://arxiv.org/abs/2512.14629"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Yashvishe13/MuseCPEval/blob/main/musecpeval/metrics/structural_form.py"><img height="20" src="https://img.shields.io/badge/GitHub-MuseCPEval-181717?logo=github&amp;logoColor=white" alt="MuseCPEval"></a> |
| 事件顺序分数（ESS）↑ | 描述的事件顺序与检测到的事件顺序之间，类似 Kendall 系数的排序一致度。 | 通用音频 | 目标事件顺序；分离后事件轨道的起始时间估计。 | <a href="https://aclanthology.org/2025.acl-long.1147/"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper"></a> |  |

#### 音频质量与自然度

| 指标 | 衡量内容 | 音频模态 | 参考信息／输入 | 论文／标准 | 代码／模型 |
| --- | --- | --- | --- | --- | --- |
| MOS / CMOS ↑ | 人工评定输出质量，或相对于另一段录音的比较质量。 | 语音；音乐；通用音频 | 听评人员与任务相关评分协议；CMOS 还需对比音频。 | <a href="https://www.itu.int/rec/T-REC-P.800/en"><img height="20" src="https://img.shields.io/badge/ITU-Standard-brightgreen" alt="Standard"></a> | <a href="https://github.com/microsoft/P.808"><img height="20" src="https://img.shields.io/badge/GitHub-P.808-181717?logo=github&amp;logoColor=white" alt="Speech listening tests"></a><br>语音听评 |
| MOSNet 预测 MOS ↑ | 面向语音转换开发的语音自然度自动预测分数。 | 语音 | 编辑后的语音。 | <a href="https://arxiv.org/abs/1904.08352"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/lochenchou/MOSNet"><img height="20" src="https://img.shields.io/badge/GitHub-MOSNet-181717?logo=github&amp;logoColor=white" alt="MOSNet"></a> |
| UTMOSv2 预测 MOS ↑ | 面向高质量合成语音开发的自然度 MOS 预测分数。 | 语音 | 编辑后的语音。 | <a href="https://arxiv.org/abs/2409.09305"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/sarulab-speech/UTMOSv2"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a><br><a href="https://huggingface.co/sarulab-speech/UTMOSv2"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="HF Model"></a> |
| SpeechJudge-GRM（成对评估） | 成对自然度评分与偏好，并生成对应解释。 | 语音 | 目标转录文本，以及对应同一文本的两段候选语音。 | <a href="https://arxiv.org/abs/2511.07931"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/AmphionTeam/SpeechJudge"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a><br><a href="https://huggingface.co/RMSnow/SpeechJudge-GRM"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="HF Model"></a> |
| DNSMOS P.835 ↑ | 预测语音信号、背景噪声和整体质量分数。 | 语音 | 编辑后的语音。 | <a href="https://arxiv.org/abs/2110.01763"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/microsoft/DNS-Challenge/tree/master/DNSMOS"><img height="20" src="https://img.shields.io/badge/GitHub-DNSMOS-181717?logo=github&amp;logoColor=white" alt="DNSMOS"></a> |
| NISQA ↑ | 预测整体语音质量及各类退化维度；NISQA-TTS 面向合成语音自然度。 | 语音 | 编辑后的语音；适用的 NISQA 权重。 | <a href="https://arxiv.org/abs/2104.09494"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/gabrielmittag/NISQA"><img height="20" src="https://img.shields.io/badge/GitHub-NISQA-181717?logo=github&amp;logoColor=white" alt="NISQA"></a> |
| PAM ↑ | 通过音频—语言模型与正、负质量提示的对比，评估无参考音频质量。 | 语音；音乐；通用音频 | 编辑后的音频；固定质量提示，以及 PAM 实现使用的 MS-CLAP 骨干模型。 | <a href="https://arxiv.org/abs/2402.00282"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/soham97/PAM"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a> |
| PESQ ↑ | 退化或修复语音相对于参考语音的感知质量。 | 语音 | 对应的干净目标语音；8 kHz 窄带或 16 kHz 宽带模式。 | <a href="https://www.itu.int/rec/T-REC-P.862/en"><img height="20" src="https://img.shields.io/badge/ITU-Standard-brightgreen" alt="Standard"></a> | <a href="https://github.com/ludlows/PESQ"><img height="20" src="https://img.shields.io/badge/GitHub-PESQ-181717?logo=github&amp;logoColor=white" alt="PESQ"></a> |
| STOI ↑ | 估计退化或增强语音的可懂度。 | 语音 | 时间对齐的干净目标语音。 | <a href="https://sps.ewi.tudelft.nl/pubs/Taal2010.pdf"><img height="20" src="https://img.shields.io/badge/Paper-Link-brightgreen" alt="Paper"></a> | <a href="https://github.com/mpariente/pystoi"><img height="20" src="https://img.shields.io/badge/GitHub-pystoi-181717?logo=github&amp;logoColor=white" alt="pystoi"></a> |
| SI-SDR ↑ | 补偿全局尺度差异后的目标信号重建保真度。 | 语音；音乐；通用音频 | 时间对齐的目标波形或独立目标音源。 | <a href="https://arxiv.org/abs/1811.02508"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Lightning-AI/torchmetrics/blob/master/src/torchmetrics/functional/audio/sdr.py"><img height="20" src="https://img.shields.io/badge/GitHub-TorchMetrics-181717?logo=github&amp;logoColor=white" alt="TorchMetrics"></a> |
| NOMAD 距离 ↓ | 在学习到的嵌入空间中衡量语音感知退化。 | 语音 | 干净参考语音；不要求语言内容一致。 | <a href="https://arxiv.org/abs/2309.16284"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/alessandroragano/nomad"><img height="20" src="https://img.shields.io/badge/GitHub-NOMAD-181717?logo=github&amp;logoColor=white" alt="NOMAD"></a> |
| SpeechBERTScore ↑ | 通过自监督语音特征的贪心匹配，近似衡量有参考语音质量。 | 语音 | 自然参考语音；固定编码器、层及精确率／召回率／F1 变体。 | <a href="https://arxiv.org/abs/2401.16812"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Takaaki-Saeki/DiscreteSpeechMetrics"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a> |
| Fréchet 音频距离（FAD）↓ | 输出与参考音频嵌入分布之间的距离。 | 音乐；通用音频 | 参考音频集合；相同的嵌入骨干模型与预处理。 | <a href="https://arxiv.org/abs/1812.08466"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/microsoft/fadtk"><img height="20" src="https://img.shields.io/badge/GitHub-FADtk-181717?logo=github&amp;logoColor=white" alt="FADtk"></a> |

#### 多维度评估器

用于多维度评估编辑结果与音频美学质量的可复用模型和工具集。

| 评估器 | 音频模态 | 评测维度 | 参考信息／输入 | 论文 | 代码／模型 |
| --- | --- | --- | --- | --- | --- |
| AuditEval (SSL / LLM) | 通用音频 | 质量、编辑相关性及对源音频的忠实度。 | 源音频与编辑音频；原始与目标描述。 | <a href="https://arxiv.org/abs/2508.11966"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/NKU-HLT/AuditEval"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a><br><a href="https://modelscope.cn/models/YuhangJia/AuditEval/summary"><img height="20" src="https://img.shields.io/badge/ModelScope-Models-624AFF" alt="ModelScope"></a> |
| MuseCPEval | 音乐 | 和声、节奏、结构与旋律保留；工具集中另含音色指标。 | 源音乐与编辑音乐；选定的待保留音乐属性。 | <a href="https://arxiv.org/abs/2512.14629"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/Yashvishe13/MuseCPEval"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a> |
| MMAE 评分准则评估器（Qwen3-Omni） | 语音；音乐；通用音频 | 指令遵循率（IFR）、一致性率（CR）和完全匹配率（EMR）。 | 源／输出音频、编辑指令，以及样本对应的 MMAE 评分准则。 | <a href="https://arxiv.org/abs/2606.07229"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/ddlBoJack/MMAE/tree/main/eval"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a> |
| Audiobox Aesthetics | 语音；音乐；通用音频 | 内容愉悦度（CE）、内容实用性（CU）、制作复杂度（PC）与制作质量（PQ）。 | 仅需编辑后的音频。 | <a href="https://arxiv.org/abs/2502.05139"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/facebookresearch/audiobox-aesthetics"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a><br><a href="https://huggingface.co/facebook/audiobox-aesthetics"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="HF Model"></a> |
| SongEval 评分模型 | 音乐（歌曲） | 整体连贯性、易记性、人声呼吸／分句自然度、结构清晰度和整体音乐性。 | 包含人声与伴奏的完整歌曲音频。 | <a href="https://arxiv.org/abs/2505.10793"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/ASLP-lab/SongEval"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a><br><a href="https://github.com/ASLP-lab/SongEval/tree/main/ckpt"><img height="20" src="https://img.shields.io/badge/GitHub-Weights-181717?logo=github&amp;logoColor=white" alt="Weights"></a> |
| MuseCritic | 音乐（歌曲） | 连贯性、音乐性、易记性、结构清晰度与人声自然度；输出分数和自然语言点评。 | 完整歌曲音频；公开的美学评分准则。 | <a href="https://arxiv.org/abs/2608.11755"><img height="20" src="https://img.shields.io/badge/arXiv-Paper-brightgreen" alt="arXiv"></a> | <a href="https://github.com/WuqnEl/MuseCritic"><img height="20" src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&amp;logoColor=white" alt="GitHub"></a><br><a href="https://huggingface.co/WuqnEl/MuseCritic"><img height="20" src="https://img.shields.io/badge/Hugging_Face-Model-FFD21E?logo=huggingface&amp;logoColor=black" alt="HF Model"></a> |

---

<a id="challenges-and-future-directions"></a>

## 🔮 挑战与未来方向

基于基础模型的音频编辑仍面临以下系统层面的挑战：

1. **复杂编辑。**  
   真实世界的音频交织着语义事件、说话人身份、声学属性、背景氛围、节奏、空间线索和混响。未来系统应支持精确的音源／事件定位、属性级修改，并在语音、音乐和通用音频中可靠地保留非目标内容。
2. **开放域场景下的鲁棒性。**  
   编辑模型应在噪声、混响、音源重叠、长音频上下文和模糊指令下保持可靠。更准确的指令理解与定位、长上下文建模、迭代精修和自我验证，是实现真实场景稳健编辑的重要方向。
3. **忠实且面向编辑任务的评测。**  
   现有评测常将生成质量与编辑质量混为一谈。未来基准应明确标注编辑目标、操作、保留区域和相关控制信号，以分别评估编辑成功程度与非目标内容的保留情况。
4. **安全、版权与滥用防范。**  
   现代编辑系统能够逼真地修改语音内容、说话人身份、情绪、环境声音和音乐。因此，实际部署需要结合来源追溯、水印、篡改音频检测和负责任的数据许可等互补机制。

---

<a id="citation"></a>

## 引用

如果本综述或仓库对您的研究有所帮助，欢迎引用我们的论文：

```bibtex
@article{pan2026audio,
  title={Audio Editing in the Era of Foundation Models: A Survey},
  author={Pan, Changhao and Fan, Yifei and Zhuo, Fan and Chen, Yifu and Guo, Wenxiang and Zhang, Yu and Li, Ruiqi and Zhu, Zhiyuan and Yang, Rui and Ji, Shengpeng and others},
  journal={arXiv preprint arXiv:2606.23139},
  year={2026}
}
```

<a id="contributing"></a>

## 参与贡献

本仓库将持续更新。如果有遗漏的音频编辑模型、数据集或评测基准，欢迎提交 [issue](https://github.com/MM-Speech/AudioEditSurvey/issues) 或 pull request。

---

<a id="license"></a>

## 📄 许可证

除下文另有说明外，本仓库的原创内容采用 [MIT 许可证](LICENSE)。

[综述论文](https://arxiv.org/abs/2606.23139)及转载或改编自论文的内容（包括 `assets/taxonomy_overview.png`、`assets/train-based.png` 和 `assets/train-free.png`）仍采用 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)。MIT 许可证不会改变这些材料的许可条款。

所链接的第三方论文、代码、模型、模型权重、数据集和工具，均遵循各自的许可证。
