# UW_Madison_GI_Tract_Segmentation
Deep learning-based solution for automatic segmentation of stomach and intestines in MRI scans to streamline MR-Linac guided radiotherapy and improve cancer treatment efficiency.

This repository hosts the code and solutions for an exciting deep learning project focused on improving cancer treatment using MRI-guided radiotherapy. The competition, supported by the UW-Madison Carbone Cancer Center, aims to create models that automatically segment the stomach and intestines on MRI scans, helping oncologists deliver more precise and efficient radiation therapy.

## 🚀 Motivation
Each year, millions of people are diagnosed with gastrointestinal cancers, and approximately half of them undergo radiation therapy. Modern technologies like MR-Linacs allow radiation oncologists to visualize tumors and surrounding organs in real-time. However, adjusting the radiation beams daily to avoid healthy tissues like the stomach and intestines is a painstaking manual process.

This competition challenges participants to develop a method to automate this segmentation process, reducing treatment times and enabling better care for patients.

![In this figure, the tumor (pink thick line) is close to the stomach (red thick line). High doses of radiation are directed to the tumor while avoiding the stomach. The dose levels are represented by the rainbow of outlines, with higher doses represented by red and lower doses represented by green.](https://github.com/user-attachments/assets/31485428-6796-4759-bc80-cc1398a480ec)


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
