# 🎓 LectureMind — RAG-Based AI Teaching Assistant

> Transform long lecture videos into an interactive, searchable and
> timestamp-aware AI learning assistant.

---

## 📌 Overview

**LectureMind** is an end-to-end **Retrieval-Augmented Generation (RAG)**
application that converts technical lecture videos into an interactive
AI teaching assistant.

The system extracts audio from lecture videos, generates timestamped
transcripts using **Faster-Whisper**, creates semantic chunks, generates
embeddings using **SBERT**, and stores them in **FAISS** for efficient
similarity search.

A **Cross-Encoder** reranks retrieved lecture segments before passing
the most relevant evidence to an **OpenRouter LLM**. This enables
grounded answers based specifically on the lecture content.

The application is built using **Streamlit** and provides four core
functionalities:

- 📚 Lecture Processing
- 🤖 AI Tutor
- 📝 Study Guide
- 🧪 Quiz Generator

---

## 🚀 Key Features

### 📚 Lecture Processing

- Upload lecture videos in `.mp4`, `.mov`, `.mkv`, `.avi`, or `.webm`
- Extract audio using **FFmpeg**
- Generate timestamped transcripts using **Faster-Whisper**
- Create overlapping semantic chunks
- Generate dense semantic embeddings
- Build a **FAISS** vector index

### 🤖 AI Tutor

Ask questions directly about the lecture.

The system performs:

```text
Question
   ↓
SBERT Embedding
   ↓
FAISS Retrieval
   ↓
Top-K Candidates
   ↓
Cross-Encoder Reranking
   ↓
Relevant Lecture Evidence
   ↓
OpenRouter LLM
   ↓
Grounded Answer
