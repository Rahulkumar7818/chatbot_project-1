# 🤖 Human-Like Conversational Chatbot

A human-like, emotionally intelligent conversational chatbot designed for consumer-facing
applications such as social platforms or UGC (User Generated Content) platforms.

This chatbot goes beyond a basic Q&A system by demonstrating **empathy, contextual
awareness, long-term memory, identity consistency, and scalability**.

---

## 🎯 Objective

To design and implement a conversational agent that:
- Feels natural and human-like
- Adapts tone based on emotional context
- Remembers users across sessions
- Maintains a consistent persona
- Avoids hallucinations and false memories
- Scales efficiently with minimal runtime cost

---

## ✨ Key Features

### 🧠 Memory System
- **Short-Term Memory:** Recent messages for smooth conversation flow
- **Long-Term Memory:** User profile, preferences, and facts stored persistently
- **Semantic Memory:** Summarized past conversations stored as vector embeddings

### 🎭 Human-Like Interaction
- Emotion-aware responses (empathetic, playful, neutral)
- Context-aware tone shifting
- Diverse and non-templated replies

### 🔐 Identity Consistency
- Fixed chatbot persona: **Ava**
- Never reveals itself as an AI or model
- Maintains consistent answers under probing questions

### 🛡️ Hallucination Resistance
- Does not fabricate memories or events
- Gives grounded or clarifying responses when unsure
- Handles contradictions gracefully

---

## 🏗️ Architecture Overview

Client (Web / Mobile / UGC Platform)
|
v
FastAPI Backend (Stateless)
|
+-- Conversation Orchestrator
| |
| +-- Tone Detection
| +-- Memory Manager
| +-- Prompt Builder
|
+-- Gemini-2.5-Flash API
|
+-- Storage Layer
|
+-- Redis (Short-term memory)
+-- PostgreSQL / MongoDB (User profiles)
+-- ChromaDB (Vector memory)


📄 Detailed architecture explanation is available in `architecture.pdf`.

---

## 🛠️ Tech Stack

| Layer | Technology |
|------|-----------|
| Backend | Python + FastAPI |
| LLM | Gemini-2.5-Flash |
| Short-Term Memory | Redis |
| Long-Term Memory | PostgreSQL / MongoDB |
| Vector Store | ChromaDB (local) |
| Hosting (Optional) | Render / HuggingFace Spaces |

---

## 🧩 Chatbot Persona

- **Name:** Ava  
- **Personality:** Warm, friendly, emotionally intelligent  
- **Tone:** Casual and respectful  
- **Role:** Digital conversational companion  

Persona is centrally defined and never changes.

---

## 🚀 Local Setup Instructions

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/your-username/chatbot.git
cd chatbot

2️⃣ Create Virtual Environment
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate

3️⃣ Install Dependencies
pip install -r requirements.txt

4️⃣ Set Environment Variables
export GEMINI_API_KEY=your_api_key
export REDIS_URL=your_redis_url
export DATABASE_URL=your_database_url

5️⃣ Run the Backend
uvicorn backend.main:app --reload

📡 API Usage
POST /chat

Request

{
  "user_id": "u123",
  "message": "Hi, I'm feeling a bit low today"
}


Response

{
  "reply": "I'm really glad you told me. Do you want to talk about what's been bothering you?"
}

🧪 Test Cases Covered
Test Case	Status
Long-term memory recall	✅
Context-aware tone adaptation	✅
Personalization over time	✅
Response naturalness & diversity	✅
Identity consistency	✅
Hallucination resistance	✅
Memory stability	✅
📂 Project Structure
chatbot/
│
├── backend/
│   ├── main.py
│   ├── llm.py
│   ├── memory.py
│   ├── tone.py
│   ├── prompts.py
│
├── data/
│   ├── chroma/
│
├── README.md
├── architecture.pdf
└── demo_video.mp4
