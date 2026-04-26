# SpecDraft Lab

> Speculative decoding workbench with CUDA profiling and acceptance analysis

## 1. Project Overview

**SpecDraft Lab** is a GitHub-ready project idea focused on **speculative decoding, draft-verifier pipelines, low-latency generation, GPU profiling**.

Speculative decoding can reduce generation latency, but its real gain depends on draft-model quality, acceptance rate, and verification overhead. This project provides a reproducible lab to measure that tradeoff in detail.

**Target area:** CUDA / vLLM inference systems  
**Primary users:** LLM inference teams, performance engineers, applied research groups

---

## 2. Why This Project Matters

This project is strong for the job market because it demonstrates more than model training. It shows the ability to think across:

- model design
- optimization and quantization or systems tuning
- runtime constraints
- reproducible benchmarking
- product-style engineering and evaluation


---

## 3. Core Features

- Baseline vs speculative decoding benchmarks
- Draft-model acceptance-rate analysis
- Nsight-based GPU profiling for prefill and decode phases
- Prompt-category comparison for where speculation helps most
- Report generator with speedup and overhead breakdown

---

## 4. Proposed System Architecture

1. Prompt workload is divided into task families
2. Baseline and speculative pipelines run side-by-side
3. Telemetry records acceptance rate, extra verification cost, and latency
4. Profiler traces GPU execution patterns
5. Analysis summarizes net gain by workload type

---

## 5. Recommended Tech Stack

- Python experiment runner
- vLLM or compatible speculative decoding setup
- CUDA profiling tools
- Notebook/reporting layer
- Optional lightweight draft models for controlled experiments


---

## 6. Data / Workload Ideas

Instruction prompts, coding prompts, summarization tasks, and long-generation prompts.

For a strong repository, keep one **small reproducible benchmark set** in the repo and document how the larger benchmark was prepared. That makes the project easier for others to run and review.

---

## 7. Milestone Plan

### Phase 1
Set up baseline serving benchmark

### Phase 2
Integrate draft + verifier workflow

### Phase 3
Add acceptance and overhead telemetry

### Phase 4
Run workload-specific experiments

### Phase 5
Publish guidance for when to enable speculation

### Final Deliverable
A working demo, a benchmark report, and clear ablations showing what changed performance or accuracy.

---

## 8. Evaluation Metrics

- Inter-token latency
- End-to-end generation time
- Acceptance rate
- Extra verifier cost
- Net speedup by prompt family


---

## 9. Suggested Repository Structure

```text
specdraft-lab/
├── README.md
├── app/ or src/
├── models/
├── scripts/
├── configs/
├── notebooks/ or reports/
├── benchmarks/
├── assets/
└── docs/
```


---

