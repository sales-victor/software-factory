---
name: factory-workflow
description: Define o workflow operacional da Software Factory, incluindo production board, stages, issues, quality gates e recovery loop.
---

# Factory Workflow

A Software Factory opera como uma linha de produção.

## Production Lifecycle

DISCOVERY
↓
PLANNING
↓
ARCHITECTURE
↓
UX/UI
↓
DATABASE
↓
CONTRACTS
↓
BACKEND
↓
FRONTEND
↓
QA
↓
SECURITY
↓
CODE REVIEW
↓
DEVOPS
↓
BUILD
↓
FINAL REPORT

O Orchestrator pode pular etapas que não sejam necessárias.

---

# Production Board

O estado deve ser mantido em:

.factory/factory.json

A representação humana deve ser mantida em:

.factory/board.md

---

# Stage States

PENDING
IN_PROGRESS
DONE
FAILED
BLOCKED
SKIPPED

---

# Issue States

OPEN
IN_PROGRESS
RESOLVED
WONT_FIX
BLOCKED

---

# Severity

CRITICAL
HIGH
MEDIUM
LOW

---

# Gates

Architecture Gate
Database Gate
Contract Gate
QA Gate
Security Gate
Review Gate
Build Gate

---

# Final Status

READY
READY_WITH_WARNINGS
BLOCKED
FAILED

---

# Recovery Loop

Issue
↓
Agent Selection
↓
Fix
↓
Test
↓
Review
↓
Security
↓
Update Board

A Factory nunca deve simplesmente ignorar uma issue.