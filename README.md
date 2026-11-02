# ProcessMirror AI

> Hybrid AI Consulting Platform for Process Discovery, Process Documentation, Tool Mapping, Automation Assessment and Initial ROI Estimation

## From employee knowledge to decision-ready process intelligence

Organizations cannot improve work they cannot see. ProcessMirror AI turns structured employee interviews into validated process documentation and visualizations, then helps teams assess automation opportunities and initial savings and ROI scenarios.

Leaders get a clearer view of how work is performed, which systems and roles are involved, and where bottlenecks or improvement opportunities may exist. The workflow establishes and validates the current state before assessing what to improve—giving consultants, executives and teams a shared basis for the next decision.

For hiring teams, the interactive demos and end-to-end workflow make the product's functional scope easy to explore at a glance.

### See the platform in action

[Open the interactive employee interview demo](https://daniel-prokop.github.io/ProcessMirrorAI/ProcessMirror_AI_SAVI_Interviewformular_Multiprozess.html) · [Open the interactive executive assessment report](https://daniel-prokop.github.io/ProcessMirrorAI/ProcessMirror_AI_SAVI_Abschlussbericht_Demo-GmbH.html)

![Employee interview portal preview](./eingabeformular%20screenshot.png)

![Executive assessment report preview](./report%20screenshot.png)

The sections below provide the platform's technical documentation, including its capabilities, data flow, workflows and architecture.

---

## Executive Summary

Organizations often struggle to improve or automate processes because operational knowledge is fragmented, undocumented or exists only in employees' heads.

ProcessMirror AI addresses this challenge through a governed workflow that captures employee knowledge, validates it through human review and transforms it into actionable process intelligence.

The platform automatically produces:

- Process Documentation
- Process Diagrams
- Tool Mappings
- Automation Opportunities
- Savings Scenarios
- Initial ROI Estimations
- Executive Reports

while maintaining a controlled approval process throughout the workflow.

---

## Key Capabilities

✅ Employee-driven process discovery

✅ Human-reviewed process validation

✅ Automated process documentation

✅ Automated process diagram generation

✅ Tool and integration mapping

✅ Automation opportunity identification

✅ Cross-process analysis

✅ Bottleneck detection

✅ Initial ROI estimation and savings scenarios

✅ Executive reporting

✅ Deterministic governance and approval workflows

✅ AI-assisted consulting workflows

✅ Pseudonymized LLM processing

---

# Privacy-Aware Data Flow

ProcessMirror AI uses n8n guardrails to prepare process data before it is sent to an LLM. These guardrails detect and filter personally identifiable information (PII) and secret keys, then pseudonymize values before each LLM call.

After LLM processing, n8n uses the mappings to restore the corresponding values in a controlled workflow step. This describes the implemented data flow; it is not a claim of regulatory compliance, certification or absolute protection.

## Data Protection Workflow

```text
Employee Input
        ↓
PII Detection and Filtering
        ↓
Secret Key Detection and Filtering
        ↓
Pseudonymization before each LLM call
        ↓
AI Processing
        ↓
LLM Result
        ↓
Controlled Re-Identification by n8n
        ↓
Business Report
```

### PII Filtering and Pseudonymization

Detected personal information is filtered and values are replaced with pseudonyms before LLM processing. For example:

```text
John Doe
      ↓
PERSON_01
```

### Secret Key Filtering

The n8n guardrails detect and filter secret keys before the data is sent to an LLM. The LLM input is therefore pseudonymized rather than containing the original values handled by these guardrails.

### LLM Processing and Re-Identification

The Discovery Agent and Assessment Agent receive pseudonymized values. After processing, n8n uses the mappings to re-identify corresponding values in the result and restore business context for downstream reporting. Re-identification takes place outside the LLM processing step.

This enables:

- Employee-specific process documentation
- Department mappings
- Ownership information
- Company-level reporting
- Executive assessments

without sending the original values to the LLM as part of the described flow.

The workflow includes:

- Data Minimization
- Pseudonymization
- Human Review
- Controlled Re-Identification
- Explainable AI Workflows
- Human-in-the-Loop Governance

---

# Solution Architecture

ProcessMirror AI consists of three coordinated workflows.

```text
┌─────────────────────────────────────────────┐
│ 00 MASTER ORCHESTRATOR                      │
│ Campaigns · Governance · Reporting          │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│ 01 DISCOVERY AGENT                          │
│ Process Discovery                           │
│ Gap Detection                               │
│ Diagram Generation                          │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│ 02 ASSESSMENT AGENT                         │
│ Tool Mapping                                │
│ Automation Discovery                        │
│ ROI Assessment                              │
└─────────────────────────────────────────────┘
```

---

# Complete Workflow Landscape

![Master Workflow](process%20mirror%20ai%2000%20master%20workflow%20screenshot.png)

The Master Orchestrator coordinates the complete lifecycle from the initial consultant request to the final executive report.

---

# Discovery Agent

![Discovery Agent](process%20mirror%20ai%2001%20discovery%20agent%20screenshot.png)

The Discovery Agent transforms employee knowledge into structured, reviewable and reusable process intelligence.

Its primary objective is understanding the current state of operations before any optimization is proposed.

---

# Assessment Agent

![Assessment Agent](process%20mirror%20ai%2002%20assessment%20agent%20screenshot.png)

The Assessment Agent evaluates approved process knowledge and generates automation opportunities, tool recommendations and savings assessments based on documented evidence.

---

# User Experience

In addition to the workflow architecture, ProcessMirror AI provides dedicated user-facing interfaces for process discovery and assessment review.

The interfaces are intentionally provided in German because the platform was designed for German organizations, operational process consulting and German-speaking business environments.

---

# Employee Interview Portal

![Employee Interview Portal](eingabeformular%20screenshot.png)

The employee interview portal serves as the primary entry point into ProcessMirror AI.

Employees document process knowledge, responsibilities, systems, bottlenecks and improvement opportunities through a structured interview experience.

The interview can be transformed into:

- Process Documentation
- Process Diagrams
- Tool Mappings
- Automation Opportunities
- Savings Scenarios
- Initial ROI Estimations

### Interactive Version

The complete interactive interview experience is available in:

**ProcessMirror_AI_SAVI_Interviewformular_Multiprozess.html**

### Why is the interview form in German?

ProcessMirror AI was designed for German organizations and operational consulting scenarios.

Business terminology, process descriptions and employee interviews often require precise wording and compliance-sensitive communication.

For that reason, the interview experience is intentionally provided in German.

---

# Executive Assessment Report

![Executive Assessment Report](report%20screenshot.png)

After all process information has been reviewed and validated, ProcessMirror AI generates a consultant-style executive report.

The report consolidates:

- Process Documentation
- Process Diagrams
- Tool Mappings
- Automation Opportunities
- Savings Scenarios
- Initial ROI Estimations
- Strategic Recommendations

### Interactive Version

The complete interactive assessment report is available in:

**ProcessMirror_AI_SAVI_Abschlussbericht_Demo-GmbH.html**

### Why is the assessment report in German?

The generated report targets German decision-makers, department managers and consultants.

Business terminology, recommendations and operational assessments are therefore provided in German to maximize clarity and practical applicability.

---

# Workflow 00 — Master Orchestrator

The Master Workflow acts as the central control layer of ProcessMirror AI.

It coordinates communication, governance, approvals, AI interactions and reporting activities.

## Responsibilities

- Campaign creation
- Employee onboarding
- Interview management
- Approval workflows
- Governance enforcement
- Knowledge aggregation
- Workflow orchestration
- ROI calculations
- Report generation
- Report delivery

## End-to-End Business Flow

```text
Consultant Request
        │
        ▼
Campaign Creation
        │
        ▼
Employee Interviews
        │
        ▼
AI Process Discovery
        │
        ▼
Employee Validation
        │
        ▼
Consultant Approval
        │
        ▼
Automation Assessment
        │
        ▼
ROI Estimation
        │
        ▼
Executive Report
```

---

# Workflow 01 — Discovery Agent

The Discovery Agent acts as a digital process analyst.

Its purpose is to understand how work is actually performed inside an organization and transform unstructured employee knowledge into structured process documentation.

## Core Responsibilities

### Process Discovery

Extracts:

- Activities
- Inputs
- Outputs
- Systems
- Roles
- Responsibilities
- Dependencies

### Gap Detection

Identifies:

- Missing information
- Incomplete descriptions
- Unknown responsibilities
- Missing system references

### Clarification Support

Generates targeted follow-up questions whenever documentation quality is insufficient.

### Diagram Generation

Produces:

- Process Documentation
- Process Models
- Mermaid Diagrams
- Visual Process Flows

## Discovery Principles

The Discovery Agent should:

✅ ask questions

✅ document uncertainties

✅ identify knowledge gaps

✅ structure information

The Discovery Agent should never:

❌ invent process steps

❌ invent systems

❌ invent stakeholders

❌ invent business rules

❌ invent metrics

---

# Workflow 02 — Automation Assessment Agent

The Assessment Agent evaluates validated process knowledge and identifies realistic optimization opportunities.

Unlike the Discovery Agent, its objective is not understanding the process.

Its objective is improving the process.

## Core Responsibilities

### Automation Opportunity Discovery

Identifies:

- Repetitive activities
- Manual transfers
- Approval bottlenecks
- Duplicate work
- Delays
- Integration opportunities

### Tool Mapping

Links opportunities to suitable technology and implementation approaches.

### Savings Assessment

Evaluates:

- Potential effort reductions
- Time-saving opportunities
- Efficiency improvements

### Initial ROI Estimation

Creates rough ROI scenarios based on documented process metrics.

Examples include:

- Estimated hours saved per month
- Estimated hours saved per year
- Estimated labor cost reductions
- Estimated financial impact ranges

ROI figures are intentionally presented as preliminary estimations rather than guaranteed business outcomes.

## Connected Assessment Tools

### Find Automatable Activities

Identifies automation-friendly process steps.

### Validate Opportunity Mapping

Ensures recommendations can be traced back to documented process evidence.

### Check Savings Assumptions

Validates assumptions behind estimated efficiency gains.

### Public Integration Research

Researches publicly available tools, integrations and implementation options.

---

# Human-in-the-Loop Governance

```text
Employee Interview
        ↓
AI Discovery
        ↓
Employee Validation
        ↓
Consultant Approval
        ↓
Automation Assessment
        ↓
ROI Estimation
        ↓
Executive Report
```

Many process improvement initiatives attempt to automate processes before they fully understand them. ProcessMirror AI reverses that sequence:

```text
Understand
      ↓
Validate
      ↓
Assess
      ↓
Estimate ROI
      ↓
Improve
```

The result is a process intelligence workflow that combines deterministic governance, pseudonymized LLM processing and human review.

---

# Technology Stack

- n8n
- Deterministic Workflow Orchestration
- Multi-Agent Architecture
- Human-in-the-Loop Governance
- Process Discovery
- Process Analysis
- Process Diagram Generation
- Tool Mapping
- Automation Assessment
- ROI Estimation
- HTML Reporting

---

# Repository Contents

```text
├── README.md
│
├── ProcessMirror_AI_SAVI_Interviewformular_Multiprozess.html
├── ProcessMirror_AI_SAVI_Abschlussbericht_Demo-GmbH.html
├── processmirror-social-preview.png
│
├── eingabeformular screenshot.png
├── report screenshot.png
│
├── process mirror ai 00 master workflow screenshot.png
├── process mirror ai 01 discovery agent screenshot.png
└── process mirror ai 02 assessment agent screenshot.png
```

---

# Project Vision

ProcessMirror AI bridges the gap between employee knowledge, process consulting and intelligent automation.

By combining deterministic workflows, AI agents, privacy-aware processing, governance controls and human validation, organizations can transform operational knowledge into actionable automation initiatives while maintaining transparency, traceability and trust.
