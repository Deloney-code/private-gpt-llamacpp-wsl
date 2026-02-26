#🔐 PrivateGPT: Hardened Local AI Architecture (WSL/LlamaCPP)
## 📌 Executive Summary
In an era where data privacy is the primary barrier to AI adoption, this project demonstrates a zero-trust, fully air-gapped deployment of a Large Language Model (LLM). By leveraging WSL and LlamaCPP, I have engineered a solution that allows organizations to utilize Retrieval Augmented Generation (RAG) without the risk of intellectual property leakage associated with cloud-based AI providers (e.g., OpenAI, Anthropic).

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

##🛠 Tech Stack

Engine: LlamaCPP (High-performance C++ inference)

Model: Meta-Llama-3.1-8B-Instruct (GGUF Quantized)

Environment: WSL2 (Ubuntu 22.04 LTS) on Windows 11

Logic: PrivateGPT + LlamaIndex

Orchestration: Poetry (Dependency isolation)

## 🛡 Security Objectives

- All inference runs locally
- Bound to 127.0.0.1 (no external exposure)
- Model files excluded from Git tracking
- Secrets removed from configuration files
- GitHub workflows removed to reduce CI attack surface
- Token-based Git authentication (PAT)

---
## 🛡 Security Hardening & Controls

This deployment is intentionally hardened to meet strict cybersecurity compliance standards:

Network Isolation: The API and Gradio UI are bound strictly to 127.0.0.1. This prevents "Side-loading" attacks or unauthorized access from the local network (LAN).

Zero-Telemetry: All external "phone-home" features are disabled. 100% of the inference and document embedding occurs in the isolated WSL RAM space.

Attack Surface Reduction: Removed all upstream .github/workflows and CI/CD configurations to prevent Supply Chain Attacks and unauthorized automated runners.

Secrets Management: Implemented .gitignore hardening to ensure that .env files, Personal Access Tokens (PATs), and local model binaries are never leaked to public version control.

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
## 📈 Use-Case Impact
## 🏢 For Organizations (Enterprise Security)
Compliance: Meets GDPR, HIPAA, and SOC2 requirements for data residency—data never leaves the local infrastructure.

IP Protection: Allows legal and R&D teams to query sensitive internal documents (contracts, codebases) without feeding them into training sets for public models.

Cost Efficiency: Eliminates recurring API costs by utilizing existing hardware for local inference.

## 👤 For Personal Use (Privacy Sovereignty)
Data Sovereignty: Full control over your "Second Brain."

Offline Reliability: Works without internet access, providing a reliable AI assistant for remote or secure environments.

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

## 👤 Author & Certification
Deloney Sime Cybersecurity Engineer | Certified Ethical Hacker (CEH) | AI Security Specialist Mission: Bridging the gap between cutting-edge AI and rigorous security protocols.
