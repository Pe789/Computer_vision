# Pneumonia challenge

- Repository: `computer vision`
- Type of Challenge: `Consolidation`
- Duration: `2 days`
- Deadline: `dd/mm/yy H:i AM/PM`
- Team: `solo`

## Mission objectives

- To learn how to design and evaluate a custom made convolutional neural network for practical purposes

## The Mission

**Design a CNN capable of recognizing pneumonia in x-rays of patients**

### Must-have features

- A CNN trained on [this dataset](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia) that can recognize new images outside of the training set
- Proper model evaluation (split dataset, confusion matrix, hyper-parameter tuning, etc)
- Visualizations of model results and evaluations (properly labeled, titled...)

### Nice-to-have features

- A visualization of the feature maps of the model
- Comparison with other CNN model structures


## Repo structure
```
.
├── input\chest_xray
│   └── chest_xray/
│       └── test/
│           └── NORMAL/
│           └── PNEUMONIA/
│       └── train/
│           └── NORMAL/
│           └── PNEUMONIA/
│       └── val/
│           └── NORMAL/
│           └── PNEUMONIA/
├── .gitignore
├── README.md
├── challenge-pneumonia.ipynb
├── solution_pneumonia_0.ipynb
├── solution_pneumonia_1.ipynb
├── solution_pneumonia_2.ipynb
├── solution_pneumonia_3.ipynb
```
## Usage
### 1. Clone the repository
   
### 2. Create a virtual environment
    
### 3. Install the required libraries 
requirements.txt still to be generated

### 4. Download the data set
Respect the input structure showing in the repo

### 5. Check notebooks
#### (challenge_pneumonia.ipynb)
Notebook with the challenge explained by Becode.  Just as background info.
#### (solution-pneumonia_0.ipynb)
Notebook based on a solution found in Kaggle.  To get started.  Can be ignored as solution improved in the following notebooks:
  - only  the last dense layer is kept
  - only working in grayscale
  - dropout layer added to reduce limit of overfitting
  - early stopping added*
  - metrics added
  - SHAP added
  - ...

#### solution-pneumonia_1.ipynb
-   Contains a CNN build from scratch.
-   The model contains 15,841 trainable parameters.
-   Test results go into this order:
```
    Test Accuracy: 0.90
    Precision: 0.91
    Recall: 0.94
    AUC: 0.96
```
- Early stopping a applied, with a patience of 5, keeping the best weights.
- SHAP is implemented to explain on some sample images.

To try: Run the steps as shown in the notebooks.

#### solution-pneumonia_2.ipynb
-   Here flattening and a dense layer is being added to the pretrained VGG19 model.
-   This model contains 25,089 trainable parameters.
-   Test results go into this order:
```
    Test Accuracy: 0.93
    Precision: 0.93
    Recall: 0.97
    AUC: 0.96
```
- Early stopping a applied, with a patience of 2, keeping the best weights.

To try: Run the steps as shown in the notebooks.  Warning, training this model takes considerable more time !  Last saved version ran over 1h.

#### solution-pneumonia_3.ipynb
-   This notebook is based on solution-pneumonia_1.ipynb, but softmax is used as last activation function instead of sigmoid.
-   This model contains 22,114 trainable parameters.
-   Test results go into this order:
```
    Test Accuracy: 0.92
    Precision: 0.92
    Recall: 0.92
    AUC: 0.97
```
- Early stopping a applied, with a patience of 5, keeping the best weights.

To try: Run the steps as shown in the notebooks.  

## Notes
    *The validation set only contains 18 images (9 normal, 9 pneumonia).  Ideally, more images should be available.
    SHAP is generating black images on the model based on the pretrained VGG19 model.  No solution found yet.