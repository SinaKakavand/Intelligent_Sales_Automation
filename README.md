# Intelligent Sales Automation

<p align="center">
  <strong>Turning Sales Conversations into Actionable Intelligence.</strong>
  <br />
  AI Engineering · LLMs · RAG · Workflow Automation
</p>

<p align="center">
  <img src="https://img.shields.io/badge/AI-Engineering-7C3AED?style=flat-square" alt="AI Engineering" />
  <img src="https://img.shields.io/badge/LLM-Powered-2563EB?style=flat-square" alt="LLM Powered" />
  <img src="https://img.shields.io/badge/RAG-Context--Aware-0D9488?style=flat-square" alt="RAG" />
  <img src="https://img.shields.io/badge/Orchestration-n8n-EA580C?style=flat-square" alt="n8n" />
</p>

---

## Overview

Sales calls contain valuable information about customer needs, objections, buying signals, and sales performance. But reviewing conversations one by one makes it difficult to turn that information into consistent, actionable insights.

**Intelligent Sales Automation** uses AI and automated workflows to turn sales conversations into structured intelligence that supports better decisions.

The project has two complementary systems:

- **System 2 — Per-Call Intelligence:** Analyzes individual sales calls and extracts useful insights from each conversation.
- **System 1 — Daily Sales Intelligence:** Brings call-level information together to highlight broader patterns, recurring objections, and potential opportunities.
- **Shared RAG Layer:** Provides relevant business context to support both types of analysis.

The goal is simple: move beyond call summaries and make sales conversations more useful at both the individual and team levels.

## At a Glance

| Area | What it does |
|---|---|
| Call analysis | Turns individual conversations into structured insights |
| Daily intelligence | Highlights patterns across multiple calls |
| Shared knowledge | Adds relevant business context through RAG |
| Audio resilience | Tested with noisy, low-quality recordings at a 6 kHz sample rate |
| Data privacy | Uses masking layers to help protect sensitive customer information |
| Automation | Coordinates processing through n8n workflows |

---

## Architecture

The diagrams below explain how the two systems fit together, how each analysis path works, and where privacy and reliability considerations come into play.

They show the system at a conceptual level. Proprietary workflow logic, internal configuration, and sensitive integration details are intentionally excluded.

### 01. System Architecture

The two systems address different questions: *What happened in this call?* and *What are we learning from all our calls?* Both draw on a shared knowledge layer for business context.

**[Keep your existing System Architecture Mermaid diagram here.]**

### 02. System 2 — Per-Call Intelligence

System 2 focuses on one conversation at a time. It takes a call recording through the analysis process and produces structured insights that can help with follow-up and sales decisions.

**[Keep your existing System 2 Mermaid diagram here.]**

### 03. System 1 — Daily Sales Intelligence

System 1 looks at the bigger picture. It brings together information from individual calls to help identify recurring objections, performance patterns, and opportunities that may not be obvious from a single conversation.

Quantitative aggregation and AI interpretation serve different purposes: validated data provides the numerical foundation, while AI helps interpret the results and explain meaningful patterns.

**[Keep your existing System 1 Mermaid diagram here.]**

### 04. Privacy & Reliability

Customer data protection and reliable execution are important considerations throughout an AI workflow. This diagram illustrates the intended approach to input validation, sensitive-data masking, output checks, exception handling, and monitoring.

**[Keep your existing Privacy & Reliability Mermaid diagram here.]**

These diagrams describe the design at a high level. They are not a claim that every control operates identically across every processing path.

---

## Workflow Architecture

The following screenshots show the n8n workflows behind the two systems. They provide a practical view of the workflow structure alongside the conceptual architecture above.

### System 1 — Daily Sales Intelligence

![System 1 — n8n workflow](https://github.com/SinaKakavand/Intelligent_Sales_Automation/blob/main/Screenshots_workflow/System1%20-%20N8N%20workflow.jpg?raw=true)

*Daily analysis across aggregated sales-call data.*

### System 2 — Per-Call Intelligence

![System 2 — n8n workflow](https://github.com/SinaKakavand/Intelligent_Sales_Automation/blob/main/Screenshots_workflow/System2%20-%20N8N%20workflow.jpg?raw=true)

*Analysis of individual sales conversations.*

---

## Demo — Real Sales Call Analysis

This example pairs a sample outbound sales call with its corresponding AI-generated analysis report.

**Scenario:** Scenario 5 — Outbound Call — Good Salesperson  
**Call date:** October 7, 2026

| Resource | Description |
|---|---|
| [Read the Analysis Report (PDF)](https://github.com/SinaKakavand/Intelligent_Sales_Automation/blob/main/Demo/Call%20Intelligence%20-%20Scenario%205%20-%20Outbound%20Call%20-%20Good%20Salesperson%20-%202026-10-07.pdf) | See the resulting call intelligence report |
| [Listen to the Sample Call (WAV)](https://github.com/SinaKakavand/Intelligent_Sales_Automation/blob/main/Demo/Scenario%205%20-%20Outbound%20Call%20-%20Good%20Salesperson.wav) | Listen to the audio used in the demonstration |

The example illustrates how a sales conversation can be transformed into structured information for review and follow-up. It represents one scenario, not a comprehensive performance benchmark.

---

## Engineering Highlights

### 1. Handling Low-Quality Audio

Sales recordings are not always clean. Background noise, limited bandwidth, and recording quality can all affect downstream analysis.

During testing, the workflow successfully processed noisy, low-quality audio files with a **6 kHz sample rate**. This demonstrates that the tested workflow can handle conditions beyond ideal recordings, although results may vary with different audio, languages, and transcription models.

### 2. Privacy-Aware Processing

Sales conversations may contain personal and commercially sensitive information. The system includes **masking layers for sensitive customer information** to reduce unnecessary exposure during processing.

Masking is one part of a broader privacy approach. Secure credentials, access controls, appropriate data retention, and careful handling of model inputs and outputs remain important.

### 3. Shared Knowledge Through RAG

Both systems use a shared retrieval layer to bring relevant business knowledge into their analysis. This helps connect individual conversations and daily sales patterns to a common business context.

### 4. Separating Metrics from Interpretation

Daily sales intelligence combines quantitative aggregation with AI-based interpretation. Where possible, metrics should come from validated source data, while the language model focuses on explaining patterns and generating higher-level insights.

### 5. Workflow-Based Automation

The project uses n8n to coordinate the processing steps. The public repository focuses on the architecture, design decisions, demonstrations, and selected engineering considerations rather than exposing the complete proprietary implementation.

---

## Repository Contents

The repository includes the README and supporting materials:

- `Demo/` — sample call recordings and analysis reports.
- `Screenshots_workflow/` — screenshots of the n8n workflows.
- `Docs/` — project documentation, including the [Project Proposal (PDF)](Docs/Proposal%20for%20Intelligent_Sales_Automation.pdf).

All conceptual architecture diagrams are embedded directly in this README using Mermaid. No separate diagram files are required.

---

## Scope & Transparency

This repository is an **AI Engineering Case Study**, not a public release of the complete production workflow.

It presents the project's architecture, analytical approach, selected workflow screenshots, and demonstration materials while keeping proprietary implementation details private.

The architecture diagrams are conceptual, and the audio-resilience result applies to the scenarios tested. Neither should be interpreted as a guarantee of production performance under all conditions.

---

## Future Directions

Potential next steps include:

- Evaluating analysis and transcription quality across a wider range of audio conditions.
- Adding regression tests for prompts and structured outputs.
- Measuring retrieval quality and contextual grounding.
- Tracking processing latency, cost, and failure rates.
- Further evaluating privacy controls and data-handling boundaries.
- Incorporating human review for uncertain or high-impact findings.

---

## Technology Focus

`n8n` · `LLMs` · `Retrieval-Augmented Generation` · `AI Engineering` · `Sales Analytics` · `Workflow Automation` · `Data Privacy` · `Reliability`

---

<p align="center">
  <strong>Intelligent Sales Automation</strong>
  <br />
  Turning Sales Conversations into Actionable Intelligence.
</p>
