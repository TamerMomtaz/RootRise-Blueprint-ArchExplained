# RootRise v6.0 — The &Eye Lens Framework

**Document Version:** 2.0  
**Last Updated:** January 5, 2026  
**Status:** Production-Ready Framework  
**Author:** Tee (CTO)  
**For:** Ahmed El-Gazzar (Technical DevOps Lead) & Development Team

---

## Table of Contents

1. [Overview](#1-overview)
2. [The &Eye Philosophy](#2-the-eye-philosophy)
3. [Lens Architecture](#3-lens-architecture)
4. [Complete Lens Index](#4-complete-lens-index)
5. [Lens Categories](#5-lens-categories)
6. [Lens-to-Agent Priority Matrix](#6-lens-to-agent-priority-matrix)
7. [Lens-Based Report Prioritization](#7-lens-based-report-prioritization)
8. [Multi-Lens Configuration](#8-multi-lens-configuration)
9. [LangGraph Integration](#9-langgraph-integration)
10. [API Specifications](#10-api-specifications)
11. [UI Behavior](#11-ui-behavior)
12. [Quick Reference](#12-quick-reference)

---

## 1. Overview

### 1.1 What is The &Eye?

The &Eye is the third configuration layer of the RootRise diagnostic system. While The Pantheon defines *who* analyzes the SME (agents) and My Sector defines *with what context* (sector intelligence), The &Eye defines *toward what goal* (transformation objective).

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    THE THREE CONFIGURATION LAYERS                            │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  LAYER 1: THE PANTHEON              "WHO analyzes?"                         │
│  ├─ 11 specialist agents                                                     │
│  ├─ User selects Add-On agents                                               │
│  └─ Core agents always included                                              │
│                                                                              │
│  LAYER 2: MY SECTOR                 "WITH WHAT context?"                     │
│  ├─ 31 industry sectors                                                      │
│  ├─ 11 intelligence dimensions per sector                                    │
│  ├─ Growth Pathways & Strategic Summary                                      │
│  └─ MENA-specific benchmarks (6 countries)                                   │
│                                                                              │
│  LAYER 3: THE &EYE                  "TOWARD WHAT goal?"                      │
│  ├─ 17 transformation lenses (1 Featured + 15 Standard + 1 Custom)          │
│  ├─ Reprioritizes agent focus                                                │
│  └─ Reshapes report structure and recommendations                            │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 The Core Insight

> *"The same SME, analyzed through different lenses, gets different—but equally rigorous—transformation paths."*

An SME with identical data analyzed through:

- **Export Readiness** lens → Focus on certification gaps, packaging compliance, market entry
- **Investment Readiness** lens → Focus on governance, financial documentation, valuation drivers
- **Cost Optimization** lens → Focus on waste elimination, margin improvement, efficiency
- **The Crema** lens → Focus on quick wins achievable in 30-60-90 days

Same data. Different priorities. Different recommendations. Different report structure.

### 1.3 Document Purpose

This document provides Ahmed and the development team with:

- Complete definitions for all 17 transformation lenses
- Agent priority matrices for each lens
- Report content prioritization rules
- LangGraph workflow integration specifications
- API endpoint definitions
- UI behavior specifications
- Multi-lens conflict resolution logic

---

## 2. The &Eye Philosophy

### 2.1 Design Principles

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      THE &EYE DESIGN PRINCIPLES                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  1. GOAL-DRIVEN ANALYSIS                                                     │
│     Every finding is evaluated against the user's stated objective.          │
│     Relevance to the lens determines prominence, not just severity.          │
│                                                                              │
│  2. WEIGHT ADJUSTMENT, NOT DATA FILTERING                                    │
│     Lenses don't hide data—they reprioritize it.                             │
│     All findings remain accessible; focus determines emphasis.               │
│                                                                              │
│  3. SAME RIGOR, DIFFERENT LENS                                               │
│     Export Readiness lens demands the same analytical depth                  │
│     as Investment Readiness. Only the focal point changes.                   │
│                                                                              │
│  4. HUMAN AGENCY PRESERVED (&I Philosophy)                                   │
│     The SME owner chooses their lens based on their goals.                   │
│     The system serves the goal; it doesn't impose one.                       │
│                                                                              │
│  5. TRANSPARENT REASONING                                                    │
│     When a lens prioritizes certain findings, the "why" is visible.          │
│     "Highlighted because you selected Export Readiness"                      │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 &I Philosophy Integration

The &Eye embodies the &I Philosophy by:

- **Letting the human define success** — The SME owner's goal drives the analysis
- **Making AI priorities transparent** — The user can see why findings are weighted
- **Supporting, not dictating** — Recommendations align with stated objectives
- **Preserving agency** — The user can change lenses or view alternative perspectives

---

## 3. Lens Architecture

### 3.1 Lens Data Structure

```typescript
interface TransformationLens {
  // Core identification
  lens_id: string;                    // e.g., "eye_001", "eye_crema"
  display_name: string;               // e.g., "Export Readiness"
  display_name_ar: string;            // Arabic name
  category: LensCategory;
  
  // User-facing content
  user_statement: {
    en: string;                       // "I want to sell internationally"
    ar: string;
  };
  short_description: {
    en: string;
    ar: string;
  };
  detailed_description: {
    en: string;
    ar: string;
  };
  
  // Visual elements
  icon: string;                       // Emoji or icon identifier
  accent_color: string;               // Optional lens-specific accent
  focus_tags: string[];               // e.g., ["Certifications", "Logistics"]
  
  // Behavior configuration
  agent_priority_adjustments: AgentPriorityAdjustment[];
  auto_select_agents: string[];
  report_section_order: string[];
  content_prioritization: ContentPrioritizationRule[];
  
  // Feature flags
  is_featured: boolean;               // The Crema = true
  is_default_selected: boolean;       // The Crema = true
  allows_combination: boolean;        // Can combine with other lenses
  
  // Metadata
  version: string;
  last_updated: string;
}

type LensCategory = 
  | 'featured'      // The Crema
  | 'growth'        // Export, Investment, Market Expansion
  | 'transition'    // Succession, Partnership & M&A
  | 'operations'    // Digital, Operational Excellence, Cost
  | 'impact'        // Workforce, Supply Chain, ESG, Innovation, CX, Risk
  | 'custom';       // User-defined

interface AgentPriorityAdjustment {
  agent_id: string;
  weight_multiplier: number;          // 0.5-1.5
  focus_dimensions: string[];
  reason: string;
}
```

---

## 4. Complete Lens Index

### 4.1 All 17 Lenses

| ID | Name | Category | Primary Agents | File |
|----|------|----------|----------------|------|
| **EYE-CREMA** | The &Eye Crema | Featured | Ohno, Graham, Marvin | `EYE-000_The_Crema.md` |
| **EYE-001** | Export Readiness | Growth | Ricardo, Landor | `EYE-001_Export_Readiness.md` |
| **EYE-002** | Investment Readiness | Growth | Graham, Porter | `EYE-002_Investment_Readiness.md` |
| **EYE-003** | Digital Transformation | Operations | Lovelace, Marvin | `EYE-003_Digital_Transformation.md` |
| **EYE-004** | Operational Excellence | Operations | Marvin, Ohno | `EYE-004_Operational_Excellence.md` |
| **EYE-005** | Market Expansion | Growth | Porter, Ricardo | `EYE-005_Market_Expansion.md` |
| **EYE-006** | Brand Building | Growth | Landor, Porter | `EYE-006_Brand_Building.md` |
| **EYE-007** | Workforce Development | Impact | Mayo, Marvin | `EYE-007_Workforce_Development.md` |
| **EYE-008** | Supply Chain Optimization | Impact | Ohno, Ricardo | `EYE-008_Supply_Chain_Optimization.md` |
| **EYE-009** | Sustainability & ESG | Impact | Marvin, Ohno | `EYE-009_Sustainability_ESG.md` |
| **EYE-010** | Innovation & R&D | Impact | Lovelace, Porter | `EYE-010_Innovation_RD.md` |
| **EYE-011** | Customer Experience | Impact | Porter, Lovelace | `EYE-011_Customer_Experience.md` |
| **EYE-012** | Cost Optimization | Operations | Graham, Ohno | `EYE-012_Cost_Optimization.md` |
| **EYE-013** | Risk & Resilience | Impact | Marvin, Ohno | `EYE-013_Risk_Resilience.md` |
| **EYE-014** | Succession & Governance | Transition | Graham, Mayo | `EYE-014_Succession_Governance.md` |
| **EYE-015** | Partnership & M&A | Transition | Graham, Porter | `EYE-015_Partnership_MA.md` |
| **EYE-CUSTOM** | Custom Objective | Custom | (AI-determined) | `EYE-CUSTOM_Custom_Objective.md` |

### 4.2 Lens Summaries

#### Featured Lens

**EYE-CREMA: The &Eye Crema** ☕
> "I want quick wins NOW — show me what I can achieve in 30-60-90 days"

The Crema extracts highest-value, lowest-effort improvements. This is RootRise's **signature differentiator** — while other tools deliver overwhelming reports, The Crema answers the question every SME owner asks first: "What can I do RIGHT NOW?"

- **Pre-selected by default** (can be deselected)
- **Combines with all other lenses** (acts as a filter)
- **Focus:** 30-day, 60-day, 90-day action plans

---

#### Growth Category

**EYE-001: Export Readiness** 🌍
> "I want to sell internationally"

Assesses and develops readiness to enter international markets. Covers certification gaps, compliance requirements, logistics capabilities, and market entry strategies.

**EYE-002: Investment Readiness** 💰
> "If an investor evaluated this business tomorrow, what would they find?"

Prepares your business to attract investment from banks, VCs, development funds, or strategic investors. Focuses on financial health, governance structures, and valuation drivers.

**EYE-005: Market Expansion** 📈
> "I want to grow my market presence"

Identifies domestic and regional growth opportunities. Covers competitive positioning, market entry strategies, and geographic expansion.

**EYE-006: Brand Building** 🎨
> "I want to strengthen my brand"

Assesses brand positioning, market presence, and visual identity. Focuses on differentiation, customer perception, and brand strategy.

---

#### Operations Category

**EYE-003: Digital Transformation** 💻
> "I want to modernize my business"

Assesses digital maturity and builds a practical roadmap for modernization. Covers tech stack, automation, digital presence, and data-driven decision making.

**EYE-004: Operational Excellence** ⚙️
> "I want to run better"

Systematic improvement of how your business operates. Covers process optimization, quality management, lean principles, and building operational consistency.

**EYE-012: Cost Optimization** 📊
> "I want better margins"

Identifies where profits are leaking and how to plug them. Deep dive into cost structure, pricing optimization, waste elimination, and efficiency improvements.

---

#### Impact Category

**EYE-007: Workforce Development** 👥
> "I want to build my team"

Focuses on growing and developing your workforce. Covers hiring capacity, skills development, workforce planning, and organizational scaling.

**EYE-008: Supply Chain Optimization** 🔗
> "I want a more efficient supply chain"

Assesses supply chain efficiency and resilience. Covers supplier relationships, logistics, inventory management, and lean operations.

**EYE-009: Sustainability & ESG** 🌱
> "I want to be sustainable"

Assesses environmental, social, and governance performance. Identifies sustainability gaps, green certification opportunities, and ESG improvements.

**EYE-010: Innovation & R&D** 💡
> "I want to innovate"

Assesses innovation capacity and R&D readiness. Covers product development, technology adoption, and innovation culture.

**EYE-011: Customer Experience** ⭐
> "I want happier customers"

Evaluates customer journey, satisfaction, and retention. Focuses on service quality, feedback mechanisms, and customer-centric improvements.

**EYE-013: Risk & Resilience** 🛡️
> "I want to be prepared for disruption"

Assesses business continuity, risk management, and operational resilience. Identifies vulnerabilities and mitigation strategies.

---

#### Transition Category

**EYE-014: Succession & Governance** 👤
> "I want to prepare for leadership transition"

Evaluates how dependent the business is on current leadership. Develops plans for succession, organizational independence, and governance maturity.

**EYE-015: Partnership & M&A** 🤝
> "I want to find a partner or prepare for sale"

Assesses readiness for strategic partnerships, joint ventures, or acquisition. Covers valuation, due diligence readiness, and deal preparation.

---

#### Custom Category

**EYE-CUSTOM: Custom Objective** ✨
> "I have a specific goal that doesn't fit the standard lenses"

For goals not covered by the 15 predefined lenses. Describe your specific objective, and the AI interprets it to configure agent priorities and report structure.

- **Exclusive** — Cannot be combined with standard lenses (can combine with Crema)
- **AI-interpreted** — The Drucker analyzes the description and configures the diagnostic

---

## 5. Lens Categories

### 5.1 Category Structure

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        17 TRANSFORMATION LENSES                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  [FEATURED] THE CREMA                                                        │
│  └─ EYE-CREMA: Quick Wins Focus (30-60-90 days)                             │
│                                                                              │
│  [GROWTH - 4 Lenses]                                                         │
│  ├─ EYE-001: Export Readiness                                               │
│  ├─ EYE-002: Investment Readiness                                           │
│  ├─ EYE-005: Market Expansion                                               │
│  └─ EYE-006: Brand Building                                                 │
│                                                                              │
│  [OPERATIONS - 3 Lenses]                                                     │
│  ├─ EYE-003: Digital Transformation                                         │
│  ├─ EYE-004: Operational Excellence                                         │
│  └─ EYE-012: Cost Optimization                                              │
│                                                                              │
│  [IMPACT - 6 Lenses]                                                         │
│  ├─ EYE-007: Workforce Development                                          │
│  ├─ EYE-008: Supply Chain Optimization                                      │
│  ├─ EYE-009: Sustainability & ESG                                           │
│  ├─ EYE-010: Innovation & R&D                                               │
│  ├─ EYE-011: Customer Experience                                            │
│  └─ EYE-013: Risk & Resilience                                              │
│                                                                              │
│  [TRANSITION - 2 Lenses]                                                     │
│  ├─ EYE-014: Succession & Governance                                        │
│  └─ EYE-015: Partnership & M&A                                              │
│                                                                              │
│  [CUSTOM]                                                                    │
│  └─ EYE-CUSTOM: Custom Objective                                            │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 5.2 Category Colors (UI)

```css
:root {
  --lens-featured: #F5C563;       /* Gold for The Crema */
  --lens-growth: #5DD4C3;         /* Bright Teal */
  --lens-operations: #4A90A4;     /* Steel Blue */
  --lens-impact: #7CB342;         /* Leaf Green */
  --lens-transition: #8B7355;     /* Warm Brown */
  --lens-custom: #B8904A;         /* Bronze Gold */
}
```

---

## 6. Lens-to-Agent Priority Matrix

### 6.1 Complete Priority Matrix

```
┌──────────────────────────────────────────────────────────────────────────────────────┐
│                        LENS → AGENT PRIORITY MATRIX                                   │
├──────────────────────────────────────────────────────────────────────────────────────┤
│                        │ Mar │ Gra │ Ric │ Lov │ May │ Ohn │ Por │ Lan │             │
│ LENS                   │ vin │ ham │ ardo│ lace│  o  │ o   │ ter │ dor │ AUTO-SELECT │
├────────────────────────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────────────┤
│ EYE-CREMA (Crema)      │ 1.3 │ 1.4★│ 0.9 │ 1.0 │ 1.0 │ 1.5★│ 0.9 │ 0.9 │ None        │
├────────────────────────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────────────┤
│ EYE-001 Export         │ 1.1 │ 1.0 │ 1.5★│ 0.9 │ 0.9 │ 1.2 │ 1.0 │ 1.5★│ Ric, Lan    │
│ EYE-002 Investment     │ 1.1 │ 1.5★│ 0.8 │ 0.9 │ 1.2 │ 0.9 │ 1.3★│ 0.8 │ Por         │
│ EYE-005 Market Exp.    │ 1.0 │ 1.2 │ 1.2 │ 0.9 │ 0.9 │ 0.9 │ 1.5★│ 1.0 │ Por         │
│ EYE-006 Brand          │ 1.0 │ 0.9 │ 0.9 │ 1.2 │ 0.9 │ 0.9 │ 1.3★│ 1.5★│ Lan, Por    │
├────────────────────────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────────────┤
│ EYE-003 Digital        │ 1.2 │ 1.0 │ 0.8 │ 1.5★│ 1.1 │ 1.0 │ 0.9 │ 0.8 │ Lov         │
│ EYE-004 Ops Excellence │ 1.3★│ 0.9 │ 0.8 │ 1.1 │ 1.0 │ 1.5★│ 0.8 │ 0.9 │ Ohn         │
│ EYE-012 Cost Opt.      │ 1.1 │ 1.5★│ 0.8 │ 1.0 │ 0.9 │ 1.4★│ 1.1 │ 0.8 │ Ohn         │
├────────────────────────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────────────┤
│ EYE-007 Workforce      │ 1.2 │ 1.1 │ 0.8 │ 0.8 │ 1.5★│ 1.0 │ 0.9 │ 0.8 │ May         │
│ EYE-008 Supply Chain   │ 1.2 │ 1.0 │ 1.2 │ 0.9 │ 0.9 │ 1.5★│ 0.9 │ 1.2 │ Ohn         │
│ EYE-009 ESG            │ 1.3★│ 1.1 │ 0.9 │ 0.9 │ 1.2 │ 1.4★│ 0.9 │ 1.2 │ Ohn         │
│ EYE-010 Innovation     │ 1.1 │ 1.0 │ 0.9 │ 1.5★│ 1.0 │ 1.0 │ 1.3★│ 0.9 │ Lov         │
│ EYE-011 Customer Exp.  │ 1.1 │ 1.0 │ 0.9 │ 1.3★│ 1.0 │ 0.9 │ 1.4★│ 1.1 │ Por         │
│ EYE-013 Risk           │ 1.4★│ 1.2 │ 0.9 │ 1.0 │ 1.0 │ 1.3★│ 1.0 │ 0.9 │ None        │
├────────────────────────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────────────┤
│ EYE-014 Succession     │ 1.2 │ 1.4★│ 0.7 │ 0.9 │ 1.5★│ 0.9 │ 0.9 │ 0.7 │ May         │
│ EYE-015 M&A            │ 1.1 │ 1.5★│ 0.9 │ 0.9 │ 1.1 │ 0.9 │ 1.4★│ 0.8 │ Por         │
└────────────────────────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────────────┘

★ = Primary agent for this lens (highest weight)
```

### 6.2 Weight Combination Logic

When multiple lenses are active, agent weights are combined using **weighted_primary** strategy:

```typescript
function combineWeights(lenses: string[]): Record<string, number> {
  // Primary lens (first selected) gets 60% weight
  // Secondary lenses split remaining 40%
  const primaryWeight = 0.6;
  const secondaryWeight = 0.4 / (lenses.length - 1 || 1);
  
  const combined: Record<string, number> = {};
  
  for (const agent of AGENTS) {
    let weight = lensPriorityMatrix[lenses[0]].agent_weights[agent] * primaryWeight;
    
    for (let i = 1; i < lenses.length; i++) {
      weight += lensPriorityMatrix[lenses[i]].agent_weights[agent] * secondaryWeight;
    }
    
    combined[agent] = weight;
  }
  
  return combined;
}
```

---

## 7. Lens-Based Report Prioritization

### 7.1 Report Section Ordering

Each lens defines a preferred order for report sections:

```typescript
interface LensReportConfig {
  lens_id: string;
  lead_sections: string[];           // Sections that appear first
  emphasized_sections: string[];     // Sections with expanded treatment
  de_emphasized_sections: string[];  // Sections that are condensed
  appendix_candidates: string[];     // Sections that may be moved to appendix
}
```

### 7.2 The Crema Special Behavior

When The Crema is active alongside other lenses, it acts as a **filter**:

```
OTHER LENS FINDINGS → CREMA FILTER → PRIORITIZED QUICK WINS

Example:
- Export Readiness produces 25 recommendations
- Crema filter applied: 8 qualify as quick wins (≤90 days, low/medium effort)
- Report leads with "Export Readiness Quick Wins"
- Remaining 17 recommendations included but de-emphasized
```

---

## 8. Multi-Lens Configuration

### 8.1 Selection Rules

```typescript
interface LensSelectionRules {
  // The Crema
  crema: {
    is_default_selected: true;
    can_be_deselected: true;
    combines_with_all: true;
  };
  
  // Standard lenses
  standard: {
    max_simultaneous: 3;
    can_combine: true;
  };
  
  // Custom lens
  custom: {
    is_exclusive: true;  // Cannot combine with standard lenses
    can_combine_with_crema: true;
  };
}
```

### 8.2 Conflict Resolution

```typescript
interface ConflictResolution {
  // Content emphasis conflicts
  content_conflicts: {
    rule: "primary_lens_wins";
    secondary_action: "include_but_de_emphasize";
  };
  
  // Agent priority conflicts
  agent_conflicts: {
    rule: "weighted_combination";
    primary_weight: 0.6;
    secondary_weight: 0.4;
  };
  
  // Report section conflicts
  section_conflicts: {
    rule: "merge_section_orders";
    primary_sections_first: true;
  };
}
```

---

## 9. LangGraph Integration

### 9.1 Lens Processing Node

The Drucker processes lens configuration at diagnostic initialization:

```typescript
const processLensConfiguration: StateGraphNode = {
  name: "process_lens_configuration",
  
  async execute(state: DiagnosticState): Promise<Partial<DiagnosticState>> {
    const { active_lenses, custom_lens_description } = state.configuration;
    
    // Calculate combined agent weights
    const combinedWeights = calculateCombinedWeights(active_lenses);
    
    // Determine auto-selected agents
    const autoSelectedAgents = determineAutoSelectedAgents(active_lenses);
    
    // Compute report section order
    const sectionOrder = computeSectionOrder(active_lenses);
    
    // Handle custom lens interpretation
    let customInterpretation = null;
    if (active_lenses.includes('eye_custom') && custom_lens_description) {
      customInterpretation = await interpretCustomLens(custom_lens_description);
    }
    
    return {
      lens_configuration: {
        ...state.lens_configuration,
        computed_agent_weights: combinedWeights,
        auto_selected_agents: autoSelectedAgents,
        report_section_order: sectionOrder,
        custom_interpretation: customInterpretation
      }
    };
  }
};
```

### 9.2 State Schema Extension

```typescript
interface DiagnosticState {
  // ... existing fields ...
  
  configuration: {
    selected_agents: string[];
    sector_id: string;
    selected_lenses: string[];        // From The &Eye
    custom_lens_description?: string;
  };
  
  lens_configuration: {
    active_lenses: string[];
    primary_lens: string;
    computed_agent_weights: Record<string, number>;
    auto_selected_agents: string[];
    report_section_order: string[];
    crema_active: boolean;
    custom_interpretation?: CustomLensInterpretation;
  };
}
```

---

## 10. API Specifications

### 10.1 Lens Endpoints

```yaml
# List all lenses
GET /api/v1/lenses
Response:
  lenses: Lens[]
  categories: LensCategory[]

# Get lens details
GET /api/v1/lenses/{lens_id}
Response:
  lens: LensDetails
  agent_priorities: AgentPriorityConfig
  report_config: LensReportConfig

# Validate lens combination
POST /api/v1/lenses/validate-combination
Request:
  lens_ids: string[]
Response:
  valid: boolean
  conflicts: LensConflict[]
  combined_weights: Record<string, number>

# Interpret custom lens
POST /api/v1/lenses/interpret-custom
Request:
  description: string
  sector_id: string
Response:
  interpretation: CustomLensInterpretation
  confidence_score: number
  similar_lenses: string[]
```

### 10.2 Diagnostic Endpoints (Lens-Aware)

```yaml
# Initialize diagnostic with lenses
POST /api/v1/diagnostic/initiate
Request:
  sme_id: string
  configuration:
    selected_agents: string[]
    sector_id: string
    selected_lenses: string[]          # From The &Eye
    custom_lens_description?: string
Response:
  diagnostic_id: string
  computed_configuration:
    final_agent_list: string[]
    agent_weights: Record<string, number>
    report_section_order: string[]
    crema_active: boolean
```

---

## 11. UI Behavior

### 11.1 Lens Selection Screen

```typescript
interface LensSelectionUISpec {
  // Screen layout
  layout: {
    title: "What's Your Transformation Goal?";
    subtitle: "Select lenses to focus your diagnostic";
    step_indicator: "STEP 3 OF 3";
  };
  
  // The Crema positioning
  crema: {
    position: "top";
    width: "full";           // Spans all columns
    is_default_selected: true;
    badge: "FEATURED";
    highlight_color: "gold";
  };
  
  // Category grouping
  categories: {
    display: "grouped";
    collapsible: false;
    show_category_headers: true;
  };
  
  // Selection behavior
  selection: {
    max_standard_lenses: 3;
    crema_separate_from_limit: true;
    custom_replaces_standard: true;
  };
}
```

### 11.2 Lens Card Component

```typescript
interface LensCardSpec {
  // Visual states
  default: {
    background: "transparent";
    border: "1px solid var(--border-subtle)";
  };
  
  selected: {
    background: "var(--lens-category-color-subtle)";
    border: "2px solid var(--lens-category-color)";
    show_checkmark: true;
  };
  
  // Content
  display: {
    icon: true;
    name: true;
    user_statement: true;  // Italicized
    focus_tags: true;      // As pills
  };
}
```

---

## 12. Quick Reference

### 12.1 Lens Summary Table

| Lens ID | Name | Category | Primary Agents | User Statement |
|---------|------|----------|----------------|----------------|
| EYE-CREMA | The Crema | Featured | Ohno, Graham | Quick wins in 30-60-90 days |
| EYE-001 | Export Readiness | Growth | Ricardo, Landor | Sell internationally |
| EYE-002 | Investment Readiness | Growth | Graham, Porter | Raise capital |
| EYE-003 | Digital Transformation | Operations | Lovelace, Marvin | Modernize |
| EYE-004 | Operational Excellence | Operations | Marvin, Ohno | Run better |
| EYE-005 | Market Expansion | Growth | Porter, Ricardo | Grow market presence |
| EYE-006 | Brand Building | Growth | Landor, Porter | Strengthen brand |
| EYE-007 | Workforce Development | Impact | Mayo, Marvin | Build team |
| EYE-008 | Supply Chain | Impact | Ohno, Ricardo | Efficient supply chain |
| EYE-009 | ESG | Impact | Marvin, Ohno | Be sustainable |
| EYE-010 | Innovation | Impact | Lovelace, Porter | Innovate |
| EYE-011 | Customer Experience | Impact | Porter, Lovelace | Happy customers |
| EYE-012 | Cost Optimization | Operations | Graham, Ohno | Better margins |
| EYE-013 | Risk & Resilience | Impact | Marvin, Ohno | Be prepared |
| EYE-014 | Succession | Transition | Graham, Mayo | Leadership transition |
| EYE-015 | Partnership & M&A | Transition | Graham, Porter | Find partner or sell |
| EYE-CUSTOM | Custom Objective | Custom | (AI-determined) | Specific goal |

### 12.2 Files Inventory

| File | Description | Size |
|------|-------------|------|
| `RootRise_Eye_Lens_Framework_v2.md` | This document | ~40 KB |
| `EYE-000_The_Crema.md` | Featured quick wins lens | ~15 KB |
| `EYE-001_Export_Readiness.md` | Export lens | ~9 KB |
| `EYE-002_Investment_Readiness.md` | Investment lens | ~44 KB |
| ... | ... | ... |
| `EYE-015_Partnership_MA.md` | M&A lens | ~62 KB |
| `EYE-CUSTOM_Custom_Objective.md` | Custom lens | ~12 KB |

---

## Document Metadata

```yaml
document_type: "Lens Framework Specification"
version: "2.0"
lenses_covered: 17
categories_covered: 6
last_updated: "2026-01-05"
status: "Production Ready"
author: "Tee (CTO)"
for: "Ahmed El-Gazzar (Technical DevOps Lead)"

changes_from_v1:
  - Updated lens numbering to match EYE-001 through EYE-015 system
  - Added new lenses: Market Expansion, Brand Building, Innovation, Customer Experience, Risk & Resilience
  - Removed: Inheritance Prep, Sale/Exit, Local Development (merged into other lenses)
  - Enhanced The Crema documentation
  - Added Custom Objective lens with AI interpretation
  - Updated agent priority matrix
  - Added category-based organization

companion_documents:
  - "RootRise_Infrastructure_Blueprint_v1.1.md"
  - "RootRise_Core_Agent_Prompts.md"
  - "RootRise_AddOn_Agent_Prompts.md"
  - "RootRise_Utility_Agent_Prompts.md"
  - "RootRise_Sector_Knowledge_Framework.md"
```

---

*The &Eye — See your business through any lens.*
