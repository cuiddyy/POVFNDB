# POVFNDB: Perception, Understanding and Reasoning: A Multimodal Benchmark for Video Fake News Detection

## 📋 Overview

POVFNDB is a comprehensive benchmark designed to evaluate Multimodal Large Language Models (MLLMs) on Video Fake News Detection (VFND) through a process-oriented approach. The benchmark systematically assesses models across three core capabilities: **Perception**, **Understanding**, and **Reasoning**.

---

## 🎯 Task Categories

### 1️⃣ Perception Tasks

Perception tasks evaluate MLLMs' ability to identify and extract crucial visual and textual elements from video news content.

#### **Key Elements Perception (KEP)**
- **Description**: Identify all elements in original shooting footage (OSF) that are crucial for VFND, including on-site footage, interview segments, and other primary source information about events.
- **Format**: Open-Ended with format constraints
- **Target**: Original Shooting Footage (OSF)
- **Metric**: Average Elements Hit Rate (Avg.EHR)

#### **Distinguish Creator-added Content and Original Shooting Footage (DCS)**
- **Description**: Recognize and differentiate between creator-added content (CAC) and original shooting footage. CAC is more susceptible to manipulation and carries stronger authorial intent, while OSF provides relatively unaltered information.
- **Format**: Open-Ended with format constraints
- **Target**: Creator-Added Content (CAC) & Original Shooting Footage (OSF)
- **Metric**: ROUGE-L

#### **Creator-added Text Color Perception (CCP)**
- **Description**: Perceive the font color of text embedded in videos. Text color reflects the creator's professional background and influences viewer comprehension.
- **Format**: Single Selection
- **Target**: Creator-Added Content (CAC)
- **Metric**: Accuracy

#### **Creator-added Text 2D-position Perception (CPP)**
- **Description**: Identify the spatial location of text within video frames. Text position reflects the creation style of news content.
- **Format**: Single Selection
- **Target**: Creator-Added Content (CAC)
- **Metric**: Accuracy

#### **Key Elements Temporal Grounding (KEG)**
- **Description**: Identify temporal ranges of key elements to enable precise visual information extraction and verification, thereby enhancing video understanding accuracy.
- **Format**: Open-Ended with format constraints
- **Target**: Original Shooting Footage (OSF)
- **Metric**: Intersection over Union (IoU)

#### **Shooting Angles Counting (SAC)**
- **Description**: Identify angle transitions and count the number of distinct camera viewpoints. More camera angles enable multi-perspective recording of news events, particularly in accident scene footage.
- **Format**: Open-Ended with format constraints
- **Target**: Original Shooting Footage (OSF)
- **Metric**: Average Absolute Distance (Avg.AD)

#### **Human Identity Recognition (HIR)**
- **Description**: Retrieve and identify all human identities that appear in the video.
- **Format**: Multi Selection
- **Target**: Original Shooting Footage (OSF)
- **Metric**: Accuracy

---

### 2️⃣ Understanding Tasks

Understanding tasks assess MLLMs' capability to comprehend global video semantics and extract thematic information.

#### **News Video Type Understanding (NTU)**
- **Description**: Determine the type of news video. Different news types rely on distinct evidence for verification, making type determination crucial for applying type-specific detection strategies.
- **Format**: Open-Ended
- **Target**: Creator-Added Content (CAC) & Original Shooting Footage (OSF)
- **Metric**: Accuracy

#### **News Video Theme Understanding (NEU)**
- **Description**: Obtain global comprehension of video news and extract thematic information (What, When, Where, Who, How, etc.) to guide focus on elements relevant to key content.
- **Format**: Single Selection
- **Target**: Creator-Added Content (CAC) & Original Shooting Footage (OSF)
- **Metric**: Average of Factual Consistency (FC), Theme Relevance (TR), and Completeness (CO)

---

### 3️⃣ Reasoning Tasks

Reasoning tasks evaluate MLLMs' ability to synthesize multi-modal information and make final veracity judgments.

#### **Final Detection Reasoning (FDR)**
- **Description**: Synthesize multi-modal entities extracted through perception and understanding capabilities, incorporate external general knowledge, and apply logical rationales to determine video veracity.
- **Format**: Open-Ended
- **Evaluation Dimensions**:
  - **Entities Extraction**: Average Entities Hit Rate (Avg.ENHR)
  - **External Knowledge**: Average Knowledge Hit Rate (Avg.KHR)
  - **Rationale Quality**: Average Rationale Hit Rate (Avg.RHR)
  - **Final Judgment**: Accuracy (Real/Fake classification)

---

## 📊 Task Overview Table

| **Task Type** | **Task** | **Format** | **Target** | **Metrics** |
|---------------|----------|------------|------------|-------------|
| **Perception** | Key Elements Perception (KEP) | Open-Ended with format | OSF | Avg.EHR |
| | Distinguish CAC and OSF (DCS) | Open-Ended with format | CAC & OSF | ROUGE-L |
| | Creator-added Text Color (CCP) | Single Selection | CAC | Accuracy |
| | Creator-added Text Position (CPP) | Single Selection | CAC | Accuracy |
| | Key Elements Grounding (KEG) | Open-Ended with format | OSF | IoU |
| | Shooting Angles Counting (SAC) | Open-Ended with format | OSF | Avg.AD |
| | Human Identity Recognition (HIR) | Multi Selection | OSF | Accuracy |
| **Understanding** | News Video Type (NTU) | Open-Ended | CAC & OSF | Accuracy |
| | News Video Theme (NEU) | Single Selection | CAC & OSF | Avg.FC/TR/CO |
| **Reasoning** | Final Detection Reasoning (FDR) | Open-Ended | CAC & OSF | Avg.ENHR |
| | | | External Knowledge | Avg.KHR |
| | | | Rationale | Avg.RHR |
| | | | Real/Fake | Accuracy |

---

## 🔑 Key Concepts

### Abbreviations
- **CAC**: Creator-Added Content
- **OSF**: Original Shooting Footage
- **Ext.Know.**: External Knowledge
- **VFND**: Video Fake News Detection
- **MLLMs**: Multimodal Large Language Models

### Metrics Explained
- **Avg.EHR**: Average Elements Hit Rate
- **Avg.AD**: Average Absolute Distance
- **Avg.ENHR**: Average Entities Hit Rate
- **Avg.RHR**: Average Rationale Hit Rate
- **Avg.KHR**: Average Knowledge Hit Rate
- **FC**: Factual Consistency
- **TR**: Theme Relevance
- **CO**: Completeness
- **IoU**: Intersection over Union

---

## 📖 Citation

If you find POVFNDB useful for your research, please consider citing our work:

```bibtex
@article{povfndb2024,
  title={POVFNDB: A Process-Oriented Video Fake News Detection Benchmark},
  author={Your Name},
  journal={arXiv preprint arXiv:XXXX.XXXXX},
  year={2024}
}
