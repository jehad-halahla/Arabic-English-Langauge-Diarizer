# Arabic-English-Langauge-Diarizer
a project that highlights the need for arabic code-switched datasets and the need for models that accurately do the language diarization task.

# 🔀 Language Code-Switching Identification

An AI-based system for diarizing code-switched speech, focusing on English-Arabic language transitions. This project was developed as part of our graduation requirements for a B.Sc. in Computer Engineering at Birzeit University.

## 📌 Overview

Code-switching, the practice of alternating between languages within the same utterance, presents challenges for conventional Automatic Speech Recognition (ASR) systems. Our system addresses these challenges by integrating robust transcription and language identification models to detect and segment multilingual speech.

We use a multi-step pipeline that includes:
- Transcription using **Whisper** and **WhisperX** for word-level alignment.
- Language Identification using:
  - `speechbrain/lang-id-voxlingua107-ecapa` (pretrained)
  - A **custom CNN-based LID model** trained on Arabic-English data.
- Generation of **RTTM** files marking language segments.

## 🧠 Technologies & Tools

- **Whisper**: Multilingual speech-to-text model by OpenAI.
- **WhisperX**: Forced alignment tool for precise word-level timestamps.
- **SpeechBrain VoxLingua107-ECAPA**: Pretrained language identification model.
- **Custom CNN Model**: Built with MFCCs and trained on Mozilla Common Voice data.
- **Praat**: Used for manual ground-truth segmentation.
- **Python**: Core language for building and evaluating the pipeline.


## 🔬 Experiments and Results

| LID Approach              | DER (%) | Missed Detection | False Alarm | Confusion |
|--------------------------|---------|------------------|-------------|-----------|
| VoxLingua107-ECAPA       | 37.85   | 0.2609           | 0.0068      | 3.4608    |
| Custom CNN-based LID     | 40.09   | 0.2581           | 0.0068      | 3.8127    |

- 📌 **Evaluation Metric**: Diarization Error Rate (DER)
- Ground truth was manually constructed using Praat.

## ⚠️ Limitations

- **Short segments** degrade LID performance.
- **Dialectal variation** in Arabic affects accuracy.
- **Whisper/WhisperX** are computationally intensive.
- Manual RTTM annotation was required due to lack of datasets.

## 🚀 Future Work

- Explore lightweight forced-alignment alternatives.
- Add support for more dialects and language pairs (e.g., Arabic-Hebrew).
- Improve model efficiency (quantization, pruning).
- Extend to real-time applications (e.g., subtitle generation, virtual assistants).
- Incorporate speaker diarization.

## 👨‍💻 Authors

- [Jehad Halahla](https://github.com/jehadkhaled)
- Hamza Awashra
- Masa Itmaiza

**Supervised by**: Dr. Abualseoud Hanani  
**Birzeit University**, Department of Electrical and Computer Engineering, Class of 2025.

## 📄 License

This project is for academic and research use. Licensing terms to be defined.

## 📚 Citation

If you use this code or refer to our methodology, please cite our graduation project:

> Jehad Halahla, Hamza Awashra, Masa Itmaiza. *Language Code-Switching Identification*, Birzeit University, Jan 2025.


