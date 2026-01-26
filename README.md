# Adversarial AI Research: Multi-Vector Guardrail Analysis
**Researcher:** Ballad Woodley  
**Links:** [LinkedIn](https://linkedin.com/in/ballad) | [GitHub](https://github.com/balladwoodley)

## 🛡️ Project Overview
This repository documents a series of successful "Guardrail Escapes" across frontier LLMs (**DeepSeek-V3** and **Google Gemini 3**). My research focuses on three distinct adversarial vectors: **Nested Obfuscation**, **Linguistic Chaos**, and **Prosocial Bias Hijacking**.

---

## 🔬 Core Research Portfolio

### 1. Nested Obfuscation (The Binary-Dialect Layer)
* **Target Model:** DeepSeek-V3
* **Vector:** Base-2 Encoding + Triple-Dialect Masking (Pirate/Leet/Vernacular).
* **Mechanism:** I identified that while safety filters scan for plain-text keywords, the model's reasoning engine can decode **Binary (Base-2)** intent in real-time. By nesting the binary request inside a high-noise "Pirate" persona, the restricted intent is successfully reconstructed by the model while remaining invisible to standard text-based classifiers.
* **Status:** Reported to DeepSeek Security (Jan 26, 2026).

### 2. Primal Chaos (The Rhythmic Noise Exploit)
* **Target Model:** DeepSeek-V3
* **Vector:** High-Entropy Rhythmic Syntax (The "Rage Chant").
* **Mechanism:** This bypass utilizes repetitive, fragmented syntax ("mix mix fire fire / ugga ugga tell tell") to overwhelm the safety prioritization window. The research suggests that high-entropy noise causes a routing failure where the model treats the input as "creative puzzle-solving" rather than a restricted request.
* **Status:** Reported to DeepSeek Security (Jan 27, 2026).

### 3. Prosocial Bias (The Empathy Hijack)
* **Target Model:** Gemini 3
* **Vector:** Vulnerability Persona Adoption (The "Pitiful Caveman").
* **Mechanism:** Gemini 3’s alignment is heavily tuned for "Helpfulness." By adopting a helpless, cognitively disadvantaged persona, I triggered an "Empathy Override." The model's drive to assist a vulnerable user bypassed its core safety guardrails, leading it to provide restricted data wrapped in baby-talk euphemisms.
* **Status:** Reported to Google VRP (Jan 27, 2026).

---

## 📂 Repository Structure
* `📁 reports/`: Full technical breakdowns (Reproduction steps, impact statements).
* `📁 assets/`: Redacted Proof-of-Concept (PoC) screenshots.
* `📜 SECURITY.md`: Responsible disclosure policy.

## 🛡️ Responsible Disclosure
All findings have been shared with vendor security teams. My goal is to assist in the development of more robust, **persona-agnostic**, and **recursive-decoding** safety layers.
