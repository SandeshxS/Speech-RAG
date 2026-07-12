# Speech-RAG

An end-to-end RAG assistant that turns raw audio — from a YouTube link or an uploaded file — into a searchable, summarized record. It transcribes, translates Hindi speech to English using Sarvam AI API, summarizes with an LLM, and lets you chat with the transcript using RAG.

## Features

- **🎥 Flexible input** — paste a YouTube URL or upload an audio file directly
- **🗣️ Transcription** — speech-to-text via Sarvam AI API
- **🌐 Hindi → English translation** — automatic language detection and translation using the Sarvam AI API
- **📝 Content summarization** — LangChain LCEL pipeline on Groq's free-tier LLMs to generate a summary, key decisions, and action items
- **💬 Chat with your transcript** — RAG pipeline built on ChromaDB + HuggingFace embeddings for grounded Q&A over the content
- **📄 Export** — download results as PDF or TXT
- **🖥️ Simple UI** — built entirely in Streamlit


## How it works

```
YouTube URL / Audio Upload
        │
        ▼
  yt-dlp (if URL) ──► extract audio
        │
        ▼
  Sarvam AI API ──► transcript / Hindi → English translation
        │
        ▼
  LangChain LCEL + Groq ──► summary, key decisions, action items
        │
        ▼
  ChromaDB + HuggingFace embeddings ──► vector store for RAG chat
        │
        ▼
  Streamlit UI ──► view results, chat with transcript, export PDF/TXT

```
