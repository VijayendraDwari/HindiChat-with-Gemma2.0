# HindiChat with Gemma 2.0 🇮🇳

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Gemma](https://img.shields.io/badge/Gemma-2.0--9B-red)
![Unsloth](https://img.shields.io/badge/Unsloth-Optimized-green)
![License](https://img.shields.io/badge/license-MIT-green.svg)

A state-of-the-art Hindi language chatbot powered by Gemma 2.0, optimized with Unsloth, and fine-tuned on high-quality Hindi conversations.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Model Architecture](#model-architecture)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [Training Details](#training-details)
- [Performance Metrics](#performance-metrics)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)

## Overview

HindiChat leverages Google's Gemma 2.0 model (9B parameters) with Unsloth optimizations to create a high-performance Hindi language conversational AI. The model is fine-tuned using the FreedomIntelligence/alpaca-gpt4-hindi dataset and implements efficient training techniques including LoRA and Flash Attention 2.

## Features

- 🚀 **Optimized Performance**: Utilizes Unsloth for enhanced efficiency
- 💡 **Advanced Fine-tuning**: LoRA-based parameter-efficient training
- ⚡ **Flash Attention 2**: Improved memory usage and training speed
- 🎯 **Specialized Prompting**: Custom Hindi Alpaca prompt template
- 📚 **High-Quality Dataset**: Fine-tuned on GPT-4 generated Hindi conversations
- 🔧 **4-bit Quantization**: Memory-efficient inference
- 📈 **RoPE Scaling**: Enhanced position encoding

## Model Architecture
#### 

The base model, unsloth/gemma-2-9b, supports RoPE scaling, 4-bit quantization for memory efficiency, and fine-tuning with LoRA (Low-Rank Adaptation).
Flash Attention 2 is utilized to enable softcapping and improve efficiency during training.

### Base Model Configuration
```python
Model: unsloth/gemma-2-9b
Parameters: 9 billion
Quantization: 4-bit
Attention: Flash Attention 2
Position Encoding: RoPE with scaling
```
Methodology and Dataset Overview

Methodology
This project uses the Unsloth Gemma-2-9B model to fine-tune and evaluate a Natural Language Processing (NLP) model for Hindi language tasks. The methodology involves:


Prompt Design:

A custom Hindi Alpaca Prompt Template is designed to format instructions, inputs, and expected outputs in a conversational structure.

### निर्देश:
{instruction}

### इनपुट:
{input}

### उत्तर:
{response}


#### Fine-Tuning:

The LoRA method is used for parameter-efficient fine-tuning by modifying key transformer layers (e.g., q_proj, k_proj, v_proj).
Training is conducted using SFTTrainer from the trl library, with configurations such as mixed precision (bfloat16), small batch sizes, and linear learning rate schedules.
Inference and Evaluation:

The fine-tuned model is tested on general knowledge and domain-specific questions in Hindi to ensure its understanding and response quality.
The inference process uses preformatted Hindi Alpaca prompts, and the outputs are decoded for review.
Model Deployment:

The final model and tokenizer are saved to Google Drive for future reuse and deployment.

#### Dataset
The dataset used for fine-tuning is FreedomIntelligence/alpaca-gpt4-hindi, a high-quality Hindi dataset derived from GPT-4 outputs. It contains structured conversations designed for instruction-tuning in the Hindi language.

Structure:
Each data point includes:

#### Instruction: The task description.
Input: Context or additional information (optional).
Response: The expected output from the model.
Preprocessing:

The dataset is mapped to the custom Hindi Alpaca prompt format.
End-of-sequence tokens (EOS) are appended to ensure proper text generation during training and inference.
This combination of cutting-edge models, efficient fine-tuning techniques, and a well-structured dataset ensures a robust pipeline for high-quality Hindi language generation and understanding.




