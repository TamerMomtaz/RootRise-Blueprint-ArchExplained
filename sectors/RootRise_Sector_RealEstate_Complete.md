# RootRise Sector Knowledge Pack
# Real Estate
## Version 1.0 | December 2025

---

# Document Information

| Attribute | Value |
|-----------|-------|
| **Sector ID** | `real_estate` |
| **Version** | 1.0 |
| **Last Updated** | December 2025 |
| **Status** | Active |
| **ISIC Rev.4 Divisions** | 68 (Real Estate Activities), 41 (Building Construction - Development), 81 (Facilities Management) |
| **Primary Markets** | Egypt, Saudi Arabia, UAE, Jordan, Morocco |
| **SME Employee Range** | 5-200 |
| **SME Revenue Range** | $100K - $50M |

## Sector Overview

Real Estate in MENA is experiencing **transformative growth** driven by Vision 2030 mega-projects, population growth, urbanization, and economic diversification. The sector encompasses development, brokerage, property management, and facilities services, with significant SME opportunity in specialized niches and services.

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                    REAL ESTATE VALUE CHAIN                                       │
├─────────────────────────────────────────────────────────────────────────────────┤
│                                                                                  │
│   DEVELOPMENT                         TRANSACTION                               │
│   ───────────                         ───────────                               │
│                                                                                  │
│   ┌──────────────┐                    ┌──────────────────────┐                  │
│   │ LAND         │                    │  BROKERAGE           │                  │
│   │ ACQUISITION  │                    │  • Sales             │                  │
│   │ • Site ID    │                    │  • Leasing           │                  │
│   │ • Due dilig. │                    │  • Commercial        │                  │
│   │ • Purchase   │                    │  • Residential       │                  │
│   └──────┬───────┘                    └──────────────────────┘                  │
│          │                                                                       │
│          ▼                            ┌──────────────────────┐                  │
│   ┌──────────────┐                    │  VALUATION &         │                  │
│   │ DEVELOPMENT  │                    │  ADVISORY            │                  │
│   │ • Planning   │                    │  • Appraisals        │                  │
│   │ • Design     │                    │  • Feasibility       │                  │
│   │ • Construction│                   │  • Investment        │                  │
│   │ • Marketing  │                    │  • Consulting        │                  │
│   └──────┬───────┘                    └──────────────────────┘                  │
│          │                                                                       │
│          ▼                                                                       │
│   MANAGEMENT                          SERVICES                                  │
│   ──────────                          ────────                                  │
│                                                                                  │
│   ┌──────────────┐                    ┌──────────────────────┐                  │
│   │ PROPERTY     │                    │  FACILITIES          │                  │
│   │ MANAGEMENT   │                    │  MANAGEMENT          │                  │
│   │ • Leasing    │                    │  • Hard services     │                  │
│   │ • Tenant rel.│                    │  • Soft services     │                  │
│   │ • Rent coll. │                    │  • Technical         │                  │
│   │ • Maintenance│                    │  • Integrated FM     │                  │
│   └──────────────┘                    └──────────────────────┘                  │
│                                                                                  │
│   KEY MENA CHARACTERISTICS:                                                     │
│   • Vision 2030 mega-projects (NEOM, Red Sea, Qiddiya, Diriyah)               │
│   • Foreign ownership reforms (Saudi, UAE Golden Visa)                        │
│   • High urbanization (80%+ in Gulf, growing elsewhere)                       │
│   • Young population driving housing demand                                   │
│   • Oversupply in some segments (Dubai office, Cairo luxury)                  │
│   • Regulatory modernization (RERA, escrow laws)                              │
│   • PropTech adoption accelerating                                            │
│                                                                                  │
└─────────────────────────────────────────────────────────────────────────────────┘
```

## Applicable Countries

| Country Code | Country Name | Market Size Estimate | Key Drivers |
|--------------|--------------|---------------------|-------------|
| EG | Egypt | $20-35 billion | Population, urbanization |
| SA | Saudi Arabia | $60-100 billion | Vision 2030, mega-projects |
| AE | UAE | $80-120 billion | Hub status, investment |
| JO | Jordan | $5-8 billion | Urbanization, refugees |
| MA | Morocco | $15-25 billion | Urbanization, tourism |

---

# Dimension 1: Industry Classification

## 1.1 ISIC Rev.4 Classification

### Primary ISIC Codes

| Division | Description | SME Relevance |
|----------|-------------|---------------|
| **68** | Real estate activities | **Very High** |
| **41** | Construction of buildings (development) | **High** |
| **81** | Services to buildings and landscape | **Very High** |

### Detailed Class Breakdown

**Division 68 - Real Estate Activities:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| **6810** | **Real estate activities with own or leased property** | **Very High** |
| **6820** | **Real estate activities on a fee or contract basis** | **Very High** |

**Division 41 - Building Construction:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| **4100** | **Construction of buildings** (development aspect) | **High** |

**Division 81 - Facilities Services:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| **8110** | **Combined facilities support activities** | **Very High** |
| **8121** | **General cleaning of buildings** | **High** |
| **8129** | **Other building and industrial cleaning** | **High** |
| **8130** | **Landscape care and maintenance** | **High** |

## 1.2 Subsector Taxonomy

```json
{
  "subsectors": [
    {
      "subsector_id": "residential_development",
      "subsector_name": "Residential Development",
      "subsector_name_ar": "التطوير السكني",
      "description": "Development and sale of residential properties",
      "isic_codes": ["4100", "6810"],
      "typical_sme_size": "20-150 employees",
      "typical_sme_revenue": "$5M-$50M",
      "mena_market_size_estimate": "$80-120 billion",
      "growth_rate_5yr": "8-15%",
      "key_segments": ["Affordable", "Mid-market", "Luxury", "Mixed-use"]
    },
    {
      "subsector_id": "commercial_development",
      "subsector_name": "Commercial Development",
      "subsector_name_ar": "التطوير التجاري",
      "description": "Development of office, retail, industrial properties",
      "isic_codes": ["4100", "6810"],
      "typical_sme_size": "15-100 employees",
      "typical_sme_revenue": "$3M-$40M",
      "mena_market_size_estimate": "$40-70 billion",
      "growth_rate_5yr": "6-12%",
      "key_segments": ["Office", "Retail", "Industrial", "Logistics"]
    },
    {
      "subsector_id": "residential_brokerage",
      "subsector_name": "Residential Brokerage",
      "subsector_name_ar": "الوساطة العقارية السكنية",
      "description": "Sales and rental brokerage for residential properties",
      "isic_codes": ["6820"],
      "typical_sme_size": "5-50 employees",
      "typical_sme_revenue": "$200K-$8M",
      "mena_market_size_estimate": "$3-6 billion",
      "growth_rate_5yr": "6-12%",
      "key_segments": ["Sales", "Rentals", "Luxury", "Off-plan"]
    },
    {
      "subsector_id": "commercial_brokerage",
      "subsector_name": "Commercial Brokerage & Advisory",
      "subsector_name_ar": "الوساطة والاستشارات التجارية",
      "description": "Commercial real estate transactions and advisory",
      "isic_codes": ["6820"],
      "typical_sme_size": "5-40 employees",
      "typical_sme_revenue": "$300K-$10M",
      "mena_market_size_estimate": "$2-4 billion",
      "growth_rate_5yr": "8-14%",
      "key_segments": ["Office", "Retail", "Industrial", "Investment"]
    },
    {
      "subsector_id": "property_management",
      "subsector_name": "Property Management",
      "subsector_name_ar": "إدارة العقارات",
      "description": "Management of residential and commercial properties",
      "isic_codes": ["6820", "8110"],
      "typical_sme_size": "10-80 employees",
      "typical_sme_revenue": "$300K-$12M",
      "mena_market_size_estimate": "$4-8 billion",
      "growth_rate_5yr": "10-18%",
      "key_segments": ["Residential", "Commercial", "Retail", "Mixed-use"]
    },
    {
      "subsector_id": "facilities_management",
      "subsector_name": "Facilities Management",
      "subsector_name_ar": "إدارة المرافق",
      "description": "Hard and soft FM services for buildings and assets",
      "isic_codes": ["8110", "8121", "8129", "8130"],
      "typical_sme_size": "20-200 employees",
      "typical_sme_revenue": "$500K-$20M",
      "mena_market_size_estimate": "$15-25 billion",
      "growth_rate_5yr": "10-15%",
      "key_segments": ["Integrated FM", "Technical services", "Soft services", "Specialized"]
    },
    {
      "subsector_id": "valuation_advisory",
      "subsector_name": "Valuation & Advisory",
      "subsector_name_ar": "التقييم والاستشارات",
      "description": "Property valuation, feasibility, investment advisory",
      "isic_codes": ["6820"],
      "typical_sme_size": "5-30 employees",
      "typical_sme_revenue": "$200K-$5M",
      "mena_market_size_estimate": "$1-2 billion",
      "growth_rate_5yr": "8-15%",
      "key_segments": ["Valuation", "Feasibility", "Investment", "Research"]
    },
    {
      "subsector_id": "owners_association",
      "subsector_name": "Owners Association Management",
      "subsector_name_ar": "إدارة جمعيات الملاك",
      "description": "Management of community associations and common areas",
      "isic_codes": ["6820", "8110"],
      "typical_sme_size": "10-60 employees",
      "typical_sme_revenue": "$300K-$8M",
      "mena_market_size_estimate": "$1-3 billion",
      "growth_rate_5yr": "12-20%",
      "key_segments": ["Residential communities", "Mixed-use", "Commercial"]
    },
    {
      "subsector_id": "proptech",
      "subsector_name": "PropTech & Real Estate Technology",
      "subsector_name_ar": "تقنيات العقارات",
      "description": "Technology solutions for real estate industry",
      "isic_codes": ["6820", "6312"],
      "typical_sme_size": "10-80 employees",
      "typical_sme_revenue": "$200K-$15M",
      "mena_market_size_estimate": "$1-3 billion",
      "growth_rate_5yr": "25-40%",
      "key_segments": ["Listings/portals", "PropMgmt software", "Transaction tech", "Smart building"]
    },
    {
      "subsector_id": "real_estate_investment",
      "subsector_name": "Real Estate Investment & Fund Management",
      "subsector_name_ar": "الاستثمار العقاري وإدارة الصناديق",
      "description": "Investment vehicles, REITs, fund management",
      "isic_codes": ["6810", "6630"],
      "typical_sme_size": "5-40 employees",
      "typical_sme_revenue": "$500K-$20M (fees)",
      "mena_market_size_estimate": "$3-8 billion (AUM fees)",
      "growth_rate_5yr": "12-20%",
      "key_segments": ["REITs", "Private equity", "Funds", "Syndication"]
    }
  ]
}
```

## 1.3 Property Types

### Residential

| Type | Characteristics | Target Market |
|------|-----------------|---------------|
| Villas/Townhouses | Standalone, premium | Families, luxury |
| Apartments | Multi-unit, various grades | Mass market to luxury |
| Affordable Housing | Government-subsidized | Lower-income |
| Student Housing | Purpose-built | Universities |
| Senior Living | Age-restricted | Elderly (emerging) |
| Serviced Apartments | Furnished, short-term | Corporate, tourists |

### Commercial

| Type | Characteristics | Key Metrics |
|------|-----------------|-------------|
| Grade A Office | Premium, CBD locations | Rent/sqm, occupancy |
| Grade B/C Office | Secondary locations | Yield, occupancy |
| Retail - Mall | Enclosed, anchor tenants | GLA, footfall |
| Retail - Strip | Street-front, neighborhood | Rent/sqm |
| Industrial/Logistics | Warehouse, distribution | Rent/sqm, height |
| Data Centers | Technical, power-intensive | Power density |

### Specialized

| Type | Characteristics | Growth Trend |
|------|-----------------|--------------|
| Healthcare | Hospitals, clinics | High |
| Education | Schools, universities | High |
| Hospitality | Hotels, resorts | High (Vision 2030) |
| Mixed-Use | Multiple uses combined | Very High |
| Co-working | Flexible office | High |

## 1.4 Value Chain Position

| Position | Description | Typical SME Type | Margin Profile |
|----------|-------------|------------------|----------------|
| **Developer** | Create new properties | Development companies | 15-35% (high risk) |
| **Investor/Owner** | Hold income properties | Investment companies | Yield 5-12% |
| **Broker/Agent** | Transaction intermediary | Brokerages | 1-5% commission |
| **Manager** | Operate properties | PM/FM companies | 5-15% of revenue |
| **Advisor** | Provide expertise | Consultancies | 30-50% margin |
| **Service Provider** | FM, maintenance | FM companies | 8-20% margin |

## 1.5 Adjacent Sectors

| Adjacent Sector | Relationship | Integration Level |
|-----------------|--------------|-------------------|
| **Construction** | Development execution | Very High |
| **Financial Services** | Mortgages, investment | Very High |
| **Legal Services** | Transactions, contracts | High |
| **Architecture/Engineering** | Design, planning | High |
| **Hospitality** | Hotel properties | High |
| **Retail** | Retail properties | High |

---

# Dimension 2: Financial Benchmarks

## 2.1 Development Metrics

### Development Returns

| Project Type | Target IRR | Target Margin | Development Period |
|--------------|-----------|---------------|-------------------|
| Residential - Affordable | 15-22% | 12-18% | 18-30 months |
| Residential - Mid-market | 18-28% | 15-25% | 24-36 months |
| Residential - Luxury | 20-35% | 18-30% | 30-48 months |
| Office | 15-25% | 12-22% | 24-42 months |
| Retail | 18-30% | 15-28% | 24-48 months |
| Mixed-Use | 18-28% | 15-25% | 36-60 months |

### Development Cost Breakdown

| Cost Category | Residential % | Commercial % |
|---------------|---------------|--------------|
| Land | 15-35% | 20-40% |
| Construction | 45-65% | 40-55% |
| Professional Fees | 5-10% | 6-12% |
| Marketing/Sales | 3-8% | 2-5% |
| Finance Costs | 5-12% | 6-15% |
| Contingency | 3-8% | 3-8% |
| Developer Overhead | 3-6% | 3-6% |

### Sales Performance

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| Pre-sales (Off-plan) | <30% | 30-50% | 50-70% | >70% |
| Sales Velocity | <3%/mo | 3-6%/mo | 6-10%/mo | >10%/mo |
| Price Premium vs Market | Discount | At market | 5-15% | >15% |
| Collection Rate | <85% | 85-92% | 92-97% | >97% |

## 2.2 Investment Metrics

### Yield Benchmarks by Property Type

| Property Type | Egypt | Saudi Arabia | UAE | Jordan |
|---------------|-------|--------------|-----|--------|
| Prime Residential | 4-7% | 5-8% | 4-7% | 6-9% |
| Grade A Office | 8-12% | 7-10% | 6-9% | 9-13% |
| Retail - Prime | 8-12% | 7-10% | 7-10% | 9-13% |
| Industrial/Logistics | 9-14% | 8-12% | 7-10% | 10-14% |
| Hospitality | 8-14% | 8-12% | 6-10% | 9-14% |

### Capital Values (USD/sqm)

| Property Type | Egypt | Saudi Arabia | UAE | Jordan |
|---------------|-------|--------------|-----|--------|
| Prime Residential | $800-2,500 | $2,000-6,000 | $3,000-15,000+ | $1,000-3,500 |
| Grade A Office | $1,500-4,000 | $2,500-6,000 | $4,000-10,000 | $1,500-4,000 |
| Retail - Mall | $2,000-6,000 | $3,000-8,000 | $5,000-15,000 | $2,000-5,000 |
| Industrial | $300-800 | $500-1,500 | $800-2,500 | $400-1,000 |

### Rental Rates (USD/sqm/year)

| Property Type | Egypt | Saudi Arabia | UAE | Jordan |
|---------------|-------|--------------|-----|--------|
| Prime Residential | $60-180 | $150-400 | $200-600+ | $80-250 |
| Grade A Office | $150-350 | $200-450 | $300-700 | $150-350 |
| Retail - Prime | $200-600 | $300-800 | $500-2,000+ | $200-500 |
| Industrial | $30-80 | $50-120 | $80-200 | $40-100 |

## 2.3 Brokerage Financial Metrics

### Commission Structures

| Transaction Type | Commission Rate | Split (Agent/Company) |
|------------------|-----------------|----------------------|
| Residential Sale | 1-3% | 50-70% / 30-50% |
| Residential Lease | 2.5-5% annual rent | 50-60% / 40-50% |
| Commercial Sale | 1-2% | 40-60% / 40-60% |
| Commercial Lease | 5-15% annual rent | 40-60% / 40-60% |
| Land Sale | 1-3% | 50-70% / 30-50% |

### Brokerage Profitability

| Metric | Small Firm | Mid-Size | Large Firm |
|--------|-----------|----------|------------|
| **Revenue/Agent** | $30-80K | $60-150K | $100-300K |
| **Gross Margin** | 20-35% | 30-45% | 40-55% |
| **Operating Margin** | 8-18% | 12-25% | 18-35% |
| **Agent Retention** | 40-60% | 55-70% | 65-80% |

## 2.4 Property & Facilities Management

### Fee Structures

| Service | Fee Basis | Typical Rate |
|---------|-----------|--------------|
| Residential PM | % of rent collected | 5-10% |
| Commercial PM | % of rent or per sqm | 3-8% or $2-8/sqm |
| OA Management | Per unit/month | $30-150/unit |
| FM - Soft Services | Per sqm/month | $1-4/sqm |
| FM - Hard Services | Per sqm/month | $2-8/sqm |
| Integrated FM | Per sqm/month | $4-15/sqm |

### PM/FM Profitability

| Metric | Small Firm | Mid-Size | Large Firm |
|--------|-----------|----------|------------|
| **Gross Margin** | 20-30% | 25-38% | 30-45% |
| **Operating Margin** | 6-15% | 10-20% | 15-28% |
| **Revenue/Employee** | $30-60K | $40-80K | $50-100K |
| **Contract Renewal** | 70-80% | 78-88% | 85-95% |

## 2.5 Working Capital Requirements

### Cash Flow Characteristics

| Subsector | Revenue Pattern | Working Capital % |
|-----------|-----------------|-------------------|
| Development | Lumpy, milestone-based | 30-60% of project |
| Brokerage | Transaction-based | 10-20% |
| Property Management | Monthly recurring | 15-25% |
| Facilities Management | Monthly/quarterly | 20-35% |
| Valuation/Advisory | Project-based | 15-25% |

### Seasonality

| Segment | Peak Period | Low Period | Variance |
|---------|-------------|------------|----------|
| Residential Sales | Q4, Q1 | Ramadan, Summer | High |
| Commercial Leasing | Q4, Q1 | Summer | Medium |
| Property Management | Consistent | Ramadan | Low |
| FM Services | Consistent | - | Low |

## 2.6 Capital Requirements

### Development Capital

| Project Size | Equity Required | Debt:Equity | Total Investment |
|--------------|-----------------|-------------|------------------|
| Small Residential (20-50 units) | $1-5M | 60:40 to 70:30 | $3-15M |
| Medium Residential (50-200 units) | $5-20M | 65:35 to 75:25 | $15-80M |
| Large Residential (200+ units) | $20-100M+ | 70:30 to 80:20 | $80-400M+ |
| Commercial (10,000+ sqm) | $10-50M+ | 60:40 to 70:30 | $30-200M+ |

### Service Company Startup

| Business Type | Setup Cost | Working Capital | Total |
|---------------|------------|-----------------|-------|
| Small Brokerage | $20-80K | $30-100K | $50-180K |
| Property Management | $30-100K | $50-150K | $80-250K |
| FM Company | $50-200K | $100-400K | $150-600K |
| Valuation Practice | $20-60K | $30-80K | $50-140K |
| PropTech Startup | $100-500K | $100-300K | $200-800K |

## 2.7 Valuation Multiples

| Subsector | Revenue Multiple | EBITDA Multiple | Key Drivers |
|-----------|------------------|-----------------|-------------|
| Development | 0.3-0.8x | 4-8x | Land bank, track record |
| Brokerage | 0.3-1x | 3-7x | Agent quality, brand |
| Property Management | 0.8-2x | 5-12x | Contract value, retention |
| Facilities Management | 0.5-1.5x | 4-10x | Contract base, margin |
| Valuation/Advisory | 0.5-1.5x | 4-10x | Reputation, clients |
| PropTech | 2-8x | 10-30x | Growth, technology |

---

# Dimension 3: Operational KPIs

## 3.1 Development KPIs

### Project Performance

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Project IRR** | Internal rate of return | <15% | 15-20% | 20-28% | >28% |
| **Development Margin** | Profit/revenue | <12% | 12-18% | 18-25% | >25% |
| **Schedule Variance** | vs planned completion | >20% late | 10-20% | <10% | On time |
| **Cost Overrun** | vs budget | >15% | 8-15% | 3-8% | <3% |
| **Sales Velocity** | Units sold/month | <3% | 3-6% | 6-10% | >10% |
| **Pre-sales %** | Sold before completion | <30% | 30-50% | 50-70% | >70% |

### Quality & Defects

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Defects at Handover** | Per unit | >15 | 8-15 | 3-8 | <3 |
| **Warranty Claims** | Year 1 per unit | >5 | 2-5 | 1-2 | <1 |
| **Customer Satisfaction** | Survey score | <70% | 70-80% | 80-90% | >90% |
| **Referral Rate** | From buyers | <10% | 10-20% | 20-35% | >35% |

## 3.2 Brokerage KPIs

### Agent Performance

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Transactions/Agent** | Annual closed deals | <6 | 6-12 | 12-24 | >24 |
| **Revenue/Agent** | Annual commission | <$40K | $40-80K | $80-150K | >$150K |
| **Listing Conversion** | Listed to sold | <40% | 40-60% | 60-80% | >80% |
| **Days on Market** | Listing to sale | >120 | 90-120 | 60-90 | <60 |
| **Lead Conversion** | Leads to clients | <5% | 5-12% | 12-20% | >20% |

### Business Health

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Market Share** | Area transactions | <2% | 2-5% | 5-10% | >10% |
| **Agent Retention** | Annual | <50% | 50-70% | 70-85% | >85% |
| **Repeat Business** | From past clients | <15% | 15-25% | 25-40% | >40% |
| **Referral Rate** | Client referrals | <20% | 20-35% | 35-50% | >50% |

## 3.3 Property Management KPIs

### Financial Performance

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Collection Rate** | Rent collected/due | <90% | 90-95% | 95-98% | >98% |
| **Occupancy Rate** | Occupied/total units | <85% | 85-92% | 92-97% | >97% |
| **Tenant Retention** | Renewals | <65% | 65-78% | 78-88% | >88% |
| **NOI Growth** | Year-over-year | <0% | 0-3% | 3-6% | >6% |
| **Operating Ratio** | OpEx/Revenue | >55% | 45-55% | 35-45% | <35% |

### Service Quality

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Tenant Satisfaction** | Survey score | <70% | 70-80% | 80-90% | >90% |
| **Maintenance Response** | Hours to respond | >48 | 24-48 | 8-24 | <8 |
| **Work Order Completion** | On-time % | <80% | 80-90% | 90-96% | >96% |
| **Vacancy Turn Time** | Days to re-let | >45 | 30-45 | 15-30 | <15 |
| **Complaint Resolution** | Within 24 hours | <70% | 70-85% | 85-95% | >95% |

## 3.4 Facilities Management KPIs

### Operational Excellence

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Uptime** | Equipment availability | <95% | 95-97% | 97-99% | >99% |
| **PPM Compliance** | Planned maintenance | <80% | 80-90% | 90-97% | >97% |
| **Response Time** | Emergency calls | >60 min | 30-60 | 15-30 | <15 min |
| **SLA Achievement** | Met/total SLAs | <90% | 90-95% | 95-98% | >98% |
| **Energy Efficiency** | kWh/sqm reduction | 0% | 0-5% | 5-12% | >12% |

### Business Performance

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Contract Retention** | Renewals | <75% | 75-85% | 85-93% | >93% |
| **Client Satisfaction** | Survey score | <75% | 75-85% | 85-93% | >93% |
| **Gross Margin** | Per contract | <18% | 18-28% | 28-38% | >38% |
| **Labor Productivity** | Revenue/employee | <$40K | $40-60K | $60-85K | >$85K |
| **Safety** | Lost time incidents | >3/year | 1-3 | 0-1 | 0 |

## 3.5 OA Management KPIs

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Service Charge Collection** | Collected/due | <85% | 85-92% | 92-97% | >97% |
| **Owner Satisfaction** | Survey score | <70% | 70-80% | 80-90% | >90% |
| **Meeting Quorum** | AGM attendance | <25% | 25-40% | 40-60% | >60% |
| **Reserve Fund Adequacy** | vs requirements | <50% | 50-75% | 75-100% | >100% |
| **Violation Resolution** | Within SLA | <80% | 80-90% | 90-96% | >96% |

## 3.6 Investment/Fund KPIs

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Fund IRR** | Net return | <8% | 8-12% | 12-18% | >18% |
| **Cash Yield** | Annual distribution | <4% | 4-6% | 6-9% | >9% |
| **Occupancy (Portfolio)** | Weighted average | <85% | 85-92% | 92-97% | >97% |
| **WALT** | Weighted avg lease term | <3 yrs | 3-5 yrs | 5-8 yrs | >8 yrs |
| **Investor Retention** | Re-investment | <60% | 60-75% | 75-88% | >88% |

---

*End of Part 1 - Continue to Part 2 for Dimensions 4-7*
# Dimension 4: Regulatory Landscape

## 4.1 Business Licenses & Permits

### Developer Licenses

| License Type | Issuing Authority | Validity | Cost Range |
|--------------|-------------------|----------|------------|
| Developer Registration | Real Estate Authority | 1-3 years | $5,000-50,000 |
| Project License | Municipality/Authority | Per project | $10,000-100,000+ |
| Sales License (Off-plan) | Real Estate Regulator | Per project | $2,000-20,000 |
| Escrow Account Setup | Bank/Regulator | Per project | $1,000-10,000 |
| Building Permit | Municipality | Per project | % of construction |
| Completion Certificate | Municipality | Per project | $1,000-10,000 |

### Brokerage Licenses

| License Type | Issuing Authority | Validity | Cost Range |
|--------------|-------------------|----------|------------|
| Broker License (Company) | Real Estate Authority | Annual | $1,000-10,000 |
| Agent License (Individual) | Real Estate Authority | Annual | $200-2,000 |
| Trade License | Commerce/Economy | Annual | $500-5,000 |
| Branch License | Real Estate Authority | Per location | $500-3,000 |

### Property/Facilities Management

| License Type | Issuing Authority | Validity | Cost Range |
|--------------|-------------------|----------|------------|
| PM License | Real Estate Authority | Annual | $1,000-8,000 |
| FM License | Municipality/Authority | Annual | $2,000-15,000 |
| OA Management License | Real Estate Regulator | Annual | $1,000-5,000 |
| Cleaning Services License | Municipality | Annual | $1,000-5,000 |
| Security Services License | Security Authority | Annual | $5,000-25,000 |

### Valuation & Advisory

| License Type | Issuing Authority | Validity | Cost Range |
|--------------|-------------------|----------|------------|
| Valuer Registration | Real Estate Authority | Annual | $500-5,000 |
| RICS Membership | RICS | Annual | $500-2,000 |
| Consulting License | Commerce Ministry | Annual | $500-3,000 |

## 4.2 Regulatory Framework by Country

### UAE (Dubai/Abu Dhabi)

| Regulation | Description | Impact |
|------------|-------------|--------|
| RERA (Dubai) | Real Estate Regulatory Agency | Comprehensive regulation |
| DLD (Dubai) | Dubai Land Department | Registration, fees |
| ADGM/DIFC | Free zone regulations | Investment vehicles |
| Escrow Law | Buyer protection | Off-plan sales |
| Strata Law | Jointly owned property | OA management |
| Broker Regulations | Agent licensing | Professional standards |

### Saudi Arabia

| Regulation | Description | Impact |
|------------|-------------|--------|
| REGA | Real Estate General Authority | Sector development |
| Ejar System | Rental contract registration | Standardization |
| Wafi Program | Off-plan sales regulation | Buyer protection |
| Sakani Program | Housing support | Affordable housing |
| RICS Valuations | Mandatory for lending | Valuation standards |
| Foreign Ownership | Expanding access | Market opening |

### Egypt

| Regulation | Description | Impact |
|------------|-------------|--------|
| Real Estate Regulatory Authority | New regulator (forming) | Modernization |
| Building Law | Construction standards | Compliance |
| Registration Law | Property registration | Title clarity |
| Consumer Protection | Buyer rights | Developer obligations |
| Tax Laws | Property taxes | Transaction costs |

### Jordan

| Regulation | Description | Impact |
|------------|-------------|--------|
| Land & Survey Department | Registration | Title system |
| Real Estate Brokers Law | Licensing | Professional standards |
| Strata Title Law | Multi-unit ownership | Condominium development |
| Building Codes | Construction | Standards |

### Morocco

| Regulation | Description | Impact |
|------------|-------------|--------|
| ANCFCC | Land registry | Registration |
| VEFA Law | Off-plan sales | Buyer protection |
| Professional Regulations | Broker/agent | Standards |
| Urban Planning | Zoning | Development |

## 4.3 Foreign Ownership Rules

| Country | Freehold Access | Restrictions |
|---------|-----------------|--------------|
| **UAE** | Designated areas | Non-designated require partner |
| **Saudi Arabia** | Expanding (recent reforms) | Some restrictions remain |
| **Egypt** | Generally permitted | Some land restrictions |
| **Jordan** | Permitted with approval | Agricultural land restricted |
| **Morocco** | Generally permitted | Agricultural land restricted |

## 4.4 Compliance Requirements

### Developer Compliance

| Requirement | Description | Frequency |
|-------------|-------------|-----------|
| Escrow Deposits | Buyer funds protection | Per project |
| Progress Reporting | Construction milestones | Quarterly |
| Financial Audits | Project accounts | Annual |
| Consumer Disclosures | Project information | At sale |
| Completion Guarantees | Bonds/insurance | Per project |
| Defect Liability | Warranty period | 10+ years (structural) |

### Broker/Agent Compliance

| Requirement | Description | Frequency |
|-------------|-------------|-----------|
| License Renewal | Maintain active license | Annual |
| Training Requirements | CPD hours | Annual (varies) |
| Insurance | Professional liability | Annual |
| Contract Standards | Prescribed forms | Per transaction |
| Commission Disclosure | Transparency | Per transaction |
| AML/KYC | Client verification | Per transaction |

### PM/FM Compliance

| Requirement | Description | Frequency |
|-------------|-------------|-----------|
| Health & Safety | Workplace safety | Ongoing |
| Fire Safety | Building compliance | Annual inspection |
| Environmental | Waste, emissions | Ongoing |
| Labor Law | Employee compliance | Ongoing |
| Insurance | Liability coverage | Annual |
| Financial Reporting | To owners/clients | Monthly/quarterly |

## 4.5 Certifications

| Certification | Purpose | Cost Range | Validity |
|---------------|---------|------------|----------|
| RICS Membership | Valuation, advisory | $500-2,000/year | Annual |
| BIFM/IWFM | Facilities management | $300-1,000/year | Annual |
| LEED AP | Green building | $500-1,500 | 2 years |
| ISO 9001 | Quality management | $3,000-15,000 | 3 years |
| ISO 41001 | FM management | $5,000-20,000 | 3 years |
| ISO 14001 | Environmental | $5,000-20,000 | 3 years |
| BOMA | Property management | $500-2,000/year | Annual |

## 4.6 Regulatory Bodies by Country

### UAE

| Authority | Responsibility |
|-----------|---------------|
| RERA (Dubai) | Real estate regulation |
| DLD (Dubai) | Land registration |
| Abu Dhabi DoM | Abu Dhabi regulation |
| ADGM, DIFC | Financial free zones |
| Dubai Municipality | Building permits |

### Saudi Arabia

| Authority | Responsibility |
|-----------|---------------|
| REGA | Sector regulation |
| Ministry of Municipal Affairs | Planning, permits |
| SAMA | Mortgage regulation |
| Capital Market Authority | REITs |
| Ministry of Housing | Housing programs |

### Egypt

| Authority | Responsibility |
|-----------|---------------|
| Real Estate Regulatory Authority | Sector regulation (new) |
| Ministry of Housing | Policy |
| General Organization for Physical Planning | Planning |
| Survey Authority | Registration |

### Jordan

| Authority | Responsibility |
|-----------|---------------|
| Land & Survey Department | Registration |
| Greater Amman Municipality | Permits, planning |
| Ministry of Public Works | Building codes |

### Morocco

| Authority | Responsibility |
|-----------|---------------|
| ANCFCC | Land registry |
| Ministry of Housing | Policy |
| Urban Agencies | Planning |

---

# Dimension 5: Competitive Dynamics

## 5.1 Market Structure

| Subsector | Concentration | Market Leaders | Fragmentation |
|-----------|---------------|----------------|---------------|
| Development - Large | High | Major developers | Concentrated |
| Development - SME | Low | Many small developers | Fragmented |
| Brokerage | Low | Many agencies | Highly fragmented |
| Commercial Advisory | Medium | International + regional | Moderate |
| Property Management | Medium | Growing consolidation | Moderate |
| Facilities Management | Medium | International + regional | Moderate |
| Valuation | Medium | RICS firms dominant | Moderate |

## 5.2 Porter's Five Forces

```
┌─────────────────────────────────────────────────────────────────────┐
│              REAL ESTATE FIVE FORCES SUMMARY                        │
├─────────────────────────────────────────────────────────────────────┤
│                                                                      │
│                  NEW ENTRANTS: 2.5/5                                │
│                  (Capital intensive; relationships matter)          │
│                        │                                            │
│                        ▼                                            │
│   SUPPLIER POWER ────────────► INDUSTRY ◄───── BUYER POWER         │
│       3.5/5                    RIVALRY           3.5/5             │
│   (Land scarcity,               3.5/5        (Multiple options,     │
│    construction cost)       (Many players,     information         │
│                              cycle-driven)     availability)        │
│                        │                                            │
│                        ▼                                            │
│                SUBSTITUTES: 2/5                                     │
│                (Limited - location fixed, co-living/working)        │
│                                                                      │
│   OVERALL ATTRACTIVENESS: MODERATE                                  │
│   Key: Location + Relationships + Capital Access + Execution        │
└─────────────────────────────────────────────────────────────────────┘
```

### Force Details

| Force | Rating | Key Factors |
|-------|--------|-------------|
| **New Entrants** | 2.5/5 | Capital barriers; regulatory; relationships |
| **Supplier Power** | 3.5/5 | Land scarcity; construction cost inflation |
| **Buyer Power** | 3.5/5 | Information availability; many options |
| **Substitutes** | 2/5 | Limited substitutes for real estate |
| **Rivalry** | 3.5/5 | Cycle-driven; oversupply in segments |

## 5.3 Competitive Strategies

| Strategy | Description | Best For | Requirements |
|----------|-------------|----------|--------------|
| Land Bank | Control prime locations | Large developers | Capital, relationships |
| Niche Specialist | Focus segment/geography | SME developers | Deep expertise |
| Service Excellence | Quality differentiation | PM/FM, brokerage | Operations |
| Technology Leader | PropTech-enabled | All segments | Tech investment |
| Integrated Services | Full value chain | Large groups | Breadth |
| Cost Leader | Efficient operations | FM, commodity | Scale, efficiency |
| Brand Premium | Reputation-based | Luxury, advisory | Track record |

## 5.4 Industry Trends

| Trend | Impact | Timeframe | SME Opportunity |
|-------|--------|-----------|-----------------|
| **Vision 2030 Projects** | Massive development | 2-10 years | Subcontracting, services |
| **PropTech Adoption** | Digital transformation | Ongoing | Tech-enabled services |
| **Sustainability/ESG** | Green building demand | 2-7 years | Certification, retrofits |
| **Affordable Housing** | Government focus | Ongoing | Developer programs |
| **Flexible Space** | Co-working, flex offices | Ongoing | Management, brokerage |
| **Smart Buildings** | IoT, automation | 2-7 years | FM, integration |
| **Foreign Investment** | Ownership reforms | Ongoing | Brokerage, advisory |
| **Institutional Capital** | REITs, funds growing | Ongoing | Fund services |
| **Consolidation** | M&A in services | Ongoing | Exit opportunity |

## 5.5 Major Player Landscape

### Developers by Country

| Country | Major Players | Characteristics |
|---------|---------------|-----------------|
| **UAE** | Emaar, Nakheel, Damac, Aldar | Large-scale, branded |
| **Saudi Arabia** | Roshn, Dar Al Arkan, Saudi Aramco RE | Government + private |
| **Egypt** | Palm Hills, SODIC, Talaat Moustafa | Mixed-use, community |
| **Jordan** | Abdali, Saraya, various | Smaller scale |
| **Morocco** | CGI, Addoha, Alliances | Social housing + premium |

### International Service Providers

| Company | Services | MENA Presence |
|---------|----------|---------------|
| JLL | Full service advisory | Pan-MENA |
| CBRE | Full service advisory | Pan-MENA |
| Cushman & Wakefield | Advisory, FM | Select markets |
| Savills | Advisory, valuation | Growing |
| Knight Frank | Advisory, residential | Strong (UAE, Saudi) |
| Colliers | Advisory, PM | Select markets |

### FM Providers

| Company | Scope | Presence |
|---------|-------|----------|
| Emrill | Integrated FM | UAE |
| Farnek | Integrated FM | UAE |
| Imdaad | Integrated FM | UAE |
| ENGIE | Technical FM | Regional |
| ISS | Soft services | Regional |
| Various local | Market-specific | Country |

## 5.6 Market-Specific Dynamics

| Country | Market Characteristics | Key Opportunity |
|---------|----------------------|-----------------|
| **UAE** | Most developed, competitive | Niche, services |
| **Saudi Arabia** | Fastest growing, Vision 2030 | All segments |
| **Egypt** | Large, fragmented, informal | Formalization, services |
| **Jordan** | Smaller, stable | Services, refugee housing |
| **Morocco** | Growing, French influence | Social housing, tourism |

---

# Dimension 6: Digital Maturity

## 6.1 Technology Adoption Benchmarks

| Subsector | Current Adoption | Digital Leaders | Digital Laggards | Key Gap |
|-----------|------------------|-----------------|------------------|---------|
| Development (Large) | Medium-High | 55% | 15% | BIM, sales tech |
| Development (SME) | Low-Medium | 20% | 50% | Basic systems |
| Brokerage | Medium | 45% | 30% | CRM, listings |
| Property Management | Medium | 40% | 35% | PM software |
| Facilities Management | Medium-High | 50% | 25% | CAFM, IoT |
| Valuation | Medium | 40% | 35% | Valuation software |

## 6.2 Digital Maturity Levels

```
┌─────────────────────────────────────────────────────────────────────────────┐
│              REAL ESTATE DIGITAL MATURITY LEVELS                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  LEVEL 1: TRADITIONAL (Score 0-20)                                          │
│  • Paper records, spreadsheets, manual processes                            │
│  • Typical: Traditional brokers, small developers                           │
│                                                                              │
│  LEVEL 2: BASIC DIGITAL (Score 21-40)                                       │
│  • Basic CRM, listing portals, email marketing                              │
│  • Typical: Small-medium agencies, PM companies                             │
│                                                                              │
│  LEVEL 3: CONNECTED (Score 41-60)                                           │
│  • Integrated PM/FM software, online transactions, analytics                │
│  • Typical: Progressive companies, franchises                               │
│                                                                              │
│  LEVEL 4: INTEGRATED (Score 61-80)                                          │
│  • Full digital operations, BIM, IoT, predictive maintenance                │
│  • Typical: Large developers, international firms                           │
│                                                                              │
│  LEVEL 5: INTELLIGENT (Score 81-100)                                        │
│  • AI-driven insights, smart building, automated operations                 │
│  • Typical: PropTech leaders, innovation pioneers                           │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 6.3 Core Technology Systems

### Development

| System | Priority | Investment Range | Payback | MENA Adoption |
|--------|----------|------------------|---------|---------------|
| Project Management | Critical | $5K-50K | 6-12 mo | 60% |
| BIM | High | $10K-100K | 12-24 mo | 35% |
| Sales/CRM | Critical | $3K-30K | 6-12 mo | 50% |
| ERP/Accounting | Critical | $10K-100K | 12-18 mo | 55% |
| Customer Portal | Medium | $5K-30K | 12-24 mo | 25% |

### Brokerage

| System | Priority | Investment Range | Payback | MENA Adoption |
|--------|----------|------------------|---------|---------------|
| CRM | Critical | $2K-20K | 3-6 mo | 50% |
| Listing Management | Critical | $1K-10K | 3-6 mo | 65% |
| Website/Portal | High | $3K-30K | 6-12 mo | 70% |
| Transaction Management | Medium | $2K-15K | 6-12 mo | 25% |
| Marketing Automation | Medium | $2K-10K | 6-12 mo | 30% |

### Property/Facilities Management

| System | Priority | Investment Range | Payback | MENA Adoption |
|--------|----------|------------------|---------|---------------|
| PM Software | Critical | $5K-50K | 6-12 mo | 45% |
| CAFM/CMMS | Critical (FM) | $10K-100K | 12-18 mo | 50% |
| Tenant Portal | High | $3K-25K | 12-18 mo | 30% |
| IoT/BMS Integration | High | $10K-100K+ | 18-36 mo | 25% |
| Mobile Field App | High | $3K-20K | 6-12 mo | 40% |
| Accounting Integration | Critical | $5K-30K | 6-12 mo | 55% |

## 6.4 PropTech Ecosystem

### PropTech Categories

| Category | Examples | MENA Players |
|----------|----------|--------------|
| Listings/Portals | Zillow, Rightmove | Property Finder, Bayut, Aqarmap |
| Transaction | DocuSign, Dotloop | Developing |
| PM Software | Yardi, RealPage, Buildium | Local + international |
| FM/CAFM | IBM Maximo, Archibus | International |
| Smart Building | Honeywell, Siemens | Growing |
| Valuation Tech | AVMs | Emerging |
| Investment | Crowdfunding platforms | SmartCrowd, Stake |

### High-Impact Digital Interventions

| Subsector | Priority 1 | Priority 2 | Priority 3 | Impact |
|-----------|------------|------------|------------|--------|
| Development | Project management | Sales CRM | BIM | 20-35% efficiency |
| Brokerage | CRM implementation | Listing syndication | Marketing automation | 25-40% productivity |
| PM | PM software | Tenant portal | Analytics | 30-50% efficiency |
| FM | CAFM/CMMS | Mobile app | IoT sensors | 25-40% efficiency |
| Valuation | Valuation software | Data analytics | Market intelligence | 30-45% productivity |

## 6.5 Smart Building Technology

### Building Systems

| System | Function | ROI Timeline |
|--------|----------|--------------|
| BMS (Building Management) | Central control | 2-4 years |
| Access Control | Security | 1-3 years |
| CCTV/Security | Monitoring | 1-2 years |
| Energy Management | Efficiency | 2-5 years |
| IoT Sensors | Monitoring, analytics | 2-4 years |
| Tenant Apps | Engagement | 1-2 years |

---

# Dimension 7: Workforce Norms

## 7.1 Organizational Structures

### Small Developer (20-40 employees)
```
              Managing Director
                    │
       ┌────────────┼────────────┐
       │            │            │
   Development    Sales &      Finance &
    Manager      Marketing       Admin
       │            │            │
   Project       Sales Team   Accounts
   Managers      Marketing    HR/Admin
   Site Staff    Customer Svc Legal/Comp
```

### Brokerage Firm (15-40 employees)
```
              General Manager/Owner
                    │
       ┌────────────┼────────────┐
       │            │            │
   Sales          Admin        Marketing
   Manager        Manager
       │            │            │
   Senior        Coordinator   Marketing
   Agents        Listings      Digital
   Agents        Finance
```

### FM Company (50-150 employees)
```
              General Manager
                    │
       ┌────────────┼────────────┬────────────┐
       │            │            │            │
  Operations     Technical    Finance/      HR/
   Manager       Manager       Admin       Safety
       │            │            │            │
  Site Mgrs    Engineers     Accounts    Training
  Supervisors  Technicians   Procurement  Compliance
  Staff        Specialists
```

## 7.2 Key Roles

### Development Roles

| Role | Responsibilities | Experience | Education |
|------|------------------|------------|-----------|
| Development Director | Strategy, P&L | 15+ years | Business/RE degree |
| Project Director | Large project oversight | 10-15 years | Engineering/RE |
| Sales Director | Sales strategy, team | 10-12 years | Business/Marketing |
| Project Manager | Day-to-day execution | 5-8 years | Engineering/PM |
| Sales Manager | Sales team leadership | 5-8 years | Business |
| Sales Executive | Direct selling | 2-5 years | Any degree |

### Brokerage Roles

| Role | Responsibilities | Experience | Requirements |
|------|------------------|------------|--------------|
| Broker/Owner | Business leadership | 10+ years | Broker license |
| Sales Manager | Team leadership | 5-10 years | Agent license |
| Senior Agent | High-value transactions | 5+ years | Agent license |
| Agent | Transaction execution | 1-5 years | Agent license |
| Listings Coordinator | Admin support | 1-3 years | Organization skills |
| Marketing Executive | Marketing execution | 2-4 years | Marketing skills |

### PM/FM Roles

| Role | Responsibilities | Experience | Certifications |
|------|------------------|------------|----------------|
| General Manager | Operations leadership | 12+ years | FM qualification |
| Operations Manager | Service delivery | 8-12 years | FM/PM cert |
| Property Manager | Building management | 5-8 years | PM certification |
| Technical Manager | Hard services | 8-12 years | Engineering |
| Site Manager | Site operations | 5-8 years | FM experience |
| Engineer/Technician | Technical services | 3-8 years | Trade certification |
| Supervisor | Team leadership | 3-5 years | FM experience |

## 7.3 Compensation Benchmarks (USD/month)

### Egypt

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Development Director | - | - | $3,000-8,000 |
| Project Manager | $600-1,000 | $1,000-2,000 | $2,000-4,000 |
| Sales Manager | $500-800 | $800-1,500 | $1,500-3,000 |
| Property Manager | $400-700 | $700-1,200 | $1,200-2,500 |
| FM Site Manager | $350-600 | $600-1,000 | $1,000-2,000 |
| Agent (Base + Comm) | $200-400 | $400-800 | $800-1,500 |

### Saudi Arabia

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Development Director | - | - | $12,000-30,000 |
| Project Manager | $4,000-6,500 | $6,500-10,000 | $10,000-18,000 |
| Sales Manager | $3,500-5,500 | $5,500-9,000 | $9,000-15,000 |
| Property Manager | $3,000-5,000 | $5,000-8,000 | $8,000-14,000 |
| FM Site Manager | $2,500-4,000 | $4,000-7,000 | $7,000-12,000 |
| Agent (Base + Comm) | $1,500-2,500 | $2,500-4,500 | $4,500-8,000 |

### UAE

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Development Director | - | - | $15,000-40,000 |
| Project Manager | $5,000-8,000 | $8,000-13,000 | $13,000-22,000 |
| Sales Manager | $4,500-7,000 | $7,000-12,000 | $12,000-20,000 |
| Property Manager | $4,000-6,500 | $6,500-10,000 | $10,000-18,000 |
| FM Site Manager | $3,500-5,500 | $5,500-9,000 | $9,000-15,000 |
| Agent (Base + Comm) | $2,000-3,500 | $3,500-6,000 | $6,000-12,000+ |

### Jordan

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Development Director | - | - | $4,000-10,000 |
| Project Manager | $900-1,500 | $1,500-2,800 | $2,800-5,000 |
| Sales Manager | $700-1,200 | $1,200-2,200 | $2,200-4,000 |
| Property Manager | $600-1,000 | $1,000-1,800 | $1,800-3,500 |
| FM Site Manager | $500-900 | $900-1,600 | $1,600-3,000 |
| Agent (Base + Comm) | $350-600 | $600-1,200 | $1,200-2,500 |

## 7.4 Skills Gap Analysis

| Skill Area | Availability | Demand | Gap Severity |
|------------|--------------|--------|--------------|
| PropTech/Digital | Low | Very High | **Critical** |
| Sustainability/Green | Very Low | High | **Critical** |
| Project Management | Medium | High | **High** |
| Data Analytics | Low | High | **High** |
| Customer Service | Medium | High | **Medium-High** |
| Technical FM Skills | Low-Medium | High | **High** |
| Sales/Negotiation | Medium | High | **Medium** |
| Financial Analysis | Medium | High | **Medium** |

## 7.5 Labor Market Characteristics

| Characteristic | Egypt | Saudi Arabia | UAE | Jordan |
|---------------|-------|--------------|-----|--------|
| Local vs Expat | 95%+ local | 35/65 | 15/85 | 80/20 |
| Turnover (Sales) | 30-45% | 35-50% | 40-60% | 30-45% |
| Turnover (Operations) | 20-30% | 25-40% | 30-45% | 20-35% |
| Female Participation | 20-30% | 15-25% (growing) | 30-40% | 25-35% |
| Commission-Based | Common | Common | Very common | Common |
| Nationalization | N/A | High priority | Moderate | N/A |

## 7.6 HR KPIs

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| Agent Turnover | >50% | 35-50% | 20-35% | <20% |
| Operations Turnover | >35% | 25-35% | 15-25% | <15% |
| Revenue/Employee | <$40K | $40-70K | $70-120K | >$120K |
| Training Hours/Year | <20 | 20-40 | 40-60 | >60 |
| Agent Productivity | <6 deals | 6-12 | 12-20 | >20 |
| Time to Productivity | >6 mo | 4-6 mo | 2-4 mo | <2 mo |

---

*End of Part 2 - Continue to Part 3 for Dimensions 8-11*
# Dimension 8: Supply Chain

## 8.1 Input Categories

### Development Inputs

| Category | % of Costs | Import Dependency | Key Suppliers |
|----------|-----------|-------------------|---------------|
| Land | 15-35% | N/A (local) | Landowners, government |
| Construction | 45-65% | Medium (30-50%) | Contractors |
| Professional Services | 5-10% | Medium | Architects, engineers |
| Marketing | 3-8% | Low | Agencies |
| Finance | 5-12% | Medium | Banks, investors |
| Permits/Fees | 2-5% | N/A | Government |

### Service Company Inputs

| Category | % of Costs | Key Sources |
|----------|-----------|-------------|
| Labor | 50-70% | Local labor market |
| Materials/Supplies | 10-25% | Local distributors |
| Technology | 5-12% | Software vendors |
| Subcontractors | Variable | Specialized services |
| Insurance | 2-5% | Insurance companies |
| Utilities | 2-8% | Utility providers |

## 8.2 Key Supplier Relationships

### Development

| Supplier Type | Relationship | Terms |
|---------------|--------------|-------|
| Land Sellers | Transaction | Negotiated |
| General Contractors | Contract | Progress payments |
| Architects/Engineers | Professional fees | Milestone-based |
| Banks/Lenders | Loan agreements | Market terms |
| Marketing Agencies | Project-based | Monthly/milestone |
| Sales Agencies | Commission | On completion |

### Services (PM/FM)

| Supplier Type | Relationship | Terms |
|---------------|--------------|-------|
| Cleaning Supplies | Ongoing | Net 30 |
| Equipment/Parts | As needed | Net 30-60 |
| Subcontractors | Contract | Per work order |
| Technology Vendors | Annual | Subscription |
| Uniforms | Periodic | As ordered |
| Security Equipment | Project | Purchase/lease |

## 8.3 Subcontracting Models

### FM Subcontracting

| Service | Typically Subcontracted | Reason |
|---------|------------------------|--------|
| Specialized MEP | Often | Technical expertise |
| Deep Cleaning | Sometimes | Equipment |
| Landscaping | Often | Specialized |
| Pest Control | Usually | Licensed |
| Fire Systems | Usually | Specialized |
| Elevators | Always | Manufacturer |
| Security | Sometimes | Licensed |

### Development Subcontracting

| Service | Model | Typical Terms |
|---------|-------|---------------|
| General Construction | Main contractor | Fixed/GMP |
| MEP Works | Subcontract | Fixed |
| Finishing | Subcontract | Fixed |
| Sales | In-house or agency | Commission |
| Marketing | Agency | Fee + media |

## 8.4 Procurement Considerations

### Make vs Buy

| Function | In-House | Outsource | Hybrid |
|----------|----------|-----------|--------|
| Development PM | Usually | Sometimes | - |
| Sales | Usually | Sometimes | Common |
| Property Management | Core | Specialized | - |
| Hard FM Services | Core | Specialized | Common |
| Soft FM Services | Sometimes | Often | Common |
| Security | Sometimes | Often | - |

### Vendor Management

| Category | Approach | Review Frequency |
|----------|----------|------------------|
| Critical Suppliers | Partnership | Quarterly |
| Regular Suppliers | Managed | Semi-annual |
| Commodities | Competitive | Annual tender |
| Specialized | Relationship | Per project |

---

# Dimension 9: Export Requirements

## 9.1 Cross-Border Opportunities

### Service Export

| Service | Export Method | Target Markets |
|---------|---------------|----------------|
| PM/FM Services | Regional expansion | Adjacent markets |
| Advisory | Project-based | Regional |
| Development Expertise | JV, management | New markets |
| PropTech | SaaS model | Regional |

### Investment Export

| Vehicle | Structure | Markets |
|---------|-----------|---------|
| Development JV | Partnership | New markets |
| Fund Investment | Capital deployment | Regional |
| Management Contract | Fee-based | Regional |
| Brand License | Franchise | New markets |

## 9.2 International Standards

### Professional Standards

| Standard | Application | Recognition |
|----------|-------------|-------------|
| RICS Valuation Standards | Valuation | Global |
| IFRS 16 | Lease accounting | Global |
| IVS (International Valuation) | Valuation | Global |
| BOMA Standards | Measurement | International |
| ISO 41001 | FM management | Global |

### Building Standards

| Standard | Application | Recognition |
|----------|-------------|-------------|
| LEED | Green building | Global |
| BREEAM | Sustainability | International |
| WELL | Wellness | Growing |
| Estidama (UAE) | Regional green | UAE/Gulf |
| Mostadam (Saudi) | Saudi sustainability | Saudi |

## 9.3 Market Entry Considerations

### Entry Modes

| Mode | Investment | Control | Risk |
|------|------------|---------|------|
| Organic Expansion | High | Full | High |
| Acquisition | High | Full | Medium-High |
| Joint Venture | Shared | Shared | Medium |
| Partnership | Low | Limited | Low |
| Franchise | Low | Limited | Low |

### Key Considerations

| Factor | Assessment Needs |
|--------|------------------|
| Licensing | Local requirements |
| Local Partner | Necessity, selection |
| Market Understanding | Research, networks |
| Capital | Investment requirements |
| Talent | Local hiring, relocation |

---

# Dimension 10: Packaging & Labeling

## 10.1 Service Packaging

### Development Products

| Package | Target | Components |
|---------|--------|------------|
| Affordable Housing | First-time buyers | Basic specs, financing |
| Mid-Market | Upgraders | Standard, amenities |
| Luxury | High-net-worth | Premium, services |
| Investment | Investors | Yield focus, management |
| Off-Plan | Price-sensitive | Discount, payment plan |

### Service Products

| Package | Components | Pricing |
|---------|------------|---------|
| Basic PM | Rent collection, basic maint | % of rent |
| Full PM | Comprehensive management | Higher % |
| Soft FM Only | Cleaning, security | Per sqm |
| Technical FM | MEP, maintenance | Per sqm |
| Integrated FM | Full service | Per sqm bundle |
| Asset Management | Strategic + operational | % of AUM |

### Brokerage Services

| Package | Components | Pricing |
|---------|------------|---------|
| Standard Agency | Marketing, viewings, negotiation | Commission |
| Premium/Exclusive | Dedicated service, marketing | Higher commission |
| Buyer Representation | Search, due diligence | Buyer fee/shared |
| Investment Advisory | Analysis, sourcing | Fee + commission |

## 10.2 Marketing Collateral

### Development Marketing

| Material | Purpose | Channel |
|----------|---------|---------|
| Project Brochure | Sales tool | Direct, showroom |
| Website/Microsite | Digital presence | Online |
| Show Unit/Apartment | Experience | On-site |
| Video/Virtual Tour | Remote viewing | Digital |
| Payment Plan | Financing | Sales |
| Floor Plans | Specifications | All |

### Service Company Marketing

| Material | Purpose | Channel |
|----------|---------|---------|
| Capability Statement | Credibility | Proposals |
| Case Studies | Proof points | Proposals, web |
| Service Catalog | Offerings | Direct |
| Accreditations | Trust | All |
| Client References | Social proof | Proposals |

## 10.3 Contract Standards

### Development Contracts

| Contract | Parties | Key Terms |
|----------|---------|-----------|
| SPA (Sale Purchase) | Developer-Buyer | Payment, handover |
| Reservation | Developer-Buyer | Deposit, terms |
| Construction | Developer-Contractor | Scope, schedule, payment |
| Professional Services | Developer-Consultant | Scope, fees |

### Service Contracts

| Contract | Parties | Key Terms |
|----------|---------|-----------|
| PM Agreement | Owner-PM Company | Scope, fees, term |
| FM Contract | Client-FM Provider | SLAs, KPIs, pricing |
| Lease Agreement | Landlord-Tenant | Rent, term, conditions |
| OA Agreement | Association-Manager | Scope, fees |

## 10.4 Reporting Standards

### Property Management Reports

| Report | Frequency | Content |
|--------|-----------|---------|
| Financial Statement | Monthly | Income, expenses |
| Rent Roll | Monthly | Tenant, rent status |
| Occupancy Report | Monthly | Units, vacancies |
| Maintenance Log | Monthly | Work orders, status |
| Budget vs Actual | Monthly | Variance analysis |
| Annual Report | Yearly | Comprehensive review |

### FM Reports

| Report | Frequency | Content |
|--------|-----------|---------|
| SLA Performance | Monthly | KPIs vs targets |
| Work Order Summary | Weekly/Monthly | Reactive, PPM |
| Safety Report | Monthly | Incidents, compliance |
| Energy Report | Monthly | Consumption, efficiency |
| Quality Audit | Quarterly | Inspection results |

---

# Dimension 11: MENA Regional Context

## 11.1 Country Profiles

### UAE

| Attribute | Details |
|-----------|---------|
| **Market Size** | $80-120 billion |
| **Key Segments** | Residential, commercial, hospitality |
| **Characteristics** | Most developed, regulated, competitive |
| **Challenges** | Oversupply (some segments), price correction |
| **Opportunities** | Services, niche development, PropTech |
| **Regulatory** | RERA (Dubai), strong framework |

### Saudi Arabia

| Attribute | Details |
|-----------|---------|
| **Market Size** | $60-100 billion |
| **Key Segments** | Residential (Vision 2030), commercial, mega-projects |
| **Characteristics** | Fastest growth, Vision 2030 transformation |
| **Challenges** | Capacity, Saudization, new market |
| **Opportunities** | Mega-projects, affordable housing, services |
| **Regulatory** | REGA, evolving framework |

### Egypt

| Attribute | Details |
|-----------|---------|
| **Market Size** | $20-35 billion |
| **Key Segments** | Residential, new cities, commercial |
| **Characteristics** | Large market, high informality, new developments |
| **Challenges** | Currency, registration, informality |
| **Opportunities** | Formalization, new cities, services |
| **Regulatory** | Developing framework |

### Jordan

| Attribute | Details |
|-----------|---------|
| **Market Size** | $5-8 billion |
| **Key Segments** | Residential, commercial, refugee housing |
| **Characteristics** | Stable, smaller market, regional factors |
| **Challenges** | Economic constraints, regional instability |
| **Opportunities** | Services, specific segments |
| **Regulatory** | Established framework |

### Morocco

| Attribute | Details |
|-----------|---------|
| **Market Size** | $15-25 billion |
| **Key Segments** | Social housing, tourism, commercial |
| **Characteristics** | Government focus on housing, tourism development |
| **Challenges** | Affordability, informality |
| **Opportunities** | Social housing, tourism, Africa gateway |
| **Regulatory** | French-influenced framework |

## 11.2 Vision 2030 Impact (Saudi Arabia)

### Mega-Projects

| Project | Investment | Status | RE Opportunity |
|---------|------------|--------|----------------|
| NEOM | $500B+ | Development | All segments |
| Red Sea | $16B | Opening | Hospitality, residential |
| Qiddiya | $8B | Development | Entertainment, residential |
| Diriyah Gate | $20B+ | Development | Heritage, commercial |
| Roshn Communities | $70B+ | Rolling | Residential |
| King Abdullah Financial District | $10B+ | Operational | Commercial |

### Housing Targets

| Initiative | Target | Impact |
|------------|--------|--------|
| Home Ownership | 70% by 2030 | Massive development |
| Sakani Program | 300K+ homes/year | Affordable focus |
| REDF Financing | Expanded | Mortgage growth |

## 11.3 Property Cycles

### Current Market Position (2024-2025)

| Market | Cycle Phase | Outlook |
|--------|-------------|---------|
| **UAE - Dubai** | Recovery/growth | Positive |
| **UAE - Abu Dhabi** | Stable growth | Positive |
| **Saudi Arabia** | Strong growth | Very positive |
| **Egypt** | Correction/stabilization | Cautious |
| **Jordan** | Stable | Neutral |
| **Morocco** | Moderate growth | Positive |

### Key Drivers

| Driver | Impact |
|--------|--------|
| Interest Rates | Mortgage affordability |
| Oil Prices | Gulf economies |
| Population Growth | Demand fundamentals |
| Government Programs | Affordable housing |
| Foreign Investment | Demand, capital |
| Tourism | Hospitality demand |

## 11.4 Business Culture Considerations

| Aspect | Consideration |
|--------|---------------|
| Relationship-Based | Trust crucial in transactions |
| Family Ownership | Many developers family-controlled |
| Government Role | Major developer, regulator |
| Negotiation | Extended, flexibility expected |
| Payment Culture | Post-dated checks, installments |
| Ramadan | Reduced activity |
| Friday/Weekend | Thursday-Friday/Friday-Saturday |
| Wasta (Connections) | Relationships matter |

## 11.5 Investment Considerations

### Foreign Investment Rules

| Country | Access | Trends |
|---------|--------|--------|
| UAE | Designated freehold areas | Expanding |
| Saudi | Expanding access | Major reforms |
| Egypt | Generally open | Encouraging |
| Jordan | With approval | Open |
| Morocco | Generally open | Encouraging |

### Financing Environment

| Aspect | UAE | Saudi | Egypt |
|--------|-----|-------|-------|
| Mortgage Availability | Good | Growing | Limited |
| Development Finance | Good | Growing | Challenging |
| Interest Rates | 5-8% | 5-7% | 15-25%+ |
| LTV Ratios | 60-80% | 70-90% | 50-70% |

## 11.6 Strategic Opportunities

| Opportunity | Markets | Potential | Requirements |
|-------------|---------|-----------|--------------|
| Vision 2030 Services | Saudi | **Very High** | Presence, capacity |
| Affordable Housing | Egypt, Morocco | **High** | Government relationships |
| PropTech | All | **High** | Technology, capital |
| FM Consolidation | All | **High** | Scale, operations |
| Green Buildings | UAE, Saudi | **High** | Expertise |
| Industrial/Logistics | All | **High** | Sector knowledge |
| Senior Living | UAE, Saudi | **Medium-High** | Emerging market |
| Student Housing | All | **Medium-High** | Education partnerships |

---

# Document Summary

## Sector Overview

**Real Estate** in MENA represents:

**Market Size & Growth:**
- ~$200-350 billion total market
- Vision 2030 driving massive investment in Saudi
- Strong fundamentals (demographics, urbanization)
- Services sector growing 10-18% annually

**Key Characteristics:**
- Capital-intensive development segment
- Service businesses (PM/FM) more accessible for SMEs
- Relationship-driven transactions
- Regulatory modernization ongoing
- PropTech adoption accelerating
- Cycles and oversupply in some segments

**SME Landscape:**
- Development: Requires significant capital; niche opportunities
- Brokerage: Accessible entry; fragmented market
- Property Management: Growing demand; professionalization
- Facilities Management: Strong opportunity; consolidating
- Advisory/Valuation: Expertise-driven; RICS important

**Priority Subsectors:**
1. **Facilities Management** - Growing, consolidating, recurring
2. **Property Management** - Professionalization trend
3. **PropTech** - High growth, transformation
4. **Brokerage** - Accessible, but competitive
5. **Development Services** - Support mega-projects

## Critical Insights for SME Diagnostics

### Key Success Factors

1. **Capital Access** - Critical for development
2. **Client Relationships** - Transaction-driven
3. **Operational Excellence** - PM/FM differentiation
4. **Technology Adoption** - Competitive advantage
5. **Regulatory Compliance** - License maintenance
6. **Team Quality** - Sales agents, technicians

### Red Flags to Assess

- High agent turnover (>50%)
- Low collection rates (<90%)
- Poor occupancy management
- No technology systems
- License/compliance gaps
- Single client dependency

### Upside Indicators

- Strong retention (clients, staff)
- High collection rates (>97%)
- Technology-enabled operations
- Multiple revenue streams
- Quality certifications
- Vision 2030 positioning (Saudi)

## Agent Usage Guide

| Agent | Primary Dimensions | Key Data Points |
|-------|-------------------|-----------------|
| **The Drucker** | 1, 11 | Subsector classification, regional context |
| **The Marvin** | 3, 4 | Operational KPIs, regulatory compliance |
| **The Graham** | 2 | Development IRR, yields, PM margins |
| **The Ricardo** | 9, 10 | International standards, service packaging |
| **The Lovelace** | 6 | PropTech adoption, CAFM/CMMS |
| **The Mayo** | 7 | Compensation, agent productivity |
| **The Ohno** | 8 | Subcontracting, procurement |
| **The Porter** | 5 | Market dynamics, cycles |
| **The Landor** | 10 | Marketing, contracts |

## Cross-Sector Integration

| Connected Sector | Real Estate Integration |
|------------------|------------------------|
| Construction | Development execution |
| Financial Services | Mortgages, investment |
| Hospitality | Hotel properties |
| Retail | Retail properties |
| Professional Services | Legal, advisory |
| Logistics | Industrial properties |

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | December 2025 | RootRise Product Team | Initial release |

---

*This document is part of the RootRise Sector Knowledge Pack series, providing comprehensive sector intelligence for The Pantheon multi-agent diagnostic system.*
