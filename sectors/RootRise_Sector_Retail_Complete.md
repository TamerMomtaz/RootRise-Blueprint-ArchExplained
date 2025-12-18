# RootRise Sector Knowledge Pack
# Retail & Distribution
## Version 1.0 | December 2025

---

# Document Information

| Attribute | Value |
|-----------|-------|
| **Sector ID** | `retail_distribution` |
| **Version** | 1.0 |
| **Last Updated** | December 2025 |
| **Status** | Active |
| **ISIC Rev.4 Divisions** | 45 (Motor Vehicle Trade), 46 (Wholesale), 47 (Retail) |
| **Primary Markets** | Egypt, Saudi Arabia, UAE, Jordan, Morocco |
| **SME Employee Range** | 5-250 |
| **SME Revenue Range** | $100K - $50M |

## Sector Overview

Retail & Distribution in MENA is undergoing **massive transformation** driven by e-commerce adoption, digital payment growth, and evolving consumer expectations. The sector connects manufacturers to consumers and serves as the critical final mile of the supply chain.

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                    RETAIL & DISTRIBUTION VALUE CHAIN                             │
├─────────────────────────────────────────────────────────────────────────────────┤
│                                                                                  │
│   UPSTREAM                    CORE OPERATIONS                   DOWNSTREAM      │
│   ─────────                   ───────────────                   ──────────      │
│                                                                                  │
│   ┌──────────────┐           ┌──────────────────────┐         ┌─────────────┐  │
│   │ SUPPLIERS    │           │  WHOLESALE/           │         │ CUSTOMERS   │  │
│   │ • Manufactur-│──────────►│  DISTRIBUTION         │         │ • B2C       │  │
│   │   ers        │           │  • Import/Export      │────────►│ • B2B       │  │
│   │ • Importers  │           │  • Bulk Breaking      │         │ • Online    │  │
│   │ • Brands     │           │  • Territory Mgmt     │         │ • Offline   │  │
│   └──────────────┘           └──────────┬───────────┘         └─────────────┘  │
│                                         │                                       │
│                              ┌──────────▼───────────┐                          │
│   LOGISTICS INTEGRATION      │  RETAIL               │         CHANNELS        │
│   ─────────────────────      │  OPERATIONS           │         ─────────       │
│   • Warehousing              │  • Store Operations   │         • Physical      │
│   • Last-Mile                │  • E-commerce         │         • Online        │
│   • Cold Chain               │  • Merchandising      │         • Omnichannel   │
│   • Fulfillment              │  • Customer Service   │         • Marketplace   │
│                              └──────────────────────┘                          │
│                                                                                  │
│   KEY MENA CHARACTERISTICS:                                                     │
│   • E-commerce growth 25-40% CAGR (accelerated post-COVID)                     │
│   • Young, digital-native population driving change                            │
│   • Cash-on-delivery still dominant (declining)                                │
│   • Mall culture strong but diversifying                                       │
│   • Social commerce emerging rapidly                                           │
│   • Hyperlocal/Q-commerce growing fast                                         │
│                                                                                  │
└─────────────────────────────────────────────────────────────────────────────────┘
```

## Applicable Countries

| Country Code | Country Name | Retail Market Size | E-commerce Penetration |
|--------------|--------------|-------------------|------------------------|
| EG | Egypt | $70-90 billion | 4-6% |
| SA | Saudi Arabia | $150-180 billion | 12-18% |
| AE | UAE | $60-80 billion | 18-25% |
| JO | Jordan | $12-15 billion | 6-9% |
| MA | Morocco | $30-40 billion | 3-5% |

---

# Dimension 1: Industry Classification

## 1.1 ISIC Rev.4 Classification

### Primary ISIC Codes

| Division | Description | SME Relevance |
|----------|-------------|---------------|
| **45** | Wholesale/retail of motor vehicles | Medium |
| **46** | Wholesale trade | **Very High** |
| **47** | Retail trade | **Very High** |

### Detailed Class Breakdown

**Division 46 - Wholesale Trade:**

| Group | Description | SME Relevance |
|-------|-------------|---------------|
| 461 | Wholesale on a fee/contract basis | High |
| **462** | **Wholesale of agricultural products, food, beverages** | **Very High** |
| **463** | **Wholesale of household goods** | **Very High** |
| 464 | Wholesale of machinery, equipment | High |
| 465 | Wholesale of computers, electronics | High |
| **466** | **Other specialized wholesale** | **High** |
| **469** | **Non-specialized wholesale trade** | **Very High** |

**Division 47 - Retail Trade:**

| Group | Description | SME Relevance |
|-------|-------------|---------------|
| **471** | **Retail in non-specialized stores (supermarkets, hypermarkets)** | **Very High** |
| **472** | **Retail of food, beverages, tobacco in specialized stores** | **Very High** |
| 473 | Retail of automotive fuel | Medium |
| **474** | **Retail of electronics, computers, telecoms** | **High** |
| **475** | **Retail of other household equipment** | **Very High** |
| **476** | **Retail of cultural/recreation goods** | **High** |
| **477** | **Retail of other goods in specialized stores** | **Very High** |
| 478 | Retail via stalls and markets | Medium |
| **479** | **Retail not in stores (e-commerce)** | **Very High** |

## 1.2 Subsector Taxonomy

```json
{
  "subsectors": [
    {
      "subsector_id": "grocery_supermarket",
      "subsector_name": "Grocery & Supermarket",
      "subsector_name_ar": "البقالة والسوبر ماركت",
      "description": "Food retail from convenience to hypermarket formats",
      "isic_codes": ["4711", "4721", "4722", "4723"],
      "typical_sme_size": "5-150 employees",
      "typical_sme_revenue": "$200K-$30M",
      "mena_market_size_estimate": "$120-150 billion",
      "growth_rate_5yr": "4-7%",
      "e_commerce_penetration": "3-8%"
    },
    {
      "subsector_id": "fashion_apparel",
      "subsector_name": "Fashion & Apparel",
      "subsector_name_ar": "الأزياء والملابس",
      "description": "Clothing, footwear, accessories retail",
      "isic_codes": ["4771", "4772"],
      "typical_sme_size": "3-80 employees",
      "typical_sme_revenue": "$100K-$15M",
      "mena_market_size_estimate": "$40-55 billion",
      "growth_rate_5yr": "5-9%",
      "e_commerce_penetration": "15-25%"
    },
    {
      "subsector_id": "electronics_appliances",
      "subsector_name": "Electronics & Appliances",
      "subsector_name_ar": "الإلكترونيات والأجهزة",
      "description": "Consumer electronics, computers, home appliances",
      "isic_codes": ["4741", "4742", "4743", "4752", "4753"],
      "typical_sme_size": "5-60 employees",
      "typical_sme_revenue": "$300K-$25M",
      "mena_market_size_estimate": "$25-35 billion",
      "growth_rate_5yr": "6-10%",
      "e_commerce_penetration": "20-35%"
    },
    {
      "subsector_id": "health_beauty",
      "subsector_name": "Health & Beauty",
      "subsector_name_ar": "الصحة والجمال",
      "description": "Cosmetics, personal care, pharmacy retail",
      "isic_codes": ["4773", "4774"],
      "typical_sme_size": "3-50 employees",
      "typical_sme_revenue": "$100K-$10M",
      "mena_market_size_estimate": "$15-22 billion",
      "growth_rate_5yr": "8-14%",
      "e_commerce_penetration": "12-22%"
    },
    {
      "subsector_id": "home_furniture",
      "subsector_name": "Home & Furniture",
      "subsector_name_ar": "المنزل والأثاث",
      "description": "Furniture, home décor, homewares",
      "isic_codes": ["4751", "4752", "4759"],
      "typical_sme_size": "5-80 employees",
      "typical_sme_revenue": "$200K-$20M",
      "mena_market_size_estimate": "$18-25 billion",
      "growth_rate_5yr": "5-8%",
      "e_commerce_penetration": "8-15%"
    },
    {
      "subsector_id": "fmcg_distribution",
      "subsector_name": "FMCG Distribution",
      "subsector_name_ar": "توزيع السلع الاستهلاكية",
      "description": "Wholesale distribution of fast-moving consumer goods",
      "isic_codes": ["4621", "4622", "4631", "4632", "4633"],
      "typical_sme_size": "10-200 employees",
      "typical_sme_revenue": "$500K-$50M",
      "mena_market_size_estimate": "$80-100 billion",
      "growth_rate_5yr": "5-8%",
      "e_commerce_penetration": "2-5%"
    },
    {
      "subsector_id": "specialty_retail",
      "subsector_name": "Specialty Retail",
      "subsector_name_ar": "التجزئة المتخصصة",
      "description": "Specialized stores: sports, toys, jewelry, books, etc.",
      "isic_codes": ["4761", "4762", "4763", "4764", "4773", "4774", "4775"],
      "typical_sme_size": "3-40 employees",
      "typical_sme_revenue": "$100K-$8M",
      "mena_market_size_estimate": "$20-30 billion",
      "growth_rate_5yr": "4-8%",
      "e_commerce_penetration": "10-20%"
    },
    {
      "subsector_id": "ecommerce_pure_play",
      "subsector_name": "E-commerce Pure Play",
      "subsector_name_ar": "التجارة الإلكترونية",
      "description": "Online-only retailers and marketplaces",
      "isic_codes": ["4791"],
      "typical_sme_size": "5-100 employees",
      "typical_sme_revenue": "$100K-$30M",
      "mena_market_size_estimate": "$25-40 billion",
      "growth_rate_5yr": "25-40%",
      "e_commerce_penetration": "100%"
    },
    {
      "subsector_id": "convenience_proximity",
      "subsector_name": "Convenience & Proximity",
      "subsector_name_ar": "المتاجر الصغيرة",
      "description": "Convenience stores, neighborhood shops, kiosks",
      "isic_codes": ["4711", "4719"],
      "typical_sme_size": "2-15 employees",
      "typical_sme_revenue": "$50K-$2M",
      "mena_market_size_estimate": "$30-45 billion",
      "growth_rate_5yr": "3-5%",
      "e_commerce_penetration": "1-3%"
    },
    {
      "subsector_id": "b2b_wholesale",
      "subsector_name": "B2B Wholesale & Trade",
      "subsector_name_ar": "الجملة والتجارة",
      "description": "Business-to-business wholesale, trading companies",
      "isic_codes": ["461", "469"],
      "typical_sme_size": "5-100 employees",
      "typical_sme_revenue": "$300K-$40M",
      "mena_market_size_estimate": "$60-80 billion",
      "growth_rate_5yr": "4-7%",
      "e_commerce_penetration": "5-12%"
    }
  ]
}
```

## 1.3 Retail Format Definitions

| Format | Size (sqm) | SKUs | Typical Revenue | Characteristics |
|--------|-----------|------|-----------------|-----------------|
| Hypermarket | 5,000-15,000+ | 40,000-100,000 | $10M-$100M | Full range, destination |
| Supermarket | 1,000-5,000 | 15,000-40,000 | $2M-$20M | Weekly shopping |
| Convenience | 100-500 | 2,000-5,000 | $200K-$2M | Top-up, impulse |
| Specialty Store | 50-500 | 500-5,000 | $100K-$5M | Category focus |
| Department Store | 3,000-20,000 | 10,000-50,000 | $5M-$50M | Multi-category |
| Discounter | 500-2,000 | 1,500-5,000 | $1M-$10M | Value focus |
| E-commerce | N/A | Unlimited | $100K-$100M+ | Digital-first |

## 1.4 Value Chain Position

| Position | Description | Typical SME Type | Margin Profile |
|----------|-------------|------------------|----------------|
| **Importer/Distributor** | Source from manufacturers, distribute to retail | Trading companies | 8-20% |
| **Wholesaler** | Bulk breaking, territory coverage | Regional distributors | 5-15% |
| **Retailer - General** | Multi-category retail | Supermarkets, variety | 15-30% |
| **Retailer - Specialty** | Category specialist | Fashion, electronics | 30-50% |
| **E-commerce Platform** | Online marketplace | Marketplaces | 10-25% commission |
| **E-commerce Brand** | D2C online | Digital-native brands | 40-70% |

## 1.5 Adjacent Sectors

| Adjacent Sector | Relationship | Integration Level |
|-----------------|--------------|-------------------|
| **Logistics & Transportation** | Fulfillment, last-mile | Very High |
| **F&B Manufacturing** | Product sourcing | Very High |
| **Textiles & Apparel** | Fashion sourcing | High |
| **Tech/Digital Services** | E-commerce platforms | High |
| **Financial Services** | Payments, financing | High |
| **Marketing/Advertising** | Customer acquisition | Medium |

---

# Dimension 2: Financial Benchmarks

## 2.1 Revenue Distribution

### Revenue per Square Meter (Retail)

| Subsector | Low | Average | Good | Excellent |
|-----------|-----|---------|------|-----------|
| Hypermarket | <$3K | $3-5K | $5-8K | >$8K |
| Supermarket | <$4K | $4-7K | $7-12K | >$12K |
| Convenience | <$5K | $5-10K | $10-18K | >$18K |
| Fashion | <$3K | $3-6K | $6-12K | >$12K |
| Electronics | <$8K | $8-15K | $15-25K | >$25K |
| Health/Beauty | <$5K | $5-10K | $10-18K | >$18K |
| Furniture | <$2K | $2-4K | $4-7K | >$7K |

### Revenue per Employee

| Subsector | Poor | Average | Good | Excellent |
|-----------|------|---------|------|-----------|
| Grocery/Supermarket | <$80K | $80-150K | $150-250K | >$250K |
| Fashion | <$50K | $50-100K | $100-180K | >$180K |
| Electronics | <$100K | $100-200K | $200-350K | >$350K |
| FMCG Distribution | <$150K | $150-300K | $300-500K | >$500K |
| E-commerce | <$100K | $100-250K | $250-500K | >$500K |
| Wholesale/B2B | <$200K | $200-400K | $400-700K | >$700K |

## 2.2 Profitability Benchmarks

### Gross Margin by Subsector

| Subsector | Low | Average | Top Performer |
|-----------|-----|---------|---------------|
| Grocery/Supermarket | 15-20% | 20-28% | 28-35% |
| Fashion/Apparel | 35-45% | 45-55% | 55-70% |
| Electronics | 12-18% | 18-28% | 28-40% |
| Health/Beauty | 30-40% | 40-50% | 50-65% |
| Home/Furniture | 35-45% | 45-55% | 55-70% |
| FMCG Distribution | 8-12% | 12-18% | 18-25% |
| E-commerce (1P) | 15-25% | 25-35% | 35-50% |
| E-commerce (Marketplace) | 60-75% | 75-85% | 85-95% |
| Convenience | 20-28% | 28-35% | 35-45% |

### EBITDA Margin

| Subsector | Low | Average | Top Performer |
|-----------|-----|---------|---------------|
| Grocery/Supermarket | 2-4% | 4-7% | 7-12% |
| Fashion/Apparel | 5-10% | 10-18% | 18-28% |
| Electronics | 2-5% | 5-10% | 10-18% |
| Health/Beauty | 8-12% | 12-20% | 20-30% |
| Home/Furniture | 5-10% | 10-18% | 18-25% |
| FMCG Distribution | 2-4% | 4-7% | 7-12% |
| E-commerce | -10-0% | 0-8% | 8-20% |
| Convenience | 3-6% | 6-12% | 12-18% |

### Net Profit Margin

| Subsector | Breakeven | Profitable | Strong | Excellent |
|-----------|-----------|------------|--------|-----------|
| Grocery | 0-1% | 1-3% | 3-5% | >5% |
| Fashion | 0-3% | 3-8% | 8-15% | >15% |
| Electronics | 0-2% | 2-5% | 5-10% | >10% |
| FMCG Distribution | 0-1% | 1-3% | 3-6% | >6% |
| E-commerce | -20-0% | 0-5% | 5-12% | >12% |

## 2.3 Cost Structure

### Retail Cost Breakdown (Physical)

| Cost Category | Grocery | Fashion | Electronics | Convenience |
|---------------|---------|---------|-------------|-------------|
| COGS | 70-80% | 40-55% | 70-85% | 65-75% |
| Rent/Occupancy | 3-8% | 10-20% | 5-12% | 5-12% |
| Labor | 8-15% | 12-22% | 8-15% | 10-18% |
| Utilities | 1-3% | 1-2% | 1-2% | 2-4% |
| Marketing | 1-3% | 3-8% | 2-5% | 0.5-2% |
| Shrinkage/Loss | 1-3% | 2-5% | 1-2% | 2-5% |
| Other OpEx | 2-5% | 3-8% | 3-6% | 3-6% |

### E-commerce Cost Breakdown

| Cost Category | 1P Model | Marketplace | D2C Brand |
|---------------|----------|-------------|-----------|
| COGS | 55-75% | N/A | 25-45% |
| Fulfillment | 8-15% | 3-8% | 10-20% |
| Customer Acquisition | 8-20% | 15-35% | 15-40% |
| Technology | 3-8% | 8-15% | 5-12% |
| Payment Processing | 2-4% | 2-4% | 2-4% |
| Returns Handling | 2-8% | 1-3% | 3-10% |
| Customer Service | 1-3% | 2-5% | 2-5% |
| G&A | 5-10% | 10-20% | 8-15% |

### FMCG Distribution Cost Breakdown

| Cost Category | % of Revenue | Variability |
|---------------|--------------|-------------|
| COGS | 80-90% | Variable |
| Logistics/Transport | 3-8% | Semi-variable |
| Warehouse | 1-3% | Fixed |
| Sales Force | 2-5% | Semi-fixed |
| Admin/Overhead | 1-3% | Fixed |
| Bad Debt | 0.5-2% | Variable |

## 2.4 Working Capital Requirements

### Inventory Days by Subsector

| Subsector | Poor | Average | Good | Excellent |
|-----------|------|---------|------|-----------|
| Grocery (Fresh) | >10 | 5-10 | 3-5 | <3 |
| Grocery (Ambient) | >45 | 30-45 | 20-30 | <20 |
| Fashion | >120 | 80-120 | 50-80 | <50 |
| Electronics | >60 | 40-60 | 25-40 | <25 |
| FMCG Distribution | >45 | 30-45 | 20-30 | <20 |
| Home/Furniture | >90 | 60-90 | 40-60 | <40 |

### Cash Conversion Cycle

| Subsector | DSO | DIO | DPO | CCC |
|-----------|-----|-----|-----|-----|
| Grocery (Cash) | 0-3 | 20-35 | 30-60 | -25 to 0 |
| Fashion | 15-45 | 60-120 | 30-60 | 30-90 |
| Electronics | 15-30 | 30-50 | 30-60 | 0-30 |
| FMCG Distribution | 30-60 | 25-40 | 20-45 | 15-50 |
| E-commerce | 0-7 | 15-40 | 20-45 | -20 to 15 |
| B2B Wholesale | 45-90 | 30-60 | 30-60 | 30-90 |

## 2.5 Capital Requirements

### Startup CapEx by Format

| Format | Fit-out/sqm | Equipment | Inventory | Total Startup |
|--------|-------------|-----------|-----------|---------------|
| Convenience (200 sqm) | $200-400/sqm | $15-30K | $20-50K | $75-150K |
| Supermarket (2,000 sqm) | $300-600/sqm | $100-250K | $150-400K | $1-2M |
| Fashion Store (300 sqm) | $400-800/sqm | $30-60K | $50-150K | $200-450K |
| E-commerce (Pure) | N/A | $20-80K tech | $50-200K | $100-350K |
| Distribution Center | $50-150/sqm | $100-500K | $500K-2M | $1-5M |

### Working Capital as % of Revenue

| Subsector | Low | Average | High |
|-----------|-----|---------|------|
| Grocery | 5% | 8-12% | 18% |
| Fashion | 15% | 25-35% | 50% |
| Electronics | 10% | 15-25% | 35% |
| FMCG Distribution | 12% | 18-28% | 40% |
| E-commerce | 8% | 12-20% | 30% |

## 2.6 Valuation Multiples

| Subsector | Revenue Multiple | EBITDA Multiple | Key Drivers |
|-----------|------------------|-----------------|-------------|
| Grocery | 0.2-0.5x | 4-8x | Location, scale |
| Fashion | 0.3-1.0x | 5-12x | Brand, margins |
| Electronics | 0.1-0.4x | 3-8x | Exclusive brands |
| FMCG Distribution | 0.2-0.5x | 5-10x | Territory, principals |
| E-commerce | 1-5x | 15-50x | Growth, tech |
| Specialty Retail | 0.3-1.0x | 5-12x | Category, loyalty |

---

# Dimension 3: Operational KPIs

## 3.1 Store Operations KPIs

### Sales Performance

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Sales/sqm/year** | Revenue productivity | <$3K | $3-6K | $6-12K | >$12K |
| **Sales/employee/year** | Labor productivity | <$80K | $80-150K | $150-250K | >$250K |
| **Basket Size (ATV)** | Average transaction | <$15 | $15-30 | $30-60 | >$60 |
| **Items per Transaction** | Basket depth | <3 | 3-6 | 6-12 | >12 |
| **Conversion Rate** | Visitors to buyers | <15% | 15-25% | 25-40% | >40% |
| **Footfall Growth** | YoY traffic change | <0% | 0-5% | 5-15% | >15% |

### Inventory Management

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Inventory Turnover** | Annual turns | <4 | 4-8 | 8-15 | >15 |
| **GMROI** | Gross margin ROI | <150% | 150-250% | 250-400% | >400% |
| **Shrinkage Rate** | Loss % of sales | >3% | 1.5-3% | 0.5-1.5% | <0.5% |
| **Stock-Out Rate** | Out of stock % | >8% | 4-8% | 2-4% | <2% |
| **Days of Cover** | Inventory days | See section | See section | See section | See section |
| **Dead Stock %** | Unsellable % | >10% | 5-10% | 2-5% | <2% |

### Customer Metrics

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **NPS** | Net Promoter Score | <20 | 20-40 | 40-60 | >60 |
| **CSAT** | Customer Satisfaction | <70% | 70-80% | 80-90% | >90% |
| **Repeat Purchase Rate** | Return customers | <20% | 20-35% | 35-50% | >50% |
| **Customer Lifetime Value** | Total customer value | <$50 | $50-150 | $150-500 | >$500 |

## 3.2 E-commerce KPIs

### Traffic & Conversion

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Conversion Rate** | Visitors to orders | <1% | 1-2.5% | 2.5-5% | >5% |
| **Cart Abandonment** | Abandoned carts | >80% | 70-80% | 60-70% | <60% |
| **Bounce Rate** | Single page exits | >60% | 45-60% | 30-45% | <30% |
| **Add to Cart Rate** | Browse to cart | <5% | 5-10% | 10-18% | >18% |
| **Session Duration** | Time on site | <1 min | 1-3 min | 3-6 min | >6 min |

### Order Economics

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Average Order Value** | Revenue per order | <$30 | $30-60 | $60-120 | >$120 |
| **Customer Acquisition Cost** | Cost per customer | >$50 | $25-50 | $10-25 | <$10 |
| **CAC Payback** | Months to recover | >18 | 12-18 | 6-12 | <6 |
| **LTV:CAC Ratio** | Value vs cost | <1 | 1-3 | 3-5 | >5 |
| **Orders per Customer/Year** | Purchase frequency | <1.5 | 1.5-3 | 3-6 | >6 |

### Fulfillment & Delivery

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **On-Time Delivery** | Within promise | <80% | 80-90% | 90-97% | >97% |
| **Order Accuracy** | Correct orders | <95% | 95-98% | 98-99.5% | >99.5% |
| **Return Rate** | Orders returned | >20% | 12-20% | 5-12% | <5% |
| **Time to Ship** | Order to dispatch | >48h | 24-48h | 12-24h | <12h |
| **Delivery Cost/Order** | Fulfillment cost | >$8 | $5-8 | $3-5 | <$3 |

## 3.3 Distribution KPIs

### Sales & Territory

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Numeric Distribution** | % outlets stocking | <40% | 40-60% | 60-80% | >80% |
| **Weighted Distribution** | Sales-weighted | <50% | 50-70% | 70-85% | >85% |
| **Share of Shelf** | Shelf space % | <Fair share | Fair share | >Fair+20% | >Fair+40% |
| **Sales per Route** | Route productivity | <$2K/day | $2-4K | $4-7K | >$7K |
| **Strike Rate** | Orders per visit | <50% | 50-70% | 70-85% | >85% |

### Operations

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Warehouse Turns** | Inventory velocity | <10 | 10-15 | 15-25 | >25 |
| **Fill Rate** | Orders complete | <90% | 90-95% | 95-98% | >98% |
| **Delivery Accuracy** | Correct deliveries | <95% | 95-98% | 98-99.5% | >99.5% |
| **Returns %** | Products returned | >5% | 2-5% | 0.5-2% | <0.5% |
| **Days Inventory Outstanding** | Inventory days | >40 | 30-40 | 20-30 | <20 |

## 3.4 Omnichannel KPIs

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Cross-Channel Customers** | Multi-channel % | <10% | 10-20% | 20-35% | >35% |
| **Click & Collect Adoption** | BOPIS usage | <5% | 5-15% | 15-30% | >30% |
| **Unified Inventory Accuracy** | Cross-channel sync | <90% | 90-95% | 95-99% | >99% |
| **Cross-Channel LTV Premium** | Multi vs single | <20% | 20-40% | 40-80% | >80% |

---

*End of Part 1 - Continue to Part 2 for Dimensions 4-7*
# Dimension 4: Regulatory Landscape

## 4.1 Business Licenses & Permits

### Retail Licenses

| License Type | Issuing Authority | Validity | Cost Range |
|--------------|-------------------|----------|------------|
| Trade License | Ministry of Commerce/Economy | 1-3 years | $200-2,000 |
| Commercial Registration | Chamber of Commerce | Annual | $100-500 |
| Municipality License | Local Municipality | Annual | $200-2,000 |
| Food Handling License | Health/Food Authority | 1-2 years | $300-1,500 |
| Alcohol License | Special Authority | Annual | $5K-50K (where permitted) |
| Tobacco License | Ministry of Commerce | Annual | $500-2,000 |
| Pharmacy License | Drug Authority | Annual | $2K-10K |

### E-commerce Licenses

| License Type | Issuing Authority | Validity | Cost Range |
|--------------|-------------------|----------|------------|
| E-commerce License | Economy Ministry | 1-3 years | $500-3,000 |
| Payment Gateway Approval | Central Bank | 1-3 years | $2K-20K |
| Data Protection Registration | Data Authority | Varies | $500-5,000 |
| Cross-Border E-commerce | Customs | Annual | $1K-10K |

### Wholesale/Distribution Licenses

| License Type | Issuing Authority | Validity | Cost Range |
|--------------|-------------------|----------|------------|
| Import License | Trade Ministry | Annual | $500-5,000 |
| Wholesale Trade License | Commerce Ministry | 1-3 years | $500-3,000 |
| Cold Storage License | Health Authority | Annual | $1K-5K |
| Bonded Warehouse | Customs | Annual | $5K-25K |
| Food Distribution License | Food Safety Authority | 1-2 years | $1K-5K |

## 4.2 Consumer Protection Requirements

### Key Regulations

| Requirement | Standard | Applicability |
|-------------|----------|---------------|
| Price Display | Clear visible pricing | All retail |
| Receipt Provision | Itemized receipts | All sales |
| Return Policy | Clear policy display | All retail |
| Warranty Terms | Written warranties | Durable goods |
| Product Safety | Safety standards | All products |
| Halal Certification | Religious compliance | Food, cosmetics |
| Arabic Labeling | Language requirement | All consumer goods |
| Expiry Date Display | Clear date marking | Food, cosmetics, pharma |

### E-commerce Specific

| Requirement | Description |
|-------------|-------------|
| Clear Pricing | All-in pricing including delivery |
| Payment Security | PCI-DSS compliance |
| Privacy Policy | Data usage transparency |
| Terms of Service | Clear T&Cs |
| Return/Refund Rights | Cooling-off periods (varies) |
| Electronic Contracts | Digital signature validity |

## 4.3 Product Category Regulations

### Food & Grocery

| Requirement | Authority | Standard |
|-------------|-----------|----------|
| Food Safety | Food Safety Authority | HACCP, local standards |
| Halal Certification | Islamic Authority | Halal standards |
| Nutritional Labeling | Health Ministry | Mandatory disclosure |
| Expiry Dating | Food Authority | Date marking rules |
| Import Permits | Agriculture/Food Authority | Per shipment |
| Cold Chain | Health Authority | Temperature standards |

### Cosmetics & Personal Care

| Requirement | Authority | Standard |
|-------------|-----------|----------|
| Product Registration | Drug/Health Authority | Pre-market approval |
| Ingredient Disclosure | Health Authority | Full ingredient list |
| Safety Testing | Regulatory Authority | Product safety data |
| Import License | Health Ministry | Per product |
| Halal Status | Islamic Authority | For Muslim markets |

### Electronics

| Requirement | Authority | Standard |
|-------------|-----------|----------|
| SASO/ESMA Compliance | Standards Authority | Technical standards |
| Energy Efficiency | Energy Authority | Efficiency ratings |
| Warranty Requirements | Consumer Protection | Minimum warranty |
| Import Standards | Customs/Standards | Type approval |

## 4.4 Regulatory Bodies by Country

### Egypt

| Authority | Responsibility |
|-----------|---------------|
| Ministry of Trade & Industry | Trade licensing |
| NFSA | Food safety |
| Consumer Protection Authority | Consumer rights |
| Central Bank of Egypt | Payment regulation |
| NTRA | Telecom/e-commerce |

### Saudi Arabia

| Authority | Responsibility |
|-----------|---------------|
| Ministry of Commerce | Trade licensing |
| SFDA | Food, drug, cosmetics |
| CITC | E-commerce, digital |
| SAMA | Payment systems |
| SASO | Standards |

### UAE

| Authority | Responsibility |
|-----------|---------------|
| DED/DET | Trade licensing |
| Dubai Municipality | Health, safety |
| ESMA | Standards |
| Central Bank | Payments |
| TDRA | E-commerce |

### Jordan

| Authority | Responsibility |
|-----------|---------------|
| MIT | Trade licensing |
| JFDA | Food, drugs |
| Consumer Protection | Consumer rights |
| Central Bank | Payments |

## 4.5 Certifications

| Certification | Purpose | Cost Range | Validity |
|---------------|---------|------------|----------|
| ISO 9001 | Quality management | $3K-15K | 3 years |
| ISO 22000 | Food safety | $5K-25K | 3 years |
| HACCP | Food safety (retail) | $2K-10K | 1-3 years |
| PCI-DSS | Payment security | $5K-50K | Annual |
| Halal Certification | Islamic compliance | $1K-5K | Annual |
| Organic Certification | Organic products | $2K-10K | Annual |

---

# Dimension 5: Competitive Dynamics

## 5.1 Market Structure

| Subsector | Concentration | Key Players | Fragmentation |
|-----------|---------------|-------------|---------------|
| Hypermarket | High | Carrefour, Lulu, Panda | Few large players |
| Supermarket | Medium | Regional chains | Moderate |
| Convenience | Low | Independents, chains | Highly fragmented |
| Fashion | Medium | Global + regional | Moderate |
| Electronics | Medium-High | eXtra, Sharaf DG, chains | Consolidating |
| E-commerce | Medium | Amazon, Noon, locals | Consolidating |
| FMCG Distribution | Medium | Nationals, MNCs | Moderate |

## 5.2 Porter's Five Forces

```
┌─────────────────────────────────────────────────────────────────────┐
│              RETAIL FIVE FORCES SUMMARY                             │
├─────────────────────────────────────────────────────────────────────┤
│                                                                      │
│                  NEW ENTRANTS: 2.5/5                                │
│                  (E-commerce lowering barriers)                      │
│                        │                                            │
│                        ▼                                            │
│   SUPPLIER POWER ────────────► INDUSTRY ◄───── BUYER POWER         │
│       3/5                      RIVALRY           4/5               │
│   (Big brands                   4.5/5        (Price transparency,   │
│    have power)              (Intense, multi-    easy switching)     │
│                              channel)                               │
│                        │                                            │
│                        ▼                                            │
│                SUBSTITUTES: 3/5                                     │
│                (Online vs offline, D2C)                             │
│                                                                      │
│   OVERALL ATTRACTIVENESS: MODERATE-CHALLENGING                      │
│   Key: Differentiation + Omnichannel + Customer loyalty            │
└─────────────────────────────────────────────────────────────────────┘
```

### Force Analysis

| Force | Rating | Key Factors |
|-------|--------|-------------|
| **New Entrants** | 2.5/5 | E-commerce lowers barriers; prime locations limited |
| **Supplier Power** | 3/5 | Strong brands have power; many alternatives exist |
| **Buyer Power** | 4/5 | High price transparency; easy to compare and switch |
| **Substitutes** | 3/5 | Online substitutes offline; D2C bypasses retail |
| **Rivalry** | 4.5/5 | Intense competition; promotional pressure; e-commerce disruption |

## 5.3 Competitive Strategies

| Strategy | Description | Best For | Requirements |
|----------|-------------|----------|--------------|
| Cost Leadership | Lowest price positioning | Discount/value | Scale, efficiency |
| Differentiation | Unique assortment/experience | Specialty, premium | Brand, curation |
| Convenience | Location, speed, ease | Convenience, e-commerce | Network, technology |
| Private Label | Own brand development | Grocery, fashion | Scale, sourcing |
| Omnichannel | Seamless cross-channel | Modern retailers | Technology, integration |
| Community/Local | Neighborhood focus | Independent, specialty | Relationships, service |
| Vertical Integration | Control supply chain | D2C brands | Capital, expertise |

## 5.4 Industry Trends

| Trend | Impact | Timeframe | SME Opportunity |
|-------|--------|-----------|-----------------|
| **E-commerce Growth** (25-40% CAGR) | Massive disruption | Ongoing | Must adapt or specialize |
| **Social Commerce** | New channel | 1-3 years | Low-cost entry |
| **Q-Commerce** (Quick delivery) | Speed expectations | Ongoing | Partnership or niche |
| **Private Label Growth** | Margin opportunity | Ongoing | Sourcing capability |
| **Omnichannel Integration** | Customer expectation | 2-5 years | Investment required |
| **Sustainability** | Consumer preference | 3-7 years | Differentiation |
| **Personalization** | Data-driven | 2-5 years | Technology adoption |
| **Digital Payments** | Cash decline | Ongoing | Infrastructure |
| **Experience Retail** | Store differentiation | 2-5 years | Innovation |

## 5.5 Major Player Landscape

### Regional E-commerce

| Platform | Markets | Model | Threat Level |
|----------|---------|-------|--------------|
| Amazon (Souq) | UAE, Saudi, Egypt | 1P + 3P | Very High |
| Noon | UAE, Saudi, Egypt | 1P + 3P | Very High |
| Namshi | UAE, Saudi | Fashion | High |
| Jumia | Egypt, Morocco | 3P Marketplace | High |
| Talabat/Snoonu | Gulf | Q-commerce | High |

### Regional Retail Chains

| Chain | Format | Markets | Strength |
|-------|--------|---------|----------|
| Carrefour (MAF) | Hyper/Super | Pan-MENA | Scale, locations |
| Lulu | Hyper/Super | Gulf, Egypt | Value, fresh |
| Panda | Hyper/Super | Saudi | Local knowledge |
| Centrepoint | Fashion/Home | Gulf | Multi-format |
| Sharaf DG | Electronics | Gulf | Category expertise |

## 5.6 Market-Specific Dynamics

| Country | Retail Value | E-commerce % | Key Dynamics |
|---------|--------------|--------------|--------------|
| **UAE** | $60-80B | 18-25% | Most advanced e-commerce; expat-driven; mall culture |
| **Saudi** | $150-180B | 12-18% | Largest market; Vision 2030; rapid digitization |
| **Egypt** | $70-90B | 4-6% | Largest population; price-sensitive; informal sector |
| **Morocco** | $30-40B | 3-5% | EU influence; growing middle class |
| **Jordan** | $12-15B | 6-9% | Small but tech-savvy; regional hub potential |

---

# Dimension 6: Digital Maturity

## 6.1 Technology Adoption Benchmarks

| Subsector | Current Adoption | Digital Leaders | Digital Laggards | Key Gap |
|-----------|------------------|-----------------|------------------|---------|
| Hypermarket/Super | Medium-High | 40% | 25% | Omnichannel |
| Convenience | Low | 10% | 60% | POS, inventory |
| Fashion Retail | Medium | 35% | 30% | E-commerce |
| Electronics | Medium-High | 45% | 20% | Online integration |
| E-commerce | High | 70% | 10% | Advanced analytics |
| FMCG Distribution | Medium | 30% | 35% | Sales force automation |
| B2B Wholesale | Low-Medium | 20% | 50% | Digital ordering |

## 6.2 Digital Maturity Levels

```
┌─────────────────────────────────────────────────────────────────────────────┐
│              RETAIL DIGITAL MATURITY LEVELS                                  │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  LEVEL 1: ANALOG (Score 0-20)                                               │
│  • Cash register, paper records, no digital presence                        │
│  • Typical: Traditional souks, small independents                          │
│                                                                              │
│  LEVEL 2: BASIC DIGITAL (Score 21-40)                                       │
│  • Basic POS, social media presence, WhatsApp orders                        │
│  • Typical: Small chains, progressive independents                         │
│                                                                              │
│  LEVEL 3: CONNECTED (Score 41-60)                                           │
│  • Integrated POS/inventory, basic e-commerce, loyalty program              │
│  • Typical: Medium retailers, regional chains                              │
│                                                                              │
│  LEVEL 4: INTEGRATED (Score 61-80)                                          │
│  • ERP, omnichannel, CRM, analytics, automation                            │
│  • Typical: Leading chains, digital-forward brands                         │
│                                                                              │
│  LEVEL 5: INTELLIGENT (Score 81-100)                                        │
│  • AI/ML personalization, predictive, automated operations                  │
│  • Typical: E-commerce leaders, tech-native retailers                      │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 6.3 Core Technology Systems

### Retail Systems

| System | Priority | Investment Range | Payback | MENA Adoption |
|--------|----------|------------------|---------|---------------|
| Modern POS | Critical | $2K-20K/store | 6-12 mo | 60% |
| Inventory Management | Critical | $5K-50K | 6-18 mo | 45% |
| E-commerce Platform | High | $5K-100K | 12-24 mo | 35% |
| CRM/Loyalty | High | $3K-30K | 12-24 mo | 25% |
| ERP | Medium-High | $20K-200K | 18-36 mo | 30% |
| Analytics/BI | Medium | $5K-50K | 12-24 mo | 20% |
| Mobile App | Medium | $10K-100K | 12-24 mo | 15% |
| Self-Checkout | Low-Medium | $10K-50K/unit | 24-36 mo | 5% |

### Distribution Systems

| System | Priority | Investment Range | Payback | MENA Adoption |
|--------|----------|------------------|---------|---------------|
| Sales Force Automation | High | $3K-30K | 6-12 mo | 35% |
| Route Planning | High | $5K-30K | 6-12 mo | 25% |
| WMS | Medium-High | $10K-100K | 12-24 mo | 30% |
| DMS (Distribution) | High | $10K-80K | 12-18 mo | 25% |
| B2B E-commerce | Medium | $10K-80K | 12-24 mo | 15% |
| Demand Planning | Medium | $10K-50K | 12-24 mo | 15% |

## 6.4 E-commerce Platform Options

| Platform Type | Examples | Best For | Cost Range/Month |
|---------------|----------|----------|------------------|
| SaaS (Basic) | Shopify, WooCommerce | Small retailers | $30-300 |
| SaaS (Advanced) | Shopify Plus, BigCommerce | Medium retailers | $300-2,000 |
| Marketplace | Amazon, Noon, Namshi | All sizes | Commission-based |
| Custom | Magento, custom build | Large retailers | $2K-20K+ |
| Social Commerce | Instagram, Facebook | Small/D2C | Platform fees |
| WhatsApp Commerce | WhatsApp Business | Small/local | Low cost |

## 6.5 High-Impact Digital Interventions

| Subsector | Priority 1 | Priority 2 | Priority 3 | Impact |
|-----------|------------|------------|------------|--------|
| Grocery | Inventory mgmt | E-commerce | Loyalty | 15-25% efficiency |
| Fashion | E-commerce | CRM | Omnichannel | 25-50% revenue |
| Electronics | Online presence | Price mgmt | Service integration | 20-35% revenue |
| Distribution | Sales force automation | Route optimization | B2B e-commerce | 20-30% productivity |
| Convenience | Modern POS | Digital payments | Inventory | 10-20% efficiency |

## 6.6 Digital Payment Landscape

| Payment Method | UAE | Saudi | Egypt | Jordan |
|----------------|-----|-------|-------|--------|
| Cards | 55-65% | 35-45% | 15-25% | 20-30% |
| Digital Wallets | 15-25% | 10-20% | 5-10% | 5-10% |
| Cash | 20-30% | 35-50% | 65-80% | 60-70% |
| BNPL | 3-8% | 5-12% | 1-3% | 2-5% |

---

# Dimension 7: Workforce Norms

## 7.1 Organizational Structures

### Small Retail Store (5-15 employees)
```
              Owner/Manager
                   │
       ┌───────────┼───────────┐
       │           │           │
    Supervisor   Cashiers    Stock
      (1)        (2-4)       (2-4)
```

### Medium Retailer (30-80 employees)
```
                General Manager
                     │
        ┌────────────┼────────────┐
        │            │            │
     Store       Operations    Finance/
    Manager       Manager       Admin
        │            │            │
   ┌────┴────┐   ┌───┴───┐    Accountant
Supervisors  Sales  Buyers  Logistics   (1-2)
  (3-5)     Team   (2-4)    (3-6)
             (15-30)
```

### FMCG Distributor (50-150 employees)
```
                   General Manager
                        │
       ┌────────────────┼────────────────┐
       │                │                │
    Sales            Operations       Finance
   Director           Manager         Manager
       │                │                │
   ┌───┴───┐       ┌────┴────┐      ┌───┴───┐
  Area     Key    Warehouse  Delivery  AR    HR
 Managers Account  Team       Fleet   (2-3)  (1-2)
  (3-5)   (2-4)   (10-30)   (20-60)
    │
 Sales Reps
  (20-50)
```

## 7.2 Key Roles

### Retail Roles

| Role | Responsibilities | Experience | Education |
|------|------------------|------------|-----------|
| Store Manager | Overall store P&L | 5-10 years | Degree preferred |
| Department Manager | Category management | 3-5 years | Diploma+ |
| Buyer/Merchandiser | Product selection, pricing | 3-7 years | Degree |
| Visual Merchandiser | Store presentation | 2-5 years | Design background |
| Sales Associate | Customer service, sales | 0-2 years | Secondary |
| Cashier | Transaction processing | 0-1 year | Secondary |
| Stock/Inventory | Receiving, stocking | 0-2 years | Secondary |

### E-commerce Roles

| Role | Responsibilities | Experience | Skills |
|------|------------------|------------|--------|
| E-commerce Manager | Online P&L, strategy | 5-8 years | Digital, analytics |
| Digital Marketing | Traffic acquisition | 3-5 years | Performance marketing |
| Content Manager | Product content, SEO | 2-4 years | Writing, SEO |
| Customer Service | Online support | 1-3 years | Communication |
| Fulfillment Manager | Order processing | 3-5 years | Operations |
| Data Analyst | Performance analytics | 2-4 years | Analytics, SQL |

### Distribution Roles

| Role | Responsibilities | Experience | Requirements |
|------|------------------|------------|--------------|
| Sales Manager | Territory P&L | 5-10 years | Sales experience |
| Key Account Manager | Major customer management | 4-7 years | Negotiation |
| Sales Representative | Route sales | 1-4 years | License, local knowledge |
| Merchandiser | In-store execution | 1-3 years | Attention to detail |
| Warehouse Supervisor | Operations oversight | 3-5 years | Logistics experience |
| Delivery Driver | Customer delivery | 1-3 years | License |

## 7.3 Compensation Benchmarks (USD/month)

### Egypt

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Store Manager | $400-600 | $600-1,000 | $1,000-1,800 |
| Sales Associate | $120-180 | $180-280 | $280-400 |
| Cashier | $100-150 | $150-220 | $220-320 |
| Sales Rep (Distribution) | $200-350 | $350-550 | $550-850 |
| E-commerce Manager | $600-1,000 | $1,000-1,800 | $1,800-3,000 |

### Saudi Arabia

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Store Manager | $2,500-3,500 | $3,500-5,500 | $5,500-8,500 |
| Sales Associate | $800-1,200 | $1,200-1,800 | $1,800-2,500 |
| Cashier | $700-1,000 | $1,000-1,400 | $1,400-1,800 |
| Sales Rep (Distribution) | $1,500-2,500 | $2,500-4,000 | $4,000-6,000 |
| E-commerce Manager | $4,000-6,000 | $6,000-10,000 | $10,000-15,000 |

### UAE

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Store Manager | $3,000-4,500 | $4,500-7,000 | $7,000-12,000 |
| Sales Associate | $800-1,300 | $1,300-2,000 | $2,000-3,000 |
| Cashier | $700-1,000 | $1,000-1,500 | $1,500-2,200 |
| Sales Rep (Distribution) | $1,500-2,500 | $2,500-4,500 | $4,500-7,000 |
| E-commerce Manager | $5,000-8,000 | $8,000-13,000 | $13,000-20,000 |

### Jordan

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Store Manager | $600-900 | $900-1,400 | $1,400-2,200 |
| Sales Associate | $280-400 | $400-600 | $600-850 |
| Cashier | $250-350 | $350-500 | $500-700 |
| Sales Rep (Distribution) | $450-700 | $700-1,100 | $1,100-1,600 |
| E-commerce Manager | $800-1,400 | $1,400-2,500 | $2,500-4,000 |

## 7.4 Skills Gap Analysis

| Skill Area | Availability | Demand | Gap Severity |
|------------|--------------|--------|--------------|
| E-commerce/Digital | Low | Very High | **Critical** |
| Data Analytics | Low | High | **High** |
| Digital Marketing | Low-Medium | Very High | **Critical** |
| Customer Experience | Medium | High | **Medium-High** |
| Inventory Management | Medium | High | **Medium** |
| Omnichannel Operations | Low | High | **High** |
| Category Management | Medium | High | **Medium** |
| Sales Leadership | Medium | High | **Medium** |

## 7.5 Labor Market Characteristics

| Characteristic | Egypt | Saudi Arabia | UAE | Jordan |
|---------------|-------|--------------|-----|--------|
| Local vs Expat | 95% local | 35/65 | 15/85 | 80/20 |
| Retail Turnover | 35-50% | 25-40% | 40-60% | 30-45% |
| Female Participation | 20-30% | 25-35% | 40-50% | 25-35% |
| Nationalization | N/A | High (Saudization) | Medium | N/A |
| Minimum Wage Impact | High | Low | Low | Medium |

## 7.6 HR KPIs

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| Staff Turnover | >50% | 35-50% | 20-35% | <20% |
| Sales/Employee | See D2 | See D2 | See D2 | See D2 |
| Absenteeism | >10% | 5-10% | 2-5% | <2% |
| Training Hours/Year | <8 | 8-16 | 16-32 | >32 |
| Employee NPS | <20 | 20-35 | 35-50 | >50 |

---

*End of Part 2 - Continue to Part 3 for Dimensions 8-11*
# Dimension 8: Supply Chain

## 8.1 Sourcing Models

### Retail Sourcing

| Model | Description | Typical Use | Margin Impact |
|-------|-------------|-------------|---------------|
| Direct Import | Import from manufacturers | Large retailers | Highest margins |
| Local Distributor | Via authorized distributor | Medium retailers | Standard margins |
| Wholesaler | Via wholesale market | Small retailers | Lower margins |
| Consignment | Pay after sale | Fashion, electronics | Reduced risk |
| D2C Brand Direct | Manufacturer direct | Specialty | Negotiated |
| Private Label | Own brand sourcing | Grocery, fashion | Higher margins |

### Distribution Sourcing

| Model | Description | Working Capital | Control |
|-------|-------------|-----------------|---------|
| Principal Distributor | Exclusive brand rights | High | High |
| Multi-Brand Distributor | Multiple principals | Medium-High | Medium |
| Cash & Carry | Retailer pickup | Low | Low |
| Drop-Ship | Direct to customer | Very Low | Low |

## 8.2 Supplier Relationships

### Retail Supplier Terms

| Supplier Type | Payment Terms | Typical MOQ | Relationship |
|---------------|---------------|-------------|--------------|
| Large FMCG (P&G, Nestle) | Net 30-60 | Standard | Terms set |
| Fashion Brands | COD to Net 30 | Seasonal | Variable |
| Local Manufacturers | Net 15-45 | Negotiable | Relationship-based |
| Private Label | Net 30-60 | Per container | Partnership |
| Imports (Direct) | LC/TT advance | Per container | Formal |

### Distribution Terms with Principals

| Term Type | Range | Notes |
|-----------|-------|-------|
| Distributor Margin | 8-25% | Category dependent |
| Payment to Principal | Net 30-90 | Relationship dependent |
| Marketing Support | 2-8% of sales | Joint activities |
| Target Bonuses | 1-5% | Performance incentives |
| Exclusivity Period | 1-5 years | Territory rights |

## 8.3 Inventory Management

### Category Management Approaches

| Category Type | Assortment Depth | Turns Target | Margin Target |
|---------------|------------------|--------------|---------------|
| Destination (Traffic) | Broad | High (>15) | Low (15-25%) |
| Routine (Staples) | Medium | High (12-20) | Low-Medium |
| Convenience | Narrow | Medium (8-15) | Medium |
| Seasonal | Variable | Low (2-6) | Medium-High |
| Specialty/Impulse | Selective | Medium (6-12) | High (>40%) |

### Inventory Optimization

| Strategy | Application | Impact |
|----------|-------------|--------|
| ABC Analysis | Prioritize fast movers | 15-25% reduction |
| Safety Stock Optimization | Balance service vs cost | 10-20% reduction |
| Demand Forecasting | Predict sales patterns | 20-30% accuracy |
| Automated Replenishment | System-driven ordering | 25-40% efficiency |
| Markdown Optimization | Dynamic clearance | 5-15% margin save |

## 8.4 Fulfillment Models

### E-commerce Fulfillment

| Model | Description | Best For | Cost/Order |
|-------|-------------|----------|------------|
| In-Store Fulfillment | Pick from store | Omnichannel | $2-4 |
| Dark Store | Dedicated fulfillment | Q-commerce | $3-6 |
| Central Warehouse | DC fulfillment | Pure e-commerce | $3-5 |
| 3PL Fulfillment | Outsourced | Scaling | $4-8 |
| Dropship | Supplier ships | Marketplace | Minimal |
| Click & Collect | Customer pickup | Omnichannel | $1-2 |

### Delivery Options

| Option | Timeframe | Customer Expectation | Cost |
|--------|-----------|---------------------|------|
| Same-Day | <6 hours | Growing rapidly | $5-15 |
| Next-Day | 12-24 hours | Standard (Gulf) | $3-8 |
| 2-3 Day | 48-72 hours | Standard (Egypt) | $2-5 |
| Scheduled | Customer choice | Preferred | $3-6 |
| Click & Collect | Customer pickup | Growing | Free-$2 |

## 8.5 Distribution Network Design

### Store Network Optimization

| Factor | Weight | Consideration |
|--------|--------|---------------|
| Population Density | High | Catchment analysis |
| Competition | High | White space mapping |
| Rent/Occupancy Cost | High | 4-wall profitability |
| Accessibility | Medium | Parking, transport |
| Demographics | Medium | Target customer fit |
| Visibility | Medium | Brand presence |

### Distribution Territory Design

| Factor | Consideration |
|--------|---------------|
| Geographic Coverage | Drive time, route density |
| Channel Mix | Traditional vs modern trade |
| Outlet Universe | Total addressable outlets |
| Frequency Needs | Visit cycle requirements |
| Volume Density | Revenue per route |

## 8.6 Returns Management

### Return Rates by Category

| Category | E-commerce | Physical | Key Reasons |
|----------|------------|----------|-------------|
| Fashion/Apparel | 20-40% | 5-15% | Fit, style |
| Electronics | 5-15% | 3-8% | Defects, change of mind |
| Health/Beauty | 3-8% | 1-3% | Allergic reaction |
| Home/Furniture | 10-20% | 3-8% | Size, quality |
| Grocery | 1-3% | 1-2% | Quality, expiry |

### Returns Processing

| Process Step | Cost Impact | Best Practice |
|--------------|-------------|---------------|
| Return Receipt | $0.50-1 | Centralized processing |
| Quality Inspection | $0.30-1 | Standardized grading |
| Restocking | $0.50-2 | Quick turnaround |
| Refurbishment | $2-20 | Category-specific |
| Liquidation | Revenue loss | Secondary channels |

---

# Dimension 9: Export Requirements

## 9.1 Cross-Border E-commerce

### Export Capabilities

| Capability | Requirements | Key Markets |
|------------|--------------|-------------|
| Cross-Border Selling | Logistics, payments, compliance | GCC intra-regional |
| Marketplace Export | Platform requirements | Global (Amazon, etc.) |
| D2C International | Website localization | Diaspora markets |
| B2B Export | Trade documentation | Regional |

### Cross-Border Logistics

| Model | Description | Cost Structure |
|-------|-------------|----------------|
| Direct Shipping | Ship from origin | High per unit |
| Bonded Warehouse | Pre-position stock | Medium setup |
| Fulfillment Partner | 3PL in destination | Per order |
| Marketplace FBA | Platform fulfillment | Fees + storage |

## 9.2 Product Export Considerations

### Regulatory Requirements

| Requirement | Details |
|-------------|---------|
| Product Registration | May need registration in destination |
| Labeling | Language, regulatory compliance |
| Certifications | Standards compliance (SASO, ESMA) |
| Customs Classification | HS codes, duties |
| Halal Certification | Required for food, cosmetics |

### Documentation

| Document | Purpose |
|----------|---------|
| Commercial Invoice | Transaction record |
| Packing List | Contents detail |
| Certificate of Origin | Preferential duties |
| Health Certificate | Food, cosmetics |
| Halal Certificate | Islamic compliance |

## 9.3 Distribution Rights Export

### Territory Expansion

| Model | Description | Requirements |
|-------|-------------|--------------|
| Master Distributor | Export distribution rights | Principal approval |
| Sub-Distribution | Appoint sub-distributors | Territory management |
| Franchise Export | Retail concept export | Brand standards |

---

# Dimension 10: Packaging & Labeling

## 10.1 Retail Packaging Requirements

### Consumer Packaging

| Element | Requirement | Standard |
|---------|-------------|----------|
| Arabic Language | Mandatory in MENA | Local regulations |
| Ingredients List | Full disclosure | Category-specific |
| Nutritional Info | Mandatory for food | GCC/national standards |
| Expiry Date | Clear marking | Product category |
| Country of Origin | Disclosure | Trade regulations |
| Net Weight/Volume | Accurate | Standards authority |
| Barcode | EAN/UPC | GS1 standards |

### Category-Specific Requirements

| Category | Special Requirements |
|----------|---------------------|
| Food | Nutritional facts, allergens, halal |
| Cosmetics | Full ingredients (INCI), warnings |
| Electronics | Energy rating, safety marks |
| Textiles | Composition, care instructions |
| Children's Products | Safety warnings, age suitability |

## 10.2 Labeling Standards

### Price Labeling

| Requirement | Standard |
|-------------|----------|
| Shelf Price | Clear, visible |
| Unit Pricing | Per kg/liter where required |
| Promotional Price | Clear original/sale |
| Currency | Local currency |
| VAT | Inclusive pricing |

### Product Labeling

| Standard | Application | Authority |
|----------|-------------|-----------|
| GSO Standards | GCC countries | GSO |
| SFDA Requirements | Saudi | SFDA |
| ESMA | UAE | ESMA |
| Egyptian Standards | Egypt | EOS |

## 10.3 Private Label Packaging

| Element | Consideration |
|---------|---------------|
| Brand Identity | Consistent design system |
| Legal Compliance | All regulatory requirements |
| Quality Perception | Packaging materials |
| Cost Efficiency | Production economics |
| Sustainability | Eco-friendly options |

---

# Dimension 11: MENA Regional Context

## 11.1 Country Profiles

### Egypt

| Attribute | Details |
|-----------|---------|
| **Population** | 105+ million |
| **Retail Market** | $70-90 billion |
| **E-commerce Penetration** | 4-6% |
| **Key Characteristics** | Price-sensitive, informal sector dominant, cash-heavy |
| **Growth Drivers** | Youth bulge, smartphone penetration, fintech |
| **Challenges** | Inflation, currency volatility, logistics infrastructure |
| **Opportunities** | E-commerce growth, modern trade expansion, fintech |

### Saudi Arabia

| Attribute | Details |
|-----------|---------|
| **Population** | 35+ million |
| **Retail Market** | $150-180 billion |
| **E-commerce Penetration** | 12-18% |
| **Key Characteristics** | High spending power, Vision 2030 transformation |
| **Growth Drivers** | Entertainment sector growth, tourism, Saudization |
| **Challenges** | Saudization costs, competition, seasonality |
| **Opportunities** | Entertainment retail, experience retail, private label |

### UAE

| Attribute | Details |
|-----------|---------|
| **Population** | 10+ million |
| **Retail Market** | $60-80 billion |
| **E-commerce Penetration** | 18-25% |
| **Key Characteristics** | Most mature e-commerce, expat-driven, premium focus |
| **Growth Drivers** | Tourism, expo legacy, regional hub |
| **Challenges** | High rents, competition, labor costs |
| **Opportunities** | Omnichannel, luxury, regional e-commerce hub |

### Jordan

| Attribute | Details |
|-----------|---------|
| **Population** | 11+ million |
| **Retail Market** | $12-15 billion |
| **E-commerce Penetration** | 6-9% |
| **Key Characteristics** | Tech-savvy, regional refugees, educated workforce |
| **Growth Drivers** | Digital adoption, regional transit |
| **Challenges** | Small market, economic pressure |
| **Opportunities** | E-commerce, regional distribution |

### Morocco

| Attribute | Details |
|-----------|---------|
| **Population** | 37+ million |
| **Retail Market** | $30-40 billion |
| **E-commerce Penetration** | 3-5% |
| **Key Characteristics** | EU influence, growing middle class, French language |
| **Growth Drivers** | Infrastructure investment, Africa gateway |
| **Challenges** | E-commerce infrastructure, rural access |
| **Opportunities** | Modern trade expansion, Africa e-commerce |

## 11.2 Consumer Behavior Insights

### Shopping Patterns

| Behavior | Egypt | Saudi | UAE | Jordan |
|----------|-------|-------|-----|--------|
| Mall Shopping | High | Very High | Very High | High |
| Weekly Grocery | Traditional | Hypermarket | Supermarket | Traditional |
| E-commerce Use | Growing | High | Very High | Growing |
| Cash Payment | 70%+ | 40%+ | 25%+ | 65%+ |
| Social Commerce | Growing | High | High | Growing |
| Brand Loyalty | Medium | Medium-High | Low-Medium | Medium |

### Peak Seasons

| Season | Impact | Categories |
|--------|--------|------------|
| Ramadan | Very High | Food, fashion, gifts |
| Eid | Very High | Fashion, electronics, gifts |
| Back to School | High | Stationery, electronics, fashion |
| Summer | Medium | Travel, fashion |
| White Friday/Black Friday | High | Electronics, fashion, general |
| Year-End | Medium | General |

## 11.3 Regulatory Bodies

| Country | Trade | Food Safety | Consumer | E-commerce |
|---------|-------|-------------|----------|------------|
| Egypt | MTI | NFSA | CPA | NTRA |
| Saudi | MC | SFDA | MC | CITC |
| UAE | DED | Municipality | DED | TDRA |
| Jordan | MIT | JFDA | MIT | TRC |
| Morocco | MCI | ONSSA | MCI | ANRT |

## 11.4 Strategic Opportunities

| Opportunity | Markets | Potential | Requirements |
|-------------|---------|-----------|--------------|
| E-commerce Growth | All | Very High | Technology, logistics |
| Private Label | Saudi, UAE | High | Sourcing, quality |
| Convenience Retail | All | High | Location network |
| Q-Commerce | Gulf, Egypt | High | Dark stores, fleet |
| Omnichannel | Advanced markets | High | Integration |
| Social Commerce | All | Medium-High | Content, engagement |
| Sustainability | UAE, Saudi | Medium | Sourcing, packaging |

## 11.5 Business Culture Considerations

| Aspect | Consideration |
|--------|---------------|
| Relationships | Long-term partnerships valued |
| Negotiation | Extended process; flexibility expected |
| Payment Culture | Cash still significant; COD in e-commerce |
| Ramadan Impact | Reduced hours, evening peak, gift buying |
| Friday Operations | Closed/reduced in Gulf; normal in Egypt |
| Halal Importance | Critical for food, cosmetics, even fashion |
| Local Preference | National brands gaining ground |

---

# Document Summary

## Sector Overview

**Retail & Distribution** in MENA represents:

**Market Size:**
- ~$300-400 billion total MENA retail market
- E-commerce growing 25-40% annually
- Critical final link in supply chain to consumers

**Key Characteristics:**
- Rapid digital transformation (e-commerce, payments, operations)
- Young, mobile-first consumer base driving change
- Mall culture strong but diversifying to convenience and online
- Cash still dominant but declining rapidly
- Private label opportunity expanding

**SME Landscape:**
- Wide range from convenience stores to specialty retailers
- Distribution/wholesale as critical intermediary
- E-commerce enabling small players to reach markets
- Technology adoption becoming survival requirement

**Priority Subsectors:**
1. **E-commerce Pure Play** - 25-40% CAGR, highest growth
2. **Grocery/Supermarket** - Largest market, omnichannel transformation
3. **Fashion & Apparel** - Strong online growth, brand opportunities
4. **FMCG Distribution** - Digital transformation, B2B e-commerce
5. **Health & Beauty** - Fast-growing, e-commerce enabled

## Agent Usage Guide

| Agent | Primary Dimensions | Key Data Points |
|-------|-------------------|-----------------|
| **The Drucker** | 1, 11 | Subsector classification, MENA context |
| **The Marvin** | 3, 4 | Retail KPIs, compliance requirements |
| **The Graham** | 2 | Margins, working capital, valuation |
| **The Ricardo** | 9, 10 | Cross-border, labeling requirements |
| **The Lovelace** | 6 | Digital maturity, e-commerce platforms |
| **The Mayo** | 7 | Workforce, compensation, skills gaps |
| **The Ohno** | 8 | Supply chain, inventory, fulfillment |
| **The Porter** | 5 | Five Forces, competitive strategies |
| **The Landor** | 10 | Packaging standards, consumer labeling |

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | December 2025 | RootRise Product Team | Initial release |

---

*This document is part of the RootRise Sector Knowledge Pack series, providing comprehensive sector intelligence for The Pantheon multi-agent diagnostic system.*
