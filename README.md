<h1 align="center">Laela Zorana</h1>
<p align="center"><strong>I make frontier multimodal and embodied models cheap to train and fast to run, from the GPU kernel up to the model on the robot, and I measure where it breaks.</strong></p>

<p align="center">
  <a href="https://huggingface.co/LaelaZ">Hugging Face</a> ·
  <a href="https://www.kaggle.com/laelazorana">Kaggle</a> ·
  <a href="https://www.linkedin.com/in/laela-zorana-362309114">LinkedIn</a> ·
  <a href="https://dagshub.com/laelazorana">DagsHub</a>
</p>

---

## About

Most AI work stops at the notebook. Mine goes a layer down, into the kernels, quantization, and distributed training that decide what a model actually costs to run, and then onto the hardware it has to run on. I write custom GPU kernels in Triton and CUDA, quantize models to fit a latency and power budget, and run distributed training in PyTorch and JAX. Lately I've been pushing that same efficiency work into vision-language-action models and reinforcement post-training, the part of robotics where every millisecond of inference is a millisecond the arm is standing still.

Every project runs locally with one command and comes with tests, CI, and real measurements. When I report a speedup I put the baseline right next to it, and when a lever doesn't pay off I publish that too, because knowing where it isn't is half the job.

**Background:** a decade of model validation and risk work in regulated environments, including a bank's Chief Risk Office, which is where I learned not to trust a result until I've seen how it was measured. I bring that same habit to the systems layer now, across kernels, training, and inference. Certified in AI Agents and Agentic AI Architecture in Python (Vanderbilt, 2025).

---

## ⭐ Flagship: embodied-efficiency

**Making frontier embodied and multimodal models cheap to run and safe to deploy.** A VLA folds laundry in a lab demo, then stalls on the actual robot, because end-to-end inference runs at 3 to 5 Hz and a robot arm needs 50 to 100 Hz. That gap is an engineering problem, and this repo measures the levers that close it on a real batch-1 VLA flow-matching sampler, with correctness and no-leak checks gating every number.

| | What it shows | Links |
|---|---|---|
| **CUDA-graph sampler** | manual graph capture of the N-step flow loop runs **5.9x over eager** (4.82 to 0.82 ms/step on a T4), beats torch.compile, replays exactly, leaks zero memory | [repo](https://github.com/LaelaZorana/embodied-efficiency) · [thesis](https://github.com/LaelaZorana/embodied-efficiency/blob/main/THESIS.md) |
| **Weight-only low-bit, reported as a negative** | four experiments showing int4/int8 here's a memory-footprint lever (int8 2x, int4 4x smaller, under 5% action error), not a batch-1 latency win, on T4 and L4 | [results](https://github.com/LaelaZorana/embodied-efficiency/blob/main/kernel/RESULTS.md) |

---

## 🚀 Systems and performance

| Project | What it's |
|---|---|
| [**triton-kernel-lab**](https://github.com/LaelaZorana/triton-kernel-lab) | Custom GPU kernels in Triton: a fused single-pass softmax (about 2x a PyTorch baseline), a tiled matmul against cuBLAS, fused activations, with a pytest suite |
| [**mlops-training-pipeline**](https://github.com/LaelaZorana/mlops-training-pipeline) | Composable training toolkit: PyTorch and JAX trainers, experiment tracking, distributed config (DDP/FSDP) with per-device memory estimation |
| [**python-perf-optimizer**](https://github.com/LaelaZorana/python-perf-optimizer) | Profiling, latency and throughput benchmarking, memory and leak tracking, with a severity-tagged optimization advisor |

**Competitions (Kaggle):** fine-tuned **Nemotron-3-Nano-30B** with a LoRA adapter served under vLLM, **banked 0.84**; **NeuroGolf**, building the smallest ONNX graphs that solve ARC-AGI tasks exactly under a hard parameter budget; **ARC Prize 2026**, a hierarchical program-induction solver.

---

## 🧩 Applied AI, end to end

Fine-tune, prove it on data it never saw, serve it like production.

| Project | What it does | Measured |
|---|---|---|
| [**distilbert-emotion**](https://github.com/LaelaZorana/distilbert-emotion) · [API](https://github.com/LaelaZorana/distilbert-emotion-api) · [▶ demo](https://laelaz-distilbert-emotion-api.hf.space) | DistilBERT fine-tuned on `dair-ai/emotion`, then served behind a real API | accuracy **0.920**, macro F1 **0.874** on 2,000 held-out examples, plus the confidently-wrong cases; live API with dynamic batching, Prometheus and Grafana, load test, multi-stage Docker |
| [**ParaPilot**](https://github.com/LaelaZorana/parapilot) · [▶ demo](https://laelaz-parapilot.hf.space) | Grounded, cited legal GPS for Illinois divorce: RAG plus a scope gate and citations | anti-hallucination eval on real Haiku-4.5: **3.8% hallucination at 85.3% groundedness** |
| [**SupportCopilot**](https://github.com/LaelaZorana/ecom-support-copilot) · [▶ demo](https://laelaz-ecom-support-copilot.hf.space) | E-commerce support agent: RAG over catalog and policies, policy-correct refunds, escalation | **80% ticket deflection** on a seeded synthetic eval (generated tickets, not live traffic) |
| [**InterviewCoach**](https://github.com/LaelaZorana/ai-interview-coach) · [▶ demo](https://laelaz-ai-interview-coach.hf.space) | Paste a job description, get tailored questions and rubric-scored answers | full-stack, provider-agnostic, CI across 3 Python versions |
| [**Solidity Static Auditor**](https://github.com/LaelaZorana/solidity-audit-ai) · [▶ demo](https://laelaz-solidity-audit-ai.hf.space) | Rule-based, SWC-mapped Solidity analyzer plus optional LLM remediation | 10 detectors, machine-readable reports for CI gating |
| [**LLM Security Scanner**](https://github.com/LaelaZorana/llm-security-scanner) · [▶ demo](https://laelaz-llm-security-scanner.hf.space) | Red-team battery for LLM apps plus a NIST AI RMF / ISO 42001 governance pack | injection, jailbreak, and PII probes, severity-scored report |
| [**CommercePipeline**](https://github.com/LaelaZorana/ecommerce-data-pipeline) · [▶ demo](https://laelaz-ecommerce-data-pipeline.hf.space) | DuckDB warehouse: staging, marts, data-quality gates, dashboard | 100k+ rows, quality gates that fail closed |

---

## 🔎 Validation and oversight

The rigor layer, kept where it belongs: checking my own systems, not as the headline.

| Repo | What it's |
|------|-------------|
| [ai-agent-scenario-qc](https://github.com/LaelaZorana/ai-agent-scenario-qc) | Oversight harness for autonomous-agent training scenarios: schema validation, rubric scoring, semantic defect detection |
| [rlhf-pairwise-rater](https://github.com/LaelaZorana/rlhf-pairwise-rater) | Pairwise rating CLI for model responses: per-axis scoring, Cohen's kappa inter-rater agreement |
| [content-policy-rater](https://github.com/LaelaZorana/content-policy-rater) | Rubric-based content reviewer: configurable aggregation, per-criterion agreement |
| [scorm-qa-validator](https://github.com/LaelaZorana/scorm-qa-validator) | Validator for SCORM 1.2/2004 packages: manifest parsing, defect logs |

---

**Stack:** Python · PyTorch · JAX · Triton · CUDA · Transformers · FastAPI · Docker · DuckDB · RAG and evaluation harnesses · Prometheus / Grafana · CI/CD

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=LaelaZorana&show_icons=true&theme=default&hide_border=true" alt="GitHub Stats" />
</p>
