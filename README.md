# SyntacticalProcessing

# Identifying Entities in Healthcare Data

This repository features a machine learning project aimed at developing a custom Named Entity Recognition (NER) model to identify  **Diseases** and **Treatments** in medical text data. The goal is to extract predicted treatments linked to diseases using a Conditional Random Fields (CRF) model for enhanced information retrieval.

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Overview

The goal of this project is to identify diseases and treatments from unstructured medical text. The project involves:

- **Data Preprocessing**: Cleaning and transforming raw medical text into structured sentences with corresponding labels.
- **Feature Engineering**: Creating relevant features for each word, including word identity, capitalization, and context-based features (e.g., neighboring words).
- **Model Building**: Training a Conditional Random Fields (CRF) model to assign disease (D) and treatment (T) labels to the dataset.
- **Evaluation**:: Predicting labels for the test dataset and extracting predicted treatments associated with each disease.

## Dataset
The provided dataset includes:
- `train_sent`: Training sentences.
- `train_label`: Labels corresponding to the training sentences.
- `test_sent`: Test sentences.
- `test_label`: Labels corresponding to the test sentences.

## Methodology
The project is divided into several steps:
1. **Data Preprocessing**: 
   - Construct complete sentences from individual words.
   - Create matching label sequences for each sentence.
   
2. **Feature Engineering**: 
   - Define features for each word, including:
     - Word identity (lowercased)
     - Suffixes (last 2-3 characters)
     - Capitalization check
     - Word is numeric or not
     - Contextual features (previous and next word characteristics)
     
3. **Model Building**:
   - A Conditional Random Fields (CRF) model is trained using the `sklearn_crfsuite` library.
   
4. **Disease-Treatment Extraction**: 
   - Predicted labels from the CRF model are used to extract the corresponding treatments for each identified disease.
   - This is stored in a structured format (e.g., pandas DataFrame).

## Installation

pip install pandas numpy  spacy sklearn-crfsuite
python -m spacy download en_core_web_sm
