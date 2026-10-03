# Personal AI Lab

> A project I’m building to learn how modern language-model systems work from the ground up — by turning each topic I learn into part of one real product.

[Roadmap](ROADMAP.md) · Current stage: **Planning / CP00** · Target: **24–32 weeks**

---

## About the project

I did not want to learn Python, APIs, machine learning, fine-tuning, RAG, agents and deployment as disconnected subjects.

So I decided to build one project that grows with me.

Personal AI Lab starts small: a command-line program that can send a prompt to a model and save the result. From there, it gradually becomes a platform where I can compare models, run local models, build my own Turkish evaluation set, fine-tune smaller models, work with personal documents, add tools and workflows, and finally deploy the whole system.

The point is not only to reach the final product.

I want the repository to keep a record of **how I got there**.

---

## How I’m learning

The basic rule for the project is:

```text
Learn → Build → Test → Measure → Document → Commit
```

I try to learn a concept when the project actually needs it.

For example:

- I learn Python by building the first CLI and benchmark code.
- I learn APIs while adding model providers.
- I learn evaluation while building a Turkish benchmark.
- I learn PyTorch and ML concepts before fine-tuning.
- I learn databases when experiment history needs persistence.
- I learn RAG when the assistant needs to work with documents.
- I learn Docker when the application needs to run outside my laptop.

A checkpoint is complete only when I can explain what I built and show that it works.

---

## What I want to build

The final version should let me do things like:

- run both local and API-based language models,
- compare the same prompt across models,
- measure latency, failures and cost where available,
- evaluate models with a custom Turkish benchmark,
- prepare datasets and run LoRA / QLoRA experiments,
- compare base and fine-tuned models,
- search and answer from personal documents,
- give models tools and controlled workflows,
- keep experiment history in a database,
- expose the system through an API,
- and run it as a containerized production application.

The personal assistant will eventually sit on top of these pieces rather than being the first thing I build.

---

## Project evolution

```text
CLI
 │
 ├── Model providers
 │     ├── API models
 │     └── Local models
 │
 ├── Benchmarking & evaluation
 │     └── Turkish benchmark
 │
 ├── Machine learning
 │     └── Fine-tuning experiments
 │
 ├── Backend & database
 │
 ├── Personal knowledge / RAG
 │
 ├── Tools & agent workflows
 │
 └── Docker, CI/CD and production
```

---

## Roadmap

The working target is **24 weeks**, with room to extend the plan to **32 weeks** when university workload or harder checkpoints require more time.

The roadmap is checkpoint-based rather than calendar-based. I do not move forward just because a week ended.

| Milestone | Outcome |
|---|---|
| `v0.1` | Python + first CLI |
| `v0.2` | Multi-model benchmark engine |
| `v0.3` | Local model support |
| `v0.4` | Turkish evaluation benchmark |
| `v0.5` | ML foundations + first fine-tuning experiment |
| `v0.6` | FastAPI + PostgreSQL backend |
| `v0.7` | Personal knowledge / RAG |
| `v0.8` | Tools and agent workflows |
| `v0.9` | Docker, testing, CI/CD and observability |
| `v1.0` | Production version of Personal AI Lab |

The detailed plan, learning topics, resources and completion criteria are in **[ROADMAP.md](ROADMAP.md)**.

---

## Repository philosophy

This repository is also my learning log.

I want the Git history to show:

- what I learned,
- what I built with it,
- what failed,
- what I changed,
- what I measured,
- and why I made certain technical decisions.

Over time the repository will include:

```text
src/                 application code
tests/               automated tests
benchmarks/          datasets, configs and results
experiments/         reproducible experiments
docs/checkpoints/    checkpoint write-ups
docs/learning-log/   learning notes
docs/decisions/      technical decisions
```

I will add structure when it becomes useful rather than filling the repository with empty folders on day one.

---

## A rule for using coding assistants

I use coding assistants as teachers, reviewers and pair programmers.

My rule is simple:

> **If I cannot explain the code, I do not merge it.**

That means I would rather ask for an explanation, hint or code review first than generate an entire feature I do not understand.

---

## Security

Secrets, personal data and large model files do not belong in this repository.

API keys and credentials will stay in local environment variables or deployment secrets. The repository will only contain examples such as `.env.example`.

---

## Current status

**Checkpoint:** CP00 — Engineering Foundation  
**Status:** Planning  
**Next:** repository setup, Git workflow, Python environment and the first small program

---

This project will change a lot as I learn.

That is part of the point.
