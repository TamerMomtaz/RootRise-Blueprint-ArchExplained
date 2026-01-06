# RootRise v6.0 Technical Infrastructure Blueprint

**Document Version:** 1.2  
**Date:** January 6, 2026  
**Author:** Tee (The Ionganic Orchestrator - TIO)  
**For:** Ahmed El-Gazzar (Technical DevOps Lead)  
**Status:** Implementation Ready

---

## Executive Summary

This document provides the complete technical infrastructure specification for implementing **The RootRise Pantheon**—an AI-powered SME diagnostic platform. It translates our architectural vision into actionable implementation guidance, with every technical decision filtered through the lens of our **&I Philosophy: AI + Human, not AI instead of Human**.

### What This Document Covers

1. **&I Philosophy Integration** — How human-AI collaboration is embedded at every layer
2. **System Architecture Overview** — The three-layer configuration model
3. **Memory Architecture** — Session, persistent, and cross-agent state management
4. **Vector Database Design** — Sector knowledge storage and retrieval with confidence metadata
5. **LangGraph Orchestration** — Multi-agent workflow with native HITL checkpoints
6. **Questionnaire System** — 10-section data collection with agent mapping
7. **The &Eye Lens System** — 17 transformation lenses and their agent priorities
8. **API Specification** — REST endpoints including transparency and override capabilities
9. **Deployment Architecture** — Infrastructure requirements and operational principles
10. **Resource Estimates** — Compute, storage, and cost projections

### Key Metrics at a Glance

| Component | Specification |
|-----------|---------------|
| **Total Agents** | 11 (3 Core + 6 Add-On + 2 Utility) |
| **Transformation Lenses** | 17 (The &Eye: 1 Featured + 15 Standard + 1 Custom) |
| **Sector Knowledge Packs** | 31 sectors, ~2.6MB total |
| **Dimensions per Sector** | 11 knowledge dimensions + Growth Pathways + Strategic Summary |
| **Questionnaire Sections** | 10 sections, ~145 questions |
| **HITL Checkpoints** | 4 validation gates |
| **Target Countries** | 6 (EG, SA, AE, JO, LB, MA) |
| **Target Diagnostic Time** | 30 minutes (user interaction) |
| **Target Processing Time** | < 120 seconds (AI analysis) |

---

## Part 1: The &I Philosophy — Our Technical North Star

Before any infrastructure decision, we must understand what makes RootRise fundamentally different. We are not building AI that replaces human judgment—we are building AI that **augments human intelligence** while **preserving human agency**.

### 1.1 The &I Principle in Practice

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         THE &I PHILOSOPHY                                    │
│                 "AI + Human, Not AI Instead of Human"                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   AI EXCELS AT:                        HUMANS EXCEL AT:                      │
│   ├─ Pattern recognition at scale      ├─ Local market context              │
│   ├─ 24/7 consistent processing        ├─ Relationship building             │
│   ├─ Benchmarking across sectors       ├─ Cultural nuance                   │
│   ├─ Data synthesis from 11 dims       ├─ Strategic judgment calls          │
│   ├─ Consistency across diagnostics    ├─ Trust and credibility             │
│   └─ Predictive modeling               └─ Creative problem-solving          │
│                                                                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   INFRASTRUCTURE REQUIREMENTS:                                               │
│                                                                              │
│   ✓ Never pretend AI has human judgment                                      │
│   ✓ Always surface uncertainty and confidence levels                         │
│   ✓ Design explicit human-in-the-loop checkpoints as FEATURES                │
│   ✓ Enable human override at every stage                                     │
│   ✓ Preserve human agency in final decisions                                 │
│   ✓ Make AI reasoning transparent and explainable                            │
│   ✓ Support (not replace) local advisors and consultants                     │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 &I Decision Framework

For every infrastructure component, we evaluate:

| Question | Implementation Implication |
|----------|---------------------------|
| Does this support human context injection? | Memory architecture must distinguish human-provided vs AI-inferred data |
| Do the APIs enable human override? | Every assessment endpoint needs corresponding override/inject endpoints |
| Are HITL checkpoints first-class? | LangGraph nodes must include conditional human routing |
| Does reporting invite interpretation? | Reports include confidence, alternatives, and "questions to consider" |
| Is AI uncertainty visible? | Every finding carries confidence metadata surfaced to UI |

---

## Part 2: System Architecture Overview

### 2.1 The Three-Layer Configuration Model

RootRise operates on a powerful **three-layer configuration architecture** that enables the same business data to produce different but equally rigorous transformation paths.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    ROOTRISE THREE-LAYER CONFIGURATION                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   LAYER 1: THE PANTHEON (11 Agents)                                         │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │  WHO analyzes the business                                           │   │
│   │                                                                       │   │
│   │  CORE AGENTS (Always Active):                                        │   │
│   │  • The Drucker (Supervisor) — Orchestration & Planning               │   │
│   │  • The Marvin (Diagnostics) — Operational Assessment                 │   │
│   │  • The Graham (Finance) — Financial Health Analysis                  │   │
│   │                                                                       │   │
│   │  ADD-ON AGENTS (User Selects):                                       │   │
│   │  • The Ricardo (Export) — International Trade & Compliance           │   │
│   │  • The Lovelace (Digital) — Technology & Digital Transformation      │   │
│   │  • The Mayo (HR) — Workforce & Organization Development              │   │
│   │  • The Ohno (Supply Chain) — Lean Operations & Logistics             │   │
│   │  • The Porter (Market) — Competitive Strategy & Positioning          │   │
│   │  • The Landor (Packaging) — Brand Compliance & Export Packaging      │   │
│   │                                                                       │   │
│   │  UTILITY AGENTS (Always Active):                                     │   │
│   │  • The Deming (Quality) — Cross-Agent Validation                     │   │
│   │  • The Tufte (Reports) — Report Generation & Visualization           │   │
│   └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
│   LAYER 2: MY SECTOR (31 Sectors)                                           │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │  WHAT industry context applies                                       │   │
│   │                                                                       │   │
│   │  11-Dimension Framework per sector:                                  │   │
│   │  1. Industry Classification    7. Workforce Norms                    │   │
│   │  2. Financial Benchmarks       8. Supply Chain                       │   │
│   │  3. Operational KPIs           9. Export Requirements                │   │
│   │  4. Regulatory Landscape      10. Packaging & Labeling               │   │
│   │  5. Competitive Dynamics      11. MENA Regional Context              │   │
│   │  6. Digital Maturity                                                 │   │
│   │                                                                       │   │
│   │  PLUS: 5-Stage Growth Pathways, Key Financial Insights,              │   │
│   │        Strategic Summary with Success Factors & Failure Patterns     │   │
│   │                                                                       │   │
│   │  Coverage: 31 sectors across 6 MENA countries (EG, SA, AE, JO, LB, MA)│  │
│   └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
│   LAYER 3: THE &EYE (17 Lenses)                                             │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │  WHY / WHAT transformation goal                                      │   │
│   │                                                                       │   │
│   │  FEATURED (Pre-selected):                                            │   │
│   │  ☕ EYE-CREMA: The Crema — Quick Wins (30-60-90 days)                │   │
│   │                                                                       │   │
│   │  GROWTH LENSES:                                                      │   │
│   │  🌍 EYE-001: Export Readiness                                        │   │
│   │  💰 EYE-002: Investment Readiness                                    │   │
│   │  📈 EYE-005: Market Expansion                                        │   │
│   │  🎨 EYE-006: Brand Building                                          │   │
│   │                                                                       │   │
│   │  OPERATIONS LENSES:                                                  │   │
│   │  💻 EYE-003: Digital Transformation                                  │   │
│   │  ⚙️ EYE-004: Operational Excellence                                  │   │
│   │  📊 EYE-012: Cost Optimization                                       │   │
│   │                                                                       │   │
│   │  IMPACT LENSES:                                                      │   │
│   │  👥 EYE-007: Workforce Development                                   │   │
│   │  🔗 EYE-008: Supply Chain Optimization                               │   │
│   │  🌱 EYE-009: Sustainability & ESG                                    │   │
│   │  💡 EYE-010: Innovation & R&D                                        │   │
│   │  ⭐ EYE-011: Customer Experience                                     │   │
│   │  🛡️ EYE-013: Risk & Resilience                                       │   │
│   │                                                                       │   │
│   │  TRANSITION LENSES:                                                  │   │
│   │  👤 EYE-014: Succession & Governance                                 │   │
│   │  🤝 EYE-015: Partnership & M&A                                       │   │
│   │                                                                       │   │
│   │  CUSTOM:                                                             │   │
│   │  ✨ EYE-CUSTOM: Custom Objective (AI-interpreted)                    │   │
│   │                                                                       │   │
│   │  Each lens reprioritizes agent outputs and focuses recommendations   │   │
│   └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Complete Agent Roster

#### Core Agents (Always Execute)

| Agent ID | Display Name | Named After | Domain | Primary Value |
|----------|--------------|-------------|--------|---------------|
| `drucker` | The Drucker | Peter Drucker (1909-2005) | Supervision & Orchestration | Diagnostic flow management, agent coordination |
| `marvin` | The Marvin | Marvin Bower (1903-2003) | Operational Diagnostics | Process maturity, quality, efficiency assessment |
| `graham` | The Graham | Benjamin Graham (1894-1976) | Financial Analysis | Financial health, funding readiness, capital access |

#### Add-On Agents (User Selects)

| Agent ID | Display Name | Named After | Domain | Primary Value |
|----------|--------------|-------------|--------|---------------|
| `ricardo` | The Ricardo | David Ricardo (1772-1823) | Export & Trade | International market entry, trade compliance |
| `lovelace` | The Lovelace | Ada Lovelace (1815-1852) | Digital & Technology | Tech stack assessment, digital transformation |
| `mayo` | The Mayo | Elton Mayo (1880-1949) | HR & Organization | Workforce optimization, culture, skills gaps |
| `ohno` | The Ohno | Taiichi Ohno (1912-1990) | Supply Chain & Lean | Lean operations, logistics, inventory optimization |
| `porter` | The Porter | Michael Porter (1947-) | Market & Competition | Competitive strategy, market positioning |
| `landor` | The Landor | Walter Landor (1913-1995) | Packaging & Brand | Export packaging, labeling compliance, brand |

#### Utility Agents (Always Execute)

| Agent ID | Display Name | Named After | Domain | Primary Value |
|----------|--------------|-------------|--------|---------------|
| `deming` | The Deming | W. Edwards Deming (1900-1993) | Quality Validation | Cross-agent validation, consistency checking |
| `tufte` | The Tufte | Edward Tufte (1942-) | Report Generation | Report synthesis, data visualization |

### 2.3 Agent-to-Dimension Mapping

Each agent draws from specific dimensions of the sector knowledge packs:

```python
AGENT_DIMENSION_MAPPING = {
    # Core Agents
    "drucker": [1, 11],                    # Industry Classification, MENA Context
    "marvin": [1, 3, 4, 7, 8],             # Classification, Ops, Regulatory, Workforce, Supply
    "graham": [2, 1, 11],                  # Financial, Classification, MENA
    
    # Add-On Agents
    "ricardo": [9, 10, 4, 11],             # Export, Packaging, Regulatory, MENA
    "lovelace": [6, 3, 7],                 # Digital, Ops, Workforce
    "mayo": [7, 1, 11],                    # Workforce, Classification, MENA
    "ohno": [8, 3, 6, 7],                  # Supply Chain, Ops, Digital, Workforce
    "porter": [5, 1, 2, 11],               # Competitive, Classification, Financial, MENA
    "landor": [10, 9, 11],                 # Packaging, Export, MENA
    
    # Utility Agents
    "tufte": list(range(1, 12)),           # All dimensions (for report generation)
    "deming": list(range(1, 12)),          # All dimensions (for validation)
}
```

---

## Part 3: The &Eye Lens System

### 3.1 Lens Architecture

The &Eye is RootRise's transformation lens system. Each lens represents a strategic goal that reframes how the diagnostic is prioritized and presented.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                          THE &EYE LENS SYSTEM                                │
│                    "See Your Business Through Any Lens"                      │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   Same diagnostic data → Different strategic emphasis → Tailored roadmap    │
│                                                                              │
│   Example: A food manufacturer with the same assessment results:            │
│                                                                              │
│   Through THE CREMA lens (pre-selected):                                    │
│   → Quick wins achievable in 30-60-90 days across all dimensions            │
│                                                                              │
│   Through INVESTMENT READINESS lens:                                        │
│   → Focus on governance gaps, financial documentation, audit readiness      │
│                                                                              │
│   Through EXPORT READINESS lens:                                            │
│   → Focus on certifications, packaging compliance, market entry strategy    │
│                                                                              │
│   Through OPERATIONAL EXCELLENCE lens:                                      │
│   → Focus on OEE improvement, waste reduction, quality systems              │
│                                                                              │
│   The Crema can COMBINE with other lenses to filter for quick wins          │
│   within that transformation objective!                                     │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Complete Lens Roster (17 Lenses)

#### Featured Lens

| Lens ID | Name | Category | Core Question | Primary Agents | Behavior |
|---------|------|----------|---------------|----------------|----------|
| **EYE-CREMA** | The Crema | Featured | What can I achieve in 30-60-90 days? | Ohno (P1), Graham, Marvin | Pre-selected by default, combines with all lenses |

#### Growth Lenses

| Lens ID | Name | Category | Core Question | Primary Agents |
|---------|------|----------|---------------|----------------|
| **EYE-001** | Export Readiness | Growth | Is this business ready to compete internationally? | Ricardo (P1), Landor, Marvin |
| **EYE-002** | Investment Readiness | Growth | If an investor evaluated this business tomorrow, what would they find? | Graham (P1), Marvin, Porter |
| **EYE-005** | Market Expansion | Growth | What growth opportunities exist domestically and regionally? | Porter (P1), Ricardo, Graham |
| **EYE-006** | Brand Building | Growth | How strong is brand positioning and market presence? | Landor (P1), Porter, Lovelace |

#### Operations Lenses

| Lens ID | Name | Category | Core Question | Primary Agents |
|---------|------|----------|---------------|----------------|
| **EYE-003** | Digital Transformation | Operations | How digitally mature is this business and what's the transformation path? | Lovelace (P1), Marvin, Graham |
| **EYE-004** | Operational Excellence | Operations | How efficient and consistent are operations? | Marvin (P1), Ohno, Graham |
| **EYE-012** | Cost Optimization | Operations | Where are the efficiency and cost reduction opportunities? | Graham (P1), Ohno, Marvin |

#### Impact Lenses

| Lens ID | Name | Category | Core Question | Primary Agents |
|---------|------|----------|---------------|----------------|
| **EYE-007** | Workforce Development | Impact | Is the workforce optimized for current and future needs? | Mayo (P1), Marvin, Graham |
| **EYE-008** | Supply Chain Optimization | Impact | How resilient and efficient is the supply chain? | Ohno (P1), Marvin, Ricardo |
| **EYE-009** | Sustainability & ESG | Impact | What is the environmental and social impact profile? | Marvin (P1), Ohno, Graham |
| **EYE-010** | Innovation & R&D | Impact | Is the business positioned for product/service innovation? | Lovelace (P1), Porter, Marvin |
| **EYE-011** | Customer Experience | Impact | How effectively does the business serve customers? | Porter (P1), Lovelace, Landor |
| **EYE-013** | Risk & Resilience | Impact | How prepared is the business for disruption? | Marvin (P1), Ohno, Graham |

#### Transition Lenses

| Lens ID | Name | Category | Core Question | Primary Agents |
|---------|------|----------|---------------|----------------|
| **EYE-014** | Succession & Governance | Transition | Is the business prepared for leadership transition? | Graham (P1), Mayo, Marvin |
| **EYE-015** | Partnership & M&A | Transition | Is the business positioned for strategic partnerships or acquisition? | Graham (P1), Porter, Marvin |

#### Custom Lens

| Lens ID | Name | Category | Core Question | Primary Agents | Behavior |
|---------|------|----------|---------------|----------------|----------|
| **EYE-CUSTOM** | Custom Objective | Custom | User-defined transformation goal | AI-determined based on description | Exclusive (cannot combine with standard lenses, can combine with Crema) |

### 3.3 The Crema — Signature Feature

The Crema is RootRise's **signature differentiator**. While competitors deliver overwhelming reports, The Crema answers what every SME owner asks first: *"What can I do RIGHT NOW?"*

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                              THE CREMA ☕                                     │
│                    "Quick Wins in 30-60-90 Days"                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   BEHAVIOR:                                                                  │
│   • Pre-selected by default (user can deselect)                             │
│   • Combines with ANY other lens (acts as a filter)                         │
│   • Extracts highest-value, lowest-effort improvements                      │
│                                                                              │
│   FILTERING CRITERIA:                                                        │
│   • Effort: Low or Medium only                                              │
│   • Impact: High or Very High only                                          │
│   • Timeline: ≤90 days                                                      │
│   • Dependencies: Minimal external                                           │
│   • Risk: Low to Medium                                                     │
│                                                                              │
│   COMBINATION EXAMPLES:                                                      │
│   • Crema alone → All quick wins across all dimensions                      │
│   • Crema + Export Readiness → Export actions achievable in 90 days         │
│   • Crema + Investment Readiness → Investor-ready quick fixes               │
│   • Crema + Cost Optimization → Immediate margin improvements               │
│                                                                              │
│   OUTPUT STRUCTURE:                                                          │
│   • 30-Day Actions (Immediate Wins)                                         │
│   • 60-Day Actions (Short-Term Gains)                                       │
│   • 90-Day Actions (Foundational Changes)                                   │
│   • Momentum Metrics (how to measure progress)                              │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.4 Custom Objective Lens

For goals not covered by the 15 predefined lenses:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           CUSTOM OBJECTIVE ✨                                │
│                    "Your Goal. Your Transformation."                         │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   USER INPUT:                                                                │
│   User describes their specific goal in 50-1000 characters                  │
│   Example: "I want to become a certified supplier to multinational          │
│   food companies in the Gulf region..."                                     │
│                                                                              │
│   AI INTERPRETATION (by The Drucker):                                       │
│   1. Identifies key themes from description                                 │
│   2. Maps to relevant agents with priority weights                          │
│   3. Determines dimension priorities                                        │
│   4. Configures report structure                                            │
│   5. Shows user interpretation for confirmation                             │
│                                                                              │
│   BEHAVIOR:                                                                  │
│   • EXCLUSIVE: Cannot combine with standard lenses                          │
│   • CAN combine with The Crema                                              │
│   • Requires user confirmation of AI interpretation                         │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.5 Lens Configuration Schema

```typescript
interface LensConfiguration {
  lens_id: string;                        // e.g., "EYE-002", "EYE-CREMA"
  lens_name: string;                      // e.g., "Investment Readiness"
  lens_name_ar: string;                   // Arabic name
  category: "featured" | "growth" | "operations" | "impact" | "transition" | "custom";
  
  // Strategic Context
  user_goal: string;                      // What the user wants to achieve
  core_question: string;                  // The central diagnostic question
  key_insight: string;                    // The lens philosophy
  
  // Behavior Flags
  is_featured: boolean;                   // The Crema = true
  is_default_selected: boolean;           // The Crema = true
  allows_combination: boolean;            // Standard lenses = true, Custom = false
  can_combine_with_crema: boolean;        // All = true
  
  // Agent Prioritization
  agent_priorities: {
    agent_id: string;
    priority: "P1" | "P2" | "P3";         // P1 = Primary, P2 = Supporting, P3 = Context
    weight: number;                       // 0.0-1.5 weighting
    focus_areas: string[];                // Which aspects to emphasize
  }[];
  
  // Auto-select agents based on lens
  auto_select_agents: string[];           // Agents automatically included
  
  // Output Customization
  output_emphasis: string[];              // What to highlight in report
  quick_win_criteria: string[];           // How to identify quick wins
  roadmap_focus: string[];                // What transformation roadmap emphasizes
  
  // Dimension Weights (adjust importance of 11 dimensions)
  dimension_weights: {
    [dimension_id: number]: number;       // 1-11 → weight multiplier
  };
}
```

### 3.6 Lens-Agent Priority Matrix

```
┌───────────────────────────────────────────────────────────────────────────────────────┐
│                           AGENT PRIORITY BY LENS                                       │
├──────────────────┬──────┬──────┬───────┬────────┬─────┬─────┬──────┬─────┬────────────┤
│                  │Graham│Marvin│Ricardo│Lovelace│Mayo │Ohno │Porter│Lndor│AUTO-SELECT │
├──────────────────┼──────┼──────┼───────┼────────┼─────┼─────┼──────┼─────┼────────────┤
│EYE-CREMA Crema   │  P2  │  P2  │       │        │     │ P1  │      │     │ None       │
├──────────────────┼──────┼──────┼───────┼────────┼─────┼─────┼──────┼─────┼────────────┤
│EYE-001 Export    │      │  P2  │  P1   │        │     │     │      │ P2  │ Ricardo,   │
│                  │      │      │       │        │     │     │      │     │ Landor     │
│EYE-002 Investment│  P1  │  P2  │       │        │     │     │  P2  │     │ Porter     │
│EYE-005 Market    │  P2  │      │  P2   │        │     │     │  P1  │     │ Porter     │
│EYE-006 Brand     │      │      │       │   P2   │     │     │  P2  │ P1  │ Landor,    │
│                  │      │      │       │        │     │     │      │     │ Porter     │
├──────────────────┼──────┼──────┼───────┼────────┼─────┼─────┼──────┼─────┼────────────┤
│EYE-003 Digital   │  P2  │  P2  │       │   P1   │     │     │      │     │ Lovelace   │
│EYE-004 Operations│  P2  │  P1  │       │        │     │ P2  │      │     │ Ohno       │
│EYE-012 Cost      │  P1  │  P2  │       │        │     │ P2  │      │     │ Ohno       │
├──────────────────┼──────┼──────┼───────┼────────┼─────┼─────┼──────┼─────┼────────────┤
│EYE-007 Workforce │  P2  │  P2  │       │        │ P1  │     │      │     │ Mayo       │
│EYE-008 Supply    │      │  P2  │  P2   │        │     │ P1  │      │     │ Ohno       │
│EYE-009 ESG       │  P2  │  P1  │       │        │     │ P2  │      │     │ Ohno       │
│EYE-010 Innovation│      │  P2  │       │   P1   │     │     │  P2  │     │ Lovelace   │
│EYE-011 Customer  │      │      │       │   P2   │     │     │  P1  │ P2  │ Porter     │
│EYE-013 Risk      │  P2  │  P1  │       │        │     │ P2  │      │     │ None       │
├──────────────────┼──────┼──────┼───────┼────────┼─────┼─────┼──────┼─────┼────────────┤
│EYE-014 Succession│  P1  │  P2  │       │        │ P2  │     │      │     │ Mayo       │
│EYE-015 M&A       │  P1  │  P2  │       │        │     │     │  P2  │     │ Porter     │
├──────────────────┼──────┼──────┼───────┼────────┼─────┼─────┼──────┼─────┼────────────┤
│EYE-CUSTOM        │ (AI-determined based on user description)       │ Varies     │
└──────────────────┴──────┴──────┴───────┴────────┴─────┴─────┴──────┴─────┴────────────┘

P1 = Primary Agent (highest weight, detailed analysis)
P2 = Supporting Agent (moderate weight, contextual analysis)
Empty = Context only (low weight, if selected by user)
AUTO-SELECT = Agents automatically included when this lens is selected
```

### 3.7 Lens Selection Rules

```typescript
interface LensSelectionRules {
  // The Crema
  crema: {
    is_default_selected: true;
    can_be_deselected: true;
    combines_with_all: true;
    behavior_when_combined: "filter";     // Filters other lens results for quick wins
  };
  
  // Standard lenses (EYE-001 through EYE-015)
  standard: {
    max_simultaneous: 3;
    can_combine_with_each_other: true;
    can_combine_with_crema: true;
  };
  
  // Custom lens
  custom: {
    is_exclusive: true;                   // Cannot combine with standard lenses
    can_combine_with_crema: true;
    requires_user_input: true;
    requires_ai_interpretation: true;
    requires_user_confirmation: true;
  };
}
```

---

## Part 4: Sector Knowledge Architecture

### 4.1 Sector Coverage (31 Sectors)

#### Industrial Sectors (14)

| # | Sector ID | Sector Name | Size | Version |
|---|-----------|-------------|------|---------|
| 1 | `agriculture_agribusiness` | Agriculture & Agribusiness | 79KB | 2.0 |
| 2 | `automotive` | Automotive | 78KB | 2.0 |
| 3 | `chemicals_plastics` | Chemicals, Plastics & Specialty | 80KB | 2.0 |
| 4 | `construction_building` | Construction & Building | 86KB | 2.0 |
| 5 | `electronics_manufacturing` | Electronics Manufacturing | 92KB | 1.0 |
| 6 | `energy_utilities` | Energy & Utilities | 91KB | 1.0 |
| 7 | `filling_bottling` | Filling & Bottling | 85KB | 1.0 |
| 8 | `food_beverage_manufacturing` | Food & Beverage Manufacturing | 97KB | 1.0 |
| 9 | `furniture_manufacturing` | Furniture Manufacturing | 83KB | 1.0 |
| 10 | `metal_fabrication` | Metal Fabrication & Manufacturing | 65KB | 2.0 |
| 11 | `paper_printing` | Paper & Printing | 81KB | 1.0 |
| 12 | `pharmaceuticals` | Pharmaceuticals Manufacturing | 78KB | 2.0 |
| 13 | `plastics_manufacturing` | Plastics Manufacturing | 80KB | 1.0 |
| 14 | `textiles_apparel` | Textiles & Apparel | 84KB | 2.0 |

#### Services Sectors (15)

| # | Sector ID | Sector Name | Size | Version |
|---|-----------|-------------|------|---------|
| 15 | `beauty_wellness` | Beauty & Wellness | 90KB | 1.0 |
| 16 | `education_training` | Education & Training | 78KB | 2.0 |
| 17 | `environmental_services` | Environmental Services | 84KB | 1.0 |
| 18 | `financial_services` | Financial Services | 76KB | 2.0 |
| 19 | `healthcare_services` | Healthcare Services | 83KB | 2.0 |
| 20 | `hospitality_tourism` | Hospitality & Tourism | 86KB | 2.0 |
| 21 | `logistics_transportation` | Logistics & Transportation | 80KB | 2.0 |
| 22 | `maintenance_repair` | Maintenance & Repair Services | 87KB | 1.0 |
| 23 | `professional_services` | Professional Services | 80KB | 2.0 |
| 24 | `real_estate` | Real Estate | 76KB | 2.0 |
| 25 | `retail_commerce` | Retail & Commerce | 81KB | 2.0 |
| 26 | `security_services` | Security Services | 86KB | 1.0 |
| 27 | `technology_it` | Technology & IT Services | 81KB | 2.0 |
| 28 | `telecommunications` | Telecommunications | 91KB | 1.0 |
| 29 | `trading_distribution` | Trading & Distribution | 100KB | 1.0 |

#### Creative Sectors (1)

| # | Sector ID | Sector Name | Size | Version |
|---|-----------|-------------|------|---------|
| 30 | `creative_industries` | Creative Industries | 96KB | 1.0 |

#### Micro Enterprise (1)

| # | Sector ID | Sector Name | Size | Version |
|---|-----------|-------------|------|---------|
| 31 | `home_based_micro` | Home-Based & Micro Enterprise | 100KB | 1.0 |

**Total: 31 sectors | ~2.6 MB | ~60,000 lines**

### 4.2 Enhanced 11-Dimension Framework

Each sector knowledge pack contains:

```typescript
interface SectorKnowledgePack {
  // METADATA
  metadata: {
    sector_id: string;
    sector_name: string;
    sector_name_ar: string;
    version: string;
    last_updated: string;
    sector_type: "industrial" | "services" | "creative" | "micro";
    data_sources: DataSource[];
    applicable_countries: string[];       // ["EG", "SA", "AE", "JO", "LB", "MA"]
    sme_size_range: SMESizeRange;
  };

  // THE 11 DIMENSIONS
  industry_classification: IndustryClassification;      // Dimension 1
  financial_benchmarks: FinancialBenchmarks;            // Dimension 2
  operational_kpis: OperationalKPIs;                    // Dimension 3
  regulatory_landscape: RegulatoryLandscape;            // Dimension 4
  competitive_dynamics: CompetitiveDynamics;            // Dimension 5
  digital_maturity: DigitalMaturityProfile;             // Dimension 6
  workforce_norms: WorkforceNorms;                      // Dimension 7
  supply_chain: SupplyChainProfile;                     // Dimension 8
  export_requirements: ExportRequirements;              // Dimension 9
  packaging_labeling: PackagingLabelingStandards;       // Dimension 10
  mena_context: MENARegionalContext;                    // Dimension 11

  // ENHANCED FEATURES (v2.0)
  growth_pathways: {                                    // 5-stage growth model
    stages: GrowthStage[];                              // Startup → Major
    transition_guides: TransitionGuide[];
  };
  
  key_financial_insights: KeyFinancialInsights;         // Sector-specific insights
  
  strategic_summary: {                                  // Success/failure patterns
    critical_success_factors: string[];
    common_failure_patterns: string[];
    red_flags: RedFlag[];
    positive_indicators: PositiveIndicator[];
  };

  // SUBSECTOR OVERRIDES
  subsectors: SubsectorOverride[];
}
```

### 4.3 Vector Database Design

#### Collection Schema (Qdrant)

```python
sector_knowledge_schema = {
    "collection_name": "sector_knowledge",
    "vectors_config": {
        "size": 1536,           # OpenAI text-embedding-3-small
        "distance": "Cosine"
    },
    "on_disk_payload": True
}

chunk_payload = {
    # Identity
    "chunk_id": "string",
    "sector_id": "string",
    "sector_name": "string",
    
    # Classification
    "dimension": "integer",         # 1-11 (or 12 for growth, 13 for strategic)
    "dimension_name": "string",
    
    # Geographic
    "country_code": "string|null",
    "applicable_countries": "array[string]",
    
    # Content
    "content": "string",
    "heading_path": "string",
    
    # Confidence Metadata (&I)
    "source_reliability": "float",  # 0-1
    "confidence_score": "float",    # 0-1
    
    # Versioning
    "pack_version": "string",
    "indexed_at": "string"
}
```

#### Resource Estimates

| Resource | Specification | Rationale |
|----------|---------------|-----------|
| Storage | ~8GB initial, scalable to 100GB | 31 sectors × ~2500 chunks × 2KB avg + embeddings |
| RAM | 16GB recommended | In-memory indexing for fast retrieval |
| Collections | 1 primary + 1 auxiliary | sector_knowledge + custom_context |
| Embedding Model | OpenAI text-embedding-3-small (1536 dims) | Balance of quality/cost |
| Embedding Cost | ~$0.02 per 1M tokens | One-time indexing ~$10 |
| Query Latency | <100ms p95 | With proper indexing |

---

## Part 5: Questionnaire System

### 5.1 Questionnaire Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        QUESTIONNAIRE ARCHITECTURE                            │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   DESIGN PRINCIPLES:                                                         │
│   • Conversational — Questions feel like consultation, not bureaucracy       │
│   • Progressive — Core questions first, details unlock based on responses    │
│   • Agent-Aligned — Every question maps to specific agent data needs         │
│   • &I Philosophy — Human context injection points throughout                │
│   • MENA-Ready — Arabic translations, regional context options               │
│   • Time-Respectful — 20-30 minutes total, with save/resume                  │
│                                                                              │
│   COMPLETION TIMES:                                                          │
│   • Core sections (always shown): ~12 minutes                                │
│   • Full diagnostic (all add-ons): ~31 minutes                               │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 5.2 Section Structure

| Section | Code | Questions | Est. Time | Condition | Primary Agents |
|---------|------|-----------|-----------|-----------|----------------|
| Business Profile | BP | 15 + 4 conditional | 3 min | Always | Drucker, All |
| Financial Health | FH | 20 + 5 conditional | 5 min | Always | Graham |
| Operations & Production | OP | 17 + 3 conditional | 4 min | Always | Marvin |
| Digital Maturity | DM | 12 + 1 conditional | 3 min | If Lovelace selected | Lovelace |
| Workforce & HR | WF | 11 | 3 min | If Mayo selected | Mayo |
| Market & Competition | MK | 10 | 2 min | If Porter selected | Porter |
| Supply Chain | SC | 12 | 3 min | If Ohno selected | Ohno |
| Export Readiness | EX | 15 + 2 conditional | 4 min | If Ricardo selected | Ricardo, Landor |
| Brand & Marketing | BR | 10 | 2 min | If Landor selected | Landor |
| Compliance & Certifications | CC | 8 | 2 min | Contextual | Marvin, Ricardo |
| **TOTAL (Core)** | - | **53** | **12 min** | - | - |
| **TOTAL (Full)** | - | **~145** | **31 min** | - | - |

---

## Part 6: Memory Architecture

### 6.1 Memory Layer Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                          MEMORY ARCHITECTURE                                 │
│                    (Human-AI Collaborative Memory)                           │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                    SHORT-TERM MEMORY (Session)                       │    │
│  │  Storage: Redis (TTL: 24 hours)                                      │    │
│  ├─────────────────────────────────────────────────────────────────────┤    │
│  │  • Conversation context within diagnostic session                    │    │
│  │  • User responses to questionnaire (progressive)                     │    │
│  │  • Agent findings accumulated during session                         │    │
│  │  • Current state of diagnostic workflow                              │    │
│  │  • [&I] Human clarifications and context injections                  │    │
│  │  • [&I] Human override flags with timestamps                         │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                    LONG-TERM MEMORY (Persistent)                     │    │
│  │  Storage: PostgreSQL + S3 (document store)                           │    │
│  ├─────────────────────────────────────────────────────────────────────┤    │
│  │  • SME profile (company info, sector, size, ownership)               │    │
│  │  • Historical diagnostic results (time series)                       │    │
│  │  • Benchmark comparisons over time                                   │    │
│  │  • User preferences and report settings                              │    │
│  │  • [&I] Human-provided local context (relationships, culture)        │    │
│  │  • [&I] Human annotations on past diagnostics                        │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                  CROSS-AGENT MEMORY (Shared State)                   │    │
│  │  Storage: LangGraph State Object (in-memory during execution)        │    │
│  ├─────────────────────────────────────────────────────────────────────┤    │
│  │  • How Graham's financial findings feed Porter's analysis            │    │
│  │  • How Marvin's operational data informs Mayo's HR assessment        │    │
│  │  • Shared SME context all agents can access                          │    │
│  │  • Conflict resolution when agents have different views              │    │
│  │  • [&I] Human override flags propagated to all agents                │    │
│  │  • [&I] "Human said X" vs "AI inferred X" distinction                │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                  SECTOR KNOWLEDGE (Vector Store)                     │    │
│  │  Storage: Qdrant (self-hosted) or Pinecone (managed)                 │    │
│  ├─────────────────────────────────────────────────────────────────────┤    │
│  │  • 31 sector knowledge packs (11+ dimensions each)                   │    │
│  │  • Benchmarks, regulations, KPIs by sector/subsector/country         │    │
│  │  • [&I] Source attribution for every data point                      │    │
│  │  • [&I] Confidence metadata on benchmark reliability                 │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## Part 7: LangGraph Orchestration

### 7.1 Graph Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       LANGGRAPH ORCHESTRATION                                │
│                   (Human-in-the-Loop Native Design)                          │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   ┌─────────────┐                                                           │
│   │   START     │                                                           │
│   └──────┬──────┘                                                           │
│          │                                                                   │
│          ▼                                                                   │
│   ┌─────────────┐      GATE 1: Data Quality                                 │
│   │  DRUCKER    │◄─── Questionnaire coverage < 70%? Inconsistencies?        │
│   │(Supervisor) │      Also: Interprets Custom Lens if selected             │
│   └──────┬──────┘                                                           │
│          │                                                                   │
│   ┌──────┴──────┐                                                           │
│   │             │                                                            │
│   ▼             ▼                                                            │
│ ┌─────────┐ ┌─────────┐                                                     │
│ │ MARVIN  │ │ GRAHAM  │   ◄── Parallel Execution (Core Agents)              │
│ │(Diag)   │ │(Finance)│                                                     │
│ └────┬────┘ └────┬────┘                                                     │
│      └─────┬─────┘                                                           │
│            │                                                                 │
│            ▼                                                                 │
│     ┌─────────────┐     GATE 2: Finding Validation                          │
│     │  HITL Node  │◄─── Confidence < 70%? Cross-agent conflict?             │
│     │ (Conditional)│     Financial distress signals?                        │
│     └──────┬──────┘                                                         │
│            │                                                                 │
│   ┌────────┴────────────────────────────────────────┐                       │
│   │          ADD-ON AGENTS (Parallel)                │                       │
│   │  ┌────────┐ ┌────────┐ ┌────────┐ ┌────────┐   │                       │
│   │  │RICARDO │ │LOVELACE│ │  MAYO  │ │  OHNO  │   │ ◄── Only selected     │
│   │  │(Export)│ │(Digital)││  (HR)  │ │(Supply)│   │     agents execute    │
│   │  └────────┘ └────────┘ └────────┘ └────────┘   │     (+ auto-selected  │
│   │  ┌────────┐ ┌────────┐                          │     by lens)          │
│   │  │ PORTER │ │ LANDOR │                          │                       │
│   │  │(Market)│ │(Packag)│                          │                       │
│   │  └────────┘ └────────┘                          │                       │
│   └──────────────────┬──────────────────────────────┘                       │
│                      │                                                       │
│                      ▼                                                       │
│               ┌─────────────┐   GATE 3: Strategic Validation                 │
│               │  HITL Node  │◄── Total recommendations > $50K?               │
│               │ (Conditional)│   Major pivot suggested?                      │
│               └──────┬──────┘                                               │
│                      │                                                       │
│                      ▼                                                       │
│               ┌─────────────┐                                               │
│               │   DEMING    │◄── Quality Validation                         │
│               │  (Quality)  │    Cross-checks all outputs                   │
│               └──────┬──────┘                                               │
│                      │                                                       │
│                      ▼                                                       │
│               ┌─────────────┐                                               │
│               │   TUFTE     │◄── Report Generation                          │
│               │  (Reports)  │    Applies Lens priorities                    │
│               │             │    Applies Crema filter if active             │
│               └──────┬──────┘                                               │
│                      │                                                       │
│                      ▼                                                       │
│               ┌─────────────┐   GATE 4: Final Sign-off                      │
│               │  HITL Node  │◄── SME Owner reviews report                   │
│               │   (Final)   │    before delivery                            │
│               └──────┬──────┘                                               │
│                      │                                                       │
│                      ▼                                                       │
│               ┌─────────────┐                                               │
│               │    END      │                                               │
│               └─────────────┘                                               │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 7.2 HITL Trigger Conditions

```python
HITL_TRIGGER_CONDITIONS = {
    "gate_1_data_quality": {
        "questionnaire_coverage_below": 0.70,
        "inconsistencies_threshold": 3,
        "custom_lens_interpretation": True,   # Always review custom lens
        "handler": "embedded_associate",
        "blocking": True
    },
    "gate_2_finding_validation": {
        "agent_confidence_below": 0.70,
        "financial_distress_score_below": 40,
        "cross_agent_variance_above": 20,
        "handler": "senior_expert",
        "blocking_for": ["financial_distress", "regulatory_violation"]
    },
    "gate_3_strategic_validation": {
        "total_investment_above": 50000,
        "single_recommendation_above": 25000,
        "transformational_change_detected": True,
        "handler": "senior_expert",
        "blocking": False
    },
    "gate_4_final_signoff": {
        "always_trigger": True,
        "handler": "sme_owner",
        "blocking": False,
        "allows_feedback": True
    }
}
```

### 7.3 State Schema

```python
from typing import TypedDict, Annotated, List, Dict, Any, Optional
import operator

class PantheonState(TypedDict):
    """LangGraph state schema for The Pantheon diagnostic system."""
    
    # Session Context
    session_id: str
    sme_id: str
    
    # SME Profile
    sme_profile: Dict[str, Any]
    
    # Configuration
    selected_agents: List[str]
    sector_id: str
    subsector_id: Optional[str]
    selected_lenses: List[str]           # e.g., ["EYE-CREMA", "EYE-002"]
    custom_lens_description: Optional[str]  # If EYE-CUSTOM selected
    benchmark_set: str
    language: str
    
    # Sector Intelligence
    sector_intelligence: Dict[str, Any]
    
    # Lens Configuration (computed)
    active_lens_configs: List[Dict[str, Any]]
    computed_agent_weights: Dict[str, float]  # Combined weights from all lenses
    crema_active: bool                        # Is The Crema filtering enabled?
    custom_lens_interpretation: Optional[Dict[str, Any]]  # AI interpretation
    
    # Questionnaire
    questionnaire_responses: List[Dict[str, Any]]
    
    # Agent Outputs (accumulated)
    agent_outputs: Annotated[Dict[str, Dict], operator.or_]
    
    # &I Features
    human_context: List[Dict[str, Any]]
    human_overrides: List[Dict[str, Any]]
    pending_validations: List[Dict[str, Any]]
    resolved_validations: List[Dict[str, Any]]
    
    # Execution
    current_phase: str
    execution_order: List[str]
    completed_agents: List[str]
    errors: List[Dict[str, Any]]
    
    # Output
    final_report: Optional[Dict[str, Any]]
    
    # Audit
    audit_log: Annotated[List[Dict], operator.add]
```

---

## Part 8: API Specification

### 8.1 Core Endpoints

```yaml
# Diagnostic Flow
POST   /diagnostic/initiate              # Start new diagnostic
POST   /diagnostic/{id}/respond          # Submit questionnaire responses
GET    /diagnostic/{id}/status           # Get current status
GET    /diagnostic/{id}/report           # Get completed report
POST   /diagnostic/{id}/feedback         # Submit feedback on report

# &I Override Endpoints
POST   /diagnostic/{id}/pause            # Pause for human review
POST   /diagnostic/{id}/override         # Override AI finding
POST   /diagnostic/{id}/inject-context   # Inject human context
POST   /diagnostic/{id}/skip-agent       # Skip specific agent
POST   /diagnostic/{id}/request-human-review  # Request expert review

# &I Transparency Endpoints
GET    /diagnostic/{id}/reasoning        # Get AI reasoning trace
GET    /diagnostic/{id}/confidence-map   # Get confidence scores
GET    /diagnostic/{id}/sources          # Get data sources used
GET    /diagnostic/{id}/uncertainties    # Get what AI doesn't know
GET    /diagnostic/{id}/explain/{finding}  # Explain specific finding

# Lens Endpoints
GET    /config/lenses                    # List all 17 lenses
GET    /config/lenses/{id}               # Get lens configuration
POST   /config/lenses/validate           # Validate lens combination
POST   /config/lenses/interpret-custom   # Interpret custom objective

# SME Management
POST   /sme/register                     # Register new SME
GET    /sme/{id}/profile                 # Get SME profile
PUT    /sme/{id}/profile                 # Update profile
GET    /sme/{id}/history                 # Get diagnostic history

# Configuration
GET    /config/sectors                   # List 31 sectors
GET    /config/sectors/{id}              # Get sector details
GET    /config/agents                    # List 11 agents
```

### 8.2 Diagnostic Initiation (with Lenses)

```typescript
// POST /diagnostic/initiate
interface InitiateDiagnosticRequest {
  sme_id: string;
  configuration: {
    selected_agents: string[];           // Core agents auto-included
    sector_id: string;
    subsector_id?: string;
    
    // Lens Configuration
    selected_lenses: string[];           // e.g., ["EYE-CREMA", "EYE-002"]
    custom_lens_description?: string;    // Required if "EYE-CUSTOM" in selected_lenses
    
    report_format: "executive_summary" | "detailed" | "presentation" | "dashboard";
    language: "en" | "ar" | "bilingual";
    benchmark_set: "mena_regional" | "industry_specific" | "global" | "custom";
  };
}

interface InitiateDiagnosticResponse {
  session_id: string;
  status: "initialized";
  
  // Computed configuration
  computed_configuration: {
    final_agent_list: string[];          // Including auto-selected by lenses
    agent_weights: Record<string, number>;
    crema_active: boolean;
    custom_lens_interpretation?: CustomLensInterpretation;
  };
  
  questionnaire_url: string;
  estimated_completion_time: string;
  sections: QuestionnaireSection[];
}
```

---

## Part 9: Deployment Architecture

### 9.1 Infrastructure Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        DEPLOYMENT ARCHITECTURE                               │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                         LOAD BALANCER                                │    │
│  │                    (AWS ALB / CloudFlare)                            │    │
│  └───────────────────────────────┬─────────────────────────────────────┘    │
│                                  │                                          │
│  ┌───────────────────────────────┼─────────────────────────────────────┐    │
│  │                         API LAYER                                    │    │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐                   │    │
│  │  │  FastAPI    │  │  FastAPI    │  │  FastAPI    │   (Auto-scaling)  │    │
│  │  │  Instance   │  │  Instance   │  │  Instance   │                   │    │
│  │  └─────────────┘  └─────────────┘  └─────────────┘                   │    │
│  └───────────────────────────────┬─────────────────────────────────────┘    │
│                                  │                                          │
│  ┌───────────────────────────────┼─────────────────────────────────────┐    │
│  │                      MESSAGE QUEUE (Redis)                           │    │
│  │  • diagnostic_sessions  • agent_tasks  • hitl_validations            │    │
│  └───────────────────────────────┬─────────────────────────────────────┘    │
│                                  │                                          │
│  ┌───────────────────────────────┼─────────────────────────────────────┐    │
│  │                     LANGGRAPH WORKERS                                │    │
│  │  ┌───────────┐  ┌───────────┐  ┌───────────┐  (Auto-scaling)        │    │
│  │  │ Worker    │  │ Worker    │  │ Worker    │                         │    │
│  │  └───────────┘  └───────────┘  └───────────┘                         │    │
│  └───────────────────────────────┬─────────────────────────────────────┘    │
│                                  │                                          │
│  ┌───────────────────────────────┴─────────────────────────────────────┐    │
│  │                        DATA LAYER                                    │    │
│  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐                │    │
│  │  │  PostgreSQL  │  │    Redis     │  │   Qdrant     │                │    │
│  │  │  (Profiles)  │  │  (Sessions)  │  │  (Vectors)   │                │    │
│  │  └──────────────┘  └──────────────┘  └──────────────┘                │    │
│  │  ┌──────────────┐  ┌──────────────┐                                  │    │
│  │  │     S3       │  │   SQLite     │                                  │    │
│  │  │  (Reports)   │  │ (Checkpoints)│                                  │    │
│  │  └──────────────┘  └──────────────┘                                  │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 9.2 Technology Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| API | FastAPI | REST endpoints, OpenAPI docs |
| Orchestration | LangGraph | Multi-agent workflow |
| Session Store | Redis | Short-term memory, TTL 24h |
| Database | PostgreSQL | Long-term storage, profiles |
| Vector DB | Qdrant | 31 sector knowledge packs |
| Object Store | S3 | Reports, documents |
| Checkpoints | SQLite | LangGraph state persistence |
| LLM | OpenAI GPT-4o | Agent intelligence |
| Embeddings | OpenAI text-embedding-3-small | Vector generation |

---

## Part 10: Resource Estimates

### 10.1 Infrastructure Costs (Monthly)

| Component | Specification | Monthly Cost |
|-----------|---------------|--------------|
| API Servers | 2-4 × t3.medium | $60-120 |
| LangGraph Workers | 2-6 × c6i.large | $120-360 |
| PostgreSQL | db.t3.medium | $50 |
| Redis | cache.t3.medium | $45 |
| Qdrant | t3.large (8GB RAM) | $60 |
| S3 Storage | 500GB | $12 |
| Load Balancer | ALB | $25 |
| **Subtotal Compute** | | **$372-672** |

| External Service | Usage | Monthly Cost |
|------------------|-------|--------------|
| OpenAI GPT-4o | 100 diagnostics × 50K tokens | $250 |
| OpenAI Embeddings | Incremental | $5 |
| SendGrid | 1000 emails | $15 |
| **Subtotal APIs** | | **$270** |

| **TOTAL** | **@ 100 diagnostics/month** | **$642-942** |

### 10.2 Scaling Projections

| Diagnostics/Month | Infrastructure | API Costs | Total |
|-------------------|----------------|-----------|-------|
| 100 | $670 | $270 | $940 |
| 500 | $1,200 | $1,350 | $2,550 |
| 1,000 | $2,000 | $2,700 | $4,700 |
| 5,000 | $5,000 | $13,500 | $18,500 |

### 10.3 Development Timeline

| Phase | Duration | Focus |
|-------|----------|-------|
| Phase 1: Foundation | 4 weeks | PostgreSQL, Redis, FastAPI, Auth |
| Phase 2: Memory & State | 3 weeks | Session management, human context/override |
| Phase 3: LangGraph | 3 weeks | State schema, nodes, HITL gates, checkpoints |
| Phase 4: Agents | 3 weeks | Core agents, add-on agents, utility agents |
| Phase 5: Vector DB | 2 weeks | Chunking pipeline, indexing 31 sectors |
| Phase 6: Questionnaire | 2 weeks | 10 sections, validation, agent mapping |
| Phase 7: Lens System | 2 weeks | 17 lenses, priority weighting, Crema filter |
| Phase 8: API | 2 weeks | Full REST API, WebSocket, docs |
| Phase 9: Testing | 2 weeks | Integration, load, security |
| Phase 10: Deployment | 1 week | Infrastructure, CI/CD, monitoring |
| **TOTAL** | **24 weeks** | |

---

## Appendix A: Complete Lens Index

### Featured

| ID | Name | Icon | Category |
|----|------|------|----------|
| EYE-CREMA | The Crema | ☕ | Featured |

### Growth

| ID | Name | Icon | Category |
|----|------|------|----------|
| EYE-001 | Export Readiness | 🌍 | Growth |
| EYE-002 | Investment Readiness | 💰 | Growth |
| EYE-005 | Market Expansion | 📈 | Growth |
| EYE-006 | Brand Building | 🎨 | Growth |

### Operations

| ID | Name | Icon | Category |
|----|------|------|----------|
| EYE-003 | Digital Transformation | 💻 | Operations |
| EYE-004 | Operational Excellence | ⚙️ | Operations |
| EYE-012 | Cost Optimization | 📊 | Operations |

### Impact

| ID | Name | Icon | Category |
|----|------|------|----------|
| EYE-007 | Workforce Development | 👥 | Impact |
| EYE-008 | Supply Chain Optimization | 🔗 | Impact |
| EYE-009 | Sustainability & ESG | 🌱 | Impact |
| EYE-010 | Innovation & R&D | 💡 | Impact |
| EYE-011 | Customer Experience | ⭐ | Impact |
| EYE-013 | Risk & Resilience | 🛡️ | Impact |

### Transition

| ID | Name | Icon | Category |
|----|------|------|----------|
| EYE-014 | Succession & Governance | 👤 | Transition |
| EYE-015 | Partnership & M&A | 🤝 | Transition |

### Custom

| ID | Name | Icon | Category |
|----|------|------|----------|
| EYE-CUSTOM | Custom Objective | ✨ | Custom |

---

## Appendix B: Agent Dependencies

```
                    ┌──────────────┐
                    │   DRUCKER    │
                    │ (Supervisor) │
                    └──────┬───────┘
                           │
              ┌────────────┴────────────┐
              │                         │
              ▼                         ▼
       ┌──────────┐              ┌──────────┐
       │  MARVIN  │              │  GRAHAM  │
       │  (Diag)  │              │(Finance) │
       └────┬─────┘              └────┬─────┘
            │                         │
    ┌───────┼───────┐         ┌──────┼──────┐
    │       │       │         │      │      │
    ▼       ▼       ▼         ▼      ▼      ▼
┌──────┐┌──────┐┌──────┐ ┌──────┐┌──────┐┌──────┐
│OHNO  ││MAYO  ││LOVELCE││PORTER││RICARDO││LANDOR│
│Supply││ HR   ││Digital││Market││Export ││Packag│
└──┬───┘└──┬───┘└───┬───┘└──┬───┘└───┬───┘└───┬──┘
   │       │        │       │        │        │
   └───────┴────────┴───────┴────────┴────────┘
                         │
                         ▼
                  ┌──────────┐
                  │  DEMING  │
                  │(Quality) │
                  └────┬─────┘
                       │
                       ▼
                  ┌──────────┐
                  │  TUFTE   │
                  │(Reports) │
                  └──────────┘
```

---

## Appendix C: Glossary

| Term | Definition |
|------|------------|
| **&I Philosophy** | AI + Human collaboration principle: AI augments, never replaces, human judgment |
| **The Pantheon** | Collective name for RootRise's 11 AI agents |
| **The &Eye** | RootRise's 17 transformation lenses that reframe diagnostic priorities |
| **The Crema** | Featured lens extracting quick wins achievable in 30-60-90 days |
| **My Sector** | The 31 sector knowledge packs providing industry intelligence |
| **HITL** | Human-in-the-Loop - checkpoints where human review is triggered |
| **Sector Knowledge Pack** | Structured intelligence file (11+ dimensions) for a specific industry |
| **Validation Gate** | One of 4 HITL checkpoints in the diagnostic workflow |
| **Confidence Score** | 0-1 metric indicating AI certainty in a finding |
| **Human Context Injection** | User-provided local knowledge that AI incorporates |
| **Human Override** | User correction of an AI-generated finding |
| **TIO** | The Ionganic Orchestrator - Tee's role title |
| **iOnganic** | Fusion of organic (human) and inorganic (AI) |

---

## Document Metadata

```yaml
document_type: "Technical Infrastructure Blueprint"
version: "1.2"
last_updated: "2026-01-06"
status: "Implementation Ready"
author: "Tee (The Ionganic Orchestrator - TIO)"
for: "Ahmed El-Gazzar (Technical DevOps Lead)"

changes_from_v1.1:
  - Added The Crema (EYE-CREMA) as featured lens
  - Added Custom Objective (EYE-CUSTOM) lens
  - Updated lens count from 15 to 17
  - Fixed lens numbering to match &Eye folder structure
  - Added lens categories (Featured, Growth, Operations, Impact, Transition, Custom)
  - Added auto-select agents by lens
  - Added Crema filtering behavior
  - Added Custom lens AI interpretation flow
  - Updated author attribution to "The Ionganic Orchestrator - TIO"
  - Added TIO and iOnganic to glossary

companion_documents:
  - "RootRise_Eye_Lens_Framework_v2.md"
  - "RootRise_Sector_Knowledge_Framework_v2.md"
  - "RootRise_Core_Agent_Prompts.md"
  - "RootRise_AddOn_Agent_Prompts.md"
  - "RootRise_Utility_Agent_Prompts.md"
  - "RootRise_Questionnaire_Schema_v1.md"
  - "EYE-000_The_Crema.md"
  - "EYE-CUSTOM_Custom_Objective.md"
```

---

**Document Version:** 1.2  
**Prepared by:** Tee (The Ionganic Orchestrator - TIO)  
**For:** Ahmed El-Gazzar (Technical DevOps Lead)  
**RootRise by DEVONEERS — January 2026**
