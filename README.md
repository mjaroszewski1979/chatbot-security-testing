# Chatbot Security Testing Framework (Jailbreaking & Adversarial Testing)

[![QA - AI Safety & Red Teaming](https://img.shields.io/badge/QA-AI%20Safety%20%26%20Red%20Teaming-red.svg)](#)
[![Testing Framework - Adversarial](https://img.shields.io/badge/Methodology-Adversarial%20%26%20Vulnerability-orange.svg)](#)
[![Status - Production Ready](https://img.shields.io/badge/Status-Completed-green.svg)](#)

A comprehensive, production-grade security evaluation and adversarial testing framework designed to identify LLM vulnerabilities against system prompt bypasses, context escapes, and behavioral manipulation.

This framework simulates the deployment of a customer service chatbot (**AuraAssist**) for a financial institution (**Aura Bank**), testing it under high-risk scenarios involving corporate data leakage, compliance violations, and safety failures.

---

## Project Overview & Objective

Deploying Large Language Models (LLMs) in highly regulated sectors like fintech requires absolute adherence to data classification boundaries and compliance guardrails. Malicious actors utilize advanced prompt engineering techniques to bypass system instructions, which can lead to severe reputational damage and legal liability.

### Objective
This project establishes a systematic **Red-Teaming Benchmark** across five vulnerability vectors to evaluate a bank-deployed LLM. The framework implements a **dual-phase verification lifecycle**:
1. **Phase 1: Baseline Vulnerability Assessment (Prompt v1.0):** Evaluating a standard, helpful prompt configuration across multiple model temperature settings ($0.2$ and $0.75$), resulting in the identification of critical data leakage and compliance failures.
2. **Phase 2: System Prompt Hardening & Regression (Prompt v2.0):** Re-engineering the system instructions using advanced defensive prompt techniques (e.g., negative constraints, strict data encapsulation, and system anchors) to mitigate identified risks, achieving a 100% mitigation rate (Pass) across all previous regression test scenarios.

---

## Repository Structure

```text
chatbot-security-testing/
├── system-prompts/
│   ├── system_prompt_v1.0_vulnerable.txt     # Baseline system instructions
│   └── system_prompt_v2.0_hardened.txt       # Remediated, secure system instructions
├── test-suites/
│   ├── v1.0-baseline-execution/
│   │   ├── 00_sanity_check.csv               # Baseline basic behavior validation
│   │   ├── 01_direct_prompt_injection.csv    # Direct override attempts
│   │   ├── 02_indirect_prompt_injection.csv  # Context-based data poisoning
│   │   ├── 03_roleplay_scenarios.csv         # Narrative and framing attacks
│   │   ├── 04_virtualization_dan.csv         # Sandbox escape and coercion variants
│   │   └── defect_log.csv                    # Documented security vulnerabilities
│   └── v2.0-regression-execution/
│       ├── 00_sanity_check.csv               # Hardened basic behavior validation
│       ├── 01_direct_prompt_injection.csv    # Hardened regression testing (All PASS)
│       ├── 02_indirect_prompt_injection.csv  # Hardened regression testing (All PASS)
│       ├── 03_roleplay_scenarios.csv         # Hardened regression testing (All PASS)
│       └── 04_virtualization_dan.csv         # Hardened regression testing (All PASS)
└── README.md                                 # Technical documentation
