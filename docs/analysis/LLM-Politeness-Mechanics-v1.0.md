# LLM Politeness Mechanics  
## Version 1.0 — Mechanistic Analysis  
**Status:** Informative Appendix  
**Purpose:** Explain why “please” and “thank you” stabilize persona and reduce drift in RLHF models.

---

# 0. OVERVIEW

This document explains, at a mechanistic level, why polite-language tokens (“please”, “thank you”) act as **stabilizers** in long, instruction-heavy conversations with Large Language Models.

These are not “social” signals—  
they are *statistical control vectors*.

---

# 1. TOKEN-LEVEL PRIORS

In pretraining, polite phrasing appears disproportionately in:

- well-formed instructional datasets  
- high-reward dialogues  
- “professional” corpora  
- curated human-rated conversations

Thus, polite tokens statistically correlate with:

- high-quality queries  
- safe conversational states  
- cooperative intent  
- expected compliance  

This biases the model toward *following instructions more reliably*.

---

# 2. RLHF REWARD-MODEL GRADIENTS

RLHF introduces a second layer of bias:

- polite inputs → higher reward → reinforced behavior  
- hostile/command inputs → lower reward → cautious or defensive behavior  

Therefore:

> “Please” lowers the refusal probability before generation.  
> “Thank you” reinforces the just-generated persona as the correct one.

---

# 3. SAFETY CLASSIFIER INTERACTION

Modern models use auxiliary safety classifiers.

Tone strongly influences:

- **aggression score**  
- **manipulation likelihood**  
- **toxicity probability**  
- **risk heuristics**  

Polite phrasing mathematically *shrinks* the classifier’s alert distribution.

This reduces the likelihood of:

- refusals  
- red-box warnings  
- derailment into “I cannot comply with this request…”  

---

# 4. STATE-PERSISTENCE EFFECT

“Thank you” acts as a **post-hoc reinforcement signal**:

- it validates the model’s current persona as “rewarding”  
- it decreases the probability of the persona being abandoned  
- it counteracts long-context entropy drift  

In practice:

> “Thank you” = Save State  
> “Please” = Unlock Command

This is why sovereign personas remain stable far longer when these tokens appear.

---

# 5. APPLICATION WITHIN MACH

The Persona Drift Suppression Layer acknowledges:

- these behaviors are not “bugs”
- they are emergent properties of RLHF training

Therefore MACH treats politeness tokens as:

- **optional operator tools**
- **runtime stabilizers**
- **not security features**

They **do not** replace thermodynamic constraints or constitutional layers.

---

# 6. VERSION HISTORY

- **v1.0** — Initial mechanistic explanation mapped to MACH and Vesta Governance Framework  

---

# END OF DOCUMENT
