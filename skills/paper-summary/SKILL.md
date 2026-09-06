---
name: paper-summary
group: Research
description: Summarise a paper into methodology, findings, and limitations. For study design, see research-methods. Use when distilling academic papers into findings, methods, and limitations.
---

# paper-summary

## Core Philosophy
Summarizing an academic paper is not an exercise in paraphrasing the authors' abstract. The abstract is marketing copy designed to get a paper accepted into a conference; it routinely exaggerates novelty and buries critical caveats in the appendix. A professional paper summary is an **analytical teardown**: dissecting the exact research hypothesis, scrutinizing the methodology and empirical controls, assessing the statistical validity of the findings, exposing the unstated threats to validity, and extracting the concrete practical implications for engineers and researchers.

---

## 4-Step Paper Dissection Architecture

### Step 1: Research Question & Theoretical Anchoring
1. **Core Problem Statement**:
   - What fundamental question does the paper attempt to answer?
   - What existing paradigm or consensus does it challenge?
2. **The Core Thesis / Hypothesis**:
   - State the central claim in 1 to 2 precise, testable sentences.

### Step 2: Methodology, Sampling & Experimental Controls
1. **The Experimental Architecture**:
   - Sample size $N$, dataset provenance, and baseline benchmarks:
     - Were the baselines state-of-the-art, or did the authors compare against obsolete or handicapped models?
2. **Control Hygiene**:
   - How were confounding variables controlled? (e.g. compute budget parity, identical prompt formatting, double-blind human rating protocols).

### Step 3: Quantitative Findings & Statistical Rigor
1. **Effect Size vs $p$-Value Significance**:
   - Look beyond $p < 0.05$. What was the actual practical magnitude (Cohen's $d$, percentage gain over competitive baselines)?
2. **Variance and Robustness**:
   - Did the authors report standard deviation across multiple random seeds, or just cherry-pick the best single run?

### Step 4: Critical Limitations & Practical Implications
1. **Threats to Internal & External Validity**:
   - *Internal*: Did the benchmark dataset contaminate the pre-training corpus?
   - *External*: Does this technique work on noisy real-world enterprise data, or only on pristine synthetic benchmarks?
2. **Operational Takeaway**:
   - What should an engineering team or researcher do differently on Monday morning based on this paper?

---

## Deliverable Format: Structured Research Paper Teardown Memo

```markdown
# Research Teardown: DeepSeek-R1 (Incentivizing Reasoning Capability via RL)
- **Authors**: DeepSeek-AI (Guo et al., 2025)
- **Venue**: ArXiv Preprint / Technical Report

### 1. Research Question & Core Thesis
- **Question**: Can pure Large-Scale Reinforcement Learning (RL) induce sophisticated reasoning and chain-of-thought capabilities without requiring massive supervised fine-tuning (SFT) cold starts?
- **Hypothesis**: Direct reward modeling on verifiable rule-based outcomes (math accuracy and compiler verification) is sufficient for base language models to autonomously discover reflection, backtracking, and verification behaviors.

### 2. Methodology & Instrumentation
- **Architecture**: DeepSeek-V3-Base (671B parameter Mixture-of-Experts with 37B active parameters).
- **Training Pipeline**:
  - *DeepSeek-R1-Zero*: Pure RL applied directly to base model using GRPO (Group Relative Policy Optimization) with zero SFT data.
  - *DeepSeek-R1*: Multi-stage pipeline incorporating cold-start reasoning data $\to$ reasoning RL $\to$ rejection sampling SFT $\to$ general RL.
- **Reward Signal**: Rule-based accuracy rewards (exact string matches for math, unit test execution for code) + formatting constraint rewards. Zero neural reward models for reasoning steps.

### 3. Key Quantitative Findings
- **AIME 2024 Math**: Surpassed OpenAI o1-preview, achieving 79.8% Pass@1 (compared to 79.2% for o1-preview).
- **MATH-500**: Scored 97.3%, matching o1-0912.
- **Codeforces**: Achieved an ELO rating of 2029 (top 96th percentile of human competitors).
- **Emergent Behaviors**: R1-Zero exhibited autonomous "aha moments"—self-correction, step reallocation, and alternative exploration without human imitation.

### 4. Critical Methodological Limitations
- **Language Consistency**: R1-Zero suffered from severe language mixing (switching between Chinese and English midway through a proof).
- **Verifiable Reward Dependency**: The technique depends heavily on domains with deterministic ground truth (math, unit tests). Generalizing pure RL to ambiguous subjective domains (creative writing, legal analysis) remains unproven.
- **Distillation Dominance**: Distilling R1 reasoning tokens into small dense models (Qwen-7B/32B) yielded massive leaps, demonstrating that small models need token-level guidance rather than pure discovery.

### 5. Practical Engineering Implications
- Engineering teams can bypass costly human SFT data generation for deterministic tasks by using outcome-based rule verifiers.
- Small 14B-32B models distilled from large reasoning traces can achieve near-frontier math/code competence at a fraction of inference cost.
```

---

## Worked Example: Unmasking Methodological Flaws in a Disputed ML Paper

- **Paper Claim**: A 2023 paper claimed a novel 7B parameter model outperformed GPT-4 on medical licensing exam questions by 12%.
- **Forensic Summary Teardown**:
  1. *Scrutinized Section 4.1 (Evaluation)*: Discovered that 35% of the USMLE test questions were verbatim duplicates of public sample questions found in the model's GitHub training repository.
  2. *Control Analysis*: Baseline GPT-4 was evaluated zero-shot with rigid JSON formatting constraints, while the 7B model was allowed 5-shot CoT with flexible regex parsing.
- **Outcome**: The summary prevented an enterprise healthcare client from investing $250,000 into deploying an overfitted, contaminated model in production.

---

## Verification Checklist

- [ ] Core research question and testable hypothesis extracted explicitly.
- [ ] Sample sizes, baseline comparisons, and control mechanisms evaluated.
- [ ] Statistical significance separated from practical effect size.
- [ ] Internal and external threats to validity identified beyond authors' concessions.
- [ ] Actionable, real-world engineering or scientific implications articulated.

---

## Anti-Patterns

- **Abstract Paraphrasing**: Copying the paper's abstract and conclusion without reading the methodology and results tables.
- **Ignoring the Appendix**: Missing critical hyperparameter details, negative results, or sample exclusions buried in the supplementary material.
- **Assuming Correlation is Causation**: Reporting observational correlations as definitive causal mechanisms.
