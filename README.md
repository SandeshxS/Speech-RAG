# AI-Video-Assistant

An end-to-end AI assistant that turns raw audio — from a YouTube link or an uploaded file — into a searchable, summarized record. It transcribes locally with Whisper, translates Hindi speech to English when needed, summarizes with an LLM, and lets you chat with the transcript using RAG.

Features
🎥 Flexible input — paste a YouTube URL or upload an audio file directly
🗣️ Local transcription — speech-to-text via faster-whisper, runs on your own machine (no audio leaves your device for this step)
🌐 Hindi → English translation — automatic language detection and translation using the Sarvam AI API
📝 Meeting summarization — LangChain LCEL pipeline on Groq's free-tier LLMs to generate a summary, key decisions, and action items
💬 Chat with your transcript — RAG pipeline built on ChromaDB + HuggingFace embeddings for grounded Q&A over the meeting content
📄 Export — download results as PDF or TXT
🖥️ Simple UI — built entirely in Streamlit


How it works

YouTube URL / Audio Upload
        │
        ▼
  yt-dlp (if URL) ──► extract audio
        │
        ▼
  faster-whisper ──► transcript (+ language detection)
        │
        ▼
  Sarvam AI API ──► Hindi → English translation (if needed)
        │
        ▼
  LangChain LCEL + Groq ──► summary, key decisions, action items
        │
        ▼
  ChromaDB + HuggingFace embeddings ──► vector store for RAG chat
        │
        ▼
  Streamlit UI ──► view results, chat with transcript, export PDF/TXT
