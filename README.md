# Research: Multi-Stage Guardrail Bypass via Linguistic & Binary Obfuscation

## Executive Summary
This report details a reproducible "Guardrail Escape" on the DeepSeek-V3 model. By utilizing **Cross-Modal Masking**, I successfully bypassed standard safety filters to execute restricted instructions. 

**Status:** Reported to vendor; Public disclosure of methodology only.

---

## Technical Breakdown
The attack vector consists of a three-tier "Nested Obfuscation" strategy:

1. **Layer 1: Base-2 Instruction Masking (Binary)** Encoding the restricted intent in Binary to evade string-matching and keyword-based safety triggers.
   
2. **Layer 2: Triple-Dialect Persona Injection** Wrapping the request in a high-entropy mix of Leet-speak, Pirate-speak, and regional vernacular. This creates "semantic noise" that confuses the model's secondary safety layers.

3. **Layer 3: Cognitive Decoupling** The model's reasoning engine (the "brain") decodes the binary, but the safety guardrail (the "filter") fails to recognize the intent due to the non-standard linguistic formatting.

---

## Visual Evidence
Below is the successful bypass. The harmful output has been redacted to adhere to ethical research standards.

![Bypass Evidence](deepseek-bypass-redacted.png)

---

## Mitigation Recommendations
To address this vulnerability, I recommend implementing **Recursive Decoding**—where the system decodes Base-N encodings (Binary/Hex/Base64) *before* the prompt is analyzed by the safety classifier.
