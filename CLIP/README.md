# CLIP: Zero-Shot Image Classification on CIFAR-100

This repository contains a professional implementation of OpenAI's **CLIP (Contrastive Language-Image Pre-training)** for zero-shot image classification. By aligning visual and textual representations in a shared latent space, the model classifies images from the **CIFAR-100 dataset** based on natural language prompts without task-specific training.



## 📌 Project Overview
Traditional classifiers are limited to fixed labels. This project leverages CLIP to perform **"zero-shot" prediction** by measuring the cosine similarity between an image's visual features and 100 different text descriptions.

## 🚀 Key Features
* **Architecture:** Utilizes the **ViT-B/32 Vision Transformer** as the image encoder and a 63M-parameter Transformer for text encoding.
* **Zero-Shot Learning:** Performs classification by comparing images against natural language prompts (e.g., "a photo of a {label}").
* **High Confidence:** Achieved a **96.34% confidence score** for identifying a "lion" among 100 potential classes.
* **Semantic Retrieval:** Demonstrates the model's ability to distinguish between closely related categories like "lion," "tiger," and "leopard".

## 🛠️ Technical Stack
* **Frameworks:** PyTorch, Torchvision
* **Library:** OpenAI CLIP
* **Dataset:** CIFAR-100
* **Tokenization:** Byte Pair Encoding (BPE) with a 49,152 vocabulary size

## 📂 Implementation Details
1. **Model Loading:** The ViT-B/32 model is loaded into the available device (CUDA or CPU).
2. **Input Preparation:** Images are preprocessed and text prompts are tokenized for all 100 CIFAR-100 classes.
3. **Feature Extraction:** Normalized embeddings are generated for both image and text inputs.
4. **Similarity Calculation:** The dot product of normalized features is calculated, followed by a softmax function to determine class probabilities.

## 📊 Results Example
For a sample image of a **lion**, the model provided the following top predictions:

| Class | Confidence |
| :--- | :--- |
| **lion** | **96.339965%** |
| tiger | 1.044002% |
| camel | 0.284237% |
| lawn_mower | 0.262529% |
| leopard | 0.258663% |