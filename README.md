# English ↔ Urdu Translator

This project implements a simple and fast English ↔ Urdu translation application using Hugging Face's `transformers` library.

## Project Overview

The goal of this project was to create an interactive tool that allows users to translate text between English and Urdu. It leverages pre-trained neural machine translation models for efficient and reasonably accurate translations.

## How It Works

1.  **Model Loading**: The application utilizes two specialized MarianMT models from the Helsinki-NLP group, hosted on Hugging Face:
    *   `Helsinki-NLP/opus-mt-en-ur` for English to Urdu translation.
    *   `Helsinki-NLP/opus-mt-ur-en` for Urdu to English translation.
    These models are loaded using `AutoTokenizer` and `AutoModelForSeq2SeqLM` to ensure compatibility.

2.  **Translation Pipelines**: The `transformers.pipeline` function is used to encapsulate the translation process for each direction, handling tokenization, model inference, and output decoding seamlessly.

3.  **Hugging Face Interface (Gradio based)**: The application is designed to be deployed on Hugging Face Spaces, typically using Gradio for the interactive UI:
    *   A dropdown menu allows users to select the translation direction (English → Urdu or Urdu → English).
    *   A "Swap" button quickly reverses the translation direction.
    *   Input and output textboxes facilitate easy text entry and display of translated results.
    *   Example translations are provided for quick demonstration.

4.  **Translation Logic**: The `translate_text` function takes the input text and selected direction, calls the appropriate translation pipeline, and returns the translated text.

## Setup and Usage

To run this application, ensure you have the necessary libraries installed:

```bash
pip install transformers==4.38.2 sentencepiece torch
```

Once installed, you can run the Gradio application code within a Python environment (like a Colab notebook) or deploy it directly to a Hugging Face Space.

## Live Application

**[https://huggingface.co/spaces/hassan121ahmad/eng_urdu_translator]**

_To create a Hugging Face Space, you typically upload your `app.py` (which contains the Gradio code) and a `requirements.txt` (listing dependencies like `transformers`, `sentencepiece`, `torch`, and `gradio`). Once deployed, you will get a public URL for your Space._

## Technologies Used

*   **Python 3.x**
*   **Hugging Face Transformers**: For neural machine translation models.
*   **Hugging Face Spaces / Gradio**: For deploying and interacting with the web UI.
*   **SentencePiece & Torch**: Dependencies for the Hugging Face models.
