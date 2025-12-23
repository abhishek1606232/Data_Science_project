# 🧠 Brain Tumor Segmentation Using Deep Learning

This project presents an **end-to-end deep learning pipeline** for brain tumor segmentation from MRI images. Multiple segmentation architectures were implemented, trained, and systematically tuned to analyze their performance on a medical imaging dataset.

---

## 📌 Project Objectives

- Perform automated brain tumor segmentation using MRI scans  
- Implement and compare multiple deep learning architectures  
- Apply parameter tuning to improve segmentation performance  
- Evaluate models using quantitative and qualitative metrics  

---

## 🧩 Models Implemented

The following models were developed and compared:

- **UNet**
- **ResUNet**
- **Simplified DeepLab (ASPP-based)**

Each model performs **binary semantic segmentation** to predict tumor regions.

---

## 📂 Dataset

- **Dataset Name:** Brain MRI Images for Brain Tumor Detection  
- **Directory:** `kaggle_3m`  
- **Image Format:** `.tif`  
- **Mask Format:** Binary tumor masks (`*_mask.tif`)  

### Dataset Split

- **Training:** 70%  
- **Validation:** 15%  
- **Testing:** 15%  

Images were resized to **128 × 128** and normalized to **[0, 1]**.

---

## ⚙️ Data Preprocessing

- Image resizing and normalization  
- Mask binarization  
- Patient-wise folder loading  
- Randomized dataset splitting  

---

## 🧪 Loss Function & Metrics

### Loss Function

- **Binary Cross-Entropy + Dice Loss**

### Evaluation Metrics

- Dice Coefficient  
- Intersection over Union (IoU)  
- Precision  
- Recall  
- F1-score  
- ROC-AUC  
- PR-AUC  

---

## 🔧 Parameter Tuning Strategy

Manual parameter tuning was applied to improve model performance and training stability.

### Tuned Hyperparameters

- **Batch Size:** `16 → 32`  
- **Learning Rate:** `3e-4 → 1e-6`  
- **Loss Function:** BCE + Dice  

### Rationale

- Increasing batch size improved gradient stability  
- Lower learning rate enabled finer weight updates  
- Early stopping prevented overfitting  

The best configuration was selected using **validation Dice coefficient**.

---

## 🏋️ Training Configuration

| Parameter        | Values Tested      |
|------------------|-------------------|
| Optimizer        | Adam              |
| Learning Rate    | 3e-4, **1e-6**    |
| Batch Size       | 16, **32**        |
| Epochs           | 40                |
| Early Stopping   | Enabled           |

---

## 📊 Model Evaluation & Comparison

All models were evaluated on the **test dataset** using the same metrics. Results were summarized in a comparison table and ranked by Dice score.

**Observed performance trend:**


