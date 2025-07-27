# 🧠 Classifying Colon Histopathology Images Using Machine Learning

**Authors:**  
- Vonny Nguyen (s3992230)  
- Tazwar Islam (s3983534)

---

## 📌 Problem Statement

Colorectal cancer is one of the most common cancers globally. Early and accurate diagnosis of colon histopathology images can improve treatment outcomes. However, manual diagnosis is time-consuming and error-prone. This project explores machine learning, particularly Convolutional Neural Networks (CNNs), to automate the classification of colon tissue images.

---

## 📂 Dataset Summary

- **Image Size:** 27×27 pixels (RGB)  
- **Total Patients:** 99  
  - `mainData.csv` (60 patients): Full labels (cancer + cell type)  
  - `extraData.csv` (39 patients): Only cancer labels  
- **Challenges:**  
  - Class imbalance  
  - Low resolution  
  - Visually similar cell types

---

## 🎯 Project Objectives

- Perform **binary classification**: Cancerous vs. Non-cancerous cells  
- Perform **multi-class classification**: Cell types — Fibroblast, Inflammatory, Epithelial, Others  
- Compare CNNs with classical models (Logistic Regression, Random Forest, SVM, XGBoost)  
- Investigate effects of image preprocessing  
- Use robust metrics (F1-score, ROC-AUC) for imbalanced data

---

## 🔧 Methodology Overview

### 🔹 Preprocessing
- Resize: 27×27 → 64×64 (to support deeper models)  
- Normalize: Pixel values scaled to [0, 1]  
- Optional transformations:  
  - Grayscale  
  - Gaussian Blur  
  - Threshold segmentation  

### 🔹 Classical Models (Baselines)
- **Binary classification:** Logistic Regression, Random Forest  
- **Multi-class classification:** SVM (linear), XGBoost  
- Flattened pixel vectors used as features

### 🔹 CNN Model
- Architecture:
  - 2× Conv layers (ReLU) + MaxPooling
  - Dropout & L2 Regularization
  - Sigmoid (binary) / Softmax (multi-class) output
- Compiled with **Adam** optimizer
- **Early stopping** and **data augmentation** applied
- Trained on raw and preprocessed image variants

---

## 📊 Results

### Binary Classification (Cancer Detection)

| Model                | Accuracy | F1 (Macro) | ROC-AUC |
|----------------------|----------|------------|---------|
| CNN (baseline image) | **87.67%** | **0.8645** | **0.9369** |
| Logistic Regression  | 87.0%    | 0.86       | —       |
| Random Forest        | 87.0%    | 0.865      | —       |

✅ **Best results** were obtained using raw RGB images and CNN.

---

### Multi-class Classification (Cell Types)

| Model                | Accuracy | Precision | Recall | F1 (Macro) |
|----------------------|----------|-----------|--------|------------|
| CNN (baseline image) | **73.2%** | **0.70**  | **0.67** | **0.68**   |
| XGBoost              | 73.0%    | 0.67      | 0.64   | 0.65       |
| SVM                  | 66.0%    | 0.62      | 0.57   | 0.59       |

📌 CNN outperformed classical models across all metrics, especially for class balance.

---

## 🔍 Key Findings

- **CNNs capture spatial features** better than classical models.
- Preprocessing such as **grayscale** or **segmentation** often reduced performance.
- **Raw RGB images** gave the best CNN results — simplicity helped.
- Classical models struggled with minority class detection.

---

## 🌱 Future Work

- Implement **semi-supervised learning** using `extraData.csv`  
- Apply **pseudo-labeling** or **teacher-student models**  
- Conduct **ablation studies** to isolate impact of regularization techniques  
- Deploy the best CNN model as a web-based diagnostic tool

---

## 🗂 Suggested Repo Structure

# 🧠 Classifying Colon Histopathology Images Using Machine Learning

**Authors:**  
- Vonny Nguyen (s3992230)  
- Tazwar Islam (s3983534)

---

## 📌 Problem Statement

Colorectal cancer is one of the most common cancers globally. Early and accurate diagnosis of colon histopathology images can improve treatment outcomes. However, manual diagnosis is time-consuming and error-prone. This project explores machine learning, particularly Convolutional Neural Networks (CNNs), to automate the classification of colon tissue images.

---

## 📂 Dataset Summary

- **Image Size:** 27×27 pixels (RGB)  
- **Total Patients:** 99  
  - `mainData.csv` (60 patients): Full labels (cancer + cell type)  
  - `extraData.csv` (39 patients): Only cancer labels  
- **Challenges:**  
  - Class imbalance  
  - Low resolution  
  - Visually similar cell types

---

## 🎯 Project Objectives

- Perform **binary classification**: Cancerous vs. Non-cancerous cells  
- Perform **multi-class classification**: Cell types — Fibroblast, Inflammatory, Epithelial, Others  
- Compare CNNs with classical models (Logistic Regression, Random Forest, SVM, XGBoost)  
- Investigate effects of image preprocessing  
- Use robust metrics (F1-score, ROC-AUC) for imbalanced data

---

## 🔧 Methodology Overview

### 🔹 Preprocessing
- Resize: 27×27 → 64×64 (to support deeper models)  
- Normalize: Pixel values scaled to [0, 1]  
- Optional transformations:  
  - Grayscale  
  - Gaussian Blur  
  - Threshold segmentation  

### 🔹 Classical Models (Baselines)
- **Binary classification:** Logistic Regression, Random Forest  
- **Multi-class classification:** SVM (linear), XGBoost  
- Flattened pixel vectors used as features

### 🔹 CNN Model
- Architecture:
  - 2× Conv layers (ReLU) + MaxPooling
  - Dropout & L2 Regularization
  - Sigmoid (binary) / Softmax (multi-class) output
- Compiled with **Adam** optimizer
- **Early stopping** and **data augmentation** applied
- Trained on raw and preprocessed image variants

---

## 📊 Results

### Binary Classification (Cancer Detection)

| Model                | Accuracy | F1 (Macro) | ROC-AUC |
|----------------------|----------|------------|---------|
| CNN (baseline image) | **87.67%** | **0.8645** | **0.9369** |
| Logistic Regression  | 87.0%    | 0.86       | —       |
| Random Forest        | 87.0%    | 0.865      | —       |

✅ **Best results** were obtained using raw RGB images and CNN.

---

### Multi-class Classification (Cell Types)

| Model                | Accuracy | Precision | Recall | F1 (Macro) |
|----------------------|----------|-----------|--------|------------|
| CNN (baseline image) | **73.2%** | **0.70**  | **0.67** | **0.68**   |
| XGBoost              | 73.0%    | 0.67      | 0.64   | 0.65       |
| SVM                  | 66.0%    | 0.62      | 0.57   | 0.59       |

📌 CNN outperformed classical models across all metrics, especially for class balance.

---

## 🔍 Key Findings

- **CNNs capture spatial features** better than classical models.
- Preprocessing such as **grayscale** or **segmentation** often reduced performance.
- **Raw RGB images** gave the best CNN results — simplicity helped.
- Classical models struggled with minority class detection.

---

## 🌱 Future Work

- Implement **semi-supervised learning** using `extraData.csv`  
- Apply **pseudo-labeling** or **teacher-student models**  
- Conduct **ablation studies** to isolate impact of regularization techniques  
- Deploy the best CNN model as a web-based diagnostic tool

---

## 🗂 Suggested Repo Structure

# 🧠 Classifying Colon Histopathology Images Using Machine Learning

**Authors:**  
- Vonny Nguyen (s3992230)  
- Tazwar Islam (s3983534)

---

## 📌 Problem Statement

Colorectal cancer is one of the most common cancers globally. Early and accurate diagnosis of colon histopathology images can improve treatment outcomes. However, manual diagnosis is time-consuming and error-prone. This project explores machine learning, particularly Convolutional Neural Networks (CNNs), to automate the classification of colon tissue images.

---

## 📂 Dataset Summary

- **Image Size:** 27×27 pixels (RGB)  
- **Total Patients:** 99  
  - `mainData.csv` (60 patients): Full labels (cancer + cell type)  
  - `extraData.csv` (39 patients): Only cancer labels  
- **Challenges:**  
  - Class imbalance  
  - Low resolution  
  - Visually similar cell types

---

## 🎯 Project Objectives

- Perform **binary classification**: Cancerous vs. Non-cancerous cells  
- Perform **multi-class classification**: Cell types — Fibroblast, Inflammatory, Epithelial, Others  
- Compare CNNs with classical models (Logistic Regression, Random Forest, SVM, XGBoost)  
- Investigate effects of image preprocessing  
- Use robust metrics (F1-score, ROC-AUC) for imbalanced data

---

## 🔧 Methodology Overview

### 🔹 Preprocessing
- Resize: 27×27 → 64×64 (to support deeper models)  
- Normalize: Pixel values scaled to [0, 1]  
- Optional transformations:  
  - Grayscale  
  - Gaussian Blur  
  - Threshold segmentation  

### 🔹 Classical Models (Baselines)
- **Binary classification:** Logistic Regression, Random Forest  
- **Multi-class classification:** SVM (linear), XGBoost  
- Flattened pixel vectors used as features

### 🔹 CNN Model
- Architecture:
  - 2× Conv layers (ReLU) + MaxPooling
  - Dropout & L2 Regularization
  - Sigmoid (binary) / Softmax (multi-class) output
- Compiled with **Adam** optimizer
- **Early stopping** and **data augmentation** applied
- Trained on raw and preprocessed image variants

---

## 📊 Results

### Binary Classification (Cancer Detection)

| Model                | Accuracy | F1 (Macro) | ROC-AUC |
|----------------------|----------|------------|---------|
| CNN (baseline image) | **87.67%** | **0.8645** | **0.9369** |
| Logistic Regression  | 87.0%    | 0.86       | —       |
| Random Forest        | 87.0%    | 0.865      | —       |

✅ **Best results** were obtained using raw RGB images and CNN.

---

### Multi-class Classification (Cell Types)

| Model                | Accuracy | Precision | Recall | F1 (Macro) |
|----------------------|----------|-----------|--------|------------|
| CNN (baseline image) | **73.2%** | **0.70**  | **0.67** | **0.68**   |
| XGBoost              | 73.0%    | 0.67      | 0.64   | 0.65       |
| SVM                  | 66.0%    | 0.62      | 0.57   | 0.59       |

📌 CNN outperformed classical models across all metrics, especially for class balance.

---

## 🔍 Key Findings

- **CNNs capture spatial features** better than classical models.
- Preprocessing such as **grayscale** or **segmentation** often reduced performance.
- **Raw RGB images** gave the best CNN results — simplicity helped.
- Classical models struggled with minority class detection.

---

## 🌱 Future Work

- Implement **semi-supervised learning** using `extraData.csv`  
- Apply **pseudo-labeling** or **teacher-student models**  
- Conduct **ablation studies** to isolate impact of regularization techniques  
- Deploy the best CNN model as a web-based diagnostic tool

---

## 🗂 Suggested Repo Structure

├── Modified_FINAL.ipynb # Main Jupyter Notebook
├── mainData.csv # Labeled data
├── extraData.csv # Partially labeled data
├── colon_data/ # Extracted images
└── README.md # Project documentation



---

## 📚 References

- Sirinukunwattana et al. (2016). Locality Sensitive Deep Learning for Detection and Classification of Nuclei in Routine Colon Cancer Histology Images.
- Kather et al. (2019). Deep learning can predict microsatellite instability directly from histology in gastrointestinal cancer.

---

> ⚠️ **Disclaimer**: This project is for academic research purposes only and is not intended for clinical use without further validation.

