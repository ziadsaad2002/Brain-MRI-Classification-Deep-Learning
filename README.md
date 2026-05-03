# Brain MRI Tumor Classification: Feature Extraction vs. End-to-End Deep Learning

## Project Overview
This repository contains the implementation for a Deep Learning comparative analysis project. The goal is to classify brain MRI scans into four distinct categories: **Glioma, Meningioma, No Tumor, and Pituitary**. 

## Methodology
The project compares two distinct Deep Learning approaches using the **MobileNetV1** architecture:

*   **Approach 1: Deep Learning Feature Extraction + ML Classifier**
    *   Used a pre-trained MobileNetV1 model (frozen base) as a feature extractor.
    *   Applied a Support Vector Machine (Linear Kernel) to classify the extracted visual features.
*   **Approach 2: End-to-End Deep Learning**
    *   Appended custom dense classification layers on top of the MobileNetV1 base.
    *   Trained the entire pipeline end-to-end using categorical crossentropy.

## Key Results
Based on testing across 1,600 MRI images:
*   **Approach 1 (SVM)** achieved a **93.06% accuracy**, demonstrating excellent precision and recall across all four classes with exceptionally fast training times.
*   **Approach 2 (End-to-End)** achieved an **81.00% accuracy** after 5 epochs, struggling specifically with distinguishing gliomas from meningiomas without further training and tuning.
*   **Conclusion:** The traditional ML classifier applied to DL-extracted features proved significantly more efficient and accurate for this dataset compared to a standard end-to-end training loop within a limited epoch timeframe.

## Technologies Used
*   Python
*   TensorFlow / Keras (MobileNetV1, ImageDataGenerator)
*   Scikit-Learn (SVM, Metrics)
*   Matplotlib & Seaborn (Data Visualization)
