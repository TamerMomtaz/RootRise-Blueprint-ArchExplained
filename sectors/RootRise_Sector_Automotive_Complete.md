# RootRise Sector Knowledge Pack
# Automotive - Parts, Dealerships & Services
## Version 1.0 | December 2025

---

# Document Information

| Attribute | Value |
|-----------|-------|
| **Sector ID** | `automotive` |
| **Version** | 1.0 |
| **Last Updated** | December 2025 |
| **Status** | Active |
| **ISIC Rev.4 Divisions** | 29 (Motor Vehicles Manufacturing), 45 (Motor Vehicle Trade & Repair), 77 (Vehicle Rental) |
| **Primary Markets** | Egypt, Saudi Arabia, UAE, Jordan, Morocco |
| **SME Employee Range** | 5-200 |
| **SME Revenue Range** | $200K - $50M |

## Sector Overview

The MENA automotive sector represents a **$80-120 billion market** spanning vehicle assembly, parts manufacturing, dealerships, aftermarket services, and rental. While OEM manufacturing is limited to Egypt and Morocco, the **aftermarket, parts distribution, and services segments** offer significant SME opportunities across the region.

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                      AUTOMOTIVE VALUE CHAIN - MENA                               │
├─────────────────────────────────────────────────────────────────────────────────┤
│                                                                                  │
│   MANUFACTURING                    DISTRIBUTION                                  │
│   ─────────────                    ────────────                                  │
│                                                                                  │
│   ┌──────────────┐                 ┌──────────────────────┐                     │
│   │ VEHICLE      │                 │  AUTHORIZED          │                     │
│   │ ASSEMBLY     │                 │  DEALERSHIPS         │                     │
│   │ • Egypt      │────────────────►│  • New vehicles      │                     │
│   │ • Morocco    │                 │  • Certified used    │                     │
│   │ (Limited)    │                 │  • Warranty service  │                     │
│   └──────────────┘                 └──────────────────────┘                     │
│                                                                                  │
│   ┌──────────────┐                 ┌──────────────────────┐                     │
│   │ PARTS        │                 │  PARTS               │                     │
│   │ MANUFACTURING│                 │  DISTRIBUTION        │                     │
│   │ • OEM supply │────────────────►│  • Wholesale         │                     │
│   │ • Aftermarket│                 │  • Retail            │                     │
│   │ • Export     │                 │  • E-commerce        │                     │
│   └──────────────┘                 └──────────────────────┘                     │
│                                                                                  │
│   AFTERMARKET                      SERVICES                                      │
│   ───────────                      ────────                                      │
│                                                                                  │
│   ┌──────────────┐                 ┌──────────────────────┐                     │
│   │ INDEPENDENT  │                 │  VEHICLE SERVICES    │                     │
│   │ WORKSHOPS    │                 │  • Rental/leasing    │                     │
│   │ • Mechanical │                 │  • Fleet management  │                     │
│   │ • Electrical │                 │  • Insurance         │                     │
│   │ • Body/paint │                 │  • Financing         │                     │
│   └──────────────┘                 └──────────────────────┘                     │
│                                                                                  │
│   ┌──────────────┐                 ┌──────────────────────┐                     │
│   │ SPECIALIZED  │                 │  EMERGING            │                     │
│   │ SERVICES     │                 │  SEGMENTS            │                     │
│   │ • Tire       │                 │  • EV infrastructure │                     │
│   │ • Glass      │                 │  • Connected car     │                     │
│   │ • AC/cooling │                 │  • Mobility services │                     │
│   │ • Detailing  │                 │  • Used car tech     │                     │
│   └──────────────┘                 └──────────────────────┘                     │
│                                                                                  │
│   KEY MENA CHARACTERISTICS:                                                     │
│   • Limited local manufacturing (Egypt, Morocco only)                           │
│   • High import dependency for vehicles and parts                               │
│   • Large aftermarket opportunity (aging vehicle fleet)                         │
│   • Growing used car market (formalization opportunity)                         │
│   • EV transition beginning (UAE, Saudi leading)                                │
│   • Fleet management growing (corporate, government)                            │
│   • Strong luxury/premium segment in Gulf                                       │
│                                                                                  │
└─────────────────────────────────────────────────────────────────────────────────┘
```

## Applicable Countries

| Country Code | Country Name | Market Size Estimate | Key Characteristics |
|--------------|--------------|---------------------|---------------------|
| EG | Egypt | $8-12 billion | Local assembly, large aftermarket |
| SA | Saudi Arabia | $25-35 billion | Largest market, premium focus |
| AE | UAE | $20-30 billion | Premium/luxury, hub for re-export |
| JO | Jordan | $2-4 billion | Import dependent, services focus |
| MA | Morocco | $8-12 billion | Manufacturing hub for export |

---

# Dimension 1: Industry Classification

## 1.1 ISIC Rev.4 Classification

### Primary ISIC Codes

| Division | Description | SME Relevance |
|----------|-------------|---------------|
| **29** | Manufacture of motor vehicles, trailers and semi-trailers | **Medium** |
| **45** | Wholesale and retail trade and repair of motor vehicles | **Very High** |
| **77** | Rental and leasing activities (vehicles) | **High** |

### Detailed Class Breakdown

**Division 29 - Motor Vehicle Manufacturing:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| 2910 | Manufacture of motor vehicles | Low (capital intensive) |
| **2920** | **Manufacture of bodies (coachwork)** | **Medium** |
| **2930** | **Manufacture of parts and accessories** | **High** |

**Division 45 - Motor Vehicle Trade & Repair:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| **4510** | **Sale of motor vehicles** | **High** |
| **4520** | **Maintenance and repair of motor vehicles** | **Very High** |
| **4530** | **Sale of motor vehicle parts and accessories** | **Very High** |
| **4540** | **Sale, maintenance, repair of motorcycles** | **High** |

**Division 77 - Rental & Leasing:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| **7710** | **Renting and leasing of motor vehicles** | **High** |

## 1.2 Subsector Taxonomy

```json
{
  "subsectors": [
    {
      "subsector_id": "parts_manufacturing",
      "subsector_name": "Automotive Parts Manufacturing",
      "subsector_name_ar": "تصنيع قطع غيار السيارات",
      "description": "OEM and aftermarket parts production",
      "isic_codes": ["2930"],
      "typical_sme_size": "20-150 employees",
      "typical_sme_revenue": "$1M-$30M",
      "mena_market_size_estimate": "$5-8 billion",
      "growth_rate_5yr": "6-10%",
      "key_segments": ["Mechanical parts", "Electrical components", "Body parts", "Rubber/plastic"]
    },
    {
      "subsector_id": "new_vehicle_dealers",
      "subsector_name": "Authorized New Vehicle Dealerships",
      "subsector_name_ar": "وكلاء السيارات الجديدة",
      "description": "Franchise dealerships for new vehicles",
      "isic_codes": ["4510"],
      "typical_sme_size": "30-200 employees",
      "typical_sme_revenue": "$5M-$50M",
      "mena_market_size_estimate": "$30-45 billion",
      "growth_rate_5yr": "3-8%",
      "key_segments": ["Mass market", "Premium/luxury", "Commercial vehicles"]
    },
    {
      "subsector_id": "used_vehicle_dealers",
      "subsector_name": "Used Vehicle Sales",
      "subsector_name_ar": "بيع السيارات المستعملة",
      "description": "Pre-owned vehicle trading and certification",
      "isic_codes": ["4510"],
      "typical_sme_size": "5-50 employees",
      "typical_sme_revenue": "$500K-$15M",
      "mena_market_size_estimate": "$15-25 billion",
      "growth_rate_5yr": "8-15%",
      "key_segments": ["Retail lots", "Certified pre-owned", "Online platforms", "Auction"]
    },
    {
      "subsector_id": "parts_distribution",
      "subsector_name": "Parts Distribution & Retail",
      "subsector_name_ar": "توزيع قطع الغيار",
      "description": "Wholesale and retail of automotive parts",
      "isic_codes": ["4530"],
      "typical_sme_size": "10-100 employees",
      "typical_sme_revenue": "$1M-$25M",
      "mena_market_size_estimate": "$10-15 billion",
      "growth_rate_5yr": "5-10%",
      "key_segments": ["OEM parts", "Aftermarket", "Lubricants", "Tires", "Batteries"]
    },
    {
      "subsector_id": "authorized_service",
      "subsector_name": "Authorized Service Centers",
      "subsector_name_ar": "مراكز الخدمة المعتمدة",
      "description": "Brand-authorized maintenance and repair",
      "isic_codes": ["4520"],
      "typical_sme_size": "20-100 employees",
      "typical_sme_revenue": "$1M-$15M",
      "mena_market_size_estimate": "$5-8 billion",
      "growth_rate_5yr": "4-8%",
      "key_segments": ["Scheduled maintenance", "Warranty repair", "Recall work"]
    },
    {
      "subsector_id": "independent_workshops",
      "subsector_name": "Independent Repair Workshops",
      "subsector_name_ar": "ورش الإصلاح المستقلة",
      "description": "Non-franchise mechanical and body repair",
      "isic_codes": ["4520"],
      "typical_sme_size": "5-50 employees",
      "typical_sme_revenue": "$100K-$5M",
      "mena_market_size_estimate": "$8-12 billion",
      "growth_rate_5yr": "5-10%",
      "key_segments": ["General mechanical", "Electrical", "Body/paint", "Specialty"]
    },
    {
      "subsector_id": "tire_services",
      "subsector_name": "Tire Sales & Services",
      "subsector_name_ar": "خدمات الإطارات",
      "description": "Tire retail, fitting, repair, and retreading",
      "isic_codes": ["4530", "4520"],
      "typical_sme_size": "5-40 employees",
      "typical_sme_revenue": "$200K-$8M",
      "mena_market_size_estimate": "$4-6 billion",
      "growth_rate_5yr": "4-7%",
      "key_segments": ["Retail", "Fleet service", "Retreading", "Specialty"]
    },
    {
      "subsector_id": "vehicle_rental",
      "subsector_name": "Vehicle Rental & Leasing",
      "subsector_name_ar": "تأجير السيارات",
      "description": "Short-term rental and long-term leasing",
      "isic_codes": ["7710"],
      "typical_sme_size": "10-80 employees",
      "typical_sme_revenue": "$500K-$20M",
      "mena_market_size_estimate": "$5-8 billion",
      "growth_rate_5yr": "8-15%",
      "key_segments": ["Daily rental", "Corporate lease", "Chauffeur", "Specialty vehicles"]
    },
    {
      "subsector_id": "fleet_management",
      "subsector_name": "Fleet Management Services",
      "subsector_name_ar": "إدارة الأساطيل",
      "description": "Fleet operations, telematics, and management",
      "isic_codes": ["7710", "4520"],
      "typical_sme_size": "15-60 employees",
      "typical_sme_revenue": "$500K-$15M",
      "mena_market_size_estimate": "$2-4 billion",
      "growth_rate_5yr": "12-20%",
      "key_segments": ["Corporate fleet", "Government", "Logistics", "Ride-hail"]
    },
    {
      "subsector_id": "auto_detailing",
      "subsector_name": "Auto Detailing & Accessories",
      "subsector_name_ar": "تلميع وإكسسوارات السيارات",
      "description": "Detailing, customization, and accessories",
      "isic_codes": ["4520", "4530"],
      "typical_sme_size": "5-30 employees",
      "typical_sme_revenue": "$100K-$3M",
      "mena_market_size_estimate": "$1-2 billion",
      "growth_rate_5yr": "8-12%",
      "key_segments": ["Detailing", "Wrapping", "Tinting", "Accessories", "PPF"]
    }
  ]
}
```

## 1.3 Vehicle Categories

### By Vehicle Type

| Category | Market Segments | Key Brands MENA |
|----------|-----------------|-----------------|
| **Passenger Cars** | Economy, Mid-range, Premium, Luxury | Toyota, Hyundai, Nissan, BMW, Mercedes |
| **SUVs/Crossovers** | Compact, Mid-size, Full-size, Luxury | Toyota, Nissan, Lexus, Land Rover |
| **Light Commercial** | Pickup, Van, Minibus | Toyota, Nissan, Mitsubishi, Ford |
| **Heavy Commercial** | Trucks, Buses | MAN, Volvo, Mercedes, Hino |
| **Motorcycles** | Scooters, Sport, Touring | Honda, Yamaha, BMW |

### By Ownership Model

| Model | Description | Primary Users |
|-------|-------------|---------------|
| **Private Ownership** | Individual purchase | Consumers |
| **Corporate Fleet** | Company-owned vehicles | Businesses |
| **Operating Lease** | Long-term rental | Corporate |
| **Finance Lease** | Lease-to-own | SME, Individual |
| **Rental** | Short-term use | Tourists, temporary needs |

## 1.4 Value Chain Position

| Position | Description | Typical SME Type | Margin Profile |
|----------|-------------|------------------|----------------|
| **OEM Supplier (Tier 1/2)** | Direct to manufacturer | Parts manufacturer | 8-15% |
| **Aftermarket Manufacturer** | Non-OEM parts | Parts manufacturer | 15-30% |
| **Importer/Distributor** | Bring products to market | Trading company | 10-25% |
| **Wholesale** | B2B distribution | Parts wholesaler | 8-15% |
| **Retail** | End consumer sales | Dealer, retailer | 5-15% |
| **Service Provider** | Labor + parts | Workshop, service center | 25-45% |

## 1.5 Adjacent Sectors

| Adjacent Sector | Relationship | Integration Level |
|-----------------|--------------|-------------------|
| **Logistics & Transportation** | Fleet customers | Very High |
| **Financial Services** | Vehicle financing, insurance | Very High |
| **Retail & Distribution** | Sales channels | High |
| **Metal Fabrication** | Parts manufacturing | High |
| **Plastics & Rubber** | Parts manufacturing | High |
| **Electronics** | Components, diagnostics | High |
| **Real Estate** | Showroom, workshop facilities | Medium |

---

# Dimension 2: Financial Benchmarks

## 2.1 Parts Manufacturing

### Profitability by Segment

| Segment | Gross Margin | Operating Margin | Net Margin |
|---------|--------------|------------------|------------|
| OEM Supplier | 18-28% | 6-12% | 4-8% |
| Aftermarket Parts | 25-40% | 12-22% | 8-15% |
| Rubber/Plastic Parts | 22-35% | 10-18% | 6-12% |
| Metal Parts | 20-32% | 8-15% | 5-10% |
| Electrical Components | 25-38% | 12-20% | 8-14% |

### Cost Structure

| Cost Category | % of Revenue | Notes |
|---------------|--------------|-------|
| Raw Materials | 40-55% | Steel, aluminum, rubber, plastic |
| Direct Labor | 12-20% | Manufacturing workers |
| Overhead | 10-18% | Utilities, depreciation |
| SG&A | 8-15% | Sales, admin |
| R&D | 2-5% | Product development |

## 2.2 Dealership Economics

### New Vehicle Dealership

| Metric | Small Dealer | Mid-Size | Large Dealer |
|--------|--------------|----------|--------------|
| **Annual Units Sold** | 200-500 | 500-1,500 | 1,500-5,000+ |
| **Revenue** | $5-15M | $15-50M | $50-200M |
| **Gross Margin - Vehicles** | 4-8% | 5-10% | 6-12% |
| **Gross Margin - Parts** | 25-35% | 28-38% | 30-40% |
| **Gross Margin - Service** | 40-55% | 45-58% | 48-60% |
| **Blended Gross Margin** | 12-18% | 15-22% | 18-25% |
| **Operating Margin** | 2-5% | 3-6% | 4-8% |

### Revenue Mix (Healthy Dealer)

| Revenue Stream | % of Revenue | % of Gross Profit |
|----------------|--------------|-------------------|
| New Vehicle Sales | 55-70% | 25-35% |
| Used Vehicle Sales | 15-25% | 20-30% |
| Parts Sales | 8-15% | 20-28% |
| Service Labor | 8-15% | 25-35% |
| F&I (Finance/Insurance) | 2-5% | 8-15% |

### Used Vehicle Dealership

| Metric | Small | Mid-Size | Large |
|--------|-------|----------|-------|
| **Annual Units** | 100-300 | 300-800 | 800-2,500 |
| **Average Selling Price** | $8-15K | $12-25K | $15-40K |
| **Gross Margin/Vehicle** | $800-2,000 | $1,500-3,500 | $2,000-5,000 |
| **Inventory Turn** | 6-10x | 8-12x | 10-15x |
| **Days to Sale** | 30-60 | 25-45 | 20-35 |

## 2.3 Parts Distribution

### Profitability

| Business Model | Gross Margin | Operating Margin | Net Margin |
|----------------|--------------|------------------|------------|
| OEM Distributor | 18-28% | 5-12% | 3-8% |
| Aftermarket Distributor | 25-40% | 10-18% | 6-12% |
| Retail (Parts Store) | 35-50% | 8-15% | 5-10% |
| E-commerce Parts | 20-35% | 5-12% | 3-8% |

### Working Capital

| Metric | Good | Average | Poor |
|--------|------|---------|------|
| Inventory Turns | >6x | 4-6x | <4x |
| Days Inventory | <60 | 60-90 | >90 |
| Days Receivable | <45 | 45-75 | >75 |
| Days Payable | 45-60 | 30-45 | <30 |

## 2.4 Service & Repair

### Workshop Profitability

| Workshop Type | Labor Margin | Parts Margin | Overall Margin |
|---------------|--------------|--------------|----------------|
| Authorized Service | 55-70% | 25-35% | 35-50% |
| Independent - Premium | 50-65% | 30-45% | 35-50% |
| Independent - Standard | 45-60% | 35-50% | 35-48% |
| Quick Service (Oil/Tire) | 40-55% | 25-40% | 30-45% |
| Body Shop | 35-50% | 20-30% | 30-42% |

### Key Metrics

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| **Labor Rate Recovery** | <80% | 80-95% | 95-110% | >110% |
| **Hours/RO (Repair Order)** | <1.5 | 1.5-2.2 | 2.2-3.0 | >3.0 |
| **Parts/Labor Ratio** | <0.6 | 0.6-0.9 | 0.9-1.2 | >1.2 |
| **Bay Productivity** | <70% | 70-85% | 85-95% | >95% |
| **Customer Pay %** | <50% | 50-65% | 65-80% | >80% |

## 2.5 Rental & Leasing

### Rental Fleet Metrics

| Metric | Small Fleet | Mid Fleet | Large Fleet |
|--------|-------------|-----------|-------------|
| **Fleet Size** | 50-200 | 200-1,000 | 1,000-5,000+ |
| **Utilization** | 60-70% | 68-78% | 75-85% |
| **Revenue/Vehicle/Month** | $800-1,500 | $1,000-2,000 | $1,200-2,500 |
| **Cost/Vehicle/Month** | $600-1,200 | $700-1,400 | $750-1,500 |
| **EBITDA Margin** | 15-25% | 20-30% | 25-35% |

### Leasing Metrics

| Metric | Operating Lease | Finance Lease |
|--------|-----------------|---------------|
| Contract Term | 2-4 years | 3-5 years |
| Residual Value Risk | Lessor | Lessee |
| Margin | 8-15% | 3-8% spread |
| Capital Intensity | High | Medium |

## 2.6 Capital Requirements

### Startup Investment by Subsector

| Subsector | Minimum | Typical | Includes |
|-----------|---------|---------|----------|
| Parts Manufacturing | $500K-2M | $2-10M | Equipment, facility, inventory |
| New Car Dealership | $2-10M | $5-30M | Franchise, facility, inventory |
| Used Car Dealership | $200K-1M | $500K-3M | Lot, inventory, facility |
| Parts Distribution | $300K-1M | $1-5M | Inventory, warehouse |
| Independent Workshop | $50K-200K | $150K-500K | Equipment, facility |
| Tire Center | $100K-400K | $250K-800K | Equipment, inventory |
| Rental Company | $500K-2M | $2-10M | Fleet, systems |

### Working Capital Requirements

| Subsector | Working Capital % Revenue |
|-----------|---------------------------|
| Parts Manufacturing | 25-40% |
| New Car Dealership | 15-30% (floor plan) |
| Used Car Dealership | 30-50% |
| Parts Distribution | 25-40% |
| Service Workshop | 10-20% |
| Rental Company | 10-20% (plus fleet) |

## 2.7 Valuation Multiples

| Subsector | Revenue Multiple | EBITDA Multiple | Key Drivers |
|-----------|------------------|-----------------|-------------|
| Parts Manufacturing | 0.5-1.2x | 4-8x | Customer base, technology |
| New Car Dealership | 0.3-0.8x | 4-8x | Brand, location, profitability |
| Used Car Dealership | 0.3-0.6x | 3-6x | Inventory turn, location |
| Parts Distribution | 0.4-1.0x | 4-8x | Territory, brands |
| Service Workshop | 0.5-1.2x | 3-7x | Customer base, reputation |
| Rental Company | 0.8-1.5x | 5-10x | Fleet size, utilization |

---

# Dimension 3: Operational KPIs

## 3.1 Parts Manufacturing KPIs

### Production Efficiency

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **OEE** | Overall Equipment Effectiveness | <65% | 65-75% | 75-85% | >85% |
| **Scrap Rate** | Defective/total | >5% | 3-5% | 1-3% | <1% |
| **First Pass Yield** | Right first time | <90% | 90-95% | 95-98% | >98% |
| **On-Time Delivery** | To customer request | <90% | 90-95% | 95-98% | >98% |
| **PPM (Defects)** | Parts per million defects | >1000 | 500-1000 | 100-500 | <100 |

### Quality & Compliance

| KPI | Target |
|-----|--------|
| Customer Returns | <0.5% |
| Warranty Claims | <1% |
| IATF 16949 Compliance | Required for OEM |
| Audit Findings | 0 major |

## 3.2 Dealership KPIs

### Sales Performance

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Units/Salesperson/Month** | Productivity | <8 | 8-12 | 12-18 | >18 |
| **Closing Ratio** | Sold/leads | <15% | 15-25% | 25-35% | >35% |
| **Gross/Unit (New)** | Profit per vehicle | <$500 | $500-1,500 | $1,500-3,000 | >$3,000 |
| **Gross/Unit (Used)** | Profit per vehicle | <$1,000 | $1,000-2,000 | $2,000-3,500 | >$3,500 |
| **F&I/Unit** | Finance products | <$300 | $300-600 | $600-1,000 | >$1,000 |

### Service Performance

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Service Absorption** | Fixed ops covers overhead | <60% | 60-80% | 80-100% | >100% |
| **Customer Pay Hours** | Labor sold/tech | <30/wk | 30-38/wk | 38-45/wk | >45/wk |
| **Tech Efficiency** | Hours flagged/available | <90% | 90-100% | 100-115% | >115% |
| **CSI Score** | Customer satisfaction | <85% | 85-90% | 90-95% | >95% |
| **Service Retention** | Return for service | <35% | 35-50% | 50-65% | >65% |

### Inventory Management

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Days Supply (New)** | Inventory days | >90 | 60-90 | 45-60 | <45 |
| **Days Supply (Used)** | Inventory days | >60 | 45-60 | 30-45 | <30 |
| **Aged Units (>90 days)** | % of inventory | >20% | 12-20% | 5-12% | <5% |
| **Parts Fill Rate** | First time fill | <85% | 85-92% | 92-97% | >97% |

## 3.3 Independent Workshop KPIs

### Productivity

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Jobs/Day/Bay** | Throughput | <2 | 2-3 | 3-4 | >4 |
| **Revenue/Bay/Month** | Productivity | <$5K | $5-8K | $8-12K | >$12K |
| **Revenue/Tech/Month** | Productivity | <$8K | $8-12K | $12-18K | >$18K |
| **Average Repair Order** | Ticket value | <$150 | $150-250 | $250-400 | >$400 |

### Customer Metrics

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Return Rate** | Comebacks | >8% | 5-8% | 2-5% | <2% |
| **Customer Retention** | Annual return | <40% | 40-55% | 55-70% | >70% |
| **Referral Rate** | From referrals | <20% | 20-35% | 35-50% | >50% |
| **Online Rating** | Google/social | <4.0 | 4.0-4.3 | 4.3-4.6 | >4.6 |

## 3.4 Rental & Fleet KPIs

### Fleet Operations

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Fleet Utilization** | Rented/available | <65% | 65-75% | 75-85% | >85% |
| **Revenue/Vehicle/Day** | Yield | <$30 | $30-50 | $50-80 | >$80 |
| **Turnaround Time** | Return to ready | >4 hrs | 2-4 hrs | 1-2 hrs | <1 hr |
| **Damage Rate** | Incidents/rental | >5% | 3-5% | 1-3% | <1% |
| **Fleet Age** | Average months | >36 | 24-36 | 18-24 | <18 |

### Business Performance

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Revenue/Employee** | Productivity | <$80K | $80-120K | $120-180K | >$180K |
| **Cost/Vehicle/Month** | Operating cost | >$1,500 | $1,000-1,500 | $700-1,000 | <$700 |
| **Customer Acquisition Cost** | CAC | >$100 | $50-100 | $25-50 | <$25 |
| **Repeat Rental Rate** | Loyalty | <30% | 30-45% | 45-60% | >60% |

---

# Dimension 4: Regulatory Landscape

## 4.1 Licensing Requirements

### Vehicle Dealership Licenses

| License Type | Issuing Authority | Requirements | Cost Range |
|--------------|-------------------|--------------|------------|
| Trade License | Municipal/Economic | Business registration | $500-5,000/year |
| Dealership License | Transport/Trade Authority | Facility, capital | $2,000-20,000 |
| Brand Authorization | OEM | Agreement, standards | Varies |
| Showroom Permit | Municipality | Facility approval | $1,000-10,000 |
| Used Car License | Transport Authority | Facility, insurance | $1,000-5,000 |

### Workshop Licenses

| License Type | Issuing Authority | Requirements | Cost Range |
|--------------|-------------------|--------------|------------|
| Workshop License | Municipality/Transport | Facility, equipment | $500-3,000/year |
| Environmental Permit | Environment Authority | Waste management | $500-2,000 |
| Civil Defense | Fire Department | Safety compliance | $200-1,000 |
| Technician Certifications | Various | Training, testing | $100-500/person |

### Rental Company Licenses

| License Type | Issuing Authority | Requirements | Cost Range |
|--------------|-------------------|--------------|------------|
| Rental License | Transport Authority | Fleet, insurance | $2,000-10,000 |
| Trade License | Economic/Municipal | Business registration | $500-5,000 |
| Branch Licenses | Per location | Each location | $500-2,000/branch |

## 4.2 Country-Specific Regulations

### Saudi Arabia

| Regulation | Authority | Impact |
|------------|-----------|--------|
| SASO Standards | Standards Authority | Vehicle/parts standards |
| Motor Vehicle Law | Traffic Department | Registration, inspection |
| Commercial Registration | MoC | Business licensing |
| Saudization | MoHR | Employment quotas |
| Warranty Regulations | Consumer Protection | Dealer obligations |
| EV Regulations | Developing | Infrastructure requirements |

### UAE

| Regulation | Authority | Impact |
|------------|-----------|--------|
| Federal Traffic Law | MoI | Vehicle standards |
| Emirates Authority | Emirate-specific | Local licensing |
| RTA (Dubai) | Roads & Transport | Dealer/workshop licensing |
| ESMA | Standards | Product standards |
| Economic Department | Trade licensing | Business permits |

### Egypt

| Regulation | Authority | Impact |
|------------|-----------|--------|
| Vehicle Import | Customs | Tariffs, duties |
| Assembly Incentives | Industrial Development | Local content requirements |
| Consumer Protection | Consumer Agency | Warranty, returns |
| Environmental | EEAA | Emissions, waste |
| Traffic Law | Traffic Department | Registration |

### Jordan

| Regulation | Authority | Impact |
|------------|-----------|--------|
| Vehicle Import | Customs | Duties (high) |
| Trade Licensing | MoIT | Business permits |
| Consumer Protection | Consumer Directorate | Warranty obligations |
| Environmental | Environment Ministry | Emissions standards |

### Morocco

| Regulation | Authority | Impact |
|------------|-----------|--------|
| Industrial Investment | AMDIE | Manufacturing incentives |
| Free Zones | TFZ Authority | Export manufacturing |
| Vehicle Standards | Various | EU-aligned standards |
| Consumer Protection | Consumer Authority | Dealer obligations |

## 4.3 Vehicle Standards & Compliance

### Technical Standards

| Standard Type | Requirements | Markets |
|---------------|--------------|---------|
| **GCC Standards (GSO)** | Gulf standardization | GCC countries |
| **SASO** | Saudi standards | Saudi Arabia |
| **Euro Standards** | Emissions (Euro 4-6) | Most MENA |
| **Safety Standards** | Crash, safety features | All markets |
| **EV Standards** | Developing | UAE, Saudi leading |

### Import Requirements

| Requirement | Typical Rules |
|-------------|---------------|
| Age Limit | 3-5 years for used |
| Mileage Limit | Varies by country |
| Left-Hand Drive | Required (all MENA) |
| Emissions | Euro 4 minimum typically |
| Documentation | Original papers required |

## 4.4 Consumer Protection

### Warranty Requirements

| Market | New Vehicle | Used Vehicle |
|--------|-------------|--------------|
| Saudi Arabia | 2 years minimum | Disclosure required |
| UAE | 2-3 years typical | Disclosure required |
| Egypt | Manufacturer's warranty | Limited regulation |
| Jordan | Manufacturer's warranty | Limited |

### Lemon Laws / Returns

| Aspect | Status |
|--------|--------|
| Right to Return | Limited in most markets |
| Defect Resolution | Repair first, then replace |
| Consumer Complaints | Through consumer protection |

## 4.5 Environmental Regulations

### Emissions Standards

| Market | Current Standard | Trend |
|--------|------------------|-------|
| Saudi Arabia | Euro 4+ | Moving to Euro 6 |
| UAE | Euro 4+ | Moving to Euro 6 |
| Egypt | Euro 2-4 | Gradual improvement |
| Morocco | Euro 5+ | EU-aligned |

### EV Regulations

| Market | EV Policy | Infrastructure |
|--------|-----------|----------------|
| Saudi Arabia | 30% by 2030 target | Developing |
| UAE | Strong support | Growing rapidly |
| Egypt | Beginning | Limited |
| Jordan | Incentives | Growing |

### Waste Management

| Requirement | Application |
|-------------|-------------|
| Used Oil Disposal | Licensed collectors |
| Battery Disposal | Regulated disposal |
| Tire Disposal | Recycling requirements |
| Scrap Vehicle | End-of-life procedures |

---

# Dimension 5: Competitive Dynamics

## 5.1 Market Structure

| Subsector | Concentration | Market Leaders | Fragmentation |
|-----------|---------------|----------------|---------------|
| New Car Dealers | High | Major distributors | Consolidated (franchise) |
| Used Car Dealers | Low | Fragmented | Highly fragmented |
| Parts Distribution | Medium | Major importers | Moderate |
| Parts Retail | Low | Many small shops | Highly fragmented |
| Authorized Service | High | Dealer networks | Consolidated |
| Independent Workshop | Very Low | No dominant | Extremely fragmented |
| Rental | Medium | International + local | Consolidating |

## 5.2 Porter's Five Forces

```
┌─────────────────────────────────────────────────────────────────────┐
│                  AUTOMOTIVE FIVE FORCES                              │
├─────────────────────────────────────────────────────────────────────┤
│                                                                      │
│                  NEW ENTRANTS: 2.5/5                                │
│                  (Capital barriers; franchise required for new)     │
│                        │                                            │
│                        ▼                                            │
│   SUPPLIER POWER ────────────► INDUSTRY ◄───── BUYER POWER         │
│       3.5/5                    RIVALRY           3/5               │
│   (OEMs powerful,               3.5/5         (Price comparison,    │
│    parts import                (Moderate,       digital enabling)   │
│    dependent)                   local intense)                      │
│                        │                                            │
│                        ▼                                            │
│                SUBSTITUTES: 3/5                                     │
│                (Public transport, ride-hail, shared mobility)       │
│                                                                      │
│   OVERALL ATTRACTIVENESS: MODERATE                                  │
│   Key: Service quality, customer relationships, digital presence   │
└─────────────────────────────────────────────────────────────────────┘
```

### Force Details

| Force | Rating | Key Factors |
|-------|--------|-------------|
| **New Entrants** | 2.5/5 | Franchise barriers, capital intensity |
| **Supplier Power** | 3.5/5 | OEM control, import dependency |
| **Buyer Power** | 3/5 | Price transparency improving |
| **Substitutes** | 3/5 | Growing alternatives to ownership |
| **Rivalry** | 3.5/5 | Moderate overall, intense locally |

## 5.3 Competitive Strategies

| Strategy | Description | Best For | Requirements |
|----------|-------------|----------|--------------|
| **Brand Exclusive** | Single brand focus | Authorized dealers | OEM relationship |
| **Multi-Brand** | Portfolio of brands | Large dealers | Capital, facilities |
| **Service Excellence** | Quality focus | Workshops, dealers | Training, equipment |
| **Price Leader** | Lowest price | Parts, used cars | Volume, efficiency |
| **Convenience** | Location, hours, speed | Quick service | Network, operations |
| **Specialist** | Niche focus | Specific brands/services | Deep expertise |
| **Digital-First** | Online/app focused | Used cars, parts | Technology |
| **Fleet Focus** | B2B customers | Rental, service | Account management |

## 5.4 Industry Trends

| Trend | Impact | Timeframe | SME Opportunity |
|-------|--------|-----------|-----------------|
| **EV Transition** | New skills, infrastructure | 5-15 years | EV service, charging |
| **Connected Cars** | Data, diagnostics | Ongoing | Telematics services |
| **Digital Retail** | Online sales, leads | Ongoing | E-commerce, digital |
| **Used Car Formalization** | Certified, transparent | Ongoing | Platform business |
| **Mobility Services** | Subscription, sharing | 3-7 years | New models |
| **Aftermarket Consolidation** | Network scale | Ongoing | Growth/exit |
| **Nationalization** | Local workforce | Ongoing | Training opportunity |
| **Fleet Management** | Outsourced operations | Ongoing | Service growth |

## 5.5 Major Player Landscape

### Vehicle Distributors by Country

| Country | Major Distributors | Characteristics |
|---------|-------------------|-----------------|
| **Saudi Arabia** | Abdul Latif Jameel (Toyota), Mohamed Yousuf Naghi (Mercedes, Hyundai), Al Jomaih (GM) | Family conglomerates |
| **UAE** | Al Futtaim (Toyota, Lexus), Al Naboodah (Audi), Al Tayer (Ford) | Diversified groups |
| **Egypt** | Ghabbour (Hyundai, Mazda), Abou Ghaly (Kia), Al Mansour (GM) | Large importers |
| **Jordan** | Mohammad Izzat Marji (Toyota), Al Majdouie | Regional distributors |
| **Morocco** | Auto Hall, Auto Nejma, Sopriam | Established dealers |

### Parts & Aftermarket

| Type | Major Players | MENA Presence |
|------|---------------|---------------|
| Parts Chains | NAPA, AutoZone | Limited direct |
| Regional Distributors | Al Futtaim Autoparts, Zayani | Strong |
| Workshop Chains | Bosch Car Service, Midas | Growing |
| Quick Lube | Jiffy Lube, Petromin | Saudi, UAE |

### Rental & Leasing

| Type | Major Players | MENA Presence |
|------|---------------|---------------|
| International | Hertz, Avis, Enterprise | UAE, Saudi |
| Regional | Al Tayer, United Cars | Strong |
| Local Champions | Various | Market specific |

## 5.6 Market-Specific Dynamics

| Country | Characteristics | SME Opportunity |
|---------|-----------------|-----------------|
| **Saudi Arabia** | Largest market, diversifying, EV focus | Service, fleet, EV |
| **UAE** | Premium focus, hub, competitive | Specialty, re-export |
| **Egypt** | Price sensitive, local assembly, large fleet | Aftermarket, value |
| **Jordan** | Import duties high, efficiency focus | Service, used |
| **Morocco** | Manufacturing hub, export oriented | Parts supply, export |

---

*End of Part 1 - Continue to Part 2 for Dimensions 6-11*
# Dimension 6: Digital Maturity

## 6.1 Technology Adoption Benchmarks

| Subsector | Current Adoption | Digital Leaders | Digital Laggards | Key Gap |
|-----------|------------------|-----------------|------------------|---------|
| New Car Dealers | Medium-High | 55% | 15% | Online sales, CRM |
| Used Car Dealers | Medium | 40% | 35% | Platforms, transparency |
| Parts Distribution | Medium | 45% | 30% | E-commerce, inventory |
| Independent Workshop | Low-Medium | 20% | 55% | Management systems |
| Rental Companies | Medium-High | 50% | 20% | Apps, fleet tech |
| Parts Manufacturing | Medium | 40% | 35% | Industry 4.0 |

## 6.2 Digital Maturity Levels

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                   AUTOMOTIVE DIGITAL MATURITY                                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  LEVEL 1: TRADITIONAL (Score 0-20)                                          │
│  • Paper-based, walk-in only, basic POS                                     │
│  • Typical: Small workshops, traditional used car lots                      │
│                                                                              │
│  LEVEL 2: BASIC DIGITAL (Score 21-40)                                       │
│  • Website, basic inventory system, social media                            │
│  • Typical: Standard dealers, parts retailers                               │
│                                                                              │
│  LEVEL 3: DIGITAL-ENABLED (Score 41-60)                                     │
│  • DMS integrated, online booking, digital marketing                        │
│  • Typical: Progressive dealers, chain workshops                            │
│                                                                              │
│  LEVEL 4: DIGITAL-FIRST (Score 61-80)                                       │
│  • Online sales, mobile apps, data analytics, telematics                    │
│  • Typical: Leading dealers, tech-forward rentals                           │
│                                                                              │
│  LEVEL 5: DIGITAL-NATIVE (Score 81-100)                                     │
│  • AI diagnostics, predictive, connected car, omnichannel                   │
│  • Typical: Digital disruptors, tech platforms                              │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 6.3 Core Technology Systems

### Dealership Technology

| System | Priority | Investment Range | Adoption | Payback |
|--------|----------|------------------|----------|---------|
| DMS (Dealer Management) | Critical | $20K-200K | 70% | 12-24 mo |
| CRM | High | $10K-50K | 55% | 6-12 mo |
| Website/Digital | High | $5K-50K | 80% | 6-12 mo |
| Inventory Management | High | $10K-50K | 60% | 6-12 mo |
| Service Scheduling | High | $5K-30K | 45% | 6-12 mo |
| F&I Software | Medium | $5K-25K | 40% | 12-18 mo |

### Workshop Technology

| System | Priority | Investment Range | Adoption | Payback |
|--------|----------|------------------|----------|---------|
| Workshop Management | High | $2K-20K | 35% | 6-12 mo |
| Diagnostic Equipment | Critical | $5K-50K | 70% | 6-18 mo |
| Parts Lookup | High | $1K-10K | 50% | 3-6 mo |
| Customer Database | High | $500-5K | 40% | 3-6 mo |
| Appointment Booking | Medium | $1K-5K | 25% | 3-6 mo |
| Digital Inspection | Medium | $2K-15K | 20% | 6-12 mo |

### Rental Technology

| System | Priority | Investment Range | Adoption | Payback |
|--------|----------|------------------|----------|---------|
| Fleet Management | Critical | $20K-100K | 65% | 12-24 mo |
| Reservation System | Critical | $10K-50K | 75% | 6-12 mo |
| Mobile App | High | $20K-100K | 45% | 12-18 mo |
| Telematics/GPS | High | $10K-50K | 55% | 12-24 mo |
| Damage Documentation | Medium | $5K-20K | 40% | 6-12 mo |

## 6.4 High-Impact Digital Interventions

| Subsector | Priority 1 | Priority 2 | Priority 3 | Impact |
|-----------|------------|------------|------------|--------|
| Dealership | DMS integration | Online lead management | Digital retailing | 20-35% efficiency |
| Workshop | Management software | Digital inspection | Online booking | 25-40% productivity |
| Parts Retail | E-commerce | Inventory optimization | Customer app | 30-50% reach |
| Rental | Mobile booking | Telematics | Self-service | 25-40% efficiency |

## 6.5 Emerging Technologies

### Connected Car & Telematics

| Application | Use Case | Impact |
|-------------|----------|--------|
| Predictive Maintenance | Alert before failure | Service opportunity |
| Usage-Based Insurance | Risk pricing | New products |
| Fleet Tracking | Location, utilization | Operational efficiency |
| Diagnostics | Remote troubleshooting | Service efficiency |
| Driver Behavior | Safety, efficiency | Fleet management |

### EV-Specific Technology

| Technology | Application | Timeline |
|------------|-------------|----------|
| Charging Infrastructure | Network management | Now |
| Battery Diagnostics | Health monitoring | Growing |
| EV Service Equipment | High-voltage systems | Required |
| Range Optimization | Route planning | Growing |

### AI/ML Applications

| Application | Use Case | Maturity |
|-------------|----------|----------|
| Pricing Optimization | Used car valuation | Growing |
| Demand Forecasting | Inventory planning | Growing |
| Chatbots | Customer service | Established |
| Visual Inspection | Damage assessment | Emerging |
| Parts Prediction | Failure forecasting | Emerging |

---

# Dimension 7: Workforce Norms

## 7.1 Organizational Structures

### Dealership (50-150 employees)
```
              General Manager
                    │
       ┌────────────┼────────────┬────────────┬────────────┐
       │            │            │            │            │
   Sales        Service       Parts       Finance      Admin/HR
   Manager      Manager      Manager     Manager
       │            │            │            │            │
   Sales Team   Advisors    Counter     F&I        Accounting
   BDC          Technicians  Warehouse   Title       HR
   Used Car Mgr Cashier     Delivery    Insurance   IT/Facilities
```

### Independent Workshop (10-30 employees)
```
              Owner/Manager
                    │
       ┌────────────┼────────────┐
       │            │            │
   Shop         Service       Admin
   Foreman      Advisors
       │            │            │
   Technicians  Reception    Accounting
   Helpers                   Parts Clerk
```

### Rental Company (30-80 employees)
```
              General Manager
                    │
       ┌────────────┼────────────┬────────────┐
       │            │            │            │
   Operations   Sales/Mkt    Fleet Mgmt   Finance/Admin
       │            │            │            │
   Station Mgrs  Corporate    Maintenance  Accounting
   Agents       Retail       Acquisition   HR
   Drivers      Digital      Disposal      IT
```

## 7.2 Key Roles

### Dealership Roles

| Role | Responsibilities | Experience | Qualifications |
|------|------------------|------------|----------------|
| General Manager | P&L, strategy, OEM relations | 10-15+ years | Business, automotive |
| Sales Manager | Sales team, targets, inventory | 5-10 years | Sales track record |
| Service Manager | Workshop operations, CSI | 5-10 years | Technical + management |
| Parts Manager | Inventory, ordering, sales | 5-8 years | Parts experience |
| F&I Manager | Financing, insurance products | 3-7 years | Finance, sales |
| Sales Consultant | Customer sales | 1-5 years | Sales aptitude |
| Service Advisor | Customer interface | 2-5 years | Technical knowledge |
| Technician | Vehicle repair | 2-10 years | Technical training |

### Workshop Roles

| Role | Responsibilities | Experience | Qualifications |
|------|------------------|------------|----------------|
| Workshop Owner/Manager | Overall operations | 10+ years | Technical + business |
| Shop Foreman | Technical supervision | 5-10 years | Senior technician |
| Master Technician | Complex repairs | 8+ years | Advanced certifications |
| General Technician | Routine repairs | 2-5 years | Vocational training |
| Apprentice | Learning, assistance | 0-2 years | Training program |
| Service Writer | Customer, estimating | 2-5 years | Customer service |

### Rental Roles

| Role | Responsibilities | Experience | Qualifications |
|------|------------------|------------|----------------|
| General Manager | Operations, P&L | 8-12+ years | Business, operations |
| Operations Manager | Day-to-day operations | 5-8 years | Operations |
| Fleet Manager | Vehicle lifecycle | 5-8 years | Fleet experience |
| Station Manager | Location operations | 3-5 years | Service, operations |
| Rental Agent | Customer service | 1-3 years | Customer service |

## 7.3 Compensation Benchmarks (USD/month)

### Egypt

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Dealership GM | $1,500-2,500 | $2,500-5,000 | $5,000-10,000 |
| Sales Manager | $800-1,200 | $1,200-2,500 | $2,500-5,000 |
| Service Manager | $700-1,200 | $1,200-2,200 | $2,200-4,000 |
| Sales Consultant | $300-500 + comm | $500-800 + comm | $800-1,500 + comm |
| Technician | $250-400 | $400-700 | $700-1,200 |
| Rental Agent | $250-400 | $400-600 | $600-900 |

### Saudi Arabia

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Dealership GM | $6,000-10,000 | $10,000-18,000 | $18,000-35,000 |
| Sales Manager | $4,000-6,500 | $6,500-12,000 | $12,000-20,000 |
| Service Manager | $3,500-6,000 | $6,000-10,000 | $10,000-18,000 |
| Sales Consultant | $1,500-2,500 + comm | $2,500-4,500 + comm | $4,500-8,000 + comm |
| Technician | $1,200-2,000 | $2,000-3,500 | $3,500-6,000 |
| Rental Agent | $1,500-2,500 | $2,500-4,000 | $4,000-6,000 |

### UAE

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Dealership GM | $8,000-12,000 | $12,000-22,000 | $22,000-45,000 |
| Sales Manager | $5,000-8,000 | $8,000-15,000 | $15,000-25,000 |
| Service Manager | $4,500-7,000 | $7,000-12,000 | $12,000-22,000 |
| Sales Consultant | $2,000-3,500 + comm | $3,500-6,000 + comm | $6,000-10,000 + comm |
| Technician | $1,500-2,500 | $2,500-4,500 | $4,500-8,000 |
| Rental Agent | $2,000-3,000 | $3,000-5,000 | $5,000-8,000 |

### Jordan

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Dealership GM | $2,000-3,500 | $3,500-6,000 | $6,000-12,000 |
| Sales Manager | $1,200-2,000 | $2,000-3,500 | $3,500-6,000 |
| Service Manager | $1,000-1,800 | $1,800-3,000 | $3,000-5,500 |
| Sales Consultant | $500-800 + comm | $800-1,300 + comm | $1,300-2,200 + comm |
| Technician | $400-700 | $700-1,200 | $1,200-2,000 |
| Rental Agent | $450-700 | $700-1,100 | $1,100-1,800 |

## 7.4 Skills Gap Analysis

| Skill Area | Availability | Demand | Gap Severity |
|------------|--------------|--------|--------------|
| EV Technicians | Very Low | Growing High | **Critical** |
| Diagnostic Specialists | Low | High | **High** |
| Digital/Data Skills | Low | High | **High** |
| Sales Professionals | Medium | High | **Medium-High** |
| Service Advisors | Low-Medium | High | **High** |
| Parts Specialists | Medium | Medium | **Medium** |
| Fleet Management | Low | High | **High** |
| Connected Car | Very Low | Growing | **Critical** |

## 7.5 Training & Certification

### Technical Certifications

| Certification | Provider | Focus |
|---------------|----------|-------|
| ASE (US Standard) | ASE | Various specialties |
| IMI (UK Standard) | IMI | Technical levels |
| OEM Certifications | Manufacturers | Brand-specific |
| EV Certifications | Various | High-voltage systems |
| AC/Refrigerant | EPA/local | Environmental |

### Sales & Service

| Training | Focus | Provider |
|----------|-------|----------|
| OEM Sales Training | Brand knowledge, process | Manufacturers |
| F&I Certification | Finance, compliance | Industry bodies |
| Service Advisor | Customer handling | OEMs, associations |
| Management | Leadership, operations | Business schools |

## 7.6 HR KPIs

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| Sales Staff Turnover | >40% | 30-40% | 20-30% | <20% |
| Technician Turnover | >30% | 20-30% | 12-20% | <12% |
| Training Hours/Year | <20 | 20-40 | 40-60 | >60 |
| Productivity (Sales) | <8 units/mo | 8-12 | 12-18 | >18 |
| Technician Efficiency | <90% | 90-100% | 100-115% | >115% |

---

# Dimension 8: Supply Chain

## 8.1 Input Categories

### Parts Manufacturing Inputs

| Category | % of Cost | Import Dependency | Key Sources |
|----------|-----------|-------------------|-------------|
| Raw Materials (Steel, Aluminum) | 30-45% | Medium-High | China, Turkey, Local |
| Plastics/Polymers | 10-20% | High | Global suppliers |
| Rubber | 5-15% | Medium-High | Malaysia, Thailand |
| Electronics/Components | 10-25% | Very High | China, Asia |
| Packaging | 3-8% | Low-Medium | Local |

### Dealership/Retail Inputs

| Category | % of Cost | Import Dependency | Key Sources |
|----------|-----------|-------------------|-------------|
| Vehicles | 70-85% | Very High | OEM sources |
| Parts Inventory | 10-20% | Very High | OEM, aftermarket |
| Marketing | 2-5% | Low | Local agencies |
| Facilities | 3-8% | Low | Local |
| Technology | 2-5% | High | Software vendors |

### Service/Workshop Inputs

| Category | % of Cost | Import Dependency | Key Sources |
|----------|-----------|-------------------|-------------|
| Parts | 40-60% | High | Distributors |
| Labor | 25-40% | Low | Local market |
| Equipment/Tools | 5-10% | High | Equipment suppliers |
| Consumables | 5-10% | Medium | Various |
| Facilities | 5-10% | Low | Local |

## 8.2 Key Supplier Relationships

### Vehicle Supply Chain

| Supplier Type | Relationship | Terms |
|---------------|--------------|-------|
| OEM/Importer | Franchise agreement | Floor plan, allocation |
| Captive Finance | Partnership | Retail/wholesale |
| Insurance | Preferred | Commission arrangements |
| Accessory Vendors | Supply agreement | Net 30-60 |

### Parts Supply Chain

| Supplier Type | Relationship | Terms |
|---------------|--------------|-------|
| OEM Parts | Franchise/agreement | Net 30-45 |
| Aftermarket Distributors | Account | Net 30-60 |
| Local Manufacturers | Direct | Net 30-45 |
| Import Agents | Trading | Various |

### Workshop Supply Chain

| Supplier Type | Relationship | Terms |
|---------------|--------------|-------|
| Parts Distributors | Account | Net 30 |
| Paint/Body Suppliers | Account | Net 30 |
| Equipment/Tool Suppliers | Purchase/lease | Various |
| Consumable Suppliers | Regular order | Net 30 |

## 8.3 Floor Plan Financing

### New Vehicle Floor Plan

| Aspect | Typical Terms |
|--------|---------------|
| Interest Rate | 4-8% above base |
| Term | Until sold or curtailed |
| Curtailment | 90-120 days typically |
| Audit | Regular inventory checks |
| Security | Vehicle title held |

### Used Vehicle Floor Plan

| Aspect | Typical Terms |
|--------|---------------|
| Interest Rate | 6-12% above base |
| Advance Rate | 70-90% of cost |
| Term | 60-90 days |
| Audit | Regular |

## 8.4 Parts Sourcing Strategy

| Source | Advantage | Disadvantage |
|--------|-----------|--------------|
| OEM Parts | Quality, warranty | Higher cost |
| OEM-equivalent | Quality, lower cost | Availability |
| Aftermarket | Lower cost, availability | Variable quality |
| Remanufactured | Cost, sustainability | Limited range |
| Local Manufacture | Cost, availability | Limited range |

---

# Dimension 9: Export Requirements

## 9.1 Export Opportunities

### Parts Manufacturing Export

| Market | Opportunity | Requirements |
|--------|-------------|--------------|
| Regional (MENA) | Medium-High | Quality certifications |
| Europe | High (Morocco) | EU standards, proximity |
| Africa | Growing | Price competitiveness |
| GCC from Egypt | Medium | Quality, logistics |

### Vehicle Re-Export

| Hub | Primary Activity | Destinations |
|----|------------------|--------------|
| UAE | Premium re-export | Africa, CIS |
| Jordan | Used vehicles | Iraq, regional |
| Morocco | Manufacturing | Europe, Africa |

## 9.2 Quality Standards for Export

### Automotive Industry Standards

| Standard | Application | Requirement |
|----------|-------------|-------------|
| IATF 16949 | OEM suppliers | Quality management |
| ISO 9001 | General quality | Foundation |
| ISO 14001 | Environmental | Many OEMs require |
| REACH | EU chemicals | EU market access |
| Various OEM | Brand-specific | Supplier qualification |

### Country-Specific Standards

| Market | Key Standards |
|--------|---------------|
| EU | CE marking, EU type approval |
| GCC | GSO conformity, SASO |
| USA | FMVSS, EPA (if applicable) |

## 9.3 Morocco Automotive Hub

### Free Zone Benefits

| Benefit | Details |
|---------|---------|
| Tax Holiday | 5 years, reduced thereafter |
| Duty Free | Imports for export |
| Simplified Customs | Streamlined procedures |
| Infrastructure | Industrial zones |

### Major Manufacturing

| Company | Activity | Export |
|---------|----------|--------|
| Renault | Assembly | Europe, Africa |
| PSA (Stellantis) | Assembly | Europe, Africa |
| Various Tier 1 | Parts supply | Global OEMs |

---

# Dimension 10: Packaging & Labeling

## 10.1 Service Packaging

### Workshop Service Menus

| Package | Components | Target |
|---------|------------|--------|
| Basic Service | Oil, filter, inspection | Value customers |
| Full Service | Comprehensive check | Standard |
| Premium Service | Full + extras | Premium customers |
| Seasonal Package | AC, winter prep | Seasonal needs |
| Mileage-Based | Per manufacturer | Warranty compliance |

### Fleet Service Packages

| Package | Components | Pricing |
|---------|------------|---------|
| Full Maintenance | All scheduled + repairs | Per km/month |
| Scheduled Only | Per manufacturer | Per service |
| Tire Program | Supply + fitting + rotation | Per km |
| Fleet Check | Inspection service | Per vehicle |

## 10.2 Dealer Product Presentation

### Showroom Standards

| Element | Requirement |
|---------|-------------|
| Vehicle Display | OEM standards, lighting |
| Signage | Brand compliant |
| Information | Pricing, specifications |
| Digital Displays | Interactive, current |
| Sales Materials | Brochures, configurators |

### Used Vehicle Presentation

| Element | Best Practice |
|---------|---------------|
| Condition Report | Detailed, transparent |
| History Report | Service, ownership |
| Pricing | Market-based, justified |
| Warranty | Clearly stated |
| Photos | High quality, comprehensive |

## 10.3 Parts Presentation

### Packaging Requirements

| Requirement | Purpose |
|-------------|---------|
| OEM Part Number | Identification |
| Fitment Information | Application guide |
| Quality Marks | Authentication |
| Barcode/QR | Inventory, verification |
| Safety Warnings | Compliance |

### Counterfeit Prevention

| Measure | Application |
|---------|-------------|
| Hologram Labels | Authentication |
| QR Verification | Online checking |
| Secure Packaging | Tamper-evident |
| Chain of Custody | Documentation |

## 10.4 Marketing & Communications

### Digital Presence

| Channel | Purpose | Priority |
|---------|---------|----------|
| Website | Inventory, information | Critical |
| Google My Business | Local search | Critical |
| Social Media | Engagement, awareness | High |
| Listing Portals | Exposure | High |
| WhatsApp Business | Communication | High (MENA) |

### Traditional Marketing

| Channel | Purpose | Usage |
|---------|---------|-------|
| Outdoor | Brand awareness | Declining |
| Print | Limited | Declining |
| Radio | Local reach | Moderate |
| Events | Launches, promotions | Periodic |

---

# Dimension 11: MENA Regional Context

## 11.1 Country Profiles

### Saudi Arabia

| Attribute | Details |
|-----------|---------|
| **Market Size** | $25-35 billion |
| **Annual Sales** | ~500,000 new vehicles |
| **Key Segments** | SUV, sedan, pickup |
| **Characteristics** | Largest market, diversifying, women drivers |
| **EV Policy** | 30% by 2030 target |
| **Opportunities** | Aftermarket, EV, fleet, women segment |
| **Challenges** | Competition, Saudization |

### UAE

| Attribute | Details |
|-----------|---------|
| **Market Size** | $20-30 billion |
| **Annual Sales** | ~200,000 new vehicles |
| **Key Segments** | Premium, luxury, SUV |
| **Characteristics** | Hub, re-export, premium focus |
| **EV Policy** | Strong support, infrastructure |
| **Opportunities** | Premium service, re-export, EV |
| **Challenges** | Competition, mature market |

### Egypt

| Attribute | Details |
|-----------|---------|
| **Market Size** | $8-12 billion |
| **Annual Sales** | ~150-200,000 new vehicles |
| **Key Segments** | Economy, sedan |
| **Characteristics** | Local assembly, price sensitive |
| **Manufacturing** | Assembly plants (GM, Nissan, others) |
| **Opportunities** | Aftermarket, parts manufacturing |
| **Challenges** | Currency, import costs |

### Jordan

| Attribute | Details |
|-----------|---------|
| **Market Size** | $2-4 billion |
| **Annual Sales** | ~30-50,000 new vehicles |
| **Key Segments** | Economy, hybrid popular |
| **Characteristics** | High duties, hybrid adoption |
| **Opportunities** | Service, used cars, hybrid |
| **Challenges** | Small market, duties |

### Morocco

| Attribute | Details |
|-----------|---------|
| **Market Size** | $8-12 billion |
| **Annual Sales** | ~150-200,000 new vehicles |
| **Key Segments** | Economy, European brands |
| **Characteristics** | Manufacturing hub, export focus |
| **Manufacturing** | Renault, PSA, major tier suppliers |
| **Opportunities** | Parts manufacturing, export |
| **Challenges** | Domestic demand, competition |

## 11.2 Vision 2030 Impact (Saudi)

### Automotive Sector Goals

| Goal | Target | Opportunity |
|------|--------|-------------|
| Local Manufacturing | New assembly plants | Parts supply |
| EV Adoption | 30% by 2030 | EV infrastructure, service |
| Women Driving | Full participation | New customer segment |
| Localization | Parts sourcing | Manufacturing |
| Tourism | Vehicle demand | Rental growth |

### Mega-Project Impact

| Project | Vehicle Demand |
|---------|---------------|
| NEOM | Fleet, rental, service |
| Red Sea | Tourism vehicles |
| Qiddiya | Entertainment transport |
| Riyadh Metro | Reduced private, fleet |

## 11.3 EV Transition

### Current State by Country

| Country | EV % of Sales | Infrastructure | Policy |
|---------|---------------|----------------|--------|
| UAE | 2-4% | Growing | Supportive |
| Saudi Arabia | <1% | Developing | Ambitious |
| Egypt | <0.5% | Minimal | Beginning |
| Jordan | 3-5% (hybrid) | Limited | Incentives |

### EV Opportunity Areas

| Opportunity | Timeframe | Requirements |
|-------------|-----------|--------------|
| Charging Infrastructure | Now | Investment, location |
| EV Service Training | Now | Technical skills |
| Battery Service | 2-5 years | Specialized equipment |
| Used EV Market | 3-5 years | Valuation expertise |

## 11.4 Business Culture Considerations

| Aspect | Consideration |
|--------|---------------|
| Relationships | Important for B2B, fleet |
| Brand Loyalty | Strong in Gulf markets |
| Negotiation | Expected on vehicle purchase |
| After-Sales | Critical for retention |
| Digital Adoption | Growing rapidly |
| Women Customers | Growing segment (Saudi) |
| Family Decisions | Often group purchase |
| Ramadan Impact | Reduced traffic, promotions |

## 11.5 Strategic Opportunities

| Opportunity | Markets | Potential | Requirements |
|-------------|---------|-----------|--------------|
| EV Services | UAE, Saudi | **Very High** | Training, equipment |
| Fleet Management | All | **High** | Technology, scale |
| Used Car Platforms | All | **High** | Digital, trust |
| Parts E-commerce | All | **High** | Inventory, logistics |
| Women Segment | Saudi | **High** | Marketing, service |
| Workshop Chains | Egypt, Saudi | **High** | Standards, brand |
| Rental/Mobility | Saudi, UAE | **High** | Fleet, technology |
| Parts Manufacturing | Egypt, Morocco | **Medium-High** | OEM relationships |

---

# Document Summary

## Sector Overview

**Automotive** in MENA represents:

**Market Size & Growth:**
- ~$80-120 billion total market
- ~1 million+ new vehicles annually
- Large aging fleet = aftermarket opportunity
- Growing used car formalization
- EV transition beginning

**Key Characteristics:**
- Limited local manufacturing (Egypt, Morocco)
- High import dependency
- Franchise-controlled new car market
- Fragmented aftermarket
- Growing digital disruption
- EV transition opportunity

**SME Landscape:**
- Franchise barriers for new cars
- Open market for used, parts, service
- Consolidation opportunity in aftermarket
- Technology enabling disruption
- Skills gap in EV, digital

**Priority Subsectors:**
1. **Independent Workshops** - Large, fragmented, professionalizing
2. **Parts Distribution** - E-commerce transformation
3. **Used Car Sales** - Formalization, platforms
4. **Fleet Management** - Growing outsourcing
5. **EV Services** - Future growth

## Critical Insights for SME Diagnostics

### Key Success Factors

1. **Customer Service Excellence** - Retention driver
2. **Technical Competence** - Quality repairs
3. **Inventory Management** - Parts availability
4. **Digital Presence** - Customer acquisition
5. **Operational Efficiency** - Profitability
6. **Location** - Traffic, visibility

### Red Flags to Assess

- High comeback/warranty rates (>5%)
- Poor inventory turn (<4x)
- Low service absorption (<60%)
- No digital presence
- High staff turnover (>40%)
- Equipment not maintained/updated
- Compliance gaps

### Upside Indicators

- Strong CSI/customer ratings (>4.5)
- Good service absorption (>80%)
- Digital booking/presence
- EV capability development
- Fleet customer relationships
- Quality certifications

## Agent Usage Guide

| Agent | Primary Dimensions | Key Data Points |
|-------|-------------------|-----------------|
| **The Drucker** | 1, 11 | Subsector classification, market context |
| **The Marvin** | 3, 4 | Workshop KPIs, compliance |
| **The Graham** | 2 | Dealer economics, margins |
| **The Ricardo** | 9 | Export (parts manufacturing) |
| **The Lovelace** | 6 | DMS, digital adoption |
| **The Mayo** | 7 | Technician skills, compensation |
| **The Ohno** | 8 | Parts sourcing, inventory |
| **The Porter** | 5 | Competitive dynamics |
| **The Landor** | 10 | Service packaging, marketing |

## Cross-Sector Integration

| Connected Sector | Automotive Integration |
|------------------|----------------------|
| **Logistics** | Fleet customers, commercial vehicles |
| **Financial Services** | Vehicle financing, insurance |
| **Metal Fabrication** | Parts manufacturing |
| **Plastics/Rubber** | Parts manufacturing |
| **Retail** | Distribution channels |
| **Real Estate** | Showroom, workshop facilities |
| **Hospitality** | Rental for tourists |

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | December 2025 | RootRise Product Team | Initial release |

---

*This document is part of the RootRise Sector Knowledge Pack series, providing comprehensive sector intelligence for The Pantheon multi-agent diagnostic system.*
