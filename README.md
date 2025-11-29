# Customer Support Multi-Agent System (RAG + Memory Bank + FastAPI + A2A)
Enterprise AI Agent for Automated Customer Support

🧠 Overview

This project is my official submission for the Agents Intensive – Capstone Project (Enterprise Track).
It implements a production-style Customer Support AI system using the Google Agent Development Kit (ADK) patterns, Gemini models, and multi-agent orchestration.

The system simulates a real customer support backend with:

✔ Multi-Agent Architecture (Payment, Refund, Order, Tech, Account, General)

✔ RAG with FAISS + Gemini Embeddings

✔ Long-Term Memory Bank (FAISS-based)

✔ A2A (Agent-to-Agent) Protocol Routing

✔ FastAPI REST Endpoints

✔ Background Worker for Long-Running Refund Investigations

✔ Full Evaluation Suite

✔ Deployed as a notebook (no cloud deployment required for submission)

This repo contains the full implementation plus exportable ZIP from Kaggle.

🏆 Features Implemented (Meets Capstone Requirements)

This project includes more than the required 3 concepts:

✔ Multi-Agent System

Separate domain agents:

PAYMENT_AGENT

REFUND_AGENT

ORDER_AGENT

TECH_AGENT

ACCOUNT_AGENT

GENERAL_AGENT

Agents communicate via A2A messages

Orchestrator handles intent routing + hop-based agent delegation

✔ RAG (Retrieval-Augmented Generation)

FAISS vector search

Gemini embedding model: text-embedding-004

Automated document chunking + metadata

✔ Memory Bank (Long-Term Memory)

Custom FAISS-based memory index

User memories attached to future queries

✔ Long-Running Operations

Thread-based Refund Investigation Engine

Pause / Resume / Status API

✔ FastAPI Restful Server

Endpoints:

POST /ask
POST /start_refund_task
GET  /task_status/{job_id}
POST /pause_task
POST /resume_task

✔ Sessions & State Management

Persistent ticket logs

User memory storage

Context compaction

✔ Evaluation Suite (Notebook Cell 17)

Measures:

Intent accuracy

RAG coverage

Agent quality

A2A correctness

Hallucination safety

E2E latency

Produces final scorecard.

📁 Repository Contents
customer-support-multi-agent-system/

│

├── Customer Support Agent.ipynb        ← Main Kaggle notebook (all code)

├── project_export.zip                  ← Full working directory export

├── requirements.txt                    ← Dependencies

└── README.md                           ← Documentation (this file)

🚀 How to Run Locally
1. Create virtual environment
python3 -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

2. Install requirements
pip install -r requirements.txt

3. Add your Gemini API key

Create a file:

.env


Inside add:

GENAI_API_KEY=your_key_here

4. Run the FastAPI server

In the notebook, Cell 15 automatically starts the server, but locally:

uvicorn main:app --reload


Then visit:

http://127.0.0.1:8000/docs

🧪 Example Query

Send a customer message:

curl -X POST -F "user_query=Payment deducted but no confirmation" http://127.0.0.1:8000/ask


You will get:

Intent classification

Agent selection

RAG context

A2A handoffs

Final answer

Ticket log file path

📊 Evaluation Results

The evaluation suite produces:

FINAL AGENT SCORECARD
===========================
Intent Accuracy:        1.00

Retriever Coverage:     1.00

Agent Quality:          0.80

A2A Correct:            True

Hallucination Safety:   0.00

E2E Latency:            ~1.6 sec


These metrics validate the correctness and reliability of the multi-agent architecture.


🧩 Use Cases

This system can be adapted for:

Enterprise customer support

Banking & fintech support

E-commerce order tracking

App technical troubleshooting

Automated helpdesk assistants

🏁 Conclusion

This project demonstrates a complete enterprise-grade multi-agent support system with:

✔ Multi-agent orchestration
✔ RAG + memory
✔ FastAPI backend
✔ Long-running tasks
✔ Full evaluation suite
✔ Production-style workflow

It represents the full application of what I learned in the Google x Kaggle Agents Intensive Program (2025).

Built by
Dinesh Karthick B (Me)(https://github.com/dineshkarthick-bca),
Dhivyadharshini K (),
Swetha K (https://github.com/swethak1766-png)

For the Kaggle x Google Agents Intensive – Capstone Project
