# UW_Madison_GI_Tract_Segmentation
Deep learning-based solution for automatic segmentation of stomach and intestines in MRI scans to streamline MR-Linac guided radiotherapy and improve cancer treatment efficiency.

This repository hosts the code and solutions for an exciting deep learning project focused on improving cancer treatment using MRI-guided radiotherapy. The competition, supported by the UW-Madison Carbone Cancer Center, aims to create models that automatically segment the stomach and intestines on MRI scans, helping oncologists deliver more precise and efficient radiation therapy.

## 🚀 Motivation
Each year, millions of people are diagnosed with gastrointestinal cancers, and approximately half of them undergo radiation therapy. Modern technologies like MR-Linacs allow radiation oncologists to visualize tumors and surrounding organs in real-time. However, adjusting the radiation beams daily to avoid healthy tissues like the stomach and intestines is a painstaking manual process.

This competition challenges participants to develop a method to automate this segmentation process, reducing treatment times and enabling better care for patients.

![Image](https://github.com/user-attachments/assets/31485428-6796-4759-bc80-cc1398a480ec)
_In this figure, the tumor (pink thick line) is close to the stomach (red thick line). High doses of radiation are directed to the tumor while avoiding the stomach. The dose levels are represented by the rainbow of outlines, with higher doses represented by red and lower doses represented by green._

## 🩺 About the Competition
### 1. Dataset:
    The dataset consists of anonymized MRI scans from actual cancer patients, taken during 1–5 sessions across their radiation treatment period.
    Scans include variations in tumor and organ positioning across days.
    Ground truth annotations outline the stomach and intestines, enabling supervised learning approaches.
### 2. Objective:
    Develop a model that can accurately segment the stomach and intestines from MRI scans to assist in precise dose delivery and minimize damage to healthy tissues.

### 3. Real-World Impact:
    Speeds up radiation therapy sessions from 1 hour to approximately 15 minutes.
    Improves treatment tolerability for patients.
    Enables hospitals to treat more patients efficiently.

# Methodology
The approach to solving the problem of automatic segmentation of the stomach and intestines in MRI scans was designed systematically, leveraging state-of-the-art deep learning techniques. Below is the detailed methodology:

## 1. Data Preparation
### Mask Conversion:
    The provided RLE-encoded masks were converted into image masks to prepare the data for supervised learning.

### Handling Imbalance:
    Used StratifiedGroupKFold to address the imbalance between empty and non-empty images, ensuring a balanced representation in training and validation splits.

## 2. Model Architecture
    Implemented the U-Net model with two robust backbones:
        EfficientNet-B1
        ResNet-50
    The architectures were selected for their capability to efficiently capture multi-scale features and handle medical image segmentation tasks.
## 3. Loss Functions
    Experimented with different loss functions to optimize model performance. The following combinations were tried:
    Jaccard Loss
    Binary Cross-Entropy (BCE) Loss
    Dice Loss
    Tversky Loss
## 4. Data Augmentation
    To enhance the generalization of the model, various augmentation techniques were applied using the Albumentations library and some of them are given here:
    ShiftScaleRotate
    Grid Distortion
    Horizontal Flip
    Vertical Flip
    These augmentations helped the model learn from diverse variations in the data.

## 5. Optimization and Learning Rate Schedulers
    Experimented with multiple optimizers and learning rate strategies, some of them are given here:
    Cosine Annealing Scheduler: To gradually reduce the learning rate over time.
    ReduceLROnPlateau: To dynamically adjust the learning rate based on validation loss.
## 6. Training and Validation
    Utilized a StratifiedGroupKFold strategy to maintain balanced splits across folds.
    Trained the models using the augmented dataset and monitored performance across folds to ensure robustness.
## 7. Evaluation and Results Visualization
    Generated loss curves to visualize the convergence behavior during training.
![image](https://github.com/user-attachments/assets/90d37228-aa77-41bd-977f-2c5eaf328455)

    Predicted masks were analyzed qualitatively by overlaying them on the input MRI scans to assess the segmentation quality.
![image](https://github.com/user-attachments/assets/a93e885b-f33e-4c9c-b6d3-f6fb4b814e65)
