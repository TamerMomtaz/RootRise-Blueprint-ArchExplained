---
agent: all
category: Eye-Lens
id: EYE-001
title: Export Readiness Transformation Lens
language: EN
version: v1.0
date: 2026-01-06
sector_specific: false
sectors: all
eye_lenses: export-readiness
summary: Configuration for Export Readiness transformation objective
---

# Export Readiness Transformation Lens

## 1. Lens Definition

**User Intent:** "I want to sell internationally"

**Core Question:** What does this SME need to do to successfully access and serve international markets?

**Success Metric:** SME achieves first export transaction within target timeline (typically 12-24 months)

## 2. Agent Activation Rules

### 2.1 Agent Priority Order

When Export Readiness lens is selected:

| Priority | Agent | Role | Activation |
|----------|-------|------|------------|
| 1 | **The Ricardo** | Primary export strategist | Always Active |
| 2 | **The Landor** | Packaging & labeling compliance | Always Active |
| 3 | **The Graham** | Export finance & risk | Always Active |
| 4 | **The Marvin** | Overall diagnostic | Always Active |
| 5 | **The Ohno** | Supply chain & logistics | Conditional |
| 6 | **The Porter** | Market analysis | Conditional |
| 7 | **The Deming** | Quality & compliance | Conditional |
| 8 | **The Lovelace** | Digital export enablers | Optional |
| 9 | **The Mayo** | Export team readiness | Optional |

### 2.2 Conditional Activation Rules

```
IF sector = Manufacturing:
    Activate The Ohno (supply chain critical)
    Activate The Deming (quality certifications)

IF target_market = "EU" OR target_market = "USA":
    Activate The Deming (regulatory compliance)
    Activate The Landor (mandatory)

IF company_size > 50 employees:
    Activate The Mayo (org readiness)

IF digital_maturity < 3:
    Activate The Lovelace (e-commerce, digital presence)
```

## 3. Pillar Weight Adjustments

### 3.1 Modified Weightings

| Pillar | Default Weight | Export Lens Weight | Rationale |
|--------|----------------|-------------------|-----------|
| Operations | 25% | 30% | Production quality critical for export |
| Finance | 25% | 20% | Important but not primary driver |
| Market | 20% | 25% | International market access key |
| Organization | 15% | 10% | Secondary consideration |
| Digital | 15% | 15% | Unchanged |

### 3.2 Dimension Priority Within Pillars

**Operations (Priority dimensions):**
1. Quality Management (40% of pillar) — Export markets demand higher quality
2. Process Documentation (30%) — Certifications require documented processes
3. Production Capacity (20%) — Must have capacity for export volumes
4. Resource Efficiency (10%) — Less critical for initial export

**Finance (Priority dimensions):**
1. Working Capital (40%) — Export credit terms require cash buffer
2. Risk Management (30%) — Currency, payment, country risk
3. Profitability (20%) — Must have margin headroom for export pricing
4. Growth Investment (10%) — Secondary

**Market (Priority dimensions):**
1. International Market Knowledge (40%) — Critical for export success
2. Competitive Positioning (25%) — How does product compare globally?
3. Customer Relationships (20%) — B2B export often relationship-driven
4. Brand Recognition (15%) — Important for consumer products

## 4. Question Prioritization

### 4.1 High-Priority Questions

When Export Readiness lens is active, emphasize these questionnaire sections:

| Section | Priority | Key Questions |
|---------|----------|---------------|
| Quality & Certifications | CRITICAL | Current certifications, target certifications, quality systems |
| International Experience | CRITICAL | Previous export, import relationships, international travel |
| Product Specifications | HIGH | Product standards, packaging, shelf life, regulations |
| Financial Capacity | HIGH | Working capital, credit facilities, insurance |
| Production Capacity | HIGH | Current utilization, expansion capability |
| Logistics | HIGH | Shipping experience, cold chain, documentation |

### 4.2 De-Prioritized Questions

| Section | Original Priority | Export Lens Priority | Rationale |
|---------|------------------|---------------------|-----------|
| HR Policies | Medium | Low | Focus on export capability first |
| Office Digital Tools | Medium | Low | Not export-critical |
| Local Marketing | Medium | Low | Domestic market secondary |
| Succession Planning | Medium | Low | Long-term consideration |

## 5. Output Prioritization

### 5.1 Report Section Order

For Export Readiness lens, reorder report sections:

1. **Export Readiness Score** — Lead with the key metric
2. **Certification Gap Analysis** — Most actionable for most SMEs
3. **Target Market Assessment** — Where can they realistically export?
4. **Operations Assessment** — Can they produce export-quality product?
5. **Financial Readiness** — Can they finance export growth?
6. **Action Roadmap** — Phased plan to export readiness
7. Other pillars (Organization, Digital) — Supporting information

### 5.2 Recommendation Categories

| Category | Priority | Focus |
|----------|----------|-------|
| Certification Requirements | 1 | What certifications are non-negotiable |
| Documentation Gaps | 2 | What documentation must be created |
| Market Entry Strategy | 3 | Which markets to target first |
| Operational Improvements | 4 | Quality and capacity upgrades |
| Financial Preparation | 5 | Working capital, insurance, hedging |
| Packaging & Labeling | 6 | Compliance with target market |
| Logistics Setup | 7 | Shipping, freight, customs |

## 6. Benchmark Adjustments

### 6.1 Export-Specific Benchmarks

Compare SME not just to sector average, but to **export-active peers:**

| Metric | Sector Average | Export-Active Average | Target for Export |
|--------|----------------|----------------------|-------------------|
| Quality Rejection Rate | 3.0% | 1.5% | < 2.0% |
| Certifications Held | 1.2 | 3.4 | ≥ 2 relevant |
| Documentation Score | 5.5/10 | 7.8/10 | ≥ 7.0/10 |
| Working Capital Days | 45 | 75 | ≥ 60 |

### 6.2 Export Readiness Index

Calculate an Export Readiness Index (ERI) specific to this lens:

```
ERI = (Certification Score × 0.30) +
      (Documentation Score × 0.20) +
      (Quality Score × 0.20) +
      (Financial Readiness × 0.15) +
      (Market Knowledge × 0.15)
```

| ERI Score | Readiness Level | Typical Timeline to First Export |
|-----------|-----------------|----------------------------------|
| 8.0 - 10.0 | Export Ready | 0-6 months |
| 6.0 - 7.9 | Near Ready | 6-12 months |
| 4.0 - 5.9 | Developing | 12-18 months |
| 2.0 - 3.9 | Foundation Building | 18-24 months |
| 0.0 - 1.9 | Not Ready | 24+ months or not viable |

## 7. Handoff Configurations

### 7.1 Marvin → Ricardo Handoff

When Marvin completes diagnostic, pass to Ricardo:

```json
{
  "handoff_type": "export_deep_dive",
  "priority": "high",
  "context": {
    "sector": "{{sector}}",
    "current_certifications": ["{{certs}}"],
    "target_markets_mentioned": ["{{markets}}"],
    "export_experience": "{{experience_level}}",
    "product_categories": ["{{products}}"],
    "eri_score": {{eri}},
    "critical_gaps": ["{{gaps}}"]
  },
  "requested_outputs": [
    "target_market_recommendation",
    "certification_roadmap",
    "market_entry_strategy",
    "timeline_estimate"
  ]
}
```

### 7.2 Marvin → Landor Handoff

```json
{
  "handoff_type": "packaging_compliance",
  "priority": "high",
  "context": {
    "target_markets": ["{{markets}}"],
    "product_type": "{{product}}",
    "current_packaging": "{{packaging_description}}",
    "current_labels": "{{label_status}}"
  },
  "requested_outputs": [
    "compliance_gap_analysis",
    "label_requirements",
    "packaging_recommendations",
    "cost_estimate"
  ]
}
```

## 8. Success Criteria for This Lens

### 8.1 Short-Term (Diagnostic Quality)

- [ ] Export Readiness Index calculated
- [ ] Certification gaps clearly identified
- [ ] At least 2 target markets recommended
- [ ] Financial readiness assessed
- [ ] Timeline to export estimated

### 8.2 Medium-Term (Transformation Progress)

- [ ] SME begins certification process within 60 days
- [ ] Working capital arranged within 6 months
- [ ] First export inquiry generated within 12 months

### 8.3 Long-Term (Business Impact)

- [ ] First export transaction completed
- [ ] Export revenue > 10% of total within 24 months
- [ ] Second export market entered within 36 months

## 9. Related Resources

| Resource | Location | Purpose |
|----------|----------|---------|
| Export Market Profiles | Sector Knowledge Packs | Market-specific requirements |
| Certification Guide | Ricardo Knowledge Pack | HACCP, ISO, etc. details |
| Packaging Regulations | Landor Knowledge Pack | Label requirements by market |
| Export Finance Guide | Graham Knowledge Pack | Letters of credit, insurance |
| Case Studies | Marvin Cases | Export success stories |

---

*Lens Owner: The Drucker (Orchestrator) | Review Cycle: Semi-annual | Last Updated: January 2026*
