# OpenAI Whisper from Hugging Face Transformers


This repository demonstrates how to use OpenAI's Whisper model from Hugging Face Transformers for automatic speech recognition (ASR). The setup and execution are performed in a Google Colab environment.

## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Usage](#usage)
- [References](#references)

## Overview

OpenAI Whisper is a powerful ASR model that can transcribe audio files into text. This project shows how to set up and use the Whisper model to transcribe an audio file (`audio.mp3`) using Hugging Face's Transformers library.

## Installation

To get started, you need to install the Hugging Face Transformers library. This can be done directly in a Google Colab notebook.

1. **Install Hugging Face Transformers**:
    ```sh
    !pip install git+https://github.com/huggingface/transformers -q
    ```

2. **Download the audio file**:
    ```sh
    !wget -O audio.mp3 http://www.moviesoundclips.net/movies1/darkknight/criminal.mp3
    ```

## Usage

Here's a step-by-step guide to using the Whisper model for ASR:

1. **Check NVIDIA GPU availability**:
    ```sh
    !nvidia-smi
    ```

2. **Display the audio file**:
    ```python
    from IPython.display import Audio, display
    display(Audio('audio.mp3', autoplay=True))
    ```

3. **Set up the ASR pipeline using Whisper**:
    ```python
    from transformers import pipeline

    whisper = pipeline('automatic-speech-recognition', model='openai/whisper-medium', device=0)
    ```

4. **Transcribe the audio file**:
    ```python
    text = whisper('audio.mp3')
    print(text)
    ```

## References

- [Hugging Face Transformers GitHub](https://github.com/huggingface/transformers)
- [Google Colab](https://colab.research.google.com/)
- [Audio Source](http://www.moviesoundclips.net/movies1/darkknight/criminal.mp3)

This project was created using Google Colab. 

---

Feel free to clone this repository and modify it for your own use. Contributions are welcome!
