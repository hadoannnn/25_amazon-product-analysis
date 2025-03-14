# Selling on Amazon: The Patterns Behind Success
Welcome to my DA401 Capstone Project!

This project aims to understand the relationship between product presentation attributes and product success on Amazon, focusing on the Amazon Fashion category. Specifically, it examines how verbal data (titles, descriptions, and features), non-verbal data (images), and video presence influence product ratings and review counts. 
## Methodology Overview
To quantify these elements, I first compute a score for them as following: 
1. Textual analysis
    - Readability Score: using Automated Readability Index or ARI. The formula for ARI is $$ARI = 4.71 \times \left(\frac{\text{characters}}{\text{words}}\right) + 0.5 \times \left(\frac{\text{words}}{\text{sentences}}\right) - 21.43$$. Lower scores indicate higher readability, meaning the content is easier for consumers to understand.
    - Informativeness Score: a lexicon-based method is employed, where product descriptions are analyzed for key attributes using n-gram extraction and part-of-speech tagging to identify meaningful noun-adjective and noun-noun pairs. A final score is then calculated by the formula: $0.5 \log(\text{word count}) + 0.5 (\text{unique product attributes})$. This formula balances long descriptions with rich product details while penalizing excessively short descriptions.

2. Visual analysis:
  - Aesthetic Score: Images are evaluated using Google’s NIMA deep learning model, which predicts human-perceived aesthetic quality.
The model assigns a probability distribution to aesthetic scores (1–10), and the final score is computed as the weighted mean.
  - Social Presence Score: Social presence is quantified by detecting human figures in product images using YOLO (You Only Look Once), a real-time object detection model. If a person is detected, the Social Presence Score (SPS) = 1, otherwise, SPS = 0. This approach captures whether human models are featured in product imagery

3. Video Presence: Video presence is recorded as 1 if a listing includes a video and 0 if it does not.

To assess relationships, I then employ:
- Multiple Linear Regression
- Polynomial Regression
- Tree-based Model (XGBoost)

These models provide insights into how presentation attributes influence product ratings and engagement.
