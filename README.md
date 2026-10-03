<div align="center">

# 🧠 Personal AI Lab

### Learn AI engineering by building one real product from first principles to production.

[![Status](https://img.shields.io/badge/status-planning-6c63ff?style=for-the-badge)](#-current-status)
[![Roadmap](https://img.shields.io/badge/roadmap-32_weeks-0ea5e9?style=for-the-badge)](ROADMAP.md)
[![Python](https://img.shields.io/badge/Python-3.12+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-TBD-lightgrey?style=for-the-badge)](#)

**Local & API LLMs · Turkish Evaluation · Fine-tuning · RAG · Agents · FastAPI · PostgreSQL · Docker · CI/CD**

</div>

---

## ✨ What is Personal AI Lab?

**Personal AI Lab** is a long-term learning-and-building project.

The goal is not to finish courses first and build something later. Every concept is learned **when the product needs it**, then immediately implemented, tested, documented and committed.

By v1.0, the platform is intended to support:

- 🤖 API and local LLM providers
- ⚔️ Side-by-side model comparison
- 🇹🇷 A custom Turkish AI benchmark
- 🧪 Dataset and experiment tracking
- 🔧 LoRA / QLoRA fine-tuning workflows
- 📚 RAG over personal documents
- 🛠️ Tool-calling and agent workflows
- 📊 Evaluation, latency and cost observability
- 🌐 FastAPI backend + database
- 🐳 Dockerized deployment
- ⚙️ CI/CD and production checks
- 🧑‍💻 A personal assistant built on top of the lab

---

## 🎯 The Learning Rule

> **Learn → Build → Test → Measure → Document → Commit**

A checkpoint is **not complete** just because I watched a lesson or wrote code.

Each checkpoint must leave evidence in this repository:

- working code,
- tests or measurable output,
- a short technical write-up,
- meaningful commits,
- and a clear connection to the final product.

---

## 🗺️ Product Map

```text
Personal AI Lab
│
├── Model Arena
│   ├── API models
│   └── Local models
│
├── Dataset Studio
│   ├── clean
│   ├── inspect
│   └── split
│
├── Fine-tuning Studio
│   ├── LoRA
│   └── QLoRA
│
├── Turkish AI Benchmark
│   ├── quality
│   ├── instruction following
│   ├── hallucination
│   ├── latency
│   └── cost
│
├── Knowledge Base
│   ├── embeddings
│   ├── vector search
│   └── RAG
│
├── Agent Studio
│   ├── tools
│   ├── workflows
│   └── multi-agent experiments
│
├── Personal Assistant
│
└── Production Layer
    ├── FastAPI
    ├── PostgreSQL
    ├── tests
    ├── Docker
    ├── CI/CD
    └── monitoring
```

---

## 🧭 Current Status

**Phase:** Planning  
**Current checkpoint:** CP00 — Engineering Foundation  
**Target:** v1.0 in approximately **32 weeks / 8 months** at a sustainable student pace.

The detailed learning path, resources, deliverables and definition of done live in **[ROADMAP.md](ROADMAP.md)**.

---

## 📦 Planned Repository Structure

```text
Personal-AI-Lab/
│
├── README.md
├── ROADMAP.md
├── LEARNING.md
├── CHANGELOG.md
│
├── src/
│   └── personal_ai_lab/
├── tests/
├── benchmarks/
│   ├── datasets/
│   ├── configs/
│   └── results/
├── experiments/
├── docs/
│   ├── checkpoints/
│   ├── learning-log/
│   └── decisions/
├── .github/
│   └── workflows/
├── .env.example
├── .gitignore
└── pyproject.toml
```

Folders will be created **when they become necessary**, not as empty decoration.

---

## 🧪 Checkpoint Philosophy

Every checkpoint answers five questions:

1. **What do I need to learn?**
2. **Why does the product need it?**
3. **What exactly will I build with it?**
4. **How will I prove that it works?**
5. **What evidence will be committed to GitHub?**

Detailed checkpoint reports will live under:

```text
docs/checkpoints/
```

---

## 🧑‍🏫 AI-assisted Learning Policy

AI tools are used as **teachers, reviewers and pair programmers**, not as a replacement for understanding.

A simple rule:

> If I cannot explain the code, I do not merge it into the main branch.

---

## 🔐 Security Rule

Secrets never belong in Git history.

The repository may contain:

- `.env.example`
- public benchmark datasets
- configs
- metrics
- reproducible experiment metadata

It must **never** contain:

- API keys
- passwords
- private personal data
- production credentials
- large model weights

---

## 🏁 Planned Milestones

| Version | Milestone |
|---|---|
| `v0.1` | Python + CLI foundation |
| `v0.2` | Multi-model benchmark engine |
| `v0.3` | Local LLM support |
| `v0.4` | Turkish benchmark |
| `v0.5` | ML foundations + LoRA fine-tuning |
| `v0.6` | FastAPI + PostgreSQL backend |
| `v0.7` | RAG knowledge system |
| `v0.8` | Tool calling + agents |
| `v0.9` | Docker + CI/CD + observability |
| `v1.0` | Production-ready Personal AI Lab |

---

<div align="center">

### 🚧 Built in public, checkpoint by checkpoint.

*The Git history is part of the portfolio.*

</div>
