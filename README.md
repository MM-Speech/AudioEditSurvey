<div align="center">

# 🎧 AudioEditSurvey

### Audio Editing in the Era of Foundation Models: A Survey

[![Survey](https://img.shields.io/badge/Survey-Audio%20Editing-blue)](#)
[![Paper](https://img.shields.io/badge/Paper-Coming%20Soon-lightgrey)](#)
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

</div>

---

# Quick Start

1. [Introduction](#introduction)  
2. [Scope](#scope)  
3. [Overall](#overall)  
   - [Organization of This Survey](#organization-of-this-survey)  
   - [Taxonomy of Audio Editing](#taxonomy-of-audio-editing)  
   - [Representative Audio Editing Methods](#representative-audio-editing-methods)  
4. [Foundation Models for Audio Editing](#foundation-models-for-audio-editing)  
5. [Training-based Audio Editing](#training-based-audio-editing)  
6. [Training-free Audio Editing](#training-free-audio-editing)  
7. [Resources](#resources)  
   - [Available Datasets](#available-datasets)  
   - [Data Tools](#data-tools)  
   - [Evaluation Protocols and Benchmarks](#evaluation-protocols-and-benchmarks)  
8. [Systemization Challenges and Future Directions](#systemization-challenges-and-future-directions)  
9. [Citation](#citation)

# 📰 What's New

- **2026.5.18:** The paper and full paper list will be updated soon.

---

## 📌 Introduction

This repository maintains the project page and paper list for **AudioEditSurvey: Audio Editing in the Era of Foundation Models**.

> **Abstract**  
> Audio editing aims to modify a given synthetic or real-world audio signal to meet users' specific needs. As a promising yet challenging direction in AIGC, it has attracted increasing attention in recent years. With the rapid progress of text-to-audio and text-to-speech generation, powerful audio generation models have become the primary foundation for modern audio editing systems. In this survey, we provide a comprehensive review of foundation-model-based audio editing. We first define the scope of audio editing from a unified perspective and present a detailed taxonomy of existing editing tasks. We then summarize the major foundation-model paradigms for audio editing, and review representative approaches from both training-based and training-free perspectives. In addition, we systematically discuss related resources, including datasets, data construction tools, and evaluation protocols. Finally, we identify open challenges in this field and outline promising directions for future research.

---

## 🎯 Scope

In this survey, we focus on works that make direct contributions to audio editing in the era of foundation models. To ensure a precise and focused discussion, we adopt two main inclusion criteria: (1) the task should center on audio editing, which we define as modifying the acoustic attributes, instances, or content of an existing audio recording, without transformations so substantial that they amount to generating an entirely new audio sample; (2) the method should rely on mainstream audio foundation model paradigms.
Accordingly, we do not cover works primarily focused on audio generation, nor do we provide an extensive discussion of signal-processing-based audio editing methods. In addition, to maintain a focused scope, spatial audio\footnote{Spatial audio refers to multi-channel audio formats, such as binaural stereo and first-order Ambisonics (FOA).} and related editing techniques are beyond the main scope of this survey.

---

## 🧭 Overall

### 🗂️ Taxonomy Overview

![Taxonomy of Audio Editing Tasks](taxonomy_overview.png)

*Figure 1: Taxonomy of audio editing tasks.*



### 🧩 Taxonomy Details




| Category | Definition | Representative Editing Goals |
|---|---|---|
| Acoustic Editing | Modifies low-level perceptual attributes while preserving the overall structure and source characteristics of the original audio. | restoration, reverberation editing, loudness/mixing control, equalization, spectral texture editing |
| Semantic Editing | Modifies high-level interpretable information conveyed by audio while maintaining task-irrelevant properties. | linguistic editing, expressive editing, stylistic editing |
| Instance Editing | Manipulates identifiable audio entities while preserving the remaining scene and source relationships. | replacement, deletion/extraction, insertion, overlay/remixing |

### 📚 Representative Audio Editing Methods

| Model | Category | Paper URL |
|---|---|---|
| FluentSpeech | Training-based / Diffusion | https://arxiv.org/abs/2305.13612 |
| VoiceCraft | Training-based / Codec | https://arxiv.org/abs/2403.16973 |
| uSee | Training-based / Diffusion | https://arxiv.org/abs/2310.00900 |
| SpeechX | Training-based / Codec | https://arxiv.org/abs/2308.06873 |
| CosyEdit | Training-based / Codec | https://arxiv.org/abs/2601.05329 |
| AUDIT | Training-based / Diffusion | https://arxiv.org/abs/2304.00830 |
| SAO-Instruct | Training-based / Diffusion | https://arxiv.org/abs/2510.22795 |
| Non-Rigid Prompt Edit | Training-based / Diffusion | https://arxiv.org/abs/2310.12858 |
| InstructME | Training-based / Diffusion | https://arxiv.org/abs/2308.14360 |
| Instruct-MusicGen | Training-based / Codec | https://arxiv.org/abs/2405.18386 |
| AST | Training-free / Diffusion | https://arxiv.org/abs/2604.16056 |
| EdiTTS | Training-free / Diffusion | https://arxiv.org/abs/2110.02584 |
| DDPM Inversion | Training-free / Diffusion | https://arxiv.org/abs/2402.10009 |
| AudioEditor | Training-free / Diffusion | https://arxiv.org/abs/2409.12466 |
| PPAE | Training-free / Diffusion | https://arxiv.org/abs/2406.04350 |
| AudioMorphix | Training-free / Diffusion | https://arxiv.org/abs/2505.16076 |
| MelodyFlow | Training-free / Flow | https://arxiv.org/abs/2407.03648 |
| MEDIC | Training-free / Diffusion | https://arxiv.org/abs/2407.13220 |
| MusicMagus | Training-free / Diffusion | https://arxiv.org/abs/2402.06178 |
| MusRec | Training-free / Flow | https://arxiv.org/abs/2511.04376 |

---

## 🏗️ Foundation Models for Audio Editing

### 1. Early Neural Editing Models

Before the foundation-model era, early neural audio editing methods mainly explored task-specific generative models for local reconstruction and attribute control. 

### 2. Token-based Codec Language Models

Token-based codec language models cast audio editing as conditional generation over discrete audio tokens. After continuous audio is converted into compact discrete token sequences, target regions are edited through autoregressive continuation, infilling, or selective regeneration conditioned on context, prompts, or task controls.

### 3. Diffusion and Flow-Matching Models

Diffusion and flow-matching models formulate audio editing as conditional transformation in continuous acoustic spaces, such as mel-spectrograms or audio latents. Instead of infilling discrete tokens, they modify audio through conditional denoising, latent inversion, or continuous flow transformation, making them suitable for high-fidelity reconstruction, region-level refinement, and fine-grained acoustic control in complex scenarios.

### 4. Audio Editing Interfaces

Instruction-conditioned and multimodal interfaces for audio editing provide high-level control for foundation-model-based audio editing. They allow users to specify editing intents through natural language instructions, task prompts, reference audio, temporal regions, or visual cues, which are shifted into target spans, task embeddings, event locations, speaker references, or preservation constraints.

---

## 🧪 Training-based Audio Editing

Training-based approaches refer to audio editing methods that learn editing behaviors from supervised pairs, pseudo-pairs, or instruction-based triplets before inference. These methods explicitly optimize editing objectives, condition following, and preservation constraints, enabling stable and controllable editing. We group existing works into three categories based on their supervision and conditioning mechanisms, and discuss their core methods and functional scopes.

<p align="center">
  <img src="train-based.png" alt="Overview of training-based audio editing methods" width="900">
</p>

<p align="center">
  <em>Figure 2: Overview of training-based audio editing methods.</em>
</p>


| Paradigm | Description | Representative Scope |
|---|---|---|
| Task-specific Training | Optimizes models for predefined editing functions or domains. | text-based speech editing, prosody correction, source separation, music stem separation |
| Reference- and Attribute-based Training | Specifies the editing direction through reference audio, style examples, or attribute labels. | voice conversion, timbre transfer, emotion editing, mixing style transfer |
| Instruction-conditioned Training | Learns from instruction-input-output triplets to follow natural-language editing requests. | addition, deletion, replacement, inpainting, super-resolution, music remixing, expressive refinement |


---

## 🪄 Training-free Audio Editing

Training-free approaches adapt pretrained audio generative models to editing without parameter updates. They operate by manipulating inference-time mechanisms, such as inversion, attention control, prompt or guidance adjustment, and mask-based constraints. We group existing methods into three common categories, which are often combined to improve localization, preservation, and controllability. Since token-based autoregressive models are less naturally suited to training-free editing, this section mainly focuses on non-autoregressive paradigms, especially diffusion-based foundation models.

<p align="center">
  <img src="train-free.png" alt="Overview of training-free audio editing methods" width="900">
</p>

<p align="center">
  <em>Figure 3: Overview of training-free audio editing methods.</em>
</p>



| Paradigm | Description | Representative Scope |
|---|---|---|
| Inversion-Based Editing | Maps source audio back into the latent, noise, or trajectory space of a pretrained generative model, then edits it by modifying conditions or sampling trajectories. | DDPM/DDIM inversion, latent inversion, flow-based inversion, speech or music reconstruction and editing |
| Attention-Controlled Editing | Guides pretrained generative models by modifying or reusing internal attention patterns without parameter updates. | cross-attention event localization, self-attention preservation, prompt-level manipulation |
| Mask- and Region-Guided Editing | Specifies where to edit and where to preserve the source audio in waveform, spectrogram, latent, or source-component spaces. | localized editing, inpainting, restoration, source-level manipulation |
| Token-Level Editing with Codec Models | Manipulates discrete audio tokens through masking, infilling, continuation, or selective regeneration at inference time. | speech infilling, localized resynthesis, codec-token editing |



---

## 📦 Resources



### 🛠️ Data Tools

<table>
  <thead>
    <tr>
      <th>Category</th>
      <th>Method</th>
      <th>URL</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="10"><b>Temporal Localization Tools</b></td>
      <td>Praat</td>
      <td><a href="https://www.fon.hum.uva.nl/praat/">Link</a></td>
    </tr>
    <tr>
      <td>Montreal Forced Aligner (MFA)</td>
      <td><a href="https://arxiv.org/abs/1705.09525">Link</a></td>
    </tr>
    <tr>
      <td>WhisperX</td>
      <td><a href="https://arxiv.org/abs/2303.00747">Link</a></td>
    </tr>
    <tr>
      <td>pyannote.audio</td>
      <td><a href="https://arxiv.org/abs/1911.01255">Link</a></td>
    </tr>
    <tr>
      <td>PANNs</td>
      <td><a href="https://arxiv.org/abs/1912.10211">Link</a></td>
    </tr>
    <tr>
      <td>Parselmouth</td>
      <td><a href="https://doi.org/10.1016/j.wocn.2018.07.001">Link</a></td>
    </tr>
    <tr>
      <td>RMVPE</td>
      <td><a href="https://arxiv.org/abs/2306.15412">Link</a></td>
    </tr>
    <tr>
      <td>CREPE</td>
      <td><a href="https://arxiv.org/abs/1802.06182">Link</a></td>
    </tr>
    <tr>
      <td>ROSYOT</td>
      <td><a href="https://aclanthology.org/2024.acl-long.526/">Link</a></td>
    </tr>
    <tr>
      <td>MusicYOLO</td>
      <td><a href="https://ieeexplore.ieee.org/abstract/document/9746684">Link</a></td>
    </tr>
    <tr>
      <td rowspan="6"><b>Semantic Annotation Tools</b></td>
      <td>FunASR</td>
      <td><a href="https://arxiv.org/abs/2305.11013">Link</a></td>
    </tr>
    <tr>
      <td>Whisper</td>
      <td><a href="https://arxiv.org/abs/2212.04356">Link</a></td>
    </tr>
    <tr>
      <td>HTS-AT</td>
      <td><a href="https://arxiv.org/abs/2202.00874">Link</a></td>
    </tr>
    <tr>
      <td>SELD-TCN</td>
      <td><a href="https://ieeexplore.ieee.org/abstract/document/9287716">Link</a></td>
    </tr>
    <tr>
      <td>emotion2vec</td>
      <td><a href="https://arxiv.org/abs/2312.15185">Link</a></td>
    </tr>
    <tr>
      <td>Qwen3-Omni</td>
      <td><a href="https://arxiv.org/abs/2509.17765">Link</a></td>
    </tr>
    <tr>
      <td rowspan="9"><b>Pair Construction Tools</b></td>
      <td>MaskGCT</td>
      <td><a href="https://arxiv.org/abs/2409.00750">Link</a></td>
    </tr>
    <tr>
      <td>StyleTTS</td>
      <td><a href="https://ieeexplore.ieee.org/abstract/document/10852161">Link</a></td>
    </tr>
    <tr>
      <td>AutoVC</td>
      <td><a href="https://arxiv.org/abs/1905.05879">Link</a></td>
    </tr>
    <tr>
      <td>YourTTS</td>
      <td><a href="https://arxiv.org/abs/2112.02418">Link</a></td>
    </tr>
    <tr>
      <td>Open-Unmix</td>
      <td><a href="https://joss.theoj.org/papers/10.21105/joss.01667">Link</a></td>
    </tr>
    <tr>
      <td>Spleeter</td>
      <td><a href="https://joss.theoj.org/papers/10.21105/joss.02154">Link</a></td>
    </tr>
    <tr>
      <td>Demucs</td>
      <td><a href="https://arxiv.org/abs/2111.03600">Link</a></td>
    </tr>
    <tr>
      <td>AudioSep</td>
      <td><a href="https://arxiv.org/abs/2308.05037">Link</a></td>
    </tr>
    <tr>
      <td>SAM-Audio</td>
      <td><a href="https://arxiv.org/abs/2512.18099">Link</a></td>
    </tr>
  </tbody>
</table>

### 📏 Evaluation Protocols and Benchmarks

<table>
  <thead>
    <tr>
      <th>Category</th>
      <th>Method</th>
      <th>URL</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="4"><b>Edit Success and Instruction Adherence</b></td>
      <td>WER / CER</td>
      <td><a href="https://dl.acm.org/doi/abs/10.1145/3565472.3595606">Link</a></td>
    </tr>
    <tr>
      <td>emotion2vec</td>
      <td><a href="https://arxiv.org/abs/2312.15185">Link</a></td>
    </tr>
    <tr>
      <td>CLAP</td>
      <td><a href="https://arxiv.org/abs/2206.04769">Link</a></td>
    </tr>
    <tr>
      <td>Pitch and Rhythm Accuracy</td>
      <td><a href="https://proceedings.neurips.cc/paper_files/paper/2023/hash/94b472a1842cd7c56dcb125fb2765fbd-Abstract-Conference.html">Link</a></td>
    </tr>
    <tr>
      <td rowspan="6"><b>Preservation and Locality</b></td>
      <td>Speaker Similarity / X-vector</td>
      <td><a href="https://ieeexplore.ieee.org/document/8461375">Link</a></td>
    </tr>
    <tr>
      <td>Waveform / Spectrogram Similarity</td>
      <td><a href="https://ieeexplore.ieee.org/abstract/document/9103053">Link</a></td>
    </tr>
    <tr>
      <td>NOMAD</td>
      <td><a href="https://ieeexplore.ieee.org/abstract/document/10448028">Link</a></td>
    </tr>
    <tr>
      <td>PESQ</td>
      <td><a href="https://ieeexplore.ieee.org/document/941023">Link</a></td>
    </tr>
    <tr>
      <td>STOI</td>
      <td><a href="https://ieeexplore.ieee.org/document/5495701">Link</a></td>
    </tr>
    <tr>
      <td>SI-SDR</td>
      <td><a href="https://arxiv.org/abs/1811.02508">Link</a></td>
    </tr>
    <tr>
      <td rowspan="5"><b>Temporal and Structural Consistency</b></td>
      <td>Boundary Error</td>
      <td><a href="https://www.sciencedirect.com/science/article/pii/S0167639324000141">Link</a></td>
    </tr>
    <tr>
      <td>WDTW</td>
      <td><a href="https://arxiv.org/abs/2604.16056">Link</a></td>
    </tr>
    <tr>
      <td>Melody Accuracy</td>
      <td><a href="https://arxiv.org/abs/2311.07069">Link</a></td>
    </tr>
    <tr>
      <td>Rhythm F1</td>
      <td><a href="https://arxiv.org/abs/2407.15060">Link</a></td>
    </tr>
    <tr>
      <td>Dynamics Correlation</td>
      <td><a href="https://arxiv.org/abs/2507.11096">Link</a></td>
    </tr>
    <tr>
      <td rowspan="10"><b>Audio Quality and Naturalness</b></td>
      <td>MOS / CMOS</td>
      <td><a href="https://www.itu.int/rec/T-REC-P.800.1">Link</a></td>
    </tr>
    <tr>
      <td>MOSNet</td>
      <td><a href="https://arxiv.org/abs/1904.08352">Link</a></td>
    </tr>
    <tr>
      <td>DNSMOS</td>
      <td><a href="https://arxiv.org/abs/2010.15258">Link</a></td>
    </tr>
    <tr>
      <td>NISQA</td>
      <td><a href="https://arxiv.org/abs/2104.09494">Link</a></td>
    </tr>
    <tr>
      <td>FAD</td>
      <td><a href="https://arxiv.org/abs/1812.08466">Link</a></td>
    </tr>
    <tr>
      <td>AuditScore / AuditEval</td>
      <td><a href="https://arxiv.org/abs/2508.11966">Link</a></td>
    </tr>
    <tr>
      <td>TTA-Bench</td>
      <td><a href="https://ojs.aaai.org/index.php/AAAI/article/view/40639">Link</a></td>
    </tr>
    <tr>
      <td>AudioEval</td>
      <td><a href="https://arxiv.org/abs/2510.14570">Link</a></td>
    </tr>
    <tr>
      <td>T2A-Feedback</td>
      <td><a href="https://aclanthology.org/2025.acl-long.1147/">Link</a></td>
    </tr>
    <tr>
      <td>MuseCPBench</td>
      <td><a href="https://arxiv.org/abs/2512.14629">Link</a></td>
    </tr>
  </tbody>
</table>

---

## 🔮 Systemization Challenges and Future Directions

Foundation-model-based audio editing still faces several system-level challenges:

1. **Complex editing.**  
   Real-world recordings entangle semantic events, speaker identity, acoustic texture, background ambience, rhythm, spatial cues, and reverberation. Future systems should support object localization, attribute-level modification, and non-target preservation across speech, music, and general audio.

2. **Robustness under open-domain conditions.**  
   Editing models must remain stable when audio contains noise, reverberation, overlapping sources, long-range dependencies, or ambiguous user intents. Improving instruction grounding, long-context modeling, iterative refinement, self-verification, retrieval-augmented editing, and multi-stage correction are promising directions.

3. **Faithful and specific evaluation.**  
   Current protocols often conflate generation quality with editing quality. Reliable benchmarks should provide explicit annotations of target regions, edit operations, preservation regions, and control signals, enabling separate measurement of edit success and non-target preservation.

4. **Safety, copyright, and misuse prevention.**  
   Audio editing systems can realistically alter speech content, speaker identity, emotion, background sounds, and music. Watermarking, provenance tracking, edited-audio detection, and responsible data licensing are important for practical deployment.

---

## 📝 Citation

If you find this survey useful, please consider citing our paper.



---



## 📄 License

This repository is released for academic and research purposes. The license will be updated soon.
