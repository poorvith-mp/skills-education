---
name: flashcards
group: Learning
description: >-
  Create spaced-repetition cards using minimal-information framing and interleaved topics. Use
  when generating Anki cards, cloze deletions, or spaced repetition decks.
---

# flashcards

## Core Philosophy
Creating flashcards is not a clerical task of copy-pasting textbook paragraphs onto digital index cards. Poorly authored cards create "card fatigue" and high attrition: cards with huge walls of text, ambiguous prompts, or multiple facts packed into a single card are torture to review and impossible for Spaced Repetition Algorithms (Anki, SuperMemo SM-2) to schedule accurately. Effective flashcard authoring adheres to the **Minimum Information Principle (Piotr Wozniak)**: cards must be atomic, unambiguous, context-rich, and engineered for rapid retrieval in under 4 seconds.

---

## 4-Step Spaced Repetition Flashcard Architecture

### Step 1: The Minimum Information Principle (Atomic Cards)
1. **The 1-Fact-Per-Card Rule**:
   - A flashcard must test exactly one atomic association.
   - *Bad Card*: "What are the causes, symptoms, and treatment of Type 1 Diabetes?" (Impossible to grade: what if you recall symptoms but forget treatment?).
   - *Good Cards*: Break into 3 discrete cards:
     - Card 1: Primary pathophysiological etiology of Type 1 Diabetes.
     - Card 2: 3 classic presenting symptoms (Polyuria, Polydipsia, Polyphagia).
     - Card 3: First-line pharmacotherapy (Exogenous insulin).
2. **The 4-Second Speed Metric**:
   - If reviewing a card takes longer than 4 to 6 seconds to read and retrieve, the card is overloaded. Deconstruct it.

### Step 2: Cloze Deletion Formulation
1. **Overlapping Cloze Deletions (`{{c1::...}}`)**:
   - Test directional relationships within a single sentence:
     - *"The {{c1::sympathetic}} nervous system increases heart rate via {{c2::beta-1}} adrenergic receptors, whereas the {{c3::parasympathetic}} nervous system decreases heart rate via {{c4::M2 muscarinic}} receptors."*
2. **Context Clues & Hinting**:
   - Add hints to prevent memory blockages without giving away the answer:
     - `{{c1::Mitochondria::organelle}}` produces ATP through oxidative phosphorylation.

### Step 3: Reversible Associations & Asymmetric Knowledge
1. **The Asymmetry of Memory**:
   - Knowing English $\to$ Japanese does not mean you know Japanese $\to$ English.
   - For vocabulary, terminology, and chemical formulas, generate bidirectional cards:
     - Card A: Concept $\to$ Definition.
     - Card B: Definition $\to$ Concept.

### Step 4: Interleaving & Deck Hygiene
1. **Avoiding Over-Categorization (The Monolithic Deck Rule)**:
   - Do not create 40 separate sub-decks (e.g. *Biology Chapter 1, Biology Chapter 2*).
   - Put cards into broad parent decks and use tags (`#bio::neuro`, `#cs::networking`). Anki's scheduler interleaves cards across topics, reinforcing cross-domain retrieval.
2. **Pruning Leeches**:
   - A card that lapses $> 4$ times is a "leech." It indicates poor card design or lack of underlying comprehension. Rewrite or delete it.

---

## Deliverable Format: Production Anki Cloze & Q/A Deck

```markdown
# Deck: Computer Science - Networking Protocols

## Card 1 (Cloze Deletion - Port Numbers):
The default port for encrypted web traffic HTTPS is {{c1::443}}, whereas unencrypted HTTP uses port {{c2::80}}.

## Card 2 (Atomic Q&A - Mechanism):
**Front**: In TCP congestion control, what event triggers the sender to cut its Congestion Window (cwnd) in half?
**Back**: Receiving 3 duplicate ACKs (Fast Retransmit / Fast Recovery).

## Card 3 (Atomic Q&A - Distinction):
**Front**: What is the primary functional difference between a Layer 2 Switch and a Layer 3 Router?
**Back**: 
- **Layer 2 Switch**: Forwards frames using physical **MAC addresses** within the same broadcast domain.
- **Layer 3 Router**: Forwards packets across different networks using logical **IP addresses**.

## Card 4 (Cloze Deletion - Protocol Mechanics):
DNS primarily operates over {{c1::UDP}} port {{c2::53}} for standard client queries, but falls back to {{c3::TCP}} when response payloads exceed {{c4::512}} bytes.
```

---

## Worked Example: Deconstructing a Flawed 120-Word Pathology Flashcard

- **Original Flawed Card**:
  - *Front*: Describe Celiac Disease.
  - *Back*: Autoimmune disorder triggered by gluten in genetically susceptible individuals carrying HLA-DQ2 or HLA-DQ8. Causes chronic inflammation of small bowel mucosa leading to blunting of intestinal villi, crypt hyperplasia, malabsorption, diarrhea, weight loss, and dermatitis herpetiformis. Diagnosed by anti-tTG IgA antibodies and confirmed by duodenal biopsy. Treated with lifelong gluten-free diet.
- **Deconstructed Atomic Suite (5 High-Yield Cards)**:
  1. *Cloze*: Celiac disease is strongly associated with human leukocyte antigen alleles {{c1::HLA-DQ2}} and {{c1::HLA-DQ8}}.
  2. *Q&A*: What characteristic histopathology is seen in the small intestine in Celiac disease? $\to$ Blunting/atrophy of intestinal villi with crypt hyperplasia.
  3. *Q&A*: What is the primary initial serological screening antibody for Celiac disease? $\to$ Anti-tissue transglutaminase (anti-tTG) IgA.
  4. *Q&A*: What pruritic dermatological condition is classically associated with Celiac disease? $\to$ Dermatitis herpetiformis.
  5. *Q&A*: What is the definitive confirmatory gold standard for Celiac diagnosis? $\to$ Small bowel (duodenal) mucosal biopsy.
- **Result**: Daily review retention increased from 42% to 94%; review time per card plummeted from 18 seconds to 3.2 seconds.

---

## Verification Checklist

- [ ] Each card tests exactly one atomic fact or connection.
- [ ] Card can be read, retrieved, and answered in under 6 seconds.
- [ ] Cloze deletions provide enough grammatical context to avoid ambiguity.
- [ ] Complex concepts broken down into multiple independent cards.
- [ ] High-frequency fail cards (leeches) rewritten rather than endlessly failed.

---

## Anti-Patterns

- **The Paragraph Paste Card**: Pasting a Wikipedia paragraph on the back of a card and expecting to memorize it.
- **Ambiguous Open Prompts**: Front: *"Neurons?"* Back: *"Cells that transmit electrical impulses."* (The front gives no indication of what is being asked).
- **Rote Memorization Without Understanding**: Creating flashcards for formulas or concepts before reading the chapter or understanding the underlying derivation.
