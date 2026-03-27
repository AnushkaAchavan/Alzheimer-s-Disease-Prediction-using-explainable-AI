$$ # Alzheimer's ~Disease ~Image ~Preprocessing ~Pipeline $$ 

A robust preprocessing pipeline designed to convert raw 3D MRI brain scan data into usable 2D grayscale image slices, along with structured metadata for further Machine Learning and Deep Learning tasks.

## Project Overview

This project focuses on preparing Alzheimer's Disease Neuroimaging Initiative (ADNI) dataset images for model training.

## The pipeline:

Converts 3D .nii MRI scans → 2D slices
Transforms images into grayscale .png format
Generates a final combined metadata CSV

This preprocessing step is essential for building accurate AI models for Alzheimer's disease detection.

 ## Objectives
 Convert .nii medical images into 2D slices
 Normalize and convert images into grayscale .png format
 Organize processed data efficiently
 Merge multiple metadata files into a single structured CSV
 
## Folder Structure
raw_data/
│
├── ADNI1_Complete_1.5Yr_3T/
│ ├── ADNI/
│ │ ├── 002_S_0413/
│ │ │ ├── *.nii files
│ │
│ ├── metadata.csv
│
processed_data/
│
├── slices/ # Generated 2D image slices
└── final_metadata/ # Combined CSV file
│
ADNI_PRE/
│
├── run_pipeline.py
└── requirements.txt

 ## Installation & Setup
* 1️ Clone the Repository
git clone <your-repo-link>
cd ADNI_PRE
* 2️ Install Dependencies
pip install -r requirements.txt
* 3️ Run the Pipeline
python run_pipeline.py
 
 ## Output
 
After successful execution, you will get:

 Image Data
 Location: processed_data/slices/
 Contains: 2D grayscale .png image slices
 Metadata
Location: processed_data/final_metadata/
Contains:
Combined CSV from all folders
Corresponding image slice IDs
 Common Issues & Fixes
 1. CSV File Locked Error

Problem: Pipeline stops if CSV is open
Solution:
Close the CSV file before running the script

Problem: File path exceeds 260–279 character limit

## Solutions:

Rename folders to shorter names

ADNI1_Complete_3Yr_3T → 3Yr_3T

Move project closer to root directory

C:/Projects/ADNI_PRE

 ## Use Cases
 Alzheimer's Disease Detection
 Deep Learning (CNN models)
 Medical Image Analysis
 Research & Academic Projects
 
 ## Tech Stack
Python 
NumPy
Pandas
NiBabel (for .nii files)
OpenCV / PIL

 ## Future Improvements
 Add data augmentation
 Visualization dashboard
 Parallel processing for faster slicing
 Direct integration with ML models
