
#  Alzheimer's Disease Image Preprocessing Pipeline

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A robust preprocessing pipeline designed to transform raw **3D MRI brain scan data** into optimized **2D grayscale image slices**, accompanied by structured metadata for Machine Learning and Deep Learning applications.

---

##  Project Overview

This project streamlines the preparation of **ADNI (Alzheimer's Disease Neuroimaging Initiative)** datasets. Raw medical imaging is often too heavy and complex for standard CNNs; this pipeline bridges that gap by:

* **Dimensionality Reduction:** Converting 3D `.nii` volumes into high-quality 2D slices.
* **Format Standardizing:** Transforming medical data into `.png` grayscale images.
* **Data Alignment:** Merging disparate metadata files into a single, structured CSV for model training.

---

##  Objectives

- [x] **Extraction:** Convert `.nii` medical images into 2D slices.
- [x] **Normalization:** Standardize pixel intensity and convert to grayscale.
- [x] **Organization:** Automate folder structures for large-scale datasets.
- [x] **Data Merging:** Consolidate metadata into a single source of truth.

---

##  Folder Structure

```text
ADNI_PRE/
├── raw_data/                  # Original ADNI Dataset
│   ├── ADNI1_Complete_3T/
│   │   └── ADNI/
│   │       └── 002_S_0413/    # Subject ID
│   │           └── *.nii      # Raw scans
│   └────  ADNI1_Complete_3T.csv
│   ├── ADNI1_Complete_2T/
|
├── src/                       # Source file with main functions
│   ├── convert_to_slices.py/  # Slice the 3D images into 2D images
│   └── merge_csv.py/          # Merge all the different csv files into one master csv
│   └── utils.py/              # Conatins utilty functions like find_all_nii_images, get_image_id, get_subject_id
|
├── processed_data/            # Pipeline Output
│   ├── slices/                # Generated 2D .png images
│   └── final_metadata/        # Combined structured CSV
├── run_pipeline.py            # Main execution script
└── requirements.txt           # Project dependencies
```

---

##  Tech Stack

| Library | Purpose |
| :--- | :--- |
| **NiBabel** | Handling and header extraction of `.nii` files |
| **NumPy** | High-performance matrix operations for image arrays |
| **Pandas** | Metadata manipulation and CSV consolidation |
| **OpenCV / PIL** | Image normalization and `.png` encoding |

---

##  Installation & Setup

### 1. Clone the Repository
```bash
git clone [https://github.com/your-username/ADNI_PRE.git](https://github.com/your-username/ADNI_PRE.git)
make sure to create raw data folder as shown in folder structure
cd ADNI_PRE
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the Pipeline
```bash
python run_pipeline.py
```

##  Output Details

Upon successful execution, the `processed_data/` directory will contain:

1.  **Image Data (`/slices/`)**: 2D grayscale `.png` slices indexed by subject and slice number.
2.  **Metadata (`/final_metadata/`)**: A master CSV file linking each image slice to its corresponding clinical labels (Subject ID, Diagnosis, Age, etc.).

---

##  Common Issues & Fixes

> [!TIP]
> **Windows Path Limit:** If you encounter errors regarding file paths, move your project closer to the root directory (e.g., `C:/ADNI_PRE`) or shorten the raw data folder names.

| Error | Cause | Solution |
| :--- | :--- | :--- |
| **Permission Denied** | Metadata CSV is open in Excel | Close the file before running the script. |
| **Path Length Error** | Character limit exceeded (>260) | Rename `ADNI1_Complete_1.5Yr_3T` to `3Yr_3T`. |
| **ModuleNotFound** | Missing dependencies | Re-run `pip install -r requirements.txt`. |

---

##  License
Distributed under the MIT License. See `LICENSE` for more information.
```
