# 📝 Conversation Summarizer

A **conversation summarization application** built using **T5 (Text-to-Text Transfer Transformer)** and **FastAPI**. The project fine-tunes the `t5-small` model on the **SAMSum dataset** to generate concise summaries of conversations.

The trained model is integrated with a FastAPI backend, allowing users to send a conversation and receive an automatically generated summary.

---

## 🚀 Features

* 🤖 T5-based abstractive conversation summarization
* 💬 Summarizes multi-person conversations
* 📚 Fine-tuned on the SAMSum dataset
* ⚡ FastAPI backend
* 🔌 REST API endpoint for conversation summarization
* 🧹 Conversation preprocessing and cleaning
* 🔤 T5 tokenization
* 🎯 Beam-search based generation
* 💻 CPU/GPU support when available

---

## 🧠 Model

The project uses **T5-small**.

T5 treats conversation summarization as a **text-to-text generation task**. The input conversation is converted into tokens, passed through the encoder-decoder model, and the decoder generates a concise summary.

The model is fine-tuned using the SAMSum dataset.

---

## 📊 Dataset

The project uses the **SAMSum dataset**, which contains conversations along with human-written summaries.

Each example contains:

```text
id
dialogue
summary
```

Example:

```text
Dialogue:
Amanda: I baked cookies. Do you want some?
Jerry: Sure!
Amanda: I'll bring you tomorrow.

Summary:
Amanda baked cookies and will bring Jerry some.
```

---

## 🔄 Workflow

```text
Conversation
     ↓
Preprocessing
     ↓
T5 Tokenizer
     ↓
Fine-tuned T5 Model
     ↓
Text Generation
     ↓
Conversation Summary
     ↓
FastAPI Response
```

---

## 🌐 FastAPI API

### `POST /summarize/`

Send a conversation to the API:

```json
{
    "dialogue": "Rahul: Are you joining the workshop tomorrow?\nNeha: Yes, it starts at 10 AM."
}
```

Example response:

```json
{
    "summary": "Rahul and Neha will attend the workshop tomorrow at 10 AM."
}
```

---

## ▶️ Run the Application

Install dependencies:

```bash
pip install -r requirements.txt
```

Start the FastAPI server:

```bash
uvicorn app:app --reload
```

Open:

```text
http://127.0.0.1:8000
```

API documentation:

```text
http://127.0.0.1:8000/docs
```

---

## 📁 Project Structure

```text
conversation-summarizer/
│
├── Dataset/
│   ├── samsum-train.csv
│   └── samsum-validation.csv
│
├── saved_summary_model/
│
├── results/
│
├── app.py
├── index.html
├── text_summarizer.ipynb
├── requirements.txt
└── README.md
```

---

## 🛠️ Technologies

* Python
* PyTorch
* Hugging Face Transformers
* T5
* SentencePiece
* Pandas
* FastAPI
* Uvicorn
* Jinja2
* SAMSum Dataset

---

## 📈 Future Improvements

* Train using the complete SAMSum dataset
* Add ROUGE evaluation
* Improve summary length control
* Experiment with larger T5 models
* Add GPU training
* Improve handling of long conversations
* Add Docker support
* Deploy the FastAPI application

---

## 🎯 Learning Outcomes

This project demonstrates practical experience with:

* Transformer-based NLP
* T5 encoder-decoder architecture
* Conversation preprocessing
* Tokenization
* Fine-tuning pretrained models
* Text generation
* Beam search
* FastAPI model deployment
* Building an NLP inference API

---

## 👨‍💻 Author

**Sakib Khan**

A practical implementation of **Transformer-based conversation summarization using T5 and FastAPI**.
