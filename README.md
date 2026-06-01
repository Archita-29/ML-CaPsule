# Emotion Audio Classification using MFCC and KNN

## Overview

This project implements an Emotion Audio Classification system that detects human emotions from speech audio using Mel-Frequency Cepstral Coefficients (MFCC) and the K-Nearest Neighbors (KNN) algorithm.

The model is trained on the RAVDESS (Ryerson Audio-Visual Database of Emotional Speech and Song) dataset and can classify speech into multiple emotional categories.

## Features

* Audio preprocessing and WAV file handling
* MFCC feature extraction from speech signals
* Emotion classification using K-Nearest Neighbors (KNN)
* Euclidean distance-based similarity calculation
* Model evaluation using accuracy metrics
* Emotion prediction for unseen audio samples
* Model persistence using Pickle

## Supported Emotions

The model supports classification of the following emotions:

* Neutral
* Calm
* Happy
* Sad
* Angry
* Fearful
* Disgust
* Surprised

## Dataset

This project uses the RAVDESS Speech Emotion Recognition dataset.

The dataset contains professionally recorded speech samples expressing different emotions from multiple actors.

Dataset Structure:

```text
Actor_01/
Actor_02/
...
Actor_24/
```

Each audio filename contains encoded information about the emotion being expressed.

Example:

```text
03-01-05-01-02-01-12.wav
```

Emotion code:

```text
01 → Neutral
02 → Calm
03 → Happy
04 → Sad
05 → Angry
06 → Fearful
07 → Disgust
08 → Surprised
```

## Project Workflow

```text
Audio Files
     ↓
Preprocessing
     ↓
MFCC Feature Extraction
     ↓
Feature Vector Generation
     ↓
Train-Test Split
     ↓
KNN Classification
     ↓
Emotion Prediction
     ↓
Performance Evaluation
```

## Feature Extraction

Mel-Frequency Cepstral Coefficients (MFCCs) are extracted from each audio sample to capture important speech characteristics.

Steps:

1. Load WAV audio file
2. Normalize audio signal
3. Extract MFCC coefficients
4. Compute mean MFCC values
5. Generate a fixed-length feature vector

## Model Training

The extracted MFCC feature vectors are used to train a K-Nearest Neighbors classifier.

Training pipeline:

* Load dataset
* Extract MFCC features
* Encode emotion labels
* Split data into training and testing sets
* Standardize features
* Train KNN classifier
* Evaluate model performance

## Evaluation

The model is evaluated using:

* Accuracy Score
* Confusion Matrix
* Classification Report

### Sample Result

```text
Accuracy: 71.64%
```

Note: Accuracy may vary depending on train-test split and preprocessing settings.

## Installation

Clone the repository:

```bash
git clone <repository-url>
cd emotion-audio-classification
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Requirements

```text
numpy
pandas
scipy
python_speech_features
scikit-learn
matplotlib
pickle
```

## Usage

### Train the Model

```bash
python train.py
```

### Predict Emotion from Audio

```bash
python predict.py
```

Example:

```text
Input Audio: sample.wav

Predicted Emotion: Happy
```

## Model Persistence

The trained model and preprocessing objects are stored using Pickle for future inference.

Saved components:

* Training Features
* Training Labels
* Feature Scaler
* Label Encoder
* K Value

## Future Enhancements

* Real-time microphone input
* Deep Learning based emotion recognition
* CNN/LSTM architectures
* Graphical User Interface (GUI)
* Live emotion monitoring
* Improved feature engineering

## Acknowledgements

* RAVDESS Dataset
* Scikit-learn
* Python Speech Features
* SciPy

## License

This project follows the license terms of the parent repository.
