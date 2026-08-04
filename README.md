# 🩺 DineTune-AI

### Fine-Tuned Medical Question-Answering Assistant

DineTune-AI is a hands-on **Large Language Model fine-tuning project** focused on adapting a pretrained language model to the medical question-answering domain.

The project uses **Qwen2.5-1.5B-Instruct** and **QLoRA (Quantized Low-Rank Adaptation)** to perform memory-efficient domain-specific fine-tuning on a medical question-answering dataset.

The complete training workflow, configurations, training logs, and final metrics are documented in the included Jupyter Notebook.

> ⚠️ **Medical Disclaimer:** This project is intended for educational and research purposes only. It should not be used for medical diagnosis, treatment, or professional medical decision-making.

---

## 📌 Project Overview

Large Language Models are trained on broad datasets and may not perform optimally for specialized domains.

The goal of DineTune-AI was to explore how a pretrained instruction-following model can be adapted to a specific domain using **Parameter-Efficient Fine-Tuning (PEFT)**.

For this project, a medical question-answering dataset was prepared and used to fine-tune **Qwen2.5-1.5B-Instruct** using **QLoRA**.

### Project Highlights

| Area | Implementation |
|---|---|
| Domain | 🩺 Medical Question Answering |
| Base Model | Qwen2.5-1.5B-Instruct |
| Fine-Tuning | QLoRA |
| PEFT Method | LoRA |
| Quantization | 4-bit |
| Training Framework | Hugging Face Transformers |
| Trainer | TRL SFTTrainer |
| GPU Environment | NVIDIA Tesla T4 |
| Training Platform | Google Colab |
| Training Status | ✅ Completed |

---

## 🎯 Objectives

The main objectives of this project were to gain practical experience with:

- Large Language Models (LLMs)
- Domain-specific model adaptation
- Supervised Fine-Tuning (SFT)
- Parameter-Efficient Fine-Tuning (PEFT)
- LoRA and QLoRA
- 4-bit model quantization
- Medical dataset preprocessing
- Hugging Face Transformers
- GPU-based model training
- Training monitoring and evaluation

---

## 🧠 Model

### Base Model

**Qwen/Qwen2.5-1.5B-Instruct**

### Fine-Tuning Technique

**QLoRA — Quantized Low-Rank Adaptation**

QLoRA makes fine-tuning more memory-efficient by combining:

1. 4-bit quantization of the pretrained model
2. Frozen base model parameters
3. Trainable LoRA adapter parameters

Instead of updating the entire pretrained model, the training process focuses on a much smaller set of adapter parameters.

---

## 📊 Dataset

The project uses a structured medical question-answering dataset.

Each training example contains:

| Field | Description |
|---|---|
| `instruction` | Task or instruction given to the model |
| `input` | Medical question or context |
| `output` | Expected medical answer |

### Dataset Pipeline

```text
Raw Medical Data
       ↓
Data Inspection
       ↓
Cleaning & Preprocessing
       ↓
Training Format
       ↓
QLoRA Fine-Tuning