🧠 Brain Tumor Segmentation Using Deep Learning
This project presents an end-to-end deep learning pipeline for brain tumor segmentation from MRI images. Multiple segmentation architectures were implemented, trained, and systematically tuned to analyze their performance on a medical imaging dataset.
📌 Project Objectives
Perform automated brain tumor segmentation using MRI scans
Implement and compare multiple deep learning architectures
Apply parameter tuning to improve segmentation performance
Evaluate models using quantitative and qualitative metrics
🧩 Models Implemented
The following models were developed and compared:
UNet
ResUNet
Simplified DeepLab (ASPP-based)
Each model performs binary semantic segmentation to predict tumor regions.
📂 Dataset
Dataset Name: Brain MRI Images for Brain Tumor Detection
Directory: kaggle_3m
Image Format: .tif
Mask Format: Binary tumor masks (*_mask.tif)
Dataset Split
Training: 70%
Validation: 15%
Testing: 15%
Images were resized to 128 × 128 and normalized to [0, 1].
⚙️ Data Preprocessing
Image resizing and normalization
Mask binarization
Patient-wise folder loading
Randomized dataset splitting
🧪 Loss Function & Metrics
Loss Function
Binary Cross-Entropy + Dice Loss
Evaluation Metrics
Dice Coefficient
Intersection over Union (IoU)
Precision
Recall
F1-score
ROC-AUC
PR-AUC
🔧 Parameter Tuning Strategy
To improve model performance and training stability, manual parameter tuning was performed. The following hyperparameters were experimentally adjusted:
Tuned Hyperparameters
Batch Size: 16 → 32
Learning Rate: 3e-4 → 1e-6
Loss Function: BCE + Dice (baseline)
Rationale
Increasing the batch size to 32 improved gradient stability
Reducing the learning rate to 1e-6 enabled finer weight updates during later training stages
Early stopping was used to prevent overfitting
Multiple configurations were trained and compared, and the best-performing settings were selected based on validation Dice coefficient.
🏋️ Training Configuration
Parameter	Values Tested
Optimizer	Adam
Learning Rate	3e-4, 1e-6
Batch Size	16, 32
Epochs	40
Early Stopping	Enabled
📊 Model Evaluation & Comparison
Each trained model was evaluated on the test dataset using the same metrics.
Results were summarized in a comparison table and ranked by Dice coefficient.
Observed Performance Trend:
ResUNet > UNet > DeepLab
🖼️ Visualization
The following visualizations were generated:
Original MRI images
Ground truth tumor masks
Predicted segmentation masks
Overlay of predictions on MRI images
These qualitative results complement quantitative metrics.
▶️ How to Run the Project
Open the notebook in Google Colab
Mount Google Drive
Set the dataset path:
DATASET_PATH = "/content/drive/MyDrive/kaggle_3m"
Run all cells sequentially
📁 Project Structure
├── data_loading.py        # Data loading & preprocessing
├── models.py              # UNet, ResUNet, DeepLab
├── train.py               # Training and tuning
├── evaluate.py            # Metrics and evaluation
├── visualization.py       # Result visualization
├── README.md              # Project documentation
(In the Colab notebook, all components are implemented sequentially.)
🚀 Future Work
Attention UNet
Learning rate scheduling
Cross-validation
Multi-class tumor segmentation
Model ensembling
