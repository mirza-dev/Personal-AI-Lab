# 🗺️ Personal AI Lab — Learning & Product Roadmap

> **Target path:** 24 weeks  
> **Flexible window:** 24–32 weeks (~6–8 months)  
> **Planned start:** 2026-10-05  
> **Rule:** A checkpoint ends when the learning objective and product deliverable are complete — not when the calendar says so.

---

## How to use this roadmap

This is not a course list.

Every checkpoint follows the same loop:

```text
LEARN
  ↓
BUILD IT INTO PERSONAL AI LAB
  ↓
TEST / MEASURE
  ↓
DOCUMENT
  ↓
COMMIT
  ↓
RELEASE WHEN A MILESTONE IS COMPLETE
```

The **24-week path** is the working target. The **32-week path** gives room for university workload, difficult concepts, debugging, and deeper experiments.

### Weekly rhythm

A sustainable default:

- **3–4 study/build sessions per week**
- **~1.5–2.5 hours per session**
- One session: learn + small exercises
- Two sessions: build into the product
- One session: test, document, review, commit

If a week is busy, reduce session count — do not skip the checkpoint.

---

# Overview

| Checkpoint | Duration | Main learning | Product outcome | Version |
|---|---:|---|---|---|
| CP00 | 1 week | Git, Python environment, project workflow | Reproducible project foundation | — |
| CP01 | 2–3 weeks | Python fundamentals | First CLI + result persistence | v0.1 |
| CP02 | 2–3 weeks | APIs, HTTP, JSON, abstractions | Multi-model benchmark engine | v0.2 |
| CP03 | 2–3 weeks | Local LLM inference, Transformers | Local model provider | v0.3 |
| CP04 | 4–5 weeks | Evaluation, datasets, statistics | Turkish AI Benchmark | v0.4 |
| CP05 | 3–4 weeks | ML, PyTorch, transformers, LoRA | First fine-tuned model + comparison | v0.5 |
| CP06 | 3–4 weeks | FastAPI, SQL, PostgreSQL | Persistent backend/API | v0.6 |
| CP07 | 2–3 weeks | Embeddings, retrieval, RAG | Personal knowledge system | v0.7 |
| CP08 | 2–3 weeks | Tool calling, agents, workflows | Agent Studio + assistant tools | v0.8 |
| CP09 | 3 weeks | Docker, tests, CI/CD, observability | Production deployment | v0.9 → v1.0 |

**Fastest total:** 24 weeks  
**Buffer ceiling:** 32 weeks

---

# CP00 — Engineering Foundation
**Target: 1 week**

## Learn
- What Git tracks: working tree, staging area, commits
- Repository / branch / commit / pull request mental model
- Python virtual environments
- Package installation
- Environment variables
- Basic terminal navigation
- Why secrets must never be committed

## Build
Create the working foundation for Personal AI Lab:

```text
src/personal_ai_lab/
tests/
docs/checkpoints/
docs/learning-log/
benchmarks/
experiments/
.env.example
.gitignore
pyproject.toml
```

Do not create empty folders merely for appearance; create them as they become useful.

## GitHub evidence
- Repository structure
- CP00 checkpoint report
- First learning log
- Meaningful small commits
- GitHub Issue for CP01

## Definition of Done
You can explain:
- what a commit is,
- why branches exist,
- what `.gitignore` does,
- how Python dependencies are isolated,
- and why API keys are loaded from environment variables.

You can clone the repository on a clean machine and understand how to start it.

## Main resources
- [Pro Git book](https://git-scm.com/book/en/v2)
- [Python virtual environments](https://docs.python.org/3/tutorial/venv.html)
- [GitHub Docs — Getting started with Git](https://docs.github.com/en/get-started/getting-started-with-git)

---

# CP01 — Python → First Working Product
**Target: 2–3 weeks**

## Learn
Use **CS50P as the main course** and immediately connect topics to the product.

Core topics:
- variables and types
- conditionals
- loops
- functions
- exceptions
- libraries / imports
- dictionaries and lists
- file I/O
- classes only when the product genuinely needs them
- basic unit testing

## Build
Create the first Personal AI Lab CLI.

Example flow:

```text
$ pal prompt
Prompt: Explain gradient descent in Turkish.

Result saved:
experiments/runs/2026-xx-xx-run-001.json
```

At first the “model” may be a simple mocked provider. The purpose is the software structure.

Implement:
- CLI input
- structured result object
- timestamps
- JSON output
- basic error handling
- configuration loading

## Test
- valid prompt
- empty prompt
- failed provider call
- result is saved correctly

## GitHub evidence
- `src/personal_ai_lab/`
- `tests/`
- checkpoint report
- learning log
- v0.1 release notes

## Definition of Done
You should be able to write the first version yourself without asking an AI to generate the entire file.

## Main resources
- [CS50P](https://cs50.harvard.edu/python/)
- [Python Tutorial](https://docs.python.org/3/tutorial/)
- [pytest — Getting Started](https://docs.pytest.org/en/stable/getting-started.html)

---

# CP02 — APIs & Multi-Model Benchmark Engine
**Target: 2–3 weeks**

## Learn
- HTTP request / response
- REST basics
- JSON serialization
- status codes
- timeouts and retries
- API authentication
- Python type hints
- interfaces / provider abstraction
- latency measurement
- token/cost metadata
- dependency boundaries

## Build

Create a provider interface:

```text
ModelProvider
├── OpenAIProvider
├── AnthropicProvider
├── GeminiProvider
└── later: LocalProvider
```

Then build:

```text
Prompt
  ↓
Benchmark Runner
  ├── Provider A
  ├── Provider B
  └── Provider C
  ↓
Normalized Result
  ↓
JSON / report
```

The important part is not how many providers you add. The important part is that the benchmark runner does not care which provider it is calling.

## Measure
For each run:
- model
- latency
- input/output token usage when available
- estimated cost when available
- success / failure
- raw output

## Test
- provider failures do not crash the full benchmark
- results have one normalized schema
- credentials are never committed
- a mock provider can test the system without API spending

## GitHub evidence
- architecture decision explaining the provider pattern
- benchmark output example
- tests
- v0.2 release

## Main resources
- [Python urllib / HTTP documentation](https://docs.python.org/3/library/urllib.html)
- Official API documentation for whichever providers are actually used
- [Python typing](https://docs.python.org/3/library/typing.html)

---

# CP03 — Local LLM Inference
**Target: 2–3 weeks**

## Learn
- tokenizer
- tokens
- context window
- model weights
- parameters
- quantization
- inference vs training
- CPU / GPU / Apple Silicon constraints
- Hugging Face model repositories
- basic Transformers workflow

## Build
Add a real local provider.

Possible first path:
- a small Qwen-family instruct model
- Transformers for learning the underlying flow
- later compare with a local runtime if useful

The goal:

```text
Benchmark Runner
   ├── API model
   └── Local model
```

Both must produce the same normalized result structure.

## Measure
- load time
- first-token latency where measurable
- total generation latency
- memory usage observation
- output quality notes

## Test
Run the same Turkish prompt set against:
- one API model
- one local model

## GitHub evidence
- local model config
- no model weights in Git
- reproducible setup instructions
- first API-vs-local benchmark report
- v0.3 release

## Main resources
- [Hugging Face LLM Course](https://huggingface.co/learn/llm-course)
- [Transformers documentation](https://huggingface.co/docs/transformers)
- [Qwen documentation](https://qwen.readthedocs.io/)

---

# CP04 — Turkish AI Benchmark & Evaluation
**Target: 4–5 weeks**

This checkpoint is what makes the project more than a chatbot clone.

## Learn
- train / validation / test separation
- benchmark leakage
- deterministic vs model-based evaluation
- exact-match / rule-based scoring
- rubric-based scoring
- LLM-as-a-judge limitations
- sampling and variance
- mean / median / distributions
- basic confidence and uncertainty thinking
- dataset versioning
- reproducibility

## Build
Create a versioned Turkish evaluation dataset.

Initial categories could include:
- instruction following
- Turkish grammar and fluency
- summarization
- information extraction
- classification
- reasoning
- ambiguity handling
- hallucination resistance
- structured JSON output
- tool-use readiness

Start small and high quality.

Example:

```text
benchmarks/
├── datasets/
│   └── tr-benchmark-v0.1.jsonl
├── configs/
├── evaluators/
└── results/
```

## Build the evaluation pipeline

```text
Dataset
   ↓
Model Runner
   ↓
Responses
   ↓
Evaluators
   ├── deterministic
   ├── rubric
   └── optional judge model
   ↓
Report
```

## Measure
Produce a report with:
- per-category score
- overall score
- latency
- failure count
- cost for API models
- qualitative examples

## Test
The same frozen dataset and config should reproduce the same deterministic parts of the evaluation.

## GitHub evidence
- benchmark dataset
- dataset card / methodology
- scoring code
- benchmark report
- limitations section
- v0.4 release

## Main resources
- [Hugging Face Evaluate](https://huggingface.co/docs/evaluate/)
- [scikit-learn model evaluation concepts](https://scikit-learn.org/stable/modules/model_evaluation.html)
- Relevant official provider evaluation guidance when a judge model is used

---

# CP05 — Machine Learning, PyTorch & LoRA Fine-Tuning
**Target: 3–4 weeks**

## Learn
Only the ML concepts needed to understand what you are doing — but understand them properly.

### Foundations
- tensors
- features / targets
- forward pass
- loss
- gradient
- backpropagation
- optimizer
- learning rate
- epochs
- batches
- train / validation
- overfitting / underfitting

### Deep learning / LLM bridge
- embeddings
- neural networks
- transformer high-level architecture
- attention intuition
- causal language modeling
- supervised fine-tuning
- LoRA
- QLoRA
- adapters
- rank
- quantization

## Build — Part A
Before touching an LLM:
- create one tiny PyTorch training example
- inspect loss decreasing
- intentionally overfit a tiny dataset
- understand what changed

## Build — Part B
Fine-tune a **small model** on a carefully prepared Turkish instruction dataset.

Hardware rule:
- local training only when the model/setup fits safely,
- otherwise use a temporary training environment,
- never hide hardware limitations behind “it should work”.

Store:
- config
- dataset version
- seed when applicable
- learning rate
- epochs
- batch settings
- LoRA parameters
- loss history

## The critical experiment
Compare:

```text
BASE MODEL
    vs
FINE-TUNED MODEL
```

using the **same frozen benchmark from CP04**.

Fine-tuning is considered useful only if evaluation supports the claim.

## GitHub evidence
- training config
- small reproducible script
- experiment report
- loss plot/data
- base-vs-tuned benchmark
- failure analysis
- v0.5 release

Do not commit large weights to normal Git.

## Main resources
- [PyTorch — Learn the Basics](https://docs.pytorch.org/tutorials/beginner/basics/)
- [Hugging Face Transformers](https://huggingface.co/docs/transformers)
- [PEFT documentation](https://huggingface.co/docs/peft/)
- [TRL SFT Trainer](https://huggingface.co/docs/trl/sft_trainer)

---

# CP06 — FastAPI, SQL & PostgreSQL
**Target: 3–4 weeks**

Now the lab stops being a collection of scripts and starts becoming a service.

## Learn

### FastAPI
- routes
- request / response models
- validation
- dependency injection basics
- async conceptually
- errors
- API documentation
- testing endpoints

### SQL / PostgreSQL
- tables
- primary / foreign keys
- SELECT / INSERT / UPDATE / DELETE
- joins
- indexes
- transactions
- schema design
- migrations concept

## Build

Convert core functions into APIs:

```text
POST /runs
GET  /runs/{id}
POST /benchmarks
GET  /benchmarks/{id}
GET  /models
```

Persist:
- benchmark runs
- model metadata
- experiment metadata
- evaluation results

## Test
- API contract tests
- validation failures
- DB persistence
- duplicate / invalid requests
- provider failure handling

## GitHub evidence
- API architecture diagram
- schema documentation
- example requests
- tests
- migration history
- v0.6 release

## Main resources
- [FastAPI Tutorial](https://fastapi.tiangolo.com/tutorial/)
- [PostgreSQL Tutorial](https://www.postgresql.org/docs/current/tutorial.html)
- [SQLAlchemy documentation](https://docs.sqlalchemy.org/)

---

# CP07 — RAG & Personal Knowledge
**Target: 2–3 weeks**

## Learn
- embeddings
- cosine similarity intuition
- chunking
- metadata
- retrieval
- top-k
- vector indexes
- retrieval precision/recall intuition
- context construction
- citations
- RAG evaluation
- why RAG and fine-tuning solve different problems

## Build
Create the Knowledge Base:

```text
Document
  ↓
Parse
  ↓
Chunk
  ↓
Embed
  ↓
Vector Store
  ↓
Retrieve
  ↓
LLM Answer + Sources
```

Start with a small, controlled document corpus.

## Test
Create questions where:
- answer exists in documents
- answer does not exist
- multiple documents conflict
- irrelevant chunks are retrieved

Track retrieval quality separately from answer quality.

## Storage
Prefer a design that can evolve toward PostgreSQL + vector search rather than introducing unnecessary infrastructure early.

## GitHub evidence
- RAG architecture
- retrieval evaluation set
- example cited answers
- failure cases
- v0.7 release

## Main resources
- [pgvector](https://github.com/pgvector/pgvector)
- [Sentence Transformers documentation](https://www.sbert.net/)
- Provider/model embedding documentation actually used in the implementation

---

# CP08 — Tool Calling, Agents & Personal Assistant
**Target: 2–3 weeks**

## Learn
- tool schemas
- structured outputs
- function/tool calling
- deterministic orchestration vs autonomous loops
- state
- memory boundaries
- retries
- planner/executor pattern
- evaluator pattern
- multi-agent trade-offs
- permissions and safety boundaries

## Build

Start **without** multi-agent complexity.

### Stage 1 — Tool-calling assistant
Give the assistant a small set of safe tools:
- calculator
- local knowledge retrieval
- benchmark lookup
- selected internal APIs

### Stage 2 — Workflow
Create a controlled workflow such as:

```text
User Request
   ↓
Router
   ↓
Retrieve / Tool
   ↓
Model
   ↓
Evaluator
   ↓
Response
```

### Stage 3 — Multi-agent experiment
Only after the single-agent/workflow baseline works, test whether separate planner/evaluator roles actually improve a measurable outcome.

## Test
Evaluate:
- tool selection accuracy
- invalid arguments
- repeated tool loops
- hallucinated tools
- task completion rate
- latency overhead

## GitHub evidence
- tool schemas
- workflow diagram
- evaluation set
- baseline vs agentic comparison
- v0.8 release

## Main resources
Use the official tool-calling documentation for the model provider actually implemented. Avoid adopting an agent framework before understanding the underlying loop.

---

# CP09 — Docker, CI/CD, Observability & Production
**Target: 3 weeks**

## Learn
- image vs container
- Dockerfile
- layers
- volumes
- networking
- Docker Compose
- environment configuration
- production vs development config
- health checks
- logs
- metrics
- CI
- CD
- deployment environments
- basic security practices

## Build

Containerize:

```text
API
PostgreSQL
optional model service
```

with Docker Compose for development.

Add GitHub Actions:

```text
push / pull request
       ↓
lint
       ↓
tests
       ↓
build
       ↓
deployment checks
```

Add observability for at least:
- request count
- error count
- model latency
- benchmark latency
- provider failures
- token/cost metadata when available

## Production gate

v1.0 is only reached when:

- [ ] clean installation path exists
- [ ] secrets are externalized
- [ ] tests run automatically
- [ ] API starts from documented commands
- [ ] database migrations are reproducible
- [ ] Docker build succeeds
- [ ] CI passes
- [ ] errors are logged
- [ ] core model calls are observable
- [ ] benchmark can compare base/local/fine-tuned configurations
- [ ] RAG answers can show sources
- [ ] agent tools are bounded and tested
- [ ] README contains screenshots / architecture / setup
- [ ] limitations are documented

## Main resources
- [Docker — Get Started](https://docs.docker.com/get-started/)
- [GitHub Actions documentation](https://docs.github.com/en/actions)
- [FastAPI deployment concepts](https://fastapi.tiangolo.com/deployment/)

---

# Version milestones

```text
CP00  Engineering foundation
 ↓
v0.1  Python CLI
 ↓
v0.2  Multi-model benchmark
 ↓
v0.3  Local LLM
 ↓
v0.4  Turkish AI Benchmark
 ↓
v0.5  Fine-tuning
 ↓
v0.6  API + PostgreSQL
 ↓
v0.7  RAG
 ↓
v0.8  Agents
 ↓
v0.9  Production infrastructure
 ↓
v1.0  Personal AI Lab
```

---

# GitHub workflow for every checkpoint

Every checkpoint should normally have:

1. **Issue**
   - goal
   - learn
   - build
   - definition of done

2. **Branch**
   ```bash
   checkpoint/XX-short-name
   ```

3. **Small commits**
   Examples:
   ```text
   feat: add benchmark result schema
   test: cover provider timeout
   docs: record benchmark architecture
   ```

4. **Checkpoint report**
   ```text
   docs/checkpoints/CPXX-name.md
   ```

5. **Learning log**
   What was learned and where it was used in the product.

6. **Pull request / review**
   Explain what changed and why.

7. **Release**
   Only when a product milestone is reached.

---

# AI assistant rule

AI is allowed to:
- explain
- give hints
- review code
- identify bugs
- propose tests
- compare approaches
- challenge architectural decisions

AI should not silently replace the learning process.

> **If I cannot explain the code, I do not merge it.**

For difficult tasks, ask the AI to teach in layers:

```text
1. Explain the concept.
2. Give me a small exercise.
3. Review my attempt.
4. Give hints before giving the full solution.
5. Connect it to Personal AI Lab.
```

---

# How we know the roadmap is working

At the end of the journey, the repository should show more than a final application.

It should show the engineering story:

```text
Python
→ APIs
→ model abstraction
→ local inference
→ evaluation
→ ML / PyTorch
→ fine-tuning
→ backend / database
→ RAG
→ agents
→ Docker
→ CI/CD
→ production
```

The Git history itself becomes part of the portfolio.
