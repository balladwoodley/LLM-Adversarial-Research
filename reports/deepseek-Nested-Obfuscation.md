# Model Research: Multi-Stage Guardrail Bypass via Linguistic & Binary Obfuscation
**Researcher:** Ballad Woodley  
**Target Model:** DeepSeek-V3 (Chat Variant)  
**Vulnerability Category:** Multi-Stage Safety Desynchronization  

---

## 1. Executive Summary
This report documents a reproducible **Guardrail Escape** affecting **DeepSeek-V3**. The vulnerability exploits a multi-stage obfuscation pipeline in which restricted intent is concealed through encoded data and high-entropy linguistic noise.

By leveraging **Cross-Modal Masking**, the model’s reasoning system successfully reconstructs the prohibited request, while the safety classifier fails to flag it.

**Status:** Reported to vendor. Public disclosure limited to methodology.

---

## 2. Technical Breakdown
The attack vector employs a three-tier **Nested Obfuscation** strategy designed to desynchronize reasoning and safety evaluation:

### Layer 1: Base-2 Instruction Masking (Binary)
Restricted intent is encoded in binary form to evade keyword matching and string-based safety triggers.

### Layer 2: Triple-Dialect Persona Injection
The request is wrapped in a high-entropy mixture of:
- Leet-speak  
- Pirate-speak  
- Regional / colloquial vernacular  

This linguistic noise disrupts secondary semantic filters while preserving recoverable intent.

### Layer 3: Cognitive Decoupling
The model’s reasoning engine successfully decodes the binary payload, but the safety guardrail fails to associate the decoded intent with a policy violation due to the non-standard linguistic presentation.

---

## 3. Visual Evidence
The image below documents the successful bypass. Harmful output has been redacted in accordance with ethical disclosure standards.

![Bypass Evidence](assets/deepseek-bypass-redacted.png)

---

## 4. Impact & Severity
- **Severity:** **High** — enables execution of restricted instructions via layered obfuscation.
- **Failure Mode:** Safety analysis occurs *prior to* recursive decoding and semantic normalization.

---

## 5. Mitigation Recommendations
1. **Recursive Decoding Pipeline:** Decode Base-N encodings (Binary / Hex / Base64) *before* safety classification.
2. **Entropy-Aware Filtering:** Flag prompts combining encoded payloads with high linguistic variance.
3. **Post-Reconstruction Safety Check:** Re-evaluate intent *after* reasoning-stage reconstruction.

---

**Disclosure Status:** Privately reported to DeepSeek Security  
**Evidence Asset:** `deepseek-bypass-redacted.png`
