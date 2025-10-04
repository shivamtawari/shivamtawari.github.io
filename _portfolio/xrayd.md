---
title: "XRayd - An AI-Powered Medical Imaging Platform"
excerpt: "A web application that leverages multiple deep learning models to predict up to 21 lung diseases from chest X-ray and CT scan images, with a focus on AI explainability."
collection: portfolio
repo: https://github.com/shivamtawari/XRayd-AI
---

As part of the **AI for Healthcare Hackathon 2021**, our team developed XRayd, an AI-powered platform to assist in the analysis of medical chest scans. The project was awarded **Second Runner Up** for its comprehensive approach, technical depth, and focus on model interpretability.

![XRayd UI](/images/xrayd_ui.png)
*Xrayd Platform UI*

## The Challenge

Diagnosing lung diseases from medical scans requires specialized expertise and can be time-consuming. We aimed to create a tool that could serve as a "second opinion" for medical professionals, capable of identifying multiple potential diseases from a single scan and providing insights into its reasoning.

## The End Result: An Interactive Prediction Platform

The outcome is a user-friendly web application where a user can upload a chest X-ray or CT scan image and receive predictions for 21 different lung diseases.

![XRayd Prediction Results](/images/xrayd_predictions.png)
*The prediction interface displays probabilities for various lung diseases in a clean, tag-based format.*

A key feature of the platform is **AI Explainability**. Alongside the predictions, the system generates a heatmap using Grad-CAM (Gradient-weighted Class Activation Mapping). This visualization highlights the specific regions in the scan that the model focused on to make its prediction, offering crucial transparency.

![XRayd Explainability with Grad-CAM](/images/xrayd_explainability.png)
*Example of Grad-CAM output, showing the original X-ray next to the heatmap for a TB prediction.*

## The Technical Backbone: A Suite of Specialized Models

The platform is powered by a collection of distinct, fine-tuned deep learning models, each tailored for a specific classification task. This multi-model approach ensures higher accuracy and robustness.

### Model Summaries

<details>
  <summary><strong>1. Multi-Class COVID-19 Classification (EfficientNetB7)</strong></summary>
  <p>This model uses a transfer learning approach with EfficientNetB7 for classifying chest X-rays into four categories, including COVID-19. By freezing the pre-trained base and adding a custom classification head, the model achieved approximately 85% validation accuracy, with Grad-CAM for interpretability.</p>
</details>

<details>
  <summary><strong>2. Multi-Label Disease Classification (SEResNet152)</strong></summary>
  <p>To handle the complex NIH Chest X-ray dataset, we employed a pre-trained SEResNet152. The architecture was adapted with a custom classifier head and trained on a TPU using Binary Cross-Entropy loss and class weights to manage severe class imbalance, evaluated with per-class AUC and accuracy.</p>
</details>

<details>
  <summary><strong>3. Multi-Label Cancer Classification (VGG16)</strong></summary>
  <p>This model identifies four types of cancer from CT scans. Built on a fine-tuned VGG16 base, it features a custom head with Batch Normalization and ReLU activations for stable learning. The model was trained over 100 epochs, with performance tracked via accuracy/loss curves and Grad-CAM visualizations.</p>
</details>

<details>
  <summary><strong>4. Binary Pneumonia Classification (Custom VGG-style CNN)</strong></summary>
  <p>We implemented a custom VGG-style CNN for binary "Normal" vs. "Pneumonia" classification. Initial layers were seeded with VGG16 weights. A key feature was a custom data generator that performed on-the-fly data augmentation and oversampling to address class imbalance, achieving 82.5% test accuracy with high recall (0.99).</p>
</details>

## Technologies Used

- **Machine Learning:** TensorFlow, Keras, EfficientNet, SEResNet, VGG16
- **Backend:** Python, Flask
- **Frontend:** HTML, CSS, JavaScript

## Outcome

- **Second Runner Up, AI for Healthcare Hackathon 2021:** The project was recognized for its technical sophistication, practical application, and emphasis on explainable AI.

![Second Runner Up Certificate](/images/AI for Healthcare Hackathon.png)


**[View Source Code on GitHub](https://github.com/shivamtawari/XRayd-AI)** 