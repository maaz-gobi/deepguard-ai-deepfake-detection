# DeepGuard — Frequently Asked Questions

## General

**What is DeepGuard?**
DeepGuard is a deepfake video detection system. Upload a video and it classifies it as REAL or FAKE with a confidence score, using a ResNeXt-50 + LSTM deep-learning model.

**What problem does it solve?**
Deepfakes are increasingly used for fraud, misinformation, and impersonation. DeepGuard gives a practical, technical way to flag manipulated video.

## How It Works

**Why ResNeXt + LSTM?**
ResNeXt-50 extracts strong visual features from each frame. The LSTM then models how those features change across frames — deepfakes often leave subtle temporal inconsistencies that a single-frame model would miss.

**What does the frame count do?**
It sets how many frames of the video the model analyses. More frames means more temporal signal and higher accuracy — from ~84% at 10 frames to ~93.6% at 100 frames.

**Does it analyse the whole frame?**
No — it detects and crops the face region from each frame, so the model focuses on where manipulation actually happens.

## Performance

**How accurate is it?**
Up to 93.59% on a 6,000-video benchmark at 100 frames.

**Does it need a GPU?**
No. A GPU speeds up inference, but DeepGuard runs on CPU as well.

## Access & Licensing

**Is DeepGuard open source?**
Yes. DeepGuard is licensed under the GNU General Public License v3.0. It is a derivative work built on prior GPLv3-licensed code and is distributed under the same license.

**Can I train my own model?**
Yes. The project includes a full training pipeline — preprocessing, training, and prediction notebooks — and documents the public datasets used (FaceForensics++, Celeb-DF, DFDC).

**How do I get a demo or deployment help?**
See the Contact section in the main [README](../README.md).
