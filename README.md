# AI-agents

# 📺 YouTube Video Summary Creator (LangChain RAG Agent)

## 🚀 Overview
This project implements a **Retrieval-Augmented Generation (RAG) agent using LangChain** that summarizes YouTube videos and answers user questions **strictly based on the video transcript**.  
It combines transcript extraction, semantic search, and GPT-4 reasoning to deliver **accurate, non-hallucinated responses**.

---

## 🧠 What This Agent Does
- Extracts transcripts from YouTube videos using the video ID
- Splits long transcripts into manageable semantic chunks
- Stores embeddings in a vector database
- Retrieves the most relevant transcript sections for a user query
- Generates answers **only from retrieved context**
- Responds with *“I don’t know”* if the transcript lacks sufficient information

---

## 🏗️ RAG Architecture Flow
1. **Environment Setup**
   - API keys stored securely as environment variables

2. **Transcript Extraction**
   - YouTube transcripts fetched using `YouTubeTranscriptAPI`
   - Language-specific extraction supported

3. **Preprocessing**
   - Transcript printed for verification
   - Converted into snippets and merged into a single text corpus

4. **Text Chunking**
   - Text split using a text splitter
   - Chunk size: `1000`
   - Total chunks created: `75`

5. **Embedding & Vector Storage**
   - Each chunk embedded individually
   - Stored in a vector store for semantic retrieval

6. **Retrieval**
   - Top 5 semantically similar chunks retrieved based on user query

7. **Prompt Engineering**
   - System prompt:
     ```
     You are a helpful assistant.
     Answer ONLY from the provided transcript context.
     If the context is insufficient, say you don't know.
     ```

8. **LLM Response Generation**
   - Model: **GPT-4**
   - Temperature: **0.2** (deterministic, factual responses)
   - Final answer generated using augmented prompt (query + context)

---

## 🛠️ Tech Stack
- **LangChain**
- **OpenAI GPT-4**
- **YouTube Transcript API**
- **Text Splitters**
- **Vector Store & Retriever**
- **Python**

---

## 📌 Example Video Used
**Think School Podcast**  
*OpenAI VP on “How AI Will Redefine Work” featuring Srinivas Narayanan*

---

## 🔒 Guardrails & Reliability
- No external knowledge usage
- Answers grounded only in retrieved transcript chunks
- Explicit fallback when information is missing
- Designed to minimize hallucinations

---

## 📈 Future Enhancements
- Multi-video RAG support
- UI using Streamlit or Gradio
- Persistent vector database (FAISS / Chroma / Pinecone)
- Multilingual transcript support
- Timestamp-based answers

---

## 📄 Use Cases
- Summarizing long podcasts or interviews
- Extracting insights from lectures or talks
- Asking contextual questions from video content
- Learning and research workflows

---



