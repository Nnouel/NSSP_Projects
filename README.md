# README NSSP Project


This project analyzes a subset taken from the Human Connectome Project, and contains task-fMRI and structural data related to language processing, as undertaken by researchers Binder et al. The task in question contains interleaved story and task blocks, approximately matched in duration, although individual blocks vary. The purpose of the math task is to provide a comparison task equally attentionally and auditorily demanding, but unlikely to generate activation of semantic processing areas. Our goal was to study brain neural activity related to language tasks, first using GLMs to identify task-related brain activations in the math and story tasks, and secondly using Independant Component Analysis (ICA) as a data-driven approach to identify spatial maps of brain activity, which are then compared to GLM-identified regions.

## Table of Contents

- [Installation](#installation)
- [Dataset](#dataset)
  - [Downloading the Data](#downloading-the-data)
  - [Data Organisation](#data-organisation)
- [Repository Organisation](#repository-organisation)
- [Usage](#usage)
---

## 1. Installation

Clone the repository:

```bash
git clone https://github.com/Nnouel/NSSP_Projects
cd NSSP_Projects
```

---

## 2. Dataset

This project uses the following datasets:

| Dataset | Description | Source |
|---|---|---|
| `T1w` | Structural Data | [Download link](https://drive.google.com/drive/u/1/folders/1P8_oebUgEBdF1urhXrYmxlmf6I_o4n8D) |
| `fMRI` | task-fMRI data | [Download link](https://drive.google.com/drive/u/1/folders/1P8_oebUgEBdF1urhXrYmxlmf6I_o4n8D) |

### 2.1 Downloading the Data

Datasets can be downloaded from the sources listed above. The link is the same for both datasets, and leads to a Google Drive.

**Instructions:**

1. Access the dataset using the provided download link. 
2. Download folders T1w and fMRI.
3. Extract the downloaded archives, if necessary.
4. Place the files in the main repository directory.


### 2.2 Data Organisation

All datasets should be stored in the main repository directory, following this structure:

```text
T1w/
├── T1w.nii.gz
│   
└── fMRI/
    └── tfMRI_LANGUAGE_LR/
        ├── tfMRI_LANGUAGE_LR_task_onsets.csv
        └── tfMRI_LANGUAGE_LR.nii.gz
```

The dataset folders `T1w` and `fMRI` should be listed in `.gitignore`.

---

## 3. Repository Organisation

The repository is organised as follows:

```text
NSSP_Projects/
│
├── T1w.nii.gz      # Structural data
│   
├──  fMRI/
|   └── tfMRI_LANGUAGE_LR/
|        ├── tfMRI_LANGUAGE_LR_task_onsets.csv      # Task data
|        └── tfMRI_LANGUAGE_LR.nii.gz               # fMRI data
│             
│
├── G_code/
|   ├── 01_Preprocessing_GLM.ipynb                  # Part 1 notebook
|   ├── 02_ICA.ipynb                                # Part 2 notebook                 
|   └── utils.py                                    
│
├── Images/                 # Generated figures
│
│
├── requirements.txt         # Python dependencies
├── .gitignore               # Files and directories excluded from Git
├──README.md                # Project documentation
|
|
# Below, these directories are created on running `G_code/01_Preprocessing_GLM`
|
|
└── derivatives/
    └── preprocessed_data/
        ├── anat/               # Anatomical derived data
        ├── func/               # Functional derived data
        └── fmap/
```

## 4. Usage

Run notebooks starting from 01_... to 02_... in order to generate the proper preprocessing data.

For example:

```bash
# Run Part 1 notebook
jupyter G_code/01_Preprocessing_GLM.ipynb

# Run Part 2 notebook
jupyter G_code/02_ICA.ipynb
```


