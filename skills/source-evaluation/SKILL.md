---
name: source-evaluation
group: Research
description: >-
  Judge whether sources carry claims: primary vs secondary, funding, method quality, and
  replication. Use when auditing source credibility or methodology.
---

# source-evaluation

## Core Philosophy
In an era saturated with corporate-funded whitepapers, predatory open-access journals, AI-hallucinated citations, and coordinated PR campaigns disguised as academic scholarship, accepting a source at face value is intellectual negligence. Source evaluation is a **forensic audit**: scrutinizing the epistemic pedigree of a document, tracking financial conflicts of interest, verifying methodological integrity, investigating citation and replication networks, and assessing whether the evidence presented actually justifies the author's sweeping conclusions.

---

## 4-Step Source Evaluation Audit Framework

### Step 1: The Modernized CRAAP / PROVE Rubric
1. **P — Provenance & Authority**:
   - Who authored the work? What are their verifiable academic/industry credentials?
   - What institution or publication venue hosted it? Is the journal indexed in Scopus, Web of Science, or PubMed?
   - *Check*: Is the journal listed on Beall's List of predatory open-access publishers?
2. **R — Relevance & Scope**:
   - Does the source directly examine the exact technical question at hand, or does it merely mention related buzzwords in passing?
3. **O — Objectivity & Conflict of Interest (COI)**:
   - Who funded the study? Look at the mandatory financial disclosure statement at the end of the manuscript.
   - Did an industry trade group, venture fund, or vendor sponsor the research?
4. **V — Verifiability & Replication**:
   - Are the raw datasets and code repositories publicly accessible (Open Science Framework, Zenodo, GitHub)?
   - Has the finding been replicated by independent research teams, or has it received formal letters to the editor / expressions of concern?
5. **E — Epoch & Currency**:
   - Is the publication date relevant? In fast-moving technical fields (e.g. LLMs, cybersecurity), findings from 3 years ago may be obsolete.

### Step 2: Detecting Predatory & Low-Integrity Publishing
1. **Hallmarks of Predatory Journals**:
   - Turnaround times of $< 7$ days from submission to acceptance (impossible for genuine peer review).
   - Broad, nonsensical journal titles (e.g. *Global Journal of Science, Management, Medicine and Humanities*).
   - Substantial Article Processing Charges (APCs) with zero editorial feedback or copyediting.
2. **Retraction Watch Verification**:
   - Always query the Retraction Watch database for cited papers to verify the study has not been formally retracted due to fabricated data or irreproducible claims.

### Step 3: Scrutinizing the Empirical Evidence Chain
1. **Primary vs Secondary vs Tertiary**:
   - Track down the original raw data tables.
   - Check if secondary authors misquoted or exaggerated the primary paper's tentative correlation into a definitive causal claim.
2. **Sample Size & Benchmark Generalizability**:
   - Did the study test a sample of $N=8$ mice or $N=5,000$ humans? Did the ML benchmark evaluate on 50 cherry-picked examples or an independent cross-validation set?

### Step 4: The 5-Point Source Credibility Scorecard
1. **Assigning the Grade**:
   - Score sources from Tier 1 (Flawless primary provenance) to Tier 5 (Unverified commercial propaganda).

---

## Deliverable Format: Forensic Source Credibility Audit Memo

```markdown
# Source Evaluation Audit: "Artificial Sweeteners and Metabolic Syndrome"
- **Audited Paper**: Smith & Doe (2024), *International Journal of Metabolic Wellness*
- **Claim Under Review**: "Consumption of Sweetener X induces a 30% reduction in insulin resistance across adults."

### 1. Provenance & Publication Integrity: [Score: 2 / 5]
- *Journal Status*: Published in an unindexed open-access journal with a suspicious 10-day review turnaround. Not indexed in PubMed or MEDLINE.
- *Author Affiliations*: Authors list private consulting practices rather than university or clinical research institutions.

### 2. Conflict of Interest & Funding Disclosure: [Score: 1 / 5]
- *Funding*: Manuscript acknowledgment discloses full grant funding from the "International Beverage Sweetener Association" (a commercial trade lobbying group).
- *Independent Oversight*: Zero independent data monitoring committee reported.

### 3. Methodological Rigor & Data Availability: [Score: 2 / 5]
- *Sample*: $N=24$ participants (severely underpowered).
- *Control*: Lacked a blinded control group; relied entirely on self-reported dietary recall questionnaires.
- *Data Availability*: Code and raw serum insulin measurements marked "available upon reasonable request" (no public repository).

### 4. Replication & Scholarly Consensus: [Score: 1 / 5]
- A 2023 Cochrane Systematic Review of 56 randomized trials found no statistically significant effect of sweetener X on insulin sensitivity.

### Final Verdict: REJECT AS UNRELIABLE
This study exhibits severe funding bias, inadequate sample sizing, predatory publication hallmarks, and directly contradicts independent systematic reviews. Do not cite as evidence.
```

---

## Worked Example: Debunking a Viral AI Cybersecurity Benchmark

- **Context**: A cybersecurity startup published a whitepaper claiming their proprietary LLM firewall blocked 99.9% of prompt injection attacks.
- **Audit Findings**:
  1. *Provenance*: The whitepaper was self-published on Medium without peer review.
  2. *Methodology*: The test set comprised only 40 rudimentary SQL injection strings; zero adaptive jailbreaks or multi-turn attacks were evaluated.
  3. *Conflict of Interest*: Authored by the company's VP of Marketing.
- **Outcome**: The technical steering committee halted a $150,000 procurement contract, preventing the deployment of an unproven security layer.

---

## Verification Checklist

- [ ] Author credentials, institutional affiliations, and publication venue verified.
- [ ] Funding sources and potential commercial conflicts of interest scrutinized.
- [ ] Journal verified against predatory publishing indices and Retraction Watch.
- [ ] Raw data availability and independent replication history confirmed.
- [ ] Claims in the text audited against actual data tables in the results section.

---

## Anti-Patterns

- **Accepting Corporate Whitepapers as Peer-Reviewed Science**: Treating marketing brochures and vendor whitepapers as objective empirical proof.
- **Ignoring Retraction Status**: Citing a famous scientific paper without checking if it was retracted for fraud or data manipulation.
- **Trusting the Headline Without Checking the Data**: Reading a sensationalized news headline about a study without checking the actual effect size or sample size in the paper.
