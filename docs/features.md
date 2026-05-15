# DeepGuard — Features

A detailed look at what DeepGuard does. (Showcase documentation for a GPLv3 open-source project.)

## REAL / FAKE Video Classification

Upload a video and DeepGuard returns a clear verdict — **REAL** or **FAKE** — with a confidence score. No technical interpretation required.

## ResNeXt-50 + LSTM Architecture

- **ResNeXt-50 CNN** extracts a feature vector from each video frame using transfer learning.
- **LSTM** reads those per-frame features as a sequence, learning the temporal inconsistencies between frames that betray a deepfake.

A single-frame classifier can miss manipulation that only shows up across time — DeepGuard's sequence model is built for exactly that.

## Face-Focused Preprocessing

Every frame is processed before analysis:

- The video is split into frames
- The face region is detected in each frame
- The face is cropped so the model focuses on the manipulated region

## Configurable Frame Count

Choose how many frames to analyse — from 10 up to 100. More frames means more temporal signal and higher accuracy (84% → 93%).

## Proven Accuracy

Trained and evaluated on a 6,000-video dataset built from FaceForensics++, Celeb-DF, and the Deepfake Detection Challenge (DFDC). Accuracy reaches **93.59%** at 100 frames.

## Web Application

A Django web app provides the full workflow:

- Video upload
- Prediction with confidence score
- Prediction history

## Full Training Pipeline

Beyond the web app, the project includes notebooks for the complete model lifecycle:

- Preprocessing (frame splitting, face cropping)
- Model creation and training (ResNeXt + LSTM)
- Prediction on new, unseen video

## Deployment Ready

- Runs on GPU (CUDA) or CPU
- Dockerized, with an nginx reverse-proxy configuration included
