# 📝 REPORT


## Objective
The goal of this project is to develop an automated system that listens to spoken English audio, extracts grammar-related features, and predicts a grammar quality score ranging from 1 to 5 (aligning with human-annotated rubric scores). The problem is approached as a regression task.

## Approach Overview
Audio Input: Raw .wav audio files (train & test).

Feature Extraction: Three sets of features are extracted:

Acoustic features (MFCCs, chroma, ZCR, spectral centroid).

Wav2Vec2 embeddings: Deep features from a pretrained transformer model that capture high-level speech/language representations.

Meta features: Duration, energy, RMS energy, and tempo.

Data Augmentation: Strong augmentations are applied to training audio for robustness.

Modeling: Both a LightGBM regressor and an MLPRegressor are trained; their predictions are ensembled.

## Pipeline Architecture

Audio Preprocessing: Resampling, trimming, normalization.

Augmentation (train only): Noise, pitch, tempo, shift.

Feature Extraction: Acoustic + deep + meta.

Feature Scaling: StandardScaler.

Model Training: LightGBM, MLPRegressor, with ensembling.

Evaluation/Visualization: RMSE, Pearson correlation, actual vs predicted scatter/distribution plots.

Submission: CSV with test predictions.

## Results

Train RMSE/Pearson: 0.0710/0.9984

Validation RMSE/Pearson: 0.8000/0.7319

Prediction Distribution: See scatter and histogram plots; predictions closely match actual scores on validation.

Submission: Test predictions saved in correct format.
