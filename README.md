# 🧠 AI Flashcard Generator — Hugging Face

A beginner-friendly flashcard generator built with:

- Python
- Streamlit
- Hugging Face Inference Providers
- PDF/TXT input
- CSV/JSON export

## 1. Install Python

Use Python 3.10+.

## 2. Open the project folder

In Command Prompt / PowerShell:

```bash
cd flashcard_generator_huggingface
```

## 3. Create a virtual environment

Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

## 4. Install dependencies

```bash
pip install -r requirements.txt
```

## 5. Create your Hugging Face token

Create a Hugging Face User Access Token with permission to make Inference Providers calls.

Then copy `.env.example` to `.env` and put your token there:

```env
HF_TOKEN=hf_xxxxxxxxxxxxxxxxx
HF_MODEL=openai/gpt-oss-120b:fastest
```

Do NOT share your token or upload `.env` to GitHub.

## 6. Run the application

```bash
streamlit run app.py
```

Your browser should open the Streamlit application.

## How it works

1. Paste study notes or upload a TXT/PDF.
2. Select the number and difficulty of cards.
3. Click Generate Flashcards.
4. The app sends the notes to the selected Hugging Face model.
5. The model returns structured JSON.
6. The app displays the questions and answers.
7. Export the deck as CSV or JSON.

## Changing the model

The sidebar lets you change the model. The default is:

```text
openai/gpt-oss-120b:fastest
```

You can use another chat-completion model supported by Hugging Face Inference Providers.

## Common problems

### "HF_TOKEN is missing"

Make sure the file is named exactly:

```text
.env
```

and contains:

```env
HF_TOKEN=hf_your_token_here
```

### Model/provider error

Try another currently available chat-completion model from Hugging Face Inference Providers.

### PDF gives no text

Scanned/image-only PDFs may not contain selectable text. This version extracts embedded text; OCR can be added later.

## Project structure

```text
flashcard_generator_huggingface/
├── app.py
├── requirements.txt
├── .env.example
└── README.md
```
