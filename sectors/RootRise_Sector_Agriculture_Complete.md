# RootRise Sector Knowledge Pack
# Agriculture & Agribusiness
## Version 1.0 | December 2025

---

# Sector Metadata

```json
{
  "metadata": {
    "sector_id": "agriculture_agribusiness",
    "sector_name": "Agriculture & Agribusiness",
    "sector_name_ar": "الزراعة والأعمال الزراعية",
    "version": "1.0.0",
    "last_updated": "2025-12-11",
    "sector_type": "Industrial (Primary Production)",
    "data_sources": [
      {
        "source_id": "fao_mena_2024",
        "name": "FAO Regional Overview of Food Security and Nutrition - Near East and North Africa",
        "type": "international_org",
        "publication_date": "2024-11",
        "reliability_score": 0.95
      },
      {
        "source_id": "worldbank_agri_2024",
        "name": "World Bank Agriculture and Food Global Practice - MENA Regional Brief",
        "type": "international_org",
        "publication_date": "2024-06",
        "reliability_score": 0.93
      },
      {
        "source_id": "icarda_2024",
        "name": "International Center for Agricultural Research in the Dry Areas Reports",
        "type": "research",
        "publication_date": "2024-08",
        "reliability_score": 0.92
      },
      {
        "source_id": "usda_mena_2024",
        "name": "USDA Foreign Agricultural Service MENA Reports",
        "type": "government",
        "publication_date": "2024-09",
        "reliability_score": 0.90
      },
      {
        "source_id": "gafi_egypt_2024",
        "name": "General Authority for Investment Egypt - Agricultural Investment Guide",
        "type": "government",
        "publication_date": "2024-05",
        "reliability_score": 0.88
      },
      {
        "source_id": "moccae_uae_2024",
        "name": "UAE Ministry of Climate Change - Agricultural Statistics",
        "type": "government",
        "publication_date": "2024-07",
        "reliability_score": 0.88
      },
      {
        "source_id": "mosd_jordan_2024",
        "name": "Jordan Ministry of Agriculture - Agricultural Sector Overview",
        "type": "government",
        "publication_date": "2024-04",
        "reliability_score": 0.87
      },
      {
        "source_id": "statista_agri_mena_2024",
        "name": "Statista Agriculture in the MENA Region",
        "type": "research",
        "publication_date": "2024-10",
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
    "applicable_countries": ["EG", "SA", "AE", "JO", "MA", "TN", "LB", "IQ", "SY", "YE", "OM", "BH", "KW", "QA", "DZ", "LY", "PS", "SD"],
    "sme_size_range": {
      "min_employees": 3,
      "max_employees": 150,
      "min_revenue_usd": 25000,
      "max_revenue_usd": 15000000
    }
  }
}
```

---

# Dimension 1: Industry Classification

## 1.1 Standard Classifications

| Classification | Code | Description |
|----------------|------|-------------|
| **ISIC Rev.4 Section** | A | Agriculture, forestry and fishing |
| **ISIC Division** | 01 | Crop and animal production |
| **ISIC Division** | 02 | Forestry and logging |
| **ISIC Division** | 03 | Fishing and aquaculture |
| **Related Division** | 10 | Manufacture of food products |
| **Related Division** | 11 | Manufacture of beverages |
| **NACE Rev.2** | A01-A03 | Agriculture, forestry and fishing |
| **RootRise Type** | Industrial (Primary) | Primary production and processing |

### Detailed ISIC Classification Breakdown

**Division 01 - Crop and Animal Production:**

| ISIC Group | ISIC Class | Description | SME Relevance in MENA |
|------------|------------|-------------|----------------------|
| 01.1 | 01.11 | Growing of cereals (except rice), leguminous crops and oil seeds | **High** - Wheat, barley, lentils |
| 01.1 | 01.12 | Growing of rice | Medium - Limited (Egypt mainly) |
| 01.1 | 01.13 | Growing of vegetables and melons, roots and tubers | **Very High** - Vegetable farms |
| 01.2 | 01.21 | Growing of grapes | **High** - Table grapes, raisins |
| 01.2 | 01.22 | Growing of tropical and subtropical fruits | **Very High** - Citrus, mangoes |
| 01.2 | 01.23 | Growing of citrus fruits | **Very High** - Major export |
| 01.2 | 01.24 | Growing of pome fruits and stone fruits | **High** - Apples, peaches |
| 01.2 | 01.25 | Growing of other tree and bush fruits and nuts | **Very High** - Dates, olives, almonds |
| 01.2 | 01.26 | Growing of oleaginous fruits | **Very High** - Olives for oil |
| 01.3 | 01.30 | Plant propagation | **High** - Nurseries, seedlings |
| 01.4 | 01.41 | Raising of cattle and buffaloes | **High** - Dairy, beef |
| 01.4 | 01.42 | Raising of horses and other equines | Low - Specialized |
| 01.4 | 01.43 | Raising of camels and camelids | Medium - Traditional, growing |
| 01.4 | 01.44 | Raising of sheep and goats | **Very High** - Red meat, dairy |
| 01.4 | 01.45 | Raising of swine | Not Applicable - Religious prohibition |
| 01.4 | 01.46 | Raising of poultry | **Very High** - Eggs, broilers |
| 01.4 | 01.47 | Raising of other animals | Medium - Bees, rabbits |
| 01.5 | 01.50 | Mixed farming | **Very High** - Common SME model |
| 01.6 | 01.61 | Support activities for crop production | **High** - Agri-services |
| 01.6 | 01.62 | Support activities for animal production | **High** - Veterinary, AI services |
| 01.6 | 01.63 | Post-harvest crop activities | **High** - Sorting, packing |
| 01.6 | 01.64 | Seed processing for propagation | **High** - Certified seeds |

**Division 03 - Fishing and Aquaculture:**

| ISIC Group | ISIC Class | Description | SME Relevance in MENA |
|------------|------------|-------------|----------------------|
| 03.1 | 03.11 | Marine fishing | Medium - Traditional fisheries |
| 03.1 | 03.12 | Freshwater fishing | Low - Limited water bodies |
| 03.2 | 03.21 | Marine aquaculture | **High** - Growing rapidly (Egypt, Saudi) |
| 03.2 | 03.22 | Freshwater aquaculture | **Very High** - Tilapia, carp (Egypt) |

## 1.2 Value Chain Position

```
┌─────────────────────────────────────────────────────────────────────────────────────┐
│                    AGRICULTURE & AGRIBUSINESS VALUE CHAIN                            │
│                          (Water-Scarcity Context)                                    │
├─────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                      │
│  INPUT SUPPLY          PRIMARY PRODUCTION          POST-HARVEST/PROCESSING          │
│  (Upstream)            (SME Core Focus)            (Downstream/Linkages)            │
│                                                                                      │
│  ┌─────────────────┐   ┌─────────────────────┐   ┌─────────────────────┐            │
│  │ Seeds &         │   │ CROP PRODUCTION     │   │ Sorting &           │            │
│  │ Seedlings       │──►│ • Field crops       │──►│ Grading             │            │
│  │ (Local/Import)  │   │ • Vegetables        │   │ (Pack-houses)       │            │
│  └─────────────────┘   │ • Fruits            │   └─────────┬───────────┘            │
│                        │ • Tree crops        │             │                        │
│  ┌─────────────────┐   │   (Dates, Olives)   │   ┌─────────▼───────────┐            │
│  │ Fertilizers &   │──►│                     │   │ Cold Chain &        │            │
│  │ Agrochemicals   │   └─────────┬───────────┘   │ Storage             │────►       │
│  │ (60% imported)  │             │               │ (Limited in MENA)   │            │
│  └─────────────────┘             │               └─────────┬───────────┘            │
│                                  │                         │                        │
│  ┌─────────────────┐             │               ┌─────────▼───────────┐            │
│  │ Water &         │             │               │ Food Processing     │            │
│  │ Irrigation      │─────────────┤               │ (Linked Sector)     │            │
│  │ (CRITICAL)      │             │               │ • Juices, oils      │            │
│  └─────────────────┘             │               │ • Dairy products    │            │
│                                  │               │ • Preserved foods   │            │
│  ┌─────────────────┐   ┌─────────▼───────────┐   └─────────────────────┘            │
│  │ Feed &          │   │ LIVESTOCK           │                                      │
│  │ Nutrition       │──►│ • Poultry           │──►┌─────────────────────┐            │
│  │ (High import    │   │ • Dairy cattle      │   │ Slaughter &         │            │
│  │  dependency)    │   │ • Sheep/Goats       │   │ Processing          │            │
│  └─────────────────┘   │ • Aquaculture       │   │ (Abattoirs)         │            │
│                        └─────────────────────┘   └─────────────────────┘            │
│  ┌─────────────────┐                                                                │
│  │ Machinery &     │                             ┌─────────────────────┐            │
│  │ Equipment       │─────────────────────────────►│ MARKETS             │            │
│  │ (Service model) │   ┌─────────────────────┐   │ • Local wholesale   │            │
│  └─────────────────┘   │ AGRI-SERVICES       │──►│ • Retail chains     │            │
│                        │ • Extension         │   │ • Export (EU, Gulf) │            │
│  ┌─────────────────┐   │ • Veterinary        │   │ • Food service      │            │
│  │ Technology &    │──►│ • Mechanization     │   └─────────────────────┘            │
│  │ Digital Tools   │   │ • Testing/Labs      │                                      │
│  │ (Emerging)      │   └─────────────────────┘                                      │
│  └─────────────────┘                                                                │
│                                                                                      │
│  ═══════════════════════════════════════════════════════════════════════════════   │
│  CRITICAL ENABLER: WATER MANAGEMENT - Scarcity shapes all decisions in MENA Agri    │
│  ═══════════════════════════════════════════════════════════════════════════════   │
│                                                                                      │
│  SME FOCUS AREAS:                                                                   │
│  ★ Primary Production (Crops, Livestock, Aquaculture)                              │
│  ★ Agri-Services (Extension, Veterinary, Mechanization)                            │
│  ★ Post-Harvest (Sorting, Packing, Limited Processing)                             │
│  ★ Protected Agriculture (Greenhouses, Vertical Farms)                             │
│                                                                                      │
│  FORWARD LINKAGES:                                                                  │
│  • Food & Beverage Manufacturing (Heavy)                                            │
│  • Chemicals & Fertilizers (Medium)                                                 │
│  • Logistics & Cold Chain (Heavy)                                                   │
│  • Retail & Distribution (Medium)                                                   │
│                                                                                      │
│  BACKWARD LINKAGES:                                                                 │
│  • Chemicals (Fertilizers, Pesticides)                                              │
│  • Pharmaceuticals (Veterinary)                                                     │
│  • Machinery & Equipment                                                            │
│  • Water & Utilities                                                                │
└─────────────────────────────────────────────────────────────────────────────────────┘
```

**Primary SME Positions in MENA Agriculture:**

| Position | Description | Typical SME Size | Revenue Range (USD) |
|----------|-------------|------------------|---------------------|
| **Small-Scale Farmer** | Traditional family farms, mixed crops | 3-10 workers | $25K-$200K |
| **Medium Commercial Farm** | Specialized crop/livestock production | 10-50 workers | $200K-$2M |
| **Protected Agriculture** | Greenhouse/vertical farming operations | 5-30 workers | $100K-$1.5M |
| **Poultry Operation** | Broiler or layer farms | 10-75 workers | $300K-$5M |
| **Dairy Farm** | Cattle/goat dairy operations | 8-40 workers | $200K-$3M |
| **Aquaculture Farm** | Fish/shrimp production | 10-50 workers | $150K-$2M |
| **Agri-Services** | Extension, veterinary, mechanization | 5-25 workers | $75K-$800K |
| **Pack-house/Sorting** | Post-harvest handling | 15-100 workers | $200K-$3M |
| **Nursery/Seedling** | Plant propagation business | 5-30 workers | $100K-$1M |

## 1.3 Subsector Taxonomy

```
AGRICULTURE & AGRIBUSINESS
│
├── CROP PRODUCTION
│   ├── Vegetable Production [veg_production]
│   │   ├── Open-field vegetables
│   │   ├── Protected/greenhouse vegetables
│   │   └── Organic vegetable production
│   │
│   ├── Fruit Production [fruit_production]
│   │   ├── Citrus (oranges, lemons, grapefruit)
│   │   ├── Stone fruits (peaches, apricots)
│   │   ├── Tropical fruits (mangoes, bananas)
│   │   └── Table grapes
│   │
│   ├── Field Crops [field_crops]
│   │   ├── Cereals (wheat, barley, maize)
│   │   ├── Legumes (lentils, chickpeas, fava beans)
│   │   ├── Oil seeds (sesame, sunflower)
│   │   └── Industrial crops (cotton, sugar beet)
│   │
│   ├── Date Production [date_production]
│   │   ├── Premium varieties (Medjool, Deglet Noor)
│   │   ├── Commercial varieties
│   │   └── Organic dates
│   │
│   └── Olive & Tree Crops [olive_tree_crops]
│       ├── Olives (oil, table)
│       ├── Almonds and nuts
│       └── Figs and pomegranates
│
├── LIVESTOCK PRODUCTION
│   ├── Poultry [poultry]
│   │   ├── Broiler production
│   │   ├── Layer/egg production
│   │   ├── Breeder farms
│   │   └── Turkey and other poultry
│   │
│   ├── Dairy [dairy]
│   │   ├── Cattle dairy
│   │   ├── Goat/sheep dairy
│   │   └── Buffalo dairy (Egypt)
│   │
│   ├── Red Meat [red_meat]
│   │   ├── Sheep production
│   │   ├── Goat production
│   │   ├── Cattle fattening
│   │   └── Camel production
│   │
│   └── Other Livestock [other_livestock]
│       ├── Beekeeping/apiculture
│       ├── Rabbit production
│       └── Ostrich farming
│
├── AQUACULTURE [aquaculture]
│   ├── Freshwater aquaculture
│   │   ├── Tilapia production
│   │   ├── Catfish production
│   │   └── Carp production
│   │
│   ├── Marine aquaculture
│   │   ├── Sea bream/bass
│   │   ├── Shrimp farming
│   │   └── Shellfish
│   │
│   └── Integrated systems
│       ├── Aquaponics
│       └── Rice-fish systems
│
├── PROTECTED AGRICULTURE [protected_ag]
│   ├── Greenhouses
│   │   ├── Low-tech tunnels
│   │   ├── Climate-controlled greenhouses
│   │   └── High-tech Dutch-style
│   │
│   └── Vertical Farming
│       ├── Indoor CEA facilities
│       └── Urban agriculture
│
└── AGRI-SERVICES [agri_services]
    ├── Extension & Advisory
    │   ├── Agronomic consulting
    │   └── Digital agriculture services
    │
    ├── Veterinary Services
    │   ├── Large animal practice
    │   ├── Poultry health
    │   └── Aquatic health
    │
    ├── Mechanization Services
    │   ├── Contract farming
    │   ├── Harvesting services
    │   └── Land preparation
    │
    ├── Testing & Quality
    │   ├── Soil testing
    │   ├── Water analysis
    │   └── Residue testing
    │
    └── Input Supply & Distribution
        ├── Seed/seedling retailers
        ├── Fertilizer distributors
        └── Agricultural equipment dealers
```

## 1.4 Subsector Definitions

### 1.4.1 Vegetable Production

```json
{
  "subsector_id": "veg_production",
  "name": "Vegetable Production",
  "name_ar": "إنتاج الخضروات",
  "isic_class": "01.13",
  "description": "Growing of vegetables and melons, roots and tubers in open fields or protected environments",
  "typical_products": ["tomatoes", "cucumbers", "peppers", "potatoes", "onions", "lettuce", "carrots", "eggplant", "squash", "watermelon"],
  "mena_specifics": {
    "key_producing_countries": ["EG", "MA", "JO", "TN", "SA"],
    "export_commodities": ["tomatoes", "potatoes", "onions", "peppers"],
    "water_intensity": "high",
    "seasonality": "year-round with peak seasons",
    "labor_intensity": "high",
    "typical_farm_size_hectares": {
      "small": "0.5-5",
      "medium": "5-50",
      "large": "50-500"
    }
  },
  "sme_profile": {
    "typical_employees": "5-50",
    "typical_revenue_usd": "50000-2000000",
    "growth_potential": "high",
    "export_orientation": "medium-high"
  }
}
```

### 1.4.2 Fruit Production

```json
{
  "subsector_id": "fruit_production",
  "name": "Fruit Production",
  "name_ar": "إنتاج الفاكهة",
  "isic_class": "01.21-01.25",
  "description": "Growing of tree fruits, grapes, and tropical fruits for fresh consumption and processing",
  "typical_products": ["citrus (oranges, lemons)", "grapes", "mangoes", "apples", "peaches", "apricots", "bananas", "pomegranates", "figs"],
  "mena_specifics": {
    "key_producing_countries": ["EG", "MA", "TN", "JO", "LB", "SA"],
    "export_commodities": ["citrus", "grapes", "mangoes", "pomegranates"],
    "water_intensity": "high (perennial crops)",
    "seasonality": "seasonal with storage extension",
    "labor_intensity": "high (especially harvest)",
    "typical_orchard_size_hectares": {
      "small": "1-10",
      "medium": "10-100",
      "large": "100-1000"
    }
  },
  "sme_profile": {
    "typical_employees": "5-60",
    "typical_revenue_usd": "75000-3000000",
    "growth_potential": "high",
    "export_orientation": "high"
  }
}
```

### 1.4.3 Poultry

```json
{
  "subsector_id": "poultry",
  "name": "Poultry Production",
  "name_ar": "إنتاج الدواجن",
  "isic_class": "01.46",
  "description": "Raising of poultry for meat (broilers) and eggs (layers), including breeder operations",
  "typical_products": ["broiler chickens", "table eggs", "day-old chicks", "parent stock"],
  "mena_specifics": {
    "key_producing_countries": ["EG", "SA", "AE", "MA", "JO"],
    "integration_level": "high (vertical integration common)",
    "feed_dependency": "very high (70-80% imported)",
    "biosecurity_importance": "critical",
    "typical_farm_capacity": {
      "small": "5000-20000 birds",
      "medium": "20000-100000 birds",
      "large": "100000-500000 birds"
    }
  },
  "sme_profile": {
    "typical_employees": "10-75",
    "typical_revenue_usd": "300000-5000000",
    "growth_potential": "high",
    "export_orientation": "low-medium"
  }
}
```

### 1.4.4 Dairy

```json
{
  "subsector_id": "dairy",
  "name": "Dairy Production",
  "name_ar": "إنتاج الألبان",
  "isic_class": "01.41, 01.44",
  "description": "Production of raw milk from cattle, goats, sheep, and buffaloes for fluid milk and dairy processing",
  "typical_products": ["raw milk", "yogurt (on-farm)", "cheese (artisanal)", "ghee/butter"],
  "mena_specifics": {
    "key_producing_countries": ["EG", "SA", "MA", "TN", "JO"],
    "herd_composition": "mixed (cattle, goat, sheep, buffalo)",
    "feed_cost_percentage": "60-70%",
    "cooling_chain_challenge": "critical",
    "typical_herd_size": {
      "small": "5-30 animals",
      "medium": "30-200 animals",
      "large": "200-2000 animals"
    }
  },
  "sme_profile": {
    "typical_employees": "8-40",
    "typical_revenue_usd": "200000-3000000",
    "growth_potential": "high",
    "export_orientation": "low"
  }
}
```

### 1.4.5 Date Production

```json
{
  "subsector_id": "date_production",
  "name": "Date Production",
  "name_ar": "إنتاج التمور",
  "isic_class": "01.25",
  "description": "Cultivation of date palms for fresh and processed dates, a strategic MENA crop",
  "typical_products": ["fresh dates", "dried dates", "date syrup", "date paste", "date sugar"],
  "mena_specifics": {
    "key_producing_countries": ["EG", "SA", "AE", "IQ", "DZ", "TN", "MA", "OM"],
    "premium_varieties": ["Medjool", "Deglet Noor", "Barhi", "Khudri", "Ajwa"],
    "global_market_share": "85%+ of world production",
    "water_efficiency": "high (drought tolerant)",
    "seasonality": "harvest August-November",
    "typical_farm_size_palms": {
      "small": "50-500 palms",
      "medium": "500-5000 palms",
      "large": "5000-50000 palms"
    }
  },
  "sme_profile": {
    "typical_employees": "5-40",
    "typical_revenue_usd": "50000-2000000",
    "growth_potential": "very high",
    "export_orientation": "very high"
  }
}
```

### 1.4.6 Olive & Tree Crops

```json
{
  "subsector_id": "olive_tree_crops",
  "name": "Olive & Tree Crops",
  "name_ar": "الزيتون والمحاصيل الشجرية",
  "isic_class": "01.26, 01.25",
  "description": "Cultivation of olives for oil and table consumption, plus almonds, figs, and other tree crops",
  "typical_products": ["olive oil (EVOO)", "table olives", "almonds", "figs", "pistachios", "carob"],
  "mena_specifics": {
    "key_producing_countries": ["TN", "MA", "EG", "JO", "LB", "SY", "PS"],
    "olive_oil_types": ["extra virgin", "virgin", "lampante", "refined"],
    "mediterranean_heritage": "ancient cultivation traditions",
    "alternate_bearing": "high (affects planning)",
    "typical_grove_size_hectares": {
      "small": "1-10",
      "medium": "10-100",
      "large": "100-1000"
    }
  },
  "sme_profile": {
    "typical_employees": "5-35",
    "typical_revenue_usd": "50000-1500000",
    "growth_potential": "high",
    "export_orientation": "very high (especially TN, MA)"
  }
}
```

### 1.4.7 Aquaculture

```json
{
  "subsector_id": "aquaculture",
  "name": "Aquaculture",
  "name_ar": "الاستزراع السمكي",
  "isic_class": "03.21, 03.22",
  "description": "Farming of fish, shrimp, and other aquatic organisms in freshwater and marine environments",
  "typical_products": ["tilapia", "mullet", "carp", "sea bream", "sea bass", "shrimp", "catfish"],
  "mena_specifics": {
    "key_producing_countries": ["EG", "SA", "AE", "IR", "IQ"],
    "egypt_dominance": "95%+ of MENA freshwater production",
    "water_source_constraints": "critical consideration",
    "feed_dependency": "very high (mostly imported)",
    "typical_farm_size": {
      "small": "1-5 hectares / 5-20 cages",
      "medium": "5-50 hectares / 20-100 cages",
      "large": "50+ hectares / 100+ cages"
    }
  },
  "sme_profile": {
    "typical_employees": "10-50",
    "typical_revenue_usd": "150000-2000000",
    "growth_potential": "very high",
    "export_orientation": "medium"
  }
}
```

### 1.4.8 Protected Agriculture

```json
{
  "subsector_id": "protected_ag",
  "name": "Protected Agriculture / Greenhouses",
  "name_ar": "الزراعة المحمية / البيوت المحمية",
  "isic_class": "01.13, 01.30",
  "description": "Crop production under controlled or semi-controlled environments including greenhouses, tunnels, and vertical farms",
  "typical_products": ["tomatoes", "cucumbers", "peppers", "lettuce", "herbs", "strawberries", "flowers"],
  "mena_specifics": {
    "key_countries": ["SA", "AE", "JO", "EG", "MA", "KW", "QA"],
    "technology_spectrum": "low-tech tunnels to high-tech CEA",
    "water_savings": "up to 90% vs open field",
    "climate_adaptation": "critical for Gulf states",
    "investment_per_hectare_usd": {
      "low_tech_tunnel": "10000-30000",
      "medium_tech_greenhouse": "50000-150000",
      "high_tech_climate_controlled": "500000-2000000",
      "vertical_farm": "1000000-5000000"
    }
  },
  "sme_profile": {
    "typical_employees": "5-30",
    "typical_revenue_usd": "100000-1500000",
    "growth_potential": "very high",
    "export_orientation": "medium-high"
  }
}
```

### 1.4.9 Red Meat / Livestock

```json
{
  "subsector_id": "red_meat",
  "name": "Red Meat / Livestock",
  "name_ar": "اللحوم الحمراء / الثروة الحيوانية",
  "isic_class": "01.41, 01.43, 01.44",
  "description": "Raising of sheep, goats, cattle, and camels for meat production",
  "typical_products": ["lamb/mutton", "goat meat", "beef", "camel meat"],
  "mena_specifics": {
    "key_countries": ["EG", "SA", "MA", "SD", "DZ", "TN", "JO"],
    "cultural_significance": "very high (Eid, celebrations)",
    "feed_import_dependency": "high",
    "extensive_vs_intensive": "mixed, trending intensive",
    "typical_herd_size": {
      "small": "10-50 animals",
      "medium": "50-300 animals",
      "large": "300-2000 animals"
    }
  },
  "sme_profile": {
    "typical_employees": "3-25",
    "typical_revenue_usd": "100000-2000000",
    "growth_potential": "medium",
    "export_orientation": "low (mostly domestic)"
  }
}
```

### 1.4.10 Field Crops

```json
{
  "subsector_id": "field_crops",
  "name": "Field Crops / Grains",
  "name_ar": "المحاصيل الحقلية / الحبوب",
  "isic_class": "01.11",
  "description": "Production of cereals, legumes, and industrial crops",
  "typical_products": ["wheat", "barley", "maize", "lentils", "chickpeas", "fava beans", "cotton", "sesame"],
  "mena_specifics": {
    "key_countries": ["EG", "MA", "TN", "SA", "IQ", "SY", "DZ"],
    "strategic_importance": "food security priority",
    "import_gap": "significant (MENA imports 50%+ of wheat)",
    "water_constraints": "major limiting factor",
    "typical_farm_size_hectares": {
      "small": "1-10",
      "medium": "10-100",
      "large": "100-1000"
    }
  },
  "sme_profile": {
    "typical_employees": "3-20",
    "typical_revenue_usd": "25000-500000",
    "growth_potential": "medium",
    "export_orientation": "low"
  }
}
```

### 1.4.11 Agri-Services

```json
{
  "subsector_id": "agri_services",
  "name": "Agricultural Services",
  "name_ar": "الخدمات الزراعية",
  "isic_class": "01.61, 01.62, 01.63, 01.64",
  "description": "Support activities including extension, veterinary services, mechanization, and post-harvest handling",
  "typical_services": ["agronomic advisory", "veterinary care", "AI services", "contract harvesting", "soil testing", "irrigation design", "machinery rental"],
  "mena_specifics": {
    "market_maturity": "emerging (growing private sector)",
    "traditional_providers": "government extension services",
    "digital_disruption": "agri-tech startups emerging",
    "key_opportunities": "mechanization services, precision ag"
  },
  "sme_profile": {
    "typical_employees": "5-25",
    "typical_revenue_usd": "75000-800000",
    "growth_potential": "very high",
    "export_orientation": "low (local service)"
  }
}
```

## 1.5 Adjacent Sectors

| Sector | Relationship | Relevance Score | Key Linkages |
|--------|--------------|-----------------|--------------|
| **Food & Beverage Manufacturing** | Customer | 0.95 | Raw material supplier; processing of ag outputs |
| **Chemicals & Plastics** | Supplier | 0.85 | Fertilizers, pesticides, packaging materials |
| **Logistics & Transportation** | Complementary | 0.80 | Cold chain, distribution, export logistics |
| **Pharmaceuticals (Veterinary)** | Supplier | 0.75 | Animal health products, vaccines |
| **Retail & Distribution** | Customer | 0.70 | Fresh produce sales channel |
| **Water & Utilities** | Supplier (Critical) | 0.90 | Irrigation water, energy for pumping |
| **Construction** | Complementary | 0.50 | Farm structures, greenhouses, storage |
| **Financial Services** | Complementary | 0.65 | Agricultural finance, crop insurance |
| **Tech / Digital Services** | Complementary | 0.60 | Precision agriculture, farm management |

---

# Dimension 2: Financial Benchmarks

## 2.1 Revenue Benchmarks

### Sector-Wide Revenue Distribution

| Percentile | Annual Revenue (USD) | Employees | Description |
|------------|---------------------|-----------|-------------|
| 10th | $30,000 | 3-5 | Subsistence/small holder |
| 25th | $100,000 | 5-10 | Small commercial |
| Median | $350,000 | 15-25 | Medium commercial |
| 75th | $1,200,000 | 40-75 | Large commercial |
| 90th | $4,500,000 | 100-150 | Industrial scale |

### Revenue per Employee by Subsector

| Subsector | Low | Median | High | Notes |
|-----------|-----|--------|------|-------|
| Vegetable Production | $15,000 | $35,000 | $70,000 | Labor intensive |
| Fruit Production | $20,000 | $45,000 | $90,000 | Seasonal variations |
| Poultry | $40,000 | $75,000 | $120,000 | High automation potential |
| Dairy | $25,000 | $50,000 | $85,000 | Capital intensive |
| Date Production | $15,000 | $40,000 | $80,000 | Highly seasonal harvest |
| Olive/Tree Crops | $12,000 | $30,000 | $60,000 | Alternate bearing impact |
| Aquaculture | $25,000 | $55,000 | $100,000 | Growing efficiency |
| Protected Agriculture | $35,000 | $65,000 | $120,000 | Capital/tech intensive |
| Red Meat | $30,000 | $60,000 | $100,000 | Feed cost dominant |
| Field Crops | $10,000 | $25,000 | $50,000 | Mechanized, lower labor |
| Agri-Services | $20,000 | $40,000 | $80,000 | Service-based model |

### Revenue Growth Rates (5-Year CAGR)

| Subsector | Conservative | Expected | Optimistic |
|-----------|--------------|----------|------------|
| Vegetable Production | 3% | 6% | 10% |
| Fruit Production | 4% | 7% | 12% |
| Poultry | 5% | 8% | 12% |
| Dairy | 4% | 7% | 11% |
| Date Production | 8% | 12% | 18% |
| Olive/Tree Crops | 3% | 6% | 10% |
| Aquaculture | 10% | 15% | 22% |
| Protected Agriculture | 12% | 18% | 28% |
| Red Meat | 2% | 5% | 8% |
| Field Crops | 1% | 3% | 5% |
| Agri-Services | 8% | 14% | 22% |

## 2.2 Profitability Metrics

### Gross Margin Benchmarks

| Subsector | Poor (<) | Acceptable | Good | Excellent (>) |
|-----------|----------|------------|------|---------------|
| Vegetable Production | 20% | 25-35% | 35-45% | 45% |
| Fruit Production | 25% | 30-40% | 40-50% | 50% |
| Poultry - Broilers | 8% | 12-18% | 18-25% | 25% |
| Poultry - Layers | 15% | 20-30% | 30-40% | 40% |
| Dairy | 15% | 20-30% | 30-40% | 40% |
| Date Production | 30% | 40-55% | 55-70% | 70% |
| Olive Oil (Premium) | 25% | 35-50% | 50-65% | 65% |
| Aquaculture | 15% | 22-32% | 32-42% | 42% |
| Protected Agriculture | 25% | 35-45% | 45-55% | 55% |
| Red Meat | 10% | 15-25% | 25-35% | 35% |
| Field Crops | 15% | 20-30% | 30-40% | 40% |
| Agri-Services | 30% | 40-55% | 55-70% | 70% |

### Operating Margin (EBITDA) Benchmarks

| Subsector | Below Average (<) | Average | Above Average | Top Quartile (>) |
|-----------|-------------------|---------|---------------|------------------|
| Vegetable Production | 8% | 12-18% | 18-25% | 25% |
| Fruit Production | 10% | 15-22% | 22-30% | 30% |
| Poultry | 5% | 8-14% | 14-20% | 20% |
| Dairy | 8% | 12-18% | 18-25% | 25% |
| Date Production | 18% | 25-35% | 35-45% | 45% |
| Olive/Tree Crops | 12% | 18-28% | 28-38% | 38% |
| Aquaculture | 10% | 15-22% | 22-30% | 30% |
| Protected Agriculture | 12% | 18-26% | 26-35% | 35% |
| Red Meat | 5% | 8-15% | 15-22% | 22% |
| Field Crops | 8% | 12-20% | 20-28% | 28% |
| Agri-Services | 15% | 22-32% | 32-45% | 45% |

### Net Profit Margin Benchmarks

| Subsector | Survival | Sustainable | Good | Excellent |
|-----------|----------|-------------|------|-----------|
| Vegetable Production | 2-5% | 5-10% | 10-15% | >15% |
| Fruit Production | 3-6% | 6-12% | 12-18% | >18% |
| Poultry | 1-3% | 3-7% | 7-12% | >12% |
| Dairy | 2-5% | 5-10% | 10-15% | >15% |
| Date Production | 8-12% | 12-20% | 20-30% | >30% |
| Olive/Tree Crops | 5-10% | 10-18% | 18-25% | >25% |
| Aquaculture | 3-7% | 7-12% | 12-18% | >18% |
| Protected Agriculture | 5-10% | 10-16% | 16-22% | >22% |
| Red Meat | 1-3% | 3-8% | 8-12% | >12% |
| Field Crops | 3-6% | 6-12% | 12-18% | >18% |
| Agri-Services | 8-12% | 12-20% | 20-30% | >30% |

## 2.3 Cost Structure Analysis

### Typical Cost Breakdown by Subsector

**Crop Production (Vegetables/Fruits):**

| Cost Category | % of Revenue | Variability | Key Drivers |
|---------------|--------------|-------------|-------------|
| Seeds/Seedlings | 3-8% | Medium | Variety, source |
| Fertilizers | 8-15% | High | Input prices, soil |
| Pesticides/Chemicals | 3-8% | Medium | Pest pressure |
| Water/Irrigation | 10-20% | High | Source, method |
| Labor | 25-40% | Low | Seasonality |
| Energy | 3-8% | Medium | Pumping, cooling |
| Packaging | 5-12% | Medium | Market destination |
| Transport | 5-10% | Medium | Distance, cold chain |
| Land Lease/Depreciation | 5-10% | Low | Location |
| **Total COGS** | **67-80%** | | |

**Poultry Production:**

| Cost Category | % of Revenue | Variability | Key Drivers |
|---------------|--------------|-------------|-------------|
| Feed | 55-70% | Very High | Commodity prices, import |
| Day-Old Chicks | 8-12% | Medium | Genetics, source |
| Veterinary/Medicine | 3-6% | Medium | Biosecurity, disease |
| Labor | 5-10% | Low | Automation level |
| Energy | 5-10% | Medium | Climate control |
| Utilities/Water | 2-4% | Low | |
| Depreciation | 3-5% | Low | Equipment, housing |
| **Total COGS** | **82-92%** | | |

**Dairy Production:**

| Cost Category | % of Revenue | Variability | Key Drivers |
|---------------|--------------|-------------|-------------|
| Feed/Fodder | 55-65% | Very High | Local vs imported |
| Labor | 12-18% | Low | Herd size, milking system |
| Veterinary/AI | 3-6% | Medium | Herd health |
| Energy | 3-5% | Medium | Cooling, milking |
| Replacement Animals | 5-10% | Medium | Culling rate |
| Depreciation | 3-6% | Low | Equipment, animals |
| **Total COGS** | **75-85%** | | |

**Aquaculture:**

| Cost Category | % of Revenue | Variability | Key Drivers |
|---------------|--------------|-------------|-------------|
| Feed | 45-60% | Very High | FCR, import prices |
| Fingerlings/Fry | 8-15% | Medium | Species, quality |
| Labor | 8-15% | Low | Intensity of system |
| Energy | 5-12% | High | Aeration, pumping |
| Veterinary/Treatment | 2-5% | Medium | Disease management |
| Harvest/Processing | 5-10% | Medium | Market format |
| Depreciation | 5-8% | Low | Infrastructure |
| **Total COGS** | **68-85%** | | |

## 2.4 Working Capital Metrics

### Cash Conversion Cycle by Subsector

| Subsector | DSO (Days) | DIO (Days) | DPO (Days) | CCC (Days) | Notes |
|-----------|------------|------------|------------|------------|-------|
| Vegetable Production | 15-30 | 30-60 | 20-40 | 25-50 | Quick turnover |
| Fruit Production | 20-45 | 60-120 | 30-60 | 50-105 | Seasonal, storage |
| Poultry - Broilers | 10-20 | 45-60 | 30-45 | 25-35 | Fast cycle |
| Poultry - Layers | 15-30 | 7-14 | 20-40 | 2-4 | Daily egg sales |
| Dairy | 7-20 | 15-30 | 15-30 | 7-20 | Very quick |
| Date Production | 30-90 | 120-240 | 30-60 | 120-270 | Long storage |
| Olive/Tree Crops | 30-60 | 90-180 | 30-60 | 90-180 | Seasonal |
| Aquaculture | 15-30 | 120-270 | 30-60 | 105-240 | Long grow-out |
| Protected Ag | 10-25 | 30-60 | 20-40 | 20-45 | Continuous |
| Red Meat | 20-45 | 180-365 | 30-60 | 170-350 | Long cycle |
| Field Crops | 30-60 | 60-180 | 30-60 | 60-180 | Seasonal |
| Agri-Services | 30-45 | 15-30 | 30-45 | 15-30 | Service model |

### Working Capital as % of Revenue

| Subsector | Minimum | Typical | High | Notes |
|-----------|---------|---------|------|-------|
| Vegetable Production | 15% | 25% | 40% | Input financing needs |
| Fruit Production | 20% | 35% | 55% | Orchard establishment |
| Poultry | 20% | 30% | 45% | Feed inventory |
| Dairy | 15% | 25% | 40% | Herd value |
| Date Production | 25% | 40% | 60% | Storage, long sales |
| Aquaculture | 30% | 45% | 65% | Grow-out period |
| Protected Ag | 20% | 30% | 45% | Operating cycle |
| Red Meat | 35% | 50% | 70% | Long cycle |
| Field Crops | 20% | 35% | 50% | Seasonal |
| Agri-Services | 10% | 18% | 28% | Low inventory |

## 2.5 Capital Expenditure Norms

### Initial Investment by Subsector (Per Unit)

| Subsector | Unit | Low | Medium | High | Notes |
|-----------|------|-----|--------|------|-------|
| Vegetable Production | per hectare | $3,000 | $8,000 | $20,000 | Open field |
| Fruit Orchard | per hectare | $8,000 | $15,000 | $35,000 | Including establishment |
| Poultry - Broiler | per 10,000 birds | $30,000 | $60,000 | $120,000 | Housing + equipment |
| Poultry - Layer | per 10,000 birds | $80,000 | $150,000 | $250,000 | Cages + equipment |
| Dairy | per cow | $3,000 | $6,000 | $12,000 | Animal + facilities |
| Date Palm | per palm | $100 | $250 | $500 | Establishment |
| Aquaculture (Pond) | per hectare | $15,000 | $35,000 | $80,000 | Earthen ponds |
| Aquaculture (Cage) | per cage | $3,000 | $8,000 | $15,000 | Marine/reservoir |
| Greenhouse (Low-tech) | per hectare | $15,000 | $35,000 | $60,000 | Tunnel type |
| Greenhouse (Hi-tech) | per hectare | $200,000 | $500,000 | $1,500,000 | Climate controlled |
| Vertical Farm | per m² | $500 | $1,200 | $3,000 | Indoor CEA |

### Annual CapEx as % of Revenue (Maintenance + Growth)

| Subsector | Maintenance | Moderate Growth | Aggressive Growth |
|-----------|-------------|-----------------|-------------------|
| Vegetable Production | 3-5% | 8-12% | 15-25% |
| Fruit Production | 5-8% | 10-15% | 20-30% |
| Poultry | 5-8% | 12-18% | 20-30% |
| Dairy | 6-10% | 12-18% | 22-35% |
| Date Production | 3-5% | 8-12% | 15-20% |
| Aquaculture | 5-10% | 15-22% | 25-40% |
| Protected Ag | 8-12% | 15-25% | 30-50% |
| Field Crops | 4-6% | 8-12% | 15-20% |
| Agri-Services | 5-8% | 10-15% | 18-25% |

## 2.6 Financial Ratios

### Liquidity Ratios

| Ratio | Formula | Below Average | Average | Above Average | Sector Notes |
|-------|---------|---------------|---------|---------------|--------------|
| Current Ratio | CA/CL | <1.2 | 1.2-1.8 | 1.8-2.5 | Seasonal fluctuation |
| Quick Ratio | (CA-Inv)/CL | <0.6 | 0.6-1.0 | 1.0-1.5 | Biological assets |
| Cash Ratio | Cash/CL | <0.1 | 0.1-0.3 | 0.3-0.5 | Typically low |

### Leverage Ratios

| Ratio | Formula | Low Risk | Moderate | Elevated | High Risk |
|-------|---------|----------|----------|----------|-----------|
| Debt/Equity | Total Debt/Equity | <0.5 | 0.5-1.5 | 1.5-2.5 | >2.5 |
| Debt/EBITDA | Total Debt/EBITDA | <2.0 | 2.0-4.0 | 4.0-6.0 | >6.0 |
| Interest Coverage | EBIT/Interest | >5.0 | 3.0-5.0 | 1.5-3.0 | <1.5 |

### Efficiency Ratios

| Ratio | Formula | Poor | Average | Good | Excellent |
|-------|---------|------|---------|------|-----------|
| Asset Turnover | Revenue/Total Assets | <0.4 | 0.4-0.8 | 0.8-1.2 | >1.2 |
| Inventory Turnover | COGS/Avg Inventory | <3 | 3-6 | 6-12 | >12 |
| Fixed Asset Turnover | Revenue/Fixed Assets | <0.6 | 0.6-1.2 | 1.2-2.0 | >2.0 |

## 2.7 Valuation Multiples

### Revenue Multiples by Subsector

| Subsector | Distressed | Fair Value | Premium | Strategic |
|-----------|------------|------------|---------|-----------|
| Vegetable Production | 0.3-0.5x | 0.5-1.0x | 1.0-1.5x | 1.5-2.5x |
| Fruit Production | 0.5-0.8x | 0.8-1.5x | 1.5-2.5x | 2.5-4.0x |
| Poultry | 0.3-0.5x | 0.5-0.8x | 0.8-1.2x | 1.2-2.0x |
| Dairy | 0.4-0.6x | 0.6-1.0x | 1.0-1.5x | 1.5-2.5x |
| Date Production | 0.6-1.0x | 1.0-2.0x | 2.0-3.5x | 3.5-5.0x |
| Olive/Tree Crops | 0.5-0.8x | 0.8-1.5x | 1.5-2.5x | 2.5-4.0x |
| Aquaculture | 0.5-0.8x | 0.8-1.5x | 1.5-2.5x | 2.5-4.0x |
| Protected Ag | 0.8-1.2x | 1.2-2.0x | 2.0-3.5x | 3.5-6.0x |
| Agri-Services | 0.5-1.0x | 1.0-2.0x | 2.0-3.5x | 3.5-5.0x |

### EBITDA Multiples by Subsector

| Subsector | Distressed | Fair Value | Premium | Strategic |
|-----------|------------|------------|---------|-----------|
| Vegetable Production | 2-3x | 3-5x | 5-7x | 7-10x |
| Fruit Production | 3-4x | 4-7x | 7-10x | 10-14x |
| Poultry | 3-4x | 4-6x | 6-8x | 8-12x |
| Dairy | 3-5x | 5-7x | 7-10x | 10-14x |
| Date Production | 4-6x | 6-10x | 10-15x | 15-20x |
| Olive/Tree Crops | 4-6x | 6-9x | 9-13x | 13-18x |
| Aquaculture | 4-5x | 5-8x | 8-12x | 12-16x |
| Protected Ag | 5-7x | 7-10x | 10-15x | 15-22x |
| Agri-Services | 4-6x | 6-10x | 10-14x | 14-18x |

### Key Valuation Considerations for Agriculture

| Factor | Impact on Valuation | Notes |
|--------|---------------------|-------|
| Water Rights | +20-50% premium | Critical in MENA |
| Land Ownership vs Lease | +15-30% for owned | Security of tenure |
| Certifications (GlobalGAP, Organic) | +10-25% | Market access |
| Export Contracts | +15-30% | Revenue quality |
| Vertical Integration | +10-20% | Margin capture |
| Technology/Precision Ag | +10-25% | Efficiency premium |
| Key Person Risk | -15-30% | Founder dependency |
| Climate Vulnerability | -10-25% | Water, weather risks |

---

# Dimension 3: Operational KPIs

## 3.1 Production Efficiency Metrics

### Crop Production KPIs

| KPI | Unit | Poor | Average | Good | Excellent | Measurement |
|-----|------|------|---------|------|-----------|-------------|
| **Yield per Hectare** | | | | | | |
| Tomatoes (open field) | tons/ha | <40 | 40-60 | 60-80 | >80 | Annual |
| Tomatoes (greenhouse) | tons/ha | <150 | 150-250 | 250-400 | >400 | Annual |
| Cucumbers (greenhouse) | tons/ha | <100 | 100-180 | 180-280 | >280 | Annual |
| Potatoes | tons/ha | <20 | 20-30 | 30-40 | >40 | Per cycle |
| Citrus | tons/ha | <20 | 20-30 | 30-45 | >45 | Annual |
| Dates | kg/palm | <50 | 50-80 | 80-120 | >120 | Annual |
| Olives | tons/ha | <3 | 3-6 | 6-10 | >10 | Annual |
| **Land Utilization** | % | <60% | 60-75% | 75-90% | >90% | Annual |
| **Crop Cycle Efficiency** | cycles/year | <1.5 | 1.5-2.0 | 2.0-2.5 | >2.5 | Open field veg |
| **Post-Harvest Loss** | % | >25% | 15-25% | 8-15% | <8% | Farm to market |
| **First Grade Yield** | % | <50% | 50-65% | 65-80% | >80% | Export grade |

### Livestock Production KPIs

| KPI | Unit | Poor | Average | Good | Excellent | Subsector |
|-----|------|------|---------|------|-----------|-----------|
| **Poultry - Broilers** | | | | | | |
| Feed Conversion Ratio (FCR) | kg feed/kg gain | >2.0 | 1.8-2.0 | 1.6-1.8 | <1.6 | Critical |
| Mortality Rate | % | >6% | 4-6% | 2-4% | <2% | Flock health |
| Average Daily Gain | g/day | <50 | 50-60 | 60-70 | >70 | Growth |
| Days to Market Weight | days | >45 | 40-45 | 35-40 | <35 | Cycle time |
| **Poultry - Layers** | | | | | | |
| Hen-Day Production | % | <75% | 75-82% | 82-90% | >90% | Egg output |
| Eggs per Hen Housed | eggs/year | <280 | 280-310 | 310-340 | >340 | Productivity |
| Feed per Dozen Eggs | kg | >2.2 | 1.9-2.2 | 1.6-1.9 | <1.6 | Efficiency |
| **Dairy** | | | | | | |
| Milk Yield | liters/cow/day | <15 | 15-22 | 22-30 | >30 | Cattle |
| Milk Yield | liters/goat/day | <1.5 | 1.5-2.5 | 2.5-3.5 | >3.5 | Goats |
| Somatic Cell Count | cells/ml | >400K | 250-400K | 150-250K | <150K | Quality |
| Fat Content | % | <3.2% | 3.2-3.6% | 3.6-4.2% | >4.2% | Quality |
| Days Open | days | >150 | 120-150 | 90-120 | <90 | Reproduction |
| **Red Meat** | | | | | | |
| Average Daily Gain - Sheep | g/day | <150 | 150-200 | 200-280 | >280 | Fattening |
| Feed Conversion - Cattle | kg/kg | >10 | 8-10 | 6-8 | <6 | Feedlot |
| Lambing Rate | % | <100% | 100-130% | 130-160% | >160% | Reproduction |

### Aquaculture KPIs

| KPI | Unit | Poor | Average | Good | Excellent | Notes |
|-----|------|------|---------|------|-----------|-------|
| Feed Conversion Ratio (FCR) | | | | | | |
| Tilapia | ratio | >2.0 | 1.7-2.0 | 1.4-1.7 | <1.4 | |
| Sea Bream | ratio | >2.5 | 2.0-2.5 | 1.7-2.0 | <1.7 | |
| Shrimp | ratio | >2.0 | 1.6-2.0 | 1.3-1.6 | <1.3 | |
| **Survival Rate** | % | <70% | 70-80% | 80-90% | >90% | Critical |
| **Stocking Density** | | | | | | |
| Tilapia (ponds) | kg/m³ | <15 | 15-25 | 25-40 | >40 | Intensive |
| **Growth Rate** | g/day | | | | | |
| Tilapia | g/day | <2 | 2-3 | 3-4 | >4 | |
| **Cycle Time** | days | >200 | 180-200 | 150-180 | <150 | To market |

### Protected Agriculture KPIs

| KPI | Unit | Poor | Average | Good | Excellent | Notes |
|-----|------|------|---------|------|-----------|-------|
| **Yield** (greenhouse tomato) | kg/m² | <30 | 30-50 | 50-70 | >70 | Annual |
| **Water Use Efficiency** | kg/m³ | <15 | 15-25 | 25-40 | >40 | Critical MENA |
| **Energy per kg Product** | kWh/kg | >3 | 2-3 | 1-2 | <1 | Climate control |
| **Labor Productivity** | kg/hour | <5 | 5-10 | 10-18 | >18 | Automation |
| **Climate Uniformity** | CV % | >25% | 15-25% | 8-15% | <8% | Tech level |

## 3.2 Quality Metrics

### General Quality KPIs

| KPI | Formula | Target | Critical Threshold |
|-----|---------|--------|-------------------|
| Grade A/Export Quality | Grade A Output / Total Output | >75% | <50% concern |
| Customer Complaint Rate | Complaints / Deliveries | <2% | >5% action needed |
| Rejection Rate at Market | Rejected Qty / Delivered Qty | <5% | >10% problem |
| Certification Compliance | Audits Passed / Total Audits | 100% | <90% risk |
| Pesticide Residue Compliance | Samples Within MRL / Total | 100% | Any violation critical |

### Product-Specific Quality Standards

**Fresh Produce:**

| Quality Parameter | Unit | Minimum | Target | Premium |
|-------------------|------|---------|--------|---------|
| Brix (Sugars) - Tomato | °Brix | 4.0 | 5.0-6.0 | >6.5 |
| Brix - Citrus | °Brix | 10 | 11-13 | >14 |
| Size Uniformity | % within spec | 80% | 90% | >95% |
| Color Consistency | % conforming | 85% | 92% | >97% |
| Shelf Life Achieved | % of expected | 80% | 90% | >95% |
| Organic Matter (Soil) | % | 1% | 2-3% | >4% |

**Dairy Quality:**

| Parameter | Unit | Acceptable | Good | Premium |
|-----------|------|------------|------|---------|
| Total Bacterial Count | CFU/ml | <500,000 | <200,000 | <50,000 |
| Somatic Cell Count | cells/ml | <500,000 | <300,000 | <150,000 |
| Fat Content | % | 3.0-3.2 | 3.3-3.6 | >3.7 |
| Protein Content | % | 2.8-3.0 | 3.0-3.2 | >3.3 |
| Antibiotic Residue | | Zero | Zero | Zero |

## 3.3 Resource Utilization

### Water Efficiency (Critical for MENA)

| Crop/Activity | Water Use (m³/ton product) | Drip Irrigation | Flood/Furrow | Notes |
|---------------|---------------------------|-----------------|--------------|-------|
| Tomatoes | 70-100 | 50-70 | 150-250 | Drip essential |
| Citrus | 800-1200 | 600-900 | 1500-2500 | Annual total |
| Dates | 20-40 m³/palm/year | - | Traditional higher | Drought tolerant |
| Wheat | 1000-1500 | 800-1200 | 2000-3000 | Rainfed where possible |
| Poultry | 3-5 L/bird/day | N/A | N/A | Direct consumption |
| Dairy | 80-120 L/cow/day | N/A | N/A | Including wash |
| Aquaculture | 5-15 m³/kg fish | - | - | Recirculating saves |

### Water KPIs

| KPI | Unit | Poor | Average | Good | Excellent |
|-----|------|------|---------|------|-----------|
| Water Productivity | kg product/m³ | <8 | 8-15 | 15-25 | >25 |
| Irrigation Efficiency | % water to crop | <50% | 50-70% | 70-85% | >85% |
| Water Cost/Revenue | % | >15% | 10-15% | 5-10% | <5% |
| Recycled Water Use | % of total | 0% | 10-30% | 30-60% | >60% |

### Energy Efficiency

| Subsector | Energy Cost % Revenue | Poor | Average | Good | Excellent |
|-----------|----------------------|------|---------|------|-----------|
| Crop Production | % | >12% | 8-12% | 5-8% | <5% |
| Poultry | % | >8% | 5-8% | 3-5% | <3% |
| Dairy | % | >6% | 4-6% | 2-4% | <2% |
| Aquaculture | % | >15% | 10-15% | 6-10% | <6% |
| Protected Ag | % | >20% | 12-20% | 7-12% | <7% |

## 3.4 Productivity Metrics

### Labor Productivity by Subsector

| Subsector | Unit | Low | Medium | High | Best Practice |
|-----------|------|-----|--------|------|---------------|
| Vegetable Production | ha/FTE | 0.5-1.0 | 1.0-2.0 | 2.0-5.0 | 5-10 (mechanized) |
| Fruit Orchards | ha/FTE | 2-4 | 4-8 | 8-15 | 15-30 |
| Poultry (Broiler) | birds/FTE | 15,000 | 25,000 | 40,000 | 60,000+ |
| Dairy | cows/FTE | 10-15 | 15-30 | 30-50 | 50-100 |
| Aquaculture | tons/FTE | 5-10 | 10-20 | 20-40 | 40-80 |
| Greenhouses | m²/FTE | 500-1000 | 1000-2000 | 2000-4000 | 4000-8000 |

### Land Productivity

| KPI | Definition | How to Improve |
|-----|------------|----------------|
| Revenue per Hectare | Total Revenue / Cultivated Area | Crop selection, yields, prices |
| Gross Margin per Hectare | Gross Margin / Cultivated Area | Input efficiency, premium markets |
| Cropping Intensity | Total Cropped Area / Available Land | Multiple crops, relay planting |

### Asset Productivity

| KPI | Formula | Sector Benchmark |
|-----|---------|------------------|
| Output per Dollar Invested | Annual Revenue / Total Fixed Assets | 0.8-1.5x |
| Livestock Units per Hectare | LSU / Total Farm Area | 2-5 LSU/ha intensive |
| Equipment Utilization | Hours Used / Available Hours | >70% target |

## 3.5 Delivery Performance

### Supply Chain KPIs

| KPI | Definition | Target | Critical |
|-----|------------|--------|----------|
| On-Time Delivery | % deliveries on scheduled date | >95% | <85% |
| Order Fill Rate | % orders completely fulfilled | >98% | <90% |
| Cold Chain Integrity | % shipments within temp spec | 100% | <95% |
| Lead Time (Harvest to Delivery) | Hours/Days | <24-48h | >72h |
| Shrinkage in Transit | % volume loss | <3% | >8% |

### Traceability KPIs

| KPI | Definition | Target | Notes |
|-----|------------|--------|-------|
| Lot Traceability | % products traceable to farm/batch | 100% | Export requirement |
| Recall Response Time | Hours to identify affected product | <4 hours | Food safety |
| Documentation Accuracy | % records error-free | >99% | Audit ready |

---

# Dimension 4: Regulatory Landscape

## 4.1 Business Licenses & Permits

### Core Agricultural Licenses

| License Type | Issuing Authority | Requirements | Validity | Renewal |
|--------------|-------------------|--------------|----------|---------|
| **Farm Registration** | Ministry of Agriculture | Land documentation, activity description | Indefinite | Annual update |
| **Animal Production License** | Ministry of Agriculture + GOVS | Facility inspection, veterinary approval | 1-3 years | Pre-expiry |
| **Aquaculture License** | Fisheries Authority | Environmental assessment, water rights | 5-10 years | Application |
| **Water Extraction Permit** | Ministry of Water/Irrigation | Well registration, quota allocation | 1-5 years | Quota review |
| **Pesticide Application** | Plant Protection Authority | Operator certification | 2-3 years | Training |
| **Organic Certification** | Accredited Certifier | Full standards compliance | 1 year | Annual audit |
| **Export License** | Trade Ministry | Registration, phytosanitary capability | 1-2 years | Renewal |

### Facility-Specific Permits

| Facility Type | Key Permits Required | Time to Obtain | Typical Cost (USD) |
|---------------|---------------------|----------------|-------------------|
| Poultry Farm | Environmental, Veterinary, Building | 3-6 months | $1,000-5,000 |
| Dairy Farm | Veterinary, Milk Handling, Environmental | 2-4 months | $500-2,500 |
| Pack-house | Food Safety, Export, Municipality | 2-4 months | $1,000-3,000 |
| Greenhouse | Building, Agriculture, Environmental | 2-3 months | $500-2,000 |
| Slaughterhouse | Veterinary, Halal, Municipal | 6-12 months | $5,000-20,000 |
| Aquaculture Farm | Fisheries, Environmental, Water | 4-8 months | $2,000-10,000 |

## 4.2 Compliance Requirements

### Food Safety Compliance

| Standard | Applicability | Requirements | Audit Frequency |
|----------|---------------|--------------|-----------------|
| **HACCP** | All food handling | Hazard analysis, CCPs, documentation | Annual |
| **GlobalGAP** | Export to EU/retail | Farm management, traceability, welfare | Annual |
| **ISO 22000** | Processing facilities | Food safety management system | Annual |
| **BRC/IFS** | Retail suppliers | Comprehensive food safety | Annual |
| **Organic** | Organic producers | Input control, segregation, records | Annual |
| **Halal** | Meat producers | Slaughter requirements, certification | Variable |

### Environmental Compliance

| Requirement | Threshold | Penalty for Non-Compliance |
|-------------|-----------|---------------------------|
| Water Use Permit | >100 m³/day | License suspension |
| Waste Discharge | Any discharge to water | Heavy fines, closure |
| Pesticide Storage | Any quantity | Inspection failures |
| Air Emissions (Poultry) | >50,000 birds | EIA required |
| Land Use Change | Agricultural to other | Permit required |

### Labor Compliance

| Requirement | Standard | Common Violations |
|-------------|----------|-------------------|
| Minimum Wage | Country-specific | Seasonal worker underpayment |
| Working Hours | 48 hrs/week standard | Harvest season overtime |
| Safety Equipment | PPE for agrochemicals | Inadequate provision |
| Worker Housing | Basic standards | Migrant worker conditions |
| Child Labor | Prohibited under 15 | Family farm exceptions |

## 4.3 Industry Certifications

### Quality & Safety Certifications

| Certification | Purpose | Market Access | Cost (USD/year) | Audit Requirements |
|---------------|---------|---------------|-----------------|-------------------|
| **GlobalGAP** | Farm assurance | EU retailers, exports | $1,500-5,000 | Annual third-party |
| **Organic (EU/USDA)** | Organic claims | Premium markets | $2,000-8,000 | Annual + spot checks |
| **Fair Trade** | Social certification | Specialty markets | $3,000-10,000 | Annual |
| **Rainforest Alliance** | Sustainability | Global brands | $2,000-6,000 | Annual |
| **ISO 22000** | Food safety management | B2B credibility | $3,000-10,000 | Surveillance audits |
| **BRC Global** | UK retail requirement | UK supermarkets | $4,000-12,000 | Annual |

### Export-Specific Certifications

| Certification | Required For | Issuing Body | Key Requirements |
|---------------|--------------|--------------|------------------|
| **Phytosanitary Certificate** | All plant exports | National Plant Protection | Pest-free inspection |
| **Health Certificate** | Animal products | Veterinary Authority | Health status verification |
| **Halal Certificate** | Meat to Muslim markets | Approved Islamic bodies | Slaughter compliance |
| **Certificate of Origin** | Trade agreements | Chamber of Commerce | Production evidence |
| **Organic Export** | Organic products | Accredited certifier | Organic compliance |

### Emerging Certifications

| Certification | Focus | Adoption in MENA | Future Importance |
|---------------|-------|------------------|-------------------|
| Carbon Footprint | Emissions accounting | Early stage | Growing |
| Water Stewardship | Water use efficiency | Pilot programs | High (MENA context) |
| Animal Welfare | Livestock conditions | Limited | Growing (EU exports) |
| Regenerative Ag | Soil health, biodiversity | Very early | Emerging |

## 4.4 Regulatory Bodies by Country

### Egypt

| Body | Arabic Name | Jurisdiction | Key Regulations |
|------|-------------|--------------|-----------------|
| Ministry of Agriculture & Land Reclamation | وزارة الزراعة واستصلاح الأراضي | Overall agriculture policy | Agricultural Law 53/1966 |
| General Organization for Veterinary Services (GOVS) | الهيئة العامة للخدمات البيطرية | Animal health | Veterinary Law 122/1979 |
| Plant Protection Authority | الإدارة المركزية لمكافحة الآفات | Phytosanitary | Pesticide regulation |
| Agricultural Development Fund | صندوق التنمية الزراعية | Financing | Agricultural credit |
| HEIA (Horticultural Export) | جمعية التصدير البستاني | Export promotion | Export standards |

### Saudi Arabia

| Body | Arabic Name | Jurisdiction | Key Regulations |
|------|-------------|--------------|-----------------|
| Ministry of Environment, Water & Agriculture (MEWA) | وزارة البيئة والمياه والزراعة | Overall sector | Agricultural Strategy |
| Saudi Food & Drug Authority (SFDA) | الهيئة العامة للغذاء والدواء | Food safety | Food safety systems |
| Agricultural Development Fund (ADF) | صندوق التنمية الزراعية | Financing, support | Subsidized lending |
| Saudi Grains Organization (SAGO) | المؤسسة العامة للحبوب | Grain purchasing | Price support |

### UAE

| Body | Arabic Name | Jurisdiction | Key Regulations |
|------|-------------|--------------|-----------------|
| Ministry of Climate Change & Environment (MOCCAE) | وزارة التغير المناخي والبيئة | Federal agriculture | Agricultural policies |
| Abu Dhabi Agriculture & Food Safety Authority (ADAFSA) | جهاز أبوظبي للرقابة الغذائية | Abu Dhabi | Local regulations |
| Dubai Municipality | بلدية دبي | Dubai | Local food safety |
| Emirates Authority for Standardization (ESMA) | هيئة الإمارات للمواصفات والمقاييس | Standards | Technical regulations |

### Jordan

| Body | Arabic Name | Jurisdiction | Key Regulations |
|------|-------------|--------------|-----------------|
| Ministry of Agriculture | وزارة الزراعة | Overall agriculture | Agricultural Law |
| Jordan Food & Drug Administration (JFDA) | المؤسسة العامة للغذاء والدواء | Food safety | Food safety law |
| Agricultural Credit Corporation | مؤسسة الإقراض الزراعي | Financing | Agricultural loans |
| Jordan Valley Authority | سلطة وادي الأردن | Jordan Valley irrigation | Water allocation |

## 4.5 Import/Export Regulations

### Export Requirements by Market

| Destination | Key Requirements | Documentation | Certifications |
|-------------|------------------|---------------|----------------|
| **European Union** | EU MRLs, traceability | Phytosanitary, EUR.1 | GlobalGAP recommended |
| **Gulf States (GCC)** | GSO standards, Halal | Health cert, CoO | Halal for meat |
| **Russia** | Rosselkhoznadzor approval | Quality cert, origin | GOST compliance |
| **United States** | FDA registration, phytosanitary | USDA permit | FSMA compliance |
| **UK (Post-Brexit)** | IPAFFS registration | Phytosanitary | Similar to EU |
| **Asian Markets** | Country-specific protocols | Variable | Increasing requirements |

### Common Export Barriers

| Barrier Type | Examples | Mitigation |
|--------------|----------|------------|
| **Phytosanitary** | Pest interceptions | Integrated pest management |
| **MRL Violations** | Pesticide residues | GAP, testing program |
| **Documentation** | Incomplete paperwork | Process standardization |
| **Cold Chain Breaks** | Temperature excursions | Equipment, training |
| **Labeling** | Non-compliant labels | Market-specific labels |

---

# Dimension 5: Competitive Dynamics

## 5.1 Market Structure

### Industry Concentration by Subsector

| Subsector | Concentration | Number of Players | Fragmentation Level |
|-----------|---------------|-------------------|---------------------|
| Vegetable Production | Very Low | Millions of farms | Highly fragmented |
| Fruit Production | Low | Hundreds of thousands | Fragmented |
| Poultry | Medium-High | Hundreds (SME) to dozens (large) | Consolidating |
| Dairy | Medium | Thousands | Moderately fragmented |
| Date Production | Low | Hundreds of thousands | Fragmented (export consolidating) |
| Aquaculture | Medium | Hundreds to thousands | Consolidating |
| Protected Agriculture | Medium | Hundreds | Growing consolidation |
| Agri-Services | Low-Medium | Thousands | Emerging |

### Competitive Landscape Map

```
                    HIGH DIFFERENTIATION
                           │
    PREMIUM/NICHE          │          INTEGRATED LEADERS
    • Organic producers    │          • Large poultry integrators
    • Specialty varieties  │          • Major exporters
    • Artisanal products   │          • Agri-tech leaders
                           │
   ─────────────────────────┼────────────────────────────►
   LOW COMPETITION         │          HIGH COMPETITION
                           │
    EMERGING/SMALL-SCALE   │          COMMODITY PLAYERS
    • New entrants         │          • Commodity farmers
    • Subsistence farms    │          • Volume traders
    • Start-ups            │          • Basic input suppliers
                           │
                    LOW DIFFERENTIATION
```

## 5.2 Porter's Five Forces Analysis

### Threat of New Entrants: MODERATE-LOW

| Factor | Impact | Assessment |
|--------|--------|------------|
| Capital Requirements | Moderate barrier | Varies by subsector; poultry/dairy high |
| Land Access | High barrier | Especially in urbanized areas |
| Water Rights | Very high barrier | Critical scarcity in MENA |
| Technical Know-how | Moderate barrier | Available but not ubiquitous |
| Regulatory Barriers | Moderate | Licenses achievable for SMEs |
| Economies of Scale | Low-Moderate | Benefits exist but SMEs viable |
| Brand Loyalty | Low | Commodity markets mostly |

**Overall Threat Level:** 3/5 - Barriers exist but entry possible for committed players

### Bargaining Power of Suppliers: MODERATE-HIGH

| Supplier Type | Power Level | Rationale |
|---------------|-------------|-----------|
| Seed Companies | High | Concentrated, imported varieties |
| Feed Suppliers | Very High | Import dependent, few major players |
| Fertilizer Suppliers | High | Import dependent, volatile prices |
| Agrochemical Companies | High | Branded products, regulations |
| Equipment Suppliers | Moderate | Multiple options, leasing available |
| Veterinary/Pharma | Moderate | Growing competition |
| Water (Government) | Very High | Monopoly, scarcity |

**Overall Power Level:** 4/5 - Input dependency is critical vulnerability

### Bargaining Power of Buyers: MODERATE-HIGH

| Buyer Type | Power Level | Rationale |
|------------|-------------|-----------|
| Large Retailers | Very High | Concentrated, set terms |
| Export Traders | High | Market access gatekeepers |
| Food Processors | High | Few buyers, specifications |
| Wholesale Markets | Moderate | Multiple options |
| Direct Consumers | Low | Fragmented demand |
| Restaurants/Hotels | Moderate | Quality focus, regular orders |

**Overall Power Level:** 3.5/5 - Increasing buyer consolidation pressuring farmers

### Threat of Substitutes: LOW-MODERATE

| Product | Substitute Threat | Notes |
|---------|-------------------|-------|
| Fresh Produce | Low | Limited substitutes for fresh |
| Poultry | Moderate | Competition from red meat, fish |
| Dairy | Moderate | Plant-based alternatives growing |
| Dates | Low | Cultural/religious importance |
| Olive Oil | Low-Moderate | Other cooking oils available |
| Fresh Fish | Moderate | Frozen, imported alternatives |

**Overall Threat Level:** 2.5/5 - Food staples have limited substitutes

### Rivalry Among Existing Competitors: HIGH

| Factor | Assessment | Impact |
|--------|------------|--------|
| Number of Competitors | Very high | Millions of farms |
| Industry Growth | Moderate | Population growth drives demand |
| Product Differentiation | Low | Mostly commodities |
| Switching Costs | Very low | Easy to change suppliers |
| Fixed Costs | Moderate-High | Pressure to produce |
| Exit Barriers | High | Land, specialized assets |
| Diversity of Competitors | High | Different scales, strategies |

**Overall Rivalry:** 4/5 - Intense competition, thin margins

### Five Forces Summary

```
┌────────────────────────────────────────────────────────────────┐
│           AGRICULTURE FIVE FORCES SUMMARY                       │
├────────────────────────────────────────────────────────────────┤
│                                                                 │
│                  NEW ENTRANTS: 3/5                             │
│                  (Moderate barriers)                           │
│                        │                                       │
│                        ▼                                       │
│   SUPPLIER POWER ────────────► INDUSTRY ◄───── BUYER POWER    │
│       4/5                      RIVALRY           3.5/5         │
│   (High import                   4/5          (Retail power    │
│    dependency)              (Fragmented,       increasing)     │
│                            commoditized)                       │
│                        │                                       │
│                        ▼                                       │
│                SUBSTITUTES: 2.5/5                              │
│                (Limited for food)                              │
│                                                                 │
│   OVERALL INDUSTRY ATTRACTIVENESS: MODERATE                    │
│   Key Success Factor: Differentiation + Scale                  │
└────────────────────────────────────────────────────────────────┘
```

## 5.3 Competitive Positioning Strategies

### Strategy Options for SMEs

| Strategy | Description | Best Suited For | Requirements |
|----------|-------------|-----------------|--------------|
| **Cost Leadership** | Lowest cost producer | Field crops, commodities | Scale, efficiency |
| **Differentiation** | Premium quality/varieties | Fruits, organics, specialty | Marketing, certification |
| **Focus/Niche** | Specific segment | Organic, local, ethnic | Deep market knowledge |
| **Vertical Integration** | Control more of chain | Poultry, dairy | Capital, management |
| **Geographic** | Regional stronghold | Perishables, services | Distribution, relationships |
| **Technology Leader** | Precision/protected ag | Greenhouses, high-value | Investment, skills |

### Competitive Advantages by Subsector

| Subsector | Key Success Factors | Sustainable Advantages |
|-----------|---------------------|------------------------|
| Vegetable Production | Yield, timing, quality | Location, water access, technology |
| Fruit Production | Variety, post-harvest | Established orchards, certifications |
| Poultry | FCR, biosecurity, integration | Scale, vertical integration |
| Dairy | Genetics, feeding, cooling | Herd quality, processor contracts |
| Date Production | Variety, quality grading | Premium varieties, brand |
| Olive Oil | Quality, certification | Terroir, organic certification |
| Aquaculture | FCR, survival, water | Site quality, technical expertise |
| Protected Ag | Yields, consistency | Technology, climate control |
| Agri-Services | Expertise, coverage | Reputation, relationships |

## 5.4 Industry Trends & Disruptions

### Major Trends Shaping MENA Agriculture

| Trend | Description | Impact on SMEs | Timeframe |
|-------|-------------|----------------|-----------|
| **Water Scarcity** | Groundwater depletion, climate change | Critical - adapt or exit | Ongoing |
| **Technology Adoption** | Precision ag, IoT, drones | Opportunity for efficiency | 3-7 years |
| **Vertical Farming** | Indoor CEA expansion | Disruption to greenhouse | 5-10 years |
| **Food Safety Demands** | Traceability, certification | Cost but market access | Ongoing |
| **Labor Constraints** | Costs rising, availability | Push for automation | Ongoing |
| **Climate Volatility** | Extreme weather, shifting seasons | Risk management critical | Accelerating |
| **Import Substitution** | Government food security push | Opportunity for local | Ongoing |
| **E-commerce/D2C** | Direct sales platforms | New channel opportunity | Growing |
| **Consolidation** | Larger players acquiring | Exit or differentiate | Ongoing |

### Emerging Competitors & Disruptors

| Disruptor Type | Examples | Threat Level | Response |
|----------------|----------|--------------|----------|
| **Agri-tech Startups** | Precision ag platforms | Medium | Partner or adopt |
| **Large Agribusiness** | Vertical integrators | High | Differentiate, cooperate |
| **Retail Private Label** | Supermarket brands | High | Add value, direct sales |
| **Foreign Competition** | Imports, FTAs | Medium-High | Quality, local, cost |
| **Alternative Proteins** | Plant-based, cell-ag | Low (long-term) | Monitor |

## 5.5 Regional Market Dynamics

### MENA Agricultural Market Overview

| Country | Agri GDP (% of total) | Key Products | Growth Drivers |
|---------|----------------------|--------------|----------------|
| **Egypt** | 11% | Vegetables, citrus, rice, cotton | Population, export |
| **Saudi Arabia** | 2.5% | Dairy, poultry, dates | Food security mandate |
| **Morocco** | 12% | Citrus, olives, vegetables | EU export access |
| **Tunisia** | 10% | Olive oil, dates, vegetables | EU proximity |
| **Jordan** | 4% | Vegetables, citrus, olive oil | Regional exports |
| **UAE** | <1% | Dates, vegetables (protected) | Technology, imports |
| **Iraq** | 5% | Dates, wheat, vegetables | Reconstruction |
| **Algeria** | 12% | Dates, wheat, vegetables | Import substitution |

### Trade Flow Patterns

```
┌────────────────────────────────────────────────────────────────────────┐
│               MENA AGRICULTURAL TRADE FLOWS                            │
├────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│   EXPORTS FROM MENA                     IMPORTS TO MENA                │
│   ──────────────────                    ─────────────────               │
│                                                                         │
│   Egypt ──► EU (Citrus, Vegetables)     Wheat ◄── Russia, Ukraine     │
│   Morocco ──► EU (Citrus, Vegetables)   Feed ◄── Americas, EU         │
│   Tunisia ──► EU (Olive Oil)            Meat ◄── Brazil, Australia    │
│   Egypt/Jordan ──► GCC (Fresh Produce)  Dairy ◄── EU, Oceania         │
│   Gulf Dates ──► Global Markets         Rice ◄── Asia                 │
│                                                                         │
│   INTRA-REGIONAL:                                                      │
│   Egypt ──► Gulf (Vegetables, Fruits, Dairy)                          │
│   Jordan ──► Gulf (Vegetables, Processed)                             │
│   Syria/Lebanon ──► Gulf (Fruits, Olive Oil) - disrupted              │
│                                                                         │
└────────────────────────────────────────────────────────────────────────┘
```

### Competitive Position by Country

| Country | Competitive Strengths | Competitive Weaknesses | Strategic Position |
|---------|----------------------|------------------------|-------------------|
| **Egypt** | Scale, labor, Nile water, EU access | Infrastructure, quality consistency | Volume exporter |
| **Morocco** | EU proximity, quality, certifications | Water stress, land fragmentation | Premium exporter |
| **Tunisia** | Olive heritage, organic growth | Scale, investment | Niche premium |
| **Saudi Arabia** | Capital, technology, domestic market | Water crisis, high costs | Strategic self-sufficiency |
| **UAE** | Technology, logistics hub | Limited land/water, cost | High-tech niche |
| **Jordan** | Quality, certifications, Gulf access | Water, small scale | Premium regional |

---

*End of Dimensions 1-5 - Continue to Part 2 for Dimensions 6-11*

---

# Dimension 6: Digital Maturity

## 6.1 Technology Adoption Benchmarks

### Current Digital Maturity by Subsector

| Subsector | Current Adoption Level | Digital Leaders (%) | Digital Laggards (%) | Key Gap |
|-----------|------------------------|--------------------|--------------------|---------|
| Vegetable Production | Low-Medium | 15% | 50% | Farm management systems |
| Fruit Production | Low | 10% | 60% | Traceability, post-harvest |
| Poultry | Medium-High | 35% | 25% | Integrated systems |
| Dairy | Medium | 25% | 40% | Herd management, cooling |
| Date Production | Low | 8% | 70% | Sorting, quality systems |
| Aquaculture | Medium | 30% | 35% | Monitoring, feeding |
| Protected Ag | Medium-High | 45% | 20% | Climate control, automation |
| Agri-Services | Low-Medium | 20% | 45% | Digital delivery, platforms |

### Digital Maturity Assessment Framework

```
┌─────────────────────────────────────────────────────────────────────────────┐
│              AGRICULTURE DIGITAL MATURITY LEVELS                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  LEVEL 1: MANUAL (Score 0-20)                                               │
│  ────────────────────────────                                               │
│  • Paper-based records                                                       │
│  • No digital tools                                                         │
│  • Manual data collection                                                   │
│  • No connectivity                                                          │
│  • Typical: Traditional smallholders                                        │
│                                                                              │
│  LEVEL 2: BASIC DIGITAL (Score 21-40)                                       │
│  ───────────────────────────────────                                        │
│  • Spreadsheets for records                                                 │
│  • Basic smartphone use                                                     │
│  • WhatsApp for communication                                               │
│  • Some weather apps                                                        │
│  • Typical: Progressive small farms                                         │
│                                                                              │
│  LEVEL 3: CONNECTED (Score 41-60)                                           │
│  ─────────────────────────────────                                          │
│  • Farm management software                                                 │
│  • Digital record keeping                                                   │
│  • Basic sensors (temp, humidity)                                           │
│  • E-commerce presence                                                      │
│  • Typical: Medium commercial farms                                         │
│                                                                              │
│  LEVEL 4: INTEGRATED (Score 61-80)                                          │
│  ─────────────────────────────────                                          │
│  • Integrated ERP/farm system                                               │
│  • IoT sensors throughout                                                   │
│  • Automated data collection                                                │
│  • Traceability systems                                                     │
│  • Typical: Large commercial, export-focused                                │
│                                                                              │
│  LEVEL 5: INTELLIGENT (Score 81-100)                                        │
│  ────────────────────────────────────                                       │
│  • AI/ML decision support                                                   │
│  • Precision agriculture                                                    │
│  • Predictive analytics                                                     │
│  • Autonomous systems                                                       │
│  • Typical: Agri-tech leaders, vertical farms                              │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 6.2 Core Technology Systems

### Essential Digital Infrastructure

| System Category | Priority | Investment Range (USD) | Payback Period | Adoption Rate MENA |
|-----------------|----------|----------------------|----------------|-------------------|
| **Smartphones/Tablets** | Critical | $200-800 | Immediate | 75% |
| **Basic Internet** | Critical | $50-200/month | Immediate | 60% |
| **Farm Management Software** | High | $500-5,000/year | 1-2 years | 20% |
| **Weather Monitoring** | High | $100-1,000 | 1 season | 35% |
| **Basic Accounting** | High | $200-1,000/year | 6-12 months | 30% |
| **Traceability System** | Medium-High | $1,000-10,000 | 1-3 years | 15% (exporters: 60%) |
| **IoT Sensors** | Medium | $500-10,000 | 1-3 years | 10% |
| **Drone Services** | Medium | $200-500/service | Immediate | 5% |
| **ERP Integration** | Lower (for SMEs) | $10,000-50,000 | 2-4 years | 5% |

### Subsector-Specific Technologies

**Crop Production:**

| Technology | Application | Investment | ROI Potential | Maturity |
|------------|-------------|------------|---------------|----------|
| Soil Sensors | Moisture, nutrients | $100-500/sensor | 10-25% yield gain | Mature |
| Weather Stations | On-farm climate data | $500-3,000 | Risk reduction | Mature |
| Satellite Imagery | Crop health monitoring | $2-10/ha/year | Early detection | Mature |
| Variable Rate Tech | Precision application | $5,000-20,000 | 15-30% input savings | Mature |
| Drone Spraying | Precision application | $200-500/ha/service | Labor, efficacy | Emerging |
| AI Pest Detection | Disease identification | $500-2,000/year | Early intervention | Emerging |

**Livestock Production:**

| Technology | Application | Investment | ROI Potential | Maturity |
|------------|-------------|------------|---------------|----------|
| RFID Tagging | Animal identification | $2-10/tag | Traceability | Mature |
| Automated Feeding | Precision nutrition | $5,000-50,000 | FCR improvement | Mature |
| Climate Control | Environment management | $10,000-100,000 | Mortality reduction | Mature |
| Health Monitoring | Early disease detection | $500-5,000 | Treatment costs | Emerging |
| Robotic Milking | Dairy automation | $150,000-250,000 | Labor, efficiency | Limited in MENA |
| Genetics Software | Breeding decisions | $1,000-5,000/year | Herd improvement | Emerging |

**Aquaculture:**

| Technology | Application | Investment | ROI Potential | Maturity |
|------------|-------------|------------|---------------|----------|
| Water Quality Sensors | O2, pH, temp monitoring | $500-5,000 | Mortality reduction | Mature |
| Automated Feeders | Precision feeding | $2,000-20,000 | FCR improvement | Mature |
| Underwater Cameras | Behavior monitoring | $1,000-10,000 | Feed optimization | Emerging |
| Biomass Estimation | Stock assessment | $2,000-10,000 | Planning accuracy | Emerging |
| AI Disease Detection | Health monitoring | $5,000-20,000 | Early treatment | Emerging |

## 6.3 Digital Readiness Assessment

### Assessment Questions by Category

**Infrastructure (25 points):**

| Question | Yes/Partial/No | Points |
|----------|---------------|--------|
| Reliable internet at farm location? | | 0/3/5 |
| Smartphones for key personnel? | | 0/3/5 |
| Computer/tablet for office work? | | 0/3/5 |
| Backup power available? | | 0/3/5 |
| Digital payment capability? | | 0/2/5 |

**Systems & Data (25 points):**

| Question | Yes/Partial/No | Points |
|----------|---------------|--------|
| Digital record keeping? | | 0/3/5 |
| Farm management software? | | 0/3/5 |
| Financial/accounting system? | | 0/3/5 |
| Production tracking? | | 0/3/5 |
| Inventory management? | | 0/2/5 |

**Connectivity & Integration (25 points):**

| Question | Yes/Partial/No | Points |
|----------|---------------|--------|
| Connected to buyers digitally? | | 0/3/5 |
| Digital supplier management? | | 0/3/5 |
| Market price information access? | | 0/3/5 |
| Traceability capability? | | 0/3/5 |
| E-commerce/online sales? | | 0/2/5 |

**Skills & Culture (25 points):**

| Question | Yes/Partial/No | Points |
|----------|---------------|--------|
| Staff comfortable with technology? | | 0/3/5 |
| Owner/manager digitally literate? | | 0/3/5 |
| Regular technology training? | | 0/3/5 |
| Data-driven decision making? | | 0/3/5 |
| Digital transformation plans? | | 0/2/5 |

## 6.4 Digital Opportunities by Subsector

### High-Impact Digital Interventions

| Subsector | Priority 1 | Priority 2 | Priority 3 | Estimated Impact |
|-----------|------------|------------|------------|------------------|
| Vegetable Production | Weather alerts, market prices | Traceability | Precision irrigation | 15-25% efficiency |
| Fruit Production | Post-harvest tracking | Quality grading tech | Export documentation | 20-30% loss reduction |
| Poultry | Environmental controls | Feed management | Health monitoring | 5-15% FCR improvement |
| Dairy | Herd management | Cooling monitoring | Milk quality tracking | 10-20% productivity |
| Date Production | Quality sorting | Traceability | Market platforms | 20-40% value capture |
| Aquaculture | Water quality monitoring | Feed optimization | Biomass tracking | 10-25% yield increase |
| Protected Ag | Climate control | Crop monitoring | Integrated systems | 20-40% efficiency |
| Agri-Services | Digital platforms | Remote advisory | Data services | Market expansion |

### Agri-Tech Ecosystem in MENA

| Country | Agri-Tech Activity | Notable Startups/Initiatives | Focus Areas |
|---------|-------------------|------------------------------|-------------|
| **Egypt** | Growing | Fresh Source, Mozare3 | Marketplace, inputs |
| **UAE** | Advanced | Pure Harvest, Madar Farms | Vertical farming, CEA |
| **Saudi Arabia** | Developing | Red Sea Farms, Nawaat | Aquaculture, hydroponics |
| **Jordan** | Emerging | Zad, various | Water tech, services |
| **Morocco** | Emerging | Various pilots | Citrus tech, traceability |

---

# Dimension 7: Workforce Norms

## 7.1 Organizational Structure

### Typical Agricultural SME Structures

**Small Farm (5-15 employees):**

```
                    Owner/Manager
                         │
          ┌──────────────┼──────────────┐
          │              │              │
    Field Workers    Equipment     Family Labor
       (2-8)        Operator (1)      (2-5)
```

**Medium Commercial Farm (15-50 employees):**

```
                      Owner/GM
                         │
        ┌────────────────┼────────────────┐
        │                │                │
   Farm Manager    Admin/Finance    Technical Advisor
        │                │           (Part-time)
    ┌───┴───┐            │
    │       │            │
 Field    Pack-      Accountant
Supervisors house     (Shared)
  (2-3)   Manager
    │       │
Workers  Packers
(10-30)   (5-15)
```

**Large Commercial Farm (50-150 employees):**

```
                        General Manager
                              │
       ┌──────────────────────┼──────────────────────┐
       │                      │                      │
  Operations           Finance/Admin            Sales/Export
   Manager                Manager                 Manager
       │                      │                      │
  ┌────┴────┐           ┌─────┴─────┐          ┌─────┴─────┐
  │         │           │           │          │           │
Field    Post-       Accountant  HR/Admin   Export    Local
Manager  Harvest        (1-2)      (1-2)    Coord.    Sales
  │      Manager                              │
  │         │                            Documentation
  │    ┌────┴────┐
  │    │         │
Supervisors  QA Team  Cold Chain
 (3-5)       (2-3)     (2-5)
  │
Field Workers (30-80)
Seasonal Workers (20-50)
```

## 7.2 Key Roles & Responsibilities

### Core Agricultural Roles

| Role | Key Responsibilities | Required Experience | Education |
|------|---------------------|---------------------|-----------|
| **Farm Manager** | Overall operations, planning, team leadership | 5-10 years | Agriculture degree preferred |
| **Field Supervisor** | Daily coordination, quality control, worker management | 3-5 years | Secondary + experience |
| **Agronomist** | Crop management, pest control, nutrition | 3-5 years | Agriculture degree |
| **Veterinarian** | Animal health, treatment, compliance | 5+ years | Veterinary degree |
| **Irrigation Technician** | Water management, system maintenance | 2-5 years | Technical training |
| **Pack-house Manager** | Post-harvest operations, quality, logistics | 3-5 years | Secondary + training |
| **Quality Controller** | Testing, compliance, documentation | 2-3 years | Food science/agriculture |
| **Equipment Operator** | Machinery operation, basic maintenance | 1-3 years | Training + license |
| **Field Worker** | Planting, cultivation, harvesting | Entry level | Basic training |

### Specialized Roles by Subsector

**Poultry-Specific:**

| Role | Responsibilities | Skills Required |
|------|------------------|-----------------|
| Hatchery Manager | Incubation, chick quality | Technical, biosecurity |
| Breeder Farm Manager | Parent stock management | Genetics, reproduction |
| Broiler House Manager | Flock management, environment | Production optimization |
| Layer House Manager | Egg production, collection | Quality, efficiency |

**Dairy-Specific:**

| Role | Responsibilities | Skills Required |
|------|------------------|-----------------|
| Herd Manager | Animal husbandry, breeding | Dairy expertise |
| Milking Supervisor | Milk quality, hygiene | Equipment, protocols |
| Nutrition Specialist | Feed formulation, optimization | Animal nutrition |
| AI Technician | Artificial insemination | Technical certification |

**Aquaculture-Specific:**

| Role | Responsibilities | Skills Required |
|------|------------------|-----------------|
| Hatchery Manager | Breeding, larval rearing | Technical specialization |
| Pond/Cage Manager | Production management | Water quality, feeding |
| Feed Manager | Nutrition, inventory | FCR optimization |
| Processing Supervisor | Harvest, quality | Food safety |

## 7.3 Compensation Benchmarks

### Monthly Salaries by Role and Country (USD)

**Egypt:**

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Farm Manager | $400-600 | $600-1,000 | $1,000-1,500 |
| Agronomist | $350-500 | $500-800 | $800-1,200 |
| Field Supervisor | $200-300 | $300-450 | $450-600 |
| Field Worker | $120-180 | $180-250 | $250-350 |
| Equipment Operator | $200-300 | $300-450 | $450-600 |
| Pack-house Worker | $150-200 | $200-300 | $300-400 |

**Saudi Arabia:**

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Farm Manager | $2,500-3,500 | $3,500-5,000 | $5,000-8,000 |
| Agronomist | $2,000-3,000 | $3,000-4,500 | $4,500-6,500 |
| Field Supervisor | $1,200-1,800 | $1,800-2,500 | $2,500-3,500 |
| Field Worker | $600-900 | $900-1,200 | $1,200-1,500 |
| Equipment Operator | $1,000-1,500 | $1,500-2,200 | $2,200-3,000 |

**Jordan:**

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| Farm Manager | $600-900 | $900-1,400 | $1,400-2,000 |
| Agronomist | $500-700 | $700-1,100 | $1,100-1,600 |
| Field Supervisor | $350-500 | $500-700 | $700-1,000 |
| Field Worker | $250-350 | $350-500 | $500-650 |

### Wage Structures

| Component | Field Crops | Horticulture | Livestock | Notes |
|-----------|-------------|--------------|-----------|-------|
| Base Salary | 70-80% | 60-70% | 80-90% | Regular monthly |
| Overtime | 10-15% | 20-30% | 5-10% | Seasonal peaks |
| Productivity Bonus | 5-10% | 5-15% | 5-10% | Output based |
| Housing/Transport | 5-10% | 5-10% | 5-10% | Common in Gulf |

## 7.4 Skills Requirements

### Critical Skills Gap Analysis

| Skill Area | Current Availability | Market Demand | Gap Severity |
|------------|---------------------|---------------|--------------|
| Precision Agriculture | Low | Growing | High |
| Water Management | Medium | Very High | Medium-High |
| Food Safety/HACCP | Low-Medium | High | High |
| Post-Harvest Technology | Low | High | High |
| Digital/AgriTech | Very Low | Growing | Very High |
| Export Documentation | Medium | High | Medium |
| Equipment Operation | Medium | High | Medium |
| Organic Production | Low | Growing | Medium |

### Training Needs by Role

| Role Level | Priority Training Areas | Delivery Method | Duration |
|------------|------------------------|-----------------|----------|
| **Management** | Business planning, finance, export, quality systems | Workshops, online | 40-80 hours |
| **Technical** | GAP, pest management, irrigation, certifications | On-site, practical | 40-120 hours |
| **Supervisors** | Team leadership, quality control, safety | On-site, workshops | 20-40 hours |
| **Workers** | Harvesting, handling, safety, hygiene | On-site, practical | 8-24 hours |

## 7.5 Labor Market Characteristics

### Workforce Composition in MENA Agriculture

| Characteristic | Egypt | Saudi Arabia | Jordan | UAE |
|---------------|-------|--------------|--------|-----|
| **Local vs Migrant** | 95% local | 20% local, 80% migrant | 50/50 | 10% local, 90% migrant |
| **Seasonal vs Permanent** | 60/40 | 30/70 | 50/50 | 20/80 |
| **Female Participation** | 45% | 5% | 25% | 15% |
| **Average Age** | 35-40 | 30-40 | 35-45 | 30-40 |
| **Unionization** | Low | None | Low | None |

### Labor Challenges by Country

| Challenge | Egypt | Saudi Arabia | Jordan | Morocco |
|-----------|-------|--------------|--------|---------|
| **Cost Pressure** | Medium | High | Medium | Medium |
| **Availability** | Good | Dependent on visas | Limited local | Good |
| **Skills Gap** | High | High | High | High |
| **Turnover** | Medium | High | Medium | Low |
| **Regulations** | Complex | Strict quotas | Standard | Standard |

### Seasonal Labor Patterns

```
┌────────────────────────────────────────────────────────────────────────┐
│                    AGRICULTURAL LABOR DEMAND CYCLES                     │
├────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│  CROPS (Mediterranean Climate):                                        │
│                                                                         │
│  JAN  FEB  MAR  APR  MAY  JUN  JUL  AUG  SEP  OCT  NOV  DEC           │
│  ▓▓▓  ▓▓▓  ████ ████ ████ ▓▓▓  ▓▓▓  ████ ████ ████ ▓▓▓  ▓▓▓           │
│       Prep  Planting    Maintenance    Harvest        Winter           │
│                                                                         │
│  DATES:                                                                 │
│  ▓▓▓  ▓▓▓  ▓▓▓  ████ ████ ████ ████ ████ ████ ████ ▓▓▓  ▓▓▓           │
│       Low        Pollination      Harvest & Processing                 │
│                                                                         │
│  POULTRY (Broiler):                                                    │
│  ████ ████ ████ ████ ████ ████ ████ ████ ████ ████ ████ ████           │
│       Continuous production - relatively stable                        │
│                                                                         │
│  Legend: ████ = Peak Labor  ▓▓▓ = Base Labor                          │
└────────────────────────────────────────────────────────────────────────┘
```

## 7.6 HR Metrics & Benchmarks

### Key HR KPIs for Agriculture

| Metric | Formula | Poor | Average | Good | Excellent |
|--------|---------|------|---------|------|-----------|
| **Turnover Rate** | Departures / Avg Headcount | >40% | 25-40% | 15-25% | <15% |
| **Absenteeism** | Absent Days / Work Days | >8% | 5-8% | 3-5% | <3% |
| **Training Hours** | Training Hours / Employee | <8 | 8-16 | 16-24 | >24 |
| **Labor Cost % Revenue** | Labor Cost / Revenue | >40% | 30-40% | 20-30% | <20% |
| **Revenue per Employee** | Revenue / Employees | See Dim 2 | | | |
| **Safety Incidents** | Incidents / 100 Workers | >5 | 3-5 | 1-3 | <1 |


---

# Dimension 8: Supply Chain

## 8.1 Supply Chain Structure

### Agricultural Supply Chain Overview

```
┌────────────────────────────────────────────────────────────────────────────────┐
│                    AGRICULTURE SUPPLY CHAIN ARCHITECTURE                        │
├────────────────────────────────────────────────────────────────────────────────┤
│                                                                                 │
│   INPUT SUPPLIERS                     PRODUCTION                               │
│   ──────────────                      ──────────                               │
│   ┌─────────────┐                    ┌──────────────────┐                      │
│   │ Seeds       │───────────────────►│                  │                      │
│   │ (Import/    │                    │   FARM           │                      │
│   │  Local)     │                    │   (SME Focus)    │                      │
│   └─────────────┘                    │                  │                      │
│   ┌─────────────┐                    │  • Crop          │                      │
│   │ Fertilizers │───────────────────►│  • Livestock     │                      │
│   │ (Mostly     │                    │  • Aquaculture   │                      │
│   │  Import)    │                    │  • Protected     │                      │
│   └─────────────┘                    │                  │                      │
│   ┌─────────────┐                    └────────┬─────────┘                      │
│   │ Agrochemical│───────────────────►        │                                 │
│   │ (Import)    │                            │                                 │
│   └─────────────┘                            │                                 │
│   ┌─────────────┐                            ▼                                 │
│   │ Feed        │                    ┌──────────────────┐                      │
│   │ (Very High  │───────────────────►│  POST-HARVEST    │                      │
│   │  Import)    │                    │  • Pack-house    │                      │
│   └─────────────┘                    │  • Cold Storage  │                      │
│   ┌─────────────┐                    │  • Processing    │                      │
│   │ Equipment   │───────────────────►│  • Grading       │                      │
│   │ (Import)    │                    └────────┬─────────┘                      │
│   └─────────────┘                            │                                 │
│   ┌─────────────┐                            │                                 │
│   │ WATER       │───────────────────►        │                                 │
│   │ (CRITICAL)  │                            ▼                                 │
│   └─────────────┘                    ┌──────────────────┐                      │
│                                      │  DISTRIBUTION    │                      │
│                                      │  ┌────────────┐  │                      │
│                                      │  │ Wholesale  │──┼──► Local Market     │
│                                      │  │ Markets    │  │                      │
│                                      │  └────────────┘  │                      │
│                                      │  ┌────────────┐  │                      │
│                                      │  │ Retail     │──┼──► Consumers        │
│                                      │  │ Chains     │  │                      │
│                                      │  └────────────┘  │                      │
│                                      │  ┌────────────┐  │                      │
│                                      │  │ Export     │──┼──► Int'l Markets    │
│                                      │  │ Channels   │  │                      │
│                                      │  └────────────┘  │                      │
│                                      │  ┌────────────┐  │                      │
│                                      │  │ Processing │──┼──► F&B Industry     │
│                                      │  └────────────┘  │                      │
│                                      └──────────────────┘                      │
│                                                                                 │
│   CRITICAL CHALLENGE: Cold Chain Infrastructure Gap in MENA                    │
│   IMPORT DEPENDENCY: Seeds 40%, Fertilizer 60%, Feed 75%, Agrochem 80%        │
└────────────────────────────────────────────────────────────────────────────────┘
```

## 8.2 Input Supply Analysis

### Key Input Categories

**Seeds & Planting Material:**

| Category | Import Dependency | Key Sources | Local Production | Price Volatility |
|----------|------------------|-------------|------------------|------------------|
| Vegetable Seeds | 70-85% | Netherlands, USA, Japan | Limited hybrid | Medium |
| Fruit Seedlings | 30-50% | EU, local nurseries | Growing | Low |
| Field Crop Seeds | 40-60% | Various | Significant (wheat, barley) | Medium |
| Certified Seeds | 60-80% | International companies | Limited | Medium |

**Fertilizers:**

| Type | Import Dependency | Key Sources | Price Driver | Cost Impact |
|------|------------------|-------------|--------------|-------------|
| Nitrogen (Urea) | 40-70% | Russia, China, Gulf | Natural gas | 15-25% of input cost |
| Phosphate | 20-40% | Morocco, Russia | Mining capacity | 8-15% of input cost |
| Potash | 90%+ | Belarus, Russia, Canada | Supply concentration | 5-10% of input cost |
| Specialty/Foliar | 80%+ | EU, USA | Technology | Variable |

**Animal Feed:**

| Component | Import Dependency | Key Sources | Volatility | Cost Impact (Livestock) |
|-----------|------------------|-------------|------------|------------------------|
| Corn/Maize | 85-95% | Brazil, USA, Argentina | Very High | 30-40% of cost |
| Soybean Meal | 90-95% | Brazil, Argentina, USA | Very High | 25-35% of cost |
| Wheat Bran | 30-50% | Regional, imports | Medium | 5-10% of cost |
| Additives/Premix | 95%+ | EU, USA, China | Medium | 5-8% of cost |

### Input Procurement Best Practices

| Practice | Description | Benefit | Adoption Rate |
|----------|-------------|---------|---------------|
| **Bulk Purchasing** | Group buying cooperatives | 10-20% cost savings | 15% |
| **Forward Contracts** | Lock in prices ahead | Price certainty | 10% |
| **Supplier Diversification** | Multiple sources | Risk mitigation | 25% |
| **Local Sourcing** | Develop local suppliers | Reduced import dependency | Growing |
| **Quality Testing** | Verify input quality | Reduced losses | 30% |
| **Inventory Management** | Optimal stock levels | Cash flow | 20% |

## 8.3 Distribution Channels

### Fresh Produce Channels

| Channel | Market Share | Characteristics | SME Access |
|---------|-------------|-----------------|------------|
| **Wholesale Markets** | 50-65% | Traditional, price discovery, volume | Easy |
| **Retail Chains** | 15-25% | Quality specs, contracts, payment terms | Moderate |
| **Export** | 10-20% | Certification, documentation, cold chain | Challenging |
| **Food Service** | 5-10% | Regular orders, specifications | Growing |
| **Direct/E-commerce** | 2-5% | Higher margins, logistics challenge | Emerging |

### Channel Characteristics by Market

| Market | Primary Channel | Retailer Power | Export Activity | E-commerce Growth |
|--------|-----------------|----------------|-----------------|-------------------|
| **Egypt** | Wholesale | Growing | Significant | Emerging |
| **Saudi Arabia** | Retail | High | Limited | Growing |
| **UAE** | Retail/Import | Very High | Re-export | Advanced |
| **Jordan** | Mixed | Medium | Regional | Limited |
| **Morocco** | Wholesale/Export | Medium | Strong | Limited |

## 8.4 Cold Chain Infrastructure

### Cold Chain Gap Analysis

| Component | Availability MENA | Adequacy | Investment Need |
|-----------|------------------|----------|-----------------|
| Farm-level Cooling | 15-25% | Very Low | Critical |
| Pack-house Cold Rooms | 40-60% | Low-Medium | High |
| Refrigerated Transport | 25-40% | Low | Critical |
| Cold Storage Facilities | 50-70% | Medium | Moderate |
| Port/Airport Cold | 60-80% | Medium | Moderate |

### Temperature Requirements by Product

| Product Category | Required Temp | Tolerance | Shelf Life Impact |
|------------------|---------------|-----------|-------------------|
| Leafy Vegetables | 0-4°C | Low | Critical |
| Tomatoes | 12-15°C | Medium | Significant |
| Citrus | 5-8°C | Medium | Moderate |
| Meat/Poultry | -18 to 4°C | Very Low | Critical |
| Dairy | 2-6°C | Very Low | Critical |
| Fish/Seafood | -2 to 2°C | Very Low | Critical |
| Dates | 0-10°C | Medium | Moderate |

### Cold Chain KPIs

| KPI | Definition | Target | Critical |
|-----|------------|--------|----------|
| Temperature Excursions | % shipments with breach | <5% | >15% |
| Cooling Time to Target | Hours from harvest | <4 hours | >12 hours |
| Cold Chain Coverage | % volume in cold chain | >80% | <50% |
| Pre-cooling Availability | % farms with access | >50% | <20% |

## 8.5 Inventory Management

### Inventory Benchmarks by Product Type

| Product | Turnover (times/year) | Holding Cost % | Optimal Stock Days |
|---------|----------------------|----------------|-------------------|
| Fresh Vegetables | 50-100 | N/A (perishable) | 1-5 days |
| Fresh Fruits | 25-50 | Low-Medium | 5-15 days |
| Dates (stored) | 2-4 | Low | 90-180 days |
| Animal Feed | 12-24 | Medium | 15-30 days |
| Fertilizers | 4-8 | Low | 45-90 days |
| Agrochemicals | 3-6 | Low | 60-120 days |
| Live Animals | N/A | Very High | Minimize |
| Fish (live) | N/A | High | Minimize |

### Inventory Management Practices

| Practice | Application | Benefit | Technology |
|----------|-------------|---------|------------|
| **FIFO** | All perishables | Loss reduction | Basic tracking |
| **Just-in-Time** | Fresh produce | Cash flow, quality | Supply chain coordination |
| **Safety Stock** | Critical inputs | Continuity | Forecasting |
| **ABC Analysis** | Input prioritization | Focus resources | Basic analytics |
| **Demand Forecasting** | Production planning | Match supply/demand | Advanced systems |

## 8.6 Logistics & Transportation

### Transportation Modes

| Mode | Use Case | Cost | Speed | Cold Chain |
|------|----------|------|-------|------------|
| Farm Vehicles | Farm to pack-house | Low | Fast | Limited |
| Refrigerated Trucks | Distribution | Medium-High | Fast | Available |
| Regular Trucks | Non-perishables | Low-Medium | Fast | None |
| Maritime | Export | Low | Slow | Available |
| Air Freight | Premium export | Very High | Very Fast | Available |

### Logistics Cost Benchmarks

| Route/Activity | Cost Range | Key Variables |
|----------------|------------|---------------|
| Farm to Pack-house | $5-20/ton | Distance, road quality |
| Domestic Distribution | $15-50/ton | Distance, volume |
| Egypt to Gulf | $80-150/ton | Mode, product |
| MENA to EU (sea) | $100-200/ton | Port efficiency, season |
| MENA to EU (air) | $800-2,000/ton | Product value, urgency |

---

# Dimension 9: Export Requirements

## 9.1 Export Market Overview

### MENA Agricultural Export Profile

| Exporting Country | Key Products | Main Destinations | Export Value (USD) |
|------------------|--------------|-------------------|-------------------|
| **Egypt** | Citrus, potatoes, onions, strawberries | EU, Russia, Gulf | $3-4 billion |
| **Morocco** | Citrus, tomatoes, berries, olive oil | EU | $4-5 billion |
| **Tunisia** | Olive oil, dates, citrus | EU | $1.5-2 billion |
| **Saudi Arabia** | Dates, dairy, eggs | Gulf, Asia | $500M-1B |
| **Jordan** | Vegetables, citrus, olive oil | Gulf | $300-500M |
| **UAE** | Re-exports, dates | Global | $500M-1B |

### Market-Specific Requirements

**European Union:**

| Requirement | Details | SME Challenge |
|-------------|---------|---------------|
| MRL Compliance | EU pesticide limits | Testing costs, GAP discipline |
| Traceability | Farm to fork | System investment |
| Phytosanitary | Pest-free certification | Inspection, treatment |
| GlobalGAP | Recommended/required by retailers | Certification cost |
| Labeling | EU regulations | Label production |
| Documentation | Phyto cert, EUR.1, packing list | Administrative burden |

**Gulf Cooperation Council (GCC):**

| Requirement | Details | SME Challenge |
|-------------|---------|---------------|
| GSO Standards | Technical specifications | Testing, compliance |
| Halal (meat) | Islamic certification | Slaughter requirements |
| Labeling | Arabic, nutrition | Label compliance |
| Registration | Product registration (some) | Administrative process |
| Shelf Life | Minimum requirements | Cold chain |

**Russia/CIS:**

| Requirement | Details | SME Challenge |
|-------------|---------|---------------|
| Rosselkhoznadzor | Facility approval | Inspection process |
| Phytosanitary | Strict requirements | Compliance history |
| Quality Certificates | Product testing | Laboratory access |
| Documentation | Russian language | Translation |

## 9.2 Certifications for Export

### Certification Requirements by Market

| Certification | Required For | Cost (Annual) | Process Duration |
|---------------|--------------|---------------|------------------|
| **Phytosanitary Certificate** | All plant exports | $10-50/shipment | Per shipment |
| **GlobalGAP** | EU retail, premium markets | $1,500-5,000 | 6-12 months initial |
| **Organic (EU)** | Organic claims EU | $2,000-8,000 | 2-3 years conversion |
| **BRC Food** | UK retail | $4,000-12,000 | 6-12 months |
| **Halal** | GCC meat exports | $1,000-3,000 | 2-6 months |
| **Fair Trade** | Specialty markets | $3,000-10,000 | 6-12 months |
| **GRASP (GlobalGAP)** | Social compliance | +$500-1,000 | With GlobalGAP |

### Certification Decision Matrix

| Market Focus | Essential | Recommended | Optional |
|--------------|-----------|-------------|----------|
| **EU Supermarkets** | GlobalGAP, Phyto | BRC/IFS, GRASP | Organic, Rainforest |
| **EU Wholesale** | Phyto | GlobalGAP | Organic |
| **GCC Retail** | GSO, Halal (meat) | GlobalGAP | Organic |
| **Premium/Specialty** | Organic, Fair Trade | GlobalGAP | Carbon footprint |
| **Processing/Industrial** | Phyto | ISO 22000 | Specific buyer |

## 9.3 Export Documentation

### Required Documents by Product

| Document | Fresh Produce | Meat/Poultry | Processed | Dairy |
|----------|---------------|--------------|-----------|-------|
| Commercial Invoice | ✓ | ✓ | ✓ | ✓ |
| Packing List | ✓ | ✓ | ✓ | ✓ |
| Phytosanitary Cert | ✓ | - | Some | - |
| Health Certificate | - | ✓ | Some | ✓ |
| Halal Certificate | - | ✓ (Islamic) | Some | - |
| Certificate of Origin | ✓ | ✓ | ✓ | ✓ |
| Bill of Lading/AWB | ✓ | ✓ | ✓ | ✓ |
| EUR.1 (EU) | ✓ | ✓ | ✓ | ✓ |
| Fumigation Cert | Some | - | - | - |
| Lab Analysis | ✓ | ✓ | ✓ | ✓ |

### Documentation Process

```
┌────────────────────────────────────────────────────────────────────────┐
│                   EXPORT DOCUMENTATION WORKFLOW                         │
├────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│   PRE-SHIPMENT (5-15 days before)                                      │
│   ─────────────────────────────────                                    │
│   1. Confirm order & specifications                                    │
│   2. Arrange inspection date                                           │
│   3. Prepare samples for testing                                       │
│   4. Book shipping/logistics                                           │
│                                                                         │
│   INSPECTION & CERTIFICATION (3-7 days before)                         │
│   ─────────────────────────────────────────────                        │
│   5. Phytosanitary inspection                                          │
│   6. Lab results received                                              │
│   7. Certificates issued                                               │
│                                                                         │
│   SHIPPING (Day of)                                                    │
│   ───────────────────                                                  │
│   8. Final documentation package                                       │
│   9. Customs clearance (origin)                                        │
│   10. Goods loaded                                                     │
│                                                                         │
│   POST-SHIPMENT                                                        │
│   ────────────────                                                     │
│   11. Tracking & temperature monitoring                                │
│   12. Advance copies to buyer                                          │
│   13. Customs clearance (destination)                                  │
│   14. Delivery & payment                                               │
│                                                                         │
│   COMMON DELAYS:                                                       │
│   • Missing/incorrect documents                                        │
│   • Failed inspections                                                 │
│   • Lab result delays                                                  │
│   • Shipping capacity                                                  │
└────────────────────────────────────────────────────────────────────────┘
```

## 9.4 Export Compliance

### Maximum Residue Limits (MRLs)

| Market | Stringency | Reference | Key Consideration |
|--------|------------|-----------|-------------------|
| **European Union** | Very strict | EU Pesticide Database | Default 0.01 ppm |
| **USA** | Strict | EPA tolerances | Different from EU |
| **Russia** | Strict | EAEU regulations | Own standards |
| **GCC** | Moderate | GSO/Codex | Generally follow Codex |
| **Japan** | Very strict | Positive list system | Complex requirements |
| **China** | Moderate-Strict | GB standards | Evolving |

### Compliance Best Practices

| Practice | Description | Investment | Impact |
|----------|-------------|------------|--------|
| **GAP Implementation** | Good Agricultural Practice | Medium | Foundation |
| **Spray Records** | Complete pesticide documentation | Low | Traceability |
| **Pre-shipment Testing** | Lab analysis before export | $50-200/test | Confidence |
| **Buyer Communication** | Understand specific requirements | Low | Alignment |
| **Buffer Zones** | Separation from non-compliant areas | Low-Medium | Risk reduction |
| **IPM Program** | Integrated Pest Management | Medium | Reduced chemistry |

## 9.5 Export Logistics

### Mode Selection by Product

| Product | Primary Mode | Transit Time | Cost/kg | Temperature |
|---------|--------------|--------------|---------|-------------|
| Strawberries | Air | 1-2 days | $1.50-3.00 | 0-2°C |
| Citrus (EU) | Sea (reefer) | 7-14 days | $0.08-0.15 | 4-8°C |
| Dates | Sea | 14-30 days | $0.05-0.10 | Ambient/cool |
| Fresh Fish | Air | 1-2 days | $2.00-5.00 | 0-2°C |
| Poultry (frozen) | Sea (reefer) | 14-21 days | $0.10-0.20 | -18°C |
| Olive Oil | Sea | 14-30 days | $0.05-0.12 | Ambient |

### Key Export Ports/Airports

| Country | Facility | Specialization | Capacity |
|---------|----------|----------------|----------|
| **Egypt** | Alexandria Port | General, citrus | High |
| **Egypt** | Cairo Airport | Premium, berries | Medium |
| **Morocco** | Agadir Port | Tomatoes, citrus | High |
| **Tunisia** | Sfax Port | Olive oil | Medium |
| **Jordan** | Aqaba Port | Vegetables | Medium |
| **UAE** | Jebel Ali | Re-export hub | Very High |

---

# Dimension 10: Packaging & Labeling

## 10.1 Packaging Requirements

### Primary Packaging by Product

| Product | Standard Packaging | Premium Option | Export Spec |
|---------|-------------------|----------------|-------------|
| Tomatoes | Plastic crates, cartons | Clamshells, flow-wrap | 5-6kg cartons |
| Citrus | Mesh bags, cartons | Branded cartons | 15kg cartons |
| Dates | Bulk boxes | Gift boxes, retail packs | 5kg branded cartons |
| Strawberries | Punnets | Premium clamshells | 250g-500g punnets |
| Eggs | Trays, cartons | Branded cartons | 30-egg trays |
| Poultry | Bulk, bags | IQF, portions | As per buyer |
| Fresh Fish | Polystyrene boxes | Modified atmosphere | 5-20kg boxes |
| Olive Oil | Bulk drums | Glass bottles, tin | Bottles, 0.5-5L |

### Packaging Material Costs

| Material | Cost Range | Pros | Cons |
|----------|------------|------|------|
| Corrugated Cartons | $0.30-1.50 each | Recyclable, printing | Moisture sensitive |
| Plastic Crates | $3-8 each (reusable) | Durable, hygienic | Initial cost, return |
| Mesh/Net Bags | $0.05-0.20 each | Low cost, ventilation | Limited protection |
| Clamshells | $0.10-0.40 each | Visibility, protection | Plastic concerns |
| Modified Atmosphere | $0.15-0.50 each | Shelf life extension | Equipment cost |
| Glass Bottles | $0.30-2.00 each | Premium image | Weight, breakage |

## 10.2 Labeling Requirements

### Mandatory Label Elements by Market

**European Union:**

| Element | Requirement | Notes |
|---------|-------------|-------|
| Product Name | Legal name | Standardized terms |
| Country of Origin | Mandatory | "Product of [Country]" |
| Net Quantity | Weight/volume | Metric units |
| Date Marking | Best before/Use by | Format specific |
| Lot Number | Traceability | Required |
| Producer/Importer | Name & address | EU address required |
| Storage Conditions | If applicable | Temperature, etc. |
| Nutrition (processed) | Mandatory | Per 100g format |
| Allergens (processed) | Highlighted | Bold/underline |

**GCC Markets:**

| Element | Requirement | Notes |
|---------|-------------|-------|
| Arabic Text | Mandatory | All key information |
| Product Name | Arabic & English | |
| Country of Origin | Required | Both languages |
| Production/Expiry | Gregorian & Hijri | Both calendars |
| Net Weight | Metric | Arabic numerals |
| Ingredients | Arabic | Processed foods |
| Halal (meat) | Required | Certified mark |
| Nutrition | Required | Arabic format |

### Label Design Best Practices

| Element | Local Market | Export Market | Premium |
|---------|--------------|---------------|---------|
| Brand Prominence | Medium | High | Very High |
| Quality Marks | Optional | Essential | Essential |
| Variety/Grade | Basic | Detailed | Detailed |
| Traceability Code | Optional | Required | QR code |
| Sustainability Claims | Rare | Growing | Important |
| Story/Origin | Rare | Valuable | Essential |

## 10.3 Packaging Innovation

### Emerging Packaging Trends

| Trend | Description | Adoption | SME Relevance |
|-------|-------------|----------|---------------|
| **Sustainable Packaging** | Recyclable, biodegradable | Growing | Medium-term |
| **Active Packaging** | Moisture/ethylene control | Limited | Premium products |
| **Smart Packaging** | Temperature indicators, QR | Emerging | Export |
| **Reduced Plastic** | Alternative materials | Growing | Regulatory pressure |
| **Portion Packs** | Consumer convenience | Established | Value-add |
| **Modified Atmosphere** | Shelf life extension | Medium | Export advantage |

### Sustainability Requirements

| Market | Current Status | Future Direction |
|--------|----------------|------------------|
| **EU** | Packaging regulation tightening | Mandatory recycled content |
| **UK** | Plastic packaging tax | Extended producer responsibility |
| **UAE** | Single-use plastic bans | Sustainability mandates |
| **Saudi** | Limited regulation | Vision 2030 sustainability |

## 10.4 Packaging Operations

### Pack-house Standards

| Standard | Requirement | Certification |
|----------|-------------|---------------|
| **Hygiene** | Cleanable surfaces, pest control | HACCP |
| **Cold Chain** | Temperature control | GlobalGAP |
| **Traceability** | Lot tracking system | GlobalGAP, BRC |
| **Worker Safety** | PPE, training | GRASP, local law |
| **Waste Management** | Proper disposal | Environmental |

### Packaging Line KPIs

| KPI | Definition | Target | Notes |
|-----|------------|--------|-------|
| Packing Efficiency | Output/hour | Varies by product | Benchmark internally |
| Material Waste | Waste/total material | <5% | Cost control |
| Label Accuracy | Correct labels/total | >99.9% | Critical for export |
| Temperature Compliance | % time in spec | 100% | Food safety |
| Pack Weight Accuracy | Within tolerance | 100% | Regulatory |

---

# Dimension 11: MENA Regional Context

## 11.1 Country Profiles

### Egypt

| Attribute | Details |
|-----------|---------|
| **Population** | 105 million |
| **Agriculture GDP %** | 11.3% |
| **Key Products** | Citrus, vegetables, rice, cotton, poultry, aquaculture |
| **Primary Regulator** | Ministry of Agriculture and Land Reclamation |
| **Licensing Complexity** | Medium |
| **Minimum Wage (USD/month)** | $220 |
| **SME Lending** | Moderate availability |
| **Water Source** | Nile River |
| **Water Stress** | High |
| **Key Opportunities** | Export expansion, new land reclamation, aquaculture growth |
| **Key Challenges** | Water scarcity, currency volatility, infrastructure gaps |

### Saudi Arabia

| Attribute | Details |
|-----------|---------|
| **Population** | 36 million |
| **Agriculture GDP %** | 2.5% |
| **Key Products** | Dates, dairy, poultry, vegetables (protected) |
| **Primary Regulator** | Ministry of Environment, Water & Agriculture (MEWA) |
| **Licensing Complexity** | Medium-High |
| **Minimum Wage (USD/month)** | $1,070 (Saudis) |
| **SME Lending** | Good availability (subsidized) |
| **Water Source** | Groundwater (depleting), desalination |
| **Water Stress** | Extreme |
| **Key Opportunities** | Protected agriculture, AgriTech, dates, food security |
| **Key Challenges** | Water crisis, high operating costs, labor dependency |

### Jordan

| Attribute | Details |
|-----------|---------|
| **Population** | 11.5 million |
| **Agriculture GDP %** | 4.5% |
| **Key Products** | Tomatoes, cucumbers, citrus, olives |
| **Primary Regulator** | Ministry of Agriculture |
| **Licensing Complexity** | Medium |
| **Minimum Wage (USD/month)** | $310 |
| **SME Lending** | Moderate availability |
| **Water Source** | Jordan River, groundwater, treated wastewater |
| **Water Stress** | Extreme |
| **Key Opportunities** | Premium exports to Gulf, organic production |
| **Key Challenges** | Severe water scarcity, small market size |

### UAE

| Attribute | Details |
|-----------|---------|
| **Population** | 10 million |
| **Agriculture GDP %** | <1% |
| **Key Products** | Dates, vegetables (protected), vertical farming |
| **Primary Regulator** | MOCCAE, ADAFSA (Abu Dhabi) |
| **Licensing Complexity** | Medium |
| **Minimum Wage** | Market-driven |
| **SME Lending** | Good availability |
| **Water Source** | Desalination (80%), groundwater |
| **Water Stress** | Extreme |
| **Key Opportunities** | Vertical farming, AgriTech hub, food security tech |
| **Key Challenges** | Limited land, extreme climate, high costs |

### Morocco

| Attribute | Details |
|-----------|---------|
| **Population** | 37 million |
| **Agriculture GDP %** | 12% |
| **Key Products** | Citrus, olives, vegetables, cereals |
| **Primary Regulator** | Ministry of Agriculture |
| **Licensing Complexity** | Medium |
| **Minimum Wage (USD/month)** | $300 |
| **SME Lending** | Moderate-Good |
| **Water Source** | Dams, groundwater |
| **Water Stress** | High |
| **Key Opportunities** | EU market expansion, olive oil, organic growth |
| **Key Challenges** | Water stress, land fragmentation, drought risk |

## 11.2 Regional Trade Agreements

| Agreement | Members | Agricultural Benefits |
|-----------|---------|----------------------|
| **GAFTA** | Arab League states | Zero tariffs on Arab goods |
| **EU-Morocco AA** | Morocco, EU | 98%+ products duty-free |
| **EU-Egypt AA** | Egypt, EU | Progressive liberalization |
| **GCC Customs Union** | Gulf states | Free movement within GCC |
| **Jordan-US FTA** | Jordan, USA | Duty-free access |

## 11.3 Government Support Programs

| Country | Main Program | Focus | SME Access |
|---------|--------------|-------|------------|
| **Egypt** | Agricultural Development Fund | Land, exports | Medium |
| **Saudi Arabia** | ADF + Vision 2030 | Technology, water | Good |
| **UAE** | Emirate programs | AgriTech, protected ag | Good |
| **Jordan** | ACC, Valley Authority | Water, exports | Medium |
| **Morocco** | Génération Green | All agriculture | Very Good |

## 11.4 Cross-Cutting Regional Challenges

| Challenge | Severity | Mitigation |
|-----------|----------|------------|
| **Water Scarcity** | Critical | Efficiency tech, crop selection |
| **Climate Change** | High | Adaptation, protected agriculture |
| **Import Dependency** | High | Local production, partnerships |
| **Quality Standards** | Medium-High | Certification, training |
| **Technology Gap** | High | Training, investment |

## 11.5 Strategic Opportunities

| Opportunity | Key Countries | Requirements |
|-------------|---------------|--------------|
| **EU Export Expansion** | Morocco, Egypt, Tunisia | Certification, quality |
| **Gulf Food Security** | Egypt, Jordan | Logistics, relationships |
| **Organic Growth** | Tunisia, Morocco | Certification, markets |
| **Date Leadership** | Saudi, UAE, Egypt | Quality, branding |
| **AgriTech Hub** | UAE, Saudi | Investment, ecosystem |
| **Aquaculture** | Egypt, Saudi | Technology, feed |

## 11.6 Business Culture Considerations

| Aspect | Consideration |
|--------|---------------|
| **Relationships** | Very important - invest time in building trust |
| **Decision Making** | Often centralized - engage owner/senior management |
| **Ramadan** | Reduced working hours, adjust schedules |
| **Family Business** | Common structure - understand dynamics |
| **Communication** | Indirect common - read between lines |

---

# Document Summary

## Sector Overview

The **Agriculture & Agribusiness** sector in MENA represents a critical industry characterized by:

**Strategic Importance:**
- Food security priority for all MENA governments
- Major employer, especially in Egypt, Morocco, Tunisia
- Significant export potential (EU, GCC markets)
- Strong linkages to F&B manufacturing, chemicals, logistics

**Key Characteristics:**
- **Water scarcity** is the defining constraint across the region
- High input import dependency (feed, fertilizers, seeds)
- Growing technology adoption, especially in Gulf protected agriculture
- Strong comparative advantages in dates, olives, citrus, vegetables
- Diverse subsector profiles with varying financial and operational benchmarks

**SME Landscape:**
- Highly fragmented, millions of small farms
- Consolidation trends in poultry, dairy, aquaculture
- Emerging agri-services sector with growth potential
- SME size range: 3-150 employees, $25K-$15M revenue

**Priority Subsectors:**
1. **Protected Agriculture** - High growth, water efficiency, technology
2. **Aquaculture** - Fast growing, especially Egypt
3. **Date Production** - MENA competitive advantage, export potential
4. **Poultry** - Scale opportunities, integration
5. **Agri-Services** - Emerging, high margin potential

## Agent Usage Guide

| Agent | Primary Dimensions | Key Data Points |
|-------|-------------------|-----------------|
| **The Drucker** | 1, 11 | Sector classification, MENA context, subsector routing |
| **The Marvin** | 3, 4 | Operational KPIs, compliance requirements |
| **The Graham** | 2 | Financial benchmarks, margins, working capital, valuation |
| **The Ricardo** | 9, 10 | Export markets, certifications, packaging |
| **The Lovelace** | 6 | Digital maturity, technology adoption |
| **The Mayo** | 7 | Workforce norms, compensation, skills gaps |
| **The Ohno** | 8 | Supply chain structure, cold chain, logistics |
| **The Porter** | 5 | Five Forces, competitive strategies, trends |
| **The Landor** | 10 | Labeling requirements, packaging standards |

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | December 2025 | RootRise Product Team | Initial release |

---

*This document is part of the RootRise Sector Knowledge Pack series, providing comprehensive sector intelligence for The Pantheon multi-agent diagnostic system.*
