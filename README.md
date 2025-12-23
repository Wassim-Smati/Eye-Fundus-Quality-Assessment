# Hand-crafted Visual Features for Eye Fundus Image Quality Assessment

## 📋 Project Overview

This project aims to automate the quality assessment of **Retinal Fundus Images** (RGB). In medical diagnostics, poor-quality images can lead to misdiagnosis or automated analysis failures. Our solution uses **Machine Learning (SVM)** based on **hand-crafted visual features** to classify images as "Good" or "Bad" (Reject).

This work was conducted as a student project at **Télécom Paris (Institut Polytechnique de Paris)**.


### Key Objectives
* **Filter** unreadable images before they reach diagnostic algorithms.
* **Analyze** the impact of various image features (texture, sharpness, contrast).
* **Compare** different preprocessing and augmentation techniques.

---

## 🛠 Methodology

The pipeline follows a classical Machine Learning approach rather than Deep Learning, focusing on feature engineering.

1.  **Preprocessing**:
    * Cropping to remove black borders.
    * Resizing for consistency.
    * **CLAHE** (Contrast Limited Adaptive Histogram Equalization) to enhance local contrast.
2.  **Feature Extraction**:
    * **Statistical Features**: Mean, standard deviation, skewness, kurtosis of pixel intensities.
    * **Texture Features (GLCM)**: Contrast, Correlation, Energy, Homogeneity (Haralick features).
    * **Sharpness/Focus**: Laplacians and gradient-based metrics to detect blur.
    * *PyRadiomics* (explored for advanced feature extraction).
3.  **Data Augmentation**:
    * Artificial degradation (Gaussian blur, noise) to balance the "Bad Quality" class.
    * Rotations to increase dataset diversity.
4.  **Classification**:
    * **Model**: Support Vector Machine (SVM).
    * **Kernel**: RBF (Radial Basis Function).


---

## 📊 Results

The model performance was evaluated on a test set containing both original and augmented images.

* **Global Accuracy**: ~87%
* **Recall (Good Quality)**: High (~0.95), ensuring good images are rarely discarded.
* **Challenges**: Class 0 (Bad Quality) remains harder to detect due to class imbalance, despite data augmentation efforts.

---

## 📂 Project Structure

```bash
├── Version_Finale (1).ipynb   # Main Jupyter Notebook containing the full pipeline
├── RAPPORT_DE_PROJET.pdf      # Detailed project report (French)
├── README.md                  # Project documentation
└── data/                      # Dataset folder (not included in repo)
