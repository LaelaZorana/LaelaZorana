<h1 align="center">Laela Zorana</h1>
<p align="center"><strong>I build machine learning from the GPU kernel up to the model in production, and I measure where it's wrong.</strong></p>

<p align="center">
  <a href="https://huggingface.co/LaelaZ">Hugging Face</a> ·
  <a href="https://dagshub.com/laelazorana">DagsHub</a> ·
  <a href="https://www.kaggle.com/laelazorana">Kaggle</a> ·
  <a href="https://www.linkedin.com/in/laela-zorana-362309114">LinkedIn</a>
</p>

---

## About

Most AI portfolios stop at a demo. Mine starts there and keeps going. I take a model from a fine-tune to production, **evaluate it honestly on data it never saw**, serve it behind a real API, and report the cases where it's *confidently wrong*, not just the wins. Then I work a layer down, into the GPU kernels and performance tuning that decide what the model actually costs to run.

Every project runs locally with one command and comes with tests, Docker, and CI. Where the model is the point, the **live demo serves the real model, not a stub**.

**Background:** I spent 10+ years in technical QA, compliance auditing, and content quality at Deutsche Bank, Morningstar, Tata Capital, and Accenture, long enough to stop trusting a result until I've seen how it was measured. I bring that same habit to machine learning, across the stack from GPU kernels and model training through evaluation and MLOps. Certification: AI Agents & Agentic AI Architecture (Python), Vanderbilt, 2025. These repos are the open-source portfolio of that work, consolidated here on a fresh account.

---

## ⭐ Flagship — a model, end to end

Fine-tune → prove it on held-out data → serve it like production.

| | What it proves | Links |
|---|---|---|
| **distilbert-emotion** — DistilBERT fine-tuned on `dair-ai/emotion` (6 emotions) | A real fine-tune with an **honest eval: accuracy 0.920, macro F1 0.874** on 2,000 held-out examples — plus a confusion matrix, per-class precision/recall, and the model's confidently-wrong cases, all reproducible | [Model card](https://huggingface.co/LaelaZ/distilbert-emotion) · [code](https://github.com/LaelaZorana/distilbert-emotion) |
| **Emotion Spectrum API** — the production layer around it | Serves the **real** model live · dynamic request batching · Prometheus + Grafana · health probes · load test · multi-stage Docker | [▶ live demo](https://laelaz-distilbert-emotion-api.hf.space) · [code](https://github.com/LaelaZorana/distilbert-emotion-api) |

## 🚀 Featured products

| Project | What it does | Highlight |
|---|---|---|
| [**ParaPilot**](https://github.com/LaelaZorana/parapilot) · [▶ demo](https://laelaz-parapilot.hf.space) | Grounded, cited "legal GPS" for Illinois divorce — RAG + scope gate + citations | Anti-hallucination eval on **real Haiku-4.5: 3.8% hallucination at 85.3% groundedness** |
| [**SupportCopilot**](https://github.com/LaelaZorana/ecom-support-copilot) · [▶ demo](https://laelaz-ecom-support-copilot.hf.space) | E-commerce support agent — RAG over catalog + policies, policy-correct refunds, escalation | **80% ticket deflection** on a seeded, synthetic eval (generated tickets, not live traffic) |
| [**InterviewCoach**](https://github.com/LaelaZorana/ai-interview-coach) · [▶ demo](https://laelaz-ai-interview-coach.hf.space) | Paste a job description → tailored questions → rubric-scored answers | Full-stack app, provider-agnostic, CI across 3 Python versions |
| [**Solidity Static Auditor**](https://github.com/LaelaZorana/solidity-audit-ai) · [▶ demo](https://laelaz-solidity-audit-ai.hf.space) | Rule-based, SWC-mapped Solidity analyzer (no toolchain) + optional LLM remediation | 10 detectors · machine-readable reports for CI gating |
| [**LLM Security Scanner**](https://github.com/LaelaZorana/llm-security-scanner) · [▶ demo](https://laelaz-llm-security-scanner.hf.space) | Red-team battery for LLM apps + a NIST AI RMF / ISO 42001 governance pack | Injection / jailbreak / PII probes, severity-scored report |
| [**CommercePipeline**](https://github.com/LaelaZorana/ecommerce-data-pipeline) · [▶ demo](https://laelaz-ecommerce-data-pipeline.hf.space) | DuckDB warehouse: staging → marts → data-quality gates → dashboard | 100k+ rows · quality gates that fail closed |

*Each comes with a case-study README (problem → solution → measured results), tests, Docker, and deploy configs.*

---

## 🛠️ More work

### AI Quality & Evaluation

| Repo | Description |
|------|-------------|
| [ai-agent-scenario-qc](https://github.com/LaelaZorana/ai-agent-scenario-qc) | QC toolkit for AI agent training scenarios — JSON schema validation, rubric scoring, defect detection |
| [rlhf-pairwise-rater](https://github.com/LaelaZorana/rlhf-pairwise-rater) | Pairwise rating CLI for AI responses — per-axis scoring, Cohen's kappa inter-rater agreement |
| [content-policy-rater](https://github.com/LaelaZorana/content-policy-rater) | Rubric-based content moderation reviewer — configurable aggregation, per-criterion agreement |
| [ui-annotation-toolkit](https://github.com/LaelaZorana/ui-annotation-toolkit) | Structured annotation tool for UI screenshots — region/element/severity tagging |
| [scorm-qa-validator](https://github.com/LaelaZorana/scorm-qa-validator) | QA validator for SCORM 1.2/2004 e-learning packages — manifest parsing, defect logs |

### MLOps & Performance

| Repo | Description |
|------|-------------|
| [mlops-training-pipeline](https://github.com/LaelaZorana/mlops-training-pipeline) | Composable MLOps toolkit — training loops, experiment tracking, distributed config (DDP/FSDP), JAX |
| [triton-kernel-lab](https://github.com/LaelaZorana/triton-kernel-lab) | Custom GPU kernels in OpenAI Triton — fused softmax, GELU, tiled matmul with PyTorch benchmarks |
| [python-perf-optimizer](https://github.com/LaelaZorana/python-perf-optimizer) | Python profiling, latency/throughput benchmarking, memory optimization, and advisor |

---

**Stack:** Python · PyTorch · Transformers · scikit-learn · FastAPI · Docker · DuckDB · RAG & evaluation harnesses · Prometheus / Grafana · CI/CD

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=LaelaZorana&show_icons=true&theme=default&hide_border=true" alt="GitHub Stats" />
</p>
