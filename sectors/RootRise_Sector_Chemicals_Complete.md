# RootRise Sector Knowledge Pack
# Chemicals & Plastics
## Version 1.0 | December 2025

---

# Sector Metadata

```json
{
  "metadata": {
    "sector_id": "chemicals_plastics",
    "sector_name": "Chemicals & Plastics",
    "sector_name_ar": "الكيماويات والبلاستيك",
    "version": "1.0.0",
    "last_updated": "2025-12-11",
    "data_sources": [
      {
        "source_id": "gpca_2024",
        "name": "Gulf Petrochemicals and Chemicals Association Annual Report",
        "type": "industry_association",
        "publication_date": "2024-06",
        "reliability_score": 0.92
      },
      {
        "source_id": "icis_mena_2024",
        "name": "ICIS MENA Petrochemicals Outlook",
        "type": "research",
        "publication_date": "2024-09",
        "reliability_score": 0.90
      },
      {
        "source_id": "unido_chemicals_2023",
        "name": "UNIDO Chemical Industry Development",
        "type": "international_org",
        "publication_date": "2023-11",
        "reliability_score": 0.88
      },
      {
        "source_id": "statista_plastics_2024",
        "name": "Statista Plastics Industry MENA",
        "type": "research",
        "publication_date": "2024-08",
        "reliability_score": 0.85
      },
      {
        "source_id": "rootrise_proprietary",
        "name": "RootRise SME Assessment Data",
        "type": "proprietary",
        "publication_date": "2025-01",
        "reliability_score": 0.90
      }
    ],
    "applicable_countries": ["EG", "SA", "AE", "JO", "BH", "KW", "OM", "MA", "TN"],
    "sme_size_range": {
      "min_employees": 10,
      "max_employees": 250,
      "min_revenue_usd": 200000,
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
| **ISIC Rev.4 Division** | 20, 22 | Chemicals and chemical products; Rubber and plastics products |
| **ISIC Groups** | 20.1-20.6, 22.1-22.2 | Various chemical and plastic manufacturing |
| **NACE Rev.2** | C20, C22 | Chemical and plastics manufacturing |
| **RootRise Type** | Manufacturing | Process and discrete manufacturing |

### Detailed ISIC Classification

**Chemical Manufacturing (Division 20):**

| ISIC Class | Description | Key Products |
|------------|-------------|--------------|
| 20.11 | Industrial gases | Oxygen, nitrogen, argon, CO2, acetylene |
| 20.12 | Dyes and pigments | Colorants, pigments, dyes |
| 20.13 | Other inorganic basic chemicals | Acids, alkalis, salts, industrial chemicals |
| 20.14 | Other organic basic chemicals | Solvents, organic intermediates |
| 20.15 | Fertilizers and nitrogen compounds | NPK, urea, ammonia, phosphates |
| 20.16 | Plastics in primary forms | Polyethylene, polypropylene, PVC, PET |
| 20.17 | Synthetic rubber | Rubber compounds |
| 20.21 | Pesticides and agrochemicals | Herbicides, insecticides, fungicides |
| 20.22 | Paints, varnishes, coatings | Architectural, industrial paints |
| 20.23 | Soap, detergents, cosmetics | Cleaning products, personal care |
| 20.29 | Other chemical products | Adhesives, explosives, inks, additives |
| 20.30 | Man-made fibers | Synthetic fibers for textiles |

**Rubber and Plastics Products (Division 22):**

| ISIC Class | Description | Key Products |
|------------|-------------|--------------|
| 22.11 | Rubber tires and tubes | Vehicle tires, inner tubes |
| 22.19 | Other rubber products | Hoses, belts, gaskets, mats |
| 22.21 | Plastic plates, sheets, tubes | Films, sheets, pipes, profiles |
| 22.22 | Plastic packaging | Bags, bottles, containers, caps |
| 22.23 | Plastic building products | Doors, windows, tanks, fittings |
| 22.29 | Other plastic products | Household items, industrial parts |

## 1.2 Value Chain Position

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    CHEMICALS & PLASTICS VALUE CHAIN                          │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  FEEDSTOCK           BASIC CHEMICALS      INTERMEDIATES      END PRODUCTS   │
│  (Upstream)          (Large Scale)        (Processing)       (SME Domain)   │
│                                                                              │
│  ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐ ┌────────────┐ │
│  │ Oil & Gas       │ │ Petrochemicals  │ │ Compounding     │ │ Plastic    │ │
│  │ Refineries      │►│ (Ethylene,      │►│ Masterbatch     │►│ Products   │ │
│  │ Natural Gas     │ │  Propylene,     │ │ Additives       │ │ Packaging  │ │
│  └─────────────────┘ │  Aromatics)     │ └─────────────────┘ │ Pipes      │ │
│                      └─────────────────┘          │          │ Films      │ │
│  ┌─────────────────┐ ┌─────────────────┐ ┌───────▼─────────┐ │ Bottles    │ │
│  │ Mining          │ │ Basic Chemicals │ │ Formulation     │ │ Parts      │ │
│  │ (Phosphates,    │►│ (Acids, Alkalis │►│ Blending        │►└────────────┘ │
│  │  Potash, Salt)  │ │  Fertilizers)   │ │ Custom Mixing   │               │
│  └─────────────────┘ └─────────────────┘ └─────────────────┘ ┌────────────┐ │
│                                                   │          │ Paints     │ │
│  ┌─────────────────┐ ┌─────────────────┐ ┌───────▼─────────┐ │ Coatings   │ │
│  │ Agricultural    │ │ Specialty       │ │ Formulated      │►│ Adhesives  │ │
│  │ Inputs          │►│ Chemicals       │►│ Products        │ │ Detergents │ │
│  │                 │ │                 │ │                 │ │ Cosmetics  │ │
│  └─────────────────┘ └─────────────────┘ └─────────────────┘ └────────────┘ │
│                                                                              │
│  SME FOCUS: Plastics Processing ◄──► Formulated Products ◄──► Distribution │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Primary Position:** 
- **Upstream (Basic Chemicals):** Dominated by large petrochemical companies (SABIC, EQUATE, etc.)
- **Midstream (Processing/Compounding):** Mix of medium enterprises and large companies
- **Downstream (Conversion/Products):** Primary SME domain - plastics conversion, paints, cleaning products

## 1.3 Subsector Taxonomy

### Subsector 1: Plastic Packaging Manufacturing (plastic_packaging)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Plastic Packaging Manufacturing |
| **Name (AR)** | تصنيع العبوات البلاستيكية |
| **ISIC Classes** | 22.22 |
| **Typical Products** | Bottles, containers, caps, closures, films, bags, pouches, crates |
| **Distinguishing Characteristics** | High volume, thin margins, customer concentration (FMCG), blow molding/injection, growing sustainability pressure |

### Subsector 2: Plastic Pipes & Profiles (plastic_pipes)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Plastic Pipes & Profiles |
| **Name (AR)** | أنابيب وقطاعات بلاستيكية |
| **ISIC Classes** | 22.21, 22.23 |
| **Typical Products** | PVC pipes, HDPE pipes, PPR pipes, conduits, profiles, tanks, fittings |
| **Distinguishing Characteristics** | Infrastructure-linked, construction cycles, technical standards, government specifications |

### Subsector 3: Plastic Films & Sheets (plastic_films)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Plastic Films & Sheets |
| **Name (AR)** | أفلام وصفائح بلاستيكية |
| **ISIC Classes** | 22.21 |
| **Typical Products** | Stretch film, shrink film, agricultural film, lamination film, sheets |
| **Distinguishing Characteristics** | Extrusion-based, commodity pricing, agricultural demand, export potential |

### Subsector 4: Industrial Plastic Products (industrial_plastics)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Industrial Plastic Products |
| **Name (AR)** | منتجات بلاستيكية صناعية |
| **ISIC Classes** | 22.29 |
| **Typical Products** | Automotive parts, electrical components, appliance parts, industrial containers, pallets |
| **Distinguishing Characteristics** | Technical specifications, injection molding, OEM relationships, quality-critical |

### Subsector 5: Paints & Coatings (paints_coatings)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Paints & Coatings |
| **Name (AR)** | الدهانات والطلاءات |
| **ISIC Classes** | 20.22 |
| **Typical Products** | Architectural paints, industrial coatings, automotive finishes, wood coatings, protective coatings |
| **Distinguishing Characteristics** | Formulation expertise, color matching, brand importance, distribution network, construction-linked |

### Subsector 6: Cleaning Products & Detergents (cleaning_products)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Cleaning Products & Detergents |
| **Name (AR)** | منتجات التنظيف والمنظفات |
| **ISIC Classes** | 20.23 |
| **Typical Products** | Household cleaners, industrial cleaners, laundry detergents, dish soap, disinfectants |
| **Distinguishing Characteristics** | Consumer brand, distribution-intensive, formulation know-how, regulatory compliance, competitive market |

### Subsector 7: Adhesives & Sealants (adhesives_sealants)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Adhesives & Sealants |
| **Name (AR)** | اللاصقات والمواد المانعة للتسرب |
| **ISIC Classes** | 20.29 |
| **Typical Products** | Construction adhesives, industrial adhesives, packaging adhesives, sealants, tapes |
| **Distinguishing Characteristics** | Technical formulation, application-specific, B2B focus, construction/packaging demand |

### Subsector 8: Personal Care & Cosmetics (personal_care)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Personal Care & Cosmetics |
| **Name (AR)** | العناية الشخصية ومستحضرات التجميل |
| **ISIC Classes** | 20.23 |
| **Typical Products** | Shampoo, lotions, creams, hair care, skin care, fragrances, oral care |
| **Distinguishing Characteristics** | Brand/marketing intensive, regulatory (halal, safety), trend-driven, packaging important |

### Subsector 9: Specialty Chemicals & Compounds (specialty_chemicals)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Specialty Chemicals & Compounds |
| **Name (AR)** | الكيماويات والمركبات المتخصصة |
| **ISIC Classes** | 20.29, 20.16 |
| **Typical Products** | Masterbatch, plastic compounds, additives, water treatment chemicals, construction chemicals |
| **Distinguishing Characteristics** | Technical expertise, formulation IP, B2B sales, quality-critical, growing segment |

## 1.4 Adjacent Sectors

| Sector | Relationship | Relevance Score | Interaction |
|--------|--------------|-----------------|-------------|
| Petrochemicals | Supplier | 0.95 | Polymer resin supply |
| Food & Beverage | Customer | 0.90 | Packaging demand |
| Construction | Customer | 0.85 | Pipes, paints, adhesives |
| Agriculture | Customer | 0.80 | Films, irrigation, agrochemicals |
| Automotive | Customer | 0.75 | Parts, coatings |
| Textiles | Customer | 0.70 | Synthetic fibers, auxiliaries |
| Healthcare/Pharma | Customer | 0.70 | Packaging, disposables |
| Oil & Gas | Supplier/Customer | 0.80 | Feedstock, oilfield chemicals |

---

# Dimension 2: Financial Benchmarks

## 2.1 Revenue Benchmarks

### Revenue Distribution by Subsector

| Subsector | Median Revenue (USD) | P25 | P75 |
|-----------|---------------------|-----|-----|
| Plastic Packaging | $3,500,000 | $800,000 | $15,000,000 |
| Plastic Pipes & Profiles | $4,000,000 | $1,000,000 | $18,000,000 |
| Plastic Films & Sheets | $3,000,000 | $600,000 | $12,000,000 |
| Industrial Plastic Products | $2,500,000 | $500,000 | $10,000,000 |
| Paints & Coatings | $5,000,000 | $1,500,000 | $20,000,000 |
| Cleaning Products | $2,000,000 | $400,000 | $8,000,000 |
| Adhesives & Sealants | $2,500,000 | $600,000 | $10,000,000 |
| Personal Care/Cosmetics | $1,500,000 | $300,000 | $6,000,000 |
| Specialty Chemicals | $3,000,000 | $700,000 | $12,000,000 |

### Revenue Growth Rates

| Performance Level | Annual Growth |
|-------------------|---------------|
| Sector Average | 7% |
| Top Quartile | 15%+ |
| Bottom Quartile | 0% |

**Growth Drivers:**
- Population growth (consumer products)
- Construction activity (pipes, paints)
- Industrial development (technical plastics)
- Sustainability transition (recycled content)
- Import substitution initiatives

### Seasonality Pattern

| Attribute | Value |
|-----------|-------|
| **Pattern Type** | Moderate |
| **Peak Periods** | Q1, Q4 (construction activity); Ramadan (cleaning, personal care) |
| **Low Periods** | Summer (construction slowdown); variable by subsector |
| **Revenue Variance** | ±15-20% from mean |

### Seasonality by Subsector

| Subsector | Seasonality | Peak Period |
|-----------|-------------|-------------|
| Plastic Packaging | Low | Year-round (FMCG demand) |
| Pipes & Profiles | High | Construction season (Oct-May) |
| Agricultural Films | High | Planting seasons |
| Paints | High | Construction season |
| Cleaning Products | Medium | Ramadan, year-end |
| Personal Care | Medium | Ramadan, holidays |
| Industrial Plastics | Low | Year-round |

## 2.2 Profitability Benchmarks

### Margin Benchmarks by Subsector

| Subsector | Gross Margin | Operating Margin | Net Margin |
|-----------|--------------|------------------|------------|
| Plastic Packaging | 18-25% | 6-12% | 4-8% |
| Plastic Pipes & Profiles | 22-30% | 10-16% | 6-10% |
| Plastic Films & Sheets | 15-22% | 5-10% | 3-7% |
| Industrial Plastic Products | 25-35% | 12-18% | 8-12% |
| Paints & Coatings | 35-45% | 12-20% | 8-14% |
| Cleaning Products | 30-40% | 10-18% | 6-12% |
| Adhesives & Sealants | 35-45% | 14-22% | 10-16% |
| Personal Care/Cosmetics | 45-60% | 15-25% | 10-18% |
| Specialty Chemicals | 30-40% | 12-20% | 8-14% |

### Sector Blended Median

| Margin Type | Sector Median | Healthy Range | Top Quartile |
|-------------|---------------|---------------|--------------|
| **Gross Margin** | 30% | 18-50% | 42% |
| **Operating Margin** | 12% | 6-22% | 18% |
| **Net Margin** | 8% | 4-15% | 12% |
| **EBITDA Margin** | 15% | 8-25% | 20% |

### Margin Drivers

**Positive Factors:**
- Formulation expertise (proprietary blends)
- Brand premium (consumer products)
- Technical differentiation
- Customer lock-in (specifications)
- Efficient production
- Backward integration (compounding)

**Negative Factors:**
- Raw material volatility (polymers, solvents)
- Customer concentration
- Commodity competition
- Import competition
- Energy costs
- Working capital intensity

## 2.3 Cost Structure

### Plastics Conversion Cost Breakdown

| Cost Category | % of Revenue | Notes |
|---------------|--------------|-------|
| Raw Materials (Polymers) | 50-65% | Largest cost, volatile |
| Additives & Colorants | 5-10% | Masterbatch, stabilizers |
| Direct Labor | 8-12% | Machine operators, QC |
| Energy (Electricity) | 5-10% | Significant for processing |
| Depreciation | 4-8% | Machinery-intensive |
| Packaging | 2-4% | For finished goods |
| Overhead & Admin | 8-12% | Management, sales, support |
| Logistics | 3-5% | Delivery costs |

### Formulated Products Cost Breakdown (Paints, Cleaning)

| Cost Category | % of Revenue | Notes |
|---------------|--------------|-------|
| Raw Materials | 35-50% | Pigments, solvents, surfactants |
| Packaging | 10-15% | Containers, labels |
| Direct Labor | 8-12% | Production, filling |
| Energy | 2-5% | Lower than plastics |
| Marketing & Sales | 8-15% | Brand-dependent |
| Distribution | 5-10% | Retail, wholesale network |
| Overhead & Admin | 8-12% | Management, R&D |

### Raw Material Price Sensitivity

| Input | % of COGS | Price Volatility | Hedging Ability |
|-------|-----------|------------------|-----------------|
| Polyethylene (PE) | 15-40% | High | Limited |
| Polypropylene (PP) | 10-30% | High | Limited |
| PVC Resin | 10-30% | High | Limited |
| PET Resin | 5-20% | High | Limited |
| Titanium Dioxide | 5-15% | Medium-High | Limited |
| Solvents | 5-15% | Medium | Some |
| Surfactants | 5-15% | Medium | Limited |

## 2.4 Working Capital Benchmarks

| Metric | Plastics Conversion | Formulated Products | Distribution |
|--------|--------------------|--------------------|--------------|
| **DSO** | 60-90 days | 45-75 days | 45-60 days |
| **DIO** | 45-60 days | 30-45 days | 60-90 days |
| **DPO** | 45-60 days | 30-45 days | 30-45 days |
| **Cash Conversion Cycle** | 45-75 days | 35-60 days | 60-90 days |

### Working Capital Intensity

| Subsector | NWC % of Revenue | Notes |
|-----------|------------------|-------|
| Plastic Packaging | 20-30% | Inventory + receivables |
| Pipes & Profiles | 25-35% | Construction payment cycles |
| Paints & Coatings | 20-30% | Distribution inventory |
| Cleaning Products | 15-25% | Faster turnover |
| Personal Care | 15-25% | Retail demand |
| Specialty Chemicals | 20-30% | Custom inventory |

## 2.5 Investment & Capital Requirements

### CapEx by Subsector

| Subsector | Initial Investment | % Revenue (Maintenance) | Asset Life |
|-----------|-------------------|------------------------|------------|
| Plastic Packaging (Injection) | $500K-$5M | 4-6% | 10-15 years |
| Plastic Packaging (Blow Molding) | $300K-$3M | 4-6% | 10-12 years |
| Pipes & Profiles (Extrusion) | $500K-$5M | 5-7% | 12-15 years |
| Films & Sheets | $1M-$10M | 5-8% | 10-15 years |
| Paints & Coatings | $300K-$3M | 3-5% | 10-15 years |
| Cleaning Products | $200K-$2M | 3-5% | 10-12 years |
| Personal Care | $300K-$3M | 4-6% | 10-12 years |
| Specialty Chemicals | $500K-$5M | 4-6% | 10-15 years |

### Key Equipment Costs

**Plastics Processing:**

| Equipment | Cost Range | Capacity |
|-----------|------------|----------|
| Injection Molding Machine (small) | $50K-$150K | 50-150 tons |
| Injection Molding Machine (medium) | $150K-$400K | 150-500 tons |
| Injection Molding Machine (large) | $400K-$1M+ | 500-2000 tons |
| Blow Molding Machine | $100K-$500K | Variable |
| Extrusion Line (pipes) | $200K-$800K | Diameter-dependent |
| Extrusion Line (film) | $300K-$2M | Width/speed dependent |
| Molds (injection) | $5K-$100K+ | Per product |
| Chillers, Conveyors, Auxiliaries | $50K-$200K | Per line |

**Formulated Products:**

| Equipment | Cost Range | Notes |
|-----------|------------|-------|
| Mixing Vessels | $10K-$100K | Size-dependent |
| Dispersers | $20K-$80K | Paint production |
| Filling Lines | $50K-$500K | Automation level |
| Testing Equipment | $30K-$150K | QC laboratory |
| Packaging Lines | $30K-$200K | Automation level |

## 2.6 Valuation Multiples

### Revenue & EBITDA Multiples

| Subsector | Revenue Multiple | EBITDA Multiple |
|-----------|------------------|-----------------|
| Plastic Packaging | 0.5-1.0x | 4-7x |
| Pipes & Profiles | 0.6-1.2x | 5-8x |
| Films & Sheets | 0.4-0.8x | 4-6x |
| Industrial Plastics | 0.6-1.2x | 5-8x |
| Paints & Coatings | 0.8-1.5x | 6-9x |
| Cleaning Products | 0.7-1.3x | 5-8x |
| Personal Care/Cosmetics | 1.0-2.5x | 7-12x |
| Specialty Chemicals | 0.8-1.5x | 6-9x |

### Valuation Premium Factors

**Positive:**
- Strong brand recognition
- Diversified customer base
- Technical differentiation/IP
- Modern equipment
- Certifications (ISO, HACCP, Halal)
- Sustainability capabilities (recycled)
- Export revenue
- Recurring/contract customers

**Discount Factors:**
- Customer concentration (>30% single)
- Old equipment/technology
- Commodity products only
- High raw material exposure
- Environmental liabilities
- Regulatory compliance gaps

---

# Dimension 3: Operational KPIs

## 3.1 Production Efficiency Metrics

### Overall Equipment Effectiveness (OEE)

| Subsector | Median OEE | Target OEE | World-Class |
|-----------|------------|------------|-------------|
| Injection Molding | 65% | 78% | 85%+ |
| Blow Molding | 60% | 72% | 80%+ |
| Extrusion (Pipes) | 70% | 80% | 88%+ |
| Extrusion (Film) | 65% | 75% | 85%+ |
| Paint Production | 55% | 68% | 75%+ |
| Cleaning Products | 60% | 72% | 80%+ |

### OEE Components

| Component | Target | Notes |
|-----------|--------|-------|
| **Availability** | >90% | Minimize downtime |
| **Performance** | >90% | Run at design speed |
| **Quality** | >98% | First-pass yield |

### Capacity Utilization

| Metric | Target | Warning | Notes |
|--------|--------|---------|-------|
| Machine Utilization | 75-85% | <65% | Allow maintenance buffer |
| Shift Efficiency | >90% | <80% | Actual vs. planned output |
| Changeover Time | Minimize | >15% of time | SMED principles |

## 3.2 Quality Metrics

### Plastics Quality KPIs

| Metric | Definition | Target | Warning |
|--------|------------|--------|---------|
| **First Pass Yield (FPY)** | Good parts / total parts | >97% | <94% |
| **Scrap Rate** | Rejected / total produced | <3% | >5% |
| **Regrind Usage** | % recycled material used | Optimized | Per specification |
| **Customer Complaints** | Complaints per 1M units | <50 | >100 |
| **Customer Returns** | % of sales returned | <0.5% | >1% |
| **Dimensional Accuracy** | Within tolerance | >99% | <97% |

### Formulated Products Quality KPIs

| Metric | Definition | Target | Warning |
|--------|------------|--------|---------|
| **Batch Conformance** | Batches meeting spec | >99% | <97% |
| **Color Match Accuracy** | Delta E value | <1.0 | >2.0 |
| **Stability Testing** | Pass rate | 100% | Any failure |
| **Shelf Life Achievement** | Products meeting shelf life | 100% | <98% |
| **Viscosity Consistency** | Within spec range | >99% | <97% |
| **Customer Complaints** | Per 1000 units sold | <5 | >10 |

### Testing Requirements by Product

| Product | Key Tests | Frequency |
|---------|-----------|-----------|
| **Plastic Packaging** | Burst, drop, seal strength | Per lot |
| **Pipes** | Pressure test, dimensions | Per batch/lot |
| **Paints** | Viscosity, color, coverage | Per batch |
| **Detergents** | pH, active content, foaming | Per batch |
| **Personal Care** | pH, viscosity, microbial | Per batch |
| **Adhesives** | Bond strength, set time | Per batch |

## 3.3 Productivity Metrics

| Metric | Definition | Good | Top Quartile |
|--------|------------|------|--------------|
| **Revenue per Employee** | Total revenue / headcount | $60,000 | $90,000+ |
| **Output per Machine Hour** | Production volume / hours | Maximize | +20% vs. plan |
| **Labor Productivity** | Units per labor hour | Benchmark +10% | +25% vs. benchmark |
| **Energy per Unit** | kWh per kg produced | Minimize | -15% vs. baseline |
| **Material Yield** | Output weight / input weight | >95% | >98% |

### Productivity by Process

| Process | Typical Output | Benchmark |
|---------|----------------|-----------|
| Injection Molding | 100-500 parts/hour | Machine/mold dependent |
| Blow Molding | 200-2000 bottles/hour | Size dependent |
| Pipe Extrusion | 200-1000 kg/hour | Line dependent |
| Film Extrusion | 300-1500 kg/hour | Line/gauge dependent |
| Paint Mixing | 2-10 batches/shift | Size dependent |
| Filling (Liquids) | 2000-15000 units/hour | Automation dependent |

## 3.4 Inventory & Supply Chain KPIs

| Metric | Target | Warning | Notes |
|--------|--------|---------|-------|
| **Raw Material Days** | 30-45 | >60 | Cash flow impact |
| **WIP Days** | 3-7 | >14 | Process flow |
| **Finished Goods Days** | 15-30 | >45 | Demand planning |
| **Inventory Turnover** | 6-10x | <4x | Annual |
| **Stockout Rate** | <2% | >5% | Lost sales |
| **On-Time Delivery (OTIF)** | >95% | <90% | Customer service |

### Lead Time Benchmarks

| Product Type | Order to Delivery | Best Practice |
|--------------|-------------------|---------------|
| Stock items | 1-3 days | Same day |
| Custom packaging | 2-4 weeks | 1-2 weeks |
| Custom compounds | 1-2 weeks | 5-7 days |
| New mold/tooling | 4-12 weeks | Minimize |

## 3.5 Maintenance & Reliability

| Metric | Target | Warning |
|--------|--------|---------|
| **Planned Maintenance %** | >80% | <60% |
| **Unplanned Downtime** | <5% | >10% |
| **MTBF (Mean Time Between Failures)** | Increasing | Decreasing |
| **MTTR (Mean Time To Repair)** | <4 hours | >8 hours |
| **Maintenance Cost (% of Asset Value)** | 3-5% | >8% |
| **Spare Parts Availability** | >95% | <85% |

### Maintenance Strategy by Equipment Age

| Equipment Age | Strategy | Focus |
|---------------|----------|-------|
| 0-5 years | Preventive | Maximize OEE |
| 5-10 years | Predictive + Preventive | Monitor closely |
| 10-15 years | Proactive replacement planning | Budget for upgrade |
| 15+ years | Evaluate replacement ROI | Consider modernization |

## 3.6 Safety & Environmental KPIs

### Safety Metrics

| Metric | Target | Industry Average |
|--------|--------|------------------|
| **LTIF (Lost Time Injury Frequency)** | <2.0 | 3.5 |
| **TRIR (Total Recordable Incident Rate)** | <4.0 | 6.0 |
| **Near Miss Reporting** | >10/month | Culture dependent |
| **Safety Training Hours** | >16/year | 12 |

### Environmental Metrics

| Metric | Target | Notes |
|--------|--------|-------|
| **Energy Intensity** | kWh/kg decreasing | Track and reduce |
| **Water Usage** | L/kg minimized | Cooling, cleaning |
| **Waste to Landfill** | <5% | Recycling priority |
| **Scrap Recycling Rate** | >90% | Regrind usage |
| **VOC Emissions** | Within limits | Paints, solvents |
| **Effluent Quality** | Compliant | Treatment required |

---

# Dimension 4: Regulatory Landscape

## 4.1 Business Licensing Requirements

### Manufacturing Licenses

| License | Issuing Authority | Countries | Validity | Cost |
|---------|-------------------|-----------|----------|------|
| **Industrial License** | Industry Ministry | All MENA | 5 years | $500-$5,000 |
| **Environmental Permit** | Environment Authority | All MENA | 2-3 years | $200-$2,000 |
| **Municipality Permit** | Local Municipality | All MENA | 1 year | $100-$500 |
| **Civil Defense Permit** | Civil Defense | All MENA | 1 year | $100-$500 |
| **Chemical Handling License** | Varies | Where applicable | Variable | Variable |

### Special Permits (Product-Specific)

| Product Category | Additional Requirements |
|------------------|------------------------|
| Food Contact Packaging | Food authority approval |
| Cosmetics | Health/drug authority registration |
| Pesticides/Agrochemicals | Agriculture ministry registration |
| Cleaning Products (Antimicrobial) | Health authority registration |
| Water Treatment Chemicals | Water authority approval |

## 4.2 Product Standards & Certifications

### International Standards

| Standard | Application | Markets |
|----------|-------------|---------|
| **ISO 9001** | Quality management system | All |
| **ISO 14001** | Environmental management | Export, major customers |
| **ISO 22000 / FSSC 22000** | Food safety (packaging) | Food industry customers |
| **BRC Packaging** | Food packaging standard | UK, export |
| **FDA Compliance** | Food contact materials | US export |

### Regional Standards

| Standard Body | Countries | Coverage |
|---------------|-----------|----------|
| **SASO** | Saudi Arabia | All products |
| **ESMA** | UAE | All products |
| **EOS** | Egypt | All products |
| **GSO** | GCC | Regional harmonization |

### Product-Specific Certifications

**Plastic Packaging (Food Contact):**

| Requirement | Standard | Markets |
|-------------|----------|---------|
| Migration limits | EU 10/2011, FDA CFR 177 | EU, US |
| Overall migration | <10 mg/dm² | EU |
| Specific migration | Substance-dependent | EU, US |
| Food contact declaration | Compliance statement | All |

**Pipes & Fittings:**

| Requirement | Standard | Application |
|-------------|----------|-------------|
| Pressure rating | ISO 4427 (HDPE), ISO 1452 (PVC) | Water supply |
| Dimensions | National/international | All |
| Material certification | MRS rating | Pressure applications |
| Third-party testing | Required | Infrastructure projects |

**Paints & Coatings:**

| Requirement | Standard | Notes |
|-------------|----------|-------|
| VOC content | Variable by region | EU strictest |
| Lead content | Prohibited | All markets |
| Heavy metals | Limited | All markets |
| Performance | National standards | Application-specific |

**Cleaning Products:**

| Requirement | Standard | Markets |
|-------------|----------|---------|
| Labeling | CLP (EU), local | All |
| Active ingredient disclosure | Required | Most markets |
| Antimicrobial claims | Registration required | All |
| Biodegradability | Growing requirement | EU, premium |

**Personal Care/Cosmetics:**

| Requirement | Standard | Markets |
|-------------|----------|---------|
| Product registration | Required | All MENA |
| Halal certification | Important | MENA, Muslim markets |
| Ingredient listing (INCI) | Required | All |
| Safety assessment | Required | Most markets |
| GMP | ISO 22716 | Expected |

## 4.3 Environmental Regulations

### Emissions & Discharge

| Regulation Area | Requirements | Enforcement |
|-----------------|--------------|-------------|
| Air emissions | VOC limits (paints, solvents) | Permit conditions |
| Water discharge | Treatment required | Pre-discharge limits |
| Hazardous waste | Licensed disposal | Manifest tracking |
| General waste | Segregation encouraged | Variable enforcement |

### Extended Producer Responsibility (EPR)

| Country | Status | Scope |
|---------|--------|-------|
| **Saudi Arabia** | Emerging | Plastic packaging |
| **UAE** | Emerging | Plastic packaging |
| **Egypt** | Early discussion | Packaging |
| **EU Export** | Active | All packaging |

### Sustainability Requirements (Growing)

| Trend | Driver | Impact |
|-------|--------|--------|
| Recycled content mandates | Regulations, brands | Investment required |
| Single-use plastic restrictions | Environmental | Product redesign |
| Bio-based materials | Consumer preference | R&D investment |
| Carbon footprint reporting | Corporate customers | Data systems |

## 4.4 Chemical Safety & Handling

### GHS (Globally Harmonized System)

| Requirement | Application |
|-------------|-------------|
| Classification | All hazardous chemicals |
| Labeling | Pictograms, signal words |
| Safety Data Sheets (SDS) | All hazardous products |
| Training | Workers handling chemicals |

### Storage Requirements

| Chemical Class | Requirements |
|----------------|--------------|
| Flammable liquids | Fire-rated storage, ventilation |
| Oxidizers | Segregated storage |
| Corrosives | Containment, PPE |
| Toxic substances | Restricted access, inventory control |

### Transport Regulations

| Mode | Regulation | Requirements |
|------|------------|--------------|
| Road | ADR equivalent | Placarding, documentation |
| Sea | IMDG Code | Proper packaging, declaration |
| Air | IATA DGR | Restrictions apply |

## 4.5 Labor & Safety Regulations

### Chemical Industry Safety Requirements

| Area | Requirement |
|------|-------------|
| Personal Protective Equipment | Appropriate to hazard |
| Training | Hazard communication, handling |
| Medical surveillance | For exposure-prone roles |
| Emergency procedures | Spill response, evacuation |
| Ventilation | Engineering controls |
| Fire protection | Suppression systems |

### Occupational Exposure Limits

| Reference | Coverage |
|-----------|----------|
| OSHA PELs | Commonly referenced |
| ACGIH TLVs | Best practice reference |
| Local standards | Country-specific |

---

# Dimension 5: Competitive Dynamics

## 5.1 Market Structure

### Overall Market Characteristics

| Characteristic | Assessment |
|----------------|------------|
| **Structure Type** | Oligopoly (basic chemicals), Fragmented (downstream) |
| **CR4 (Plastics Conversion)** | 15-25% |
| **CR4 (Paints)** | 30-40% |
| **CR4 (Cleaning Products)** | 35-50% |
| **Competition Type** | Mix of price and differentiation |

### Competitive Landscape by Segment

| Segment | Local SMEs | Regional Large | Multinationals | Competition |
|---------|------------|----------------|----------------|-------------|
| Basic Petrochemicals | None | Dominant | Partners | Low (SME) |
| Plastic Packaging | Many | Several | Few | Very High |
| Pipes & Profiles | Many | Several | Few | High |
| Paints (Architectural) | Many | Few | Present | High |
| Paints (Industrial) | Few | Few | Dominant | Medium |
| Cleaning (Household) | Many | Few | Dominant | Very High |
| Personal Care | Many | Few | Dominant | Very High |
| Specialty Chemicals | Few | Few | Present | Medium |

### Key Competitor Categories

| Category | Examples | Characteristics |
|----------|----------|-----------------|
| **Global Multinationals** | Jotun, AkzoNobel, P&G, Henkel | Brand, R&D, global supply |
| **Regional Leaders** | NAPCO, SABIC affiliates, local champions | Scale, distribution, relationships |
| **Local SMEs** | Many | Flexibility, cost, local service |
| **Import Competition** | Asian manufacturers | Price, especially commodity |

## 5.2 Porter's Five Forces Analysis

### Overall Industry Attractiveness Score: 3.0/5 (Moderate)

### Force 1: Competitive Rivalry
**Intensity: HIGH (4/5)**

| Driver | Impact |
|--------|--------|
| Many players in conversion | Price pressure |
| Commodity product segments | Margin compression |
| Overcapacity (some segments) | Aggressive pricing |
| Multinational presence | Technology/brand gap |
| Low switching costs | Customer mobility |

**Implication for SMEs:** Differentiate through specialization, service, or cost leadership in niche segments.

### Force 2: Threat of New Entrants
**Level: MEDIUM (3/5)**

| Barrier | Height | Description |
|---------|--------|-------------|
| Capital Requirements | Medium | $0.5M-$5M for basic setup |
| Technical Know-how | Medium | Available but learning curve |
| Supplier Relationships | Medium | Polymer access relatively open |
| Distribution Network | Medium-High | Critical for consumer products |
| Brand Recognition | Medium-High | Consumer segments |
| Regulatory | Low-Medium | Permits obtainable |

**Implication for SMEs:** Build customer relationships and technical capabilities as barriers.

### Force 3: Threat of Substitutes
**Level: MEDIUM (3/5)**

| Substitute | Threat Level | Notes |
|------------|--------------|-------|
| Alternative materials | Medium | Glass, paper, metal |
| Bio-plastics | Growing | Niche, cost premium |
| Recycled plastics | Growing | Quality considerations |
| Concentrate vs. ready-to-use | Varies | Cleaning products |
| In-house production | Low | Most customers outsource |

**Implication for SMEs:** Monitor sustainability trends, consider recycled content capabilities.

### Force 4: Supplier Power
**Level: HIGH (4/5)**

| Driver | Impact |
|--------|--------|
| Polymer producer concentration | Price dependency |
| Oil/gas price linkage | Cost volatility |
| Global supply/demand cycles | Price swings |
| Local supply limitations | Limited negotiating power |
| Quality differentiation | Limited alternatives |

**Implication for SMEs:** Build relationships with multiple suppliers, consider strategic inventory, explore price pass-through mechanisms.

### Force 5: Buyer Power
**Level: MEDIUM-HIGH (3.5/5)**

| Driver | Impact |
|--------|--------|
| Large FMCG buyers | Negotiating power |
| Specification lock-in | Some protection |
| Easy to switch (commodity) | Price pressure |
| Quality requirements | Value opportunity |
| Import alternatives | Benchmark pressure |

**Implication for SMEs:** Develop technical value-add, build switching costs through quality and service.

## 5.3 Competitive Strategies for SMEs

### Successful SME Strategies

| Strategy | Description | Success Factors | Best Fit |
|----------|-------------|-----------------|----------|
| **Specialization** | Focus on niche products | Deep expertise, specifications | Industrial plastics, specialty |
| **Customer Intimacy** | Superior service, responsiveness | Flexibility, relationships | All segments |
| **Local Champion** | Dominate local/regional market | Distribution, brand | Consumer products |
| **Contract Manufacturing** | Produce for brands/MNCs | Quality, reliability, cost | Packaging, personal care |
| **Technical Leadership** | Solve customer problems | R&D, application expertise | Adhesives, specialty |
| **Cost Leadership** | Lowest cost producer | Efficiency, scale | Commodity segments |

### Specialization Examples

| Niche | Focus Area | Competitive Advantage |
|-------|------------|----------------------|
| Pharmaceutical packaging | GMP compliance | Quality systems |
| Automotive parts | OEM specifications | Technical capability |
| Agricultural irrigation | Local service | Distribution, support |
| Industrial coatings | Application expertise | Technical service |
| Halal personal care | Certification | Market positioning |
| Green/recycled products | Sustainability | Brand differentiation |

## 5.4 Key Success Factors

| Factor | Importance | Typical SME Performance | Improvement Path |
|--------|------------|-------------------------|------------------|
| **Raw Material Management** | Critical | Variable | Supplier relationships, hedging |
| **Quality Consistency** | Critical | Variable | Systems, training |
| **Customer Relationships** | High | Strong locally | Expansion, service |
| **Production Efficiency** | High | Below potential | OEE focus, lean |
| **Innovation/Development** | Medium-High | Weak | R&D investment |
| **Distribution** | High (consumer) | Variable | Network building |
| **Brand Building** | Medium-High | Weak | Marketing investment |
| **Sustainability** | Growing | Very weak | Strategic priority |

## 5.5 Market Trends

| Trend | Impact | Timeline | SME Opportunity |
|-------|--------|----------|-----------------|
| **Sustainability Pressure** | Mixed | Accelerating | Recycled content, bio-based |
| **E-commerce Packaging** | Positive | Ongoing | Flexible packaging, protection |
| **Local Content Mandates** | Positive | Growing | Import substitution |
| **Halal Certification** | Positive | Ongoing | Market differentiation |
| **Premium Consumer Products** | Positive | Growing | Margin opportunity |
| **Automation** | Challenge | Ongoing | Productivity improvement |
| **Plastic Restrictions** | Negative | Growing | Product innovation |
| **Food Safety Standards** | Mixed | Growing | Compliance investment |

### MENA-Specific Opportunities

| Opportunity | Description | Markets | Potential |
|-------------|-------------|---------|-----------|
| **Petrochemical Advantage** | Feedstock proximity | GCC | High |
| **Infrastructure Investment** | Pipes, construction chemicals | Saudi, Egypt | High |
| **Population Growth** | Consumer products demand | All | High |
| **Import Substitution** | Local manufacturing incentives | Saudi, UAE | High |
| **Africa Gateway** | Manufacturing for export | Egypt, Morocco | Medium |
| **Giga Projects Supply** | Construction materials | Saudi | High |

---

*Continued in Part 2: Dimensions 6-11*
# RootRise Sector Knowledge Pack
# Chemicals & Plastics (Part 2)
## Dimensions 6-11

---

# Dimension 6: Digital Maturity Patterns

## 6.1 Sector Digital Maturity

### Current State Assessment

| Metric | Value |
|--------|-------|
| **Average Digital Maturity Score** | 35/100 |
| **Comparison to Global Leaders** | Significantly behind |

**Note:** Chemicals and plastics manufacturing in MENA varies widely. Large petrochemical companies are highly digitized, while downstream SMEs typically lag significantly.

### Maturity Distribution

| Level | Description | % of MENA SMEs |
|-------|-------------|----------------|
| Level 1 | Manual/Paper-based | 30% |
| Level 2 | Basic Digital (spreadsheets, email) | 40% |
| Level 3 | Connected (some integrated systems) | 22% |
| Level 4 | Advanced (data-driven operations) | 7% |
| Level 5 | Transformative (Industry 4.0) | 1% |

### Maturity by Subsector

| Subsector | Score | Notes |
|-----------|-------|-------|
| Plastic Packaging (FMCG-linked) | 42/100 | Customer requirements drive adoption |
| Plastic Pipes (industrial) | 38/100 | QC systems more common |
| Films & Sheets | 35/100 | Process monitoring common |
| Paints & Coatings | 40/100 | Formulation software, color matching |
| Cleaning Products | 35/100 | Batch tracking improving |
| Personal Care | 38/100 | Regulatory compliance driving |
| Specialty Chemicals | 45/100 | Technical requirements |

## 6.2 Core Systems Adoption

### Administrative Systems

| System | Adoption | Leading Solutions | Cost Range |
|--------|----------|-------------------|------------|
| **Accounting** | 75% | QuickBooks, SAP B1, local | $1K-$20K/yr |
| **Inventory Management** | 50% | ERP modules, standalone | $2K-$30K/yr |
| **Basic ERP** | 30% | SAP B1, Odoo, local | $10K-$100K+ |
| **Document Management** | 35% | SharePoint, Google | $0-$5K/yr |
| **HR/Payroll** | 45% | Local solutions | $1K-$10K/yr |

### Manufacturing Systems

| System | Adoption | Leading Solutions | Cost Range |
|--------|----------|-------------------|------------|
| **Production Planning** | 25% | ERP modules, MES | $5K-$50K |
| **Quality Management (QMS)** | 30% | Dedicated QMS, ERP | $5K-$30K |
| **Batch Tracking** | 40% | ERP, manual logs | Variable |
| **Recipe/Formulation Management** | 35% | Specialized software | $5K-$50K |
| **SCADA/Process Control** | 20% | Various industrial | $10K-$100K |
| **Maintenance (CMMS)** | 20% | Fiix, UpKeep | $2K-$15K/yr |
| **Laboratory Information (LIMS)** | 15% | Specialized | $10K-$50K |

### Industry-Specific Software

| Application | Adoption | Purpose |
|-------------|----------|---------|
| **Color Matching (Paints)** | 60% | Spectrophotometry, formulation |
| **Mold Flow Analysis** | 15% | Injection molding simulation |
| **Extrusion Control** | 30% | Line monitoring |
| **Regulatory Compliance** | 25% | SDS management, registration |
| **Packaging Design (CAD)** | 40% | Product development |

## 6.3 Functional Digitization Gaps

| Function | Current Score | Best Practice | Gap | Priority |
|----------|---------------|---------------|-----|----------|
| **Recipe/Formulation Management** | 35% | 90% | 55% | High |
| **Batch Traceability** | 40% | 95% | 55% | Critical |
| **Quality Control/Testing** | 35% | 85% | 50% | High |
| **Production Scheduling** | 30% | 85% | 55% | High |
| **Inventory Management** | 40% | 85% | 45% | High |
| **Raw Material Tracking** | 35% | 90% | 55% | High |
| **Equipment Monitoring** | 25% | 80% | 55% | Medium |
| **Energy Management** | 20% | 75% | 55% | Medium |
| **Regulatory Compliance** | 35% | 90% | 55% | High |
| **Customer Orders/CRM** | 40% | 85% | 45% | Medium |

## 6.4 Automation Opportunities

### High-Impact Automation Areas

| Process | Current State | Automation Potential | Impact | Technologies |
|---------|---------------|---------------------|--------|--------------|
| **Material Weighing/Dosing** | Manual/Semi | 90% automatable | High | Automated dosing, gravimetric |
| **Process Monitoring** | Limited | 85% automatable | High | SCADA, sensors |
| **Quality Testing** | Manual | 60% automatable | High | Online analyzers |
| **Batch Recording** | Paper/Excel | 95% automatable | High | MES, batch systems |
| **Inventory Counting** | Manual | 85% automatable | Medium | Barcode/RFID |
| **Packaging/Palletizing** | Semi-automatic | 80% automatable | Medium | Robotics |
| **Predictive Maintenance** | None | 50% feasible | Medium | IoT sensors |

### Industry 4.0 Technologies

| Technology | Maturity | MENA Adoption | Potential Impact |
|------------|----------|---------------|------------------|
| **Process Sensors (IoT)** | Mature | 15% | High (quality, efficiency) |
| **Real-time Quality Monitoring** | Growing | 10% | High (defect reduction) |
| **Predictive Maintenance** | Growing | 5% | Medium (downtime reduction) |
| **Digital Twin** | Emerging | <2% | Future potential |
| **AI/ML for Optimization** | Emerging | <5% | High (process optimization) |
| **Robotics (Packaging)** | Mature | 10% | Medium (labor, consistency) |

## 6.5 Data & Analytics

### Analytics Adoption

| Capability | Adoption | Tools | Notes |
|------------|----------|-------|-------|
| Basic production reports | 60% | Excel, ERP | Standard |
| Quality trend analysis | 35% | Excel, QMS | Growing |
| OEE monitoring | 25% | MES, manual | Underutilized |
| Inventory analytics | 30% | ERP, Excel | Basic |
| Customer analytics | 20% | CRM, Excel | Limited |
| Predictive analytics | 5% | Specialized | Rare |

### Data Challenges

| Challenge | Impact | Solution Approach |
|-----------|--------|-------------------|
| Manual data entry | Errors, delays | Automation, sensors |
| Data silos | No visibility | Integration, ERP |
| Poor data quality | Wrong decisions | Validation, processes |
| Limited analysis skills | Underutilized data | Training, tools |
| No real-time access | Reactive management | Connected systems |

## 6.6 Digital Transformation Roadmap

### Phase 1: Foundation (0-12 months)
**Investment:** $15,000-$40,000

| Initiative | Outcome |
|------------|---------|
| ERP implementation or upgrade | Core data foundation |
| Digital batch records | Traceability, compliance |
| Basic quality system | Defect tracking |
| Inventory barcoding | Accuracy improvement |
| Production reporting | Visibility |

### Phase 2: Integration (12-24 months)
**Investment:** $30,000-$80,000

| Initiative | Outcome |
|------------|---------|
| MES or production module | Real-time monitoring |
| Quality management system | ISO support |
| Recipe management system | Formulation control |
| Equipment monitoring (key assets) | OEE improvement |
| Customer order integration | Service improvement |

### Phase 3: Optimization (24-48 months)
**Investment:** $50,000-$150,000

| Initiative | Outcome |
|------------|---------|
| Advanced process control | Consistency, efficiency |
| LIMS (if applicable) | Lab efficiency |
| Predictive maintenance | Reduced downtime |
| Advanced analytics/BI | Data-driven decisions |
| Automation projects | Labor efficiency |

---

# Dimension 7: Workforce Norms

## 7.1 Workforce Composition

### Headcount by Revenue Tier

| Revenue Tier (USD) | Total Employees | Production | Admin/Support |
|-------------------|-----------------|------------|---------------|
| < $500,000 | 15 | 10 | 5 |
| $500,000 - $2,000,000 | 40 | 30 | 10 |
| $2,000,000 - $5,000,000 | 80 | 60 | 20 |
| $5,000,000 - $15,000,000 | 150 | 110 | 40 |
| > $15,000,000 | 300+ | 220+ | 80+ |

### Role Distribution (Typical)

| Category | % of Workforce | Roles |
|----------|----------------|-------|
| **Management** | 5% | GM, Plant Manager, Department Heads |
| **Technical/Engineering** | 10% | Engineers, QC, R&D, Maintenance |
| **Administrative** | 10% | Finance, HR, Procurement, Admin |
| **Production Supervisors** | 8% | Shift supervisors, Line leaders |
| **Skilled Operators** | 35% | Machine operators, Technicians |
| **Semi-Skilled Workers** | 22% | Helpers, Material handlers |
| **Warehouse/Logistics** | 10% | Store, Shipping, Drivers |

### Role Distribution by Subsector

| Role | Plastics | Paints/Coatings | Consumer Products |
|------|----------|-----------------|-------------------|
| Technical/R&D | 8% | 12% | 10% |
| Production | 70% | 60% | 55% |
| Sales/Marketing | 8% | 12% | 18% |
| Admin | 14% | 16% | 17% |

## 7.2 Compensation Benchmarks

### Management & Professional (Monthly USD)

| Role | Egypt | Jordan | Saudi Arabia | UAE |
|------|-------|--------|--------------|-----|
| **Plant Manager** | $2,000-$4,000 | $2,500-$5,000 | $7,000-$15,000 | $8,000-$18,000 |
| **Production Manager** | $1,200-$2,500 | $1,500-$3,000 | $5,000-$10,000 | $6,000-$12,000 |
| **Quality Manager** | $1,000-$2,000 | $1,200-$2,500 | $4,000-$8,000 | $5,000-$10,000 |
| **R&D Manager** | $1,200-$2,500 | $1,500-$3,000 | $5,000-$10,000 | $6,000-$12,000 |
| **Maintenance Manager** | $800-$1,800 | $1,000-$2,200 | $4,000-$8,000 | $5,000-$10,000 |
| **Sales Manager** | $1,000-$2,200 | $1,200-$2,800 | $5,000-$10,000 | $6,000-$12,000 |

### Technical & Engineering (Monthly USD)

| Role | Egypt | Jordan | Saudi Arabia | UAE |
|------|-------|--------|--------------|-----|
| **Process Engineer** | $600-$1,200 | $700-$1,400 | $3,000-$6,000 | $3,500-$7,000 |
| **Quality Engineer** | $500-$1,000 | $600-$1,200 | $2,500-$5,000 | $3,000-$6,000 |
| **Maintenance Engineer** | $500-$1,100 | $600-$1,300 | $2,500-$5,500 | $3,000-$6,500 |
| **R&D Chemist** | $600-$1,200 | $700-$1,400 | $3,000-$6,000 | $3,500-$7,000 |
| **Lab Technician** | $300-$600 | $400-$700 | $1,500-$3,000 | $2,000-$4,000 |
| **QC Inspector** | $250-$500 | $350-$650 | $1,200-$2,500 | $1,500-$3,000 |

### Production & Operations (Monthly USD)

| Role | Egypt | Jordan | Saudi Arabia | UAE |
|------|-------|--------|--------------|-----|
| **Shift Supervisor** | $400-$800 | $500-$900 | $2,000-$3,500 | $2,500-$4,500 |
| **Machine Operator (Skilled)** | $250-$450 | $300-$550 | $1,200-$2,200 | $1,500-$2,800 |
| **Blending/Mixing Operator** | $250-$450 | $300-$550 | $1,200-$2,200 | $1,500-$2,800 |
| **Injection Molding Operator** | $280-$500 | $350-$600 | $1,300-$2,400 | $1,600-$3,000 |
| **Extrusion Operator** | $280-$500 | $350-$600 | $1,300-$2,400 | $1,600-$3,000 |
| **Filling Machine Operator** | $220-$400 | $280-$500 | $1,100-$2,000 | $1,400-$2,500 |
| **Helper/General Worker** | $150-$280 | $200-$350 | $600-$1,000 | $800-$1,300 |

### Compensation Structure

| Component | Manufacturing | Notes |
|-----------|---------------|-------|
| Basic Salary | 65-75% | Fixed monthly |
| Housing | 15-20% | Or provided/camp |
| Transport | 5-8% | Or provided |
| Production Bonus | 5-10% | Output-based |
| Shift Allowance | Variable | Night/rotating shifts |

## 7.3 Skills Landscape

### Critical Skills Assessment

| Skill | Importance | Availability | Gap Severity |
|-------|------------|--------------|--------------|
| **Process Engineering** | Critical | Limited | High |
| **Quality Management** | Critical | Limited | High |
| **R&D/Formulation** | High | Scarce | High |
| **Machine Operation** | Critical | Adequate | Medium |
| **Maintenance (Mechanical)** | High | Adequate | Medium |
| **Maintenance (Electrical)** | High | Limited | High |
| **PLC/Automation** | High | Scarce | High |
| **Laboratory Testing** | High | Limited | Medium |
| **Regulatory/Compliance** | Medium | Scarce | High |

### Technical Skills by Subsector

| Subsector | Critical Technical Skills |
|-----------|--------------------------|
| **Plastics Processing** | Mold setup, Process parameters, Material handling |
| **Paints/Coatings** | Color matching, Formulation, Application knowledge |
| **Cleaning Products** | Surfactant chemistry, Formulation, Stability testing |
| **Personal Care** | GMP, Cosmetic chemistry, Regulatory |
| **Specialty Chemicals** | Application engineering, Technical sales |

### Skill Development Priorities

| Skill Area | Method | Investment | Timeline |
|------------|--------|------------|----------|
| Machine operation | On-job training | Low | 2-6 months |
| Quality systems | External training + practice | Medium | 6-12 months |
| Process optimization | Training + mentoring | Medium | 6-12 months |
| Automation/PLC | External courses | High | 6-12 months |
| R&D/formulation | Education + experience | High | 2-5 years |

## 7.4 Labor Dynamics

| Metric | Chemicals/Plastics Average | Notes |
|--------|---------------------------|-------|
| **Turnover (Operators)** | 20-30% | Shift work impact |
| **Turnover (Technical)** | 15-25% | Competition for skills |
| **Absenteeism** | 5-8% | Better than construction |
| **Training Investment** | $100-$300/employee/year | Variable |
| **Shift Pattern** | 2-3 shifts common | Continuous operations |

### Retention Factors

| Factor | Impact Level | Notes |
|--------|--------------|-------|
| Compensation competitiveness | High | Market benchmarking needed |
| Working conditions | High | Safety, environment |
| Career development | Medium | Growth opportunities |
| Shift scheduling | Medium | Work-life balance |
| Company stability | High | Job security |
| Benefits package | Medium | Health, transport |

### Recruitment Challenges

| Challenge | Description | Approach |
|-----------|-------------|----------|
| Technical skills shortage | Engineering, R&D, automation | Training investment, partnerships |
| Shift work acceptance | Not everyone wants shifts | Premium pay, rotation |
| Industry perception | Chemical = hazardous | Safety culture, communication |
| Competition from O&G | Higher paying sector | Non-monetary benefits |
| Geographic location | Factory locations | Transport provision |

## 7.5 Organizational Structure

### Typical Manufacturing Organization (Medium SME)

```
General Manager
├── Production Manager
│   ├── Shift Supervisors
│   │   └── Operators, Workers
│   ├── Warehouse/Stores
│   └── Maintenance
│       └── Technicians
├── Quality Manager
│   ├── QC/QA Team
│   └── Laboratory
├── Technical/R&D Manager (if applicable)
│   └── Chemists, Technicians
├── Sales/Commercial Manager
│   ├── Sales Team
│   └── Customer Service
├── Finance Manager
│   ├── Accounting
│   └── Costing
└── HR/Admin Manager
    ├── HR
    └── Admin, Security, HSE
```

### Span of Control

| Level | Typical Ratio |
|-------|---------------|
| Production Manager : Supervisors | 1 : 3-5 |
| Supervisor : Operators | 1 : 10-20 |
| QC Manager : Inspectors | 1 : 3-6 |
| Maintenance Manager : Technicians | 1 : 4-8 |

## 7.6 HR Maturity

| Metric | Value |
|--------|-------|
| **Average HR Maturity Score** | 38/100 |

### Common HR Gaps

| Gap | Prevalence | Impact |
|-----|------------|--------|
| No structured competency framework | 70% | Development gaps |
| Informal recruitment process | 60% | Quality of hires |
| Limited safety training records | 55% | Compliance risk |
| No succession planning | 80% | Business continuity |
| Weak performance management | 65% | Accountability |
| Inadequate training programs | 60% | Skill development |

### Priority HR Improvements

| Initiative | Investment | Outcome |
|------------|------------|---------|
| Safety training program | Medium | Compliance, culture |
| Operator competency certification | Low | Quality, consistency |
| Structured onboarding | Low | Faster productivity |
| Performance review system | Low | Accountability |
| Technical training partnerships | Medium | Skill development |
| Career path definition | Low | Retention |

---

# Dimension 8: Supply Chain Characteristics

## 8.1 Supply Chain Structure

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                CHEMICALS & PLASTICS SUPPLY CHAIN                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  RAW MATERIALS ──► CHEMICALS/POLYMERS ──► PROCESSING ──► DISTRIBUTION       │
│                                                                              │
│  ┌─────────────┐   ┌─────────────────┐   ┌──────────────┐   ┌────────────┐ │
│  │ Petrochemical│   │ Polymer/Resin   │   │ Plastics     │   │ Wholesale  │ │
│  │ Feedstock   │──►│ Producers       │──►│ Converter    │──►│ Distribution││
│  │ (Naphtha,   │   │ (PE, PP, PVC,   │   │ (SME)        │   │            │ │
│  │  Ethane)    │   │  PET, etc.)     │   └──────────────┘   └────────────┘ │
│  └─────────────┘   └─────────────────┘          │                          │
│                           │                     │                          │
│  ┌─────────────┐   ┌──────▼──────────┐   ┌─────▼────────┐   ┌────────────┐ │
│  │ Chemical    │   │ Trading/        │   │ Formulator   │   │ Retail     │ │
│  │ Intermediates│──►│ Distribution    │──►│ (Paints,     │──►│ Consumer   │ │
│  │ (Solvents,  │   │                 │   │  Cleaning,   │   │            │ │
│  │  Additives) │   │                 │   │  Personal)   │   │            │ │
│  └─────────────┘   └─────────────────┘   └──────────────┘   └────────────┘ │
│                                                 │                          │
│                                          ┌──────▼──────────┐               │
│                                          │ Industrial      │               │
│                                          │ Customers       │               │
│                                          │ (B2B)           │               │
│                                          └─────────────────┘               │
└─────────────────────────────────────────────────────────────────────────────┘
```

### Key Input Categories

| Input Category | % of COGS | Supply Structure | Source |
|----------------|-----------|------------------|--------|
| **Polymer Resins** | 40-60% | Oligopoly (few major producers) | GCC, imports |
| **Solvents** | 5-15% | Moderate concentration | Local, imports |
| **Pigments/Colorants** | 5-15% | Fragmented | Imports |
| **Additives** | 3-10% | Fragmented | Mostly imports |
| **Surfactants** | 5-15% | Moderate concentration | Mix local/import |
| **Packaging** | 5-12% | Fragmented | Local |

## 8.2 Polymer Supply Landscape

### Major Polymer Suppliers (MENA)

| Producer | Countries | Products | Market Position |
|----------|-----------|----------|-----------------|
| **SABIC** | Saudi Arabia | PE, PP, PET, PS | Dominant regional |
| **EQUATE** | Kuwait | PE, PEG | Major regional |
| **Borouge** | UAE | PE, PP | Major regional |
| **Qatar Petrochemical** | Qatar | PE, PP | Major regional |
| **Egyptian Petrochemicals** | Egypt | PE, PP, PVC | Local market |
| **Imports** | Asia, EU | All types | Price benchmark |

### Polymer Supply Characteristics

| Aspect | Description |
|--------|-------------|
| **Pricing Mechanism** | Monthly contract price, linked to global indices |
| **Payment Terms** | 30-60 days typical |
| **Minimum Order** | Container load (20-25 MT) typical |
| **Lead Time** | 2-4 weeks (local), 4-8 weeks (import) |
| **Quality Consistency** | Generally good from major producers |
| **Price Volatility** | High (oil-linked, supply/demand) |

### Price Volatility Management

| Strategy | Description | Applicability |
|----------|-------------|---------------|
| **Price escalation clauses** | Pass-through to customers | B2B products |
| **Formula pricing** | Index-linked customer pricing | Large customers |
| **Strategic inventory** | Buy on dips | Working capital dependent |
| **Multiple suppliers** | Reduce dependency | Where possible |
| **Specification flexibility** | Alternative grades | Product-dependent |

## 8.3 Inventory Management

### Inventory Benchmarks

| Category | Typical Days | Target | Warning |
|----------|--------------|--------|---------|
| **Polymer Resins** | 30-45 | 21-30 | >60 |
| **Other Raw Materials** | 21-30 | 14-21 | >45 |
| **Work in Progress** | 3-7 | <5 | >10 |
| **Finished Goods** | 15-30 | 10-20 | >45 |
| **Total Inventory Days** | 60-90 | 45-60 | >100 |

### Inventory Challenges

| Challenge | Impact | Solution |
|-----------|--------|----------|
| Minimum order quantities | Over-inventory of slow movers | Consolidation, negotiation |
| Import lead times | Safety stock needed | Demand planning |
| Price volatility | Buy/hold decisions | Clear policy, limits |
| Multiple grades/colors | SKU proliferation | Rationalization |
| Shelf life (some products) | Expiry risk | FIFO, monitoring |

## 8.4 Logistics & Transportation

### Raw Material Transport

| Material | Mode | Considerations |
|----------|------|----------------|
| Bulk polymers | Container, bulk truck | Container handling |
| Bagged polymers | Truck | Warehouse space |
| Liquids (solvents) | Tank truck, drums | Hazmat regulations |
| Drums/IBCs | Truck | Handling equipment |

### Finished Goods Distribution

| Product Type | Distribution Model |
|--------------|-------------------|
| Industrial plastics | Direct delivery |
| Consumer products | Wholesale/retail distribution |
| Pipes & profiles | Dealer network + direct |
| Paints | Dealer network + retail |
| B2B chemicals | Direct + distributors |

### Logistics Costs

| Product Category | Logistics Cost (% of Sales) |
|------------------|----------------------------|
| Packaging (local) | 3-6% |
| Pipes (heavy) | 5-10% |
| Consumer products | 5-10% (distribution-intensive) |
| Industrial chemicals | 4-8% |
| Export products | 8-15% |

## 8.5 Customer Segments

### B2B Customer Types

| Customer Type | Characteristics | Typical Relationship |
|---------------|-----------------|---------------------|
| **FMCG/Food Companies** | Large volume, specifications | Contract, approval process |
| **Industrial Manufacturers** | Quality focus, technical | Long-term, specifications |
| **Construction/Contractors** | Project-based, price-sensitive | Transactional |
| **Agriculture** | Seasonal, price-sensitive | Seasonal contracts |
| **Export Customers** | Volume, certification | Contracts, L/C payment |

### B2C Distribution

| Channel | Products | Considerations |
|---------|----------|----------------|
| Retail chains | Consumer products, paints | Listing fees, margin |
| Hardware stores | Paints, adhesives | Distribution network |
| Wholesalers | Full range | Credit, volume |
| Direct/Online | Growing | Logistics capability |

### Customer Concentration Risk

| Level | Top Customer % | Risk Level |
|-------|----------------|------------|
| Healthy | <15% | Low |
| Moderate | 15-30% | Medium |
| Concentrated | 30-50% | High |
| Critical | >50% | Very High |

## 8.6 Supply Chain Risks

### Risk Assessment

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Polymer price spike | High | High | Escalation clauses, inventory |
| Supply disruption | Medium | High | Multiple suppliers, inventory |
| Currency fluctuation | High | Medium | Pricing mechanisms |
| Quality issue (input) | Medium | High | Incoming inspection, certification |
| Customer concentration | Medium | High | Diversification |
| Logistics disruption | Low | Medium | Alternative routes |
| Regulatory change | Medium | Medium | Monitoring, compliance |

### Supply Chain Improvement Opportunities

| Opportunity | Investment | Impact |
|-------------|------------|--------|
| Supplier consolidation | Low | Better terms |
| Demand planning improvement | Medium | Inventory reduction |
| Supplier quality programs | Medium | Defect reduction |
| Logistics optimization | Medium | Cost reduction |
| Customer diversification | Low | Risk reduction |

---

# Dimension 9: Export Requirements

## 9.1 Sector Export Profile

### Export Potential by Subsector

| Subsector | Export Potential | Current Export % | Key Markets |
|-----------|------------------|------------------|-------------|
| Plastic Packaging | Medium | 10-20% | Regional, Africa |
| Plastic Pipes | Medium | 15-25% | Regional, Africa |
| Plastic Films | Medium-High | 20-30% | Regional, Africa, EU |
| Industrial Plastics | Medium | 10-20% | Regional |
| Paints/Coatings | Low-Medium | 5-15% | Regional |
| Cleaning Products | Medium | 15-25% | Regional, Africa |
| Personal Care | Medium-High | 15-30% | Regional, Africa |
| Specialty Chemicals | Medium | 15-25% | Regional |

### Primary Export Markets (MENA Origin)

| Market Tier | Markets | Product Focus |
|-------------|---------|---------------|
| **Tier 1 (Regional)** | GCC inter-trade, Jordan, Iraq, Yemen | Full range |
| **Tier 2 (Africa)** | Sudan, Ethiopia, Kenya, Libya, Nigeria | Consumer products |
| **Tier 3 (Europe/US)** | EU, UK, US | Niche, certified products |
| **Tier 4 (Asia)** | South Asia, SE Asia | Limited |

## 9.2 Export Documentation

### Standard Export Documentation

| Document | Purpose | Notes |
|----------|---------|-------|
| **Commercial Invoice** | Customs valuation | Incoterms, prices |
| **Packing List** | Shipment details | Weights, quantities |
| **Certificate of Origin** | Origin verification | Preferential where applicable |
| **Bill of Lading/AWB** | Shipping document | Standard |
| **Certificate of Analysis** | Product quality | Per shipment or batch |
| **Safety Data Sheet (SDS)** | Chemical safety | Required for chemicals |

### Product-Specific Documentation

| Product Category | Additional Requirements |
|------------------|------------------------|
| **Food Contact Packaging** | Food safety compliance certificate, migration testing |
| **Cosmetics/Personal Care** | Product registration (destination), free sale certificate |
| **Chemicals (Hazardous)** | Dangerous goods declaration, transport compliance |
| **Pesticides** | Registration certificate (destination), efficacy data |

## 9.3 Certifications for Export

### Quality & Management Certifications

| Certification | Purpose | Markets | Cost | Timeline |
|---------------|---------|---------|------|----------|
| **ISO 9001** | Quality management | All | $10K-$25K | 4-8 months |
| **ISO 14001** | Environmental | EU, corporate | $12K-$30K | 6-10 months |
| **ISO 45001** | Health & safety | Corporate customers | $10K-$25K | 6-10 months |

### Product Certifications

| Certification | Application | Markets | Cost | Timeline |
|---------------|-------------|---------|------|----------|
| **FSSC 22000 / BRC** | Food contact packaging | Food industry | $15K-$40K | 6-12 months |
| **Halal Certification** | Consumer products | Muslim markets | $2K-$10K | 2-4 months |
| **GMP (ISO 22716)** | Cosmetics | All | $8K-$20K | 4-8 months |
| **REACH Registration** | Chemicals to EU | EU | Variable (€) | 6-18 months |
| **FDA Compliance** | Food contact | US | Variable | 3-12 months |

### Market-Specific Requirements

**European Union:**

| Requirement | Scope | Notes |
|-------------|-------|-------|
| **REACH** | Chemical substances >1 ton/year | Registration required |
| **CLP** | Classification, labeling, packaging | Compliance mandatory |
| **Food Contact** | EU 10/2011 | Migration limits |
| **Cosmetics Regulation** | EC 1223/2009 | Safety assessment, notification |

**GCC/Regional:**

| Requirement | Scope | Notes |
|-------------|-------|-------|
| **GSO Standards** | Product compliance | Technical regulations |
| **SFDA (Saudi)** | Food, cosmetics | Registration required |
| **ESMA (UAE)** | Product standards | Conformity assessment |
| **Halal** | Consumer products | Increasing requirement |

## 9.4 Trade Agreements

### Relevant Trade Agreements

| Agreement | Benefit | Products |
|-----------|---------|----------|
| **GAFTA** | Zero tariffs (Arab League) | All |
| **GCC Common Market** | Free trade within GCC | All |
| **EU Association Agreements** | Preferential tariffs | Most products |
| **COMESA** | Reduced tariffs | Most products |
| **AfCFTA** | Emerging African access | All |

### Rules of Origin Considerations

| Agreement | Typical Requirement |
|-----------|---------------------|
| GAFTA | 40% local value added |
| EU Association | Varies by product, often 60% |
| COMESA | Varies, typically 35-45% |

## 9.5 Export Financing & Payment

### Payment Methods

| Method | Risk Level | Usage |
|--------|------------|-------|
| Letter of Credit | Lowest | New customers, large orders |
| Documentary Collection | Medium | Established customers |
| Open Account | Higher | Trusted relationships |
| Advance Payment | Lowest (seller) | New customers, high risk |

### Export Support Programs

| Country | Programs | Support Type |
|---------|----------|--------------|
| **Egypt** | Export subsidies, GAFI support | Cash incentives, facilitation |
| **Jordan** | Export development | Market access support |
| **Saudi Arabia** | SIDF | Financing |
| **Morocco** | Export promotion | Market access, subsidies |

---

# Dimension 10: Product Standards & Specifications

## 10.1 Plastic Product Standards

### Packaging Standards

| Standard | Application | Markets |
|----------|-------------|---------|
| **ISO 22000 / FSSC 22000** | Food safety management | Food contact |
| **BRC Packaging** | Global standard for packaging | Export |
| **EU 10/2011** | Food contact materials | EU |
| **FDA 21 CFR** | Food contact substances | US |
| **Gulf Standards (GSO)** | Product specifications | GCC |

### Food Contact Requirements

| Test | Standard | Limit |
|------|----------|-------|
| Overall Migration | EU 10/2011 | <10 mg/dm² |
| Specific Migration | Substance-dependent | Per substance |
| Sensory | Various | No off-taste/odor |
| Visual | Various | No contamination |

### Pipe Standards

| Standard | Application | Products |
|----------|-------------|----------|
| **ISO 4427** | HDPE pressure pipes | Water supply |
| **ISO 1452** | PVC pressure pipes | Water supply |
| **ISO 4435** | PVC non-pressure | Sewerage |
| **DIN 8074/8075** | PE pipes | Various |
| **ASTM D2241** | PVC pipes | Pressure |

### Pipe Testing Requirements

| Test | Purpose | Frequency |
|------|---------|-----------|
| Dimensional | Size compliance | Per batch |
| Pressure (burst) | Strength | Per batch/lot |
| Impact (drop) | Impact resistance | Type testing |
| Environmental stress crack | Long-term durability | Type testing |

## 10.2 Paints & Coatings Standards

### Performance Standards

| Standard | Application |
|----------|-------------|
| **ISO 12944** | Corrosion protection |
| **ISO 2409** | Cross-cut adhesion |
| **ISO 2808** | Film thickness |
| **ASTM D523** | Gloss measurement |
| **ASTM D2247** | Humidity resistance |

### Regulatory Requirements

| Requirement | Standard | Markets |
|-------------|----------|---------|
| VOC Content | EU Directive 2004/42 | EU |
| Lead Content | Prohibited | All |
| Heavy Metals | Limited | All |
| Labeling | CLP (EU), local | All |

### Product Specifications (Typical)

| Property | Architectural Paint | Industrial Coating |
|----------|--------------------|--------------------|
| Solids Content | 40-60% | 50-80% |
| VOC | <50 g/L (low VOC) | Variable |
| Viscosity | 80-120 KU | Application-specific |
| Coverage | 8-12 m²/L | Application-specific |
| Drying Time | 1-4 hours | Product-dependent |

## 10.3 Cleaning Products Standards

### Regulatory Framework

| Region | Regulation | Requirements |
|--------|------------|--------------|
| **EU** | Detergent Regulation | Biodegradability, labeling |
| **GCC** | GSO standards | Composition, labeling |
| **US** | EPA, state | Disclosure, claims |

### Key Requirements

| Requirement | Standard | Notes |
|-------------|----------|-------|
| Biodegradability | >60% in 28 days | EU requirement |
| Surfactant declaration | Required | Most markets |
| Phosphate limits | Restricted | Environmental |
| Antimicrobial claims | Registration | Where claimed |
| Safety labeling | CLP or equivalent | All |

## 10.4 Personal Care/Cosmetics Standards

### Regulatory Requirements

| Market | Regulation | Requirements |
|--------|------------|--------------|
| **EU** | EC 1223/2009 | Safety assessment, notification, CPSR |
| **GCC** | GSO technical regulations | Registration, labeling |
| **Saudi Arabia** | SFDA regulations | Product registration |
| **UAE** | Ministry of Health | Registration |
| **Egypt** | Drug Authority | Registration |

### Key Compliance Areas

| Area | Requirement |
|------|-------------|
| Safety Assessment | Product safety report |
| GMP | ISO 22716 expected |
| Labeling | INCI ingredients, warnings |
| Claims | Substantiation required |
| Restricted Ingredients | Prohibited/restricted lists |
| Allergen Declaration | Fragrances, preservatives |
| Halal | Increasingly expected (MENA) |

### Halal Certification

| Aspect | Requirement |
|--------|-------------|
| Ingredients | No haram ingredients |
| Processing | No cross-contamination |
| Packaging | Compliant materials |
| Audit | Certification body inspection |
| Ongoing | Regular audits |

## 10.5 Labeling Requirements

### General Labeling Elements

| Element | Products | Notes |
|---------|----------|-------|
| Product Name | All | Clear identification |
| Net Contents | All | Weight/volume |
| Manufacturer | All | Name and address |
| Country of Origin | All | "Made in..." |
| Batch/Lot Number | Most | Traceability |
| Expiry Date | Where applicable | Format varies |
| Storage Conditions | Where applicable | Temperature, handling |
| Safety Warnings | Hazardous products | CLP symbols, phrases |
| Instructions | Where needed | Usage directions |

### Arabic Language Requirements

| Market | Requirement |
|--------|-------------|
| Saudi Arabia | Arabic mandatory |
| UAE | Arabic mandatory |
| Egypt | Arabic mandatory |
| Other MENA | Generally required |
| Export to EU | Local language(s) |

## 10.6 Testing & Quality Control

### In-Process Testing

| Product | Key Tests | Frequency |
|---------|-----------|-----------|
| **Plastics** | Visual, dimensions, weight | 100% / sampling |
| **Paints** | Viscosity, color, fineness | Per batch |
| **Detergents** | pH, active content, appearance | Per batch |
| **Personal Care** | pH, viscosity, appearance, micro | Per batch |
| **Adhesives** | Viscosity, tack, bond strength | Per batch |

### Laboratory Requirements

| Capability | Equipment | Investment |
|------------|-----------|------------|
| Basic QC | Balances, pH meter, viscometer | $10K-$30K |
| Intermediate | Spectrophotometer, tensile tester | $30K-$80K |
| Advanced | HPLC, GC, microbiology | $80K-$200K+ |

---

# Dimension 11: MENA Regional Context

## 11.1 Country Profiles

### Saudi Arabia

| Category | Details |
|----------|---------|
| **Market Size** | $15B+ chemicals & plastics |
| **Key Sectors** | Petrochemicals, packaging, construction materials |
| **Feedstock Advantage** | Proximity to SABIC, competitive feedstock |
| **Key Initiatives** | Vision 2030, NIDLP (industrial development) |
| **Regulatory** | SASO standards, SFDA (cosmetics/food) |
| **Opportunity** | Import substitution, local content |

**Key Clusters:**
- Jubail Industrial City (petrochemicals)
- Riyadh (conversion, consumer)
- Jeddah (consumer products, distribution)
- Dammam (industrial, packaging)

### UAE

| Category | Details |
|----------|---------|
| **Market Size** | $8B+ chemicals & plastics |
| **Key Sectors** | Packaging, consumer products, distribution |
| **Feedstock** | Borouge (Abu Dhabi), imports |
| **Hub Role** | Regional trading, re-export |
| **Regulatory** | ESMA standards |
| **Opportunity** | Quality products, export hub |

**Key Clusters:**
- Abu Dhabi (Borouge, industrial)
- Dubai (conversion, consumer, distribution)
- Sharjah/Ajman (manufacturing)
- Jebel Ali Free Zone (export/import)

### Egypt

| Category | Details |
|----------|---------|
| **Market Size** | $6B+ chemicals & plastics |
| **Key Sectors** | Fertilizers, packaging, consumer products |
| **Cost Advantage** | Labor, local market |
| **Feedstock** | Egyptian Petrochemicals, imports |
| **Export Focus** | Africa, regional |
| **Regulatory** | EOS standards |
| **Opportunity** | Export base, Africa gateway |

**Key Clusters:**
- 10th of Ramadan (plastics, packaging)
- Alexandria (chemicals, petrochemicals)
- 6th October (consumer products)
- Port Said (free zone, export)

### Jordan

| Category | Details |
|----------|---------|
| **Market Size** | $1.5B chemicals & plastics |
| **Key Sectors** | Pharmaceuticals, fertilizers, plastics |
| **Export Focus** | Iraq, regional |
| **Regulatory** | JISM standards |
| **Opportunity** | Pharma-linked, regional trade |

### Morocco

| Category | Details |
|----------|---------|
| **Market Size** | $4B+ chemicals & plastics |
| **Key Sectors** | Phosphates/fertilizers, plastics, automotive |
| **Export Focus** | Europe, Africa |
| **Advantage** | EU proximity, FTAs |
| **Opportunity** | Automotive supply, Africa gateway |

### Bahrain & Kuwait

| Country | Focus | Notes |
|---------|-------|-------|
| **Bahrain** | Petrochemicals (GPIC), trading | Smaller market, hub role |
| **Kuwait** | EQUATE, basic chemicals | Feedstock advantage |

## 11.2 Regional Market Comparison

### Market Size Comparison (Plastics Conversion)

| Country | Market Size (Est.) | Growth | SME Share |
|---------|-------------------|--------|-----------|
| Saudi Arabia | $5B+ | 5-7% | 40% |
| UAE | $3B+ | 4-6% | 45% |
| Egypt | $2.5B+ | 6-8% | 55% |
| Morocco | $1.5B+ | 5-7% | 50% |
| Jordan | $0.5B | 3-5% | 60% |

### Cost Position Comparison (Index: UAE = 100)

| Cost Factor | UAE | Saudi | Egypt | Jordan | Morocco |
|-------------|-----|-------|-------|--------|---------|
| Labor | 100 | 90 | 40 | 55 | 50 |
| Electricity | 100 | 80 | 50 | 85 | 70 |
| Polymer (local) | 100 | 90 | 105 | 110 | 110 |
| Real Estate | 100 | 70 | 35 | 50 | 45 |

### Feedstock Access

| Country | Local Production | Advantage |
|---------|------------------|-----------|
| Saudi Arabia | SABIC + others | Strong |
| UAE | Borouge | Strong |
| Kuwait | EQUATE | Strong |
| Egypt | Limited local | Moderate |
| Jordan | None | Import dependent |
| Morocco | None | Import dependent |

## 11.3 Regional Opportunities

| Opportunity | Description | Markets | Potential |
|-------------|-------------|---------|-----------|
| **Import Substitution** | Replace imports with local | Saudi, Egypt | High |
| **Construction Boom Supply** | Giga projects, infrastructure | Saudi, UAE | High |
| **Consumer Market Growth** | Population, income growth | All | High |
| **Africa Export** | Gateway to African markets | Egypt, Morocco | Medium-High |
| **Automotive Supply** | Growing auto manufacturing | Morocco, Egypt | Medium |
| **Halal Personal Care** | Global halal market | All | Medium |
| **Sustainable Products** | Recycled, bio-based | UAE, Saudi | Growing |
| **Specialty Chemicals** | Higher value, niche | All | Medium |

## 11.4 Regional Challenges

| Challenge | Impact | Countries | Mitigation |
|-----------|--------|-----------|------------|
| **Polymer Price Volatility** | Margin pressure | All | Pricing mechanisms |
| **Import Competition** | Price pressure | All | Quality, service differentiation |
| **Currency Volatility** | Cost unpredictability | Egypt | Hedging, local sourcing |
| **Energy Costs** | Competitiveness | Non-GCC | Efficiency investment |
| **Skilled Labor Shortage** | Quality, efficiency | All | Training investment |
| **Sustainability Pressure** | Compliance cost | All | Strategic investment |
| **Water Scarcity** | Process limitation | All (varies) | Efficiency, recycling |

## 11.5 Government Initiatives & Support

### Saudi Arabia

| Program | Focus | SME Benefit |
|---------|-------|-------------|
| **NIDLP** | Industrial development | Incentives, financing |
| **SIDF** | Industrial financing | Loans |
| **Local Content (IKTVA)** | Localization | Market access |
| **MODON Industrial Cities** | Manufacturing infrastructure | Land, utilities |

### UAE

| Program | Focus | SME Benefit |
|---------|-------|-------------|
| **Make it in Emirates** | Manufacturing promotion | Incentives |
| **Industrial Strategy** | Sector development | Support programs |
| **Free Zones** | Export/import | Tax advantages |

### Egypt

| Program | Focus | SME Benefit |
|---------|-------|-------------|
| **Industrial Development** | Manufacturing growth | Incentives |
| **Export Subsidies** | Export promotion | Cash support |
| **Free Zones** | Export manufacturing | Tax benefits |
| **GAFI** | Investment facilitation | Support |

### Morocco

| Program | Focus | SME Benefit |
|---------|-------|-------------|
| **Industrial Acceleration Plan** | Sector ecosystems | Incentives |
| **Free Zones (Tangier)** | Export manufacturing | Tax benefits |
| **Auto/Aero Ecosystems** | Supply chain | Market access |

## 11.6 Key Success Factors by Market

| Market | Critical Success Factors |
|--------|--------------------------|
| **Saudi Arabia** | Local content compliance, feedstock access, quality standards |
| **UAE** | Quality positioning, distribution network, export capability |
| **Egypt** | Cost efficiency, export orientation, local market presence |
| **Jordan** | Regional trade positioning, quality, relationships |
| **Morocco** | EU access, automotive supply qualification, export focus |

---

# Quick Reference Tables

## Agent Data Requirements Summary

| Agent | Primary Data from This Pack |
|-------|----------------------------|
| **The Drucker** | Subsectors, value chain, country context |
| **The Marvin** | OEE, quality metrics, production KPIs |
| **The Graham** | Margins by subsector, working capital, polymer exposure |
| **The Ricardo** | Export requirements, certifications, trade agreements |
| **The Lovelace** | Moderate baseline (35/100), MES opportunities, automation |
| **The Mayo** | Technical skills gaps, operator wages, shift patterns |
| **The Ohno** | Polymer supply chain, inventory management |
| **The Porter** | Five forces, feedstock advantage, competition |
| **The Landor** | Product standards, labeling requirements, halal |

## Critical Thresholds Summary

| Metric | Good | Warning | Critical |
|--------|------|---------|----------|
| **Gross Margin (Plastics)** | >25% | 18-25% | <18% |
| **Gross Margin (Formulated)** | >35% | 28-35% | <28% |
| **OEE** | >75% | 60-75% | <60% |
| **Scrap Rate** | <3% | 3-6% | >6% |
| **OTIF Delivery** | >95% | 88-95% | <88% |
| **Inventory Days (Total)** | <60 | 60-90 | >90 |
| **Customer Concentration** | <15% | 15-30% | >30% |
| **Digital Maturity** | >45 | 30-45 | <30 |
| **Employee Turnover** | <20% | 20-30% | >30% |

## Subsector Selection Guide

| If SME Wants... | Best Subsector | Trade-offs |
|-----------------|----------------|------------|
| Higher margins | Personal care, Specialty chemicals | Brand/R&D investment |
| Stability | Industrial plastics (OEM) | Technical requirements |
| Growth | Packaging (FMCG-linked) | Customer dependency |
| Export | Films, Consumer products | Certification investment |
| Lower capital | Cleaning products | Intense competition |
| Technical differentiation | Adhesives, Specialty | R&D capability |

---

# Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | December 2025 | RootRise Product Team | Initial Chemicals & Plastics sector pack |

---

*This document provides comprehensive sector intelligence for Chemicals & Plastics SMEs in the MENA region. For schema specification, see `RootRise_Sector_Knowledge_Framework.md`.*
