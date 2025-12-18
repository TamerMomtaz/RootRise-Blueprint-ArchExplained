# RootRise Sector Knowledge Pack
# Financial Services
## Version 1.0 | December 2025

---

# Document Information

| Attribute | Value |
|-----------|-------|
| **Sector ID** | `financial_services` |
| **Version** | 1.0 |
| **Last Updated** | December 2025 |
| **Status** | Active |
| **ISIC Rev.4 Divisions** | 64 (Financial Services), 65 (Insurance), 66 (Auxiliary Financial Services) |
| **Primary Markets** | Egypt, Saudi Arabia, UAE, Jordan, Morocco |
| **SME Employee Range** | 5-200 |
| **SME Revenue Range** | $200K - $30M |

## Sector Overview

Financial Services in MENA is experiencing **transformative disruption** driven by fintech innovation, regulatory modernization, open banking initiatives, and Vision 2030 financial sector development plans. The sector enables ALL other economic sectors through banking, insurance, investment, and payment services.

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                    FINANCIAL SERVICES VALUE CHAIN                                │
├─────────────────────────────────────────────────────────────────────────────────┤
│                                                                                  │
│   BANKING & CREDIT                    INSURANCE                                 │
│   ────────────────                    ─────────                                 │
│                                                                                  │
│   ┌──────────────┐                    ┌──────────────────────┐                  │
│   │ RETAIL       │                    │  GENERAL INSURANCE   │                  │
│   │ BANKING      │                    │  • Motor             │                  │
│   │ • Deposits   │                    │  • Property          │                  │
│   │ • Loans      │                    │  • Liability         │                  │
│   │ • Cards      │                    │  • Marine/Aviation   │                  │
│   │ • Mortgages  │                    │  • Engineering       │                  │
│   └──────────────┘                    └──────────────────────┘                  │
│                                                                                  │
│   ┌──────────────┐                    ┌──────────────────────┐                  │
│   │ SME/CORPORATE│                    │  LIFE & HEALTH       │                  │
│   │ BANKING      │                    │  INSURANCE           │                  │
│   │ • Working cap│                    │  • Life              │                  │
│   │ • Trade fin  │                    │  • Health            │                  │
│   │ • Treasury   │                    │  • Pensions          │                  │
│   └──────────────┘                    └──────────────────────┘                  │
│                                                                                  │
│   FINTECH & PAYMENTS                  INVESTMENT & WEALTH                       │
│   ──────────────────                  ───────────────────                       │
│                                                                                  │
│   ┌──────────────┐                    ┌──────────────────────┐                  │
│   │ PAYMENTS     │                    │  ASSET MANAGEMENT    │                  │
│   │ • Digital    │                    │  • Mutual funds      │                  │
│   │ • Mobile     │                    │  • ETFs              │                  │
│   │ • Gateways   │                    │  • Private equity    │                  │
│   │ • BNPL       │                    │  • REITs             │                  │
│   └──────────────┘                    └──────────────────────┘                  │
│                                                                                  │
│   ┌──────────────┐                    ┌──────────────────────┐                  │
│   │ LENDING TECH │                    │  WEALTH MANAGEMENT   │                  │
│   │ • P2P        │                    │  • Private banking   │                  │
│   │ • SME lending│                    │  • Family offices    │                  │
│   │ • Microfinance│                   │  • Advisory          │                  │
│   └──────────────┘                    └──────────────────────┘                  │
│                                                                                  │
│   KEY MENA CHARACTERISTICS:                                                     │
│   • Islamic finance significant (20-40% of banking)                            │
│   • Fintech boom (highest regional growth globally)                            │
│   • Vision 2030 financial sector development                                   │
│   • Open banking regulatory push (Saudi, Bahrain, UAE)                         │
│   • High unbanked population (opportunity)                                     │
│   • Cash-to-digital transition accelerating                                    │
│   • Regulatory sandboxes enabling innovation                                   │
│                                                                                  │
└─────────────────────────────────────────────────────────────────────────────────┘
```

## Applicable Countries

| Country Code | Country Name | Market Size Estimate | Key Drivers |
|--------------|--------------|---------------------|-------------|
| EG | Egypt | $15-25 billion | Population, financial inclusion |
| SA | Saudi Arabia | $80-120 billion | Vision 2030, diversification |
| AE | UAE | $100-150 billion | Regional hub, innovation |
| JO | Jordan | $5-8 billion | Stability, fintech |
| MA | Morocco | $20-30 billion | Africa gateway, microfinance |

---

# Dimension 1: Industry Classification

## 1.1 ISIC Rev.4 Classification

### Primary ISIC Codes

| Division | Description | SME Relevance |
|----------|-------------|---------------|
| **64** | Financial service activities, except insurance and pension | **High** |
| **65** | Insurance, reinsurance and pension funding | **High** |
| **66** | Activities auxiliary to financial service and insurance | **Very High** |

### Detailed Class Breakdown

**Division 64 - Financial Services:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| 6411 | Central banking | N/A |
| **6419** | **Other monetary intermediation** | **Medium** |
| **6491** | **Financial leasing** | **High** |
| **6492** | **Other credit granting** | **Very High** |
| **6499** | **Other financial service activities n.e.c.** | **Very High** |

**Division 65 - Insurance:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| **6511** | **Life insurance** | **Medium** |
| **6512** | **Non-life insurance** | **High** |
| 6520 | Reinsurance | Low |
| **6530** | **Pension funding** | **Medium** |

**Division 66 - Auxiliary Financial Services:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| **6611** | **Administration of financial markets** | **Low** |
| **6612** | **Security and commodity contracts brokerage** | **High** |
| **6619** | **Other activities auxiliary to financial services** | **Very High** |
| **6621** | **Risk and damage evaluation** | **High** |
| **6622** | **Activities of insurance agents and brokers** | **Very High** |
| **6629** | **Other activities auxiliary to insurance** | **High** |
| **6630** | **Fund management activities** | **High** |

## 1.2 Subsector Taxonomy

```json
{
  "subsectors": [
    {
      "subsector_id": "digital_banking",
      "subsector_name": "Digital & Challenger Banks",
      "subsector_name_ar": "البنوك الرقمية",
      "description": "Digital-first banking, neobanks, challenger banks",
      "isic_codes": ["6419", "6499"],
      "typical_sme_size": "20-150 employees",
      "typical_sme_revenue": "$2M-$30M",
      "mena_market_size_estimate": "$2-5 billion",
      "growth_rate_5yr": "30-50%",
      "key_segments": ["Retail neobank", "SME digital bank", "Islamic digital"]
    },
    {
      "subsector_id": "payment_services",
      "subsector_name": "Payment Services & Processing",
      "subsector_name_ar": "خدمات الدفع",
      "description": "Payment gateways, processors, digital wallets, POS",
      "isic_codes": ["6619", "6499"],
      "typical_sme_size": "15-120 employees",
      "typical_sme_revenue": "$1M-$25M",
      "mena_market_size_estimate": "$8-15 billion",
      "growth_rate_5yr": "20-35%",
      "key_segments": ["Gateways", "Wallets", "POS/mPOS", "Cross-border"]
    },
    {
      "subsector_id": "lending_credit",
      "subsector_name": "Alternative Lending & Credit",
      "subsector_name_ar": "الإقراض البديل",
      "description": "P2P lending, SME lending, BNPL, microfinance",
      "isic_codes": ["6492", "6499"],
      "typical_sme_size": "20-100 employees",
      "typical_sme_revenue": "$1M-$20M",
      "mena_market_size_estimate": "$5-12 billion",
      "growth_rate_5yr": "25-45%",
      "key_segments": ["SME lending", "BNPL", "Microfinance", "P2P"]
    },
    {
      "subsector_id": "insurance_broking",
      "subsector_name": "Insurance Broking & Distribution",
      "subsector_name_ar": "وساطة التأمين",
      "description": "Insurance brokers, agents, aggregators, digital insurance",
      "isic_codes": ["6622", "6629"],
      "typical_sme_size": "5-80 employees",
      "typical_sme_revenue": "$300K-$15M",
      "mena_market_size_estimate": "$3-6 billion",
      "growth_rate_5yr": "8-15%",
      "key_segments": ["Corporate broker", "Retail agent", "Digital/insurtech"]
    },
    {
      "subsector_id": "insurance_underwriting",
      "subsector_name": "Insurance Underwriting",
      "subsector_name_ar": "التأمين",
      "description": "General insurance, life insurance, takaful",
      "isic_codes": ["6511", "6512"],
      "typical_sme_size": "50-200 employees",
      "typical_sme_revenue": "$5M-$50M (GWP)",
      "mena_market_size_estimate": "$40-60 billion",
      "growth_rate_5yr": "6-12%",
      "key_segments": ["General", "Life", "Health", "Takaful"]
    },
    {
      "subsector_id": "wealth_management",
      "subsector_name": "Wealth Management & Advisory",
      "subsector_name_ar": "إدارة الثروات",
      "description": "Private banking, family offices, investment advisory",
      "isic_codes": ["6630", "6619"],
      "typical_sme_size": "10-80 employees",
      "typical_sme_revenue": "$500K-$20M",
      "mena_market_size_estimate": "$5-10 billion (fees)",
      "growth_rate_5yr": "10-18%",
      "key_segments": ["HNW advisory", "Family office", "Robo-advisory"]
    },
    {
      "subsector_id": "asset_management",
      "subsector_name": "Asset Management",
      "subsector_name_ar": "إدارة الأصول",
      "description": "Mutual funds, ETFs, private equity, real estate funds",
      "isic_codes": ["6630"],
      "typical_sme_size": "10-60 employees",
      "typical_sme_revenue": "$1M-$15M (fees)",
      "mena_market_size_estimate": "$8-15 billion (fees)",
      "growth_rate_5yr": "12-20%",
      "key_segments": ["Mutual funds", "Private equity", "REITs", "Islamic funds"]
    },
    {
      "subsector_id": "capital_markets",
      "subsector_name": "Capital Markets & Brokerage",
      "subsector_name_ar": "أسواق المال والوساطة",
      "description": "Securities brokerage, investment banking, trading",
      "isic_codes": ["6612", "6619"],
      "typical_sme_size": "15-100 employees",
      "typical_sme_revenue": "$1M-$25M",
      "mena_market_size_estimate": "$4-8 billion",
      "growth_rate_5yr": "10-18%",
      "key_segments": ["Retail brokerage", "Institutional", "Investment banking"]
    },
    {
      "subsector_id": "financial_leasing",
      "subsector_name": "Leasing & Asset Finance",
      "subsector_name_ar": "التأجير التمويلي",
      "description": "Equipment leasing, vehicle finance, asset-based lending",
      "isic_codes": ["6491"],
      "typical_sme_size": "15-80 employees",
      "typical_sme_revenue": "$2M-$30M",
      "mena_market_size_estimate": "$10-20 billion",
      "growth_rate_5yr": "8-15%",
      "key_segments": ["Equipment", "Vehicle", "Real estate"]
    },
    {
      "subsector_id": "fintech_infrastructure",
      "subsector_name": "Fintech Infrastructure & B2B",
      "subsector_name_ar": "البنية التحتية للتقنية المالية",
      "description": "Core banking, APIs, KYC/AML, regtech, embedded finance",
      "isic_codes": ["6619", "6499"],
      "typical_sme_size": "20-150 employees",
      "typical_sme_revenue": "$1M-$20M",
      "mena_market_size_estimate": "$2-5 billion",
      "growth_rate_5yr": "25-40%",
      "key_segments": ["Core banking SaaS", "Open banking", "Regtech", "Embedded finance"]
    }
  ]
}
```

## 1.3 Islamic Finance

### Sharia-Compliant Products

| Product Type | Conventional Equivalent | Key Principles |
|--------------|------------------------|----------------|
| Murabaha | Cost-plus financing | Disclosed margin |
| Ijara | Leasing | Asset ownership |
| Musharaka | Partnership | Profit/loss sharing |
| Sukuk | Bonds | Asset-backed |
| Takaful | Insurance | Mutual cooperation |
| Wakala | Agency | Fee-based |
| Mudaraba | Trust financing | Profit sharing |

### Islamic Finance Market Share

| Country | Islamic Banking % | Takaful % | Growth |
|---------|------------------|-----------|--------|
| Saudi Arabia | 70-80% | 50-60% | Dominant |
| UAE | 25-30% | 15-20% | Growing |
| Egypt | 5-8% | 3-5% | Emerging |
| Jordan | 15-20% | 10-15% | Stable |
| Morocco | 3-5% | 2-3% | New |

## 1.4 Value Chain Position

| Position | Description | Typical SME Type | Margin Profile |
|----------|-------------|------------------|----------------|
| **Full-Stack Provider** | End-to-end financial services | Digital banks, insurers | NIM 3-8%, ROE 10-25% |
| **Infrastructure Provider** | Enable others to deliver | Fintech B2B, processors | Recurring SaaS |
| **Distribution** | Connect products to customers | Brokers, agents, aggregators | Commission 5-25% |
| **Advisory** | Provide expertise | Wealth managers, consultants | Fee-based 0.5-2% |
| **Specialist** | Niche product/segment | BNPL, trade finance | Product-specific |

## 1.5 Adjacent Sectors

| Adjacent Sector | Relationship | Integration Level |
|-----------------|--------------|-------------------|
| **Technology** | Fintech development | Very High |
| **Professional Services** | Audit, legal, consulting | High |
| **Real Estate** | Mortgages, REITs | High |
| **Retail** | Payments, BNPL | Very High |
| **ALL Sectors** | Banking, insurance, payments | Universal |

---

# Dimension 2: Financial Benchmarks

## 2.1 Banking Metrics

### Net Interest Margin (NIM) by Country

| Country | Traditional Banks | Digital Banks | Microfinance |
|---------|------------------|---------------|--------------|
| Egypt | 4-7% | 6-10% | 15-30% |
| Saudi Arabia | 2.5-4% | 4-7% | 8-15% |
| UAE | 2-3.5% | 3.5-6% | N/A |
| Jordan | 3-5% | 4-7% | 10-20% |
| Morocco | 3-4.5% | 4-7% | 12-25% |

### Digital Bank / Neobank Metrics

| Metric | Seed Stage | Growth | Mature |
|--------|------------|--------|--------|
| **CAC (Customer Acquisition)** | $30-100 | $15-50 | $8-25 |
| **ARPU (Monthly)** | $2-8 | $8-20 | $15-40 |
| **LTV:CAC** | 0.5-2x | 2-4x | 4-8x |
| **Monthly Active Users** | 20-40% | 40-60% | 55-75% |
| **Cost to Serve** | $3-8/user | $2-5/user | $1-3/user |

### SME/Alternative Lending

| Metric | P2P Lending | SME Digital | Microfinance |
|--------|------------|-------------|--------------|
| **Loan Yield** | 12-25% | 15-35% | 25-50% |
| **NPL Rate** | 3-10% | 5-15% | 5-12% |
| **Cost of Risk** | 2-6% | 4-10% | 4-8% |
| **Operating Cost Ratio** | 3-8% | 5-12% | 12-25% |
| **ROE** | 8-18% | 12-25% | 15-30% |

## 2.2 Payment Services Metrics

### Payment Gateway/Processor

| Metric | Small | Mid-Size | Large |
|--------|-------|----------|-------|
| **Transaction Volume/Month** | <$5M | $5-50M | >$50M |
| **Take Rate (MDR)** | 2-4% | 1.5-3% | 1-2.5% |
| **Net Take Rate** | 0.3-0.8% | 0.2-0.6% | 0.15-0.4% |
| **Revenue/Transaction** | $0.3-1.5 | $0.2-0.8 | $0.1-0.5 |
| **Gross Margin** | 25-45% | 30-50% | 40-60% |

### Digital Wallet

| Metric | Early | Growth | Scale |
|--------|-------|--------|-------|
| **Users** | <100K | 100K-1M | >1M |
| **Monthly Transacting %** | 15-30% | 30-50% | 45-65% |
| **ARPU** | $0.5-2 | $2-8 | $5-15 |
| **Interchange/Float Income** | Primary | Growing | Diversified |

## 2.3 Insurance Metrics

### Insurance Company Ratios

| Ratio | Poor | Average | Good | Excellent |
|-------|------|---------|------|-----------|
| **Combined Ratio** | >110% | 100-110% | 90-100% | <90% |
| **Loss Ratio** | >75% | 65-75% | 55-65% | <55% |
| **Expense Ratio** | >40% | 32-40% | 25-32% | <25% |
| **ROE** | <8% | 8-12% | 12-18% | >18% |
| **Solvency Ratio** | <120% | 120-150% | 150-200% | >200% |

### Insurance Broker/Agent Metrics

| Metric | Small | Mid-Size | Large |
|--------|-------|----------|-------|
| **GWP Managed** | <$5M | $5-50M | >$50M |
| **Commission Rate** | 10-20% | 12-22% | 15-25% |
| **Revenue/Employee** | $50-100K | $80-150K | $120-250K |
| **Client Retention** | 75-85% | 82-90% | 88-95% |
| **Operating Margin** | 15-25% | 20-32% | 25-40% |

## 2.4 Wealth & Asset Management

### Asset Management Fees

| Product Type | Management Fee | Performance Fee |
|--------------|---------------|-----------------|
| Mutual Funds (Active) | 1-2% | 0-20% |
| ETFs/Index | 0.1-0.5% | N/A |
| Private Equity | 1.5-2.5% | 15-25% |
| Hedge Funds | 1-2% | 15-25% |
| REITs | 0.5-1.5% | 0-15% |
| Islamic Funds | 1-2.5% | 0-20% |

### Wealth Management Profitability

| Metric | Robo-Advisory | Mass Affluent | HNW | UHNW |
|--------|--------------|---------------|-----|------|
| **AUM/Client** | $5-50K | $100K-1M | $1-10M | >$10M |
| **Revenue/AUM** | 0.25-0.75% | 0.5-1% | 0.75-1.5% | 0.5-1.2% |
| **Cost/Client** | $10-50 | $200-800 | $2K-10K | $10K-50K |
| **Margin** | 15-35% | 25-40% | 35-55% | 40-60% |

## 2.5 Capital Markets

### Brokerage Commission Rates

| Segment | Retail | Institutional |
|---------|--------|---------------|
| Equities | 0.1-0.5% | 0.02-0.15% |
| Fixed Income | 0.1-0.5% | 0.01-0.1% |
| Derivatives | $1-10/contract | $0.5-3/contract |
| Forex | 1-5 pips | 0.5-2 pips |

### Investment Banking Fees

| Service | Fee Range | Notes |
|---------|-----------|-------|
| IPO | 3-7% | Of proceeds |
| M&A Advisory | 1-5% | Of transaction |
| Debt Arrangement | 0.5-2% | Of amount |
| Rights Issue | 2-4% | Of proceeds |
| Sukuk Arrangement | 0.5-2% | Of issue size |

## 2.6 Working Capital & Capital Requirements

### Regulatory Capital

| License Type | Minimum Capital | Notes |
|--------------|-----------------|-------|
| Digital Bank | $10-100M | Varies by country |
| Payment Institution | $500K-10M | Varies by scope |
| Insurance Company | $10-50M | By line of business |
| Insurance Broker | $100K-1M | By category |
| Asset Manager | $1-10M | By AUM tier |
| Microfinance | $1-10M | By country |
| P2P Lending | $1-5M | Regulatory dependent |

### Working Capital Needs

| Subsector | Working Capital % | Cash Intensity |
|-----------|-------------------|----------------|
| Payments | 15-25% | High (settlement) |
| Insurance Broker | 10-20% | Medium |
| Lending | 80-200% | Very High (loan book) |
| Wealth Management | 10-20% | Low |
| Brokerage | 20-40% | High (settlements) |

## 2.7 Valuation Multiples

| Subsector | Revenue Multiple | P/E Multiple | Key Drivers |
|-----------|------------------|--------------|-------------|
| Digital Banks | 3-15x | 20-50x | Growth, engagement |
| Payments | 5-15x | 25-50x | Volume, growth |
| Alternative Lending | 1-5x | 8-20x | Loan book, NPL |
| Insurance Broker | 1-3x | 8-15x | Retention, commission |
| Insurance Company | 0.5-1.5x GWP | 8-15x | Combined ratio |
| Wealth Management | 1-3% AUM | 10-20x | AUM, retention |
| Asset Management | 2-5% AUM | 10-25x | Performance, flows |

---

# Dimension 3: Operational KPIs

## 3.1 Digital Banking KPIs

### Customer Metrics

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Customer Growth** | Monthly new users | <5% | 5-12% | 12-25% | >25% |
| **Activation Rate** | Active/registered | <30% | 30-50% | 50-70% | >70% |
| **MAU/Total Users** | Monthly active | <25% | 25-45% | 45-65% | >65% |
| **App Rating** | Store rating | <4.0 | 4.0-4.3 | 4.3-4.6 | >4.6 |
| **NPS** | Net Promoter | <30 | 30-50 | 50-70 | >70 |
| **Churn Rate** | Monthly churn | >5% | 3-5% | 1-3% | <1% |

### Financial Performance

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Revenue/User** | Monthly ARPU | <$5 | $5-15 | $15-30 | >$30 |
| **CAC Payback** | Months to recover | >24 | 18-24 | 12-18 | <12 |
| **Cost to Serve** | Per user/month | >$5 | $3-5 | $1.5-3 | <$1.5 |
| **Gross Margin** | After CoS | <40% | 40-55% | 55-70% | >70% |

## 3.2 Payment Services KPIs

### Volume Metrics

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **TPV Growth** | Transaction volume YoY | <20% | 20-40% | 40-70% | >70% |
| **Transaction Count** | Monthly transactions | Below target | On target | Above | 150%+ |
| **Average Transaction** | Value per txn | Depends on segment | - | - | - |
| **Success Rate** | Completed/attempted | <92% | 92-96% | 96-98.5% | >98.5% |
| **Uptime** | System availability | <99% | 99-99.5% | 99.5-99.9% | >99.9% |

### Business Metrics

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Merchant Acquisition** | New merchants/month | <100 | 100-500 | 500-2000 | >2000 |
| **Merchant Retention** | Annual retention | <85% | 85-92% | 92-97% | >97% |
| **Take Rate** | Revenue/TPV | Below target | Target | Above | Premium |
| **Net Take Rate** | Net revenue/TPV | <0.2% | 0.2-0.4% | 0.4-0.7% | >0.7% |

## 3.3 Lending KPIs

### Portfolio Quality

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **NPL Ratio** | Non-performing/total | >10% | 5-10% | 2-5% | <2% |
| **PAR 30** | 30+ days past due | >12% | 6-12% | 3-6% | <3% |
| **Write-off Rate** | Annual write-offs | >5% | 2-5% | 1-2% | <1% |
| **Collection Rate** | Collected/due | <85% | 85-92% | 92-97% | >97% |
| **Recovery Rate** | From written-off | <20% | 20-35% | 35-50% | >50% |

### Origination Efficiency

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Approval Rate** | Approved/applications | <30% | 30-50% | 50-70% | >70% |
| **Time to Decision** | Application to decision | >5 days | 2-5 days | 1-2 days | <24 hrs |
| **Time to Disbursement** | Decision to funds | >5 days | 2-5 days | 1-2 days | Same day |
| **Cost per Loan** | Origination cost | >$100 | $50-100 | $25-50 | <$25 |
| **Conversion Rate** | Disbursed/approved | <70% | 70-82% | 82-92% | >92% |

## 3.4 Insurance KPIs

### Underwriting

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Loss Ratio** | Claims/premiums | >75% | 65-75% | 55-65% | <55% |
| **Combined Ratio** | Loss + expense | >110% | 100-110% | 90-100% | <90% |
| **GWP Growth** | Premium growth | <3% | 3-8% | 8-15% | >15% |
| **Retention Rate** | Policy renewals | <75% | 75-85% | 85-92% | >92% |

### Claims Management

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Claims Ratio** | Paid/incurred | <85% | 85-92% | 92-98% | >98% |
| **Settlement Time** | Days to settle | >30 | 15-30 | 7-15 | <7 |
| **Claim Leakage** | Over-payment % | >8% | 4-8% | 2-4% | <2% |
| **Customer Satisfaction** | Claims NPS | <40 | 40-55 | 55-70 | >70 |

### Broker/Agent KPIs

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **GWP/Employee** | Productivity | <$200K | $200-500K | $500K-1M | >$1M |
| **Client Retention** | Annual renewal | <80% | 80-88% | 88-94% | >94% |
| **Cross-Sell Ratio** | Policies/client | <1.3 | 1.3-1.8 | 1.8-2.5 | >2.5 |
| **Quote Conversion** | Bound/quoted | <25% | 25-40% | 40-55% | >55% |

## 3.5 Wealth Management KPIs

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **AUM Growth** | Year-over-year | <5% | 5-12% | 12-22% | >22% |
| **Net New Money** | Inflows - outflows | Negative | 0-5% | 5-12% | >12% |
| **Client Retention** | AUM retention | <85% | 85-92% | 92-97% | >97% |
| **Revenue/AUM** | Fee yield | <0.5% | 0.5-0.8% | 0.8-1.2% | >1.2% |
| **Client Satisfaction** | NPS | <40 | 40-55 | 55-70 | >70 |

## 3.6 Compliance & Risk KPIs

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Regulatory Breaches** | Annual incidents | >5 | 2-5 | 1-2 | 0 |
| **AML Alert Rate** | False positive % | >95% | 90-95% | 85-90% | <85% |
| **Fraud Rate** | Fraud/transactions | >0.5% | 0.2-0.5% | 0.05-0.2% | <0.05% |
| **Capital Adequacy** | vs requirement | <110% | 110-130% | 130-160% | >160% |
| **Audit Findings** | Material issues | >3 | 1-3 | 0-1 | 0 |

---

*End of Part 1 - Continue to Part 2 for Dimensions 4-7*
# Dimension 4: Regulatory Landscape

## 4.1 Licensing Framework

### Banking & Credit Licenses

| License Type | Issuing Authority | Capital Requirement | Scope |
|--------------|-------------------|---------------------|-------|
| Commercial Bank | Central Bank | $50-300M+ | Full banking |
| Digital Bank License | Central Bank | $10-100M | Digital-only |
| Finance Company | Central Bank | $5-30M | Limited lending |
| Microfinance | Central Bank/MFI Regulator | $1-10M | Small loans |
| Payment Service Provider | Central Bank | $500K-10M | Payments only |
| E-Money Institution | Central Bank | $1-5M | Wallet/e-money |

### Insurance Licenses

| License Type | Issuing Authority | Capital Requirement | Scope |
|--------------|-------------------|---------------------|-------|
| General Insurance | Insurance Authority | $10-50M | Non-life |
| Life Insurance | Insurance Authority | $15-50M | Life/savings |
| Takaful Operator | Insurance Authority | $10-50M | Islamic |
| Insurance Broker | Insurance Authority | $100K-1M | Intermediary |
| Insurance Agent | Insurance Authority | $10-50K | Sales |
| TPA (Claims Admin) | Insurance Authority | $500K-2M | Admin only |

### Capital Markets Licenses

| License Type | Issuing Authority | Capital Requirement | Scope |
|--------------|-------------------|---------------------|-------|
| Securities Broker | Securities Regulator | $2-10M | Brokerage |
| Investment Manager | Securities Regulator | $1-10M | Asset management |
| Investment Advisor | Securities Regulator | $200K-2M | Advisory |
| Fund Administrator | Securities Regulator | $500K-2M | Fund services |
| Custody Services | Securities Regulator | $5-20M | Safekeeping |

### Fintech-Specific Licenses

| License Type | Availability | Requirements |
|--------------|--------------|--------------|
| Regulatory Sandbox | UAE, Saudi, Bahrain, Egypt | Application, testing period |
| Crowdfunding License | Saudi, UAE | $1-5M capital |
| P2P Lending | Limited/developing | Varies |
| Open Banking | Saudi, Bahrain (mandated) | Technical compliance |
| Crypto/Virtual Assets | UAE (VARA), Bahrain | Specialized license |

## 4.2 Regulatory Framework by Country

### Saudi Arabia (SAMA, CMA)

| Regulation | Description | Impact |
|------------|-------------|--------|
| Open Banking Framework | Mandated API standards | Enabling innovation |
| Fintech Permit | Sandbox and full license | Fintech growth |
| Insurance Regulations | SAMA supervision | Modernizing |
| Asset Management Rules | CMA oversight | Professional standards |
| AML/CFT | Enhanced requirements | Compliance cost |
| Vision 2030 Financial Sector | Development program | Massive opportunity |

### UAE (CBUAE, SCA, DFSA, ADGM)

| Regulation | Description | Impact |
|------------|-------------|--------|
| Stored Value Facility | E-wallet licensing | Payment innovation |
| DIFC/ADGM Framework | Financial free zones | International hub |
| VARA (Dubai) | Virtual assets regulation | Crypto licensing |
| Insurance Authority Law | Federal oversight | Standardization |
| Open Finance | Developing framework | Future growth |

### Egypt (CBE, FRA)

| Regulation | Description | Impact |
|------------|-------------|--------|
| Fintech Law | New regulatory framework | Enabling fintech |
| Mobile Payment | CBE licensing | Digital growth |
| Microfinance Law | FRA oversight | Financial inclusion |
| Insurance Law | FRA modernization | Market development |
| Capital Markets Law | FRA oversight | Market depth |

### Jordan (CBJ, JSC, Insurance Commission)

| Regulation | Description | Impact |
|------------|-------------|--------|
| Mobile Payment Regulation | CBJ licensing | Wallet growth |
| Fintech Sandbox | CBJ program | Innovation |
| Insurance Law | IC oversight | Modern framework |
| Securities Law | JSC regulation | Market standards |

### Morocco (BAM, ACAPS, AMMC)

| Regulation | Description | Impact |
|------------|-------------|--------|
| Banking Law | BAM oversight | Traditional framework |
| Payment Institution | BAM licensing | Growing |
| Insurance Code | ACAPS supervision | Developed market |
| Participative Banking | Islamic finance | New segment |
| Crowdfunding | AMMC regulation | Developing |

## 4.3 Compliance Requirements

### AML/KYC Requirements

| Requirement | Standard | Frequency |
|-------------|----------|-----------|
| Customer Due Diligence | Risk-based CDD | At onboarding |
| Enhanced Due Diligence | High-risk customers | As required |
| Transaction Monitoring | Automated screening | Continuous |
| Suspicious Activity Reports | Regulatory filing | Per incident |
| PEP Screening | Political exposure | Ongoing |
| Sanctions Screening | OFAC, UN, local | Real-time |
| Record Keeping | 5-10 years | Ongoing |

### Capital & Prudential

| Requirement | Standard | Frequency |
|-------------|----------|-----------|
| Capital Adequacy | Basel III / Local | Quarterly |
| Liquidity Coverage | LCR requirements | Monthly |
| Reserve Requirements | Central bank mandate | Ongoing |
| Solvency (Insurance) | Risk-based capital | Quarterly |
| Large Exposure Limits | Concentration rules | Ongoing |

### Consumer Protection

| Requirement | Standard | Impact |
|-------------|----------|--------|
| Disclosure Requirements | Fee transparency | All products |
| Cooling-Off Periods | Right to cancel | Insurance, lending |
| Complaint Handling | Resolution timelines | All services |
| Data Protection | Privacy laws | All customer data |
| Fair Lending | Non-discrimination | Credit products |

## 4.4 Key Regulators by Country

### Saudi Arabia

| Regulator | Responsibility |
|-----------|---------------|
| SAMA (Saudi Central Bank) | Banks, payments, insurance |
| CMA (Capital Market Authority) | Securities, funds |
| Fintech Saudi | Ecosystem development |

### UAE

| Regulator | Responsibility |
|-----------|---------------|
| CBUAE | Banks, payments, money changers |
| SCA | Securities (onshore) |
| DFSA | DIFC financial services |
| ADGM FSRA | ADGM financial services |
| IA | Insurance (onshore) |
| VARA | Virtual assets (Dubai) |

### Egypt

| Regulator | Responsibility |
|-----------|---------------|
| CBE | Banks, payments |
| FRA | Insurance, non-bank finance |
| EGX | Stock exchange |

### Jordan

| Regulator | Responsibility |
|-----------|---------------|
| CBJ | Banks, payments |
| JSC | Securities |
| Insurance Commission | Insurance |

### Morocco

| Regulator | Responsibility |
|-----------|---------------|
| BAM (Bank Al-Maghrib) | Banks, payments |
| ACAPS | Insurance, pensions |
| AMMC | Capital markets |

## 4.5 Professional Certifications

| Certification | Field | Recognition |
|---------------|-------|-------------|
| CFA | Investment | Global |
| FRM | Risk management | Global |
| ACCA/CPA | Accounting | Global |
| CFP | Financial planning | Global |
| CIA | Internal audit | Global |
| CAMS | AML compliance | Global |
| PMP | Project management | Global |
| Actuarial (FSA, FIA) | Insurance | Global |

---

# Dimension 5: Competitive Dynamics

## 5.1 Market Structure

| Subsector | Concentration | Market Leaders | Fragmentation |
|-----------|---------------|----------------|---------------|
| Traditional Banking | High | Top 5 banks dominate | Oligopoly |
| Digital Banking | Low (emerging) | Neobanks emerging | New entrants |
| Payments | Medium | Visa/MC + local | Consolidating |
| Insurance | Medium | Top 10 dominant | Moderate |
| Insurance Broking | Low | Fragmented | Highly fragmented |
| Asset Management | Medium | Bank-affiliated | Moderate |
| Wealth Management | High | Private banks | Concentrated |
| Microfinance | Low-Medium | Varies by country | Fragmented |

## 5.2 Porter's Five Forces

```
┌─────────────────────────────────────────────────────────────────────┐
│              FINANCIAL SERVICES FIVE FORCES                         │
├─────────────────────────────────────────────────────────────────────┤
│                                                                      │
│                  NEW ENTRANTS: 3/5                                  │
│                  (Regulatory barriers; but fintech disruption)      │
│                        │                                            │
│                        ▼                                            │
│   SUPPLIER POWER ────────────► INDUSTRY ◄───── BUYER POWER         │
│       2.5/5                    RIVALRY           3.5/5             │
│   (Capital, tech                 4/5         (Price comparison,     │
│    available)               (Intense,         switching easier      │
│                              margin pressure)   with digital)       │
│                        │                                            │
│                        ▼                                            │
│                SUBSTITUTES: 3/5                                     │
│                (Fintech, big tech, embedded finance)                │
│                                                                      │
│   OVERALL ATTRACTIVENESS: MODERATE                                  │
│   Key: Technology + Customer Experience + Regulatory Navigation    │
└─────────────────────────────────────────────────────────────────────┘
```

### Force Details

| Force | Rating | Key Factors |
|-------|--------|-------------|
| **New Entrants** | 3/5 | Regulatory barriers but fintech licenses emerging |
| **Supplier Power** | 2.5/5 | Capital available; technology commoditizing |
| **Buyer Power** | 3.5/5 | Digital enabling comparison; switching still has friction |
| **Substitutes** | 3/5 | Big tech entry; embedded finance; crypto |
| **Rivalry** | 4/5 | Intense competition; margin pressure; digital disruption |

## 5.3 Competitive Strategies

| Strategy | Description | Best For | Requirements |
|----------|-------------|----------|--------------|
| Digital-First | Superior digital experience | Neobanks, fintechs | Tech capability |
| Relationship | Deep client relationships | Wealth, corporate | Senior talent |
| Cost Leader | Lowest fees/rates | Mass market | Scale, efficiency |
| Niche Specialist | Specific segment focus | SME, diaspora | Deep understanding |
| Platform | Ecosystem enabler | B2B fintech | API, partnerships |
| Embedded | Integrate into other services | Payments, BNPL | Distribution |
| Islamic | Sharia-compliant focus | Religious segment | Sharia board |

## 5.4 Industry Trends

| Trend | Impact | Timeframe | SME Opportunity |
|-------|--------|-----------|-----------------|
| **Open Banking** | API economy, data sharing | 2-5 years | B2B fintech |
| **Embedded Finance** | Finance in non-finance apps | Ongoing | Integration |
| **BNPL Growth** | Alternative to credit | Ongoing | Consumer lending |
| **Digital Wallets** | Cash replacement | Ongoing | Payments |
| **RegTech** | Compliance automation | 2-5 years | B2B solutions |
| **Islamic Fintech** | Sharia-compliant innovation | Ongoing | Differentiation |
| **SME Lending** | Underserved segment | Ongoing | Lending tech |
| **Instant Payments** | Real-time infrastructure | 2-4 years | New services |
| **ESG Integration** | Sustainable finance | 2-7 years | Green products |
| **Super Apps** | All-in-one platforms | 2-5 years | Platform play |

## 5.5 Major Player Landscape

### Traditional Banks by Country

| Country | Major Banks | Characteristics |
|---------|-------------|-----------------|
| **Saudi** | NCB (SNB), Al Rajhi, Riyad, SABB | Islamic dominant |
| **UAE** | FAB, Emirates NBD, ADCB, DIB | Diversified |
| **Egypt** | NBE, Banque Misr, CIB, QNB Alahli | State + private |
| **Jordan** | Arab Bank, Housing Bank, Jordan Ahli | Regional presence |
| **Morocco** | Attijariwafa, BMCE, BCP | African expansion |

### Regional/International Fintechs

| Company | Segment | Markets |
|---------|---------|---------|
| STC Pay | Payments/wallet | Saudi |
| PayTabs | Payment gateway | Pan-MENA |
| Tabby | BNPL | UAE, Saudi |
| Tamara | BNPL | Saudi |
| Fawry | Payments | Egypt |
| Paymob | Payments | Egypt, expanding |
| Lean Technologies | Open banking | Saudi, UAE |
| Wahed | Islamic robo-advisory | Global |

### International Players

| Company | Segment | MENA Presence |
|---------|---------|---------------|
| Visa/Mastercard | Cards/payments | Dominant |
| PayPal | Digital payments | Limited |
| Stripe | Payment processing | Growing |
| AXA, Allianz, Zurich | Insurance | Significant |
| HSBC, Citi, Standard Chartered | Banking | Corporate focus |

## 5.6 Market-Specific Dynamics

| Country | Market Characteristics | Key Opportunity |
|---------|----------------------|-----------------|
| **Saudi Arabia** | Highest growth, Vision 2030 | All fintech segments |
| **UAE** | Most developed, hub status | B2B, Islamic, wealth |
| **Egypt** | Largest population, high unbanked | Inclusion, payments |
| **Jordan** | Stable, tech-savvy | Payments, remittances |
| **Morocco** | Gateway to Africa | Microfinance, expansion |

---

# Dimension 6: Digital Maturity

## 6.1 Technology Adoption Benchmarks

| Subsector | Current Adoption | Digital Leaders | Digital Laggards | Key Gap |
|-----------|------------------|-----------------|------------------|---------|
| Traditional Banks | Medium-High | 50% | 20% | Customer experience |
| Digital Banks | Very High | 90% | - | By definition |
| Payments | High | 70% | 10% | Scale, integration |
| Insurance | Medium | 35% | 40% | Digital distribution |
| Wealth Management | Medium | 40% | 35% | Client portal |
| Microfinance | Low-Medium | 25% | 50% | Mobile, scoring |

## 6.2 Digital Maturity Levels

```
┌─────────────────────────────────────────────────────────────────────────────┐
│              FINANCIAL SERVICES DIGITAL MATURITY                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  LEVEL 1: LEGACY (Score 0-20)                                               │
│  • Branch-dependent, paper-based, basic systems                             │
│  • Typical: Traditional brokers, small insurers                             │
│                                                                              │
│  LEVEL 2: BASIC DIGITAL (Score 21-40)                                       │
│  • Online access, basic mobile, digital marketing                           │
│  • Typical: Traditional banks, established insurers                         │
│                                                                              │
│  LEVEL 3: DIGITAL-ENABLED (Score 41-60)                                     │
│  • Good mobile app, online onboarding, API integration                      │
│  • Typical: Progressive traditional players                                  │
│                                                                              │
│  LEVEL 4: DIGITAL-FIRST (Score 61-80)                                       │
│  • Fully digital journeys, data-driven, cloud-native                        │
│  • Typical: Challenger banks, leading fintechs                              │
│                                                                              │
│  LEVEL 5: DIGITAL-NATIVE (Score 81-100)                                     │
│  • AI-powered, real-time, predictive, embedded everywhere                   │
│  • Typical: Best-in-class fintechs                                          │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 6.3 Core Technology Systems

### Banking Technology Stack

| System | Priority | Investment Range | Adoption |
|--------|----------|------------------|----------|
| Core Banking | Critical | $500K-50M | 95% |
| Mobile Banking | Critical | $200K-5M | 85% |
| Internet Banking | Critical | $100K-2M | 90% |
| CRM | High | $100K-2M | 70% |
| AML/KYC | Critical | $200K-5M | 95% |
| API Gateway | High | $100K-1M | 50% |
| Data Analytics | High | $200K-3M | 55% |
| AI/ML Platform | Medium-High | $300K-5M | 30% |

### Insurance Technology

| System | Priority | Investment Range | Adoption |
|--------|----------|------------------|----------|
| Policy Admin | Critical | $200K-10M | 85% |
| Claims Management | Critical | $150K-5M | 80% |
| Underwriting Engine | High | $100K-3M | 60% |
| Agent Portal | High | $50K-500K | 70% |
| Customer Portal | High | $100K-1M | 45% |
| Analytics/BI | High | $100K-1M | 50% |

### Fintech Stack

| Component | Purpose | Examples |
|-----------|---------|----------|
| Cloud Infrastructure | Scalability | AWS, GCP, Azure |
| Core Banking SaaS | Banking engine | Mambu, Thought Machine |
| Payment Gateway | Transaction processing | Stripe, Checkout |
| KYC/Identity | Onboarding | Onfido, Jumio |
| Credit Scoring | Risk assessment | Various AI/ML |
| Communication | Customer engagement | Twilio, WhatsApp |

## 6.4 High-Impact Digital Interventions

| Subsector | Priority 1 | Priority 2 | Priority 3 | Impact |
|-----------|------------|------------|------------|--------|
| Banking | Mobile app excellence | Digital onboarding | Open banking | 30-50% cost reduction |
| Payments | API-first platform | Real-time processing | Data monetization | Scale enablement |
| Insurance | Digital distribution | Claims automation | Underwriting AI | 20-40% efficiency |
| Lending | Digital origination | Credit scoring AI | Collection automation | 40-60% efficiency |
| Wealth | Client portal | Robo-advisory | Portfolio analytics | 25-40% efficiency |

## 6.5 Emerging Technologies

### AI/ML Applications

| Application | Use Case | Adoption | Impact |
|-------------|----------|----------|--------|
| Credit Scoring | Alternative data | Growing | Better decisions |
| Fraud Detection | Real-time monitoring | Established | Loss reduction |
| Chatbots | Customer service | Growing | Cost reduction |
| Document Processing | KYC, claims | Growing | Efficiency |
| Personalization | Product recommendations | Emerging | Revenue |
| Underwriting | Risk assessment | Emerging | Speed, accuracy |

### Blockchain/DLT Applications

| Application | Status | Opportunity |
|-------------|--------|-------------|
| Trade Finance | Pilots/early adoption | Efficiency |
| Payments | Developing | Speed, cost |
| KYC Sharing | Pilots | Compliance |
| Sukuk Issuance | Pilots (Saudi) | Islamic finance |
| Insurance Claims | Emerging | Transparency |

---

# Dimension 7: Workforce Norms

## 7.1 Organizational Structures

### Fintech / Digital Bank (30-80 employees)
```
              CEO/Founder
                    │
       ┌────────────┼────────────┬────────────┐
       │            │            │            │
   Product/      Technology    Growth       Finance/
   Business        CTO        (Marketing)   Compliance
       │            │            │            │
   Product Mgrs   Engineers    Marketing   Finance
   Operations     Data/ML     Sales       Risk
   Customer Svc   Security    BD          Compliance
```

### Insurance Broker (20-60 employees)
```
              Managing Director
                    │
       ┌────────────┼────────────┬────────────┐
       │            │            │            │
   Corporate     Retail       Claims/      Finance/
   Sales         Sales        Service       Admin
       │            │            │            │
   Account       Agents       Claims       Accounts
   Executives    Renewals     Support      HR
   Underwriting              Processing    IT
```

### Asset Manager (15-40 employees)
```
              CEO/CIO
                    │
       ┌────────────┼────────────┬────────────┐
       │            │            │            │
  Investments    Sales/        Operations   Compliance
  (Portfolio)    Distribution               /Legal
       │            │            │            │
  Portfolio     Sales Team   Fund Admin   Compliance
  Managers      Client Svc   Operations    Legal
  Analysts      Marketing    Technology    Risk
```

## 7.2 Key Roles

### Banking/Fintech Roles

| Role | Responsibilities | Experience | Qualifications |
|------|------------------|------------|----------------|
| CEO/GM | Business leadership | 15+ years | MBA, banking exp |
| CFO | Financial management | 12+ years | CPA/CFA |
| CTO | Technology strategy | 10+ years | Tech background |
| Chief Risk Officer | Risk management | 12+ years | FRM/risk exp |
| Head of Compliance | Regulatory | 10+ years | Compliance cert |
| Product Manager | Product development | 5-8 years | Fintech exp |
| Software Engineer | Technology build | 3-8 years | CS degree |
| Data Scientist | Analytics/ML | 3-6 years | Quantitative |
| Relationship Manager | Client management | 3-8 years | Banking exp |

### Insurance Roles

| Role | Responsibilities | Experience | Qualifications |
|------|------------------|------------|----------------|
| CEO/Country Manager | Overall leadership | 15+ years | Insurance exp |
| Chief Underwriter | Underwriting policy | 12+ years | ACII/CPCU |
| Claims Director | Claims management | 10+ years | Claims exp |
| Actuary | Pricing, reserving | 5-15 years | FSA/FIA |
| Underwriter | Risk assessment | 3-8 years | ACII progress |
| Claims Handler | Claims processing | 2-5 years | Claims training |
| Broker Executive | Sales, placement | 3-8 years | Broker license |

### Wealth/Asset Management Roles

| Role | Responsibilities | Experience | Qualifications |
|------|------------------|------------|----------------|
| CIO | Investment strategy | 15+ years | CFA |
| Portfolio Manager | Fund management | 8-15 years | CFA |
| Research Analyst | Investment research | 3-8 years | CFA progress |
| Relationship Manager | Client management | 5-10 years | CFP/CFA |
| Wealth Advisor | Financial planning | 5-10 years | CFP |
| Sales/Distribution | Product sales | 3-8 years | Sales exp |

## 7.3 Compensation Benchmarks (USD/month)

### Egypt

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Bank Branch Manager | $800-1,500 | $1,500-2,500 | $2,500-5,000 |
| Fintech Product Manager | $800-1,500 | $1,500-3,000 | $3,000-6,000 |
| Software Engineer | $600-1,200 | $1,200-2,500 | $2,500-5,000 |
| Insurance Underwriter | $500-900 | $900-1,800 | $1,800-3,500 |
| Investment Analyst | $600-1,000 | $1,000-2,000 | $2,000-4,500 |
| Compliance Officer | $500-900 | $900-1,800 | $1,800-4,000 |

### Saudi Arabia

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Bank Branch Manager | $4,000-7,000 | $7,000-12,000 | $12,000-20,000 |
| Fintech Product Manager | $5,000-8,000 | $8,000-15,000 | $15,000-25,000 |
| Software Engineer | $4,000-7,000 | $7,000-13,000 | $13,000-22,000 |
| Insurance Underwriter | $3,000-5,500 | $5,500-10,000 | $10,000-18,000 |
| Investment Analyst | $4,000-7,000 | $7,000-13,000 | $13,000-25,000 |
| Compliance Officer | $3,500-6,000 | $6,000-11,000 | $11,000-20,000 |

### UAE

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Bank Branch Manager | $5,000-9,000 | $9,000-15,000 | $15,000-28,000 |
| Fintech Product Manager | $6,000-10,000 | $10,000-18,000 | $18,000-35,000 |
| Software Engineer | $5,000-9,000 | $9,000-16,000 | $16,000-30,000 |
| Insurance Underwriter | $4,000-7,000 | $7,000-13,000 | $13,000-25,000 |
| Investment Analyst | $5,000-9,000 | $9,000-16,000 | $16,000-35,000 |
| Compliance Officer | $4,500-8,000 | $8,000-14,000 | $14,000-28,000 |

### Jordan

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Bank Branch Manager | $1,200-2,200 | $2,200-4,000 | $4,000-7,500 |
| Fintech Product Manager | $1,200-2,000 | $2,000-4,000 | $4,000-8,000 |
| Software Engineer | $1,000-1,800 | $1,800-3,500 | $3,500-7,000 |
| Insurance Underwriter | $800-1,500 | $1,500-2,800 | $2,800-5,500 |
| Investment Analyst | $1,000-1,800 | $1,800-3,500 | $3,500-7,500 |
| Compliance Officer | $900-1,600 | $1,600-3,000 | $3,000-6,000 |

## 7.4 Skills Gap Analysis

| Skill Area | Availability | Demand | Gap Severity |
|------------|--------------|--------|--------------|
| Fintech/Digital | Low | Very High | **Critical** |
| Data Science/AI | Very Low | Very High | **Critical** |
| Cybersecurity | Low | Very High | **Critical** |
| Compliance/AML | Medium | Very High | **High** |
| Risk Management | Medium | High | **High** |
| Product Management | Low | High | **High** |
| Actuarial | Low | Medium | **High** |
| Sales/Relationship | Medium | High | **Medium** |
| Islamic Finance | Medium | High | **Medium** |

## 7.5 Labor Market Characteristics

| Characteristic | Egypt | Saudi Arabia | UAE | Jordan |
|---------------|-------|--------------|-----|--------|
| Local vs Expat | 95%+ local | 45/55 | 15/85 | 85/15 |
| Industry Turnover | 15-25% | 18-28% | 22-35% | 15-25% |
| Female Participation | 30-40% | 25-40% (growing) | 35-45% | 35-45% |
| Tech Talent | Growing | Scarce | Competitive | Good pool |
| Saudization | N/A | High priority | Moderate | N/A |

## 7.6 HR KPIs

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| Staff Turnover | >28% | 20-28% | 12-20% | <12% |
| Revenue/Employee | <$50K | $50-100K | $100-180K | >$180K |
| Training Hours/Year | <30 | 30-50 | 50-80 | >80 |
| Employee Satisfaction | <60% | 60-72% | 72-85% | >85% |
| Time to Fill (Tech) | >90 days | 60-90 | 40-60 | <40 |
| Regrettable Attrition | >15% | 10-15% | 5-10% | <5% |

---

*End of Part 2 - Continue to Part 3 for Dimensions 8-11*
# Dimension 8: Supply Chain

## 8.1 Input Categories

### Financial Services Inputs

| Category | % of Costs | Key Suppliers |
|----------|-----------|---------------|
| Personnel | 40-60% | Labor market |
| Technology | 15-30% | Software vendors |
| Compliance/Regulatory | 5-15% | Regtech, consultants |
| Marketing | 5-15% | Agencies, digital |
| Facilities | 3-8% | Real estate |
| Data/Information | 2-8% | Data providers |
| Professional Services | 3-8% | Legal, audit, consulting |

### Technology Suppliers

| Category | Key Vendors | Cost Model |
|----------|-------------|------------|
| Core Banking | Temenos, Infosys, Mambu | License + maintenance |
| Payment Processing | Visa/MC, network fees | Per transaction |
| Cloud Infrastructure | AWS, Azure, GCP | Usage-based |
| KYC/AML | Refinitiv, LexisNexis | Subscription |
| CRM | Salesforce, MS Dynamics | Per user |
| Analytics | SAS, Tableau, Python | License/open source |
| Communication | Twilio, WhatsApp | Usage-based |

### Data Providers

| Type | Examples | Use Case |
|------|----------|----------|
| Credit Bureau | Simah (SA), I-Score (EG) | Credit decisioning |
| Market Data | Bloomberg, Reuters | Trading, research |
| Alternative Data | Social, transactional | Credit scoring |
| KYC Data | World-Check, Dow Jones | Compliance |
| Insurance Data | Claims databases | Underwriting |

## 8.2 Vendor Management

### Key Relationships

| Vendor Type | Relationship | Contract Type |
|-------------|--------------|---------------|
| Core Systems | Strategic partnership | Multi-year license |
| Payment Networks | Membership | Membership + fees |
| Cloud Providers | Service | Pay-as-you-go |
| Compliance Vendors | Critical | Annual subscription |
| Data Providers | Essential | Annual subscription |
| Consulting | Project-based | Per engagement |

### Outsourcing Options

| Function | Outsource To | Common For |
|----------|--------------|------------|
| IT Infrastructure | Cloud providers | All |
| Call Center | BPO providers | Large institutions |
| Back Office | Processing centers | Banks, insurers |
| KYC Operations | Specialized providers | Growing |
| Collection | Collection agencies | Lenders |
| Software Development | Tech firms | Growing |

## 8.3 Distribution Channels

### Banking Distribution

| Channel | Cost/Acquisition | Trend |
|---------|------------------|-------|
| Branch | $200-500 | Declining |
| ATM | $50-150 | Stable |
| Mobile App | $5-30 | Growing rapidly |
| Web | $10-50 | Stable |
| Agent Network | $20-80 | Growing (inclusion) |
| Partnerships | Variable | Growing (embedded) |

### Insurance Distribution

| Channel | Commission | Trend |
|---------|------------|-------|
| Direct Sales Force | 15-30% | Stable |
| Independent Agents | 15-25% | Stable |
| Brokers | 10-20% | Stable (corporate) |
| Bancassurance | 20-40% | Growing |
| Digital/Direct | 5-15% | Growing rapidly |
| Aggregators | 10-20% | Growing |

### Investment Distribution

| Channel | Fee Split | Trend |
|---------|-----------|-------|
| Direct | Full retention | Growing |
| Bank Distribution | 30-50% rebate | Dominant |
| IFAs | 25-40% trail | Stable |
| Digital Platforms | 10-25% | Growing |

## 8.4 Partnership Models

### Fintech-Bank Partnerships

| Model | Description | Examples |
|-------|-------------|----------|
| White-Label | Fintech provides tech | Banking-as-a-Service |
| Referral | Lead generation | Lending, insurance |
| Integration | Embedded services | Payments in apps |
| Joint Venture | Shared ownership | Digital subsidiaries |
| Investment | Bank invests in fintech | Strategic stakes |

### Distribution Partnerships

| Partner Type | Products | Value |
|--------------|----------|-------|
| Telecos | Payments, wallets | Customer base |
| Retailers | BNPL, payments | Point of sale |
| E-commerce | Payments, credit | Transaction flow |
| Employers | Payroll, benefits | Captive audience |
| Real Estate | Mortgages, insurance | Transaction point |

---

# Dimension 9: Export Requirements

## 9.1 Cross-Border Financial Services

### Service Export Opportunities

| Service | Export Method | Key Markets |
|---------|---------------|-------------|
| Fintech B2B | SaaS licensing | Regional |
| Payment Processing | Cross-border | MENA, Africa |
| Insurance Broking | Network/partnership | Regional |
| Asset Management | Cross-border funds | GCC, international |
| Remittances | Corridor services | Labor corridors |

### Regional Hub Strategy

| Hub | Advantages | Target Markets |
|-----|-----------|----------------|
| UAE (DIFC/ADGM) | Regulation, infrastructure | Global |
| Saudi Arabia | Largest market | GCC |
| Bahrain | Fintech-friendly | GCC |
| Morocco | Francophone | Africa |
| Egypt | Population, Arabic | Arab world |

## 9.2 Cross-Border Regulations

### Passporting / Market Access

| Aspect | GCC | EU (for comparison) |
|--------|-----|---------------------|
| Banking License | No passport | Single passport |
| Insurance License | No passport | Limited passport |
| Investment Funds | Limited | UCITS passport |
| Payment Services | No passport | PSD2 passport |

### Key Considerations

| Factor | Requirement |
|--------|-------------|
| Local License | Usually required per country |
| Local Partner | Sometimes required |
| Capital Requirements | Per jurisdiction |
| Data Localization | Increasing requirements |
| Compliance | Multiple regimes |

## 9.3 International Standards

| Standard | Application | Recognition |
|----------|-------------|-------------|
| Basel III | Banking capital | Global |
| Solvency II | Insurance capital | International |
| IFRS 9/17 | Financial reporting | Global |
| FATF | AML/CFT | Global |
| PCI-DSS | Card security | Global |
| ISO 27001 | Information security | Global |

## 9.4 Remittance Corridors

### Key MENA Corridors

| Corridor | Direction | Volume |
|----------|-----------|--------|
| GCC to South Asia | Outbound | Very High |
| GCC to Egypt | Outbound | High |
| GCC to Philippines | Outbound | High |
| Europe to Morocco | Inbound | High |
| US to Egypt/Jordan | Inbound | Medium |

### Remittance Business Model

| Model | Take Rate | Competitive Factor |
|-------|-----------|-------------------|
| Traditional (Banks) | 5-10% | Trust, compliance |
| MTOs | 3-7% | Network, speed |
| Digital Remittance | 1-4% | Cost, convenience |
| Mobile Money | 2-5% | Accessibility |

---

# Dimension 10: Packaging & Labeling

## 10.1 Product Packaging

### Banking Products

| Product | Target Segment | Key Features |
|---------|---------------|--------------|
| Basic Account | Mass market | Low/no fees, basic |
| Premium Account | Affluent | Benefits, rewards |
| Youth Account | Young adults | Digital-first |
| SME Account | Businesses | Trade, lending |
| Islamic Account | Religious | Sharia-compliant |

### Insurance Products

| Product | Packaging | Distribution |
|---------|-----------|--------------|
| Motor Comprehensive | Bundled coverage | Direct, agents |
| Health Individual | Tiered plans | Direct, brokers |
| Corporate Health | Group schemes | Brokers |
| Home Insurance | Package policies | Bank, direct |
| Travel Insurance | Event-based | Travel agents, digital |

### Investment Products

| Product | Structure | Fee Model |
|---------|-----------|-----------|
| Mutual Funds | Pooled | Management fee |
| ETFs | Listed | Low fee |
| Private Equity | Closed-end | 2 and 20 |
| REITs | Listed/unlisted | Management + performance |
| Structured Products | Custom | Embedded |

## 10.2 Digital Product Packaging

### Mobile App Features

| Feature | Basic | Premium | Business |
|---------|-------|---------|----------|
| Account Management | ✓ | ✓ | ✓ |
| Payments | ✓ | ✓ | ✓ |
| Cards | Basic | Premium | Corporate |
| Lending | Limited | Full | Business loans |
| Investments | - | ✓ | ✓ |
| Analytics | Basic | Advanced | Business |
| Support | Self-serve | Priority | Dedicated |

### Subscription/Tiered Models

| Tier | Monthly Fee | Benefits |
|------|-------------|----------|
| Free | $0 | Basic features |
| Plus | $5-15 | Premium features |
| Premium | $15-50 | Full access, perks |
| Business | Custom | Enterprise features |

## 10.3 Marketing & Communications

### Regulatory Requirements

| Requirement | Description |
|-------------|-------------|
| Risk Warnings | Investment risk disclosure |
| Fee Disclosure | All fees clearly stated |
| APR Disclosure | Annual percentage rate |
| Terms & Conditions | Clear, accessible |
| Cooling-Off | Right to cancel period |
| Sharia Certification | For Islamic products |

### Marketing Channels

| Channel | Best For | Regulatory Sensitivity |
|---------|----------|------------------------|
| Digital/Social | Awareness, acquisition | Medium |
| TV/Radio | Brand building | Medium |
| Branch | Complex products | Lower |
| Direct Mail | Existing customers | Medium |
| Partnerships | Embedded distribution | Lower |
| Content Marketing | Education | Lower |

## 10.4 Customer Communications

### Statement Standards

| Element | Requirement |
|---------|-------------|
| Account Summary | Clear balance, transactions |
| Fee Breakdown | Itemized charges |
| Interest Rates | Current rates shown |
| Contact Information | Support channels |
| Dispute Process | Clear instructions |
| Language | Local + English |

### Digital Communications

| Channel | Use Case | Response Time |
|---------|----------|---------------|
| In-App Notifications | Transactions, alerts | Real-time |
| SMS | OTP, critical alerts | Immediate |
| Email | Statements, marketing | 24-48 hours |
| WhatsApp | Support, service | Growing |
| Chatbot | First-line support | Instant |

---

# Dimension 11: MENA Regional Context

## 11.1 Country Profiles

### Saudi Arabia

| Attribute | Details |
|-----------|---------|
| **Market Size** | $80-120 billion (financial sector) |
| **Key Segments** | Banking, insurance, fintech |
| **Islamic Finance** | 70-80% of banking |
| **Characteristics** | Largest market, Vision 2030 transformation |
| **Fintech Environment** | Very supportive (SAMA sandbox, Fintech Saudi) |
| **Opportunities** | Digital banking, payments, open banking, SME lending |
| **Regulatory** | SAMA (progressive), CMA |

### UAE

| Attribute | Details |
|-----------|---------|
| **Market Size** | $100-150 billion |
| **Key Segments** | Banking, wealth, fintech hub |
| **Islamic Finance** | 25-30% of banking |
| **Characteristics** | Most developed, regional/global hub |
| **Fintech Environment** | Multiple sandboxes, DIFC/ADGM |
| **Opportunities** | B2B fintech, wealth tech, crypto |
| **Regulatory** | CBUAE, DFSA, ADGM (sophisticated) |

### Egypt

| Attribute | Details |
|-----------|---------|
| **Market Size** | $15-25 billion |
| **Key Segments** | Banking, payments, microfinance |
| **Islamic Finance** | 5-8% of banking |
| **Characteristics** | Large population, high unbanked |
| **Fintech Environment** | Growing (CBE supportive) |
| **Opportunities** | Financial inclusion, payments, digital banking |
| **Regulatory** | CBE, FRA (modernizing) |

### Jordan

| Attribute | Details |
|-----------|---------|
| **Market Size** | $5-8 billion |
| **Key Segments** | Banking, payments, remittances |
| **Islamic Finance** | 15-20% of banking |
| **Characteristics** | Stable, tech-savvy population |
| **Fintech Environment** | Supportive (CBJ sandbox) |
| **Opportunities** | Payments, SME lending, remittances |
| **Regulatory** | CBJ, JSC (progressive) |

### Morocco

| Attribute | Details |
|-----------|---------|
| **Market Size** | $20-30 billion |
| **Key Segments** | Banking, microfinance, insurance |
| **Islamic Finance** | 3-5% (new, growing) |
| **Characteristics** | Gateway to Africa, developed microfinance |
| **Fintech Environment** | Developing |
| **Opportunities** | Africa expansion, microfinance, payments |
| **Regulatory** | BAM, ACAPS (traditional) |

## 11.2 Vision 2030 Financial Sector Impact

### Saudi Financial Sector Development Program

| Initiative | Target | Impact |
|------------|--------|--------|
| Increase assets under management | 80% growth | Asset management opportunity |
| Raise SME financing | 20% of bank lending | SME lending opportunity |
| Increase insurance penetration | 2.4% to 4%+ | Insurance growth |
| Develop capital markets | Increase depth | Capital markets activity |
| Promote fintech | 230+ fintechs | Ecosystem growth |
| Cashless payments | 70% of transactions | Payments opportunity |

### Key Enablers

| Enabler | Description |
|---------|-------------|
| Open Banking | Mandated by SAMA |
| Instant Payments | SARIE system |
| Digital Identity | National digital ID |
| Regulatory Sandbox | SAMA Fintech Permit |
| Fintech Saudi | Ecosystem development |

## 11.3 Islamic Finance Opportunity

### Market Size by Country

| Country | Islamic Banking Assets | Takaful Premium | Growth |
|---------|----------------------|-----------------|--------|
| Saudi Arabia | $300B+ | $10B+ | Dominant |
| UAE | $150B+ | $3B+ | Strong |
| Malaysia (comparison) | $250B+ | $5B+ | Mature |
| Egypt | $15B+ | $500M+ | Emerging |
| Morocco | $2B+ | <$100M | New |

### Islamic Fintech Opportunity

| Segment | Opportunity | Examples |
|---------|-------------|----------|
| Islamic Digital Banking | Sharia-compliant neobank | Several launching |
| Halal Investment | Robo-advisory, funds | Wahed, others |
| Islamic Crowdfunding | Sharia-compliant P2P | Emerging |
| Takaful Tech | Digital takaful | Growing |
| Islamic Payments | Compliant wallets | Integrated |

## 11.4 Financial Inclusion

### Unbanked Population

| Country | Unbanked % | Opportunity |
|---------|-----------|-------------|
| Egypt | 65-70% | Very High |
| Morocco | 55-60% | High |
| Jordan | 50-55% | High |
| Saudi Arabia | 25-30% | Medium |
| UAE | 15-20% | Low |

### Inclusion Drivers

| Driver | Impact |
|--------|--------|
| Mobile Penetration | Enables digital services |
| Government Programs | Direct benefit transfers |
| Agent Banking | Physical access point |
| Simplified KYC | Lower barriers |
| Microfinance | Small-ticket access |

## 11.5 Business Culture Considerations

| Aspect | Consideration |
|--------|---------------|
| Relationship Banking | Personal relationships matter |
| Cash Culture | Still significant (declining) |
| Islamic Preference | Strong in Gulf, growing elsewhere |
| Family Business | Large segment of wealth |
| Trust | Critical for financial services |
| Regulatory Respect | Compliance non-negotiable |
| Local Partners | Often valuable/required |

## 11.6 Strategic Opportunities

| Opportunity | Markets | Potential | Requirements |
|-------------|---------|-----------|--------------|
| Digital Banking | Saudi, Egypt | **Very High** | License, capital |
| Payments/Wallets | Egypt, Saudi | **Very High** | License, distribution |
| SME Lending | All | **Very High** | Credit scoring, capital |
| Open Banking/APIs | Saudi, UAE | **High** | Technical, partnerships |
| Islamic Fintech | Saudi, UAE | **High** | Sharia compliance |
| Insurtech | All | **High** | Distribution, data |
| Wealth Tech | UAE, Saudi | **High** | License, AUM |
| B2B Fintech | All | **High** | Enterprise sales |
| Regtech | All | **Medium-High** | Compliance expertise |
| Cross-Border Payments | All | **High** | Licenses, corridors |

---

# Document Summary

## Sector Overview

**Financial Services** in MENA represents:

**Market Size & Growth:**
- ~$250-400 billion total market
- Fintech fastest growing segment (20-50% annually)
- Vision 2030 driving transformation in Saudi
- High unbanked population = inclusion opportunity

**Key Characteristics:**
- Heavily regulated, requires licenses
- Islamic finance significant (20-80% by market)
- Digital disruption accelerating
- Cash-to-digital transition underway
- B2B fintech opportunity growing
- Regional hub dynamics (UAE, Saudi competing)

**SME Landscape:**
- Licenses create barriers but protect position
- Fintech enables SME entry in specific niches
- B2B infrastructure plays more accessible
- Distribution partnerships key for scale
- Capital requirements vary significantly

**Priority Subsectors:**
1. **Payment Services** - High growth, infrastructure play
2. **Alternative Lending** - SME gap, BNPL boom
3. **Insurance Distribution** - Digital disruption
4. **Fintech B2B** - Open banking, infrastructure
5. **Digital Banking** - Neobank opportunity

## Critical Insights for SME Diagnostics

### Key Success Factors

1. **Regulatory License** - Fundamental requirement
2. **Capital Adequacy** - Prudential compliance
3. **Technology Platform** - Digital capability
4. **Customer Acquisition** - CAC efficiency
5. **Risk Management** - NPL, fraud control
6. **Compliance Excellence** - AML/KYC

### Red Flags to Assess

- Regulatory breaches or warnings
- NPL ratio >10%
- Customer acquisition unsustainable (LTV:CAC <2)
- Technology debt / legacy systems
- Single revenue stream dependency
- Key person risk (compliance, tech)

### Upside Indicators

- Strong digital engagement (MAU >50%)
- Healthy unit economics (LTV:CAC >4)
- Low NPL (<3%)
- Regulatory sandbox or full license
- Strategic partnerships
- Islamic finance capability

## Agent Usage Guide

| Agent | Primary Dimensions | Key Data Points |
|-------|-------------------|-----------------|
| **The Drucker** | 1, 11 | Subsector classification, regional context |
| **The Marvin** | 3, 4 | Financial KPIs, regulatory compliance |
| **The Graham** | 2 | NIM, combined ratio, unit economics |
| **The Ricardo** | 9, 10 | Cross-border, product packaging |
| **The Lovelace** | 6 | Digital maturity, fintech stack |
| **The Mayo** | 7 | Fintech talent, compensation |
| **The Ohno** | 8 | Technology vendors, partnerships |
| **The Porter** | 5 | Competitive dynamics, fintech disruption |
| **The Landor** | 10 | Digital products, marketing |

## Cross-Sector Integration

Financial Services ENABLES ALL other sectors:

| Connected Sector | Financial Services Integration |
|------------------|-------------------------------|
| **ALL Sectors** | Banking, payments, insurance |
| Real Estate | Mortgages, REITs |
| Retail | Payments, BNPL |
| Manufacturing | Trade finance, working capital |
| Agriculture | Crop insurance, microfinance |
| Healthcare | Health insurance |
| Construction | Project finance, bonds |
| Logistics | Trade finance, cargo insurance |
| Hospitality | Payment processing |

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | December 2025 | RootRise Product Team | Initial release |

---

*This document is part of the RootRise Sector Knowledge Pack series, providing comprehensive sector intelligence for The Pantheon multi-agent diagnostic system.*
