---
title: "HateRaid - A Multimodal System for Detecting Hateful Memes"
excerpt: "An end-to-end system designed to identify hate speech in memes by jointly analyzing image and text content, achieving 92.6% validation accuracy."
collection: portfolio
repo: https://github.com/vishalnarnaware/HateRaid
---

HateRaid was developed for the **Manthan 2021 Hackathon**, an initiative by the Government of India focused on national security. Our team, "Artificial Mind", created this solution to tackle the growing problem of hate speech spread through multimodal content like memes.

## The Challenge: Hate is More Than Just Words

Traditional hate speech detection systems focus only on text, which is insufficient for memes. A seemingly innocuous phrase like "love the way you smell" can become deeply hateful when paired with a specific image. Detecting this requires a system that understands the complex interplay between visual and linguistic context.

![Our Approach Diagram](/images/hateful_meme.jpg)
*A visual explanation from our presentation showing how text and image combine to create hateful content.*

## The End Result: A Deployed Web Application

We designed, trained, and deployed a complete web application that allows a user to input a meme and receive a prediction on whether it is hateful or not. The system provides a clear "Hateful" or "Non-Hateful" classification.

![HateRaid Prediction UI](/images/hateful_meme_1.png)
*Screenshot of the final prediction interface from the deployed application on Azure.*

![HateRaid Features UI](/images/hateraid_ui.png)
*The application's feature page, highlighting its capabilities.*

## Our Technical Approach

Our solution was built on a robust development pipeline, from model training to deployment and user feedback.

#### 1. Model Architecture
The core of HateRaid is a supervised **Multimodal Bi-transformer (MMBT)** model. This architecture uses an "early fusion" approach, processing features from both the image and text simultaneously to make a more context-aware prediction. The model was trained on the Meta Hateful Memes Dataset, achieving a **92.6% validation accuracy**.

#### 2. Development Pipeline
We followed a structured five-step plan: Model Training → Frontend Creation → Backend Integration → Feedback Loop → Deployment. This ensured a clear path from concept to a functional product.

![Development Pipeline Diagram](/images/hateraid_pipeline.png)
*The end-to-end development pipeline we designed for the project.*

## Technologies Used

- **Machine Learning:** Python, PyTorch
- **Web Framework:** Flask
- **Deployment:** Microsoft Azure
- **Dataset:** Meta Hateful Memes Dataset

## Outcome

This project was a comprehensive exercise in building a real-world machine learning system. It demonstrated our team's ability to tackle a complex social problem with an innovative, multimodal AI solution, taking it from an idea to a deployed application.

**[View Source Code on GitHub](https://github.com/vishalnarnaware/HateRaid)**