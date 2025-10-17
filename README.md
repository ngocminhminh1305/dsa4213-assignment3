# DSA4213 Assignment 3

## Overview
This repository contains the implementation for **Assignment 3** of the NUS DSA4213 module . This assignment fine-tuned pretrained Transformer model (**DistilBERT**) to do topic dectection task, including dataset preparation, model fine-tuning, evaluation, and error analysis. Dataset choice is **AG News dataset**. _Link to the dataset_: https://www.kaggle.com/datasets/amananandrai/ag-news-classification-dataset/data

## How to Reproduce

All experiments are implemented in the Jupyter/Colab notebook.

1. Open [`code.ipynb`](./code.ipynb) in **Google Colab**.
2. Download the datasets from the link I provided and add it to "/content/drive/MyDrive/assignment3/data". You have to create a new folder named _assignment3_, then created a new folder named _data_ inside it, then upload train.csv and test.csv in the _data_ folder
3. Run all cells from top to bottom. The notebook will:
   - Install required dependencies
   - Download dataset automatically (or provide a link if manual download is needed)
   - Preprocess data
   - Train models
   - Evaluate and generate results

No additional setup is required outside the notebook. Results (metrics, plots, and saved outputs) will be generated automatically.

## How to see the code/notebook without downloading it

You can open the code.ipynb in this Github repo or can follow this link https://colab.research.google.com/drive/1xHbVs5-YxtDu9lbh3CVxJy0wwGTSdkzi?usp=sharing to the Google Colab link 

## Repository Structure
```
├── code.ipynb # Google Colab notebook with all code & experiments
├── report.pdf # Written report (PDF)
└── README.md # This file
```

## Dataset
- **Domain**: Media
- **Task**: Text classification  
- **Preprocessing** steps (done in notebook):
  - Cleaning text
  - Tokenization
  - Train/validation/test splitting

## Methods
The notebook includes:
1. **Baseline**: Simple classifier (e.g., Logistic Regression).
2. **Transformer Fine-Tuning**: Fine-tuning of pretrained models (e.g., BERT).
3. **LoRA Fine-Tuning**: Parameter-efficient alternative to full fine-tuning.
4. **Evaluation**: Accuracy, F1 score, and length-based breakdown.

## Experiments
- All experiments are implemented in the **notebook**.  
- Hyperparameters (epochs, learning rate, batch size) are adjustable directly inside the notebook.  
- Comparisons made between:
  - Full fine-tuning vs LoRA
  - Performance on different input lengths

## Results
| Model              | Accuracy    | F1 Score
|--------------------|-------------|----------
| Baseline (LogReg)  | 87.20%      | 87.36%      
| BERT + LoRA        | 93.96%      | 93.97%      
| BERT + Full FT     | 94.38%      | 94.39%      

- LoRA reduces trainable parameters while keeping performance close to full fine-tuning.  
- Misclassifications mostly occur on short or ambiguous texts.  
