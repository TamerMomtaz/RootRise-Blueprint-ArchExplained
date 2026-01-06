# RootRise Architecture v7.0
## Master Summary Document

**January 2026 | DEVONEERS**  
**Prepared by:** Tee (Product Creative Strategist / The Ionganic Orchestrator)

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Architecture Overview](#2-architecture-overview)
3. [The Pantheon — 11 AI Agents](#3-the-pantheon--11-ai-agents)
4. [My Sector — 31 Industry Knowledge Packs](#4-my-sector--31-industry-knowledge-packs)
5. [The Lens System — 17 Transformation Lenses](#5-the-lens-system--17-transformation-lenses)
6. [Questionnaire System v2.0](#6-questionnaire-system-v20)
7. [11-Dimension Scoring System](#7-11-dimension-scoring-system)
8. [The Crema — Quick Wins Engine](#8-the-crema--quick-wins-engine)
9. [Report Generation — 8 Report Types](#9-report-generation--8-report-types)
10. [Country Coverage — 6 MENA Markets](#10-country-coverage--6-mena-markets)
11. [UI Decisions & Behaviors](#11-ui-decisions--behaviors)
12. [&I Philosophy Integration](#12-i-philosophy-integration)
13. [Documentation Inventory](#13-documentation-inventory)
14. [Implementation Status](#14-implementation-status)
15. [Key Decisions Log](#15-key-decisions-log)

---

# 1. Executive Summary

This document captures all architecture decisions, specifications, and implementation requirements for **RootRise Platform v7.0**. It serves as the single source of truth for continuity across development sessions and team handoffs.

## 1.1 Key Numbers (v7.0)

| Component | Count | Change from v6 |
|-----------|-------|----------------|
| AI Agents (The Pantheon) | 11 | — |
| Sector Knowledge Packs (My Sector) | **31** | +4 |
| Transformation Lenses (The Lens System) | **17** | +2 |
| Country Coverage | **6** | +2 |
| Scoring Dimensions | **11** | NEW |
| Report Types | **8** | +4 |
| Questionnaire Sections | **12** | +2 |
| Base Questions | **~160** | +15 |

## 1.2 What's New in v7.0

| Feature | Description |
|---------|-------------|
| **Lens System Expansion** | Added EYE-CREMA (Quick Wins) and EYE-CUSTOM (Custom Objective) as special lenses |
| **Country Expansion** | Added Lebanon (LB) and Morocco (MA) to coverage |
| **Sector Packs v2.0** | All 31 packs upgraded with agent-specific instructions |
| **Questionnaire v2.0** | Added lens_relevance, quick_win_indicator, effort_level fields |
| **11-Dimension Scoring** | Comprehensive scoring across all business dimensions |
| **Crema Engine** | Full 30/60/90 day quick win bucketing system |
| **8 Report Types** | Added specialized lens reports (Investor Ready, Export Roadmap, etc.) |
| **Agent Naming** | Standardized: Removed "The" prefix from code references |
| **Agent Personas** | Each agent now has a named persona (The Conductor, The Optimizer, etc.) |

## 1.3 Core Philosophy

RootRise is built on the **&I Philosophy** — a human-AI collaboration model where:
- AI provides data-driven analysis, pattern recognition, and recommendations
- Humans provide context, judgment, and final decisions
- Every insight clearly distinguishes AI-generated content from human-provided context
- The goal is transformation, not just diagnosis

---

# 2. Architecture Overview

RootRise v7.0 uses a **three-layer configurable architecture** that allows each SME to build their own diagnostic experience.

## 2.1 The Three Layers

```
┌─────────────────────────────────────────────────────────────────┐
│                    LAYER 1: THE LENS SYSTEM                      │
│                                                                  │
│   17 strategic transformation lenses that determine:            │
│   • Which questions to prioritize                               │
│   • Which agents to activate                                    │
│   • How to weight dimensions                                    │
│   • What report format to generate                              │
│                                                                  │
│   Categories: Growth (5) | Transition (3) | Operations (5)      │
│               Impact (2) | Special (2)                          │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                    LAYER 2: THE PANTHEON                         │
│                                                                  │
│   11 specialist AI agents named after business pioneers:        │
│                                                                  │
│   Supervisor: Drucker (The Conductor)                           │
│   Core: Graham (Numbers Whisperer), Marvin (The Optimizer)      │
│   Specialists: Lovelace, Mayo, Porter, Ohno, Deming,           │
│                Ricardo, Landor                                   │
│   Utility: Tufte (The Visualizer)                               │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                    LAYER 3: SECTOR KNOWLEDGE                     │
│                                                                  │
│   31 industry-specific knowledge packs (v2.0):                  │
│                                                                  │
│   Manufacturing (8) | Services (8) | Technology (4)             │
│   Trade (4) | Primary (4) | Specialized (3)                     │
│                                                                  │
│   Each pack includes: benchmarks, regulations, KPIs,            │
│   agent instructions, MENA context for 6 countries              │
└─────────────────────────────────────────────────────────────────┘
```

## 2.2 Configuration Flow

1. **Lens Selection** — SME selects primary lens (and optionally secondary lenses + Crema)
2. **Sector Selection** — SME selects their industry from 31 sectors
3. **Questionnaire** — System routes questions based on lens configuration
4. **Agent Processing** — Pantheon agents analyze based on lens priorities
5. **Dimension Scoring** — 11-dimension scores calculated
6. **Crema Processing** — If active, recommendations bucketed into 30/60/90 days
7. **Report Generation** — Tufte generates report in selected format
8. **Human Validation** — 4 gates before final delivery

## 2.3 Data Flow Diagram

```
User Input → Lens Selection → Questionnaire Routing → Agent Processing
                                                            │
                    ┌───────────────────────────────────────┘
                    │
                    ▼
            Dimension Scoring → Crema Filter → Report Generation
                    │               │                   │
                    │               │                   ▼
                    │               │            Human Validation
                    │               │                   │
                    ▼               ▼                   ▼
              11 Scores      30/60/90 Buckets    Final Report
```

---

# 3. The Pantheon — 11 AI Agents

Each agent is named after a business/technology pioneer who shaped modern management. This naming convention adds gravitas while making agents memorable.

## 3.1 Agent Registry

| Agent | Persona | Icon | Domain | Methodology |
|-------|---------|------|--------|-------------|
| **Drucker** | The Conductor | 🎯 | Orchestration & Strategy | Management by Objectives |
| **Graham** | The Numbers Whisperer | 💎 | Financial Analysis | Value Investing Principles |
| **Marvin** | The Optimizer | ⚙️ | Operations & Efficiency | Lean Manufacturing, Systems Thinking |
| **Lovelace** | The Digitizer | 🔮 | Technology & Digital | Digital Maturity Models |
| **Mayo** | The People Person | 🌱 | HR & Culture | Human Relations Theory |
| **Porter** | The Strategist | ♟️ | Market & Competition | Five Forces, Value Chain |
| **Ohno** | The Flow Master | 🌊 | Supply Chain & Logistics | Toyota Production System |
| **Deming** | The Perfectionist | 📐 | Quality & Compliance | PDCA, 14 Points |
| **Ricardo** | The Globalizer | 🧭 | Export & Trade | Comparative Advantage |
| **Landor** | The Storyteller | 📣 | Brand & Marketing | Brand Architecture |
| **Tufte** | The Visualizer | 📊 | Data Visualization | Information Design |

## 3.2 Agent Hierarchy

```
SUPERVISOR TIER (Always Active)
└── Drucker — Orchestrates all agents, manages flow

CORE TIER (Always Active)
├── Graham — Financial baseline required for all diagnostics
└── Marvin — Operational baseline (manufacturing/hybrid sectors)

SPECIALIST TIER (Lens/Sector Activated)
├── Lovelace — Digital transformation focus
├── Mayo — Workforce development focus
├── Porter — Market strategy focus
├── Ohno — Supply chain focus
├── Deming — Quality & compliance focus
├── Ricardo — Export & trade focus
└── Landor — Brand & marketing focus

UTILITY TIER (Always Final)
└── Tufte — Report generation, always last step
```

## 3.3 Agent Activation by Lens

| Lens | Primary Agents | Secondary Agents |
|------|----------------|------------------|
| EYE-001 Export | Ricardo, Landor | Deming, Porter, Ohno |
| EYE-002 Investment | Graham, Drucker | Deming, Porter |
| EYE-003 Digital | Lovelace, Marvin | Mayo, Porter |
| EYE-004 Operations | Marvin, Ohno, Deming | Lovelace |
| EYE-005 Market | Porter, Landor | Graham |
| EYE-006 Brand | Landor, Porter | Lovelace |
| EYE-007 Workforce | Mayo | Graham, Drucker |
| EYE-008 Supply Chain | Ohno, Marvin | Lovelace |
| EYE-009 ESG | Deming, Marvin | Mayo |
| EYE-010 Innovation | Lovelace, Porter | Graham |
| EYE-011 Customer | Porter, Landor | Lovelace |
| EYE-012 Cost | Graham, Marvin, Ohno | — |
| EYE-013 Risk | Deming, Graham | Ohno |
| EYE-014 Succession | Mayo, Drucker | Deming |
| EYE-015 Partnership | Porter, Ohno | Graham |
| EYE-CREMA | All agents | — |
| EYE-CUSTOM | Drucker (routes) | Dynamic |

## 3.4 Naming Convention (v7.0 Update)

**Important:** In code and technical documentation, agents are referenced WITHOUT "The" prefix:
- ✅ `drucker`, `graham`, `marvin`
- ❌ `the_drucker`, `the_graham`, `the_marvin`

The persona names (The Conductor, The Optimizer, etc.) are used in:
- User-facing interfaces
- Reports
- Marketing materials

---

# 4. My Sector — 31 Industry Knowledge Packs

Each sector is pre-loaded with industry-specific intelligence across multiple dimensions. This ensures the diagnostic provides contextually relevant insights rather than generic AI advice.

## 4.1 Sector Registry (v2.0)

### Manufacturing & Production (8)

| Code | Sector Name | Key Focus |
|------|-------------|-----------|
| SECTOR-001 | Food Processing & Beverages | HACCP, halal, cold chain |
| SECTOR-002 | Textiles & Apparel | Quality standards, labor compliance |
| SECTOR-003 | Building Materials & Construction Products | Safety certifications, logistics |
| SECTOR-004 | Chemicals & Plastics | Environmental compliance, safety |
| SECTOR-005 | Pharmaceuticals & Medical Devices | GMP, FDA/EMA alignment |
| SECTOR-006 | Electronics & Electrical Equipment | Quality systems, RoHS |
| SECTOR-007 | Automotive Parts & Assembly | IATF 16949, OEM requirements |
| SECTOR-008 | Metal Fabrication & Machinery | Precision standards, export certs |

### Services (8)

| Code | Sector Name | Key Focus |
|------|-------------|-----------|
| SECTOR-009 | Professional Services | Credentials, client management |
| SECTOR-010 | Healthcare Services | Licensing, accreditation |
| SECTOR-011 | Education & Training | Quality assurance, accreditation |
| SECTOR-012 | Hospitality & Tourism | Service standards, seasonality |
| SECTOR-013 | Transportation & Logistics | Fleet management, compliance |
| SECTOR-014 | Financial Services (Non-Banking) | Regulatory compliance |
| SECTOR-015 | Creative & Media Services | IP, project management |
| SECTOR-016 | Facility Management & Security | Service standards, licensing |

### Technology (4)

| Code | Sector Name | Key Focus |
|------|-------------|-----------|
| SECTOR-017 | Software Development & IT Services | Agile, security, SaaS metrics |
| SECTOR-018 | E-commerce & Digital Platforms | Conversion, logistics, UX |
| SECTOR-019 | FinTech | Compliance, security, growth |
| SECTOR-020 | CleanTech & Renewable Energy | Regulations, incentives |

### Trade & Retail (4)

| Code | Sector Name | Key Focus |
|------|-------------|-----------|
| SECTOR-021 | Wholesale Distribution | Inventory, supplier management |
| SECTOR-022 | Retail Trade | Customer experience, margins |
| SECTOR-023 | Import/Export Trading | Trade compliance, logistics |
| SECTOR-024 | Franchising & Licensing | Standards, expansion |

### Primary Industries (4)

| Code | Sector Name | Key Focus |
|------|-------------|-----------|
| SECTOR-025 | Agriculture & Agribusiness | Seasonality, certifications |
| SECTOR-026 | Fishing & Aquaculture | Sustainability, cold chain |
| SECTOR-027 | Mining & Quarrying | Safety, environmental |
| SECTOR-028 | Oil & Gas Services | Safety, certifications |

### Specialized (3)

| Code | Sector Name | Key Focus |
|------|-------------|-----------|
| SECTOR-029 | Real Estate Development | Project management, financing |
| SECTOR-030 | Waste Management & Recycling | Environmental, compliance |
| SECTOR-031 | Artisanal & Handicrafts | Heritage, export potential |

## 4.2 Sector Pack Structure (v2.0)

Each sector knowledge pack includes:

| Component | Description |
|-----------|-------------|
| **Overview** | Definition, subsectors, value chain |
| **Regional Landscape** | 6-country context (EG, SA, AE, JO, LB, MA) |
| **Operational Benchmarks** | OEE, capacity, quality metrics |
| **Financial Benchmarks** | Margins, growth rates, capital needs |
| **Quality Benchmarks** | Standards, certifications |
| **Growth Benchmarks** | Expansion indicators |
| **Diagnostic Focus** | Key questions per dimension |
| **Transformation Pathways** | Common improvement journeys |
| **Agent Instructions** | Sector-specific guidance for each agent (NEW in v2.0) |

## 4.3 Agent Instructions (NEW in v2.0)

Each sector pack now includes specific instructions for agents:

```
Agent: Graham (The Numbers Whisperer)
Sector: SECTOR-001 (Food Processing)

Focus Areas:
- Working capital cycles (raw materials to finished goods)
- Seasonal cash flow patterns
- Export revenue diversification

Key Questions:
- What's the inventory turnover ratio?
- How does Ramadan affect cash flow?
- What's the margin difference between domestic vs export?

Red Flags:
- Cash conversion cycle > 90 days
- Single customer > 40% revenue
- Negative EBITDA in peak season

Quick Wins:
- Invoice factoring for export receivables
- Supplier payment term renegotiation
- SKU rationalization for margin improvement
```

---

# 5. The Lens System — 17 Transformation Lenses

Each lens represents a transformation objective. Selecting a lens reprioritizes the entire diagnostic to focus on that goal. Same business data, different analysis priorities.

## 5.1 Lens Categories

| Category | Count | Focus |
|----------|-------|-------|
| Growth | 5 | Expansion, investment, market development |
| Transition | 3 | Transformation, succession, workforce |
| Operations | 5 | Efficiency, quality, cost, risk |
| Impact | 2 | Sustainability, partnership |
| Special | 2 | Quick wins, custom objectives |

## 5.2 Complete Lens Registry

### Growth Objectives (5)

| Code | Name | "I want to..." | Primary Agents |
|------|------|----------------|----------------|
| EYE-001 | Export Expansion | start or grow my export business | Ricardo, Landor |
| EYE-002 | Investment Readiness | attract investors or prepare for funding | Graham, Drucker |
| EYE-005 | Market Expansion | enter new markets or segments | Porter, Landor |
| EYE-006 | Brand Building | strengthen my brand position | Landor, Porter |
| EYE-010 | Innovation & R&D | develop new products or services | Lovelace, Porter |

### Transition Objectives (3)

| Code | Name | "I want to..." | Primary Agents |
|------|------|----------------|----------------|
| EYE-003 | Digital Transformation | digitize my business operations | Lovelace, Marvin |
| EYE-007 | Workforce Development | build my team's capabilities | Mayo |
| EYE-014 | Succession & Governance | prepare for leadership transition | Mayo, Drucker |

### Operations Objectives (5)

| Code | Name | "I want to..." | Primary Agents |
|------|------|----------------|----------------|
| EYE-004 | Operational Excellence | improve efficiency and reduce waste | Marvin, Ohno, Deming |
| EYE-008 | Supply Chain Optimization | strengthen my supply chain | Ohno, Marvin |
| EYE-011 | Customer Experience | improve customer satisfaction | Porter, Landor |
| EYE-012 | Cost Optimization | reduce costs without sacrificing quality | Graham, Marvin, Ohno |
| EYE-013 | Risk & Resilience | protect against disruptions | Deming, Graham |

### Impact Objectives (2)

| Code | Name | "I want to..." | Primary Agents |
|------|------|----------------|----------------|
| EYE-009 | Sustainability & ESG | improve environmental/social impact | Deming, Marvin |
| EYE-015 | Partnership & M&A | find partners or acquisition targets | Porter, Ohno |

### Special Lenses (2)

| Code | Name | "I want to..." | Primary Agents |
|------|------|----------------|----------------|
| **EYE-CREMA** | The Crema — Quick Wins | actionable quick wins I can implement now | All (filters output) |
| **EYE-CUSTOM** | Custom Objective | pursue a specific goal not listed | Drucker (dynamic routing) |

## 5.3 The Crema (Featured Lens)

**The Crema** is a special lens that can be combined with any other lens. When active, it:

1. **Filters** all recommendations by effort level
2. **Buckets** actions into 30/60/90 day timelines
3. **Generates** a Crema Quick Wins Report
4. **Prioritizes** low-effort, high-impact items

```
THE CREMA FILTERING PROCESS

All Agent Recommendations
         │
         ▼
┌─────────────────────┐
│   Effort Level?     │
│  (from options)     │
└─────────────────────┘
         │
    ┌────┼────┐
    │    │    │
    ▼    ▼    ▼
  LOW  MED  HIGH
   │    │    │
   ▼    ▼    ▼
 30d   60d   90d
BUCKET BUCKET BUCKET
```

## 5.4 Lens Configuration Effects

When a lens is selected, it affects:

| Component | Effect |
|-----------|--------|
| **Questionnaire** | Certain questions weighted higher, others may be skipped |
| **Agents** | Primary agents fully activated, secondary at 70% weight |
| **Dimensions** | Relevant dimensions get multiplied scores |
| **Reports** | Recommended report type changes |
| **KPIs** | Certain KPIs emphasized in output |

---

# 6. Questionnaire System v2.0

The questionnaire is the primary data collection mechanism. v2.0 introduces lens-aware routing and Crema integration.

## 6.1 Section Structure

| Code | Section Name | Questions | Time (min) |
|------|--------------|-----------|------------|
| LS | Lens Selection | 3 | 1 |
| BP | Business Profile | 15 | 3 |
| FH | Financial Health | 20 | 5 |
| OP | Operations & Production | 18 | 4 |
| DM | Digital Maturity | 13 | 3 |
| WF | Workforce & HR | 11 | 3 |
| MK | Market & Competition | 10 | 2 |
| SC | Supply Chain | 12 | 3 |
| EX | Export Readiness | 15 | 4 |
| BR | Brand & Marketing | 10 | 2 |
| CC | Compliance & Certifications | 8 | 2 |
| **QW** | **Quick Win Assessment** | **10** | **2** |

**Total:** ~145 base questions, ~160 with conditionals  
**Typical completion:** 80-100 questions (based on routing)  
**Estimated time:** 25-35 minutes

## 6.2 New Fields in v2.0

| Field | Type | Purpose |
|-------|------|---------|
| `lens_relevance` | Array | Which lenses care about this question |
| `quick_win_indicator` | Boolean | Flags for Crema filtering |
| `effort_level` | Enum | Low/Medium/High for 30/60/90 bucketing |
| `allows_human_context` | Boolean | Can user add context? |
| `human_context_prompt` | String | Prompt for human context |

## 6.3 Question Example (v2.0)

```typescript
{
  question_id: "OP_005",
  text: {
    en: "How do you track Overall Equipment Effectiveness (OEE)?",
    ar: "كيف تتبع فعالية المعدات الشاملة (OEE)؟"
  },
  type: "single_choice",
  options: [
    { value: "real_time", label: { en: "Real-time monitoring", ar: "مراقبة فورية" }, score: 100, effort_level: null },
    { value: "detailed", label: { en: "Detailed tracking", ar: "تتبع تفصيلي" }, score: 80, effort_level: null },
    { value: "basic", label: { en: "Basic tracking", ar: "تتبع أساسي" }, score: 60, effort_level: null },
    { value: "informal", label: { en: "Informal observation", ar: "مراقبة غير رسمية" }, score: 35, effort_level: "low" },
    { value: "no_tracking", label: { en: "No tracking", ar: "لا يوجد تتبع" }, score: 15, effort_level: "low" }
  ],
  agents: ["marvin", "deming"],
  dimension_id: 6,
  lens_relevance: [
    { lens_id: "EYE-004", relevance: "primary", weight_multiplier: 1.5 },
    { lens_id: "EYE-012", relevance: "secondary", weight_multiplier: 1.2 }
  ],
  quick_win_indicator: true,
  allows_human_context: true,
  human_context_prompt: {
    en: "Any specific OEE challenges or constraints?",
    ar: "هل هناك تحديات أو قيود محددة في OEE؟"
  }
}
```

---

# 7. 11-Dimension Scoring System

The diagnostic produces scores across 11 dimensions, each mapped to specific questionnaire sections and agents.

## 7.1 Dimension Definitions

| ID | Code | Name | Name (AR) | Weight | Primary Agent |
|----|------|------|-----------|--------|---------------|
| 1 | D1 | Business Model & Profile | نموذج العمل والملف التعريفي | 8% | Drucker |
| 2 | D2 | Financial Health | الصحة المالية | 12% | Graham |
| 3 | D3 | Digital & Systems | الرقمنة والأنظمة | 9% | Lovelace |
| 4 | D4 | Processes & Documentation | العمليات والتوثيق | 9% | Deming |
| 5 | D5 | Product/Service Quality | جودة المنتج/الخدمة | 10% | Deming, Landor |
| 6 | D6 | Operational Efficiency | الكفاءة التشغيلية | 10% | Marvin |
| 7 | D7 | People & Culture | الأفراد والثقافة | 9% | Mayo |
| 8 | D8 | Supply Chain | سلسلة التوريد | 8% | Ohno |
| 9 | D9 | Market Position | الموقع السوقي | 10% | Porter, Landor |
| 10 | D10 | Compliance & Governance | الامتثال والحوكمة | 7% | Deming |
| 11 | D11 | International Readiness | الجاهزية الدولية | 8% | Ricardo |

## 7.2 Score Classification

| Range | Class | Label (EN) | Label (AR) | Color |
|-------|-------|------------|------------|-------|
| 80-100 | Excellent | Excellent | ممتاز | Green |
| 65-79 | Good | Good | جيد | Teal |
| 50-64 | Average | Average | متوسط | Yellow |
| 0-49 | Needs Work | Needs Work | يحتاج تحسين | Red |

## 7.3 Confidence Levels

Each dimension score includes a confidence indicator:

| Level | Range | Meaning |
|-------|-------|---------|
| High | ≥80% | Strong data, reliable score |
| Medium | 60-79% | Adequate data, reasonable score |
| Low | <60% | Limited data, interpret with caution |

## 7.4 Lens Impact on Dimensions

When a lens is selected, relevant dimensions receive multipliers:

**Example: EYE-002 (Investment Readiness)**
- D2 (Financial Health): ×1.5
- D10 (Compliance): ×1.4
- D4 (Processes): ×1.2

This means a score of 70 in Financial Health becomes 105 (capped at 100) for investment readiness purposes.

---

# 8. The Crema — Quick Wins Engine

The Crema is RootRise's signature feature for delivering immediate, actionable value.

## 8.1 How It Works

1. **Extract** all findings and recommendations from agents
2. **Filter** items marked with `quick_win_indicator: true`
3. **Bucket** by effort level:
   - Low effort → 30-day bucket
   - Medium effort → 60-day bucket
   - High effort → 90-day bucket
4. **Sort** by impact within each bucket
5. **Generate** Crema Quick Wins Report

## 8.2 Crema Report Structure

| Section | Content |
|---------|---------|
| Cover | Crema branding, summary stats |
| Overview | Priority breakdown, effort breakdown, impact estimates |
| 30-Day Actions | Low-effort, high-impact items |
| 60-Day Actions | Medium-effort items |
| 90-Day Actions | Larger initiatives |
| Resource Requirements | Investment, team, external support |
| Success Metrics | Tracking targets by timeline |

## 8.3 Quick Win Card Structure

Each quick win includes:

```
┌─────────────────────────────────────────────────────┐
│ [1] Quick Win Title                    ☕ 30 Days  │
├─────────────────────────────────────────────────────┤
│ Description of the quick win action                 │
│                                                     │
│ Category: Operations          Agent: ⚙️ Marvin     │
│ Effort: Low                   Impact: High         │
│ Investment: $500-2,000                             │
│                                                     │
│ First Steps:                                        │
│ 1. Identify key equipment                          │
│ 2. Set up tracking spreadsheet                     │
│ 3. Train operators on logging                      │
└─────────────────────────────────────────────────────┘
```

---

# 9. Report Generation — 8 Report Types

Tufte (The Visualizer) generates reports in 8 formats, each suited to different needs.

## 9.1 Report Type Matrix

| Type | Pages | Use Case | Lens Requirement |
|------|-------|----------|------------------|
| Executive Summary | 2-3 | Quick overview, pitches | Any |
| Full Diagnostic | 12-18 | Comprehensive analysis | Any |
| **Crema Quick Wins** | 3-4 | 30/60/90 action plan | EYE-CREMA active |
| **Lens-Focused** | 6-10 | Deep dive on lens | Single lens |
| Sector Benchmarking | 4-6 | Industry comparison | Any |
| Action Plan | 3-4 | Implementation roadmap | Any |
| **Investor Ready** | 5-7 | Due diligence package | EYE-002 |
| **Export Roadmap** | 5-7 | Market entry timeline | EYE-001 |

## 9.2 Report Components

All reports include:

| Component | Description |
|-----------|-------------|
| **Cover** | Company name, lens selection, date |
| **Lens Badge** | Shows selected transformation focus |
| **Health Score** | Overall score with radar chart |
| **Dimension Breakdown** | 11 dimension scores |
| **Key Findings** | Strengths, improvements, critical issues |
| **Agent Attribution** | Which agent generated each insight |
| **Human Context Callouts** | Bronze-bordered boxes for user context |
| **Confidence Indicators** | Color-coded reliability markers |
| **Recommendations** | Prioritized action items |
| **Data Quality Notice** | Completeness and gaps |

## 9.3 Report Languages

- **English** — Primary
- **Arabic** — Full RTL support
- **Bilingual** — Side-by-side EN/AR

---

# 10. Country Coverage — 6 MENA Markets

RootRise supports 6 MENA countries with localized context.

## 10.1 Country Registry

| Code | Name | Name (AR) | Currency | Notes |
|------|------|-----------|----------|-------|
| EG | Egypt | مصر | EGP | Largest SME base, primary market |
| SA | Saudi Arabia | المملكة العربية السعودية | SAR | Vision 2030, Saudization rules |
| AE | UAE | الإمارات العربية المتحدة | AED | Free zones, high digitalization |
| JO | Jordan | الأردن | JOD | Services focus, regional hub |
| **LB** | Lebanon | لبنان | USD* | Dollarized economy, diaspora focus |
| **MA** | Morocco | المغرب | MAD | EU proximity, Africa gateway |

## 10.2 Country-Specific Context

Each country in each sector pack includes:

- Market size estimates
- Key players
- Regulatory environment
- Licensing requirements
- Incentive zones
- Export considerations
- Government support programs

---

# 11. UI Decisions & Behaviors

## 11.1 Lens Selection (The Lens System)

| Behavior | Description |
|----------|-------------|
| The Crema | Pre-selected as default, can be deselected |
| The Crema | Spans full width (3 columns) at top of grid |
| Primary Lens | Required — at least one lens must be selected |
| Secondary Lenses | Optional — can add 1-2 more |
| Custom Lens | Shows text input for custom objective |
| Multi-select | Multiple lenses allowed (recommended limit: 3) |

## 11.2 Sector Selection (My Sector)

| Behavior | Description |
|----------|-------------|
| Category Tabs | Toggle between 6 categories |
| Single Select | One sector per diagnostic |
| Sector Card | Shows name, icon, key tags |
| Search | Filter sectors by name/keywords |

## 11.3 Agent Selection (The Pantheon)

| Agent Type | Behavior |
|------------|----------|
| Drucker | Always selected, locked (supervisor) |
| Graham, Marvin | Always included by default (core) |
| Specialists | Auto-activated by lens, can override |
| Tufte | Always included, locked (report generation) |
| Selection State | Teal border glow, checkmark indicator |

## 11.4 Questionnaire

| Behavior | Description |
|----------|-------------|
| Progress Bar | Shows completion percentage |
| Section Navigation | Tab-based section switching |
| Conditional Questions | Appear based on previous answers |
| Human Context | Optional text boxes for context |
| Validation | Real-time input validation |
| Save Progress | Auto-save every response |

## 11.5 Design System (Light-Forward)

Based on feedback, RootRise uses a **Light-Forward** design:

| Element | Light Mode | Dark Mode |
|---------|------------|-----------|
| Background | Cream (#F5F1E8) | Navy (#0F1419) |
| Cards | White (#FFFFFF) | Blue-gray (#1E2F3E) |
| Accent | Bronze (#B8904A) | Bronze (#B8904A) |
| Highlight | Teal (#5DD4C3) | Teal (#5DD4C3) |
| Text | Black (#000000) | White (#FFFFFF) |

**Reports are generated in Light Mode by default.**

---

# 12. &I Philosophy Integration

The **&I Philosophy** (AI + Human collaboration) is embedded throughout RootRise.

## 12.1 Core Principles

| AI Contribution | Human Contribution |
|-----------------|-------------------|
| Data analysis | Context and nuance |
| Pattern recognition | Judgment and priorities |
| Benchmarking | Cultural understanding |
| Recommendations | Final decisions |
| Consistency | Creativity |

## 12.2 Visual Distinction

| Element | Visual Treatment |
|---------|------------------|
| AI-generated insight | Standard text, agent attribution |
| Human-provided context | Bronze left border, cream background |
| Confidence indicator | Color-coded badge (green/yellow/red) |
| Source attribution | Footnote with data source |

## 12.3 Human Context Collection

At key questionnaire points, users can add context:

```
┌─────────────────────────────────────────────────────┐
│ 👤 Add Context (Optional)                           │
├─────────────────────────────────────────────────────┤
│ Any specific financial constraints or context?      │
│                                                     │
│ ┌─────────────────────────────────────────────────┐ │
│ │ We had currency fluctuations in Q3 that         │ │
│ │ affected our margins significantly...           │ │
│ └─────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────┘
```

This context appears in reports with clear human attribution.

---

# 13. Documentation Inventory

## 13.1 Core Architecture Documents

| Document | Version | Lines | Description |
|----------|---------|-------|-------------|
| Infrastructure Blueprint | v1.2 | ~2,000 | Complete system architecture |
| Infrastructure QuickRef | v1.2 | ~200 | Quick reference card |
| Technical Handoff | v7.0 | 3,325 | Developer implementation guide |
| Project Brief | v3.0 | 544 | Stakeholder overview |

## 13.2 Schema Documents

| Document | Version | Lines | Description |
|----------|---------|-------|-------------|
| Questionnaire Schema | v2.0 | 5,693 | All questions, routing, validation |
| Report Templates | v2.0 | 2,559 | HTML/CSS templates, components |

## 13.3 Lens Documents (17)

| Code | Document | Size |
|------|----------|------|
| EYE-000 | The Crema | 23KB |
| EYE-001 | Export Readiness | 16KB |
| EYE-002 | Investment Readiness | 45KB |
| EYE-003 | Digital Transformation | 14KB |
| EYE-004 through EYE-015 | Standard Lenses | ~60KB each |
| EYE-CREMA | Quick Wins | 22KB |
| EYE-CUSTOM | Custom Objective | 19KB |

## 13.4 Sector Knowledge Packs (31)

All sector packs are v2.0 format with:
- Agent-specific instructions
- 6-country context
- Enhanced benchmarks

---

# 14. Implementation Status

## 14.1 Completed (January 2026)

| Component | Status | Notes |
|-----------|--------|-------|
| Architecture Design | ✅ Complete | v7.0 finalized |
| Agent Definitions | ✅ Complete | 11 agents with personas |
| Lens Configurations | ✅ Complete | 17 lenses documented |
| Sector Packs | ✅ Complete | 31 packs v2.0 |
| Questionnaire Schema | ✅ Complete | v2.0 with lens routing |
| Report Templates | ✅ Complete | v2.0 with 8 types |
| Technical Handoff | ✅ Complete | v7.0 for Ahmed |
| Documentation | ✅ Complete | All docs aligned |

## 14.2 Development Phases

| Phase | Weeks | Focus |
|-------|-------|-------|
| MVP | 1-4 | Basic flow, 3 sectors, 3 lenses, 6 agents |
| Full Suite | 5-8 | All agents, all lenses, Crema engine |
| Coverage | 9-12 | All sectors, all countries, all reports |
| Polish | 13-16 | Performance, testing, documentation |

## 14.3 MVP Scope

- **Sectors:** Food Processing, Textiles, Software/IT
- **Lenses:** Investment, Digital, Operations
- **Agents:** Drucker, Graham, Marvin, Lovelace, Deming, Tufte
- **Countries:** Egypt (primary)
- **Reports:** Executive Summary, Full Diagnostic

---

# 15. Key Decisions Log

## 15.1 Architecture Decisions

| Decision | Date | Rationale |
|----------|------|-----------|
| Remove Tunisia from country list | Dec 2025 | Focus on larger markets first |
| Add Lebanon and Morocco | Jan 2026 | Strong diaspora, EU gateway |
| Agent naming without "The" in code | Jan 2026 | Cleaner code, personas separate |
| 11-dimension scoring system | Jan 2026 | Comprehensive business coverage |
| 8 report types | Jan 2026 | Lens-specific outputs needed |

## 15.2 Naming Conventions

| Element | Convention | Example |
|---------|------------|---------|
| Agent ID | lowercase | `graham` |
| Agent Name | Title case | `Graham` |
| Agent Persona | With "The" | `The Numbers Whisperer` |
| Lens Code | EYE-XXX | `EYE-002` |
| Sector Code | SECTOR-XXX | `SECTOR-001` |
| Dimension Code | D1-D11 | `D2` |
| Country Code | ISO 3166 | `EG` |

## 15.3 Design Decisions

| Decision | Date | Rationale |
|----------|------|-----------|
| Light-Forward design | Dec 2025 | Better readability, professional feel |
| Bronze as primary accent | Dec 2025 | Brand differentiation, premium feel |
| Teal as secondary accent | Dec 2025 | Contrast, call-to-action |
| Reports in Light Mode | Jan 2026 | Print-friendly, PDF readability |

---

## Change Log

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 6.0 | December 2025 | Tee | Initial comprehensive summary |
| **7.0** | **January 2026** | **Tee (TIO)** | Major update: 31 sectors (was 27), 17 lenses (was 15), 6 countries (was 4), agent naming standardization, personas added, Questionnaire v2.0, 11-dimension scoring, Crema engine details, 8 report types, complete documentation inventory, implementation status |

---

*Document Version: 7.0*  
*Last Updated: January 2026*  
*Prepared by: Tee (Product Creative Strategist / The Ionganic Orchestrator)*  
*Part of the RootRise &I SME Transformation Platform by DEVONEERS*
