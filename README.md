# 🔐 PrivateGPT Local Deployment – LlamaCPP (WSL)

## 📌 Project Overview

This project demonstrates the secure local deployment of PrivateGPT using:

- 🧠 Meta-Llama-3.1-8B (GGUF)
- ⚙️ LlamaCPP backend
- 🐧 WSL (Ubuntu)
- 💻 Windows 11 Host
- 📦 Offline document ingestion (RAG pipeline)

The system runs fully offline.  
No cloud APIs. No external data exposure.

---

## 🛡 Security Objectives

- All inference runs locally
- Bound to 127.0.0.1 (no external exposure)
- Model files excluded from Git tracking
- Secrets removed from configuration files
- GitHub workflows removed to reduce CI attack surface
- Token-based Git authentication (PAT)

---

## 🏗 Architecture

Windows 11 (Host)
│
└── WSL Ubuntu
    ├── Python 3.11 (Poetry)
    ├── PrivateGPT
    ├── LlamaCPP
    └── GGUF Model (Local)

Accessed via local Gradio UI (localhost only).

---

## ⚙️ Deployment Summary

1. Installed WSL on Windows 11  
2. Cloned PrivateGPT repository  
3. Installed LlamaCPP dependencies  
4. Downloaded Meta-Llama-3.1-8B GGUF model  
5. Configured `settings-llamacpp.yaml`  
6. Launched locally via:

```bash
poetry run python -m private_gpt
```

---

## 🎯 Cybersecurity Relevance

This project demonstrates:

- Secure AI deployment
- Offline RAG architecture
- Environment isolation using WSL
- Model integrity handling
- Secure Git configuration
- Secret management best practices

---

## 👤 Author

Deloney Sime  
Cybersecurity Engineer | CEH | AI Security
