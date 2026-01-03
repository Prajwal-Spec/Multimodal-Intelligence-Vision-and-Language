# Vision Transformer (ViT) for Image Classification

This project demonstrates the implementation and use of a **Vision Transformer (ViT)** for state-of-the-art image classification. By treating image patches as tokens, this model applies the power of Transformer architectures—originally designed for NLP—directly to visual data.



## 📌 Project Overview
Unlike traditional Convolutional Neural Networks (CNNs), the Vision Transformer (ViT) breaks an image into fixed-size patches, embeds them, and uses self-attention to model global relationships across the entire image. This project uses a pre-trained model from Google to classify real-world images into one of 1,000 ImageNet categories.

## 🚀 Key Features
* **Architecture**: Based on the `vit-base-patch16-224` model, which features a 12-layer Transformer encoder and a 768-wide hidden state.
* **Patch-Based Processing**: Images are divided into 16x16 pixel patches before being processed by the Transformer.
* **Global Attention**: Uses self-attention mechanisms (12 heads) to capture long-range dependencies across the image patches.
* **Accurate Classification**: Successfully identified complex visual subjects, such as an "Egyptian cat," from the COCO dataset.

## 🛠️ Technical Stack
* **Framework**: Hugging Face `transformers`
* **Core Libraries**: PyTorch, PIL (Pillow), Requests
* **Model**: `google/vit-base-patch16-224`
* **Dataset Reference**: ImageNet-1k

## 📂 Implementation Details
1. **Feature Extraction**: Uses `ViTFeatureExtractor` to resize, normalize, and convert images into the required tensor format.
2. **Model Loading**: Loads a pre-trained `ViTForImageClassification` model with its classification head intact.
3. **Inference**: Pass the image tensors through the model to obtain logits for 1,000 potential classes.
4. **Prediction**: Applies an `argmax` function to the logits to determine the highest-probability class index.

## 📊 Results Example
When tested with an image from the COCO dataset, the model provided a precise classification:

* **Predicted Class Index**: 285
* **Label**: **Egyptian cat**