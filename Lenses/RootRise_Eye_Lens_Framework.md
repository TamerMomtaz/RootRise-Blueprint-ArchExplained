# RootRise v6.0 — The &Eye Lens Framework

**Document Version:** 1.0  
**Last Updated:** December 11, 2025  
**Status:** Production-Ready Framework  
**Author:** Tee (Product Creative Strategist)  
**For:** Ahmed El-Gazzar (Technical DevOps Lead) & Development Team

---

## Table of Contents

1. [Overview](#1-overview)
2. [The &Eye Philosophy](#2-the-eye-philosophy)
3. [Lens Architecture](#3-lens-architecture)
4. [Complete Lens Definitions](#4-complete-lens-definitions)
5. [Lens-to-Agent Priority Matrix](#5-lens-to-agent-priority-matrix)
6. [Lens-Based Report Prioritization](#6-lens-based-report-prioritization)
7. [LangGraph Integration](#7-langgraph-integration)
8. [API Specifications](#8-api-specifications)
9. [Data Schemas](#9-data-schemas)
10. [UI Behavior Specifications](#10-ui-behavior-specifications)
11. [Multi-Lens Conflict Resolution](#11-multi-lens-conflict-resolution)
12. [Quick Reference](#12-quick-reference)

---

## 1. Overview

### 1.1 What is The &Eye?

The &Eye is the third configuration layer of the RootRise diagnostic system. While The Pantheon defines *who* analyzes the SME (agents) and My Sector defines *with what context* (sector intelligence), The &Eye defines *toward what goal* (transformation objective).

```
┌─────────────────────────────────────────────────────────────────────────┐
│                    THE THREE CONFIGURATION LAYERS                        │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│  LAYER 1: THE PANTHEON          "WHO analyzes?"                         │
│  ├─ 11 specialist agents                                                 │
│  ├─ User selects Add-On agents                                           │
│  └─ Core agents always included                                          │
│                                                                          │
│  LAYER 2: MY SECTOR             "WITH WHAT context?"                     │
│  ├─ 27 industry contexts                                                 │
│  ├─ 11 intelligence dimensions per sector                                │
│  └─ MENA-specific benchmarks and regulations                             │
│                                                                          │
│  LAYER 3: THE &EYE              "TOWARD WHAT goal?"                      │
│  ├─ 15 transformation lenses                                             │
│  ├─ Reprioritizes agent focus                                            │
│  └─ Reshapes report structure and recommendations                        │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

### 1.2 The Core Insight

**"The same SME, analyzed through different lenses, gets different—but equally rigorous—transformation paths."**

An SME with identical data analyzed through:
- **Export Readiness** lens → Focus on certification gaps, international packaging, market entry strategy
- **Succession Planning** lens → Focus on organizational structure, process documentation, leadership development
- **Profitability** lens → Focus on cost structure, pricing optimization, waste reduction

Same data. Different priorities. Different recommendations. Different report structure.

### 1.3 Document Purpose

This document provides Ahmed and the development team with:
1. Complete definitions for all 15 transformation lenses
2. Agent priority matrices for each lens
3. Report content prioritization rules
4. LangGraph workflow integration specifications
5. API endpoint definitions
6. Data schemas for lens configuration
7. Multi-lens conflict resolution logic

---

## 2. The &Eye Philosophy

### 2.1 Design Principles

```
┌─────────────────────────────────────────────────────────────────────────┐
│                      THE &EYE DESIGN PRINCIPLES                          │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│  1. GOAL-DRIVEN ANALYSIS                                                 │
│     Every finding is evaluated against the user's stated objective.      │
│     Relevance to the lens determines prominence, not just severity.      │
│                                                                          │
│  2. WEIGHT ADJUSTMENT, NOT DATA FILTERING                                │
│     Lenses don't hide data—they reprioritize it.                         │
│     All findings remain accessible; focus determines emphasis.           │
│                                                                          │
│  3. SAME RIGOR, DIFFERENT LENS                                           │
│     Export Readiness lens demands the same analytical depth              │
│     as Investment Attraction. Only the focal point changes.              │
│                                                                          │
│  4. HUMAN AGENCY PRESERVED                                               │
│     The SME owner chooses their lens based on their goals.               │
│     The system serves the goal; it doesn't impose one.                   │
│                                                                          │
│  5. TRANSPARENT REASONING                                                │
│     When a lens prioritizes certain findings, the "why" is visible.      │
│     "Highlighted because you selected Export Readiness"                  │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Lens as a "Transformation Objective"

Each lens answers a specific user question:

| Lens Category | User's Burning Question |
|---------------|-------------------------|
| **The Crema** | "What can I fix RIGHT NOW with minimal effort?" |
| **Growth** | "How do I expand—export, raise capital, find partners?" |
| **Transition** | "How do I prepare to step back—retire, sell, hand over?" |
| **Operations** | "How do I run better—margins, processes, technology?" |
| **Impact** | "How do I create broader value—jobs, sustainability, supply chains?" |

### 2.3 &I Philosophy Integration

The &Eye embodies the &I philosophy by:
1. **Letting the human define success** — The SME owner's goal drives the analysis
2. **Making AI priorities transparent** — The user can see why findings are weighted
3. **Supporting, not dictating** — Recommendations align with stated objectives
4. **Preserving agency** — The user can change lenses mid-diagnostic or view alternative perspectives

---

## 3. Lens Architecture

### 3.1 Lens Categories

```
┌─────────────────────────────────────────────────────────────────────────┐
│                       15 TRANSFORMATION LENSES                           │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│  [FEATURED] THE CREMA                                                    │
│  └─ Quick Wins Focus (30-60-90 days, low effort, high impact)           │
│                                                                          │
│  [GROWTH OBJECTIVES - 3 Lenses]                                          │
│  ├─ Export Readiness          "I want to sell internationally"          │
│  ├─ Investment Attraction     "I want to raise capital"                  │
│  └─ Partnership / JV          "I want to find a partner"                 │
│                                                                          │
│  [TRANSITION OBJECTIVES - 3 Lenses]                                      │
│  ├─ Owner Succession          "I want to retire / step back"             │
│  ├─ Inheritance Prep          "I want to pass to my children"            │
│  └─ Sale / Exit               "I want to sell the company"               │
│                                                                          │
│  [OPERATIONS OBJECTIVES - 3 Lenses]                                      │
│  ├─ Profitability             "I want better margins"                    │
│  ├─ Operational Excellence    "I want to run better"                     │
│  └─ Digital Transformation    "I want to modernize"                      │
│                                                                          │
│  [IMPACT OBJECTIVES - 4 Lenses]                                          │
│  ├─ Sustainability / ESG      "I want to be green"                       │
│  ├─ Employment Growth         "I want to create jobs"                    │
│  ├─ Supply Chain Integration  "I want to join a value chain"             │
│  └─ Local Development         "I want community impact"                  │
│                                                                          │
│  [CUSTOM]                                                                │
│  └─ Custom Objective          "I have a specific goal"                   │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Lens Data Structure

```typescript
interface TransformationLens {
  // Core identification
  lens_id: string;                    // e.g., "export_readiness"
  display_name: string;               // e.g., "Export Readiness"
  category: LensCategory;
  
  // User-facing content
  user_statement: string;             // "I want to sell internationally"
  short_description: string;          // Shown on lens card
  detailed_description: string;       // Shown when lens is expanded
  
  // Visual elements
  icon: string;                       // Icon identifier or emoji
  accent_color: string;               // Optional lens-specific accent
  
  // Focus tags (shown on UI cards)
  focus_tags: string[];               // e.g., ["Certifications", "Logistics", "Compliance"]
  
  // Behavior configuration
  agent_priority_adjustments: AgentPriorityAdjustment[];
  report_section_order: string[];
  content_prioritization: ContentPrioritizationRule[];
  
  // Feature flags
  is_featured: boolean;               // The Crema = true
  is_default_selected: boolean;       // The Crema = true (can be deselected)
  allows_multi_select: boolean;       // Can be combined with other lenses
  
  // Metadata
  created_at: string;
  updated_at: string;
}

type LensCategory = 
  | 'featured'      // The Crema
  | 'growth'        // Export, Investment, Partnership
  | 'transition'    // Succession, Inheritance, Sale
  | 'operations'    // Profitability, Excellence, Digital
  | 'impact'        // Sustainability, Employment, Supply Chain, Local
  | 'custom';       // User-defined
```

### 3.3 Lens Selection Behavior

```typescript
interface LensSelectionRules {
  // The Crema behavior
  the_crema: {
    is_pre_selected: true;           // Selected by default
    can_be_deselected: true;         // User can turn it off
    spans_full_width: true;          // UI: spans 3 columns at top
    combines_with_others: true;       // Can be active with other lenses
  };
  
  // Standard lens behavior
  standard_lenses: {
    multi_select_allowed: true;       // Can select multiple
    max_simultaneous_lenses: 3;       // Limit to avoid confusion
    conflict_resolution: 'weighted_average'; // How to handle overlaps
  };
  
  // Custom lens behavior
  custom_lens: {
    requires_description: true;       // User must describe their goal
    ai_interprets_priority: true;     // System infers agent weights
    allows_combination: false;        // Custom lens is exclusive
  };
}
```

---

## 4. Complete Lens Definitions

### 4.1 The Crema (Featured Lens)

```yaml
lens_id: "the_crema"
display_name: "The Crema"
category: "featured"
user_statement: "I want quick wins NOW — show me what I can achieve in 30-60-90 days before we go deeper."

short_description: "Quick Wins Focus"
detailed_description: |
  The Crema extracts the highest-value, lowest-effort improvements from the 
  diagnostic. These are the "cream of the crop" — actions that can be implemented 
  quickly and show visible results to stakeholders. Ideal for building momentum 
  before deeper transformation, or for demonstrating early value to funders/investors.

focus_tags:
  - "30-60-90 Days"
  - "Low Effort"
  - "High Impact"

icon: "☕"
is_featured: true
is_default_selected: true

# What this lens delivers
lens_delivers:
  - "30-60-90 day action plans"
  - "Low effort, high impact wins"
  - "Visible results for stakeholders"
  - "Cost optimization quick hits"
  - "Momentum before deep transformation"

# Agent prioritization
priority_agents:
  - agent_id: "ohno"
    reason: "Waste reduction often yields fastest wins"
  - agent_id: "graham"
    reason: "Cash flow improvements are immediately visible"
  - agent_id: "marvin"
    reason: "Process quick fixes across all dimensions"

# Scoring criteria
quick_win_criteria:
  effort_threshold: "low" | "medium"  # Exclude high-effort items
  impact_threshold: "high" | "very_high"  # Only high-impact items
  timeline_days_max: 90
  
# Report emphasis
report_sections_emphasized:
  - "quick_wins_summary"
  - "30_day_actions"
  - "60_day_actions"
  - "90_day_actions"
  - "momentum_metrics"

report_sections_de_emphasized:
  - "long_term_strategy"
  - "complex_implementations"
  - "multi_year_roadmaps"
```

### 4.2 Growth Objectives

#### 4.2.1 Export Readiness

```yaml
lens_id: "export_readiness"
display_name: "Export Readiness"
category: "growth"
user_statement: "I want to sell internationally"

short_description: "Prepare for international market entry"
detailed_description: |
  Assesses and develops your readiness to enter international markets.
  Covers certification gaps, compliance requirements, logistics capabilities,
  and market entry strategies. Prioritizes findings that directly impact
  your ability to export successfully.

focus_tags:
  - "Certifications"
  - "Logistics"
  - "Compliance"

icon: "🌍"
is_featured: false
is_default_selected: false

# Agent prioritization (higher weight = more emphasis)
agent_priority_adjustments:
  - agent_id: "ricardo"
    weight_multiplier: 1.5
    focus_dimensions: ["certification_compliance", "market_knowledge", "export_experience"]
  - agent_id: "landor"
    weight_multiplier: 1.5
    focus_dimensions: ["labeling_compliance", "packaging_export_readiness", "multi_market_compliance"]
  - agent_id: "ohno"
    weight_multiplier: 1.2
    focus_dimensions: ["logistics_efficiency", "quality_performance", "production_capacity"]
  - agent_id: "graham"
    weight_multiplier: 1.0  # Normal weight
    focus_dimensions: ["export_financing", "currency_management"]

# Auto-select these agents if not already selected
auto_select_agents: ["ricardo", "landor"]

# Report section ordering
report_section_order:
  - "export_readiness_score"
  - "certification_gap_analysis"
  - "target_market_recommendations"
  - "compliance_roadmap"
  - "packaging_assessment"
  - "logistics_evaluation"
  - "financial_readiness"
  - "quick_wins_export"
  - "full_roadmap"

# Content prioritization
content_prioritization:
  lead_with: ["export_assessment", "certification_gaps"]
  emphasize: ["market_opportunities", "compliance_roadmap", "packaging_readiness"]
  de_emphasize: ["domestic_operations", "internal_processes"]
```

#### 4.2.2 Investment Attraction

```yaml
lens_id: "investment_attraction"
display_name: "Investment Attraction"
category: "growth"
user_statement: "I want to raise capital"

short_description: "Become investor-ready"
detailed_description: |
  Prepares your business to attract investment from banks, VCs, 
  development funds, or strategic investors. Focuses on financial health,
  governance structures, valuation drivers, and investment readiness gaps.
  Identifies what investors look for and where you fall short.

focus_tags:
  - "Financials"
  - "Governance"
  - "Valuation"

icon: "💰"
is_featured: false
is_default_selected: false

agent_priority_adjustments:
  - agent_id: "graham"
    weight_multiplier: 1.5
    focus_dimensions: ["financial_health", "funding_readiness", "capital_structure"]
  - agent_id: "porter"
    weight_multiplier: 1.3
    focus_dimensions: ["competitive_position", "market_opportunity", "strategic_clarity"]
  - agent_id: "mayo"
    weight_multiplier: 1.2
    focus_dimensions: ["governance", "organizational_structure", "management_depth"]
  - agent_id: "marvin"
    weight_multiplier: 1.1
    focus_dimensions: ["process_documentation", "operational_maturity"]

auto_select_agents: ["porter"]

report_section_order:
  - "investment_readiness_score"
  - "financial_health_summary"
  - "governance_assessment"
  - "valuation_drivers"
  - "market_position"
  - "growth_potential"
  - "risk_factors"
  - "investor_ready_roadmap"

content_prioritization:
  lead_with: ["financial_health", "governance_assessment"]
  emphasize: ["valuation_drivers", "investment_readiness", "risk_mitigation"]
  de_emphasize: ["operational_details", "technical_specifics"]
```

#### 4.2.3 Partnership / JV

```yaml
lens_id: "partnership_jv"
display_name: "Partnership / JV"
category: "growth"
user_statement: "I want to find a partner"

short_description: "Prepare for strategic partnerships"
detailed_description: |
  Assesses readiness for joint ventures, strategic partnerships, or 
  co-development arrangements. Evaluates governance readiness, 
  complementarity factors, and areas that would attract or concern
  potential partners.

focus_tags:
  - "Governance"
  - "Complementarity"
  - "Readiness"

icon: "🤝"
is_featured: false
is_default_selected: false

agent_priority_adjustments:
  - agent_id: "porter"
    weight_multiplier: 1.4
    focus_dimensions: ["strategic_positioning", "value_proposition", "market_access"]
  - agent_id: "mayo"
    weight_multiplier: 1.3
    focus_dimensions: ["governance", "organizational_independence", "partnership_readiness"]
  - agent_id: "graham"
    weight_multiplier: 1.2
    focus_dimensions: ["financial_transparency", "valuation"]

auto_select_agents: ["porter"]

report_section_order:
  - "partnership_readiness_score"
  - "value_proposition"
  - "complementarity_analysis"
  - "governance_readiness"
  - "potential_partner_profiles"
  - "partnership_risks"
  - "readiness_roadmap"

content_prioritization:
  lead_with: ["value_proposition", "complementarity"]
  emphasize: ["governance_readiness", "strategic_assets"]
  de_emphasize: ["internal_operations", "cost_structure"]
```

### 4.3 Transition Objectives

#### 4.3.1 Owner Succession

```yaml
lens_id: "owner_succession"
display_name: "Owner Succession"
category: "transition"
user_statement: "I want to retire / step back"

short_description: "Prepare the business to run without you"
detailed_description: |
  Evaluates how dependent the business is on you personally and 
  develops a plan for you to step back while the business thrives.
  Focuses on organizational independence, process documentation,
  and leadership development.

focus_tags:
  - "HR"
  - "Processes"
  - "Independence"

icon: "👤"
is_featured: false
is_default_selected: false

agent_priority_adjustments:
  - agent_id: "mayo"
    weight_multiplier: 1.5
    focus_dimensions: ["owner_dependence", "management_depth", "succession_planning", "skills_gaps"]
  - agent_id: "marvin"
    weight_multiplier: 1.3
    focus_dimensions: ["process_documentation", "decision_centralization", "knowledge_capture"]
  - agent_id: "lovelace"
    weight_multiplier: 1.1
    focus_dimensions: ["systems_independence", "automation"]

auto_select_agents: ["mayo"]

report_section_order:
  - "owner_dependence_score"
  - "organizational_readiness"
  - "management_depth_assessment"
  - "process_documentation_gaps"
  - "knowledge_transfer_needs"
  - "succession_candidates"
  - "transition_roadmap"

content_prioritization:
  lead_with: ["owner_dependence", "organizational_readiness"]
  emphasize: ["succession_planning", "process_documentation", "leadership_development"]
  de_emphasize: ["growth_metrics", "market_expansion"]
```

#### 4.3.2 Inheritance Prep

```yaml
lens_id: "inheritance_prep"
display_name: "Inheritance Prep"
category: "transition"
user_statement: "I want to pass to my children"

short_description: "Prepare for family succession"
detailed_description: |
  Addresses the unique challenges of passing a business to the next 
  generation. Covers legal structures, family governance, next-gen
  readiness, and protecting the business through the transition.

focus_tags:
  - "Legal"
  - "Family Gov"
  - "Succession"

icon: "👨‍👩‍👧‍👦"
is_featured: false
is_default_selected: false

agent_priority_adjustments:
  - agent_id: "mayo"
    weight_multiplier: 1.5
    focus_dimensions: ["family_governance", "next_gen_readiness", "role_clarity"]
  - agent_id: "graham"
    weight_multiplier: 1.3
    focus_dimensions: ["ownership_structure", "legal_considerations", "estate_planning"]
  - agent_id: "marvin"
    weight_multiplier: 1.2
    focus_dimensions: ["process_documentation", "institutional_knowledge"]

auto_select_agents: ["mayo"]

report_section_order:
  - "inheritance_readiness_score"
  - "legal_structure_assessment"
  - "family_governance_analysis"
  - "next_gen_capability_assessment"
  - "knowledge_transfer_plan"
  - "risk_mitigation"
  - "transition_timeline"

content_prioritization:
  lead_with: ["legal_structure", "family_governance"]
  emphasize: ["next_gen_readiness", "succession_risks", "knowledge_transfer"]
  de_emphasize: ["market_growth", "competitive_position"]
```

#### 4.3.3 Sale / Exit

```yaml
lens_id: "sale_exit"
display_name: "Sale / Exit"
category: "transition"
user_statement: "I want to sell the company"

short_description: "Maximize value for sale"
detailed_description: |
  Prepares your business for acquisition by maximizing valuation
  and minimizing deal-breakers. Focuses on clean books, due diligence
  readiness, valuation drivers, and red flags that would concern buyers.

focus_tags:
  - "Valuation"
  - "Due Diligence"
  - "Clean Books"

icon: "🏷️"
is_featured: false
is_default_selected: false

agent_priority_adjustments:
  - agent_id: "graham"
    weight_multiplier: 1.5
    focus_dimensions: ["financial_audit_readiness", "valuation", "clean_financials"]
  - agent_id: "porter"
    weight_multiplier: 1.3
    focus_dimensions: ["market_position", "competitive_moat", "strategic_value"]
  - agent_id: "mayo"
    weight_multiplier: 1.2
    focus_dimensions: ["key_person_risk", "contracts", "compliance"]
  - agent_id: "marvin"
    weight_multiplier: 1.1
    focus_dimensions: ["documentation", "process_maturity"]

auto_select_agents: ["porter"]

report_section_order:
  - "sale_readiness_score"
  - "valuation_assessment"
  - "due_diligence_readiness"
  - "financial_health"
  - "deal_breaker_risks"
  - "value_enhancement_opportunities"
  - "sale_preparation_roadmap"

content_prioritization:
  lead_with: ["valuation_drivers", "due_diligence_gaps"]
  emphasize: ["clean_books", "risk_mitigation", "strategic_value"]
  de_emphasize: ["operational_improvements", "long_term_growth"]
```

### 4.4 Operations Objectives

#### 4.4.1 Profitability

```yaml
lens_id: "profitability"
display_name: "Profitability"
category: "operations"
user_statement: "I want better margins"

short_description: "Find the profit leaks"
detailed_description: |
  Identifies where your profits are leaking and how to plug them.
  Deep dive into cost structure, pricing optimization, waste
  elimination, and efficiency improvements that directly impact
  your bottom line.

focus_tags:
  - "Costs"
  - "Efficiency"
  - "Pricing"

icon: "📈"
is_featured: false
is_default_selected: false

agent_priority_adjustments:
  - agent_id: "graham"
    weight_multiplier: 1.5
    focus_dimensions: ["cost_structure", "margin_analysis", "pricing"]
  - agent_id: "ohno"
    weight_multiplier: 1.4
    focus_dimensions: ["waste_reduction", "efficiency", "productivity"]
  - agent_id: "porter"
    weight_multiplier: 1.1
    focus_dimensions: ["pricing_power", "competitive_pricing"]

auto_select_agents: ["ohno"]

report_section_order:
  - "profitability_assessment"
  - "cost_structure_analysis"
  - "waste_identification"
  - "pricing_optimization"
  - "efficiency_opportunities"
  - "margin_improvement_roadmap"
  - "financial_projections"

content_prioritization:
  lead_with: ["margin_gaps", "cost_structure"]
  emphasize: ["waste_reduction", "pricing_optimization", "efficiency_gains"]
  de_emphasize: ["growth_investment", "market_expansion"]
```

#### 4.4.2 Operational Excellence

```yaml
lens_id: "operational_excellence"
display_name: "Operational Excellence"
category: "operations"
user_statement: "I want to run better"

short_description: "Optimize processes and quality"
detailed_description: |
  Systematic improvement of how your business operates. Covers
  process optimization, quality management, lean principles,
  and building operational consistency that scales.

focus_tags:
  - "Processes"
  - "Quality"
  - "Lean"

icon: "⚙️"
is_featured: false
is_default_selected: false

agent_priority_adjustments:
  - agent_id: "ohno"
    weight_multiplier: 1.5
    focus_dimensions: ["lean_operations", "process_improvement", "waste_elimination"]
  - agent_id: "marvin"
    weight_multiplier: 1.3
    focus_dimensions: ["process_maturity", "operational_gaps", "quality_systems"]
  - agent_id: "lovelace"
    weight_multiplier: 1.1
    focus_dimensions: ["automation_opportunities", "process_digitization"]

auto_select_agents: ["ohno"]

report_section_order:
  - "operational_maturity_score"
  - "process_assessment"
  - "waste_analysis"
  - "quality_gaps"
  - "automation_opportunities"
  - "improvement_roadmap"
  - "implementation_priorities"

content_prioritization:
  lead_with: ["process_gaps", "operational_waste"]
  emphasize: ["quality_improvement", "lean_opportunities", "automation"]
  de_emphasize: ["market_strategy", "financial_engineering"]
```

#### 4.4.3 Digital Transformation

```yaml
lens_id: "digital_transformation"
display_name: "Digital Transformation"
category: "operations"
user_statement: "I want to modernize"

short_description: "Build your technology roadmap"
detailed_description: |
  Assesses your digital maturity and builds a practical roadmap
  for modernization. Covers tech stack, automation, digital
  presence, and data-driven decision making.

focus_tags:
  - "Tech Stack"
  - "Automation"
  - "Digital"

icon: "💻"
is_featured: false
is_default_selected: false

agent_priority_adjustments:
  - agent_id: "lovelace"
    weight_multiplier: 1.5
    focus_dimensions: ["digital_maturity", "tech_stack", "automation", "data_readiness"]
  - agent_id: "marvin"
    weight_multiplier: 1.2
    focus_dimensions: ["process_digitization", "digital_gaps"]
  - agent_id: "mayo"
    weight_multiplier: 1.1
    focus_dimensions: ["digital_skills", "change_readiness"]

auto_select_agents: ["lovelace"]

report_section_order:
  - "digital_maturity_score"
  - "tech_stack_assessment"
  - "automation_opportunities"
  - "digital_gaps"
  - "skills_assessment"
  - "technology_roadmap"
  - "investment_priorities"

content_prioritization:
  lead_with: ["digital_maturity", "tech_gaps"]
  emphasize: ["automation_opportunities", "digital_skills", "tech_roadmap"]
  de_emphasize: ["non_digital_operations", "traditional_processes"]
```

### 4.5 Impact Objectives

#### 4.5.1 Sustainability / ESG

```yaml
lens_id: "sustainability_esg"
display_name: "Sustainability / ESG"
category: "impact"
user_statement: "I want to be green"

short_description: "Achieve ESG compliance and sustainability"
detailed_description: |
  Assesses environmental, social, and governance performance.
  Identifies sustainability gaps, green certification opportunities,
  and ESG improvements that increasingly matter to customers,
  investors, and regulators.

focus_tags:
  - "Environmental"
  - "Social"
  - "Governance"

icon: "🌱"
is_featured: false
is_default_selected: false

agent_priority_adjustments:
  - agent_id: "ohno"
    weight_multiplier: 1.4
    focus_dimensions: ["resource_efficiency", "waste_reduction", "energy_consumption"]
  - agent_id: "landor"
    weight_multiplier: 1.3
    focus_dimensions: ["sustainable_packaging", "environmental_labeling"]
  - agent_id: "mayo"
    weight_multiplier: 1.2
    focus_dimensions: ["social_compliance", "workplace_safety", "fair_labor"]
  - agent_id: "graham"
    weight_multiplier: 1.1
    focus_dimensions: ["governance", "esg_reporting"]

auto_select_agents: ["ohno", "landor"]

report_section_order:
  - "esg_readiness_score"
  - "environmental_assessment"
  - "social_assessment"
  - "governance_assessment"
  - "certification_opportunities"
  - "sustainability_roadmap"
  - "impact_metrics"

content_prioritization:
  lead_with: ["environmental_gaps", "esg_readiness"]
  emphasize: ["sustainability_opportunities", "certification_paths", "impact_metrics"]
  de_emphasize: ["financial_optimization", "market_expansion"]
```

#### 4.5.2 Employment Growth

```yaml
lens_id: "employment_growth"
display_name: "Employment Growth"
category: "impact"
user_statement: "I want to create jobs"

short_description: "Scale your workforce effectively"
detailed_description: |
  Focuses on growing your workforce in a sustainable, effective way.
  Covers hiring capacity, skills development, workforce planning,
  and organizational scaling. Relevant for development programs
  with job creation mandates.

focus_tags:
  - "HR Capacity"
  - "Scaling"
  - "Workforce"

icon: "👥"
is_featured: false
is_default_selected: false

agent_priority_adjustments:
  - agent_id: "mayo"
    weight_multiplier: 1.5
    focus_dimensions: ["workforce_planning", "hiring_capacity", "skills_development"]
  - agent_id: "marvin"
    weight_multiplier: 1.2
    focus_dimensions: ["organizational_scalability", "process_capacity"]
  - agent_id: "graham"
    weight_multiplier: 1.1
    focus_dimensions: ["labor_cost_management", "growth_financing"]

auto_select_agents: ["mayo"]

report_section_order:
  - "employment_capacity_score"
  - "current_workforce_analysis"
  - "hiring_readiness"
  - "skills_gaps"
  - "organizational_scalability"
  - "workforce_growth_roadmap"
  - "job_creation_projections"

content_prioritization:
  lead_with: ["workforce_capacity", "hiring_readiness"]
  emphasize: ["skills_development", "organizational_scaling", "job_creation"]
  de_emphasize: ["automation", "cost_reduction"]
```

#### 4.5.3 Supply Chain Integration

```yaml
lens_id: "supply_chain_integration"
display_name: "Supply Chain Integration"
category: "impact"
user_statement: "I want to join a value chain"

short_description: "Become a qualified supplier"
detailed_description: |
  Assesses readiness to integrate into larger supply chains as a
  qualified supplier. Covers quality systems, logistics capabilities,
  compliance requirements, and supplier qualification standards.

focus_tags:
  - "Supplier Ready"
  - "Quality"
  - "Logistics"

icon: "🔗"
is_featured: false
is_default_selected: false

agent_priority_adjustments:
  - agent_id: "ohno"
    weight_multiplier: 1.5
    focus_dimensions: ["supply_chain_capability", "quality_systems", "logistics"]
  - agent_id: "landor"
    weight_multiplier: 1.3
    focus_dimensions: ["packaging_compliance", "labeling_standards"]
  - agent_id: "marvin"
    weight_multiplier: 1.2
    focus_dimensions: ["certification_status", "process_documentation"]

auto_select_agents: ["ohno", "landor"]

report_section_order:
  - "supplier_readiness_score"
  - "quality_systems_assessment"
  - "logistics_capability"
  - "certification_status"
  - "compliance_gaps"
  - "supplier_qualification_roadmap"
  - "target_buyer_recommendations"

content_prioritization:
  lead_with: ["supplier_readiness", "quality_gaps"]
  emphasize: ["certification_needs", "logistics_improvement", "compliance"]
  de_emphasize: ["market_strategy", "brand_development"]
```

#### 4.5.4 Local Development

```yaml
lens_id: "local_development"
display_name: "Local Development"
category: "impact"
user_statement: "I want community impact"

short_description: "Maximize local economic impact"
detailed_description: |
  Focuses on the SME's contribution to local economic development.
  Covers local sourcing, community employment, supplier development,
  and broader economic multiplier effects. Relevant for development
  programs with community impact mandates.

focus_tags:
  - "Local Sourcing"
  - "Jobs"
  - "Community"

icon: "🏘️"
is_featured: false
is_default_selected: false

agent_priority_adjustments:
  - agent_id: "ohno"
    weight_multiplier: 1.3
    focus_dimensions: ["local_sourcing", "supplier_development"]
  - agent_id: "mayo"
    weight_multiplier: 1.3
    focus_dimensions: ["local_employment", "community_engagement", "skills_transfer"]
  - agent_id: "porter"
    weight_multiplier: 1.1
    focus_dimensions: ["local_market_position", "community_relationships"]

auto_select_agents: ["mayo"]

report_section_order:
  - "local_impact_score"
  - "local_employment_analysis"
  - "local_sourcing_assessment"
  - "community_engagement"
  - "supplier_development_opportunities"
  - "impact_enhancement_roadmap"
  - "impact_metrics"

content_prioritization:
  lead_with: ["local_impact", "community_engagement"]
  emphasize: ["local_sourcing", "job_creation", "supplier_development"]
  de_emphasize: ["international_expansion", "cost_optimization"]
```

### 4.6 Custom Objective

```yaml
lens_id: "custom_objective"
display_name: "Custom Objective"
category: "custom"
user_statement: "I have a specific goal"

short_description: "Define your own transformation objective"
detailed_description: |
  For goals not covered by the 14 predefined lenses. Describe your
  specific objective, and the system will interpret it to prioritize
  the relevant aspects of the diagnostic.

focus_tags:
  - "User-Defined"
  - "Flexible"

icon: "✨"
is_featured: false
is_default_selected: false

# Custom lens requires additional input
requires_user_input: true
user_input_prompt: "Describe your specific transformation goal:"
user_input_type: "textarea"
user_input_max_length: 500

# AI interprets the custom goal
ai_interpretation:
  enabled: true
  model: "drucker"  # The supervisor agent interprets
  interpretation_prompt: |
    Based on the user's custom goal description, determine:
    1. Which agents should be prioritized (weight multipliers)
    2. Which dimensions are most relevant
    3. What report sections should lead
    4. What content should be emphasized/de-emphasized
    
# Cannot be combined with other lenses (exclusive)
allows_combination: false
```

---

## 5. Lens-to-Agent Priority Matrix

### 5.1 Complete Matrix

```typescript
const lensPriorityMatrix: Record<string, AgentPriorityConfig> = {
  // THE CREMA
  "the_crema": {
    primary_agents: ["ohno", "graham", "marvin"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.3,
      "graham": 1.3,
      "ricardo": 1.0,
      "lovelace": 1.0,
      "mayo": 1.0,
      "ohno": 1.4,
      "porter": 1.0,
      "landor": 1.0
    },
    auto_select_addons: [],
    filter_criteria: { effort: ["low", "medium"], impact: ["high", "very_high"], timeline_days_max: 90 }
  },
  
  // GROWTH
  "export_readiness": {
    primary_agents: ["ricardo", "landor"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.1,
      "graham": 1.0,
      "ricardo": 1.5,
      "lovelace": 0.9,
      "mayo": 0.9,
      "ohno": 1.2,
      "porter": 1.0,
      "landor": 1.5
    },
    auto_select_addons: ["ricardo", "landor"]
  },
  
  "investment_attraction": {
    primary_agents: ["graham", "porter", "mayo"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.1,
      "graham": 1.5,
      "ricardo": 0.8,
      "lovelace": 0.9,
      "mayo": 1.2,
      "ohno": 0.9,
      "porter": 1.3,
      "landor": 0.8
    },
    auto_select_addons: ["porter"]
  },
  
  "partnership_jv": {
    primary_agents: ["porter", "mayo", "graham"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.1,
      "graham": 1.2,
      "ricardo": 0.9,
      "lovelace": 0.9,
      "mayo": 1.3,
      "ohno": 0.9,
      "porter": 1.4,
      "landor": 0.8
    },
    auto_select_addons: ["porter"]
  },
  
  // TRANSITION
  "owner_succession": {
    primary_agents: ["mayo", "marvin"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.3,
      "graham": 1.0,
      "ricardo": 0.7,
      "lovelace": 1.1,
      "mayo": 1.5,
      "ohno": 0.9,
      "porter": 0.8,
      "landor": 0.7
    },
    auto_select_addons: ["mayo"]
  },
  
  "inheritance_prep": {
    primary_agents: ["mayo", "graham"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.2,
      "graham": 1.3,
      "ricardo": 0.7,
      "lovelace": 0.9,
      "mayo": 1.5,
      "ohno": 0.8,
      "porter": 0.8,
      "landor": 0.7
    },
    auto_select_addons: ["mayo"]
  },
  
  "sale_exit": {
    primary_agents: ["graham", "porter"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.1,
      "graham": 1.5,
      "ricardo": 0.8,
      "lovelace": 0.9,
      "mayo": 1.2,
      "ohno": 0.9,
      "porter": 1.3,
      "landor": 0.8
    },
    auto_select_addons: ["porter"]
  },
  
  // OPERATIONS
  "profitability": {
    primary_agents: ["graham", "ohno"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.1,
      "graham": 1.5,
      "ricardo": 0.8,
      "lovelace": 1.0,
      "mayo": 0.9,
      "ohno": 1.4,
      "porter": 1.1,
      "landor": 0.8
    },
    auto_select_addons: ["ohno"]
  },
  
  "operational_excellence": {
    primary_agents: ["ohno", "marvin"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.3,
      "graham": 0.9,
      "ricardo": 0.8,
      "lovelace": 1.1,
      "mayo": 1.0,
      "ohno": 1.5,
      "porter": 0.8,
      "landor": 0.9
    },
    auto_select_addons: ["ohno"]
  },
  
  "digital_transformation": {
    primary_agents: ["lovelace", "marvin"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.2,
      "graham": 1.0,
      "ricardo": 0.8,
      "lovelace": 1.5,
      "mayo": 1.1,
      "ohno": 1.0,
      "porter": 0.9,
      "landor": 0.8
    },
    auto_select_addons: ["lovelace"]
  },
  
  // IMPACT
  "sustainability_esg": {
    primary_agents: ["ohno", "landor", "mayo"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.1,
      "graham": 1.1,
      "ricardo": 0.9,
      "lovelace": 0.9,
      "mayo": 1.2,
      "ohno": 1.4,
      "porter": 0.9,
      "landor": 1.3
    },
    auto_select_addons: ["ohno", "landor"]
  },
  
  "employment_growth": {
    primary_agents: ["mayo", "marvin"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.2,
      "graham": 1.1,
      "ricardo": 0.8,
      "lovelace": 0.8,
      "mayo": 1.5,
      "ohno": 1.0,
      "porter": 0.9,
      "landor": 0.8
    },
    auto_select_addons: ["mayo"]
  },
  
  "supply_chain_integration": {
    primary_agents: ["ohno", "landor"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.2,
      "graham": 1.0,
      "ricardo": 1.0,
      "lovelace": 0.9,
      "mayo": 0.9,
      "ohno": 1.5,
      "porter": 0.9,
      "landor": 1.3
    },
    auto_select_addons: ["ohno", "landor"]
  },
  
  "local_development": {
    primary_agents: ["mayo", "ohno"],
    agent_weights: {
      "drucker": 1.0,
      "marvin": 1.1,
      "graham": 1.0,
      "ricardo": 0.8,
      "lovelace": 0.8,
      "mayo": 1.3,
      "ohno": 1.3,
      "porter": 1.1,
      "landor": 0.9
    },
    auto_select_addons: ["mayo"]
  }
};
```

### 5.2 Visual Matrix

```
┌──────────────────────────────────────────────────────────────────────────────────────┐
│                        LENS → AGENT PRIORITY MATRIX                                   │
├──────────────────────────────────────────────────────────────────────────────────────┤
│                        │ Mar │ Gra │ Ric │ Lov │ May │ Ohn │ Por │ Lan │             │
│ LENS                   │ vin │ ham │ rdo │ lac │  o  │ o   │ ter │ dor │ AUTO-SELECT │
├────────────────────────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────────────┤
│ The Crema              │ 1.3 │ 1.3 │ 1.0 │ 1.0 │ 1.0 │ 1.4★│ 1.0 │ 1.0 │ None        │
├────────────────────────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────────────┤
│ Export Readiness       │ 1.1 │ 1.0 │ 1.5★│ 0.9 │ 0.9 │ 1.2 │ 1.0 │ 1.5★│ Ric, Lan    │
│ Investment Attraction  │ 1.1 │ 1.5★│ 0.8 │ 0.9 │ 1.2 │ 0.9 │ 1.3★│ 0.8 │ Por         │
│ Partnership / JV       │ 1.1 │ 1.2 │ 0.9 │ 0.9 │ 1.3★│ 0.9 │ 1.4★│ 0.8 │ Por         │
├────────────────────────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────────────┤
│ Owner Succession       │ 1.3★│ 1.0 │ 0.7 │ 1.1 │ 1.5★│ 0.9 │ 0.8 │ 0.7 │ May         │
│ Inheritance Prep       │ 1.2 │ 1.3★│ 0.7 │ 0.9 │ 1.5★│ 0.8 │ 0.8 │ 0.7 │ May         │
│ Sale / Exit            │ 1.1 │ 1.5★│ 0.8 │ 0.9 │ 1.2 │ 0.9 │ 1.3★│ 0.8 │ Por         │
├────────────────────────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────────────┤
│ Profitability          │ 1.1 │ 1.5★│ 0.8 │ 1.0 │ 0.9 │ 1.4★│ 1.1 │ 0.8 │ Ohn         │
│ Operational Excellence │ 1.3★│ 0.9 │ 0.8 │ 1.1 │ 1.0 │ 1.5★│ 0.8 │ 0.9 │ Ohn         │
│ Digital Transformation │ 1.2 │ 1.0 │ 0.8 │ 1.5★│ 1.1 │ 1.0 │ 0.9 │ 0.8 │ Lov         │
├────────────────────────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────────────┤
│ Sustainability / ESG   │ 1.1 │ 1.1 │ 0.9 │ 0.9 │ 1.2 │ 1.4★│ 0.9 │ 1.3★│ Ohn, Lan    │
│ Employment Growth      │ 1.2 │ 1.1 │ 0.8 │ 0.8 │ 1.5★│ 1.0 │ 0.9 │ 0.8 │ May         │
│ Supply Chain Integ.    │ 1.2 │ 1.0 │ 1.0 │ 0.9 │ 0.9 │ 1.5★│ 0.9 │ 1.3★│ Ohn, Lan    │
│ Local Development      │ 1.1 │ 1.0 │ 0.8 │ 0.8 │ 1.3★│ 1.3★│ 1.1 │ 0.9 │ May         │
└────────────────────────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────────────┘

★ = Primary agent for this lens (highest weight)
```

---

## 6. Lens-Based Report Prioritization

### 6.1 Report Section Ordering

Each lens defines a preferred order for report sections. The Tufte uses this to structure the final deliverable.

```typescript
interface LensReportConfig {
  lens_id: string;
  
  // Sections that should appear first (lead the narrative)
  lead_sections: string[];
  
  // Sections that get expanded treatment
  emphasized_sections: string[];
  
  // Sections that are condensed/abbreviated
  de_emphasized_sections: string[];
  
  // Sections that may be moved to appendix
  appendix_candidates: string[];
  
  // Special formatting rules
  formatting_rules: {
    quick_wins_prominent: boolean;      // Show quick wins in executive summary?
    include_timeline_visual: boolean;   // Show roadmap timeline chart?
    score_card_style: 'detailed' | 'summary';
  };
}

const lensReportConfigs: Record<string, LensReportConfig> = {
  "the_crema": {
    lens_id: "the_crema",
    lead_sections: [
      "quick_wins_summary",
      "30_day_actions",
      "60_day_actions",
      "90_day_actions"
    ],
    emphasized_sections: [
      "momentum_metrics",
      "stakeholder_visibility_wins",
      "cost_savings_quick_hits"
    ],
    de_emphasized_sections: [
      "long_term_strategy",
      "complex_implementations",
      "multi_year_roadmaps"
    ],
    appendix_candidates: [
      "detailed_assessments",
      "methodology_notes"
    ],
    formatting_rules: {
      quick_wins_prominent: true,
      include_timeline_visual: true,
      score_card_style: 'summary'
    }
  },
  
  "export_readiness": {
    lens_id: "export_readiness",
    lead_sections: [
      "export_readiness_score",
      "certification_gap_analysis",
      "target_market_recommendations"
    ],
    emphasized_sections: [
      "compliance_roadmap",
      "packaging_assessment",
      "logistics_evaluation"
    ],
    de_emphasized_sections: [
      "hr_assessment",
      "domestic_market_analysis"
    ],
    appendix_candidates: [
      "internal_process_details",
      "non_export_findings"
    ],
    formatting_rules: {
      quick_wins_prominent: true,
      include_timeline_visual: true,
      score_card_style: 'detailed'
    }
  },
  
  // ... additional configs for each lens
};
```

### 6.2 Content Prioritization Logic

```typescript
interface ContentPrioritizer {
  /**
   * Calculates display priority for a finding based on active lenses
   */
  calculatePriority(
    finding: Finding,
    activeLenses: string[]
  ): number;
  
  /**
   * Determines section placement based on lens configuration
   */
  determinePlacement(
    content: ReportContent,
    lensConfig: LensReportConfig
  ): 'lead' | 'main_body' | 'appendix' | 'excluded';
}

// Priority calculation example
function calculateFindingPriority(
  finding: Finding,
  activeLenses: string[]
): number {
  // Base priority from finding's inherent importance
  let priority = finding.impact === 'high' ? 0.8 :
                 finding.impact === 'medium' ? 0.5 : 0.3;
  
  // Adjust based on lens relevance
  for (const lensId of activeLenses) {
    const lensConfig = lensReportConfigs[lensId];
    
    // Boost if finding's domain is in emphasized sections
    if (lensConfig.emphasized_sections.some(s => 
        finding.domain.includes(s))) {
      priority *= 1.3;
    }
    
    // Reduce if finding's domain is de-emphasized
    if (lensConfig.de_emphasized_sections.some(s => 
        finding.domain.includes(s))) {
      priority *= 0.7;
    }
  }
  
  // Special handling for The Crema
  if (activeLenses.includes('the_crema')) {
    // Only high priority if it's a quick win
    if (finding.effort === 'high' || finding.timeline_days > 90) {
      priority *= 0.5;  // Reduce priority for non-quick-wins
    }
  }
  
  return Math.min(priority, 1.0);  // Cap at 1.0
}
```

---

## 7. LangGraph Integration

### 7.1 Lens Injection into Diagnostic State

```typescript
interface DiagnosticState {
  // ... existing fields ...
  
  // Lens configuration (added at initialization)
  lens_configuration: {
    active_lenses: string[];           // e.g., ["the_crema", "export_readiness"]
    primary_lens: string;              // First selected (highest priority)
    custom_lens_description?: string;  // If custom lens is active
    
    // Computed at initialization
    computed_agent_weights: Record<string, number>;
    auto_selected_agents: string[];
    report_section_order: string[];
  };
}
```

### 7.2 Lens Processing Node

The Drucker (supervisor) processes lens configuration at the start of each diagnostic:

```typescript
// LangGraph node definition
const processLensConfiguration: StateGraphNode = {
  name: "process_lens_configuration",
  
  async execute(state: DiagnosticState): Promise<Partial<DiagnosticState>> {
    const { active_lenses, custom_lens_description } = state.lens_configuration;
    
    // Step 1: Calculate combined agent weights
    const combinedWeights = calculateCombinedWeights(active_lenses);
    
    // Step 2: Determine auto-selected agents
    const autoSelectedAgents = determineAutoSelectedAgents(active_lenses);
    
    // Step 3: Compute report section order
    const sectionOrder = computeSectionOrder(active_lenses);
    
    // Step 4: Handle custom lens (if present)
    let interpretedCustomLens = null;
    if (active_lenses.includes('custom_objective') && custom_lens_description) {
      interpretedCustomLens = await interpretCustomLens(custom_lens_description);
    }
    
    return {
      lens_configuration: {
        ...state.lens_configuration,
        computed_agent_weights: combinedWeights,
        auto_selected_agents: autoSelectedAgents,
        report_section_order: sectionOrder,
        interpreted_custom_lens: interpretedCustomLens
      }
    };
  }
};

function calculateCombinedWeights(lenses: string[]): Record<string, number> {
  const weights: Record<string, number> = {
    drucker: 1.0, marvin: 1.0, graham: 1.0, ricardo: 1.0,
    lovelace: 1.0, mayo: 1.0, ohno: 1.0, porter: 1.0, landor: 1.0
  };
  
  // Average weights across all active lenses
  for (const agentId of Object.keys(weights)) {
    let totalWeight = 0;
    for (const lensId of lenses) {
      const lensWeights = lensPriorityMatrix[lensId]?.agent_weights;
      if (lensWeights && lensWeights[agentId]) {
        totalWeight += lensWeights[agentId];
      }
    }
    weights[agentId] = totalWeight / lenses.length;
  }
  
  return weights;
}
```

### 7.3 Agent Execution with Lens Context

Each agent receives lens context in its input:

```typescript
interface AgentInput {
  // ... existing fields ...
  
  lens_context: {
    active_lenses: string[];
    my_weight: number;                  // This agent's computed weight
    my_focus_dimensions: string[];      // Dimensions to emphasize
    is_primary_for_lens: boolean;       // Am I a primary agent for any active lens?
    report_section_ownership: string[]; // Which report sections I'm responsible for
  };
}
```

### 7.4 LangGraph Workflow Diagram

```
┌─────────────────────────────────────────────────────────────────────────┐
│                    DIAGNOSTIC WORKFLOW WITH LENS INTEGRATION             │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│  [START] → [Initialize Session]                                          │
│                    ↓                                                     │
│            [Load User Configuration]                                     │
│            ├─ Selected Agents (The Pantheon)                            │
│            ├─ Selected Sector (My Sector)                               │
│            └─ Selected Lenses (The &Eye) ← LENS INJECTION               │
│                    ↓                                                     │
│        ┌───────────────────────────┐                                    │
│        │ PROCESS LENS CONFIGURATION │ ← Drucker processes lenses        │
│        │ • Calculate agent weights  │                                    │
│        │ • Auto-select agents       │                                    │
│        │ • Compute section order    │                                    │
│        │ • Interpret custom lens    │                                    │
│        └─────────────┬─────────────┘                                    │
│                      ↓                                                   │
│        ┌───────────────────────────┐                                    │
│        │   DRUCKER ORCHESTRATES     │                                    │
│        │ • Routes to agents         │                                    │
│        │ • Applies weight priority  │ ← Lens weights affect execution   │
│        │ • Manages dependencies     │                                    │
│        └─────────────┬─────────────┘                                    │
│                      ↓                                                   │
│    ┌─────────────────┼─────────────────┐                                │
│    ↓                 ↓                 ↓                                 │
│ [MARVIN]         [GRAHAM]         [ADD-ONs]                             │
│ weight: 1.3      weight: 1.5      weights: varied                       │
│ ← Each agent knows its lens-adjusted weight and focus dimensions        │
│    └─────────────────┼─────────────────┘                                │
│                      ↓                                                   │
│        ┌───────────────────────────┐                                    │
│        │       THE DEMING           │                                    │
│        │ • Validates outputs        │                                    │
│        │ • Cross-agent checks       │                                    │
│        └─────────────┬─────────────┘                                    │
│                      ↓                                                   │
│        ┌───────────────────────────┐                                    │
│        │       THE TUFTE            │                                    │
│        │ • Applies lens priorities  │ ← LENS AFFECTS REPORT STRUCTURE   │
│        │ • Orders sections          │                                    │
│        │ • Emphasizes content       │                                    │
│        │ • Generates deliverable    │                                    │
│        └─────────────┬─────────────┘                                    │
│                      ↓                                                   │
│                  [FINAL REPORT]                                          │
│                  Structured by lens priorities                           │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## 8. API Specifications

### 8.1 Lens Endpoints

```yaml
# Get available lenses
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
  interpreted_priorities: AgentPriorityConfig
  suggested_report_order: string[]
  confidence: number
```

### 8.2 Diagnostic Configuration Endpoints (Lens-Aware)

```yaml
# Initialize diagnostic with lens configuration
POST /api/v1/diagnostic/initiate
Request:
  sme_id: string
  configuration:
    selected_agents: string[]          # From The Pantheon
    sector_id: string                  # From My Sector
    selected_lenses: string[]          # From The &Eye
    custom_lens_description?: string   # If custom lens
Response:
  diagnostic_id: string
  computed_configuration:
    final_agent_list: string[]         # Including auto-selected
    agent_weights: Record<string, number>
    report_section_order: string[]
  estimated_duration_minutes: number

# Get lens impact preview (before starting diagnostic)
POST /api/v1/diagnostic/lens-preview
Request:
  configuration:
    selected_agents: string[]
    sector_id: string
    selected_lenses: string[]
Response:
  preview:
    agents_affected: AgentImpact[]
    report_structure_preview: string[]
    focus_areas: string[]
    de_emphasized_areas: string[]
```

### 8.3 Report Endpoints (Lens-Aware)

```yaml
# Get report with lens explanation
GET /api/v1/diagnostic/{id}/report
Query params:
  include_lens_reasoning: boolean      # Include why content is prioritized
Response:
  report: FullReport
  lens_reasoning?: {
    active_lenses: string[]
    content_prioritization_explanation: string
    alternative_views_available: string[]  # Other lenses user could apply
  }

# Get report through different lens (post-hoc)
POST /api/v1/diagnostic/{id}/report/alternate-lens
Request:
  alternate_lens_id: string
Response:
  report: FullReport                   # Same data, different structure
  comparison: {
    sections_reordered: string[]
    newly_emphasized: string[]
    newly_de_emphasized: string[]
  }
```

---

## 9. Data Schemas

### 9.1 Lens Definition Schema (Database)

```sql
CREATE TABLE transformation_lenses (
  lens_id VARCHAR(50) PRIMARY KEY,
  display_name VARCHAR(100) NOT NULL,
  category VARCHAR(20) NOT NULL,
  user_statement VARCHAR(500) NOT NULL,
  short_description VARCHAR(200) NOT NULL,
  detailed_description TEXT NOT NULL,
  icon VARCHAR(10) NOT NULL,
  accent_color VARCHAR(7),
  focus_tags JSONB NOT NULL,              -- ["tag1", "tag2"]
  is_featured BOOLEAN DEFAULT FALSE,
  is_default_selected BOOLEAN DEFAULT FALSE,
  allows_multi_select BOOLEAN DEFAULT TRUE,
  agent_priority_adjustments JSONB NOT NULL,  -- AgentPriorityAdjustment[]
  report_section_order JSONB NOT NULL,        -- string[]
  content_prioritization JSONB NOT NULL,      -- ContentPrioritizationRule[]
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW(),
  
  CONSTRAINT valid_category CHECK (category IN 
    ('featured', 'growth', 'transition', 'operations', 'impact', 'custom'))
);

CREATE TABLE diagnostic_lens_selections (
  diagnostic_id UUID NOT NULL REFERENCES diagnostics(id),
  lens_id VARCHAR(50) NOT NULL REFERENCES transformation_lenses(lens_id),
  selection_order INT NOT NULL,           -- 1 = primary, 2 = secondary, etc.
  custom_description TEXT,                -- Only for custom lens
  selected_at TIMESTAMP DEFAULT NOW(),
  
  PRIMARY KEY (diagnostic_id, lens_id)
);

CREATE TABLE lens_computed_configurations (
  diagnostic_id UUID PRIMARY KEY REFERENCES diagnostics(id),
  active_lenses JSONB NOT NULL,           -- string[]
  primary_lens VARCHAR(50) NOT NULL,
  computed_agent_weights JSONB NOT NULL,  -- Record<string, number>
  auto_selected_agents JSONB NOT NULL,    -- string[]
  report_section_order JSONB NOT NULL,    -- string[]
  computed_at TIMESTAMP DEFAULT NOW()
);
```

### 9.2 TypeScript Types (Frontend/Backend)

```typescript
// Core lens type
interface TransformationLens {
  lens_id: string;
  display_name: string;
  category: LensCategory;
  user_statement: string;
  short_description: string;
  detailed_description: string;
  icon: string;
  accent_color?: string;
  focus_tags: string[];
  is_featured: boolean;
  is_default_selected: boolean;
  allows_multi_select: boolean;
  agent_priority_adjustments: AgentPriorityAdjustment[];
  report_section_order: string[];
  content_prioritization: ContentPrioritizationRule[];
}

type LensCategory = 
  | 'featured' 
  | 'growth' 
  | 'transition' 
  | 'operations' 
  | 'impact' 
  | 'custom';

interface AgentPriorityAdjustment {
  agent_id: string;
  weight_multiplier: number;
  focus_dimensions: string[];
}

interface ContentPrioritizationRule {
  action: 'lead_with' | 'emphasize' | 'de_emphasize' | 'exclude';
  content_types: string[];
}

// Diagnostic configuration with lenses
interface DiagnosticConfiguration {
  selected_agents: string[];
  sector_id: string;
  selected_lenses: string[];
  custom_lens_description?: string;
}

// Computed lens configuration
interface ComputedLensConfiguration {
  active_lenses: string[];
  primary_lens: string;
  computed_agent_weights: Record<string, number>;
  auto_selected_agents: string[];
  report_section_order: string[];
  interpreted_custom_lens?: InterpretedCustomLens;
}

interface InterpretedCustomLens {
  original_description: string;
  inferred_focus_areas: string[];
  suggested_agent_weights: Record<string, number>;
  confidence_score: number;
}
```

---

## 10. UI Behavior Specifications

### 10.1 Lens Selection Screen

```typescript
interface LensSelectionUISpec {
  // Screen layout
  layout: {
    screen_title: "What's Your Transformation Goal?";
    subtitle: "Select the lens that matches your primary objective. This prioritizes your diagnostic.";
    step_indicator: "STEP 3 OF 3";
  };
  
  // The Crema positioning
  the_crema: {
    position: "top";
    width: "full";                       // Spans all 3 columns
    is_pre_selected: true;
    badge: "NEW";
    highlight_color: "accent";           // Stand out visually
  };
  
  // Standard lenses
  standard_lenses: {
    layout: "grid";
    columns: 2;                          // 2 columns below The Crema
    card_style: "selectable";
    show_focus_tags: true;
    show_icon: true;
  };
  
  // Selection behavior
  selection: {
    multi_select: true;
    max_selections: 3;
    show_selection_count: true;          // "2 of 3 selected"
    warn_at_max: true;                   // "Maximum lenses selected"
  };
  
  // Information panel (sidebar)
  info_panel: {
    position: "right";
    show_on_hover: true;
    content: {
      lens_name: true;
      detailed_description: true;
      what_it_delivers: true;
      priority_agents: true;             // "Priority Agents Activated"
    };
  };
  
  // Navigation
  navigation: {
    back_button: true;                   // "← Back"
    next_button: {
      label: "▶ Generate Diagnostic";
      enabled_when: "at_least_one_lens_selected";
    };
    footer_info: "Ready to generate your diagnostic • {agent_count} agents • {sector_name} • {lens_names}";
  };
}
```

### 10.2 Lens Card Component

```typescript
interface LensCardProps {
  lens: TransformationLens;
  is_selected: boolean;
  on_select: (lens_id: string) => void;
  is_disabled: boolean;                  // If max selections reached
}

interface LensCardVisualSpec {
  // Default state
  default: {
    background: "transparent";
    border: "1px solid var(--border-subtle)";
    border_radius: "8px";
    padding: "16px";
  };
  
  // Selected state
  selected: {
    background: "var(--teal-subtle)";
    border: "2px solid var(--bright-teal)";
    show_checkmark: true;
  };
  
  // Hover state
  hover: {
    border: "1px solid var(--border-hover)";
    show_info_trigger: true;             // "Learn more" appears
  };
  
  // Card content
  content: {
    icon: { size: "24px", position: "top-left" };
    lens_name: { font_size: "16px", font_weight: "600" };
    user_statement: { font_size: "14px", color: "var(--text-secondary)", style: "italic" };
    focus_tags: { display: "inline-pills", max_visible: 3 };
  };
}
```

### 10.3 Known UI Bug

```typescript
// BUG: The Crema toggle doesn't properly deselect
// EXPECTED: Clicking selected Crema should deselect it
// ACTUAL: Crema remains selected after click

// FIX NEEDED in lens_selection_handler:
function handleLensClick(lensId: string, currentState: SelectionState) {
  if (lensId === 'the_crema' && currentState.selected_lenses.includes('the_crema')) {
    // BUG: This branch is not executing
    return {
      ...currentState,
      selected_lenses: currentState.selected_lenses.filter(l => l !== 'the_crema')
    };
  }
  // ... rest of handler
}
```

---

## 11. Multi-Lens Conflict Resolution

### 11.1 Weight Combination Strategy

When multiple lenses are active, agent weights are combined:

```typescript
type WeightCombinationStrategy = 'average' | 'max' | 'weighted_primary';

// Current strategy: weighted_primary
// Primary lens (first selected) gets 60% weight, others split 40%
function combineWeights(
  lenses: string[],
  strategy: WeightCombinationStrategy = 'weighted_primary'
): Record<string, number> {
  const agents = ['drucker', 'marvin', 'graham', 'ricardo', 'lovelace', 'mayo', 'ohno', 'porter', 'landor'];
  const combined: Record<string, number> = {};
  
  for (const agent of agents) {
    switch (strategy) {
      case 'average':
        combined[agent] = lenses.reduce((sum, lens) => 
          sum + (lensPriorityMatrix[lens]?.agent_weights[agent] || 1.0), 0) / lenses.length;
        break;
        
      case 'max':
        combined[agent] = Math.max(...lenses.map(lens => 
          lensPriorityMatrix[lens]?.agent_weights[agent] || 1.0));
        break;
        
      case 'weighted_primary':
        const primaryWeight = lensPriorityMatrix[lenses[0]]?.agent_weights[agent] || 1.0;
        const secondaryWeights = lenses.slice(1).map(lens => 
          lensPriorityMatrix[lens]?.agent_weights[agent] || 1.0);
        const secondaryAvg = secondaryWeights.length > 0 
          ? secondaryWeights.reduce((a, b) => a + b, 0) / secondaryWeights.length 
          : 1.0;
        combined[agent] = (primaryWeight * 0.6) + (secondaryAvg * 0.4);
        break;
    }
  }
  
  return combined;
}
```

### 11.2 Report Section Merge Logic

When multiple lenses suggest different section orders:

```typescript
function mergeSectionOrders(lenses: string[]): string[] {
  // Get section orders for each lens
  const sectionOrders = lenses.map(lens => 
    lensReportConfigs[lens]?.lead_sections || []);
  
  // Primary lens sections come first
  const primarySections = sectionOrders[0] || [];
  
  // Add unique sections from secondary lenses
  const merged = [...primarySections];
  for (let i = 1; i < sectionOrders.length; i++) {
    for (const section of sectionOrders[i]) {
      if (!merged.includes(section)) {
        merged.push(section);
      }
    }
  }
  
  return merged;
}
```

### 11.3 Conflict Resolution Rules

```typescript
interface ConflictResolutionRules {
  // If two lenses emphasize conflicting areas
  content_emphasis_conflict: {
    rule: "primary_lens_wins";
    secondary_lens_action: "include_but_de_emphasize";
  };
  
  // If lenses suggest different agent priorities
  agent_priority_conflict: {
    rule: "weighted_combination";
    primary_weight: 0.6;
    secondary_weight: 0.4;
  };
  
  // If custom lens conflicts with standard lens
  custom_lens_conflict: {
    rule: "custom_lens_exclusive";
    action: "custom_lens_replaces_all";
  };
  
  // The Crema + other lens
  crema_combination: {
    rule: "crema_filters_results";
    action: "apply_quick_win_filter_to_all_findings";
    timeline_filter: 90;  // Days
    effort_filter: ["low", "medium"];
  };
}
```

---

## 12. Quick Reference

### 12.1 Lens Summary Table

| Lens ID | Display Name | Category | Primary Agents | Auto-Select |
|---------|--------------|----------|----------------|-------------|
| `the_crema` | The Crema | featured | Ohno, Graham, Marvin | None |
| `export_readiness` | Export Readiness | growth | Ricardo, Landor | Ricardo, Landor |
| `investment_attraction` | Investment Attraction | growth | Graham, Porter | Porter |
| `partnership_jv` | Partnership / JV | growth | Porter, Mayo | Porter |
| `owner_succession` | Owner Succession | transition | Mayo, Marvin | Mayo |
| `inheritance_prep` | Inheritance Prep | transition | Mayo, Graham | Mayo |
| `sale_exit` | Sale / Exit | transition | Graham, Porter | Porter |
| `profitability` | Profitability | operations | Graham, Ohno | Ohno |
| `operational_excellence` | Operational Excellence | operations | Ohno, Marvin | Ohno |
| `digital_transformation` | Digital Transformation | operations | Lovelace, Marvin | Lovelace |
| `sustainability_esg` | Sustainability / ESG | impact | Ohno, Landor | Ohno, Landor |
| `employment_growth` | Employment Growth | impact | Mayo, Marvin | Mayo |
| `supply_chain_integration` | Supply Chain Integration | impact | Ohno, Landor | Ohno, Landor |
| `local_development` | Local Development | impact | Mayo, Ohno | Mayo |
| `custom_objective` | Custom Objective | custom | (AI-determined) | (AI-determined) |

### 12.2 Lens Category Colors (UI)

```css
:root {
  --lens-featured: #F5C563;       /* Gold for The Crema */
  --lens-growth: #5DD4C3;         /* Bright Teal */
  --lens-transition: #8B7355;     /* Warm Brown */
  --lens-operations: #4A90A4;     /* Steel Blue */
  --lens-impact: #7CB342;         /* Leaf Green */
  --lens-custom: #B8904A;         /* Bronze Gold */
}
```

### 12.3 Key Implementation Checklist

```markdown
□ Database schema for lenses created
□ Lens endpoints implemented
□ LangGraph lens processing node added
□ Agent weight injection working
□ Tufte lens-based prioritization implemented
□ UI lens selection screen built
□ The Crema toggle bug fixed
□ Multi-lens conflict resolution tested
□ Custom lens interpretation working
□ Lens reasoning in reports implemented
```

---

## Document Metadata

```yaml
document_type: "Lens Framework Specification"
version: "1.0"
lenses_covered: 15
categories_covered: 6
companion_documents:
  - "RootRise_Core_Agent_Prompts.md"
  - "RootRise_AddOn_Agent_Prompts.md"
  - "RootRise_Utility_Agent_Prompts.md"
  - "RootRise_Sector_Knowledge_Framework.md"
  - "RootRise_Infrastructure_Blueprint.md"
last_updated: "2025-12-11"
status: "Production Ready"
```

---

*This document provides the complete specification for The &Eye lens framework. It should be read alongside the Infrastructure Blueprint to understand how lenses integrate into the broader RootRise architecture.*
