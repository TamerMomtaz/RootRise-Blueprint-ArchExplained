# RootRise Infrastructure Blueprint v1.1 — Quick Reference

**For Ahmed El-Gazzar | January 2026**

---

## 🎯 What We're Building

An AI-powered SME diagnostic platform with:
- **11 Agents** (The Pantheon)
- **15 Lenses** (The &Eye)
- **31 Sectors** (My Sector)
- **6 Countries** (EG, SA, AE, JO, LB, MA)

---

## 🏛️ The Pantheon (11 Agents)

### Core Agents (Always Run)
| Agent | Role | Dimensions |
|-------|------|------------|
| **Drucker** | Orchestrator | 1, 11 |
| **Marvin** | Operations | 1, 3, 4, 7, 8 |
| **Graham** | Finance | 2, 1, 11 |

### Add-On Agents (User Selects)
| Agent | Role | Dimensions |
|-------|------|------------|
| **Ricardo** | Export | 9, 10, 4, 11 |
| **Lovelace** | Digital | 6, 3, 7 |
| **Mayo** | HR | 7, 1, 11 |
| **Ohno** | Supply Chain | 8, 3, 6, 7 |
| **Porter** | Market | 5, 1, 2, 11 |
| **Landor** | Packaging | 10, 9, 11 |

### Utility Agents (Always Run)
| Agent | Role | Dimensions |
|-------|------|------------|
| **Deming** | Quality Validation | All (1-11) |
| **Tufte** | Report Generation | All (1-11) |

---

## 👁️ The &Eye (15 Lenses)

| ID | Lens | Primary Agent |
|----|------|---------------|
| EYE-001 | Export Readiness | Ricardo |
| EYE-002 | Investment Readiness | Graham |
| EYE-003 | Digital Transformation | Lovelace |
| EYE-004 | Operational Excellence | Marvin |
| EYE-005 | Market Expansion | Porter |
| EYE-006 | Brand Building | Landor |
| EYE-007 | Workforce Development | Mayo |
| EYE-008 | Supply Chain Optimization | Ohno |
| EYE-009 | Sustainability & ESG | Marvin |
| EYE-010 | Innovation & R&D | Lovelace |
| EYE-011 | Customer Experience | Porter |
| EYE-012 | Cost Optimization | Graham |
| EYE-013 | Risk & Resilience | Marvin |
| EYE-014 | Succession & Governance | Graham |
| EYE-015 | Partnership & M&A | Graham |

---

## 📊 My Sector (31 Sectors)

### Legacy v2.0 (16)
Agriculture, Automotive, Chemicals, Construction, Education, Financial, Healthcare, Hospitality, Logistics, Metal, Pharmaceuticals, Professional, Real Estate, Retail, Technology, Textiles

### New v1.0 (15)
Beauty & Wellness, Creative Industries, Electronics Manufacturing, Energy & Utilities, Environmental Services, Filling & Bottling, Food & Beverage Manufacturing, Furniture Manufacturing, Home-Based & Micro, Maintenance & Repair, Paper & Printing, Plastics Manufacturing, Security Services, Telecommunications, Trading & Distribution

**Total: 31 sectors | 2.6 MB | ~60,000 lines**

---

## 📋 Questionnaire (10 Sections, ~145 Questions)

| Section | Code | Questions | Time | Required |
|---------|------|-----------|------|----------|
| Business Profile | BP | 15 | 3 min | Always |
| Financial Health | FH | 20 | 5 min | Always |
| Operations | OP | 17 | 4 min | Always |
| Digital Maturity | DM | 12 | 3 min | If Lovelace |
| Workforce | WF | 11 | 3 min | If Mayo |
| Market | MK | 10 | 2 min | If Porter |
| Supply Chain | SC | 12 | 3 min | If Ohno |
| Export | EX | 15 | 4 min | If Ricardo |
| Brand | BR | 10 | 2 min | If Landor |
| Compliance | CC | 8 | 2 min | Contextual |
| **Core** | - | **53** | **12 min** | - |
| **Full** | - | **~145** | **31 min** | - |

---

## 🚦 HITL Gates (4 Checkpoints)

| Gate | Triggers When | Handler |
|------|---------------|---------|
| **Gate 1** | Coverage < 70%, inconsistencies | Embedded Associate |
| **Gate 2** | Confidence < 70%, cross-agent conflict | Senior Expert |
| **Gate 3** | Recommendations > $50K | Senior Expert |
| **Gate 4** | Always (final review) | SME Owner |

---

## 🔧 Technology Stack

| Layer | Technology |
|-------|------------|
| API | FastAPI |
| Orchestration | LangGraph |
| Session Store | Redis (24h TTL) |
| Database | PostgreSQL |
| Vector DB | Qdrant |
| Object Store | S3 |
| LLM | OpenAI GPT-4o |

---

## 🔑 Key API Endpoints

### Diagnostic Flow
```
POST /diagnostic/initiate
POST /diagnostic/{id}/respond
GET  /diagnostic/{id}/status
GET  /diagnostic/{id}/report
```

### &I Override
```
POST /diagnostic/{id}/pause
POST /diagnostic/{id}/override
POST /diagnostic/{id}/inject-context
```

### &I Transparency
```
GET /diagnostic/{id}/reasoning
GET /diagnostic/{id}/confidence-map
GET /diagnostic/{id}/sources
GET /diagnostic/{id}/explain/{finding}
```

---

## 📐 11-Dimension Framework

| # | Dimension | Primary Users |
|---|-----------|---------------|
| 1 | Industry Classification | Drucker, All |
| 2 | Financial Benchmarks | Graham |
| 3 | Operational KPIs | Marvin, Ohno |
| 4 | Regulatory Landscape | Marvin, Ricardo |
| 5 | Competitive Dynamics | Porter |
| 6 | Digital Maturity | Lovelace |
| 7 | Workforce Norms | Mayo |
| 8 | Supply Chain | Ohno |
| 9 | Export Requirements | Ricardo |
| 10 | Packaging & Labeling | Landor |
| 11 | MENA Regional Context | All |

**PLUS (v2.0 Enhancements):**
- 5-Stage Growth Pathways
- Key Financial Insights
- Strategic Summary (success factors, failure patterns, red flags)

---

## 💰 Cost Estimates (100 diagnostics/month)

| Category | Monthly |
|----------|---------|
| Compute | $370-670 |
| APIs | $270 |
| **Total** | **~$640-940** |

---

## 📅 Timeline (24 weeks)

| Phase | Weeks |
|-------|-------|
| Foundation | 1-4 |
| LangGraph | 5-7 |
| Agents | 8-10 |
| Vector DB | 11-12 |
| Questionnaire | 13-14 |
| Lens System | 15-16 |
| API | 17-18 |
| Testing | 19-20 |
| Deployment | 21-24 |

---

## ✅ &I Philosophy Checklist

For every component, verify:
- [ ] Human can pause/redirect
- [ ] Confidence scores visible
- [ ] "I don't know" is valid
- [ ] Human context weighted
- [ ] Overrides logged
- [ ] Reasoning explainable
- [ ] Reports invite interpretation

---

*Full details: `RootRise_Infrastructure_Blueprint_v1.1.md`*
