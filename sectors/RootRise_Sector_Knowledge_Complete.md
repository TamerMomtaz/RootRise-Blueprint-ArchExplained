# RootRise Sector Knowledge Pack Framework
## Version 1.0 | December 2025

---

# Table of Contents

1. [Framework Overview](#1-framework-overview)
2. [The 11 Dimensions](#2-the-11-dimensions)
3. [Complete Schema Specification](#3-complete-schema-specification)
4. [Agent Data Requirements Mapping](#4-agent-data-requirements-mapping)
5. [Implementation Guidelines](#5-implementation-guidelines)

---

# 1. Framework Overview

## 1.1 Purpose

The Sector Knowledge Pack is the **domain intelligence layer** that powers all diagnostic agents in The RootRise Pantheon. It provides sector-specific benchmarks, regulations, KPIs, and contextual data that enable accurate, relevant assessments for each SME.

## 1.2 Design Principles

| Principle | Description |
|-----------|-------------|
| **Comprehensive** | Covers all 11 dimensions required by diagnostic agents |
| **Hierarchical** | Supports sector → subsector → category granularity |
| **MENA-First** | Built with MENA regional context as primary lens |
| **Agent-Aligned** | Data structures map directly to agent input requirements |
| **Updateable** | Clear versioning and update pathways |
| **Evidence-Based** | All benchmarks cite source and recency |

## 1.3 MVP Sectors

| Priority | Sector | Rationale |
|----------|--------|-----------|
| **1** | Food & Beverage Manufacturing | UNIDO alignment, strong MENA presence, export potential |
| **2** | Light Manufacturing / Textiles | Job creation focus, export readiness, regional clusters |
| **3** | Tech / Digital Services | Growth trajectory, digital-native, investment attraction |

---

# 2. The 11 Dimensions

```
┌─────────────────────────────────────────────────────────────────────────┐
│                    SECTOR KNOWLEDGE PACK DIMENSIONS                      │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐          │
│  │  1. INDUSTRY    │  │  2. FINANCIAL   │  │  3. OPERATIONAL │          │
│  │  CLASSIFICATION │  │  BENCHMARKS     │  │  KPIs           │          │
│  │                 │  │                 │  │                 │          │
│  │  • ISIC codes   │  │  • Revenue norms│  │  • Efficiency   │          │
│  │  • Subsectors   │  │  • Margins      │  │  • Quality      │          │
│  │  • Value chain  │  │  • Ratios       │  │  • Productivity │          │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘          │
│                                                                          │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐          │
│  │  4. REGULATORY  │  │  5. COMPETITIVE │  │  6. DIGITAL     │          │
│  │  LANDSCAPE      │  │  DYNAMICS       │  │  MATURITY       │          │
│  │                 │  │                 │  │                 │          │
│  │  • Licenses     │  │  • Structure    │  │  • Tech adoption│          │
│  │  • Compliance   │  │  • Forces       │  │  • Benchmarks   │          │
│  │  • Certifications│ │  • Positioning  │  │  • Opportunities│          │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘          │
│                                                                          │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐          │
│  │  7. WORKFORCE   │  │  8. SUPPLY      │  │  9. EXPORT      │          │
│  │  NORMS          │  │  CHAIN          │  │  REQUIREMENTS   │          │
│  │                 │  │                 │  │                 │          │
│  │  • Roles        │  │  • Structure    │  │  • Certifications│         │
│  │  • Skills       │  │  • Suppliers    │  │  • Markets      │          │
│  │  • Compensation │  │  • Logistics    │  │  • Compliance   │          │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘          │
│                                                                          │
│  ┌─────────────────┐  ┌─────────────────┐                               │
│  │ 10. PACKAGING   │  │ 11. MENA        │                               │
│  │ & LABELING      │  │ REGIONAL        │                               │
│  │                 │  │ CONTEXT         │                               │
│  │  • Requirements │  │  • Country data │                               │
│  │  • Standards    │  │  • Regulations  │                               │
│  │  • Markets      │  │  • Opportunities│                               │
│  └─────────────────┘  └─────────────────┘                               │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

## 2.1 Dimension Summary

| # | Dimension | Primary Agent Users | Key Data Types |
|---|-----------|---------------------|----------------|
| 1 | Industry Classification | Drucker, All | ISIC codes, subsectors, value chain |
| 2 | Financial Benchmarks | Graham | Margins, ratios, working capital, valuation |
| 3 | Operational KPIs | Marvin, Ohno | OEE, quality, productivity, delivery |
| 4 | Regulatory Landscape | Marvin, Ricardo | Licenses, certifications, compliance |
| 5 | Competitive Dynamics | Porter | Five Forces, strategies, trends |
| 6 | Digital Maturity | Lovelace | Tech adoption, systems, automation |
| 7 | Workforce Norms | Mayo | Compensation, skills, turnover |
| 8 | Supply Chain | Ohno | Suppliers, inventory, logistics, lean |
| 9 | Export Requirements | Ricardo | Markets, certifications, documentation |
| 10 | Packaging & Labeling | Landor | Market-specific requirements, standards |
| 11 | MENA Regional Context | All | Country profiles, trade, opportunities |

---

# 3. Complete Schema Specification

## 3.1 Master Schema

```typescript
/**
 * RootRise Sector Knowledge Pack Schema
 * Version: 1.0
 * 
 * This schema defines the complete structure for sector intelligence
 * that powers all diagnostic agents in The Pantheon.
 */

interface SectorKnowledgePack {
  // Metadata
  metadata: {
    sector_id: string;                    // Unique identifier
    sector_name: string;                  // Display name
    sector_name_ar: string;               // Arabic display name
    version: string;                      // Pack version
    last_updated: string;                 // ISO 8601 date
    data_sources: DataSource[];           // Attribution
    applicable_countries: string[];       // ISO 3166-1 alpha-2 codes
    sme_size_range: {
      min_employees: number;
      max_employees: number;
      min_revenue_usd: number;
      max_revenue_usd: number;
    };
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

  // Subsector Overrides
  subsectors: SubsectorOverride[];
}

interface DataSource {
  source_id: string;
  name: string;
  type: "government" | "industry_association" | "research" | "proprietary";
  url?: string;
  publication_date: string;
  reliability_score: number;  // 0-1
}
```

## 3.2 Dimension 1: Industry Classification

```typescript
interface IndustryClassification {
  // Standard Classifications
  isic_rev4: {
    division: string;           // e.g., "10"
    group: string;              // e.g., "10.1"
    class: string;              // e.g., "10.11"
    description: string;
  };
  
  nace_rev2?: {
    section: string;
    division: string;
    description: string;
  };
  
  rootrise_sector_type: "industrial" | "services" | "hybrid";
  
  value_chain: {
    primary_position: "upstream" | "midstream" | "downstream";
    activities: ValueChainActivity[];
  };
  
  subsectors: SubsectorDefinition[];
  
  adjacent_sectors: {
    sector_id: string;
    relationship: "supplier" | "customer" | "complementary" | "substitute";
    relevance_score: number;
  }[];
}

interface SubsectorDefinition {
  subsector_id: string;
  name: string;
  name_ar: string;
  description: string;
  isic_classes: string[];
  typical_products: string[];
  distinguishing_characteristics: string[];
}
```

## 3.3 Dimension 2: Financial Benchmarks

```typescript
interface FinancialBenchmarks {
  revenue: {
    median_annual_usd: number;
    quartiles: { p25: number; p50: number; p75: number };
    growth_rate: {
      sector_average: number;
      top_quartile: number;
      bottom_quartile: number;
    };
    seasonality: SeasonalityPattern;
  };
  
  profitability: {
    gross_margin: {
      sector_median: number;
      healthy_range: { min: number; max: number };
      by_subsector: { subsector_id: string; median: number }[];
    };
    operating_margin: { sector_median: number; healthy_range: { min: number; max: number } };
    net_margin: { sector_median: number; healthy_range: { min: number; max: number } };
    ebitda_margin: { sector_median: number; top_quartile: number };
  };
  
  cost_structure: {
    cogs_percentage: number;
    labor_percentage: number;
    overhead_percentage: number;
    marketing_percentage: number;
    typical_breakdown: CostCategory[];
  };
  
  working_capital: {
    days_sales_outstanding: { median: number; healthy_max: number };
    days_inventory_outstanding: { median: number; healthy_max: number };
    days_payables_outstanding: { median: number; healthy_min: number };
    cash_conversion_cycle: { median: number; target: number };
  };
  
  health_indicators: {
    current_ratio: { healthy_min: number; optimal: number };
    quick_ratio: { healthy_min: number; optimal: number };
    debt_to_equity: { healthy_max: number; sector_median: number };
    interest_coverage: { healthy_min: number };
  };
  
  valuation: {
    revenue_multiple: { low: number; median: number; high: number };
    ebitda_multiple: { low: number; median: number; high: number };
    factors_affecting_premium: string[];
  };
}
```

## 3.4 Dimension 3: Operational KPIs

```typescript
interface OperationalKPIs {
  production: {
    oee: {
      sector_median: number;
      world_class: number;
      components: { availability: number; performance: number; quality: number };
    };
    capacity_utilization: { sector_median: number; optimal_range: { min: number; max: number } };
    throughput_metrics: ThroughputMetric[];
  };
  
  quality: {
    defect_rate: { sector_median: number; world_class: number; unit: string };
    first_pass_yield: { sector_median: number; target: number };
    customer_complaint_rate: { sector_median: number; acceptable_max: number; unit: string };
    return_rate: { sector_median: number; acceptable_max: number };
  };
  
  productivity: {
    revenue_per_employee: { sector_median: number; top_quartile: number };
    units_per_labor_hour: { metric_name: string; sector_median: number };
    value_added_per_employee: { sector_median: number; calculation_method: string };
  };
  
  delivery: {
    on_time_delivery: { sector_median: number; world_class: number };
    order_fulfillment_cycle: { sector_median_days: number; target_days: number };
    perfect_order_rate: { sector_median: number; world_class: number };
  };
  
  safety: {
    incident_rate: { sector_median: number; target: number; calculation_basis: string };
    lost_time_injuries: { sector_median: number; target: number };
  };
  
  environmental: {
    energy_intensity: { metric: string; sector_median: number; unit: string };
    water_usage: { metric: string; sector_median: number; unit: string };
    waste_to_landfill: { sector_median: number; target: number };
  };
}
```

## 3.5 Dimension 4: Regulatory Landscape

```typescript
interface RegulatoryLandscape {
  licensing: {
    required_licenses: License[];
    typical_timeline_months: number;
    estimated_total_cost_usd: { min: number; max: number };
  };
  
  certifications: {
    mandatory: Certification[];
    recommended: Certification[];
    export_enabling: Certification[];
  };
  
  compliance_areas: ComplianceArea[];
  regulatory_bodies: RegulatoryBody[];
  
  regulatory_changes: {
    recent: RegulatoryChange[];
    upcoming: RegulatoryChange[];
  };
  
  enforcement: {
    common_violations: string[];
    typical_penalties: { violation_type: string; penalty_range: string }[];
    enforcement_intensity: "low" | "moderate" | "high";
  };
}

interface License {
  license_id: string;
  name: string;
  name_ar?: string;
  issuing_authority: string;
  applicable_countries: string[];
  validity_period_years: number;
  estimated_cost_usd: { initial: number; renewal: number };
  processing_time_weeks: { min: number; max: number };
  prerequisites: string[];
}

interface Certification {
  certification_id: string;
  name: string;
  type: "quality" | "safety" | "environmental" | "halal" | "organic" | "trade";
  issuing_bodies: string[];
  validity_period_years: number;
  estimated_cost_usd: { min: number; max: number };
  implementation_time_months: { min: number; max: number };
  benefits: string[];
  export_markets_enabled: string[];
}
```

## 3.6 Dimension 5: Competitive Dynamics

```typescript
interface CompetitiveDynamics {
  market_structure: {
    structure_type: "fragmented" | "concentrated" | "oligopolistic" | "monopolistic";
    concentration_ratio: { cr4: number; hhi: number };
    number_of_competitors: { large: number; medium: number; small: number };
    market_leaders: { name: string; estimated_market_share: number; competitive_advantage: string }[];
  };
  
  five_forces: {
    rivalry: { intensity: string; score: number; drivers: string[]; implications_for_sme: string };
    threat_of_new_entrants: { level: string; score: number; barriers: BarrierToEntry[]; implications_for_sme: string };
    threat_of_substitutes: { level: string; score: number; key_substitutes: string[]; switching_costs: string };
    supplier_power: { level: string; score: number; drivers: string[]; implications_for_sme: string };
    buyer_power: { level: string; score: number; drivers: string[]; implications_for_sme: string };
    overall_attractiveness: { score: number; interpretation: string };
  };
  
  competitive_strategies: {
    dominant_strategies: string[];
    successful_sme_strategies: { strategy: string; description: string; success_factors: string[] }[];
    strategic_groups: StrategicGroup[];
  };
  
  key_success_factors: {
    factor: string;
    importance: "critical" | "high" | "medium";
    typical_sme_performance: "weak" | "average" | "strong";
    improvement_opportunity: string;
  }[];
  
  trends: {
    trend: string;
    impact: "positive" | "negative" | "neutral";
    timeline: string;
    sme_opportunity: string;
  }[];
}
```

## 3.7 Dimension 6: Digital Maturity

```typescript
interface DigitalMaturityProfile {
  sector_digital_maturity: {
    average_score: number;
    distribution: {
      level_1_manual: number;
      level_2_basic_digital: number;
      level_3_connected: number;
      level_4_advanced: number;
      level_5_transformative: number;
    };
    comparison_to_global: "behind" | "at_par" | "ahead";
  };
  
  core_systems: {
    system_type: string;
    adoption_rate: number;
    typical_solutions: string[];
    implementation_cost_usd: { min: number; max: number };
    implementation_time_months: { min: number; max: number };
    roi_timeline_months: number;
    critical_for: string[];
  }[];
  
  functional_capabilities: {
    function: string;
    current_digitization: number;
    gap_to_best_practice: number;
    priority_technologies: string[];
    quick_wins: string[];
  }[];
  
  ecommerce: {
    b2b_adoption: number;
    b2c_adoption: number;
    d2c_potential: "low" | "medium" | "high";
    preferred_platforms: string[];
    average_digital_revenue_share: number;
  };
  
  automation: {
    high_potential_processes: {
      process: string;
      current_automation: number;
      potential_automation: number;
      roi_potential: string;
      implementation_complexity: string;
    }[];
  };
  
  transformation_priorities: {
    phase: "foundation" | "optimization" | "transformation";
    timeline: string;
    initiatives: string[];
    investment_range_usd: { min: number; max: number };
  }[];
}
```

## 3.8 Dimension 7: Workforce Norms

```typescript
interface WorkforceNorms {
  composition: {
    typical_headcount_by_revenue: {
      revenue_tier_usd: string;
      median_employees: number;
      range: { min: number; max: number };
    }[];
    role_distribution: {
      category: "production" | "administrative" | "sales" | "technical" | "management";
      percentage: number;
      typical_roles: string[];
    }[];
    skill_level_distribution: { unskilled: number; semi_skilled: number; skilled: number; professional: number };
  };
  
  compensation: {
    by_role: {
      role_category: string;
      role_title: string;
      monthly_salary_usd: { entry: number; mid: number; senior: number };
      regional_variance: { country: string; multiplier: number }[];
    }[];
    benefits_typical: string[];
    bonus_practices: string;
  };
  
  skills: {
    critical_skills: {
      skill: string;
      importance: "critical" | "high" | "medium";
      availability: "scarce" | "limited" | "adequate" | "abundant";
      training_pathway: string;
    }[];
    skill_gaps: {
      skill: string;
      gap_severity: "critical" | "significant" | "moderate";
      impact: string;
      remediation_options: string[];
    }[];
  };
  
  labor_dynamics: {
    turnover_rate: { sector_average: number; acceptable_range: { min: number; max: number } };
    absenteeism_rate: { sector_average: number; acceptable_max: number };
    recruitment_difficulty: { overall: string; by_role: { role: string; difficulty: string }[] };
    training_investment: { sector_average_per_employee_usd: number; recommended_minimum: number };
  };
  
  hr_maturity: {
    average_score: number;
    common_gaps: string[];
    priority_improvements: string[];
  };
}
```

## 3.9 Dimension 8: Supply Chain

```typescript
interface SupplyChainProfile {
  structure: {
    typical_tiers: number;
    upstream_complexity: "simple" | "moderate" | "complex";
    downstream_channels: string[];
    integration_level: "fragmented" | "partially_integrated" | "integrated";
  };
  
  suppliers: {
    key_input_categories: {
      category: string;
      percentage_of_cogs: number;
      supplier_concentration: "fragmented" | "moderate" | "concentrated";
      local_availability: number;
      import_dependency: number;
      price_volatility: "low" | "medium" | "high";
      lead_time_weeks: { min: number; typical: number; max: number };
    }[];
    common_supplier_issues: string[];
  };
  
  inventory: {
    raw_materials: { typical_weeks_of_stock: number; recommended_range: { min: number; max: number } };
    work_in_progress: { typical_days: number; benchmark: number };
    finished_goods: { typical_weeks_of_stock: number; recommended_range: { min: number; max: number } };
    inventory_turnover: { sector_median: number; top_quartile: number };
    common_issues: string[];
  };
  
  logistics: {
    inbound: { typical_modes: string[]; cost_as_percentage_of_cogs: number };
    outbound: { typical_modes: string[]; cost_as_percentage_of_revenue: number };
    warehousing: { typical_requirement_sqm_per_revenue: number; temperature_controlled: boolean };
    regional_challenges: string[];
  };
  
  risks: {
    risk_type: string;
    likelihood: "low" | "medium" | "high";
    impact: "low" | "medium" | "high";
    mitigation_strategies: string[];
  }[];
  
  lean_opportunities: {
    waste_type: string;
    prevalence: "low" | "medium" | "high";
    typical_impact_percentage: number;
    improvement_approach: string;
  }[];
}
```

## 3.10 Dimension 9: Export Requirements

```typescript
interface ExportRequirements {
  sector_export_profile: {
    export_intensity: number;
    growth_trend: "declining" | "stable" | "growing" | "rapidly_growing";
    primary_export_markets: { region: string; countries: string[]; share_of_exports: number }[];
    export_barriers: string[];
  };
  
  target_markets: {
    market_id: string;
    country_or_region: string;
    priority: "primary" | "secondary" | "emerging";
    market_size_usd: number;
    growth_rate: number;
    entry_complexity: "low" | "medium" | "high";
    required_certifications: string[];
    typical_entry_timeline_months: number;
    entry_strategy_options: string[];
  }[];
  
  certifications: {
    certification_id: string;
    name: string;
    markets_enabled: string[];
    mandatory: boolean;
    cost_usd: { min: number; max: number };
    timeline_months: { min: number; max: number };
    prerequisites: string[];
    issuing_bodies: string[];
  }[];
  
  trade_agreements: {
    agreement_name: string;
    applicable_countries: string[];
    benefits: string[];
    rules_of_origin: string;
    utilization_rate: number;
  }[];
  
  documentation: {
    document_type: string;
    description: string;
    required_for: string[];
    issuing_authority: string;
    common_errors: string[];
  }[];
  
  financing: {
    instrument: string;
    description: string;
    providers: string[];
    typical_terms: string;
  }[];
}
```

## 3.11 Dimension 10: Packaging & Labeling

```typescript
interface PackagingLabelingStandards {
  general: {
    primary_packaging_types: string[];
    secondary_packaging_types: string[];
    typical_packaging_cost_percentage: number;
    sustainability_requirements: string[];
  };
  
  labeling_by_market: {
    market: string;
    regulatory_body: string;
    mandatory_elements: LabelElement[];
    language_requirements: string[];
    date_format: string;
    measurement_system: string;
    special_requirements: string[];
    common_compliance_failures: string[];
    penalty_for_non_compliance: string;
  }[];
  
  certification_display: {
    certification: string;
    logo_requirements: string;
    placement_rules: string;
  }[];
  
  halal_labeling: {
    recognized_bodies: { body_name: string; country: string; recognition_scope: string[] }[];
    logo_specifications: string;
    common_issues: string[];
  };
  
  nutritional_labeling: {
    mandatory_markets: string[];
    format_requirements: { market: string; format: string; mandatory_nutrients: string[] }[];
  };
  
  upgrade_pathways: {
    from_level: string;
    to_level: string;
    changes_required: string[];
    estimated_cost_usd: { min: number; max: number };
    markets_unlocked: string[];
  }[];
}

interface LabelElement {
  element: string;
  mandatory: boolean;
  format: string;
  placement: string;
  font_size_minimum: string;
  examples: string[];
}
```

## 3.12 Dimension 11: MENA Regional Context

```typescript
interface MENARegionalContext {
  countries: {
    country_code: string;
    country_name: string;
    country_name_ar: string;
    
    market_overview: {
      gdp_usd: number;
      population: number;
      sector_contribution_to_gdp: number;
      growth_outlook: string;
    };
    
    regulatory: {
      primary_regulator: string;
      licensing_complexity: "low" | "medium" | "high";
      key_regulations: string[];
    };
    
    business_environment: {
      ease_of_doing_business_rank: number;
      starting_business_days: number;
      foreign_ownership_rules: string;
    };
    
    labor: {
      minimum_wage_usd_monthly: number;
      work_week_hours: number;
      nationalization_requirements: string;
      labor_law_key_points: string[];
    };
    
    financial: {
      sme_lending_availability: "limited" | "moderate" | "good";
      interest_rate_typical: number;
      government_support_programs: { program_name: string; type: string; benefit: string }[];
    };
    
    infrastructure: {
      logistics_score: number;
      electricity_reliability: number;
      internet_penetration: number;
      key_ports: string[];
      free_zones: string[];
    };
    
    cultural: {
      business_language: string[];
      decision_making_style: string;
      relationship_importance: "low" | "medium" | "high";
      ramadan_impact: string;
    };
  }[];
  
  regional_trade: {
    intra_region_trade_value: number;
    key_trade_corridors: { from: string; to: string; primary_products: string[] }[];
    trade_agreements: { agreement_name: string; members: string[]; key_benefits: string[] }[];
  };
  
  regional_opportunities: {
    opportunity: string;
    countries_involved: string[];
    relevance_to_sector: "low" | "medium" | "high";
    action_for_smes: string;
  }[];
  
  government_initiatives: {
    initiative_name: string;
    country: string;
    description: string;
    sector_relevance: "low" | "medium" | "high";
    benefits_for_smes: string[];
  }[];
}
```

---

# 4. Agent Data Requirements Mapping

## 4.1 Data Flow to Agents

| Agent | Primary Dimensions | Secondary Dimensions | Key Data Points |
|-------|-------------------|---------------------|-----------------|
| **The Drucker** | 1, 11 | All | Sector overview, country context, workflow routing |
| **The Marvin** | 1, 3, 4 | 7, 8 | KPIs, compliance areas, process benchmarks |
| **The Graham** | 2 | 1, 11 | Financial benchmarks, ratios, valuation |
| **The Ricardo** | 9, 10 | 4, 11 | Export markets, certifications, trade agreements |
| **The Lovelace** | 6 | 3, 7 | Digital benchmarks, systems, automation |
| **The Mayo** | 7 | 1, 11 | Workforce norms, compensation, labor laws |
| **The Ohno** | 8, 3 | 6, 7 | Supply chain, lean opportunities, KPIs |
| **The Porter** | 5 | 1, 2, 11 | Five Forces, strategies, trends |
| **The Landor** | 10 | 9, 11 | Labeling requirements, packaging standards |
| **The Tufte** | All | - | Report templates, visualization data |
| **The Deming** | All | - | Validation rules, benchmark ranges |

## 4.2 Subsector Override Logic

When an SME's subsector is identified, the system:

1. Loads the parent sector knowledge pack
2. Applies subsector overrides for dimensions where data differs
3. Falls back to sector-level data where subsector data is unavailable

```typescript
function getSectorIntelligence(sectorId: string, subsectorId?: string): SectorKnowledgePack {
  const basePack = loadSectorPack(sectorId);
  
  if (subsectorId) {
    const override = basePack.subsectors.find(s => s.subsector_id === subsectorId);
    if (override) {
      return mergeWithOverrides(basePack, override);
    }
  }
  
  return basePack;
}
```

---

# 5. Implementation Guidelines

## 5.1 Data Quality Standards

| Standard | Requirement |
|----------|-------------|
| **Recency** | Financial benchmarks updated annually minimum |
| **Source Attribution** | Every benchmark must cite source |
| **Confidence Scoring** | Data with <70% confidence flagged |
| **Regional Granularity** | Country-level data where available |
| **Subsector Coverage** | At least 3 subsectors per sector |

## 5.2 Update Cadence

| Data Type | Update Frequency | Trigger Events |
|-----------|------------------|----------------|
| Financial Benchmarks | Annual | New industry reports |
| Regulatory | Quarterly | Regulatory changes |
| Competitive Dynamics | Semi-annual | Market shifts |
| MENA Context | Quarterly | Policy changes |
| Digital Maturity | Annual | Technology trends |

## 5.3 Version Control

```
sector_pack_version: "1.0.0"
  - Major: Schema changes (breaking)
  - Minor: New data additions (compatible)
  - Patch: Data corrections (compatible)
```

## 5.4 Data Validation Rules

```typescript
interface ValidationRule {
  field: string;
  rule: "required" | "range" | "format" | "consistency";
  parameters?: any;
  error_message: string;
}

const financialValidations: ValidationRule[] = [
  {
    field: "gross_margin.sector_median",
    rule: "range",
    parameters: { min: 0, max: 100 },
    error_message: "Gross margin must be between 0-100%"
  },
  {
    field: "working_capital.cash_conversion_cycle.median",
    rule: "consistency",
    parameters: { formula: "DSO + DIO - DPO ± 5" },
    error_message: "Cash conversion cycle must equal DSO + DIO - DPO"
  }
];
```

---

# Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | December 2025 | RootRise Product Team | Initial framework release |

---

*This document defines the schema and framework for RootRise Sector Knowledge Packs. For the complete Food & Beverage Manufacturing sector data, see `RootRise_Sector_FoodBev.md`.*
# RootRise Sector Knowledge Pack
# Food & Beverage Manufacturing
## Version 1.0 | December 2025

---

# Sector Metadata

```json
{
  "metadata": {
    "sector_id": "food_bev_manufacturing",
    "sector_name": "Food & Beverage Manufacturing",
    "sector_name_ar": "تصنيع الأغذية والمشروبات",
    "version": "1.0.0",
    "last_updated": "2025-12-11",
    "data_sources": [
      {
        "source_id": "unido_2024",
        "name": "UNIDO Industrial Statistics",
        "type": "research",
        "publication_date": "2024-06",
        "reliability_score": 0.95
      },
      {
        "source_id": "fao_2024",
        "name": "FAO Food Outlook",
        "type": "research",
        "publication_date": "2024-11",
        "reliability_score": 0.95
      },
      {
        "source_id": "gulfood_2024",
        "name": "Gulfood Industry Report",
        "type": "industry_association",
        "publication_date": "2024-02",
        "reliability_score": 0.85
      },
      {
        "source_id": "euromonitor_2024",
        "name": "Euromonitor Packaged Food MENA",
        "type": "research",
        "publication_date": "2024-09",
        "reliability_score": 0.90
      },
      {
        "source_id": "rootrise_proprietary",
        "name": "RootRise SME Assessment Data",
        "type": "proprietary",
        "publication_date": "2025-01",
        "reliability_score": 0.90
      }
    ],
    "applicable_countries": ["EG", "SA", "AE", "JO", "MA", "TN", "LB"],
    "sme_size_range": {
      "min_employees": 10,
      "max_employees": 250,
      "min_revenue_usd": 100000,
      "max_revenue_usd": 50000000
    }
  }
}
```

---

# Dimension 1: Industry Classification

## 1.1 Standard Classifications

| Classification | Code | Description |
|----------------|------|-------------|
| **ISIC Rev.4 Division** | 10-11 | Manufacture of food products; Manufacture of beverages |
| **ISIC Groups** | 10.1-10.8, 11.0 | Processing/preserving of meat, fish, fruits, oils, dairy, grain, bakery, other food, beverages |
| **NACE Rev.2** | C10-C11 | Same as ISIC |
| **RootRise Type** | Industrial | Manufacturing-based operations |

## 1.2 Value Chain Position

**Primary Position:** Midstream

```
┌─────────────────────────────────────────────────────────────────────┐
│                    FOOD & BEVERAGE VALUE CHAIN                       │
├─────────────────────────────────────────────────────────────────────┤
│                                                                      │
│  UPSTREAM              MIDSTREAM                    DOWNSTREAM       │
│  (Agriculture)         (Manufacturing)              (Distribution)   │
│                                                                      │
│  ┌─────────┐          ┌─────────────────────┐      ┌─────────┐      │
│  │ Farmers │          │ ┌─────────────────┐ │      │ Retail  │      │
│  │ Growers │ ───────► │ │ Primary        │ │ ───► │ Whole-  │      │
│  │ Ranchers│          │ │ Processing     │ │      │ sale    │      │
│  └─────────┘          │ │ (Cleaning,     │ │      │ Food-   │      │
│                       │ │  Sorting)      │ │      │ service │      │
│  ┌─────────┐          │ └───────┬────────┘ │      └─────────┘      │
│  │ Input   │          │         │          │                       │
│  │ Suppliers│ ───────►│ ┌───────▼────────┐ │      ┌─────────┐      │
│  │ (Seeds, │          │ │ Secondary      │ │      │ End     │      │
│  │  Feed)  │          │ │ Manufacturing  │ │ ───► │ Consumer│      │
│  └─────────┘          │ │ (Value-Added)  │ │      │         │      │
│                       │ └───────┬────────┘ │      └─────────┘      │
│  ┌─────────┐          │         │          │                       │
│  │ Packaging│         │ ┌───────▼────────┐ │                       │
│  │ Suppliers│ ───────►│ │ Packaging &    │ │                       │
│  │          │         │ │ Labeling       │ │                       │
│  └─────────┘          │ └────────────────┘ │                       │
│                       └─────────────────────┘                       │
│                                                                      │
│  SME FOCUS AREA: Processing & Manufacturing ◄────────────────────   │
└─────────────────────────────────────────────────────────────────────┘
```

### Value Chain Activities

| Activity | Margin Contribution | Capital Intensity | SME Participation |
|----------|---------------------|-------------------|-------------------|
| Raw Material Sourcing | 0% | Low | High |
| Primary Processing | 15% | Medium | High |
| Secondary Manufacturing | 45% | High | High |
| Packaging & Labeling | 20% | Medium | High |
| Distribution & Sales | 20% | Medium | Medium |

## 1.3 Subsector Taxonomy

### Subsector 1: Dairy Products (dairy)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Dairy Products |
| **Name (AR)** | منتجات الألبان |
| **ISIC Classes** | 10.51, 10.52 |
| **Typical Products** | Fresh milk, Yogurt, Cheese, Butter, Ice cream, Labneh, Dairy desserts |
| **Distinguishing Characteristics** | Cold chain critical, Short shelf life, High QC requirements, Seasonal demand |

### Subsector 2: Bakery & Confectionery (bakery_confectionery)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Bakery & Confectionery |
| **Name (AR)** | المخبوزات والحلويات |
| **ISIC Classes** | 10.71, 10.72, 10.73 |
| **Typical Products** | Bread, Pastries, Biscuits, Cakes, Chocolates, Candies, Traditional sweets (Baklava, Kunafa, Maamoul) |
| **Distinguishing Characteristics** | Mix of fresh/shelf-stable, High labor for artisanal, Strong local brands, Ramadan/Eid peaks |

### Subsector 3: Processed & Preserved Foods (processed_foods)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Processed & Preserved Foods |
| **Name (AR)** | الأغذية المصنعة والمحفوظة |
| **ISIC Classes** | 10.31, 10.32, 10.39, 10.85 |
| **Typical Products** | Canned vegetables, Frozen foods, Sauces, Jams, Ready meals, Pickles, Tahini |
| **Distinguishing Characteristics** | Longer shelf life, Export potential, Seasonal raw materials, Higher automation |

### Subsector 4: Beverages (beverages)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Beverages |
| **Name (AR)** | المشروبات |
| **ISIC Classes** | 11.01, 11.02, 11.04, 11.07 |
| **Typical Products** | Fruit juices, Soft drinks, Bottled water, Energy drinks, Traditional beverages (Hibiscus, Tamarind) |
| **Distinguishing Characteristics** | High volume production, Capital intensive, Strong branding, Distribution intensive |

### Subsector 5: Oils & Fats (oils_fats)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Oils & Fats |
| **Name (AR)** | الزيوت والدهون |
| **ISIC Classes** | 10.41, 10.42 |
| **Typical Products** | Cooking oils, Olive oil, Margarine, Ghee, Specialty oils (Sesame, Sunflower) |
| **Distinguishing Characteristics** | Commodity pricing, Import dependency, Quality differentiation, Long shelf life |

### Subsector 6: Spices, Condiments & Sauces (spices_condiments)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Spices, Condiments & Sauces |
| **Name (AR)** | التوابل والبهارات والصلصات |
| **ISIC Classes** | 10.84 |
| **Typical Products** | Ground spices, Spice blends, Hot sauces, Dressings, Vinegar, Mustard, Dukkah |
| **Distinguishing Characteristics** | High margin potential, Export friendly, Regional preferences, Lower capital |

### Subsector 7: Snack Foods (snacks)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Snack Foods |
| **Name (AR)** | الوجبات الخفيفة |
| **ISIC Classes** | 10.73, 10.39 |
| **Typical Products** | Potato chips, Corn snacks, Nuts, Crackers, Popcorn, Traditional snacks |
| **Distinguishing Characteristics** | High growth category, Innovation driven, Strong branding, Wide distribution |

## 1.4 Adjacent Sectors

| Sector | Relationship | Relevance Score | Interaction |
|--------|--------------|-----------------|-------------|
| Agriculture | Supplier | 0.95 | Raw material sourcing |
| Packaging Manufacturing | Supplier | 0.85 | Packaging procurement |
| Retail Trade | Customer | 0.90 | Distribution channel |
| Hospitality | Customer | 0.75 | B2B sales |
| Logistics & Warehousing | Complementary | 0.80 | Distribution support |
| Equipment Manufacturing | Supplier | 0.70 | Machinery procurement |

---

# Dimension 2: Financial Benchmarks

## 2.1 Revenue Benchmarks

### Revenue Distribution (MENA SMEs)

| Metric | Value (USD) |
|--------|-------------|
| **Median Annual Revenue** | $2,500,000 |
| **25th Percentile** | $750,000 |
| **50th Percentile** | $2,500,000 |
| **75th Percentile** | $8,000,000 |

### Revenue Growth Rates

| Performance Level | Annual Growth |
|-------------------|---------------|
| Sector Average | 8.5% |
| Top Quartile | 15.0% |
| Bottom Quartile | 2.0% |

### Seasonality Pattern

| Attribute | Value |
|-----------|-------|
| **Pattern Type** | Moderate |
| **Peak Months** | January, March-April (Ramadan), September, December |
| **Low Months** | June, July, August |
| **Revenue Variance** | ±25% from mean |
| **Notes** | Peaks around Ramadan, Eid holidays, year-end. Summer slowdown in non-beverage categories. Beverages counter-cyclical in summer. |

## 2.2 Profitability Benchmarks

### Margin Benchmarks

| Margin Type | Sector Median | Healthy Range | Top Quartile |
|-------------|---------------|---------------|--------------|
| **Gross Margin** | 28% | 22-45% | 38% |
| **Operating Margin** | 10% | 6-18% | 15% |
| **Net Margin** | 6% | 3-12% | 10% |
| **EBITDA Margin** | 14% | 10-22% | 20% |

### Gross Margin by Subsector

| Subsector | Median Gross Margin |
|-----------|---------------------|
| Dairy Products | 22% |
| Bakery & Confectionery | 35% |
| Processed Foods | 30% |
| Beverages | 32% |
| Oils & Fats | 18% |
| Spices & Condiments | 42% |
| Snack Foods | 38% |

## 2.3 Cost Structure

### Typical Cost Breakdown

| Cost Category | % of Revenue | Variability | Optimization Potential |
|---------------|--------------|-------------|------------------------|
| Raw Materials & Ingredients | 55% | Variable | Medium |
| Packaging Materials | 12% | Semi-variable | High |
| Direct Labor | 10% | Semi-variable | Medium |
| Utilities (Energy, Water) | 5% | Semi-variable | High |
| Maintenance | 3% | Semi-variable | Medium |
| Quality Control & Testing | 2% | Fixed | Low |
| Administrative & Overhead | 8% | Fixed | Medium |
| Sales & Distribution | 5% | Variable | High |

## 2.4 Working Capital Benchmarks

| Metric | Median | Healthy Target | Warning Threshold |
|--------|--------|----------------|-------------------|
| **Days Sales Outstanding (DSO)** | 45 days | <40 days | >60 days |
| **Days Inventory Outstanding (DIO)** | 35 days | <30 days | >50 days |
| **Days Payables Outstanding (DPO)** | 40 days | 35-50 days | <30 days |
| **Cash Conversion Cycle** | 40 days | <30 days | >55 days |

## 2.5 Investment Benchmarks

| Investment Type | % of Revenue |
|-----------------|--------------|
| Total CapEx | 6% |
| Maintenance CapEx | 3.6% (60% of total) |
| Growth CapEx | 2.4% (40% of total) |
| R&D Investment | 1.5% |

## 2.6 Financial Health Indicators

| Ratio | Healthy Minimum | Optimal | Sector Median |
|-------|-----------------|---------|---------------|
| **Current Ratio** | 1.2 | 1.8 | 1.5 |
| **Quick Ratio** | 0.8 | 1.2 | 1.0 |
| **Debt-to-Equity** | <2.0 | <1.0 | 1.1 |
| **Interest Coverage** | >3.0 | >5.0 | 4.2 |

## 2.7 Valuation Multiples

| Multiple | Low | Median | High |
|----------|-----|--------|------|
| **Revenue Multiple** | 0.6x | 1.0x | 1.8x |
| **EBITDA Multiple** | 4.0x | 6.5x | 10.0x |

### Factors Affecting Premium

1. Brand strength and recognition
2. Export revenue percentage (>20% = premium)
3. Product innovation pipeline
4. Certifications (Halal, ISO, FSSC)
5. Customer concentration (<30% in top 3 = premium)
6. Owner dependency (low = premium)
7. Growth trajectory (>15% = premium)
8. Recurring revenue/contracts

---

# Dimension 3: Operational KPIs

## 3.1 Production Efficiency

### Overall Equipment Effectiveness (OEE)

| OEE Component | Sector Median | World Class | SME Target |
|---------------|---------------|-------------|------------|
| **Overall OEE** | 62% | 85% | 75% |
| Availability | 85% | 95% | 90% |
| Performance | 80% | 95% | 85% |
| Quality | 92% | 99.9% | 96% |

### Capacity Utilization

| Metric | Sector Median | Optimal Range |
|--------|---------------|---------------|
| **Capacity Utilization** | 68% | 75-90% |

### Throughput Metrics

| Metric | Unit | Sector Median | Top Quartile |
|--------|------|---------------|--------------|
| Production Volume | tons/month | 150 | 400 |
| Batch Cycle Time | hours/batch | 4.5 | 3.0 |
| Changeover Time | minutes | 45 | 20 |
| Line Speed Efficiency | % of rated | 78% | 90% |

## 3.2 Quality Metrics

| Metric | Sector Median | World Class | Target |
|--------|---------------|-------------|--------|
| **Defect Rate** | 2.5% | 0.5% | <1.5% |
| **First Pass Yield** | 94% | 99% | 98% |
| **Customer Complaint Rate** | 0.15 per 1,000 units | 0.05 | <0.10 |
| **Product Return Rate** | 1.2% | 0.3% | <0.8% |

### Food Safety Specific

| Metric | Sector Median | Target | Critical Threshold |
|--------|---------------|--------|-------------------|
| HACCP Compliance Score | 78% | 95% | <70% triggers review |
| CCP Deviations | 2.5/month | 0 | >5 triggers investigation |
| Product Recalls | 0.3/year | 0 | Any triggers root cause |
| Shelf Life Achievement | 92% | 99% | <90% triggers review |

## 3.3 Productivity Metrics

| Metric | Sector Median | Top Quartile | Target |
|--------|---------------|--------------|--------|
| **Revenue per Employee** | $65,000 | $95,000 | $80,000 |
| **Value Added per Employee** | $18,000 | $28,000 | $22,000 |
| **Cases per Labor Hour** | 12 | 20 | 16 |

### Productivity by Subsector

| Subsector | Revenue per Employee |
|-----------|---------------------|
| Dairy | $72,000 |
| Bakery/Confectionery | $48,000 |
| Processed Foods | $75,000 |
| Beverages | $95,000 |
| Oils & Fats | $85,000 |
| Snacks | $68,000 |

## 3.4 Delivery Performance

| Metric | Sector Median | World Class | Target |
|--------|---------------|-------------|--------|
| **On-Time Delivery (OTIF)** | 88% | 98% | 95% |
| **Order Fulfillment Cycle** | 5 days | 2 days | 3 days |
| **Perfect Order Rate** | 82% | 95% | 90% |

## 3.5 Safety Metrics

| Metric | Sector Median | Target | Calculation Basis |
|--------|---------------|--------|-------------------|
| **Total Recordable Incident Rate** | 4.2 | 2.0 | per 200,000 hours |
| **Lost Time Injury Frequency** | 1.8 | 0.5 | per 200,000 hours |

## 3.6 Environmental Metrics

| Metric | Sector Median | Target | Unit |
|--------|---------------|--------|------|
| **Energy Intensity** | 450 | 350 | kWh per ton output |
| **Water Usage** | 8 | 5 | m³ per ton output |
| **Waste to Landfill** | 12% | 5% | of total waste |

---

# Dimension 4: Regulatory Landscape

## 4.1 Licensing Requirements

### Required Licenses

| License | Issuing Authority | Countries | Validity | Initial Cost (USD) | Timeline |
|---------|-------------------|-----------|----------|-------------------|----------|
| **Food Manufacturing License** | Ministry of Health/Food Authority | All MENA | 1 year | $300-$800 | 4-12 weeks |
| **Industrial Operating License** | Ministry of Industry | EG, SA, AE, JO | 5 years | $500-$1,500 | 6-16 weeks |
| **Municipal Permit** | Local Municipality | All MENA | 1 year | $100-$300 | 1-4 weeks |
| **Environmental Clearance** | Environment Authority | EG, SA, AE | 2-3 years | $200-$500 | 4-8 weeks |
| **Commercial Registration** | Commerce Ministry | All MENA | Variable | $100-$500 | 1-2 weeks |

**Total Typical Timeline:** 4-6 months
**Total Estimated Cost:** $2,000-$8,000

## 4.2 Certifications

### Mandatory Certifications

| Certification | Type | Markets | Cost (USD) | Timeline | Validity |
|---------------|------|---------|------------|----------|----------|
| **Halal Certification** | Religious | GCC, MENA (mandatory) | $1,500-$5,000 | 2-6 months | 1 year |

### Recommended Certifications

| Certification | Type | Markets Enabled | Cost (USD) | Timeline | Validity |
|---------------|------|-----------------|------------|----------|----------|
| **ISO 22000** | Food Safety | Global | $8,000-$25,000 | 6-12 months | 3 years |
| **FSSC 22000** | Food Safety (GFSI) | Global, Major Retailers | $12,000-$35,000 | 9-18 months | 3 years |
| **BRC Global Standard** | Food Safety | UK, EU, US | $10,000-$30,000 | 6-12 months | 1 year |
| **HACCP** | Food Safety | All | $3,000-$10,000 | 3-6 months | 3 years |
| **ISO 9001** | Quality | All | $5,000-$15,000 | 4-8 months | 3 years |

### Export-Enabling Certifications

| Certification | Markets | Cost (USD) | Timeline | Notes |
|---------------|---------|------------|----------|-------|
| **Organic (ECOCERT/USDA)** | EU, US | $3,000-$12,000 | 12-36 months | Transition period required |
| **FDA Registration** | USA | $0-$2,000 | 1-3 months | Free registration, FSVP compliance required |
| **Kosher** | US, EU, Israel | $2,000-$8,000 | 2-6 months | Supervision fees ongoing |

## 4.3 Compliance Areas

### Food Safety & Hygiene

| Requirement | Description | Common Gaps |
|-------------|-------------|-------------|
| HACCP Plan | Hazard analysis and critical control points | Documentation, monitoring records |
| Temperature Control | Cold chain monitoring and recording | Continuous monitoring systems |
| Pest Control | Integrated pest management program | Documentation, frequency |
| Sanitation | Cleaning and sanitizing protocols | SOPs, verification records |
| Personal Hygiene | Worker health and hygiene standards | Training records, enforcement |
| Allergen Management | Cross-contamination prevention | Dedicated lines, labeling |
| Traceability | Batch tracking through supply chain | System implementation |

### Product Labeling

| Requirement | Description | Common Gaps |
|-------------|-------------|-------------|
| Ingredient Declaration | Complete list in descending order | Translation accuracy, allergens |
| Nutritional Information | Per 100g and per serving | Calculation errors |
| Date Marking | Production and expiry dates | Format compliance |
| Storage Instructions | Clear guidance | Missing or unclear |
| Allergen Warnings | Bold/highlighted declaration | Missing declarations |
| Country of Origin | Clear statement | Format non-compliance |

## 4.4 Regulatory Bodies by Country

| Country | Primary Body | Key Responsibilities |
|---------|--------------|---------------------|
| **Egypt** | NFSA (National Food Safety Authority) | Licensing, inspection, import/export |
| **Saudi Arabia** | SFDA (Saudi Food and Drug Authority) | Registration, standards, halal |
| **UAE** | ESMA + Local municipalities | Standards, conformity, halal |
| **Jordan** | JFDA (Jordan FDA) | Licensing, registration, inspection |
| **Morocco** | ONSSA | Food safety, plant/animal health |

## 4.5 Enforcement

| Violation Type | Typical Penalty | Severity |
|----------------|-----------------|----------|
| Minor labeling error | Warning to $500 | Low |
| Hygiene violation | $500-$5,000 | Medium |
| Food safety violation | $5,000-$50,000 + closure | High |
| Operating without license | Closure + legal action | Critical |

---

# Dimension 5: Competitive Dynamics

## 5.1 Market Structure

| Characteristic | Assessment |
|----------------|------------|
| **Structure Type** | Fragmented |
| **CR4 (Top 4 Concentration)** | 25% |
| **HHI (Herfindahl Index)** | 450 |

### Competitor Breakdown

| Category | Count | Market Share |
|----------|-------|--------------|
| Large (>500 employees) | 15 | 25% |
| Medium (100-500 employees) | 150 | 35% |
| Small (<100 employees) | 5,000+ | 40% |

### Market Leaders

| Leader Type | Share | Competitive Advantage |
|-------------|-------|----------------------|
| Multinational Subsidiaries | 12% | Technology, R&D, global sourcing |
| Regional Conglomerates | 8% | Scale, distribution, brand portfolio |
| Strong Local Brands | 15% | Local taste preferences, relationships |

## 5.2 Porter's Five Forces Analysis

### Overall Industry Attractiveness Score: 2.8/5 (Moderate)

### Force 1: Competitive Rivalry
**Intensity: HIGH (4/5)**

| Driver | Impact |
|--------|--------|
| Many competitors across subsectors | High fragmentation drives competition |
| Low switching costs for consumers | Easy to change brands |
| Price sensitivity in mass market | Margin pressure |
| Slow growth in mature categories | Fight for share |
| High fixed costs | Volume competition |

**Implication for SMEs:** Must differentiate through quality, niche positioning, or local relationships to avoid price wars.

### Force 2: Threat of New Entrants
**Level: MEDIUM (3/5)**

| Barrier | Height | Description |
|---------|--------|-------------|
| Capital Requirements | Medium | $100K-$2M depending on subsector |
| Regulatory Compliance | Medium | 4-6 months to achieve |
| Distribution Access | High | Shelf space limited and expensive |
| Brand Recognition | Medium | Loyalty exists but breakable |
| Economies of Scale | Medium | Advantages but not prohibitive |

**Implication for SMEs:** Barriers exist but are surmountable; focus on underserved niches.

### Force 3: Threat of Substitutes
**Level: MEDIUM (3/5)**

| Substitute | Threat Level |
|------------|--------------|
| Home-made alternatives | Medium |
| Fresh/unprocessed foods | Medium |
| Imported products | High in some categories |
| Foodservice/restaurants | Medium |
| Alternative proteins | Emerging |

**Switching Costs:** Low

**Implication for SMEs:** Emphasize convenience vs. home-made; quality vs. imports.

### Force 4: Supplier Power
**Level: MEDIUM (3/5)**

| Driver | Impact |
|--------|--------|
| Agricultural inputs commodity-driven | Price volatility exposure |
| Some ingredients have limited suppliers | Dependency risk |
| Packaging suppliers fragmented | Negotiating power |
| Import dependency for some inputs | Currency exposure |

**Implication for SMEs:** Develop multiple supplier relationships; consider backward integration.

### Force 5: Buyer Power
**Level: HIGH (4/5)**

| Driver | Impact |
|--------|--------|
| Modern retail demands margins | Profitability pressure |
| Foodservice negotiates hard | Volume vs. margin trade-off |
| Low switching costs | Easy to delist |
| Price transparency increasing | Margin compression |

**Implication for SMEs:** Diversify channels; build consumer relationships; unique value propositions.

## 5.3 Competitive Strategies

### Dominant Strategies in Sector
1. **Differentiation** (quality, innovation, brand)
2. **Focus** (niche markets, specialty products)

### Successful SME Strategies

| Strategy | Description | Success Factors |
|----------|-------------|-----------------|
| **Premium Quality Focus** | Compete on superior ingredients and taste | Consistent quality, premium packaging, certifications |
| **Regional/Traditional Specialization** | Leverage local recipes and heritage | Authentic recipes, cultural marketing |
| **Health & Wellness Positioning** | Target health-conscious consumers | Clean labels, organic certification, innovation |
| **Foodservice Specialization** | Focus on B2B rather than retail | Reliability, bulk flexibility, relationships |
| **Export Champion** | Target international markets | International certifications, competitive pricing |

## 5.4 Key Success Factors

| Factor | Importance | Typical SME Performance | Improvement Opportunity |
|--------|------------|-------------------------|------------------------|
| Product Quality & Consistency | Critical | Average | Quality systems, testing |
| Distribution Reach | Critical | Weak | Distributor partnerships |
| Brand Recognition | High | Weak | Packaging, social media |
| Cost Efficiency | High | Average | Procurement, lean practices |
| Innovation Capability | Medium | Average | R&D investment |
| Regulatory Compliance | Critical | Average | Certification investment |

## 5.5 Market Trends

| Trend | Impact | Timeline | SME Opportunity |
|-------|--------|----------|-----------------|
| Health & Wellness Focus | Positive | Accelerating | Healthier formulations |
| E-commerce Growth | Positive | Accelerating | D2C channels |
| Sustainability Pressure | Neutral | Increasing | Early mover differentiation |
| Private Label Growth | Negative | Ongoing | Become supplier or differentiate |
| Premiumization | Positive | Ongoing | Trade up to premium |
| Regional Trade Integration | Positive | Ongoing | Expand to neighbors |

---

*Continued in Part 2: Dimensions 6-11*
# RootRise Sector Knowledge Pack
# Food & Beverage Manufacturing (Part 2)
## Dimensions 6-11

---

# Dimension 6: Digital Maturity Patterns

## 6.1 Sector Digital Maturity

### Current State Assessment

| Metric | Value |
|--------|-------|
| **Average Digital Maturity Score** | 38/100 |
| **Comparison to Global** | Behind |

### Maturity Distribution

| Level | Description | % of MENA F&B SMEs |
|-------|-------------|-------------------|
| Level 1 | Manual/Paper-based | 25% |
| Level 2 | Basic Digital (spreadsheets, basic software) | 40% |
| Level 3 | Connected (integrated systems) | 25% |
| Level 4 | Advanced (data-driven) | 8% |
| Level 5 | Transformative (AI/predictive) | 2% |

## 6.2 Core Systems Adoption

| System | Adoption Rate | Typical Solutions | Implementation Cost (USD) | Timeline | ROI Period |
|--------|--------------|-------------------|---------------------------|----------|------------|
| **Accounting Software** | 75% | QuickBooks, Zoho Books, Xero | $500-$5,000 | 1-3 months | 6 months |
| **Inventory Management** | 45% | Zoho Inventory, Fishbowl | $2,000-$25,000 | 1-4 months | 12 months |
| **ERP** | 35% | SAP Business One, Odoo, ERPNext | $15,000-$100,000 | 3-12 months | 18 months |
| **CRM** | 30% | HubSpot, Zoho CRM, Salesforce | $1,000-$15,000 | 1-3 months | 12 months |
| **QMS** | 25% | MasterControl, Qualio | $5,000-$50,000 | 2-8 months | 18 months |
| **Production/MES** | 15% | Custom, AVEVA modules | $20,000-$150,000 | 4-12 months | 24 months |

## 6.3 Functional Digitization Gaps

| Function | Current Score | Gap to Best Practice | Priority Technologies | Quick Wins |
|----------|--------------|---------------------|----------------------|------------|
| Finance & Accounting | 65% | 20% | Cloud accounting, e-invoicing | Bank feed integration |
| Inventory & Warehouse | 40% | 40% | WMS, barcode/RFID | Barcode scanning |
| Quality Control | 35% | 45% | Digital QC forms, SPC | Tablet-based checklists |
| Sales & Customer | 35% | 45% | CRM, order portal | Basic CRM, WhatsApp Business |
| Production | 30% | 50% | MES, OEE monitoring | Digital production logs |
| Supply Chain | 30% | 50% | E-procurement, forecasting | Digital supplier database |

## 6.4 E-Commerce Landscape

| Metric | Current State |
|--------|---------------|
| B2B Digital Adoption | 20% |
| B2C Digital Adoption | 12% |
| D2C Potential | Medium |
| Digital Revenue Share | 5% of total revenue |
| Growth Trajectory | 25% annual growth |

### Preferred Platforms

| Platform | Primary Use | Region |
|----------|-------------|--------|
| Company Website | B2B orders, brand | All |
| Noon | B2C retail | GCC |
| Amazon.ae | B2C retail | UAE |
| Jumia | B2C retail | Egypt |
| Instagram/Facebook Shops | D2C, brand | All |
| WhatsApp Business | Orders, customer service | All |

## 6.5 Automation Opportunities

| Process | Current Automation | Potential | ROI Potential | Complexity | Technologies |
|---------|-------------------|-----------|---------------|------------|--------------|
| Inventory Counting | 25% | 85% | High | Low | Barcode, RFID, IoT |
| QC Documentation | 20% | 75% | High | Low | Digital forms, mobile apps |
| Production Scheduling | 15% | 70% | High | Medium | APS software, AI |
| Order Processing | 30% | 90% | High | Medium | EDI, portals, ERP |
| Packaging Lines | 40% | 85% | Medium | High | Automated packaging, robotics |
| AP/AR Processing | 35% | 80% | Medium | Low | Accounting automation |

## 6.6 Digital Transformation Roadmap

### Phase 1: Foundation (0-12 months)
**Investment:** $5,000-$30,000

| Initiative | Outcome |
|------------|---------|
| Cloud accounting implementation | Real-time financial visibility |
| Basic inventory management | Accurate stock levels |
| Digital QC documentation | Audit-ready records |
| Core data collection | Analytics foundation |

### Phase 2: Optimization (12-24 months)
**Investment:** $25,000-$100,000

| Initiative | Outcome |
|------------|---------|
| ERP or integrated systems | Connected operations |
| Production tracking/OEE | Efficiency gains |
| E-commerce channels | New revenue streams |
| CRM implementation | Better customer relationships |

### Phase 3: Transformation (24-48 months)
**Investment:** $50,000-$250,000

| Initiative | Outcome |
|------------|---------|
| Advanced analytics/BI | Data-driven decisions |
| IoT monitoring | Real-time visibility |
| Process automation | Productivity gains |
| Digital supply chain | Competitive advantage |

---

# Dimension 7: Workforce Norms

## 7.1 Workforce Composition

### Headcount by Revenue Tier

| Revenue Tier (USD) | Median Employees | Range |
|-------------------|------------------|-------|
| < $500,000 | 12 | 8-20 |
| $500,000 - $2,000,000 | 35 | 20-60 |
| $2,000,000 - $5,000,000 | 75 | 50-120 |
| $5,000,000 - $15,000,000 | 150 | 100-250 |
| > $15,000,000 | 300 | 200-500 |

### Role Distribution

| Category | % of Workforce | Typical Roles |
|----------|----------------|---------------|
| Production | 60% | Production workers, machine operators, packaging, QC inspectors |
| Administrative | 15% | Accountants, HR, admin assistants, procurement |
| Sales | 12% | Sales reps, key accounts, merchandisers, drivers |
| Technical | 8% | Food technologists, QC technicians, maintenance |
| Management | 5% | GM, production manager, sales manager, finance manager |

### Skill Level Distribution

| Level | % of Workforce |
|-------|----------------|
| Unskilled | 30% |
| Semi-skilled | 40% |
| Skilled | 20% |
| Professional | 10% |

## 7.2 Compensation Benchmarks

### Base Salaries by Role (Monthly USD)

| Role | Entry | Mid | Senior | Notes |
|------|-------|-----|--------|-------|
| Production Worker | $250 | $350 | $500 | Baseline for Egypt |
| Machine Operator | $350 | $500 | $700 | Higher with certifications |
| QC Technician | $400 | $600 | $900 | Lab skills valued |
| Food Technologist | $600 | $1,000 | $1,500 | University degree required |
| Production Manager | $1,200 | $2,000 | $3,500 | Experience premium |
| Sales Representative | $400 | $700 | $1,200 | Plus commission |

### Regional Salary Multipliers

| Country | Multiplier | Notes |
|---------|------------|-------|
| Egypt | 0.7x | Lower cost base |
| Jordan | 0.85x | Moderate cost |
| Morocco | 0.8x | Lower cost base |
| Saudi Arabia | 1.5x | Higher cost, nationalization |
| UAE | 1.8x | Highest cost market |

### Typical Benefits

- Social insurance (mandatory)
- Medical insurance (common in medium+ SMEs)
- Transportation allowance
- Meal allowance or subsidized meals
- End of service gratuity
- Annual bonus (0-2 months based on performance)

## 7.3 Skills Landscape

### Critical Skills Assessment

| Skill | Importance | Availability | Training Pathway |
|-------|------------|--------------|------------------|
| Food Safety & HACCP | Critical | Limited | HACCP courses (2-5 days), OJT |
| Quality Control Procedures | Critical | Limited | Internal training, certifications |
| Production Equipment Operation | Critical | Adequate | Manufacturer training, apprenticeship |
| Food Technology/Formulation | High | Scarce | University degree |
| Maintenance & Troubleshooting | High | Limited | Technical diplomas |
| Supply Chain Management | High | Limited | APICS certifications |
| Digital Literacy (Basic) | Medium | Adequate | Basic courses |
| Leadership & Supervision | High | Limited | Management programs |

### Critical Skill Gaps

| Skill | Gap Severity | Impact | Remediation Options |
|-------|--------------|--------|---------------------|
| Food safety management | Significant | Limits certification, export | External training, hire QA manager |
| Technical troubleshooting | Moderate | Downtime, costs | Training, maintenance contracts |
| Data analysis | Significant | Missed optimization | Train staff, hire graduate |
| Export & trade | Critical | Barrier to export | Partner with agencies, hire specialist |

## 7.4 Labor Dynamics

| Metric | Sector Average | Acceptable Range | Cost Impact |
|--------|----------------|------------------|-------------|
| **Turnover Rate** | 22% | 10-25% | $1,500 per turnover |
| **Absenteeism Rate** | 6% | <4% | Productivity loss |
| **Training Investment** | $120/employee/year | $200+ recommended | Capability building |

### Recruitment Difficulty

| Role | Difficulty |
|------|------------|
| Unskilled production | Easy |
| Skilled operators | Moderate |
| QC technicians | Moderate |
| Food technologists | Difficult |
| Experienced managers | Difficult |
| Sales representatives | Moderate |

## 7.5 Organizational Patterns

### Common Structures

1. **Owner-managed flat hierarchy** (small SMEs <30 employees)
2. **Functional structure** (medium SMEs 30-100)
3. **Divisional by product line** (larger/diverse SMEs)

### Span of Control Norms

| Level | Typical Ratio |
|-------|---------------|
| Production Supervisors | 1:15 |
| Administrative Managers | 1:8 |

### Common Organizational Challenges

- Owner doing too many roles (bottleneck)
- Lack of clear job descriptions
- Inadequate performance management
- Family dynamics in family businesses
- Resistance to delegation
- Key person dependency
- No succession planning

## 7.6 HR Maturity

| Metric | Value |
|--------|-------|
| **Average HR Maturity Score** | 35/100 |

### Common Gaps

- No formal HR policies/handbook
- Inconsistent compensation structures
- Minimal performance evaluation
- Ad-hoc training approach
- Poor personnel record-keeping
- No workforce planning

### Priority Improvements

1. Document basic HR policies
2. Implement simple performance tracking
3. Create training calendar for critical skills
4. Formalize compensation structure
5. Improve record keeping

---

# Dimension 8: Supply Chain Characteristics

## 8.1 Supply Chain Structure

| Attribute | Assessment |
|-----------|------------|
| **Typical Tiers** | 3 |
| **Upstream Complexity** | Moderate |
| **Integration Level** | Fragmented |

### Downstream Channels

| Channel | % of Volume | Trend |
|---------|-------------|-------|
| Modern Retail (Supermarkets) | 35% | Growing |
| Traditional Trade (Groceries) | 30% | Stable |
| Foodservice (Restaurants, Hotels) | 20% | Growing |
| Wholesale/Distributors | 10% | Stable |
| Export | 5% | Growing |
| Direct to Consumer | <1% | Emerging |

## 8.2 Supplier Landscape

### Key Input Categories

| Category | % of COGS | Concentration | Local Availability | Import Dependency | Price Volatility | Lead Time |
|----------|-----------|---------------|-------------------|-------------------|------------------|-----------|
| Agricultural Raw Materials | 35% | Fragmented | 60% | 40% | High | 1-8 weeks |
| Food Ingredients (processed) | 20% | Moderate | 45% | 55% | Medium | 2-12 weeks |
| Packaging Materials | 12% | Moderate | 70% | 30% | Medium | 2-8 weeks |
| Oils & Fats | 10% | Moderate | 30% | 70% | High | 4-16 weeks |
| Sugar & Sweeteners | 8% | Concentrated | 50% | 50% | High | 2-8 weeks |
| Dairy Ingredients | 8% | Moderate | 40% | 60% | Medium | 4-14 weeks |
| Flavorings & Additives | 5% | Concentrated | 25% | 75% | Low | 4-12 weeks |

### Common Supplier Issues

- Quality inconsistency
- Delivery reliability problems
- Price volatility exposure
- Limited supplier development
- Documentation gaps for traceability

## 8.3 Inventory Benchmarks

| Inventory Type | Typical Stock | Recommended | Warning |
|----------------|---------------|-------------|---------|
| Raw Materials | 4 weeks | 3-6 weeks | >8 weeks |
| Work in Progress | 3 days | 2 days | >5 days |
| Finished Goods | 3 weeks | 2-4 weeks | >6 weeks |

| Metric | Sector Median | Top Quartile |
|--------|---------------|--------------|
| **Inventory Turnover** | 8x | 12x |

### Common Inventory Issues

- Overstocking slow-movers
- Stockouts of fast-movers
- Poor shelf-life management (waste)
- Inaccurate counts
- Seasonal forecast errors
- Poor FIFO discipline

## 8.4 Logistics Profile

### Inbound Logistics

| Attribute | Typical |
|-----------|---------|
| Primary Modes | Road (dominant), Sea (imports) |
| Cost % of COGS | 4% |
| Critical Issues | Temperature control, customs clearance |

### Outbound Logistics

| Attribute | Typical |
|-----------|---------|
| Primary Modes | Road, Own fleet common |
| Cost % of Revenue | 6% |
| Delivery Expectations | 24-72 hours urban, 3-7 days remote |

### Warehousing

| Attribute | Benchmark |
|-----------|-----------|
| Space Requirement | 0.8 sqm per $1,000 revenue |
| Ambient Storage Cost | $4-8/sqm/month |
| Cold Storage Cost | $12-20/sqm/month |

### Regional Logistics Challenges

- Road infrastructure quality varies
- Cold chain gaps in some regions
- Border crossing delays
- Fuel cost volatility
- Limited 3PL sophistication
- Urban traffic congestion

## 8.5 Supply Chain Risks

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Supply Disruption (agriculture) | Medium | High | Multiple sourcing, safety stock |
| Price Volatility | High | Medium | Hedging, longer contracts |
| Quality Failure | Medium | High | Supplier audits, incoming QC |
| Logistics Disruption | Medium | Medium | Multiple providers, route planning |
| Supplier Concentration | Medium | High | Qualify alternatives |
| Currency Fluctuation | High | Medium | Natural hedging, forwards |

## 8.6 Lean Opportunities (8 Wastes)

| Waste Type | Prevalence | Typical Impact | Improvement Approach |
|------------|------------|----------------|---------------------|
| Overproduction | Medium | 3% of cost | Demand-driven scheduling |
| Inventory Excess | High | 5% of cost | JIT, ABC analysis |
| Waiting | High | 8% of cost | Line balancing, PM, SMED |
| Transportation | Medium | 2% of cost | Layout optimization |
| Defects & Rework | Medium | 4% of cost | Quality at source, SPC |
| Motion | Medium | 2% of cost | 5S, workstation design |
| Over-processing | Low | 1% of cost | Value stream mapping |
| Unused Talent | High | 5% of cost | Employee involvement |

---

# Dimension 9: Export Requirements

## 9.1 Sector Export Profile

| Metric | Value |
|--------|-------|
| **Export Intensity** | 12% of revenue (average) |
| **Growth Trend** | Growing |

### Primary Export Markets

| Region | Countries | Share of Exports |
|--------|-----------|------------------|
| GCC | SA, AE, KW, QA, BH, OM | 55% |
| Other MENA | IQ, LY, SD, YE | 20% |
| Africa | Sub-Saharan various | 12% |
| Europe | UK, DE, FR, IT | 8% |
| Other | US, AU, various | 5% |

### Export Barriers

- Certification requirements (especially EU, US)
- Packaging and labeling compliance
- Documentation complexity
- Market access knowledge
- Quality consistency
- Scale/capacity limitations
- Financing and payment terms

## 9.2 Target Market Profiles

### GCC Markets (Primary)

| Attribute | Assessment |
|-----------|------------|
| Market Size | $75 billion |
| Growth Rate | 5.5% |
| Entry Complexity | Medium |
| Required Certifications | Halal, GSO Conformity |
| Entry Timeline | 6 months |

**Entry Strategies:**
- Partner with established distributor
- Participate in Gulfood/SIAL exhibitions
- Enter through UAE as hub
- Private label for retailers

### European Union (Secondary)

| Attribute | Assessment |
|-----------|------------|
| Market Size | $1.2 trillion |
| Growth Rate | 2.5% |
| Entry Complexity | High |
| Required Certifications | FSSC 22000, EU Facility Approval |
| Entry Timeline | 18 months |

**Entry Strategies:**
- Ethnic food channels
- Specialty/gourmet positioning
- Private label for retailers
- Partner with EU importer

### Sub-Saharan Africa (Emerging)

| Attribute | Assessment |
|-----------|------------|
| Market Size | $150 billion |
| Growth Rate | 7.0% |
| Entry Complexity | Medium |
| Required Certifications | Country-specific, Halal for some |
| Entry Timeline | 6 months |

**Entry Strategies:**
- Partner with regional distributors
- Focus on Nigeria, Kenya, Ethiopia
- Leverage cultural/religious ties
- Competitive pricing positioning

## 9.3 Export Certifications

| Certification | Markets | Mandatory | Cost (USD) | Timeline |
|---------------|---------|-----------|------------|----------|
| Halal (GCC recognized) | GCC, Muslim markets | Yes | $1,500-$5,000 | 2-4 months |
| GSO Conformity | GCC | Yes | $500-$2,000 | 1-3 months |
| FSSC 22000 | EU, US, UK, global | No | $15,000-$40,000 | 9-18 months |
| BRC | UK, EU | No | $12,000-$35,000 | 6-12 months |
| FDA Registration | US | Yes | $0-$500 | 0.5-1 month |
| Organic (EU) | EU, UK | No | $3,000-$12,000 | 12-36 months |
| Kosher | US, EU, Israel | No | $2,000-$8,000 | 2-6 months |

## 9.4 Trade Agreements

| Agreement | Members | Key Benefits | Utilization |
|-----------|---------|--------------|-------------|
| GAFTA | Arab League | Zero tariffs, simplified customs | 65% |
| GCC Customs Union | GCC 6 | Single entry, no intra-tariffs | 80% |
| Egypt-EU Association | Egypt → EU | Reduced tariffs, quotas | 45% |
| Jordan-US FTA/QIZ | Jordan → US | Duty-free access | 55% |
| Morocco-EU | Morocco → EU | Progressive tariff elimination | 60% |

## 9.5 Export Documentation

| Document | Required For | Issuing Authority | Common Errors |
|----------|--------------|-------------------|---------------|
| Commercial Invoice | All | Exporter | Incomplete descriptions, value errors |
| Certificate of Origin | All | Chamber of Commerce | Origin criteria not met |
| Health Certificate | Food products | Ministry of Health | Product mismatch, expired |
| Halal Certificate | GCC, Muslim markets | Halal body | Non-recognized body |
| Phytosanitary Certificate | Plant products | Agriculture Ministry | Pest presence |
| Bill of Lading | Sea shipment | Carrier | Consignee errors |
| Packing List | All | Exporter | Inconsistency with invoice |

## 9.6 Export Financing Instruments

| Instrument | Description | Typical Terms |
|------------|-------------|---------------|
| Letter of Credit | Bank payment guarantee | At sight or 30-90 days |
| Export Credit Insurance | Protection against non-payment | 80-90% coverage |
| Pre-Export Financing | Working capital for orders | Up to 80% of L/C value |
| Factoring | Sell receivables for cash | 80-90% advance, 2-5% fee |

---

# Dimension 10: Packaging & Labeling Standards

## 10.1 Packaging Overview

### Primary Packaging Types

| Type | Trend | Key Applications |
|------|-------|------------------|
| Flexible pouches | Growing strongly | Snacks, sauces, ready meals |
| Plastic containers | Stable | Dairy, beverages, spreads |
| Glass containers | Stable (premium) | Jams, olive oil, sauces |
| Metal cans | Stable | Processed vegetables, fish |
| Cartons | Growing | Juices, dairy |

### Cost & Sustainability

| Metric | Value |
|--------|-------|
| Packaging as % of cost | 12% |
| Sustainability adoption | 15% |
| Recyclable packaging trend | Growing strongly |

## 10.2 Labeling Requirements by Market

### Saudi Arabia (SFDA)

| Element | Requirement | Common Failures |
|---------|-------------|-----------------|
| Language | Arabic mandatory | Translation errors |
| Product Name | Clear, prominent, Arabic | Font size issues |
| Ingredients | Descending order, Arabic | Missing items, allergens |
| Nutritional Info | Per 100g + serving, tabular | Calculation errors |
| Date Format | DD/MM/YYYY | Wrong format |
| Halal Mark | SFDA-approved logo | Non-approved logos |
| Allergens | Bold/highlighted, Arabic | Missing declarations |
| Country of Origin | Clear Arabic statement | Format issues |
| Front-of-Pack | Health warnings for high sugar/fat/sodium | New requirement |

**Penalty:** Product recall, fines up to SAR 100,000, import ban

### UAE (ESMA)

| Element | Requirement | Common Failures |
|---------|-------------|-----------------|
| Language | Arabic AND English mandatory | Missing Arabic |
| Product Name | Both languages | Inconsistency |
| Ingredients | Both languages | Allergen emphasis |
| Nutritional Info | Per 100g + serving | Format issues |
| Date Format | DD/MM/YYYY | Wrong format |
| Halal Mark | ESMA-approved | Unauthorized logos |
| Importer Details | Name, address, contact | Missing details |

**Penalty:** Product rejection, fines, import suspension

### European Union

| Element | Requirement | Common Failures |
|---------|-------------|-----------------|
| Language | Destination country language | Missing translation |
| Product Name | Legal name per EU regs | Wrong terminology |
| Ingredients | Descending order, allergens BOLD | Allergen emphasis |
| Nutritional Info | Per 100g, specific 7 nutrients | Missing salt (not sodium) |
| Date Format | "Best Before" DD/MM/YYYY | Format variation |
| Net Quantity | Metric with "e" mark | Missing "e" mark |
| Business Operator | EU address required | Non-EU address |
| Country of Origin | Required for certain products | Missing when required |
| Allergens | Bold or ALL CAPS in ingredients | Not emphasized |

**Font Minimum:** x-height 1.2mm (1mm for <80cm²)

## 10.3 Halal Labeling Requirements

### Recognized Certifying Bodies

| Body | Country | Recognized In |
|------|---------|---------------|
| ESMA/ICV | UAE | GCC, global |
| SFDA-approved bodies | Saudi Arabia | Saudi, GCC |
| JAKIM | Malaysia | Global (high recognition) |
| MUI | Indonesia | Global |
| SMIIC | Turkey | Many Muslim countries |

### Common Halal Labeling Issues

- Using non-recognized certification body
- Certificate expired
- Logo placement/size not per requirements
- Product not covered by certificate scope
- Shared facility issues not addressed

## 10.4 Nutritional Labeling

### Mandatory Markets

| Market | Format | Mandatory Nutrients |
|--------|--------|---------------------|
| GCC | Per 100g + serving | Energy, Fat, Sat Fat, Carbs, Sugars, Protein, Sodium |
| EU | Per 100g minimum | Energy, Fat, Sat Fat, Carbs, Sugars, Protein, Salt |
| US | Per serving, specific format | Calories, Fat, Sat Fat, Trans Fat, Cholesterol, Sodium, Carbs, Fiber, Sugars, Added Sugars, Protein |

### Calculation Methods

- Laboratory analysis (required for claims)
- Database calculation (acceptable for basic compliance)
- Recipe calculation (acceptable in some markets)

## 10.5 Packaging Compliance Checklist

| Check Item | Markets | Common Failure Rate |
|------------|---------|---------------------|
| All mandatory label elements present | All | 25% |
| Arabic translation accurate | GCC | 30% |
| Allergen declaration complete and emphasized | All | 20% |
| Nutritional values correctly calculated | All | 15% |
| Date format correct for market | All | 10% |
| Halal logo authorized and current | GCC | 15% |
| Font sizes meet minimums | EU | 20% |
| Country of origin correctly stated | All | 10% |

## 10.6 Packaging Upgrade Pathways

| From | To | Changes Required | Cost (USD) | Markets Unlocked |
|------|-----|------------------|------------|------------------|
| Domestic only | GCC export | Halal cert, Arabic labels, GSO compliance | $5,000-$15,000 | SA, AE, KW, QA, BH, OM |
| GCC compliant | EU export | FSSC cert, EU labeling, multilingual | $25,000-$60,000 | EU27, UK |
| Basic | Premium | Design upgrade, quality packaging | $10,000-$30,000 | Premium channels all markets |
| Conventional | Sustainable | Recyclable/bio materials | $15,000-$40,000 | EU, premium global |

---

# Dimension 11: MENA Regional Context

## 11.1 Country Profiles

### Egypt (EG)

| Category | Details |
|----------|---------|
| **Market Size** | GDP $387B, Population 109M |
| **Sector Contribution** | 4.2% of GDP, 1.2M employed |
| **Primary Regulator** | NFSA (National Food Safety Authority) |
| **Licensing Complexity** | Medium |
| **Ease of Doing Business** | Rank 114 |
| **Min Wage (Monthly)** | $140 USD |
| **Work Week** | 48 hours |
| **Nationalization** | None |
| **SME Lending** | Moderate |
| **Interest Rate** | 18-22% |
| **Key Ports** | Port Said, Damietta, Alexandria |
| **Free Zones** | Suez Canal Economic Zone, 10th of Ramadan |
| **Ramadan Impact** | High (+40% demand in confectionery/beverages) |

**Government Support Programs:**
- IMC Export Support
- MSME Development Agency financing
- Industrial Development Authority incentives

### Saudi Arabia (SA)

| Category | Details |
|----------|---------|
| **Market Size** | GDP $833B, Population 35M |
| **Sector Contribution** | 2.8% of GDP |
| **Primary Regulator** | SFDA |
| **Licensing Complexity** | Medium-High |
| **Ease of Doing Business** | Rank 62 |
| **Min Wage (Monthly)** | $800 USD (Saudis) |
| **Work Week** | 48 hours |
| **Nationalization** | Nitaqat system (quotas by sector) |
| **SME Lending** | Good |
| **Interest Rate** | 8-12% |
| **Key Ports** | Jeddah Islamic Port, King Abdullah Port |
| **Free Zones** | KAEC, Jazan |
| **Ramadan Impact** | Very High (+50% demand) |

**Government Support Programs:**
- Monsha'at SME Authority
- Saudi Industrial Development Fund
- Vision 2030 sector incentives

### United Arab Emirates (AE)

| Category | Details |
|----------|---------|
| **Market Size** | GDP $499B, Population 9.5M |
| **Sector Contribution** | 1.5% of GDP |
| **Primary Regulator** | ESMA + Emirates (local municipalities) |
| **Licensing Complexity** | Low-Medium |
| **Ease of Doing Business** | Rank 16 |
| **Min Wage (Monthly)** | None (market-driven) |
| **Work Week** | 48 hours |
| **Nationalization** | Emiratization targets (limited in manufacturing) |
| **SME Lending** | Good |
| **Interest Rate** | 6-10% |
| **Key Ports** | Jebel Ali (largest), Khalifa Port |
| **Free Zones** | 40+ including JAFZA, KIZAD |
| **Ramadan Impact** | High (+35% demand) |

**Government Support Programs:**
- Khalifa Fund
- Dubai SME
- Mohammed Bin Rashid Fund

### Jordan (JO)

| Category | Details |
|----------|---------|
| **Market Size** | GDP $45B, Population 11M |
| **Sector Contribution** | 3.5% of GDP |
| **Primary Regulator** | JFDA |
| **Licensing Complexity** | Medium |
| **Ease of Doing Business** | Rank 75 |
| **Min Wage (Monthly)** | $350 USD |
| **Work Week** | 48 hours |
| **Nationalization** | Limited quotas |
| **SME Lending** | Moderate |
| **Interest Rate** | 10-14% |
| **Key Ports** | Aqaba |
| **Free Zones** | QIZs, Aqaba SEZ |
| **Ramadan Impact** | High (+40% demand) |

**Government Support Programs:**
- Jordan Enterprise Development Corporation
- Development and Employment Fund
- QIZ/US market access benefits

### Morocco (MA)

| Category | Details |
|----------|---------|
| **Market Size** | GDP $130B, Population 37M |
| **Sector Contribution** | 4.0% of GDP |
| **Primary Regulator** | ONSSA |
| **Licensing Complexity** | Medium |
| **Ease of Doing Business** | Rank 53 |
| **Min Wage (Monthly)** | $280 USD |
| **Work Week** | 44 hours |
| **Nationalization** | None |
| **SME Lending** | Moderate |
| **Interest Rate** | 8-12% |
| **Key Ports** | Casablanca, Tangier Med |
| **Free Zones** | Tangier Free Zone, Casablanca Finance City |
| **Ramadan Impact** | High (+45% demand) |

**Government Support Programs:**
- Maroc PME
- Green Morocco Plan (agriculture linkages)
- Industrial Acceleration Plan

## 11.2 Regional Trade Dynamics

### Intra-MENA Trade

| Metric | Value |
|--------|-------|
| Total Intra-Region Trade | $180 billion |
| Food & Beverage Share | ~8% |

### Key Trade Corridors

| From | To | Primary Products | Annual Value |
|------|-----|------------------|--------------|
| Egypt | GCC | Processed foods, dairy, produce | $2.5B |
| Egypt | Libya, Sudan | Packaged foods, beverages | $1.2B |
| Jordan | Iraq, GCC | Dairy, processed foods | $800M |
| Morocco | EU | Fresh produce, processed foods | $3.5B |
| UAE | Re-export to MENA | All categories | $4.0B |

### Trade Agreements Impact

| Agreement | Key Benefit for F&B SMEs |
|-----------|-------------------------|
| GAFTA | Zero tariffs on qualifying Arab goods |
| GCC Customs Union | Single market of 50M+ consumers |
| Egypt-EU | Preferential access to 450M market |
| Morocco-EU | Geographic proximity, quotas |
| Jordan-US FTA | Duty-free US access via QIZ |

## 11.3 Regional Opportunities

| Opportunity | Countries | Relevance | Action for SMEs |
|-------------|-----------|-----------|-----------------|
| Health & Wellness Growth | All MENA | High | Develop healthier products |
| E-commerce Expansion | UAE, SA, EG | High | Launch online channels |
| Halal Export Growth | All → Global | High | Obtain recognized certification |
| Vision 2030 Localization | SA | High | Partner with Saudi distributors |
| African Market Entry | EG, MA | Medium | Target high-growth markets |
| Tourism Recovery | AE, EG, JO | Medium | Develop foodservice products |

## 11.4 Regional Challenges

| Challenge | Affected Countries | Impact | Mitigation |
|-----------|-------------------|--------|------------|
| Currency Volatility | EG, LB | High | Hedging, local sourcing |
| Import Dependencies | All | Medium | Supplier diversification |
| Logistics Infrastructure | EG, JO | Medium | Partner with 3PLs |
| Skilled Labor Shortage | All | Medium | Training investment |
| Regulatory Fragmentation | All | Medium | Market-specific compliance |

## 11.5 Government Initiatives

| Initiative | Country | Description | SME Benefits |
|------------|---------|-------------|--------------|
| Vision 2030 | SA | Economic diversification | Local manufacturing incentives |
| Industrial Strategy 2030 | EG | Industrial development | Export support, financing |
| Operation 300bn | AE | Manufacturing growth | Incentives, free zone benefits |
| Industrial Acceleration Plan | MA | Manufacturing growth | Sector-specific support |
| Make it in the Emirates | AE | Local production | Procurement preference |

---

# Quick Reference Tables

## Agent Data Requirements Summary

| Agent | Primary Data from This Pack |
|-------|----------------------------|
| **The Drucker** | Sector overview, subsectors, country context |
| **The Marvin** | KPIs (Dim 3), compliance areas (Dim 4), processes |
| **The Graham** | Financial benchmarks (Dim 2), valuation, working capital |
| **The Ricardo** | Export requirements (Dim 9), certifications, trade agreements |
| **The Lovelace** | Digital maturity (Dim 6), systems, automation |
| **The Mayo** | Workforce norms (Dim 7), compensation, labor laws |
| **The Ohno** | Supply chain (Dim 8), lean opportunities, inventory |
| **The Porter** | Competitive dynamics (Dim 5), five forces, trends |
| **The Landor** | Packaging & labeling (Dim 10), market requirements |

## Critical Thresholds Summary

| Metric | Good | Warning | Critical |
|--------|------|---------|----------|
| Gross Margin | >28% | 22-28% | <22% |
| OEE | >75% | 60-75% | <60% |
| On-Time Delivery | >95% | 85-95% | <85% |
| Inventory Turnover | >10x | 6-10x | <6x |
| Turnover Rate | <15% | 15-25% | >25% |
| Digital Maturity | >60 | 35-60 | <35 |
| Export Readiness | >70 | 40-70 | <40 |

---

# Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | December 2025 | RootRise Product Team | Initial Food & Beverage sector pack |

---

*This document provides comprehensive sector intelligence for Food & Beverage Manufacturing SMEs in the MENA region. For schema specification, see `RootRise_Sector_Knowledge_Framework.md`.*
