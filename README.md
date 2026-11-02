# ProcessMirror AI

> Human-Validated Process Discovery and Automation Assessment Platform

ProcessMirror AI is an AI-supported workflow intelligence platform built on n8n.

The platform captures operational knowledge directly from employees, transforms it into structured process documentation, validates the results through human review, and finally identifies realistic automation opportunities.

The guiding principle is simple:

**No automation recommendation without a validated understanding of the current process.**

---

# Architecture Overview

The solution is built around three coordinated workflows:

```text
┌────────────────────────────────────┐
│ 00 MASTER ORCHESTRATOR             │
│ Campaigns · Reviews · Reporting    │
└───────────────┬────────────────────┘
                │
                ▼
┌────────────────────────────────────┐
│ 01 DISCOVERY AGENT                 │
│ Process Understanding              │
│ Clarification Questions            │
│ Diagram Generation                 │
└───────────────┬────────────────────┘
                │
                ▼
┌────────────────────────────────────┐
│ 02 ASSESSMENT AGENT                │
│ Automation Opportunities           │
│ Savings Validation                 │
│ Integration Research               │
└────────────────────────────────────┘
```

---

# Complete Workflow Landscape

process%20mirror%20ai%2000%20master%20workflow%20screenshot.png

The Master Orchestrator controls the complete lifecycle from initial process intake to final company-wide reporting.

---

# Discovery Agent

process%20mirror%20ai%2001%20discovery%20agent%20screenshot.png

The Discovery Agent focuses on understanding how work is actually performed.

The objective is not automation.

The objective is to create a reliable and reviewable representation of reality.

---

# Assessment Agent

process%20mirror%20ai%2002%20assessment%20agent%20screenshot.png

The Assessment Agent operates only on approved process knowledge and identifies realistic optimization opportunities.

It does not create process documentation.

It evaluates validated process documentation.

---

# Workflow 00 — Master Orchestrator

The Master Workflow serves as the central control layer of ProcessMirror AI.

Responsibilities include:

- campaign creation
- employee onboarding
- invitation distribution
- interview coordination
- approval workflows
- document management
- process aggregation
- assessment orchestration
- final reporting

---

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
Process Discovery
        │
        ▼
Employee Validation
        │
        ▼
Consultant Approval
        │
        ▼
Company Assessment
        │
        ▼
HTML Report Generation
        │
        ▼
Delivery & Archival
```

---

## Major Functional Areas

### Kickoff

A consultant initiates a process assessment campaign.

The workflow validates the request and creates the required data structures.

### Invitations

Employees receive individual and secure process interview links.

Each employee contributes process knowledge relevant to the assessment.

### Discovery

Process information is submitted to the Discovery Agent.

The Discovery Agent analyses the workflow and detects missing information.

### Human Review

Employees review the generated process description and diagrams.

Only approved process knowledge can move forward.

### Consultant Approval

A consultant validates the approved process documentation.

This creates an additional governance layer.

### Assessment

Approved process packages are consolidated and submitted to the Automation Assessment Agent.

### Reporting

The platform generates structured reports and automation recommendations.

Results can be archived and distributed automatically.

---

# Workflow 01 — Discovery Agent

The Discovery Agent is responsible for understanding operational processes.

It transforms interview input into structured process knowledge.

---

## Goals

- understand what actually happens
- identify process steps
- identify systems
- identify responsibilities
- identify bottlenecks
- identify missing information
- generate reviewable documentation

---

## What the Agent Does

### Input Validation

Only approved and privacy-cleared inputs are accepted.

### Process Reconstruction

The agent rebuilds:

- process flow
- tasks
- participants
- systems
- inputs
- outputs
- decision points

### Clarification Questions

If information is missing, targeted follow-up questions are generated.

Examples:

- unknown system
- unclear responsibility
- incomplete process step
- missing business rule

### Diagram Generation

The workflow creates:

- written process descriptions
- process structure
- Mermaid diagrams
- rendered diagrams

---

## Discovery Principles

The agent should:

✅ ask questions

✅ document uncertainty

✅ identify information gaps

✅ structure process knowledge

The agent should never:

❌ invent process steps

❌ invent systems

❌ invent responsibilities

❌ invent business rules

---

## Discovery Output

Returned to the Master Workflow:

- process analysis
- process structure
- follow-up questions
- process diagram
- review status

---

# Workflow 02 — Automation Assessment Agent

The Assessment Agent analyzes approved process knowledge.

The goal is to discover realistic opportunities for optimization and automation.

---

## Core Responsibilities

### Opportunity Discovery

Identify:

- repetitive work
- manual transfers
- duplicate effort
- bottlenecks
- approval delays
- integration opportunities

### Validation

Ensure recommendations can be traced back to actual process information.

### Assessment

Evaluate:

- expected impact
- implementation complexity
- operational risks
- potential constraints

---

# Multi-Tool Assessment Approach

The Assessment Agent utilizes specialized tools.

### Find Automatable Activities

Identifies process steps that may be suitable for automation.

### Validate Opportunity Mapping

Ensures opportunities are linked to documented process steps.

### Check Savings Assumptions

Validates assumptions behind time-saving estimates.

### Public Integration Research

Optionally researches public integration and automation capabilities.

---

# Human-in-the-Loop Governance

Human review is a mandatory part of the architecture.

```text
Employee
    │
    ▼
Process Approval
    │
    ▼
Consultant Validation
    │
    ▼
Automation Assessment
    │
    ▼
Final Report
```

Recommendations are only generated after process knowledge has passed the review chain.

---

# Design Principles

### Traceability

Every recommendation should be connected to actual process evidence.

### Explainability

Outputs should be understandable and reviewable.

### Human Oversight

Critical transitions require human approval.

### Privacy First

Only approved and sanitized information should reach agents.

### Modular Architecture

Each workflow focuses on a single responsibility:

- Workflow 00 → Orchestration
- Workflow 01 → Process Discovery
- Workflow 02 → Opportunity Assessment

---

# Technology Stack

- n8n
- AI Agents
- Human-in-the-Loop Governance
- Process Discovery
- Workflow Assessment
- Diagram Generation
- HTML Reporting
- Email Automation
- Structured Knowledge Capture

---

# Repository Structure

```text
ProcessMirror-AI/
│
├── workflows/
│   ├── 00-master-workflow.json
│   ├── 01-discovery-agent.json
│   └── 02-assessment-agent.json
│
├── screenshots/
│   ├── process mirror ai 00 master workflow screenshot.png
│   ├── process mirror ai 01 discovery agent screenshot.png
│   └── process mirror ai 02 assessment agent screenshot.png
│
└── README.md
```

---

# Current Architecture

The implementation consists of three coordinated workflows:

1. Master Orchestrator
2. Discovery Agent
3. Automation Assessment Agent

Together they provide a complete process intelligence pipeline from process capture to validated automation recommendations while maintaining human oversight at critical decision points.
