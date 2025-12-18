# RootRise Sector Knowledge Pack
# Hospitality & Tourism
## Version 1.0 | December 2025

---

# Document Information

| Attribute | Value |
|-----------|-------|
| **Sector ID** | `hospitality_tourism` |
| **Version** | 1.0 |
| **Last Updated** | December 2025 |
| **Status** | Active |
| **ISIC Rev.4 Divisions** | 55 (Accommodation), 56 (Food & Beverage Service), 79 (Travel & Tourism), 93 (Recreation) |
| **Primary Markets** | Egypt, Saudi Arabia, UAE, Jordan, Morocco |
| **SME Employee Range** | 5-300 |
| **SME Revenue Range** | $100K - $30M |

## Sector Overview

Hospitality & Tourism is undergoing **unprecedented transformation** in MENA, driven by Vision 2030 mega-projects in Saudi Arabia, continued growth in UAE, Egypt's heritage tourism, and Morocco's diverse offerings. The sector represents a major economic diversification pillar across the region.

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                    HOSPITALITY & TOURISM VALUE CHAIN                             │
├─────────────────────────────────────────────────────────────────────────────────┤
│                                                                                  │
│   UPSTREAM                    CORE OPERATIONS                   DOWNSTREAM      │
│   ─────────                   ───────────────                   ──────────      │
│                                                                                  │
│   ┌──────────────┐           ┌──────────────────────┐         ┌─────────────┐  │
│   │ SUPPLIERS    │           │  ACCOMMODATION       │         │ CUSTOMERS   │  │
│   │ • Food/Bev   │──────────►│  • Hotels            │────────►│ • Leisure   │  │
│   │ • Linens     │           │  • Serviced Apts     │         │ • Business  │  │
│   │ • Equipment  │           │  • Resorts           │         │ • MICE      │  │
│   │ • Technology │           │  • Budget/Hostels    │         │ • Religious │  │
│   └──────────────┘           └──────────┬───────────┘         └─────────────┘  │
│                                         │                                       │
│                              ┌──────────▼───────────┐                          │
│   ENABLERS                   │  F&B SERVICE         │         CHANNELS         │
│   ────────                   │  • Restaurants       │         ─────────        │
│   • Airlines                 │  • Cafes             │         • Direct         │
│   • DMCs                     │  • Catering          │         • OTAs           │
│   • Tour Operators           │  • Cloud Kitchens    │         • Travel Agents  │
│   • Travel Tech              │  • QSR               │         • Corporate      │
│                              └──────────────────────┘         • Aggregators    │
│                                                                                  │
│   KEY MENA CHARACTERISTICS:                                                     │
│   • Vision 2030 mega-projects (NEOM, Red Sea, Qiddiya, AlUla)                  │
│   • Religious tourism (Hajj, Umrah, Holy Sites)                                │
│   • Heritage & cultural tourism (Egypt, Jordan, Morocco)                       │
│   • Business/MICE hub (UAE, Saudi)                                             │
│   • Desert/adventure tourism growth                                            │
│   • Seasonality challenges (extreme summer heat)                               │
│   • Digital transformation accelerating                                         │
│                                                                                  │
└─────────────────────────────────────────────────────────────────────────────────┘
```

## Applicable Countries

| Country Code | Country Name | Tourism Arrivals (2024) | Sector GDP Contribution |
|--------------|--------------|------------------------|------------------------|
| EG | Egypt | 14-15 million | 12-15% |
| SA | Saudi Arabia | 27-30 million (inc. religious) | 5-8% (growing) |
| AE | UAE | 18-20 million | 12-14% |
| JO | Jordan | 5-6 million | 10-12% |
| MA | Morocco | 14-15 million | 7-9% |

---

# Dimension 1: Industry Classification

## 1.1 ISIC Rev.4 Classification

### Primary ISIC Codes

| Division | Description | SME Relevance |
|----------|-------------|---------------|
| **55** | Accommodation | **Very High** |
| **56** | Food and beverage service activities | **Very High** |
| **79** | Travel agency, tour operator, reservation | **Very High** |
| **93** | Sports activities and amusement/recreation | **High** |

### Detailed Class Breakdown

**Division 55 - Accommodation:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| **5510** | **Short-term accommodation** | **Very High** |
| 5520 | Camping grounds, RV parks | Medium |
| **5590** | **Other accommodation** | **High** |

**Division 56 - Food & Beverage Service:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| **5610** | **Restaurants and mobile food service** | **Very High** |
| **5621** | **Event catering** | **Very High** |
| 5629 | Other food service activities | High |
| **5630** | **Beverage serving activities** | **Very High** |

**Division 79 - Travel & Tourism Services:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| **7911** | **Travel agency activities** | **Very High** |
| **7912** | **Tour operator activities** | **Very High** |
| **7990** | **Other reservation and related activities** | **High** |

**Division 93 - Recreation:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| **9311** | **Sports facility operation** | **High** |
| 9312 | Sports clubs | Medium |
| **9321** | **Amusement parks, theme parks** | **Medium** |
| **9329** | **Other recreation activities** | **Very High** |

## 1.2 Subsector Taxonomy

```json
{
  "subsectors": [
    {
      "subsector_id": "hotels_resorts",
      "subsector_name": "Hotels & Resorts",
      "subsector_name_ar": "الفنادق والمنتجعات",
      "description": "Full-service hotels, resorts, and boutique properties",
      "isic_codes": ["5510"],
      "typical_sme_size": "20-300 employees",
      "typical_sme_revenue": "$500K-$30M",
      "mena_market_size_estimate": "$35-45 billion",
      "growth_rate_5yr": "8-15%",
      "key_segments": ["Luxury", "Upscale", "Midscale", "Economy"]
    },
    {
      "subsector_id": "serviced_apartments",
      "subsector_name": "Serviced Apartments & Extended Stay",
      "subsector_name_ar": "الشقق الفندقية",
      "description": "Furnished apartments with hotel-like services for extended stays",
      "isic_codes": ["5510", "5590"],
      "typical_sme_size": "10-80 employees",
      "typical_sme_revenue": "$300K-$15M",
      "mena_market_size_estimate": "$5-8 billion",
      "growth_rate_5yr": "10-18%",
      "key_segments": ["Corporate", "Family", "Long-stay leisure"]
    },
    {
      "subsector_id": "restaurants_dining",
      "subsector_name": "Restaurants & Dining",
      "subsector_name_ar": "المطاعم والمقاهي",
      "description": "Full-service restaurants, casual dining, fine dining",
      "isic_codes": ["5610"],
      "typical_sme_size": "5-150 employees",
      "typical_sme_revenue": "$100K-$10M",
      "mena_market_size_estimate": "$60-80 billion",
      "growth_rate_5yr": "6-12%",
      "key_segments": ["Fine dining", "Casual", "Fast casual", "Ethnic/specialty"]
    },
    {
      "subsector_id": "qsr_fast_food",
      "subsector_name": "Quick Service Restaurants (QSR)",
      "subsector_name_ar": "مطاعم الخدمة السريعة",
      "description": "Fast food, quick service, grab-and-go concepts",
      "isic_codes": ["5610"],
      "typical_sme_size": "10-200 employees",
      "typical_sme_revenue": "$200K-$20M",
      "mena_market_size_estimate": "$25-35 billion",
      "growth_rate_5yr": "8-15%",
      "key_segments": ["International franchises", "Local brands", "Ghost kitchens"]
    },
    {
      "subsector_id": "cafes_coffee",
      "subsector_name": "Cafes & Coffee Shops",
      "subsector_name_ar": "المقاهي",
      "description": "Coffee shops, specialty cafes, tea houses",
      "isic_codes": ["5630"],
      "typical_sme_size": "5-80 employees",
      "typical_sme_revenue": "$100K-$8M",
      "mena_market_size_estimate": "$8-12 billion",
      "growth_rate_5yr": "10-18%",
      "key_segments": ["Specialty coffee", "Cafe chains", "Traditional"]
    },
    {
      "subsector_id": "catering_events",
      "subsector_name": "Catering & Events",
      "subsector_name_ar": "التموين والفعاليات",
      "description": "Event catering, corporate catering, wedding services",
      "isic_codes": ["5621", "5629"],
      "typical_sme_size": "10-150 employees",
      "typical_sme_revenue": "$200K-$15M",
      "mena_market_size_estimate": "$6-10 billion",
      "growth_rate_5yr": "8-14%",
      "key_segments": ["Weddings", "Corporate", "Institutional", "Private events"]
    },
    {
      "subsector_id": "travel_agencies",
      "subsector_name": "Travel Agencies & Tour Operators",
      "subsector_name_ar": "وكالات السفر والسياحة",
      "description": "Travel booking, tour packages, destination management",
      "isic_codes": ["7911", "7912", "7990"],
      "typical_sme_size": "3-50 employees",
      "typical_sme_revenue": "$100K-$10M",
      "mena_market_size_estimate": "$15-22 billion",
      "growth_rate_5yr": "5-12%",
      "key_segments": ["Leisure", "Corporate", "Religious (Hajj/Umrah)", "Inbound"]
    },
    {
      "subsector_id": "dmc_inbound",
      "subsector_name": "DMC & Inbound Tourism",
      "subsector_name_ar": "شركات إدارة الوجهات",
      "description": "Destination management companies, inbound tour services",
      "isic_codes": ["7912", "7990"],
      "typical_sme_size": "5-80 employees",
      "typical_sme_revenue": "$200K-$15M",
      "mena_market_size_estimate": "$4-7 billion",
      "growth_rate_5yr": "12-20%",
      "key_segments": ["Cultural", "Adventure", "Luxury", "MICE"]
    },
    {
      "subsector_id": "recreation_attractions",
      "subsector_name": "Recreation & Attractions",
      "subsector_name_ar": "الترفيه والمعالم السياحية",
      "description": "Theme parks, entertainment venues, attractions",
      "isic_codes": ["9321", "9329"],
      "typical_sme_size": "20-250 employees",
      "typical_sme_revenue": "$500K-$25M",
      "mena_market_size_estimate": "$8-15 billion",
      "growth_rate_5yr": "15-25%",
      "key_segments": ["Theme parks", "Water parks", "Adventure", "Cultural"]
    },
    {
      "subsector_id": "cloud_kitchens",
      "subsector_name": "Cloud Kitchens & Delivery-Only",
      "subsector_name_ar": "المطابخ السحابية",
      "description": "Delivery-only restaurants, virtual brands, dark kitchens",
      "isic_codes": ["5610", "5629"],
      "typical_sme_size": "5-50 employees",
      "typical_sme_revenue": "$100K-$5M",
      "mena_market_size_estimate": "$2-4 billion",
      "growth_rate_5yr": "25-40%",
      "key_segments": ["Multi-brand", "Single concept", "Aggregator-linked"]
    }
  ]
}
```

## 1.3 Hotel Classification

### Star Rating Framework

| Rating | Characteristics | ADR Range (MENA) | Target Segment |
|--------|----------------|------------------|----------------|
| **5-Star Luxury** | Full amenities, F&B, spa, premium service | $200-1,000+ | Luxury travelers, MICE |
| **5-Star** | Full amenities, multiple F&B outlets | $150-400 | Business, leisure |
| **4-Star** | Good amenities, restaurant, fitness | $80-200 | Upper mid-market |
| **3-Star** | Basic amenities, limited F&B | $50-120 | Budget-conscious |
| **2-Star/Budget** | Clean, basic, limited services | $30-70 | Economy travelers |
| **Boutique** | Unique, design-led, intimate | $100-500 | Experience seekers |

### Restaurant Categories

| Category | Check Average | Service Style | Target |
|----------|--------------|---------------|--------|
| Fine Dining | $80-300+ | Full service, premium | Special occasions |
| Casual Dining | $30-80 | Table service | Families, social |
| Fast Casual | $15-35 | Counter/table hybrid | Working professionals |
| QSR | $8-20 | Counter service | Mass market |
| Cafe | $10-30 | Counter/table | Social, work |
| Delivery-Only | $12-40 | No dine-in | Convenience |

## 1.4 Value Chain Position

| Position | Description | Typical SME Type | Margin Profile |
|----------|-------------|------------------|----------------|
| **Accommodation Owner** | Own/operate property | Hotels, serviced apts | Asset-heavy, 15-35% GOP |
| **Management Company** | Operate for owners | Hotel management | 3-5% of revenue |
| **Franchise** | Brand license | F&B franchises | Brand + royalty fees |
| **Independent Operator** | Own brand/operation | Independent F&B, boutique hotels | Variable |
| **Tour Operator** | Package & sell | Travel agencies, DMCs | 8-20% margin |
| **Technology Platform** | Enable transactions | OTAs, booking platforms | Commission model |

## 1.5 Adjacent Sectors

| Adjacent Sector | Relationship | Integration Level |
|-----------------|--------------|-------------------|
| **Retail & Distribution** | Duty-free, hotel retail | High |
| **Logistics & Transportation** | Airport transfers, tours | High |
| **Real Estate** | Property development | Very High |
| **F&B Manufacturing** | Supply chain | High |
| **Healthcare** | Medical tourism | Medium |
| **Entertainment** | Events, attractions | Very High |

---

# Dimension 2: Financial Benchmarks

## 2.1 Revenue Metrics

### Hotel Revenue Benchmarks

| Metric | Economy | Midscale | Upscale | Luxury |
|--------|---------|----------|---------|--------|
| **ADR (Average Daily Rate)** | $40-80 | $80-150 | $150-300 | $300-800+ |
| **Occupancy** | 55-70% | 60-75% | 65-80% | 55-75% |
| **RevPAR** | $25-50 | $55-110 | $100-220 | $180-500+ |
| **TRevPAR** | $35-70 | $80-160 | $150-350 | $300-800+ |
| **Revenue/Key/Year** | $12-25K | $25-50K | $50-100K | $100-250K+ |

### F&B Revenue Benchmarks

| Metric | QSR | Fast Casual | Casual Dining | Fine Dining |
|--------|-----|-------------|---------------|-------------|
| **Revenue/sqm/month** | $400-1,000 | $300-700 | $250-600 | $400-1,200 |
| **Revenue/seat/day** | $30-80 | $25-60 | $40-100 | $80-250 |
| **Check Average** | $8-20 | $15-35 | $30-80 | $80-300+ |
| **Covers/day/seat** | 3-6 | 2-4 | 1.5-3 | 0.8-1.5 |

### Travel Agency Revenue

| Metric | Traditional | Online-Focused | Specialty |
|--------|-------------|----------------|-----------|
| **Revenue/Employee** | $80-200K | $150-400K | $100-300K |
| **Commission Rate** | 8-15% | 5-12% | 10-20% |
| **Bookings/Agent/Month** | 40-100 | 80-200 | 30-80 |

## 2.2 Profitability Benchmarks

### Hotel Profitability (as % of Revenue)

| Metric | Economy | Midscale | Upscale | Luxury |
|--------|---------|----------|---------|--------|
| **Rooms Revenue %** | 85-95% | 75-85% | 60-70% | 45-55% |
| **F&B Revenue %** | 3-10% | 12-20% | 20-30% | 30-40% |
| **Other Revenue %** | 2-5% | 3-8% | 8-15% | 12-20% |
| **Departmental Profit** | 55-65% | 58-68% | 60-72% | 55-68% |
| **GOP (Gross Operating Profit)** | 25-35% | 30-40% | 35-48% | 35-50% |
| **EBITDA** | 20-30% | 25-35% | 28-40% | 28-42% |
| **NOI (Net Operating Income)** | 15-25% | 20-30% | 22-35% | 22-38% |

### F&B Profitability

| Metric | QSR | Fast Casual | Casual Dining | Fine Dining | Catering |
|--------|-----|-------------|---------------|-------------|----------|
| **Food Cost %** | 28-35% | 28-35% | 28-35% | 25-35% | 30-40% |
| **Beverage Cost %** | 20-28% | 22-30% | 18-28% | 18-28% | 25-35% |
| **Labor Cost %** | 22-30% | 25-32% | 28-35% | 32-42% | 25-35% |
| **Rent/Occupancy %** | 8-15% | 8-12% | 8-15% | 6-12% | 3-8% |
| **EBITDA** | 10-18% | 8-15% | 8-15% | 8-18% | 8-15% |
| **Net Profit** | 5-12% | 4-10% | 4-10% | 4-12% | 5-10% |

### Travel & Tour Operator Profitability

| Metric | Travel Agency | Tour Operator | DMC |
|--------|--------------|---------------|-----|
| **Gross Margin** | 12-20% | 15-30% | 20-40% |
| **Operating Margin** | 5-12% | 8-18% | 10-25% |
| **Net Margin** | 3-8% | 5-12% | 6-15% |

## 2.3 Cost Structure

### Hotel Cost Breakdown

| Cost Category | Economy | Midscale | Upscale | Luxury |
|---------------|---------|----------|---------|--------|
| Rooms Expense | 15-22% | 18-25% | 20-28% | 22-32% |
| F&B Expense | 60-75% of F&B rev | 65-78% | 65-78% | 68-80% |
| Marketing/Sales | 3-6% | 4-8% | 5-10% | 6-12% |
| Utilities | 4-8% | 4-7% | 4-7% | 4-8% |
| Maintenance | 3-6% | 3-5% | 4-6% | 4-7% |
| Admin & General | 6-10% | 7-11% | 8-12% | 8-12% |
| Management Fee | 2-4% | 3-5% | 3-5% | 3-5% |
| Franchise/Brand Fee | 0-3% | 2-6% | 4-8% | 5-10% |

### Restaurant Cost Breakdown

| Cost Category | QSR | Casual Dining | Fine Dining |
|---------------|-----|---------------|-------------|
| Food & Beverage | 28-35% | 28-35% | 28-38% |
| Labor | 22-30% | 28-35% | 32-42% |
| Rent | 8-15% | 8-15% | 6-12% |
| Utilities | 3-5% | 3-5% | 3-6% |
| Marketing | 2-5% | 3-6% | 4-8% |
| Royalty (Franchise) | 4-8% | 4-8% | N/A |
| Other Operating | 5-10% | 5-10% | 6-12% |

## 2.4 Working Capital Requirements

### Cash Flow Characteristics

| Subsector | DSO | DPO | Seasonality | Working Capital % |
|-----------|-----|-----|-------------|-------------------|
| Hotels | 15-45 days | 30-60 days | High | 5-15% |
| Restaurants (Cash) | 0-5 days | 14-30 days | Low-Medium | 3-8% |
| Restaurants (Card) | 3-10 days | 14-30 days | Low-Medium | 5-10% |
| Travel Agencies | 0-30 days | 7-45 days | High | 10-25% |
| Catering | 15-60 days | 14-45 days | High | 15-25% |
| Attractions | 0-7 days | 30-60 days | Very High | 8-20% |

## 2.5 Capital Requirements

### Startup CapEx

| Property Type | Cost/Key (Hotel) | Total Investment | Notes |
|--------------|------------------|------------------|-------|
| Budget Hotel (80 keys) | $30-60K | $2.5-5M | Basic fit-out |
| Midscale Hotel (120 keys) | $60-120K | $7-15M | Standard amenities |
| Upscale Hotel (150 keys) | $120-250K | $18-38M | Full amenities |
| Luxury Hotel (200 keys) | $250-500K+ | $50-100M+ | Premium everything |
| Serviced Apartments (50 units) | $50-100K | $2.5-5M | Furnished units |

| F&B Type | Size (sqm) | Cost/sqm | Total Investment |
|----------|------------|----------|------------------|
| QSR | 100-200 | $800-1,500 | $80-300K |
| Fast Casual | 150-300 | $1,000-2,000 | $150-600K |
| Casual Dining | 200-400 | $1,200-2,500 | $250-1M |
| Fine Dining | 200-500 | $2,000-5,000 | $400K-2.5M |
| Cloud Kitchen | 100-200 | $500-1,000 | $50-200K |

## 2.6 Valuation Multiples

| Subsector | Revenue Multiple | EBITDA Multiple | Key Drivers |
|-----------|------------------|-----------------|-------------|
| Hotels (Owned) | 1.5-4x | 8-15x | Location, brand, condition |
| Hotels (Managed) | 2-5x | 10-20x | Contract quality |
| Restaurant Chain | 0.5-2x | 5-12x | Brand, growth, unit economics |
| Single Restaurant | 0.3-1x | 3-6x | Profitability, lease |
| Travel Agency | 0.3-1x | 4-8x | Corporate accounts, tech |
| Tour Operator | 0.4-1.5x | 5-12x | Niche, reputation |
| Attractions | 1-4x | 8-20x | Uniqueness, location |

---

# Dimension 3: Operational KPIs

## 3.1 Hotel KPIs

### Occupancy & Revenue Management

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Occupancy Rate** | Rooms sold/available | <55% | 55-65% | 65-75% | >75% |
| **ADR Growth** | YoY rate change | <0% | 0-3% | 3-8% | >8% |
| **RevPAR Index** | vs competitive set | <95 | 95-100 | 100-110 | >110 |
| **Channel Mix (Direct)** | Direct bookings % | <20% | 20-35% | 35-50% | >50% |
| **Length of Stay** | Average nights | <1.5 | 1.5-2.5 | 2.5-4 | >4 |
| **Booking Window** | Days before arrival | <7 | 7-21 | 21-45 | >45 |

### Guest Experience

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Guest Satisfaction** | Survey score | <75% | 75-82% | 82-90% | >90% |
| **NPS** | Net Promoter Score | <30 | 30-50 | 50-70 | >70 |
| **Online Rating** | TripAdvisor/Google | <4.0 | 4.0-4.3 | 4.3-4.6 | >4.6 |
| **Repeat Guest Rate** | Return customers | <15% | 15-25% | 25-40% | >40% |
| **Complaint Resolution** | Resolved on-site | <70% | 70-85% | 85-95% | >95% |

### Operations Efficiency

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Revenue/Employee** | Total productivity | <$30K | $30-50K | $50-80K | >$80K |
| **Rooms Cleaned/Attendant** | Housekeeping productivity | <12 | 12-15 | 15-18 | >18 |
| **F&B Revenue/Cover** | Restaurant productivity | <$30 | $30-50 | $50-80 | >$80 |
| **Energy/Occupied Room** | Sustainability | >$8 | $5-8 | $3-5 | <$3 |
| **GOP Flow-Through** | Revenue to GOP | <40% | 40-55% | 55-70% | >70% |

## 3.2 Restaurant KPIs

### Sales & Revenue

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Table Turnover** | Covers/seat/service | <1.5 | 1.5-2.5 | 2.5-4 | >4 |
| **Check Average** | Revenue per guest | Below target | Target | Target+10% | Target+20% |
| **Revenue/sqm/month** | Space productivity | <$300 | $300-500 | $500-800 | >$800 |
| **Same-Store Sales Growth** | YoY growth | <0% | 0-5% | 5-12% | >12% |
| **Delivery Mix** | Off-premise % | N/A | 15-30% | 30-50% | Depends |

### Operations

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Food Cost %** | COGS/Food sales | >38% | 32-38% | 28-32% | <28% |
| **Labor Cost %** | Labor/Revenue | >35% | 30-35% | 25-30% | <25% |
| **Prime Cost** | Food + Labor | >70% | 65-70% | 58-65% | <58% |
| **Waste %** | Food waste | >8% | 5-8% | 2-5% | <2% |
| **Ticket Time** | Order to serve | >25 min | 18-25 min | 12-18 min | <12 min |

### Customer Experience

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Customer Satisfaction** | Survey scores | <75% | 75-85% | 85-92% | >92% |
| **Online Rating** | Google/Zomato | <3.8 | 3.8-4.2 | 4.2-4.5 | >4.5 |
| **Repeat Visit Rate** | Return customers | <25% | 25-40% | 40-55% | >55% |
| **Wait Time** | Queue/seating | >20 min | 12-20 min | 5-12 min | <5 min |
| **Complaint Rate** | Per 1000 covers | >15 | 8-15 | 3-8 | <3 |

## 3.3 Travel Agency KPIs

### Sales Performance

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Bookings/Agent/Month** | Productivity | <40 | 40-70 | 70-120 | >120 |
| **Revenue/Agent/Month** | Value productivity | <$5K | $5-10K | $10-20K | >$20K |
| **Conversion Rate** | Inquiries to bookings | <15% | 15-25% | 25-40% | >40% |
| **Average Booking Value** | Per transaction | <$500 | $500-1,500 | $1,500-3,000 | >$3,000 |
| **Commission Yield** | Commission % earned | <8% | 8-12% | 12-18% | >18% |

### Customer Metrics

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Customer Retention** | Repeat bookings | <30% | 30-45% | 45-60% | >60% |
| **NPS** | Recommendation | <30 | 30-50 | 50-70 | >70 |
| **Issue Resolution** | Within 24 hours | <70% | 70-85% | 85-95% | >95% |

## 3.4 Catering KPIs

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Events/Month** | Volume | <8 | 8-15 | 15-25 | >25 |
| **Revenue/Event** | Average size | <$2K | $2-5K | $5-15K | >$15K |
| **Food Cost %** | As % of revenue | >40% | 35-40% | 30-35% | <30% |
| **Labor Cost %** | Including casual | >35% | 30-35% | 25-30% | <25% |
| **Client Repeat Rate** | Return customers | <40% | 40-55% | 55-70% | >70% |
| **On-Time Execution** | Events on schedule | <90% | 90-95% | 95-99% | >99% |

## 3.5 Attraction KPIs

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Visitors/Day (Peak)** | Capacity utilization | <50% | 50-70% | 70-85% | >85% |
| **Revenue/Visitor** | Spend capture | <$15 | $15-30 | $30-50 | >$50 |
| **Secondary Spend %** | Non-admission | <20% | 20-35% | 35-50% | >50% |
| **Season Pass Holders** | Loyalty base | <5% | 5-15% | 15-30% | >30% |
| **Guest Satisfaction** | Survey score | <80% | 80-87% | 87-93% | >93% |

---

*End of Part 1 - Continue to Part 2 for Dimensions 4-7*
# Dimension 4: Regulatory Landscape

## 4.1 Business Licenses & Permits

### Hotel Licenses

| License Type | Issuing Authority | Validity | Cost Range |
|--------------|-------------------|----------|------------|
| Hotel Operating License | Tourism Ministry | 1-5 years | $2,000-20,000 |
| Star Rating Certification | Tourism Authority | 3-5 years | $1,000-10,000 |
| Municipality License | Local Municipality | Annual | $500-5,000 |
| Civil Defense Approval | Fire Department | Annual | $500-2,000 |
| Health & Safety License | Health Authority | Annual | $500-3,000 |
| Entertainment License | Tourism/Municipality | Annual | $1,000-10,000 |
| Alcohol License (where permitted) | Special Authority | Annual | $5,000-50,000+ |

### F&B Licenses

| License Type | Issuing Authority | Validity | Cost Range |
|--------------|-------------------|----------|------------|
| Restaurant License | Municipality | Annual | $500-3,000 |
| Food Handling License | Health/Food Authority | Annual | $300-1,500 |
| Trade License | Commerce Ministry | 1-3 years | $300-2,000 |
| Outdoor Seating Permit | Municipality | Annual | $500-5,000 |
| Music/Entertainment | Municipality | Annual | $500-3,000 |
| Shisha License | Health/Municipality | Annual | $1,000-5,000 |
| Delivery License | Municipality | Annual | $300-1,000 |

### Travel & Tourism Licenses

| License Type | Issuing Authority | Validity | Cost Range |
|--------------|-------------------|----------|------------|
| Travel Agency License | Tourism Ministry | 1-3 years | $1,000-10,000 |
| IATA Accreditation | IATA | Annual | $5,000-20,000 |
| Tour Operator License | Tourism Authority | 1-3 years | $2,000-15,000 |
| Hajj/Umrah License (Saudi) | Hajj Ministry | Annual | $10,000-50,000+ |
| Tourist Guide License | Tourism Ministry | 1-3 years | $200-1,000 |
| DMC License | Tourism Ministry | 1-3 years | $2,000-10,000 |

## 4.2 Compliance Requirements

### Hotel Compliance

| Requirement | Standard | Applicability |
|-------------|----------|---------------|
| Fire Safety | National fire code | All properties |
| Building Code | Structural safety | All buildings |
| Accessibility | Disabled access | New properties |
| Health & Hygiene | Food safety standards | F&B operations |
| Pool Safety | Health regulations | Properties with pools |
| Guest Registration | Immigration reporting | All accommodation |
| Data Protection | Privacy laws | Guest data |

### F&B Compliance

| Requirement | Standard | Applicability |
|-------------|----------|---------------|
| Food Safety | HACCP/Local standards | All F&B |
| Halal Certification | Islamic authority | Muslim markets |
| Kitchen Standards | Health codes | All kitchens |
| Waste Management | Environmental | All operations |
| Staff Health Cards | Health authority | All food handlers |
| Fire Safety | Fire code | All premises |
| Pest Control | Regular inspection | All F&B |

### Travel Agency Compliance

| Requirement | Description |
|-------------|-------------|
| Financial Guarantee | Bank guarantee/insurance |
| Professional Liability | E&O insurance |
| Client Fund Protection | Trust account/bonding |
| IATA Financial Criteria | For airline ticketing |
| Consumer Protection | Refund/cancellation policies |

## 4.3 Certifications

| Certification | Purpose | Cost Range | Validity |
|---------------|---------|------------|----------|
| ISO 9001 | Quality management | $3,000-15,000 | 3 years |
| ISO 22000 | Food safety | $5,000-25,000 | 3 years |
| HACCP | Food safety | $2,000-10,000 | 1-3 years |
| Green Key | Eco-certification | $1,000-5,000 | Annual |
| LEED | Green building | $5,000-30,000 | Varies |
| Halal | Islamic compliance | $1,000-5,000 | Annual |
| Safehotels Alliance | Safety/security | $2,000-10,000 | Annual |
| WTTC Safe Travels | Health protocols | $500-2,000 | Annual |

## 4.4 Regulatory Bodies by Country

### Egypt

| Authority | Responsibility |
|-----------|---------------|
| Ministry of Tourism & Antiquities | Tourism policy, licensing |
| Egyptian Tourism Federation | Industry representation |
| Egypt Food Safety Authority | Food safety |
| Civil Aviation Authority | Airlines, IATA |
| Ministry of Health | Health regulations |

### Saudi Arabia

| Authority | Responsibility |
|-----------|---------------|
| Ministry of Tourism | Tourism licensing, development |
| General Entertainment Authority (GEA) | Entertainment licensing |
| Ministry of Hajj & Umrah | Religious tourism |
| SCTH (Saudi Commission for Tourism) | Heritage sites |
| SFDA | Food safety |
| Ministry of Human Resources | Labor, Saudization |

### UAE

| Authority | Responsibility |
|-----------|---------------|
| DCT Abu Dhabi / DTCM Dubai | Tourism licensing |
| DED/DET | Trade licensing |
| Municipality | Health, safety |
| General Civil Aviation Authority | Aviation |
| Federal Tourism Authority | Federal coordination |

### Jordan

| Authority | Responsibility |
|-----------|---------------|
| Ministry of Tourism & Antiquities | Tourism policy |
| Jordan Tourism Board | Promotion |
| Jordan Restaurant Association | F&B standards |
| JFDA | Food safety |
| Civil Aviation Authority | Airlines |

### Morocco

| Authority | Responsibility |
|-----------|---------------|
| Ministry of Tourism | Tourism policy |
| ONMT (Office National Marocain du Tourisme) | Promotion |
| Regional Tourism Councils | Local licensing |
| ONSSA | Food safety |

## 4.5 Special Regulations

### Saudi Arabia - Vision 2030 Specific

| Regulation | Impact |
|------------|--------|
| Entertainment Licensing | New sector opening up |
| Tourism Visa | Expanded access |
| Saudization Quotas | 30-70% requirements |
| Women Employment | Expanded opportunities |
| Mixed-Gender Entertainment | New permissions |

### Religious Tourism

| Requirement | Description |
|-------------|-------------|
| Hajj/Umrah Operator License | Special authorization required |
| Ministry of Hajj Quotas | Pilgrim allocation |
| Hotel Classification (Makkah/Madinah) | Special standards |
| Package Requirements | Minimum standards |

---

# Dimension 5: Competitive Dynamics

## 5.1 Market Structure

| Subsector | Concentration | Market Leaders | Fragmentation |
|-----------|---------------|----------------|---------------|
| Hotels - Luxury | High | International chains (Marriott, Hilton, IHG) | Brand-dominated |
| Hotels - Midscale | Medium | Chains + regional groups | Moderate |
| Hotels - Budget | Low | Independent + brands | Fragmented |
| Restaurants - QSR | High | Global franchises | Chain-dominated |
| Restaurants - Casual | Medium | Regional chains + independents | Moderate |
| Restaurants - Fine | Low | Independent chefs | Highly fragmented |
| Travel Agencies | Low-Medium | Major agencies + OTAs | Fragmenting |
| DMCs | Low | Regional specialists | Fragmented |

## 5.2 Porter's Five Forces

```
┌─────────────────────────────────────────────────────────────────────┐
│              HOSPITALITY FIVE FORCES SUMMARY                        │
├─────────────────────────────────────────────────────────────────────┤
│                                                                      │
│                  NEW ENTRANTS: 2.5/5                                │
│                  (Capital intensive; brand barriers)                │
│                        │                                            │
│                        ▼                                            │
│   SUPPLIER POWER ────────────► INDUSTRY ◄───── BUYER POWER         │
│       2.5/5                    RIVALRY           4/5               │
│   (Fragmented                   4/5          (Price transparent,    │
│    suppliers)               (High fixed      OTA comparison,       │
│                              costs, excess    many options)         │
│                              capacity)                              │
│                        │                                            │
│                        ▼                                            │
│                SUBSTITUTES: 3.5/5                                   │
│                (Airbnb, home cooking, virtual meetings)             │
│                                                                      │
│   OVERALL ATTRACTIVENESS: MODERATE-CHALLENGING                      │
│   Key: Differentiation + Experience + Loyalty + Digital            │
└─────────────────────────────────────────────────────────────────────┘
```

### Force Details

| Force | Rating | Key Factors |
|-------|--------|-------------|
| **New Entrants** | 2.5/5 | High capital; brand/franchise barriers; location scarcity |
| **Supplier Power** | 2.5/5 | Many suppliers; some power in prime F&B ingredients |
| **Buyer Power** | 4/5 | OTA comparison; price transparency; many options |
| **Substitutes** | 3.5/5 | Airbnb, vacation rentals; home cooking; virtual meetings |
| **Rivalry** | 4/5 | High fixed costs; oversupply in some markets; rate wars |

## 5.3 Competitive Strategies

| Strategy | Description | Best For | Requirements |
|----------|-------------|----------|--------------|
| Brand Affiliation | Join major chain | Scale access | Franchise fees, standards |
| Boutique/Unique | Distinctive experience | Differentiation | Design, service excellence |
| Value Leader | Best price/quality | Budget segment | Cost efficiency |
| Location Dominance | Prime sites | All segments | Capital, relationships |
| Digital-First | Tech-enabled experience | Modern travelers | Technology investment |
| Niche Specialist | Specific segment focus | DMCs, specialty F&B | Deep expertise |
| Experience Focus | Memorable experiences | Upscale | Creativity, service |

## 5.4 Industry Trends

| Trend | Impact | Timeframe | SME Opportunity |
|-------|--------|-----------|-----------------|
| **Vision 2030 Development** | Massive capacity addition | 2-10 years | Supply chain, services |
| **Experiential Travel** | Experience over luxury | Ongoing | Unique offerings |
| **Sustainability** | Eco-tourism demand | 2-7 years | Green positioning |
| **Digital/Contactless** | Changed expectations | Ongoing | Tech adoption |
| **Workation/Bleisure** | Extended stays | Ongoing | Serviced apartments |
| **Local/Authentic** | Seek genuine experiences | Ongoing | Local knowledge |
| **Health & Wellness** | Wellness tourism | 2-5 years | Spa, healthy F&B |
| **Ghost Kitchens** | Delivery-first F&B | Ongoing | Lower capital entry |
| **Solo Travel** | Growing segment | Ongoing | Solo-friendly design |
| **Religious Tourism** | Growing pilgrimage | Ongoing | Specialized services |

## 5.5 Major Player Landscape

### Hotel Chains in MENA

| Group | Properties (MENA) | Segments | Strategy |
|-------|-------------------|----------|----------|
| Marriott | 200+ | Full range | Aggressive expansion |
| Hilton | 150+ | Full range | Major Saudi investment |
| IHG | 100+ | Full range | Middle East focus |
| Accor | 200+ | Full range | Regional leader |
| Rotana | 100+ | Regional | Middle East specialist |
| Emaar Hospitality | 20+ | Premium | UAE-focused |

### F&B Chains

| Type | Examples | Presence |
|------|----------|----------|
| Global QSR | McDonald's, KFC, Starbucks | Pan-MENA |
| Regional QSR | Al Baik, Herfy, Mo'men | Country-specific |
| Casual Dining | Applebee's, Chili's, local | Pan-MENA |
| Regional Concepts | Comptoir, Shakeshack | Growing |

### OTAs & Distribution

| Platform | Market Position | Commission |
|----------|-----------------|------------|
| Booking.com | Market leader | 15-25% |
| Expedia Group | Strong #2 | 15-25% |
| Agoda | Asia/MENA | 15-22% |
| Almosafer (Seera) | Regional leader | 10-20% |
| Wego | Meta-search | CPC model |

## 5.6 Market-Specific Dynamics

| Country | Market Size | Growth Driver | Key Challenge |
|---------|-------------|---------------|---------------|
| **Saudi Arabia** | Fastest growing | Vision 2030, new licenses | Capacity building |
| **UAE** | Most developed | Expo legacy, hub | Competition, rates |
| **Egypt** | High potential | Heritage, value | Infrastructure |
| **Jordan** | Niche | Religious, adventure | Regional stability |
| **Morocco** | Diverse | Culture, coast | Seasonality |

---

# Dimension 6: Digital Maturity

## 6.1 Technology Adoption Benchmarks

| Subsector | Current Adoption | Digital Leaders | Digital Laggards | Key Gap |
|-----------|------------------|-----------------|------------------|---------|
| Hotels - Chain | High | 60% | 15% | Personalization |
| Hotels - Independent | Low-Medium | 20% | 55% | PMS, distribution |
| Restaurants - Chain | Medium-High | 45% | 25% | Integration |
| Restaurants - Independent | Low | 15% | 60% | POS, online ordering |
| Travel Agencies | Medium | 35% | 35% | Online booking |
| DMCs | Low-Medium | 25% | 45% | CRM, operations |
| Attractions | Medium | 40% | 30% | Ticketing, experience |

## 6.2 Digital Maturity Levels

```
┌─────────────────────────────────────────────────────────────────────────────┐
│              HOSPITALITY DIGITAL MATURITY LEVELS                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  LEVEL 1: ANALOG (Score 0-20)                                               │
│  • Paper reservations, manual billing, no online presence                   │
│  • Typical: Traditional guesthouses, small restaurants                     │
│                                                                              │
│  LEVEL 2: BASIC DIGITAL (Score 21-40)                                       │
│  • Basic PMS/POS, website, social media, OTA presence                       │
│  • Typical: Small hotels, casual restaurants                               │
│                                                                              │
│  LEVEL 3: CONNECTED (Score 41-60)                                           │
│  • Integrated PMS/POS, channel manager, basic CRM, online ordering          │
│  • Typical: Mid-tier hotels, restaurant chains                             │
│                                                                              │
│  LEVEL 4: INTEGRATED (Score 61-80)                                          │
│  • Revenue management, loyalty systems, analytics, mobile apps              │
│  • Typical: Upscale chains, leading independents                           │
│                                                                              │
│  LEVEL 5: INTELLIGENT (Score 81-100)                                        │
│  • AI personalization, predictive analytics, IoT, automation               │
│  • Typical: Luxury chains, tech-forward concepts                           │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 6.3 Core Technology Systems

### Hotel Systems

| System | Priority | Investment Range | Payback | MENA Adoption |
|--------|----------|------------------|---------|---------------|
| PMS (Property Management) | Critical | $5K-100K | 6-12 mo | 70% |
| Channel Manager | Critical | $1K-10K/year | 3-6 mo | 50% |
| Booking Engine | Critical | $2K-20K | 6-12 mo | 55% |
| Revenue Management | High | $5K-50K/year | 6-18 mo | 30% |
| CRM/Loyalty | High | $3K-30K | 12-24 mo | 25% |
| Guest Experience App | Medium | $10K-50K | 12-24 mo | 15% |
| Contactless Check-in | Medium | $5K-30K | 12-24 mo | 20% |
| Energy Management | Medium | $10K-50K | 24-36 mo | 15% |

### F&B Systems

| System | Priority | Investment Range | Payback | MENA Adoption |
|--------|----------|------------------|---------|---------------|
| POS System | Critical | $2K-30K | 3-6 mo | 65% |
| Online Ordering | High | $3K-20K | 6-12 mo | 45% |
| Kitchen Display (KDS) | High | $1K-10K | 6-12 mo | 35% |
| Inventory Management | High | $2K-15K | 6-18 mo | 30% |
| Reservation System | Medium-High | $1K-10K | 6-12 mo | 40% |
| Delivery Integration | High | Per order fee | Immediate | 55% |
| Loyalty Program | Medium | $2K-20K | 12-24 mo | 20% |
| Analytics/BI | Medium | $3K-20K | 12-24 mo | 15% |

### Travel Agency Systems

| System | Priority | Investment Range | Payback | MENA Adoption |
|--------|----------|------------------|---------|---------------|
| GDS Access | Critical | Variable fees | Immediate | 80% |
| Booking Platform | Critical | $5K-50K | 6-12 mo | 60% |
| CRM | High | $3K-20K | 12-24 mo | 35% |
| Website/E-commerce | High | $5K-30K | 12-24 mo | 50% |
| Accounting Integration | Medium | $2K-10K | 12-24 mo | 45% |
| Tour Operations | Medium | $3K-20K | 12-24 mo | 30% |

## 6.4 High-Impact Digital Interventions

| Subsector | Priority 1 | Priority 2 | Priority 3 | Impact |
|-----------|------------|------------|------------|--------|
| Hotels | Direct booking engine | Channel manager | Guest CRM | 15-25% RevPAR |
| Restaurants | Online ordering | POS upgrade | Loyalty | 15-30% revenue |
| Travel Agencies | Online platform | CRM | Automation | 20-35% productivity |
| DMCs | Tour management system | Website/SEO | CRM | 25-40% efficiency |
| Attractions | Online ticketing | App experience | Yield management | 15-25% revenue |

## 6.5 Distribution Channel Mix

### Hotels

| Channel | Commission/Cost | Target Mix | Trend |
|---------|-----------------|------------|-------|
| Direct Website | 2-4% | 25-40% | Growing |
| Direct Walk-in/Phone | 0-2% | 5-15% | Declining |
| OTAs (Booking, Expedia) | 15-25% | 30-50% | Stable/declining |
| GDS (Corporate) | 5-15% | 10-25% | Stable |
| Wholesalers | 20-35% | 5-20% | Declining |
| Meta-Search | CPC $0.5-3 | Growing | Growing |

### Restaurants

| Channel | Commission/Cost | Target Mix | Trend |
|---------|-----------------|------------|-------|
| Dine-in | 0% | 40-70% | Recovering |
| Takeaway | 0-5% | 10-20% | Stable |
| Own Delivery | 15-25% cost | 5-15% | Growing |
| Aggregators (Talabat, etc.) | 20-35% | 15-35% | Growing |
| Corporate/Catering | 0-10% | 5-15% | Growing |

---

# Dimension 7: Workforce Norms

## 7.1 Organizational Structures

### Small Hotel (50 keys, 30-50 employees)
```
              General Manager
                    │
       ┌────────────┼────────────┐
       │            │            │
   Front Office  Housekeeping  F&B Manager
    Manager        Manager     (if applicable)
       │            │            │
   Reception    Room         Restaurant
   Concierge   Attendants      Staff
   Night Audit  Laundry
```

### Restaurant (Casual Dining, 20-40 employees)
```
              Restaurant Manager
                    │
       ┌────────────┼────────────┐
       │            │            │
   Head Chef    Front of House  Admin
       │          Manager         │
   ┌───┴───┐       │          Accounting
  Sous Chef    Supervisors      Receiving
  Line Cooks    Servers
  Prep         Host/Hostess
  Dishwasher   Bartender
```

### Travel Agency (10-30 employees)
```
              General Manager
                    │
       ┌────────────┼────────────┐
       │            │            │
   Sales/Booking  Operations   Finance
    Manager       Manager      Manager
       │            │            │
   Travel       Tour Guides   Accounting
   Consultants  Ticketing       (1-2)
   (5-15)       Support
```

## 7.2 Key Roles

### Hotel Roles

| Role | Responsibilities | Experience | Education |
|------|------------------|------------|-----------|
| General Manager | Full P&L responsibility | 10-15 years | Hospitality degree |
| Revenue Manager | Pricing, distribution | 5-8 years | Revenue/hospitality |
| Front Office Manager | Guest services | 5-8 years | Hospitality diploma |
| Executive Housekeeper | Rooms operations | 5-10 years | Housekeeping exp |
| F&B Manager | Restaurant/banquet | 5-10 years | Culinary/hospitality |
| Sales Manager | Corporate/groups | 5-8 years | Sales experience |
| Chief Engineer | Maintenance | 8-12 years | Technical |
| Guest Relations | VIP/loyalty | 3-5 years | Hospitality |

### F&B Roles

| Role | Responsibilities | Experience | Certifications |
|------|------------------|------------|----------------|
| Executive Chef | Kitchen leadership | 10-15 years | Culinary degree |
| Sous Chef | Kitchen operations | 5-8 years | Culinary training |
| Restaurant Manager | Floor operations | 5-8 years | F&B management |
| Bartender | Bar service | 2-5 years | Mixology training |
| Server | Guest service | 0-3 years | Food safety |
| Line Cook | Food preparation | 2-5 years | Culinary |
| Host/Hostess | Reservations, seating | 1-3 years | Customer service |

### Travel Roles

| Role | Responsibilities | Experience | Requirements |
|------|------------------|------------|--------------|
| Travel Consultant | Client bookings | 2-5 years | GDS training |
| Product Manager | Package development | 4-7 years | Industry knowledge |
| Tour Guide | Guest experiences | 2-5 years | Licensed |
| Operations Coordinator | Logistics | 2-4 years | Detail-oriented |
| Key Account Manager | Corporate accounts | 5-8 years | Sales experience |

## 7.3 Compensation Benchmarks (USD/month)

### Egypt

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Hotel GM | $1,500-2,500 | $2,500-5,000 | $5,000-10,000 |
| F&B Manager | $500-800 | $800-1,500 | $1,500-3,000 |
| Front Desk Agent | $200-300 | $300-500 | $500-800 |
| Chef de Cuisine | $600-1,000 | $1,000-2,000 | $2,000-4,000 |
| Server | $120-180 | $180-300 | $300-500 |
| Travel Consultant | $250-400 | $400-700 | $700-1,200 |

### Saudi Arabia

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Hotel GM | $6,000-10,000 | $10,000-18,000 | $18,000-35,000 |
| F&B Manager | $2,500-4,000 | $4,000-7,000 | $7,000-12,000 |
| Front Desk Agent | $1,200-1,800 | $1,800-2,800 | $2,800-4,000 |
| Chef de Cuisine | $3,000-5,000 | $5,000-9,000 | $9,000-15,000 |
| Server | $800-1,200 | $1,200-1,800 | $1,800-2,500 |
| Travel Consultant | $1,500-2,500 | $2,500-4,500 | $4,500-7,000 |

### UAE

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Hotel GM | $8,000-15,000 | $15,000-25,000 | $25,000-50,000 |
| F&B Manager | $3,000-5,000 | $5,000-8,000 | $8,000-15,000 |
| Front Desk Agent | $1,500-2,200 | $2,200-3,500 | $3,500-5,000 |
| Chef de Cuisine | $4,000-7,000 | $7,000-12,000 | $12,000-20,000 |
| Server | $800-1,200 | $1,200-2,000 | $2,000-3,000 |
| Travel Consultant | $2,000-3,500 | $3,500-6,000 | $6,000-10,000 |

### Jordan

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Hotel GM | $2,000-3,500 | $3,500-6,000 | $6,000-12,000 |
| F&B Manager | $700-1,200 | $1,200-2,200 | $2,200-4,000 |
| Front Desk Agent | $350-550 | $550-850 | $850-1,200 |
| Chef de Cuisine | $900-1,500 | $1,500-3,000 | $3,000-5,000 |
| Server | $280-400 | $400-650 | $650-900 |
| Travel Consultant | $450-750 | $750-1,300 | $1,300-2,200 |

## 7.4 Skills Gap Analysis

| Skill Area | Availability | Demand | Gap Severity |
|------------|--------------|--------|--------------|
| Digital/Technology | Low | Very High | **Critical** |
| Revenue Management | Low | High | **High** |
| Guest Experience | Medium | Very High | **High** |
| Culinary (Advanced) | Low-Medium | High | **High** |
| Languages (Multiple) | Medium | High | **Medium** |
| Management/Leadership | Low-Medium | High | **High** |
| Sustainability | Low | Growing | **Medium** |
| Sales/Marketing | Medium | High | **Medium** |

## 7.5 Labor Market Characteristics

| Characteristic | Egypt | Saudi Arabia | UAE | Jordan |
|---------------|-------|--------------|-----|--------|
| Local vs Expat | 90%+ local | 30/70 | 10/90 | 75/25 |
| Hotel Turnover | 25-40% | 30-50% | 40-60% | 25-35% |
| F&B Turnover | 40-60% | 35-55% | 50-70% | 35-50% |
| Female Participation | 20-30% | 15-30% (growing) | 35-45% | 25-35% |
| Nationalization | N/A | High (Saudization) | Medium | N/A |
| Seasonal Fluctuation | High | Medium | Medium | High |

## 7.6 HR KPIs

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| Staff Turnover | >50% | 35-50% | 20-35% | <20% |
| RevPAR/Employee | <$3K | $3-5K | $5-8K | >$8K |
| Training Hours/Year | <20 | 20-40 | 40-60 | >60 |
| Employee Satisfaction | <60% | 60-72% | 72-85% | >85% |
| Absenteeism | >8% | 5-8% | 2-5% | <2% |
| Internal Promotion % | <10% | 10-25% | 25-40% | >40% |

---

*End of Part 2 - Continue to Part 3 for Dimensions 8-11*
# Dimension 8: Supply Chain

## 8.1 Input Categories

### Hotel Inputs

| Category | % of Costs | Import Dependency | Key Suppliers |
|----------|-----------|-------------------|---------------|
| F&B Supplies | 15-25% | 30-60% | Local distributors, importers |
| Linens & Amenities | 3-6% | 50-80% | Regional suppliers |
| Cleaning Supplies | 2-4% | 40-70% | Local/regional |
| Maintenance/Equipment | 3-8% | 60-80% | International brands |
| Energy (Electricity/Gas) | 4-8% | Local utility | Utility companies |
| Technology/Software | 2-5% | 80-95% | International vendors |
| FF&E (Replacement) | 3-8% | 70-90% | International suppliers |

### F&B Inputs

| Category | % of Revenue | Key Considerations |
|----------|-------------|-------------------|
| Food - Proteins | 8-15% | Quality, freshness, halal |
| Food - Produce | 5-10% | Seasonality, local sourcing |
| Food - Dry Goods | 5-8% | Storage, shelf life |
| Beverages | 5-12% | Licensing, import duties |
| Packaging (Delivery) | 2-5% | Growing with delivery |
| Kitchen Consumables | 1-3% | Equipment replacement |

### Travel Agency Inputs

| Category | % of Revenue | Relationship Type |
|----------|-------------|-------------------|
| Airline Tickets | 40-60% | Commission model |
| Hotel Inventory | 15-30% | Net rates/markup |
| Ground Services | 10-25% | B2B partnerships |
| Visa Services | 2-8% | Service fees |
| Insurance | 2-5% | Partner agreements |

## 8.2 Supplier Management

### Hotel Supplier Terms

| Supplier Type | Payment Terms | Relationship |
|---------------|---------------|--------------|
| Food & Beverage | Net 7-30 | Regular orders |
| Linens/Amenities | Net 30-60 | Contracts |
| Equipment | Net 30-90 | Project-based |
| Utilities | Monthly billing | Regulated |
| Technology | Annual subscription | Contracts |
| OTAs | Commission deduction | Ongoing |

### Restaurant Supplier Terms

| Supplier Type | Payment Terms | Order Frequency |
|---------------|---------------|-----------------|
| Fresh Produce | COD to Net 7 | Daily-2x weekly |
| Proteins (Meat/Fish) | Net 7-14 | 2-3x weekly |
| Dry Goods | Net 15-30 | Weekly-monthly |
| Beverages | Net 15-30 | Weekly |
| Delivery Platforms | Weekly settlement | Continuous |

## 8.3 Inventory Management

### Hotel Inventory

| Category | Par Level Approach | Turnover Target |
|----------|-------------------|-----------------|
| Food (Perishable) | 2-4 days | 15-25x/month |
| Food (Dry) | 1-2 weeks | 4-8x/month |
| Beverages | 2-3 weeks | 3-6x/month |
| Linens | 3-5 par levels | Replace annually |
| Guest Amenities | 2-4 weeks | N/A |
| Cleaning Supplies | 2-4 weeks | N/A |

### Restaurant Inventory

| Category | Days of Stock | Key Controls |
|----------|--------------|--------------|
| Proteins | 2-5 days | Temperature, FIFO |
| Produce | 1-3 days | Freshness, waste |
| Dairy | 3-7 days | Expiry management |
| Dry Goods | 7-21 days | Pest control |
| Beverages | 14-30 days | Security |

## 8.4 Quality Standards

### Food Safety

| Standard | Requirement | Compliance |
|----------|-------------|------------|
| HACCP | Hazard analysis | All commercial F&B |
| Temperature Control | Cold chain integrity | Critical |
| Supplier Certification | Quality verification | Best practice |
| Allergen Management | Disclosure required | Mandatory |
| Halal Compliance | Islamic standards | Market requirement |

### Service Standards

| Area | Standard | Measurement |
|------|----------|-------------|
| Guest Service | Brand standards | Mystery shopping |
| Cleanliness | Inspection protocols | Daily audits |
| Food Quality | Recipe consistency | Quality checks |
| Safety | Fire/health codes | Regular inspections |

## 8.5 Procurement Models

### Centralized vs Decentralized

| Model | Best For | Benefits | Challenges |
|-------|----------|----------|------------|
| Centralized | Chains, groups | Volume pricing | Flexibility |
| Decentralized | Independents | Local relationships | Inconsistency |
| Hybrid | Medium groups | Balance | Complexity |

### Outsourcing Considerations

| Function | Outsource Option | Typical Decision |
|----------|------------------|------------------|
| Laundry | Commercial laundry | Small/medium hotels |
| Security | Security companies | All sizes |
| Maintenance | Service contracts | Specialized equipment |
| Housekeeping | Managed service | Limited |
| F&B | Management contract | Hotel restaurants |

---

# Dimension 9: Export Requirements

## 9.1 Service Export Capabilities

For hospitality, "export" primarily means serving international tourists:

| Capability | Requirements | Key Markets |
|------------|--------------|-------------|
| Inbound Tourism | Licensed operator | Source markets |
| MICE | Convention capabilities | Corporate/international |
| Medical Tourism | Healthcare partnerships | Gulf, Africa |
| Religious Tourism | Specialized licenses | Global Muslim |
| Education Tourism | Program partnerships | Regional |

## 9.2 International Standards

| Standard | Purpose | Requirement |
|----------|---------|-------------|
| Star Rating | International recognition | Consistency |
| Brand Standards | Chain compliance | Franchise requirement |
| Safety Certifications | Travel advisories | Insurance, liability |
| Language Capabilities | Guest service | Multi-lingual staff |
| Payment Systems | International cards | PCI compliance |

## 9.3 Tour Operator Export

| Service | Requirements | Markets |
|---------|--------------|---------|
| Outbound Tours | IATA, tour operator license | International |
| Hajj/Umrah Packages | Ministry license, quotas | Global Muslim |
| Corporate Travel | Corporate accounts | MNCs |
| Group Travel | Group handling | Wholesale markets |

## 9.4 International Certifications

| Certification | Purpose | Investment |
|---------------|---------|------------|
| Green Key | Eco-tourism | $1-5K |
| WTTC Safe Travels | Health protocols | $500-2K |
| Halal Certification | Muslim travelers | $1-5K |
| Accessibility Standards | Disabled travelers | Varies |
| Sustainable Tourism | ESG compliance | $2-10K |

---

# Dimension 10: Packaging & Labeling

## 10.1 Service Packaging

### Hotel Packages

| Package Type | Components | Target Segment |
|--------------|------------|----------------|
| Room Only | Accommodation | Budget/business |
| B&B | Room + breakfast | Leisure |
| Half Board | Room + 2 meals | Resorts |
| All-Inclusive | Full package | Resorts |
| Romance/Honeymoon | Special inclusions | Couples |
| Family Package | Kids amenities | Families |
| Business Package | WiFi, meeting | Corporate |

### Tour Packages

| Package Type | Components | Pricing Model |
|--------------|------------|---------------|
| FIT (Independent) | Custom itinerary | Per person |
| Group Tour | Fixed itinerary | Per person |
| Private Tour | Exclusive guide | Per group |
| Day Tours | Single day | Fixed price |
| Multi-Day | Full program | Package |
| MICE | Conference package | Per delegate |

## 10.2 F&B Packaging

### Delivery Packaging

| Requirement | Standard | Sustainability Trend |
|-------------|----------|---------------------|
| Food Safety | Temperature maintenance | Insulated packaging |
| Tamper-Evident | Sealed containers | Required |
| Branding | Logo, contact info | Marketing |
| Eco-Friendly | Biodegradable options | Growing demand |
| Portion Control | Consistent sizing | Quality control |

### Labeling Requirements

| Element | Requirement |
|---------|-------------|
| Ingredients | Allergen disclosure |
| Nutritional Info | Growing requirement |
| Expiry/Prep Time | Food safety |
| Halal Status | Market requirement |
| Business Info | Contact, license |

## 10.3 Promotional Materials

### Digital Collateral

| Material | Purpose | Standards |
|----------|---------|-----------|
| Website | Direct booking | Mobile-first, SEO |
| Social Media | Engagement | Platform-specific |
| Email Marketing | Retention | GDPR-compliant |
| OTA Listings | Distribution | Platform guidelines |
| Virtual Tours | Immersive preview | High quality |

### Print Collateral

| Material | Usage | Considerations |
|----------|-------|----------------|
| Brochures | Trade shows, in-house | Multi-language |
| Menu Design | In-restaurant | Regulatory compliance |
| Room Directory | In-room | Brand standards |
| Rate Cards | Corporate sales | Regular updates |

---

# Dimension 11: MENA Regional Context

## 11.1 Country Profiles

### Egypt

| Attribute | Details |
|-----------|---------|
| **Tourism Arrivals** | 14-15 million (2024) |
| **Hotel Rooms** | ~220,000 |
| **Key Segments** | Heritage, beach, Nile cruises |
| **Seasonality** | Peak: Oct-Apr |
| **Strengths** | UNESCO sites, value, variety |
| **Challenges** | Infrastructure, safety perception |
| **Opportunities** | Heritage revival, Red Sea development |

### Saudi Arabia

| Attribute | Details |
|-----------|---------|
| **Tourism Arrivals** | 27-30 million (inc. religious) |
| **Hotel Rooms** | ~280,000 (growing rapidly) |
| **Key Segments** | Religious, MICE, leisure (new) |
| **Seasonality** | Religious calendar-driven |
| **Strengths** | Vision 2030 investment, holy sites |
| **Challenges** | Capacity building, skills |
| **Opportunities** | NEOM, Red Sea, AlUla, entertainment |

### UAE

| Attribute | Details |
|-----------|---------|
| **Tourism Arrivals** | 18-20 million |
| **Hotel Rooms** | ~200,000 |
| **Key Segments** | MICE, luxury, beach, shopping |
| **Seasonality** | Peak: Oct-Apr |
| **Strengths** | Infrastructure, hub, brands |
| **Challenges** | Competition, rates, oversupply |
| **Opportunities** | Expo legacy, events, sustainable |

### Jordan

| Attribute | Details |
|-----------|---------|
| **Tourism Arrivals** | 5-6 million |
| **Hotel Rooms** | ~35,000 |
| **Key Segments** | Heritage (Petra), religious, medical |
| **Seasonality** | Peak: Mar-May, Sep-Nov |
| **Strengths** | UNESCO sites, safety, value |
| **Challenges** | Regional perception, airlift |
| **Opportunities** | Adventure, wellness, Dead Sea |

### Morocco

| Attribute | Details |
|-----------|---------|
| **Tourism Arrivals** | 14-15 million |
| **Hotel Rooms** | ~250,000 |
| **Key Segments** | Culture, beach, desert |
| **Seasonality** | Year-round, peak spring/fall |
| **Strengths** | Diversity, accessibility, value |
| **Challenges** | Infrastructure outside cities |
| **Opportunities** | Luxury lodges, eco-tourism |

## 11.2 Vision 2030 Impact (Saudi Arabia)

### Mega Projects

| Project | Investment | Opening | Impact |
|---------|-----------|---------|--------|
| NEOM | $500B+ | Phased 2025+ | New destination |
| Red Sea Project | $16B | 2024+ | Luxury eco-resort |
| AlUla | $15B+ | Ongoing | Heritage tourism |
| Qiddiya | $8B+ | 2024+ | Entertainment |
| Diriyah Gate | $20B+ | Ongoing | Heritage/culture |

### Tourism Targets

| Metric | 2019 | 2030 Target |
|--------|------|-------------|
| International Visitors | 17M | 150M |
| Tourism GDP Contribution | 3.5% | 10% |
| Tourism Jobs | 850K | 1.6M |
| Hotel Rooms | 220K | 500K+ |

## 11.3 Seasonality Patterns

| Market | Peak Season | Shoulder | Low Season |
|--------|------------|----------|------------|
| Egypt | Oct-Apr | Sep, May | Jun-Aug |
| Saudi (Leisure) | Oct-Apr | Sep, May | Jun-Aug |
| Saudi (Religious) | Hajj, Ramadan, Eid | Year-round | - |
| UAE | Oct-Apr | Sep, May | Jun-Aug |
| Jordan | Mar-May, Sep-Nov | Jun, Oct | Dec-Feb, Jul-Aug |
| Morocco | Mar-May, Sep-Nov | Jun, Dec | Jul-Aug |

## 11.4 Key Tourism Segments

| Segment | Key Markets | Growth Rate | MENA Relevance |
|---------|-------------|-------------|----------------|
| Religious (Hajj/Umrah) | Global Muslim | 3-5% | Very High (SA) |
| Heritage/Cultural | Europe, Asia | 5-8% | Very High (EG, JO, MA) |
| Beach/Resort | Europe, GCC | 4-7% | High (EG, UAE, MA) |
| MICE | Global corporate | 6-10% | High (UAE, SA) |
| Luxury | HNW global | 8-12% | High (UAE, SA) |
| Adventure | Europe, Americas | 10-15% | Growing (JO, MA) |
| Wellness | Global | 12-18% | Growing |
| Medical | Africa, Regional | 8-12% | High (JO, UAE) |

## 11.5 Business Culture Considerations

| Aspect | Consideration |
|--------|---------------|
| Hospitality Tradition | Exceptional guest service expected |
| Relationship-Based | Personal connections matter |
| Ramadan Operations | Adjusted hours, iftar business |
| Friday Impact | Reduced operations (Gulf) |
| Gender Considerations | Evolving in Saudi; mixed elsewhere |
| Halal Importance | Critical for food service |
| Cash Culture | Still significant in Egypt, Jordan |
| Tipping Customs | Expected but varies by country |

## 11.6 Strategic Opportunities

| Opportunity | Markets | Potential | Requirements |
|-------------|---------|-----------|--------------|
| Vision 2030 Supply Chain | Saudi | Very High | Scale, quality |
| Experiential Tourism | All | High | Creativity, authenticity |
| Sustainable Tourism | All | High | Certifications, practices |
| Digital Transformation | All | High | Technology investment |
| F&B Innovation | Gulf, Egypt | High | Concepts, quality |
| Medical Tourism | Jordan, UAE | Medium-High | Partnerships |
| Religious Tourism Services | Saudi | High | Specialized licenses |

---

# Document Summary

## Sector Overview

**Hospitality & Tourism** in MENA represents:

**Market Size & Growth:**
- ~$150-200 billion total market
- 100+ million annual visitors across region
- Fastest-growing tourism market globally (Saudi)
- Massive infrastructure investment (Vision 2030)

**Key Characteristics:**
- High seasonality (Oct-Apr peak most markets)
- Labor-intensive with service quality critical
- Digital transformation accelerating (OTAs, contactless)
- Religious tourism unique strength (Hajj/Umrah)
- Heritage assets (Egypt, Jordan) underutilized

**SME Landscape:**
- Wide range from small restaurants to boutique hotels
- Franchise model common for F&B
- Independent hotels facing brand competition
- Travel agencies disrupted by OTAs, pivoting to niche
- DMCs well-positioned for inbound growth

**Priority Subsectors:**
1. **Hotels & Resorts** - Vision 2030 creating massive opportunity
2. **Restaurants & Dining** - Growing with tourism and local demand
3. **DMC & Inbound Tourism** - International visitor growth
4. **Cloud Kitchens** - 25-40% growth, lower capital
5. **Attractions & Recreation** - New entertainment licenses (Saudi)

## Agent Usage Guide

| Agent | Primary Dimensions | Key Data Points |
|-------|-------------------|-----------------|
| **The Drucker** | 1, 11 | Subsector classification, Vision 2030 context |
| **The Marvin** | 3, 4 | Hospitality KPIs, regulatory compliance |
| **The Graham** | 2 | GOP, RevPAR, F&B margins, valuation |
| **The Ricardo** | 9, 10 | International standards, service packaging |
| **The Lovelace** | 6 | PMS/POS adoption, digital distribution |
| **The Mayo** | 7 | Workforce, compensation, skills gaps |
| **The Ohno** | 8 | Supply chain, inventory, procurement |
| **The Porter** | 5 | Five Forces, OTA dynamics, Vision 2030 |
| **The Landor** | 10 | Package design, F&B branding |

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | December 2025 | RootRise Product Team | Initial release |

---

*This document is part of the RootRise Sector Knowledge Pack series, providing comprehensive sector intelligence for The Pantheon multi-agent diagnostic system.*
