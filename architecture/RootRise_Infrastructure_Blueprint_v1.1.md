# RootRise v6.0 Technical Infrastructure Blueprint

**Document Version:** 1.1  
**Date:** January 4, 2026  
**Author:** Tee (the ionganic)
**For:** Ahmed El-Gazzar (Technical DevOps Lead)  
**Status:** Implementation Ready

---

## Executive Summary

This document provides the complete technical infrastructure specification for implementing The RootRise Pantheon—an AI-powered SME diagnostic platform. It translates our architectural vision into actionable implementation guidance, with every technical decision filtered through the lens of our **&I Philosophy**: AI + Human, not AI instead of Human.

### What This Document Covers

1. **&I Philosophy Integration** — How human-AI collaboration is embedded at every layer
2. **System Architecture Overview** — The three-layer configuration model
3. **Memory Architecture** — Session, persistent, and cross-agent state management
4. **Vector Database Design** — Sector knowledge storage and retrieval with confidence metadata
5. **LangGraph Orchestration** — Multi-agent workflow with native HITL checkpoints
6. **Questionnaire System** — 10-section data collection with agent mapping
7. **The &Eye Lens System** — 15 transformation lenses and their agent priorities
8. **API Specification** — REST endpoints including transparency and override capabilities
9. **Deployment Architecture** — Infrastructure requirements and operational principles
10. **Resource Estimates** — Compute, storage, and cost projections

### Key Metrics at a Glance

| Component | Specification |
|-----------|---------------|
| Total Agents | 11 (3 Core + 6 Add-On + 2 Utility) |
| Transformation Lenses | 15 (The &Eye) |
| Sector Knowledge Packs | 31 sectors, ~2.6MB total |
| Dimensions per Sector | 11 knowledge dimensions + Growth Pathways + Strategic Summary |
| Questionnaire Sections | 10 sections, ~145 questions |
| HITL Checkpoints | 4 validation gates |
| Target Countries | 6 (EG, SA, AE, JO, LB, MA) |
| Target Diagnostic Time | 30 minutes (user interaction) |
| Target Processing Time | < 120 seconds (AI analysis) |

---

## Part 1: The &I Philosophy — Our Technical North Star

Before any infrastructure decision, we must understand what makes RootRise fundamentally different. We are not building AI that replaces human judgment—we are building AI that **augments** human intelligence while **preserving** human agency.

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

RootRise operates on a powerful three-layer configuration architecture that enables the same business data to produce different but equally rigorous transformation paths.

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
│   │  Coverage: 31 sectors across 6 MENA countries (EG, SA, AE, JO, LB, MA)│   │
│   └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
│   LAYER 3: THE &EYE (15 Lenses)                                             │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │  WHY / WHAT transformation goal                                      │   │
│   │                                                                       │   │
│   │  EYE-001: Digital Transformation                                     │   │
│   │  EYE-002: Investment Readiness                                       │   │
│   │  EYE-003: Export Readiness                                           │   │
│   │  EYE-004: Operational Excellence                                     │   │
│   │  EYE-005: Market Expansion                                           │   │
│   │  EYE-006: Brand Building                                             │   │
│   │  EYE-007: Workforce Development                                      │   │
│   │  EYE-008: Supply Chain Optimization                                  │   │
│   │  EYE-009: Sustainability & ESG                                       │   │
│   │  EYE-010: Innovation & R&D                                           │   │
│   │  EYE-011: Customer Experience                                        │   │
│   │  EYE-012: Cost Optimization                                          │   │
│   │  EYE-013: Risk & Resilience                                          │   │
│   │  EYE-014: Succession & Governance                                    │   │
│   │  EYE-015: Partnership & M&A                                          │   │
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
│   Through INVESTMENT READINESS lens:                                        │
│   → Focus on governance gaps, financial documentation, audit readiness      │
│                                                                              │
│   Through EXPORT READINESS lens:                                            │
│   → Focus on certifications, packaging compliance, market entry strategy    │
│                                                                              │
│   Through OPERATIONAL EXCELLENCE lens:                                      │
│   → Focus on OEE improvement, waste reduction, quality systems              │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Complete Lens Roster

| Lens ID | Name | Core Question | Primary Agents |
|---------|------|---------------|----------------|
| EYE-001 | Export Readiness | Is this business ready to compete internationally? | Ricardo (P1), Landor, Marvin |
| EYE-002 | Investment Readiness | If an investor evaluated this business tomorrow, what would they find? | Graham (P1), Marvin, Porter |
| EYE-003 | Digital Transformation | How digitally mature is this business and what's the transformation path? | Lovelace (P1), Marvin, Graham |
| EYE-004 | Operational Excellence | How efficient and consistent are operations? | Marvin (P1), Ohno, Graham |
| EYE-005 | Market Expansion | What growth opportunities exist domestically and regionally? | Porter (P1), Ricardo, Graham |
| EYE-006 | Brand Building | How strong is brand positioning and market presence? | Landor (P1), Porter, Lovelace |
| EYE-007 | Workforce Development | Is the workforce optimized for current and future needs? | Mayo (P1), Marvin, Graham |
| EYE-008 | Supply Chain Optimization | How resilient and efficient is the supply chain? | Ohno (P1), Marvin, Ricardo |
| EYE-009 | Sustainability & ESG | What is the environmental and social impact profile? | Marvin (P1), Ohno, Graham |
| EYE-010 | Innovation & R&D | Is the business positioned for product/service innovation? | Lovelace (P1), Porter, Marvin |
| EYE-011 | Customer Experience | How effectively does the business serve customers? | Porter (P1), Lovelace, Landor |
| EYE-012 | Cost Optimization | Where are the efficiency and cost reduction opportunities? | Graham (P1), Ohno, Marvin |
| EYE-013 | Risk & Resilience | How prepared is the business for disruption? | Marvin (P1), Ohno, Graham |
| EYE-014 | Succession & Governance | Is the business prepared for leadership transition? | Graham (P1), Mayo, Marvin |
| EYE-015 | Partnership & M&A | Is the business positioned for strategic partnerships or acquisition? | Graham (P1), Porter, Marvin |

### 3.3 Lens Configuration Schema

```typescript
interface LensConfiguration {
  lens_id: string;                        // e.g., "EYE-002"
  lens_name: string;                      // e.g., "Investment Readiness"
  lens_name_ar: string;                   // Arabic name
  
  // Strategic Context
  user_goal: string;                      // What the user wants to achieve
  core_question: string;                  // The central diagnostic question
  key_insight: string;                    // The lens philosophy
  
  // Agent Prioritization
  agent_priorities: {
    agent_id: string;
    priority: "P1" | "P2" | "P3";         // P1 = Primary, P2 = Supporting, P3 = Context
    weight: number;                       // 0.0-1.0 weighting in final score
    focus_areas: string[];                // Which aspects to emphasize
  }[];
  
  // Output Customization
  output_emphasis: string[];              // What to highlight in report
  quick_win_criteria: string[];           // How to identify quick wins
  roadmap_focus: string[];                // What transformation roadmap emphasizes
  
  // Dimension Weights (adjust importance of 11 dimensions)
  dimension_weights: {
    [dimension_id: number]: number;       // 1-11 → weight multiplier
  };
  
  // Scoring Adjustments
  scoring_profiles: {
    dimension: string;
    weight_adjustment: number;            // Multiplier for this lens
  }[];
}
```

### 3.4 Lens-Agent Priority Matrix

```
                    ┌─────────────────────────────────────────────────────────────────┐
                    │                    AGENT PRIORITY BY LENS                        │
                    ├──────────┬──────┬──────┬───────┬────────┬─────┬─────┬──────┬─────┤
                    │          │Graham│Marvin│Ricardo│Lovelace│Mayo │Ohno │Porter│Lndor│
┌───────────────────┼──────────┼──────┼──────┼───────┼────────┼─────┼─────┼──────┼─────┤
│EYE-001 Export     │          │  P2  │  P1  │       │        │     │     │      │  P2 │
│EYE-002 Investment │    P1    │  P2  │      │       │        │     │  P2 │      │     │
│EYE-003 Digital    │    P2    │  P2  │      │  P1   │        │     │     │      │     │
│EYE-004 Operations │    P2    │  P1  │      │       │        │ P2  │     │      │     │
│EYE-005 Market     │    P2    │      │  P2  │       │        │     │  P1 │      │     │
│EYE-006 Brand      │          │      │      │  P2   │        │     │  P2 │  P1  │     │
│EYE-007 Workforce  │    P2    │  P2  │      │       │   P1   │     │     │      │     │
│EYE-008 Supply     │          │  P2  │  P2  │       │        │ P1  │     │      │     │
│EYE-009 ESG        │    P2    │  P1  │      │       │        │ P2  │     │      │     │
│EYE-010 Innovation │          │  P2  │      │  P1   │        │     │  P2 │      │     │
│EYE-011 Customer   │          │      │      │  P2   │        │     │  P1 │  P2  │     │
│EYE-012 Cost       │    P1    │  P2  │      │       │        │ P2  │     │      │     │
│EYE-013 Risk       │    P2    │  P1  │      │       │        │ P2  │     │      │     │
│EYE-014 Succession │    P1    │  P2  │      │       │   P2   │     │     │      │     │
│EYE-015 M&A        │    P1    │  P2  │      │       │        │     │  P2 │      │     │
└───────────────────┴──────────┴──────┴──────┴───────┴────────┴─────┴─────┴──────┴─────┘

P1 = Primary Agent (highest weight, detailed analysis)
P2 = Supporting Agent (moderate weight, contextual analysis)
Empty = Context only (low weight, if selected by user)
```

---

## Part 4: Sector Knowledge Architecture

### 4.1 Sector Coverage (31 Sectors)

#### Legacy Sectors (Updated to v2.0 Framework)

| # | Sector ID | Sector Name | Size | Version |
|---|-----------|-------------|------|---------|
| 1 | `agriculture_agribusiness` | Agriculture & Agribusiness | 79KB | 2.0 |
| 2 | `automotive` | Automotive | 78KB | 2.0 |
| 3 | `chemicals_plastics` | Chemicals, Plastics & Specialty | 80KB | 2.0 |
| 4 | `construction_building` | Construction & Building | 86KB | 2.0 |
| 5 | `education_training` | Education & Training | 78KB | 2.0 |
| 6 | `financial_services` | Financial Services | 76KB | 2.0 |
| 7 | `healthcare_services` | Healthcare Services | 83KB | 2.0 |
| 8 | `hospitality_tourism` | Hospitality & Tourism | 86KB | 2.0 |
| 9 | `logistics_transportation` | Logistics & Transportation | 80KB | 2.0 |
| 10 | `metal_fabrication` | Metal Fabrication & Manufacturing | 65KB | 2.0 |
| 11 | `pharmaceuticals` | Pharmaceuticals Manufacturing | 78KB | 2.0 |
| 12 | `professional_services` | Professional Services | 80KB | 2.0 |
| 13 | `real_estate` | Real Estate | 76KB | 2.0 |
| 14 | `retail_commerce` | Retail & Commerce | 81KB | 2.0 |
| 15 | `technology_it` | Technology & IT Services | 81KB | 2.0 |
| 16 | `textiles_apparel` | Textiles & Apparel | 84KB | 2.0 |

#### New Sectors (Built with Enhanced Framework)

| # | Sector ID | Sector Name | Size | Version |
|---|-----------|-------------|------|---------|
| 17 | `beauty_wellness` | Beauty & Wellness | 90KB | 1.0 |
| 18 | `creative_industries` | Creative Industries | 96KB | 1.0 |
| 19 | `electronics_manufacturing` | Electronics Manufacturing | 92KB | 1.0 |
| 20 | `energy_utilities` | Energy & Utilities | 91KB | 1.0 |
| 21 | `environmental_services` | Environmental Services | 84KB | 1.0 |
| 22 | `filling_bottling` | Filling & Bottling | 85KB | 1.0 |
| 23 | `food_beverage_manufacturing` | Food & Beverage Manufacturing | 97KB | 1.0 |
| 24 | `furniture_manufacturing` | Furniture Manufacturing | 83KB | 1.0 |
| 25 | `home_based_micro` | Home-Based & Micro Enterprise | 100KB | 1.0 |
| 26 | `maintenance_repair` | Maintenance & Repair Services | 87KB | 1.0 |
| 27 | `paper_printing` | Paper & Printing | 81KB | 1.0 |
| 28 | `plastics_manufacturing` | Plastics Manufacturing | 80KB | 1.0 |
| 29 | `security_services` | Security Services | 86KB | 1.0 |
| 30 | `telecommunications` | Telecommunications | 91KB | 1.0 |
| 31 | `trading_distribution` | Trading & Distribution | 100KB | 1.0 |

**Total: 31 sectors | 2.6 MB | ~60,000 lines**

### 4.2 Enhanced 11-Dimension Framework

Each sector knowledge pack contains the following dimensions plus enhancements:

```typescript
interface SectorKnowledgePack {
  // ─────────────────────────────────────────────────────────────────────
  // METADATA
  // ─────────────────────────────────────────────────────────────────────
  metadata: {
    sector_id: string;
    sector_name: string;
    sector_name_ar: string;
    version: string;
    last_updated: string;
    data_sources: {
      source_id: string;
      name: string;
      type: "government" | "industry_association" | "research" | "international_org" | "proprietary";
      publication_date: string;
      reliability_score: number;  // 0.0-1.0
    }[];
    applicable_countries: string[];  // ["EG", "SA", "AE", "JO", "LB", "MA"]
    sme_size_range: {
      min_employees: number;
      max_employees: number;
      min_revenue_usd: number;
      max_revenue_usd: number;
    };
  };

  // ─────────────────────────────────────────────────────────────────────
  // SECTOR INTRODUCTION (NEW in v2.0)
  // ─────────────────────────────────────────────────────────────────────
  sector_introduction: {
    overview: string;
    why_sector_matters_mena: string;
    sme_role: string;
    value_chain_diagram: string;  // ASCII diagram with SME opportunity mapping
    key_transformations: string[];
  };

  // ─────────────────────────────────────────────────────────────────────
  // THE 11 DIMENSIONS
  // ─────────────────────────────────────────────────────────────────────
  
  // Dimension 1: Industry Classification
  industry_classification: {
    isic_codes: { code: string; description: string; description_ar: string }[];
    subsectors: {
      subsector_id: string;
      name: string;
      name_ar: string;
      isic_class: string;
      description: string;
      service_categories: string[];
      mena_market_size_usd: string;
      growth_rate: string;
      sme_opportunity: {
        level: "very_strong" | "strong" | "medium" | "limited";
        entry_capital: string;
        complexity: string;
        scalability: string;
        notes: string;
      };
    }[];
    value_chain_position: string;
  };

  // Dimension 2: Financial Benchmarks
  financial_benchmarks: {
    key_financial_insight: {  // NEW: Sector-specific insight
      title: string;         // e.g., "API Dependency", "Water Costs", "COD Cash Flow"
      explanation: string;
      impact: string;
      mitigation: string;
    };
    revenue_benchmarks: {
      size_tier: string;
      revenue_range_usd: string;
      typical_characteristics: string;
    }[];
    margin_benchmarks: {
      metric: string;
      poor: string;
      acceptable: string;
      good: string;
      excellent: string;
    }[];
    cost_structure: {
      category: string;
      percentage_range: string;
      notes: string;
    }[];
    capital_requirements: {
      business_type: string;
      startup_capital: string;
      growth_capital: string;
    }[];
    working_capital: {
      dso_days: string;
      dpo_days: string;
      inventory_days: string;
      cash_cycle: string;
    };
  };

  // Dimension 3: Operational KPIs
  operational_kpis: {
    efficiency_metrics: KPIBenchmark[];
    quality_metrics: KPIBenchmark[];
    productivity_metrics: KPIBenchmark[];
    capacity_metrics: KPIBenchmark[];
  };

  // Dimension 4: Regulatory Landscape
  regulatory_landscape: {
    framework_overview: string;
    by_country: {
      country_code: string;
      country_name: string;
      regulatory_authorities: string[];
      key_requirements: {
        requirement: string;
        description: string;
        mandatory: boolean;
      }[];
      licensing: string[];
      compliance_notes: string;
    }[];
    certifications: {
      certification: string;
      purpose: string;
      required_for: string;
      recognition: string;
    }[];
  };

  // Dimension 5: Competitive Dynamics & Risk Profile
  competitive_dynamics: {
    market_structure: {
      subsector: string;
      competition_level: string;
      sme_opportunity: string;
    }[];
    competitive_positioning: string;  // Strategic positioning guidance
    risk_assessment_matrix: {
      risk: string;
      probability: string;
      impact: string;
      overall_risk: string;
      mitigation: string;
    }[];
  };

  // Dimension 6: Digital Maturity
  digital_maturity: {
    maturity_framework: {
      level: number;
      name: string;
      characteristics: string;
    }[];
    mena_adoption: {
      company_type: string;
      level_distribution: { [level: number]: string };
    }[];
    essential_systems: {
      system: string;
      purpose: string;
      investment_range: string;
      priority: string;
    }[];
    technology_roi: {
      technology: string;
      benefit: string;
      implementation_time: string;
    }[];
  };

  // Dimension 7: Workforce Norms
  workforce_norms: {
    organization_structures: string;
    salary_benchmarks: {
      position: string;
      egypt_usd: string;
      saudi_usd: string;
      uae_usd: string;
      jordan_usd: string;
      lebanon_usd: string;
      morocco_usd: string;
    }[];
    critical_skills: {
      skill: string;
      demand: string;
      availability: string;
      premium: string;
    }[];
  };

  // Dimension 8: Supply Chain
  supply_chain: {
    input_dependencies: string[];
    supplier_landscape: string;
    infrastructure_requirements: string[];
    logistics_considerations: string;
  };

  // Dimension 9: Export Requirements
  export_requirements: {
    export_readiness_factors: string[];
    key_markets: string[];
    certifications_required: string[];
    documentation: string[];
    trade_agreements: string[];
  };

  // Dimension 10: Packaging & Presentation
  packaging_labeling: {
    standards_by_market: {
      market: string;
      requirements: string[];
    }[];
    labeling_requirements: string[];
    packaging_trends: string[];
  };

  // Dimension 11: MENA Regional Context
  mena_context: {
    by_country: {
      country_code: string;
      country_name: string;
      market_overview: string;
      key_opportunities: string[];
      key_challenges: string[];
      strategic_recommendations: string[];
      // Lebanon-specific additions
      current_conditions?: string;
      recovery_positioning?: string;
    }[];
    regional_opportunities: string[];
    business_culture: string;
  };

  // ─────────────────────────────────────────────────────────────────────
  // GROWTH & SCALE PATHWAYS (NEW in v2.0)
  // ─────────────────────────────────────────────────────────────────────
  growth_pathways: {
    stages: {
      stage: number;
      name: string;  // Startup, Established, Professional, Regional, Major
      revenue_range: string;
      characteristics: string[];
      focus_areas: string[];
    }[];
    common_decision_points: {
      decision: string;
      considerations: string;
      guidance: string;
    }[];
  };

  // ─────────────────────────────────────────────────────────────────────
  // STRATEGIC SUMMARY (NEW in v2.0)
  // ─────────────────────────────────────────────────────────────────────
  strategic_summary: {
    critical_success_factors: string[];
    common_failure_patterns: string[];
    rootrise_diagnostic_implications: string[];
    red_flags: {
      indicator: string;
      concern: string;
      action: string;
    }[];
    positive_indicators: {
      indicator: string;
      strength: string;
      leverage: string;
    }[];
  };
}
```

### 4.3 Vector Database Design

#### Collection Schema (Qdrant)

```python
# Qdrant Collection: sector_knowledge
sector_knowledge_schema = {
    "collection_name": "sector_knowledge",
    "vectors_config": {
        "size": 1536,           # OpenAI text-embedding-3-small
        "distance": "Cosine"
    },
    "on_disk_payload": True
}

# Chunk Payload Schema
chunk_payload = {
    # Identity
    "chunk_id": "string",           # MD5 hash of sector_id + dimension + path + index
    "sector_id": "string",          # e.g., "food_bev_manufacturing"
    "subsector_id": "string|null",
    "sector_name": "string",
    "sector_name_ar": "string",
    
    # Classification
    "dimension": "integer",         # 1-11 (or 12 for growth_pathways, 13 for strategic_summary)
    "dimension_name": "string",
    "data_type": "string",          # benchmark | regulation | kpi | workforce | supply_chain | export | packaging | mena_context | growth | strategy
    
    # Geographic
    "country_code": "string|null",
    "applicable_countries": "array[string]",
    
    # Content
    "content": "string",
    "content_ar": "string|null",
    "heading_path": "string",       # e.g., "Financial Benchmarks > Profitability > Gross Margin"
    
    # Source Attribution (&I)
    "source_id": "string",
    "source_name": "string",
    "source_type": "string",
    "publication_date": "string",
    
    # Confidence Metadata (&I)
    "source_reliability": "float",  # 0-1
    "data_recency": "string",       # current | recent | dated | historical
    "confidence_score": "float",    # 0-1
    "confidence_rationale": "string",
    
    # Retrieval Optimization
    "keywords": "array[string]",
    "isic_codes": "array[string]",
    
    # Versioning
    "pack_version": "string",
    "indexed_at": "string"
}
```

#### Chunking Strategy

```python
class SectorKnowledgeChunker:
    """
    Chunks sector knowledge packs for vector database ingestion.
    
    Strategy:
    - Semantic boundaries: Don't split mid-concept
    - Target size: 512-1024 tokens
    - Overlap: 50-100 tokens
    - Metadata preservation: Full attribution per chunk
    """
    
    DIMENSION_MAPPING = {
        "industry_classification": (1, "Industry Classification"),
        "financial_benchmarks": (2, "Financial Benchmarks"),
        "operational_kpis": (3, "Operational KPIs"),
        "regulatory_landscape": (4, "Regulatory Landscape"),
        "competitive_dynamics": (5, "Competitive Dynamics"),
        "digital_maturity": (6, "Digital Maturity"),
        "workforce_norms": (7, "Workforce Norms"),
        "supply_chain": (8, "Supply Chain"),
        "export_requirements": (9, "Export Requirements"),
        "packaging_labeling": (10, "Packaging & Labeling"),
        "mena_context": (11, "MENA Regional Context"),
        "growth_pathways": (12, "Growth Pathways"),      # Enhanced
        "strategic_summary": (13, "Strategic Summary"),   # Enhanced
    }
    
    def chunk_sector_pack(self, markdown_file: str, sector_id: str) -> List[VectorChunk]:
        """
        1. Parse JSON metadata block from top of file
        2. Split by Dimension headers
        3. Further split by subsections
        4. Generate chunk metadata
        5. Return list of chunks ready for Qdrant
        """
        pass
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

The questionnaire is the primary data collection mechanism, designed to feel like a consultation rather than a form.

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

### 5.3 Question Schema

```typescript
interface Question {
  // Identity
  id: string;                           // e.g., "BP_001", "FH_012"
  section: SectionCode;                 // "BP" | "FH" | "OP" | "DM" | "WF" | "MK" | "SC" | "EX" | "BR" | "CC"
  subsection?: string;
  order: number;
  
  // Content (Bilingual)
  text: { en: string; ar: string };
  description?: { en: string; ar: string };
  placeholder?: { en: string; ar: string };
  
  // Type & Configuration
  type: QuestionType;
  options?: QuestionOption[];
  scale_config?: ScaleConfig;
  numeric_config?: NumericConfig;
  
  // Behavior
  required: boolean;
  conditional?: ConditionalRule[];      // Show/hide based on other answers
  validation?: ValidationRule[];
  
  // Agent Mapping
  agents: AgentCode[];                  // Which agents consume this data
  data_field: string;                   // Field name in agent input schema
  dimension?: number;                   // Sector Knowledge dimension (1-11)
  
  // &I Philosophy
  allows_human_context: boolean;        // Can user add explanatory note
  human_context_prompt?: { en: string; ar: string };
  confidence_impact: "high" | "medium" | "low";
}

type QuestionType = 
  | "single_choice" | "multiple_choice" | "scale" | "numeric" | "currency"
  | "percentage" | "text_short" | "text_long" | "date" | "date_range"
  | "file_upload" | "matrix" | "ranking" | "slider" | "yes_no"
  | "country_select" | "sector_select" | "human_context";

type AgentCode = "DRUCKER" | "MARVIN" | "GRAHAM" | "LOVELACE" | "MAYO" 
  | "PORTER" | "OHNO" | "RICARDO" | "LANDOR" | "DEMING" | "TUFTE";
```

### 5.4 Agent Data Requirements

```yaml
# Which questions each agent requires

DRUCKER:  # The Supervisor
  required_fields:
    - BP_001  # Company name
    - BP_003  # Country
    - BP_005  # Sector
    - BP_006  # Employee count
    - BP_010  # Strategic priorities
  optional_fields:
    - BP_013  # Primary challenge
    - BP_014  # Human context

GRAHAM:  # The Alchemist (Finance)
  required_fields:
    - FH_001  # Revenue
    - FH_003  # Revenue growth
    - FH_004  # Gross margin
    - FH_005  # Net margin
    - FH_006  # Cash runway
  optional_fields:
    - FH_010  # Funding history
    - FH_012  # Audit status
    - FH_020  # Human context

MARVIN:  # The Sentinel (Operations)
  required_fields:
    - OP_001  # Business model
    - OP_002  # Process maturity
    - OP_005  # Defect rate
    - OP_007  # On-time delivery
  optional_fields:
    - OP_008  # Certifications
    - OP_017  # Human context

LOVELACE:  # The Weaver (Digital)
  required_fields:
    - DM_001  # Digital maturity
    - DM_002  # Current systems
  optional_fields:
    - DM_006  # Analytics maturity
    - DM_012  # Human context

MAYO:  # The Cultivator (HR)
  required_fields:
    - WF_001  # Workforce composition
    - WF_002  # Turnover rate
  optional_fields:
    - WF_007  # Challenges
    - WF_011  # Human context

PORTER:  # The Strategist (Market)
  required_fields:
    - MK_001  # Market size
    - MK_003  # Competitive landscape
  optional_fields:
    - MK_010  # Human context

OHNO:  # The Flow Master (Supply Chain)
  required_fields:
    - SC_002  # Number of suppliers
    - SC_005  # Inventory turns
  optional_fields:
    - SC_012  # Human context

RICARDO:  # The Navigator (Export)
  required_fields:
    - EX_001  # Export status
  conditional_required:  # If exporting
    - EX_002  # Export markets
    - EX_004  # Export certifications
  optional_fields:
    - EX_015  # Human context

LANDOR:  # The Herald (Brand)
  required_fields:
    - BR_001  # Brand awareness
    - BR_003  # Marketing channels
  optional_fields:
    - BR_010  # Human context

DEMING:  # Quality Orchestrator
  aggregates_from:
    - All self_assessment_* fields
    - All *_challenges fields
    - All human_context_* fields

TUFTE:  # Report Generator
  receives:
    - All agent outputs
    - All human_context_* fields
    - Confidence scores from all agents
```

### 5.5 Cross-Field Validation Rules

```yaml
# Validation rules that span multiple questions

REVENUE_EMPLOYEE_CHECK:
  fields: [FH_001, BP_006]
  rule: |
    revenue_per_employee = FH_001.value / BP_006.score
    IF revenue_per_employee < 10000 OR revenue_per_employee > 1000000:
      warning: "Revenue per employee seems unusual - please verify"
  severity: warning

MARGIN_CONSISTENCY:
  fields: [FH_004, FH_005]
  rule: |
    IF FH_004.score < FH_005.score AND FH_004.value != "unsure" AND FH_005.value != "unsure":
      error: "Net margin cannot exceed gross margin"
  severity: error

EXPORT_CERTIFICATION_CHECK:
  fields: [EX_001, EX_004]
  rule: |
    IF EX_001.value == "currently_exporting" AND EX_004.value.length == 0:
      warning: "Exporting without certifications may limit market access"
  severity: warning
```

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

### 6.2 DiagnosticSession Model

```typescript
interface DiagnosticSession {
  // Session Identity
  session_id: string;                    // UUID v4
  sme_id: string;                        // Foreign key to SME profile
  created_at: string;                    // ISO 8601
  updated_at: string;
  expires_at: string;                    // TTL timestamp
  
  // Workflow State
  status: DiagnosticStatus;
  current_phase: DiagnosticPhase;
  current_agent: string | null;
  
  // Configuration
  configuration: {
    selected_agents: string[];           // e.g., ["drucker", "marvin", "graham", "ricardo"]
    sector_id: string;                   // e.g., "food_bev_manufacturing"
    subsector_id?: string;
    selected_lenses: string[];           // e.g., ["EYE-002", "EYE-003"]
    report_format: "executive_summary" | "detailed" | "presentation" | "dashboard";
    language: "en" | "ar" | "bilingual";
    benchmark_set: "mena_regional" | "industry_specific" | "global" | "custom";
  };
  
  // Questionnaire Progress
  questionnaire: {
    total_questions: number;
    completed_questions: number;
    current_section: string;
    responses: QuestionnaireResponse[];
  };
  
  // Agent Execution State
  agent_execution: {
    execution_order: string[];
    completed_agents: string[];
    pending_agents: string[];
  };
  
  // Agent Outputs
  agent_outputs: Record<string, AgentOutput>;
  
  // &I: Human Context
  human_context: HumanContextInjection[];
  human_overrides: HumanOverride[];
  
  // &I: Validation
  pending_validations: ValidationTrigger[];
  
  // Audit Trail
  audit_log: AuditEntry[];
}

type DiagnosticStatus = 
  | "initialized" | "questionnaire" | "processing" 
  | "validation_required" | "report_generation" 
  | "completed" | "abandoned" | "error";

type DiagnosticPhase =
  | "setup" | "data_collection" | "core_analysis" 
  | "specialist_analysis" | "validation" | "synthesis" | "delivery";
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
│   │(Supervisor) │                                                           │
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
│   │  └────────┘ └────────┘ └────────┘ └────────┘   │                       │
│   │  ┌────────┐ ┌────────┐                          │                       │
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
        "unverified_claims_threshold": 2,
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
    selected_lenses: List[str]           # e.g., ["EYE-002", "EYE-003"]
    benchmark_set: str
    language: str
    
    # Sector Intelligence
    sector_intelligence: Dict[str, Any]
    
    # Lens Configuration (loaded based on selected_lenses)
    active_lens_configs: List[Dict[str, Any]]
    
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

# SME Management
POST   /sme/register                     # Register new SME
GET    /sme/{id}/profile                 # Get SME profile
PUT    /sme/{id}/profile                 # Update profile
GET    /sme/{id}/history                 # Get diagnostic history
POST   /sme/{id}/local-context           # Add local context
GET    /sme/{id}/ai-assumptions          # What AI thinks it knows

# Configuration
GET    /config/sectors                   # List available sectors
GET    /config/sectors/{id}              # Get sector details
GET    /config/lenses                    # List available lenses
GET    /config/lenses/{id}               # Get lens configuration
GET    /config/agents                    # List available agents
```

### 8.2 Key Request/Response Schemas

```typescript
// POST /diagnostic/initiate
interface InitiateDiagnosticRequest {
  sme_id: string;
  configuration: {
    selected_agents: string[];           // Core agents auto-included
    sector_id: string;
    subsector_id?: string;
    selected_lenses: string[];           // At least one lens required
    report_format: "executive_summary" | "detailed" | "presentation" | "dashboard";
    language: "en" | "ar" | "bilingual";
    benchmark_set: "mena_regional" | "industry_specific" | "global" | "custom";
  };
}

interface InitiateDiagnosticResponse {
  session_id: string;
  status: "initialized";
  questionnaire_url: string;
  estimated_completion_time: string;
  sections: {
    code: string;
    name: string;
    question_count: number;
    required: boolean;
  }[];
}

// GET /diagnostic/{id}/status
interface DiagnosticStatusResponse {
  session_id: string;
  status: DiagnosticStatus;
  current_phase: DiagnosticPhase;
  progress: {
    questionnaire_completion: number;    // 0-100
    agents_completed: string[];
    agents_pending: string[];
    overall_percentage: number;
  };
  pending_validations: ValidationTrigger[];
  preliminary_confidence: number;        // 0-1
  estimated_remaining_time: string;
}

// GET /diagnostic/{id}/report
interface DiagnosticReport {
  report_id: string;
  session_id: string;
  generated_at: string;
  
  // SME Context
  sme_name: string;
  sector: string;
  country: string;
  
  // Applied Lenses
  applied_lenses: {
    lens_id: string;
    lens_name: string;
    weight: number;
  }[];
  
  // Overall Results
  overall_score: number;                 // 0-100
  overall_confidence: number;            // 0-1
  
  // Executive Summary
  executive_summary: {
    headline: string;
    key_strengths: string[];
    critical_gaps: string[];
    top_recommendations: string[];
  };
  
  // Dimension Scores (lens-weighted)
  dimension_scores: {
    dimension: string;
    score: number;
    benchmark: number;
    gap: number;
    confidence: number;
    lens_weight: number;                 // How this lens weighted this dimension
  }[];
  
  // Agent Findings (by agent)
  agent_findings: {
    agent_id: string;
    agent_name: string;
    findings: {
      finding_id: string;
      title: string;
      description: string;
      confidence: number;
      evidence: string[];
      lens_relevance: string[];          // Which lenses this is relevant to
    }[];
  }[];
  
  // Action Plan (lens-prioritized)
  action_plan: {
    lens_priorities: {
      lens_id: string;
      lens_name: string;
      priority_actions: ActionItem[];
    }[];
    quick_wins: ActionItem[];
    transformation_roadmap: ActionItem[];
  };
  
  // &I Transparency
  ai_transparency: {
    data_coverage: string;
    key_assumptions: string[];
    areas_of_uncertainty: string[];
    human_inputs: number;
    human_overrides: number;
    sources_used: string[];
  };
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
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                      EXTERNAL SERVICES                               │    │
│  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐                │    │
│  │  │   OpenAI     │  │   Cohere     │  │  SendGrid    │                │    │
│  │  │  (GPT-4o)    │  │ (Embeddings) │  │  (Emails)    │                │    │
│  │  └──────────────┘  └──────────────┘  └──────────────┘                │    │
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
| **API Servers** | 2-4 × t3.medium | $60-120 |
| **LangGraph Workers** | 2-6 × c6i.large | $120-360 |
| **PostgreSQL** | db.t3.medium | $50 |
| **Redis** | cache.t3.medium | $45 |
| **Qdrant** | t3.large (8GB RAM) | $60 |
| **S3 Storage** | 500GB | $12 |
| **Load Balancer** | ALB | $25 |
| **Subtotal Compute** | | **$372-672** |

| External Service | Usage | Monthly Cost |
|------------------|-------|--------------|
| **OpenAI GPT-4o** | 100 diagnostics × 50K tokens | $250 |
| **OpenAI Embeddings** | Incremental | $5 |
| **SendGrid** | 1000 emails | $15 |
| **Subtotal APIs** | | **$270** |

| **TOTAL** | @ 100 diagnostics/month | **$642-942** |

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
| **Phase 1: Foundation** | 4 weeks | PostgreSQL, Redis, FastAPI, Auth |
| **Phase 2: Memory & State** | 3 weeks | Session management, human context/override |
| **Phase 3: LangGraph** | 3 weeks | State schema, nodes, HITL gates, checkpoints |
| **Phase 4: Agents** | 3 weeks | Core agents, add-on agents, utility agents |
| **Phase 5: Vector DB** | 2 weeks | Chunking pipeline, indexing 31 sectors |
| **Phase 6: Questionnaire** | 2 weeks | 10 sections, validation, agent mapping |
| **Phase 7: Lens System** | 2 weeks | 15 lenses, priority weighting |
| **Phase 8: API** | 2 weeks | Full REST API, WebSocket, docs |
| **Phase 9: Testing** | 2 weeks | Integration, load, security |
| **Phase 10: Deployment** | 1 week | Infrastructure, CI/CD, monitoring |
| **TOTAL** | **24 weeks** | |

---

## Part 11: Implementation Checklist

### Weeks 1-4: Foundation
- [ ] PostgreSQL schema (SME profiles, diagnostic records)
- [ ] Redis setup (session management)
- [ ] FastAPI application structure
- [ ] Authentication/authorization
- [ ] Memory manager implementation

### Weeks 5-7: LangGraph Core
- [ ] PantheonState schema
- [ ] Drucker node (supervisor)
- [ ] Marvin node (diagnostics)
- [ ] Graham node (finance)
- [ ] HITL gates (4 gates)
- [ ] Checkpointing with SQLite

### Weeks 8-10: Agents & Parallel Execution
- [ ] Add-on agents (Ricardo, Lovelace, Mayo, Ohno, Porter, Landor)
- [ ] Utility agents (Deming, Tufte)
- [ ] Parallel execution coordinator
- [ ] Cross-agent state management

### Weeks 11-12: Vector Database
- [ ] Chunking pipeline for 31 sectors
- [ ] Index ~75,000 chunks
- [ ] Retrieval implementation
- [ ] Confidence metadata

### Weeks 13-14: Questionnaire System
- [ ] 10-section schema
- [ ] ~145 questions with translations
- [ ] Conditional logic engine
- [ ] Cross-field validation
- [ ] Agent data mapping

### Weeks 15-16: Lens System
- [ ] 15 lens configurations
- [ ] Agent priority matrix
- [ ] Dimension weighting
- [ ] Report customization by lens

### Weeks 17-18: API Development
- [ ] Core diagnostic endpoints
- [ ] &I override endpoints
- [ ] &I transparency endpoints
- [ ] WebSocket for real-time updates
- [ ] OpenAPI documentation

### Weeks 19-20: Testing
- [ ] Unit tests for all components
- [ ] Integration tests (end-to-end diagnostic)
- [ ] Load testing (100 concurrent diagnostics)
- [ ] Security audit

### Weeks 21-24: Deployment & Polish
- [ ] AWS infrastructure setup
- [ ] CI/CD pipeline
- [ ] Monitoring and alerting
- [ ] Documentation
- [ ] Staging deployment
- [ ] Production deployment

---

## Appendix A: Complete Sector Index

### Legacy Sectors (v2.0)
1. Agriculture & Agribusiness
2. Automotive
3. Chemicals, Plastics & Specialty
4. Construction & Building
5. Education & Training
6. Financial Services
7. Healthcare Services
8. Hospitality & Tourism
9. Logistics & Transportation
10. Metal Fabrication & Manufacturing
11. Pharmaceuticals Manufacturing
12. Professional Services
13. Real Estate
14. Retail & Commerce
15. Technology & IT Services
16. Textiles & Apparel

### New Sectors (v1.0)
17. Beauty & Wellness
18. Creative Industries
19. Electronics Manufacturing
20. Energy & Utilities
21. Environmental Services
22. Filling & Bottling
23. Food & Beverage Manufacturing
24. Furniture Manufacturing
25. Home-Based & Micro Enterprise
26. Maintenance & Repair Services
27. Paper & Printing
28. Plastics Manufacturing
29. Security Services
30. Telecommunications
31. Trading & Distribution

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
| **The &Eye** | RootRise's 15 transformation lenses that reframe diagnostic priorities |
| **My Sector** | The 31 sector knowledge packs providing industry intelligence |
| **HITL** | Human-in-the-Loop - checkpoints where human review is triggered |
| **Sector Knowledge Pack** | Structured intelligence file (11+ dimensions) for a specific industry |
| **Validation Gate** | One of 4 HITL checkpoints in the diagnostic workflow |
| **Confidence Score** | 0-1 metric indicating AI certainty in a finding |
| **Human Context Injection** | User-provided local knowledge that AI incorporates |
| **Human Override** | User correction of an AI-generated finding |

---

*Document Version: 1.1*  
*Prepared by: Tee (the Ionganic*  
*For: Ahmed El-Gazzar (Technical DevOps Lead)*  
*RootRise by DEVONEERS — January 2026*
