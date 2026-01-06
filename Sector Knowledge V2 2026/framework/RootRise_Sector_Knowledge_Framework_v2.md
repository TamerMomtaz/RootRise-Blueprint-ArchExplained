# RootRise Sector Knowledge Pack Framework

**Version:** 2.0  
**Last Updated:** January 5, 2026  
**Status:** Production-Ready Framework  
**Author:** Tee (the ionganinc)  
**For:** Ahmed El-Gazzar (Technical DevOps Lead) & Development Team

---

## Table of Contents

1. [Framework Overview](#1-framework-overview)
2. [The 11 Dimensions](#2-the-11-dimensions)
3. [Enhanced Features (v2.0)](#3-enhanced-features-v20)
4. [Complete Schema Specification](#4-complete-schema-specification)
5. [Agent Data Requirements Mapping](#5-agent-data-requirements-mapping)
6. [Country Coverage](#6-country-coverage)
7. [Sector Index](#7-sector-index)
8. [Implementation Guidelines](#8-implementation-guidelines)

---

## 1. Framework Overview

### 1.1 Purpose

The Sector Knowledge Pack is the **domain intelligence layer** that powers all diagnostic agents in The RootRise Pantheon. It provides sector-specific benchmarks, regulations, KPIs, and contextual data that enable accurate, relevant assessments for each SME.

### 1.2 What's New in v2.0

| Feature | v1.0 | v2.0 |
|---------|------|------|
| **Total Sectors** | 27 planned | 31 complete |
| **Country Coverage** | 5 countries | 6 countries (added Lebanon) |
| **Growth Pathways** | Not included | 5-stage pathway per sector |
| **Strategic Summary** | Not included | Critical success factors, failure patterns, red flags |
| **Key Financial Insights** | Basic benchmarks | Detailed financial considerations |
| **File Size (avg)** | ~40 KB | ~85 KB |

### 1.3 Design Principles

| Principle | Description |
|-----------|-------------|
| **Comprehensive** | Covers all 11 dimensions required by diagnostic agents |
| **Hierarchical** | Supports sector → subsector → category granularity |
| **MENA-First** | Built with MENA regional context as primary lens |
| **Agent-Aligned** | Data structures map directly to agent input requirements |
| **Growth-Oriented** | 5-stage growth pathways guide transformation |
| **Evidence-Based** | All benchmarks cite source and recency |

### 1.4 Sector Types

| Type | Count | Description |
|------|-------|-------------|
| **Industrial** | 14 | Manufacturing, production, processing |
| **Services** | 15 | Professional, consumer, B2B services |
| **Creative** | 1 | Design, media, arts |
| **Micro** | 1 | Home-based and micro enterprises |

---

## 2. The 11 Dimensions

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    SECTOR KNOWLEDGE PACK DIMENSIONS                          │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐              │
│  │  1. INDUSTRY    │  │  2. FINANCIAL   │  │  3. OPERATIONAL │              │
│  │  CLASSIFICATION │  │  BENCHMARKS     │  │  KPIs           │              │
│  │                 │  │                 │  │                 │              │
│  │  • ISIC codes   │  │  • Revenue norms│  │  • Efficiency   │              │
│  │  • Subsectors   │  │  • Margins      │  │  • Quality      │              │
│  │  • Value chain  │  │  • Ratios       │  │  • Productivity │              │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘              │
│                                                                              │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐              │
│  │  4. REGULATORY  │  │  5. COMPETITIVE │  │  6. DIGITAL     │              │
│  │  LANDSCAPE      │  │  DYNAMICS       │  │  MATURITY       │              │
│  │                 │  │                 │  │                 │              │
│  │  • Licenses     │  │  • Structure    │  │  • Tech adoption│              │
│  │  • Compliance   │  │  • Forces       │  │  • Benchmarks   │              │
│  │  • Certifications│ │  • Positioning  │  │  • Opportunities│              │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘              │
│                                                                              │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐              │
│  │  7. WORKFORCE   │  │  8. SUPPLY      │  │  9. EXPORT      │              │
│  │  NORMS          │  │  CHAIN          │  │  REQUIREMENTS   │              │
│  │                 │  │                 │  │                 │              │
│  │  • Roles        │  │  • Structure    │  │  • Certifications│             │
│  │  • Skills       │  │  • Suppliers    │  │  • Markets      │              │
│  │  • Compensation │  │  • Logistics    │  │  • Compliance   │              │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘              │
│                                                                              │
│  ┌─────────────────┐  ┌─────────────────┐                                   │
│  │ 10. PACKAGING   │  │ 11. MENA        │                                   │
│  │ & LABELING      │  │ REGIONAL        │                                   │
│  │                 │  │ CONTEXT         │                                   │
│  │  • Requirements │  │  • Country data │                                   │
│  │  • Standards    │  │  • Regulations  │                                   │
│  │  • Markets      │  │  • Opportunities│                                   │
│  └─────────────────┘  └─────────────────┘                                   │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.1 Dimension Summary

| # | Dimension | Primary Agent Users | Key Data Types |
|---|-----------|---------------------|----------------|
| 1 | Industry Classification | Drucker, All | ISIC codes, subsectors, value chain position |
| 2 | Financial Benchmarks | Graham | Margins, ratios, working capital, valuation |
| 3 | Operational KPIs | Marvin, Ohno | OEE, quality, productivity, delivery |
| 4 | Regulatory Landscape | Marvin, Ricardo | Licenses, certifications, compliance |
| 5 | Competitive Dynamics | Porter | Five Forces, strategies, risk matrix |
| 6 | Digital Maturity | Lovelace | Tech adoption, systems, automation |
| 7 | Workforce Norms | Mayo | Compensation, skills, turnover |
| 8 | Supply Chain | Ohno | Suppliers, inventory, logistics, lean |
| 9 | Export Requirements | Ricardo | Markets, certifications, documentation |
| 10 | Packaging & Labeling | Landor | Market-specific requirements, standards |
| 11 | MENA Regional Context | All | Country profiles, trade, opportunities |

---

## 3. Enhanced Features (v2.0)

### 3.1 Five-Stage Growth Pathways

Every v2.0 sector pack includes a 5-stage growth pathway that maps typical SME evolution:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         5-STAGE GROWTH PATHWAY                               │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  STAGE 1          STAGE 2          STAGE 3          STAGE 4          STAGE 5│
│  STARTUP          ESTABLISHED      PROFESSIONAL     REGIONAL         MAJOR  │
│  ────────         ───────────      ────────────     ────────         ───── │
│                                                                              │
│  Revenue:         Revenue:         Revenue:         Revenue:         Revenue│
│  <$500K           $500K-2M         $2M-10M          $10M-50M         >$50M  │
│                                                                              │
│  Employees:       Employees:       Employees:       Employees:       Employ │
│  1-10             10-30            30-100           100-250          >250   │
│                                                                              │
│  Focus:           Focus:           Focus:           Focus:           Focus: │
│  Survival         Stability        Scale            Expansion        Market │
│  Validation       Profitability    Systems          Multi-market     Leader │
│                                                                              │
│  Key Needs:       Key Needs:       Key Needs:       Key Needs:       Key N: │
│  - Product fit    - Cash flow      - Management     - Capital        - M&A  │
│  - First sales    - Hiring         - Processes      - New markets    - IPO  │
│  - Funding        - Operations     - ERP/Systems    - Acquisitions   - Glob │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

Each stage includes:
- **Characteristics:** What defines businesses at this stage
- **Typical Challenges:** Common pain points
- **Key Investments:** Where resources should go
- **Transition Triggers:** What enables moving to next stage
- **KPI Expectations:** Benchmarks for the stage

### 3.2 Strategic Summary

Every v2.0 sector pack concludes with a Strategic Summary containing:

```typescript
interface StrategicSummary {
  // What separates winners from losers
  critical_success_factors: {
    factor: string;
    importance: "critical" | "high" | "medium";
    description: string;
  }[];
  
  // Why businesses fail in this sector
  common_failure_patterns: {
    pattern: string;
    frequency: "very_common" | "common" | "occasional";
    prevention: string;
  }[];
  
  // Warning signs during diagnostic
  red_flags: {
    indicator: string;
    severity: "critical" | "warning" | "caution";
    implication: string;
  }[];
  
  // Positive indicators during diagnostic
  positive_indicators: {
    indicator: string;
    significance: string;
    amplification: string;
  }[];
  
  // Strategic recommendations
  transformation_priorities: {
    priority: string;
    impact: "high" | "medium" | "low";
    timeline: "quick_win" | "medium_term" | "long_term";
  }[];
}
```

### 3.3 Key Financial Insights

Enhanced financial section with sector-specific considerations:

```typescript
interface KeyFinancialInsights {
  // Sector-specific financial characteristics
  capital_intensity: "high" | "medium" | "low";
  working_capital_cycle_days: number;
  break_even_timeline_months: number;
  
  // Investment requirements by stage
  typical_investments: {
    stage: GrowthStage;
    capex_range_usd: [number, number];
    working_capital_range_usd: [number, number];
    key_investments: string[];
  }[];
  
  // Financing considerations
  common_funding_sources: string[];
  collateral_typically_accepted: string[];
  government_incentives: {
    country: string;
    program: string;
    benefit: string;
  }[];
  
  // Valuation guidance
  valuation_multiples: {
    metric: "revenue" | "ebitda" | "earnings";
    multiple_range: [number, number];
    factors_affecting: string[];
  }[];
}
```

---

## 4. Complete Schema Specification

### 4.1 Master Schema (v2.0)

```typescript
/**
 * RootRise Sector Knowledge Pack Schema
 * Version: 2.0
 */

interface SectorKnowledgePack {
  // Metadata (enhanced)
  metadata: {
    sector_id: string;
    sector_name: string;
    sector_name_ar: string;
    version: string;                      // Now follows semver
    last_updated: string;
    sector_type: "industrial" | "services" | "creative" | "micro";
    data_sources: DataSource[];
    applicable_countries: string[];       // 6 countries
    sme_size_range: SMESizeRange;
  };

  // The 11 Dimensions
  industry_classification: IndustryClassification;
  financial_benchmarks: FinancialBenchmarks;
  operational_kpis: OperationalKPIs;
  regulatory_landscape: RegulatoryLandscape;
  competitive_dynamics: CompetitiveDynamics;
  digital_maturity: DigitalMaturityProfile;
  workforce_norms: WorkforceNorms;
  supply_chain: SupplyChainProfile;
  export_requirements: ExportRequirements;
  packaging_labeling: PackagingLabelingStandards;
  mena_context: MENARegionalContext;

  // NEW in v2.0: Growth Pathways
  growth_pathways: {
    stages: GrowthStage[];
    transition_guides: TransitionGuide[];
  };

  // NEW in v2.0: Key Financial Insights
  key_financial_insights: KeyFinancialInsights;

  // NEW in v2.0: Strategic Summary
  strategic_summary: StrategicSummary;

  // Subsector Overrides
  subsectors: SubsectorOverride[];
}

interface DataSource {
  source_id: string;
  name: string;
  type: "government" | "industry_association" | "research" | "proprietary" | "international_org";
  url?: string;
  publication_date: string;
  reliability_score: number;  // 0-1
}

interface GrowthStage {
  stage_id: "startup" | "established" | "professional" | "regional" | "major";
  stage_number: 1 | 2 | 3 | 4 | 5;
  name: string;
  name_ar: string;
  revenue_range_usd: [number, number];
  employee_range: [number, number];
  characteristics: string[];
  typical_challenges: string[];
  key_investments: string[];
  kpi_expectations: Record<string, number>;
}

interface TransitionGuide {
  from_stage: string;
  to_stage: string;
  triggers: string[];
  required_capabilities: string[];
  typical_timeline_months: number;
  investment_required_usd: [number, number];
}
```

### 4.2 Dimension Schemas

#### Dimension 1: Industry Classification

```typescript
interface IndustryClassification {
  isic_rev4: {
    division: string;
    group: string;
    class: string;
    description: string;
  };
  
  nace_rev2?: {
    section: string;
    division: string;
  };
  
  rootrise_sector_type: "industrial" | "services" | "creative" | "micro";
  
  value_chain: {
    primary_position: "upstream" | "midstream" | "downstream";
    activities: ValueChainActivity[];
  };
  
  subsectors: SubsectorDefinition[];
  adjacent_sectors: AdjacentSector[];
}
```

#### Dimension 2: Financial Benchmarks

```typescript
interface FinancialBenchmarks {
  revenue_benchmarks: {
    percentile_25: number;
    percentile_50: number;
    percentile_75: number;
    currency: "USD";
    size_category: string;
  }[];
  
  margin_benchmarks: {
    gross_margin: { min: number; typical: number; best_in_class: number };
    operating_margin: { min: number; typical: number; best_in_class: number };
    net_margin: { min: number; typical: number; best_in_class: number };
  };
  
  ratio_benchmarks: {
    current_ratio: { healthy: number; warning: number; critical: number };
    quick_ratio: { healthy: number; warning: number; critical: number };
    debt_to_equity: { healthy: number; warning: number; critical: number };
    receivables_days: { good: number; typical: number; concerning: number };
    payables_days: { good: number; typical: number; concerning: number };
    inventory_days: { good: number; typical: number; concerning: number };
  };
  
  working_capital: {
    cash_conversion_cycle_days: number;
    seasonal_patterns: string[];
    peak_requirements_months: number[];
  };
  
  capex_benchmarks: {
    maintenance_percent_of_revenue: number;
    growth_capex_typical_usd: [number, number];
    depreciation_years: number;
  };
}
```

#### Dimension 3: Operational KPIs

```typescript
interface OperationalKPIs {
  efficiency_metrics: {
    oee_target: number;              // Overall Equipment Effectiveness
    capacity_utilization: number;
    labor_productivity: string;
  };
  
  quality_metrics: {
    defect_rate_target: number;
    first_pass_yield: number;
    customer_complaint_rate: number;
    return_rate: number;
  };
  
  delivery_metrics: {
    on_time_delivery_target: number;
    order_fulfillment_time_days: number;
    stockout_rate_target: number;
  };
  
  lean_indicators: {
    waste_types: string[];
    inventory_turns: number;
    changeover_time_target: string;
  };
}
```

#### Dimensions 4-11

*(Similar detailed schemas for each dimension - see full documentation)*

---

## 5. Agent Data Requirements Mapping

### 5.1 Agent-to-Dimension Matrix

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     AGENT → DIMENSION REQUIREMENTS                           │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│ AGENT          PRIMARY DIMENSIONS          SECONDARY DIMENSIONS              │
│ ─────────────────────────────────────────────────────────────────────────   │
│ Drucker        1 (Classification)          11 (MENA), All (overview)        │
│ Marvin         3 (Ops KPIs), 4 (Regulatory) 1, 7, 8                         │
│ Graham         2 (Financial)               1, 11 (for valuation)            │
│ Ricardo        9 (Export), 10 (Packaging)   4, 11                           │
│ Lovelace       6 (Digital)                 3, 7                             │
│ Mayo           7 (Workforce)               1, 11                            │
│ Ohno           8 (Supply Chain), 3 (Ops)   6, 7                             │
│ Porter         5 (Competitive)             1, 2, 11                         │
│ Landor         10 (Packaging)              9, 11                            │
│ Deming         All                         Validation across all            │
│ Tufte          All                         Report generation                │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 5.2 Data Requirements by Agent

| Agent | Required Data | Used For |
|-------|---------------|----------|
| **Drucker** | Sector classification, subsectors, value chain | Routing decisions, context setting |
| **Marvin** | Operational KPIs, regulatory requirements | Gap analysis, compliance check |
| **Graham** | Financial benchmarks, margins, ratios | Financial health assessment, valuation |
| **Ricardo** | Export requirements, certifications, markets | Export readiness assessment |
| **Lovelace** | Digital maturity benchmarks, tech adoption | Digital gap analysis |
| **Mayo** | Workforce norms, compensation, skills | HR assessment, organizational analysis |
| **Ohno** | Supply chain profile, lean indicators | Supply chain and efficiency analysis |
| **Porter** | Competitive dynamics, Five Forces | Market positioning, strategy |
| **Landor** | Packaging standards, labeling requirements | Packaging compliance, brand assessment |

---

## 6. Country Coverage

### 6.1 Supported Countries

| Code | Country | Coverage Level | Special Considerations |
|------|---------|----------------|------------------------|
| **EG** | Egypt | Comprehensive | Primary market, regulatory details, industrial zones |
| **SA** | Saudi Arabia | Comprehensive | Vision 2030 alignment, Saudization, SFDA standards |
| **AE** | UAE | Comprehensive | Free zone regulations, ESMA standards, re-export hub |
| **JO** | Jordan | Comprehensive | Regional hub positioning, trade agreements |
| **LB** | Lebanon | Comprehensive | Crisis context, recovery pathways, diaspora markets |
| **MA** | Morocco | Standard | Africa gateway, EU proximity, automotive hub |

### 6.2 Country-Specific Data Structure

```typescript
interface CountryProfile {
  country_code: string;  // ISO 3166-1 alpha-2
  country_name: string;
  country_name_ar: string;
  
  // Regulatory environment
  regulatory_authority: string;
  business_registration: string;
  typical_setup_timeline_days: number;
  key_licenses: License[];
  
  // Market characteristics
  market_size_usd: number;
  growth_rate_percent: number;
  competitive_intensity: "high" | "medium" | "low";
  
  // Sector-specific considerations
  sector_status: "mature" | "growing" | "emerging" | "nascent";
  government_support_level: "high" | "medium" | "low";
  available_incentives: Incentive[];
  
  // Operational factors
  labor_availability: "abundant" | "adequate" | "scarce";
  infrastructure_quality: "excellent" | "good" | "adequate" | "limited";
  logistics_hub_access: string[];
  
  // Risk factors
  currency_stability: "stable" | "moderate" | "volatile";
  political_risk: "low" | "medium" | "high";
  special_considerations: string[];
}
```

---

## 7. Sector Index

### 7.1 Complete Sector List (31 Sectors)

| # | Sector ID | Sector Name | Type | Size | Version |
|---|-----------|-------------|------|------|---------|
| 1 | `agriculture_agribusiness` | Agriculture & Agribusiness | Industrial | 79 KB | 2.0 |
| 2 | `automotive` | Automotive | Industrial | 78 KB | 2.0 |
| 3 | `beauty_wellness` | Beauty & Wellness | Services | 90 KB | 1.0 |
| 4 | `chemicals_plastics` | Chemicals, Plastics & Specialty | Industrial | 80 KB | 2.0 |
| 5 | `construction_building` | Construction & Building | Industrial | 86 KB | 2.0 |
| 6 | `creative_industries` | Creative Industries | Creative | 96 KB | 1.0 |
| 7 | `education_training` | Education & Training | Services | 78 KB | 2.0 |
| 8 | `electronics_manufacturing` | Electronics Manufacturing | Industrial | 92 KB | 1.0 |
| 9 | `energy_utilities` | Energy & Utilities | Industrial | 91 KB | 1.0 |
| 10 | `environmental_services` | Environmental Services | Services | 84 KB | 1.0 |
| 11 | `filling_bottling` | Filling & Bottling | Industrial | 85 KB | 2.0 |
| 12 | `financial_services` | Financial Services | Services | 76 KB | 2.0 |
| 13 | `food_beverage_manufacturing` | Food & Beverage Manufacturing | Industrial | 97 KB | 1.0 |
| 14 | `furniture_manufacturing` | Furniture Manufacturing | Industrial | 83 KB | 2.0 |
| 15 | `healthcare_services` | Healthcare Services | Services | 83 KB | 2.0 |
| 16 | `home_based_micro` | Home-Based & Micro Enterprise | Micro | 100 KB | 1.0 |
| 17 | `hospitality_tourism` | Hospitality & Tourism | Services | 86 KB | 2.0 |
| 18 | `logistics_transportation` | Logistics & Transportation | Services | 80 KB | 2.0 |
| 19 | `maintenance_repair` | Maintenance & Repair Services | Services | 87 KB | 1.0 |
| 20 | `metal_fabrication` | Metal Fabrication & Manufacturing | Industrial | 65 KB | 2.0 |
| 21 | `paper_printing` | Paper & Printing | Industrial | 81 KB | 1.0 |
| 22 | `pharmaceuticals` | Pharmaceuticals Manufacturing | Industrial | 78 KB | 2.0 |
| 23 | `plastics_manufacturing` | Plastics Manufacturing | Industrial | 80 KB | 1.0 |
| 24 | `professional_services` | Professional Services | Services | 80 KB | 2.0 |
| 25 | `real_estate` | Real Estate | Services | 76 KB | 2.0 |
| 26 | `retail_commerce` | Retail & Commerce | Services | 81 KB | 2.0 |
| 27 | `security_services` | Security Services | Services | 86 KB | 1.0 |
| 28 | `technology_it` | Technology & IT Services | Services | 81 KB | 2.0 |
| 29 | `telecommunications` | Telecommunications | Services | 91 KB | 1.0 |
| 30 | `textiles_apparel` | Textiles & Apparel | Industrial | 84 KB | 2.0 |
| 31 | `trading_distribution` | Trading & Distribution | Services | 100 KB | 1.0 |

### 7.2 Sectors by Type

**Industrial (14 sectors):**
Agriculture, Automotive, Chemicals/Plastics, Construction, Electronics Manufacturing, Energy/Utilities, Filling/Bottling, Food/Beverage Manufacturing, Furniture, Metal Fabrication, Paper/Printing, Pharmaceuticals, Plastics Manufacturing, Textiles/Apparel

**Services (15 sectors):**
Beauty/Wellness, Education/Training, Environmental Services, Financial Services, Healthcare, Hospitality/Tourism, Logistics/Transportation, Maintenance/Repair, Professional Services, Real Estate, Retail/Commerce, Security Services, Technology/IT, Telecommunications, Trading/Distribution

**Creative (1 sector):**
Creative Industries

**Micro (1 sector):**
Home-Based & Micro Enterprise

---

## 8. Implementation Guidelines

### 8.1 Vector Database Chunking

For Qdrant/vector storage, each sector pack should be chunked as follows:

```typescript
interface SectorChunk {
  chunk_id: string;
  sector_id: string;
  dimension: number;                    // 1-11
  heading_path: string[];               // ["Financial Benchmarks", "Margin Benchmarks"]
  content: string;
  content_type: "narrative" | "table" | "schema" | "list";
  
  metadata: {
    country_specific?: string;          // If country-specific content
    subsector_specific?: string;        // If subsector-specific
    growth_stage?: string;              // If stage-specific
    confidence_score: number;
    source_id: string;
  };
}
```

**Chunking Strategy:**
- Chunk by dimension (11 chunks per sector minimum)
- Additional chunks for country-specific content
- Additional chunks for growth pathway stages
- Target chunk size: 500-1000 tokens

### 8.2 Estimated Storage

| Component | Calculation | Size |
|-----------|-------------|------|
| 31 sectors × ~85 KB | Raw markdown | ~2.6 MB |
| Chunks (avg 75 per sector) | 31 × 75 × 500 tokens | ~1.2M tokens |
| Vector embeddings | 2,325 chunks × 1536 dims × 4 bytes | ~14 MB |
| Total with metadata | | ~20 MB |

### 8.3 Update Frequency

| Data Type | Update Frequency | Trigger |
|-----------|-----------------|---------|
| Financial benchmarks | Quarterly | Market data releases |
| Regulatory landscape | As needed | Regulation changes |
| Country profiles | Semi-annually | Policy changes |
| Growth pathways | Annually | Market evolution |
| Competitive dynamics | Semi-annually | Market shifts |

---

## Document Metadata

```yaml
document_type: "Sector Knowledge Framework"
version: "2.0"
sectors_covered: 31
dimensions: 11
countries: 6
last_updated: "2026-01-05"
status: "Production Ready"
author: "Tee (CTO)"
for: "Ahmed El-Gazzar (Technical DevOps Lead)"

changes_from_v1:
  - Added 4 new sectors (31 total)
  - Added Lebanon country coverage (6 total)
  - Added 5-stage Growth Pathways
  - Added Strategic Summary section
  - Added Key Financial Insights
  - Enhanced country-specific data
  - Improved chunking guidelines
  - Added version tracking per sector

companion_documents:
  - "RootRise_Infrastructure_Blueprint_v1.1.md"
  - "RootRise_Sector_Index.md"
  - "RootRise_Sector_*_Complete.md" (31 files)
```

---

*31 sectors. 11 dimensions. 6 countries. One unified intelligence layer.*
