# F5 AI Guardrail Lab – Frontend Installation Guide
This repository contains a Python Flask–based frontend application that connects to a Python-based AI Guardrail Gateway, which then integrates with F5 Calypso AI Guardrail and a backend LLM (e.g., Ollama).

The frontend does not connect to the LLM directly.
All AI traffic is enforced through the Guardrail layer.

## 1. Architecture Overview
```
Browser (UI)
   ↓
Flask Frontend App (/api/chat)
   ↓
Python Guardrail Gateway (/v1/chat/completions)
   ↓
F5 Calypso AI Guardrail (SaaS)
   ↓
LLM Runtime (Ollama /api/chat)
```

## 2. System Requirements
- OS: Ubuntu 22.04+ (tested)
- Python: 3.10+
- Network access to:
   - Guardrail Gateway (local)
   - F5 Calypso AI Guardrail (outbound HTTPS)
- LLM runtime (e.g., Ollama) reachable by Calypso AI

## 3. Directory Structure
```
/opt/chatapp
├── main_chat.py
├── templates/
│   └── index.html
└── venv/
```

## 4. Installation Steps
## 4.1 Clone the Repository
```
sudo mkdir -p /opt/chatapp
sudo chown -R $USER:$USER /opt/chatapp
cd /opt/chatapp

git clone https://github.com/<your-org>/<your-repo>.git .
```
