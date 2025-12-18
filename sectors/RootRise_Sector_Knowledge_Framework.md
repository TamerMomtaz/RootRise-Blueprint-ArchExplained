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
