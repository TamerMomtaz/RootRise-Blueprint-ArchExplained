# RootRise Sector Knowledge Pack
# Metal Fabrication & Engineering
## Version 1.0 | December 2025

---

# Sector Metadata

```json
{
  "metadata": {
    "sector_id": "metal_fabrication_engineering",
    "sector_name": "Metal Fabrication & Engineering",
    "sector_name_ar": "تصنيع المعادن والهندسة",
    "version": "1.0.0",
    "last_updated": "2025-12-11",
    "data_sources": [
      {
        "source_id": "worldsteel_2024",
        "name": "World Steel Association MENA Report",
        "type": "industry_association",
        "publication_date": "2024-07",
        "reliability_score": 0.92
      },
      {
        "source_id": "gcc_metal_2024",
        "name": "GCC Metals and Mining Report",
        "type": "research",
        "publication_date": "2024-05",
        "reliability_score": 0.88
      },
      {
        "source_id": "unido_metal_2023",
        "name": "UNIDO Metal Working Industry Analysis",
        "type": "international_org",
        "publication_date": "2023-10",
        "reliability_score": 0.90
      },
      {
        "source_id": "statista_metals_2024",
        "name": "Statista Metalworking Industry MENA",
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
      "min_revenue_usd": 150000,
      "max_revenue_usd": 40000000
    }
  }
}
```

---

# Dimension 1: Industry Classification

## 1.1 Standard Classifications

| Classification | Code | Description |
|----------------|------|-------------|
| **ISIC Rev.4 Division** | 24, 25, 28, 33 | Basic metals, Fabricated metal products, Machinery, Repair/installation |
| **ISIC Groups** | 24.1-24.5, 25.1-25.9, 28.1-28.9, 33.1-33.2 | Various metal and machinery activities |
| **NACE Rev.2** | C24, C25, C28, C33 | Metal manufacturing and engineering |
| **RootRise Type** | Manufacturing | Discrete manufacturing, engineering services |

### Detailed ISIC Classification

**Basic Metals (Division 24) - Upstream/Large Scale:**

| ISIC Class | Description | Key Products |
|------------|-------------|--------------|
| 24.10 | Iron and steel | Steel bars, billets, sections |
| 24.20 | Steel tubes and pipes | Seamless, welded pipes |
| 24.31 | Cold drawing of bars | Drawn bars, profiles |
| 24.32 | Cold rolling of narrow strip | Steel strip |
| 24.33 | Cold forming or folding | Profiles, sections |
| 24.34 | Cold drawing of wire | Wire products |
| 24.41 | Precious metals | Gold, silver processing |
| 24.42 | Aluminum production | Aluminum ingots, shapes |
| 24.43 | Lead, zinc, tin | Non-ferrous metals |
| 24.44 | Copper | Copper products |
| 24.45 | Other non-ferrous | Various metals |
| 24.51 | Casting of iron | Iron castings |
| 24.52 | Casting of steel | Steel castings |
| 24.53 | Casting of light metals | Aluminum castings |
| 24.54 | Casting of other metals | Non-ferrous castings |

**Fabricated Metal Products (Division 25) - Primary SME Domain:**

| ISIC Class | Description | Key Products |
|------------|-------------|--------------|
| 25.11 | Metal structures | Steel structures, frames |
| 25.12 | Metal doors/windows | Doors, windows, facades |
| 25.21 | Central heating radiators | Heating equipment |
| 25.29 | Tanks, reservoirs | Tanks, pressure vessels |
| 25.30 | Steam generators | Boilers (except central heating) |
| 25.40 | Weapons and ammunition | Defense products |
| 25.50 | Forging, pressing, stamping | Metal forming services |
| 25.61 | Treatment and coating | Surface treatment, coating |
| 25.62 | Machining | CNC, turning, milling |
| 25.71 | Cutlery | Knives, scissors |
| 25.72 | Locks and hinges | Hardware, fittings |
| 25.73 | Hand tools | Tools, implements |
| 25.91 | Steel drums, containers | Packaging containers |
| 25.92 | Light metal packaging | Cans, closures |
| 25.93 | Wire products | Fencing, mesh, nails |
| 25.94 | Fasteners | Bolts, nuts, screws |
| 25.99 | Other fabricated metal | Miscellaneous metal products |

**Machinery and Equipment (Division 28) - Higher Value:**

| ISIC Class | Description | Key Products |
|------------|-------------|--------------|
| 28.11 | Engines and turbines | Power generation |
| 28.12 | Fluid power equipment | Hydraulics, pneumatics |
| 28.13 | Other pumps and compressors | Industrial pumps |
| 28.14 | Valves | Industrial valves |
| 28.15 | Bearings, gears | Transmission equipment |
| 28.21 | Ovens and furnaces | Industrial heating |
| 28.22 | Lifting equipment | Cranes, hoists |
| 28.23 | Office machinery | Equipment |
| 28.24 | Power tools | Electric tools |
| 28.25 | Cooling equipment | Industrial cooling |
| 28.29 | General machinery | Various equipment |
| 28.30 | Agricultural machinery | Farm equipment |
| 28.41 | Metal forming machinery | Presses, machine tools |
| 28.49 | Other machine tools | Cutting, forming tools |
| 28.91 | Metallurgy machinery | Foundry, rolling equipment |
| 28.92 | Mining machinery | Extraction equipment |
| 28.93 | Food machinery | Processing equipment |
| 28.94 | Textile machinery | Textile equipment |
| 28.95 | Paper machinery | Paper processing |
| 28.96 | Plastic/rubber machinery | Molding, extrusion |
| 28.99 | Other special machinery | Specialized equipment |

**Repair and Installation (Division 33):**

| ISIC Class | Description | Activities |
|------------|-------------|------------|
| 33.11 | Repair of fabricated metal | Maintenance, repair |
| 33.12 | Repair of machinery | Equipment repair |
| 33.20 | Installation of machinery | Equipment installation |

## 1.2 Value Chain Position

```
┌─────────────────────────────────────────────────────────────────────────────┐
│              METAL FABRICATION & ENGINEERING VALUE CHAIN                     │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  RAW MATERIALS      PRIMARY METALS       FABRICATION        END USE          │
│  (Mining/Scrap)     (Mills/Smelters)     (SME Domain)       (Customers)      │
│                                                                              │
│  ┌─────────────────┐ ┌─────────────────┐ ┌──────────────┐ ┌──────────────┐  │
│  │ Iron Ore        │ │ Steel Mills     │ │ Structural   │ │ Construction │  │
│  │ Bauxite         │►│ Aluminum        │►│ Fabrication  │►│ Oil & Gas    │  │
│  │ Scrap Metal     │ │ Smelters        │ │ (Cutting,    │ │ Industrial   │  │
│  │ Other Ores      │ │ Foundries       │ │  Welding,    │ │ Infrastructure│  │
│  └─────────────────┘ └─────────────────┘ │  Assembly)   │ └──────────────┘  │
│                            │             └──────────────┘                    │
│                     ┌──────▼──────────┐ ┌──────────────┐ ┌──────────────┐  │
│                     │ Steel Traders   │ │ Precision    │ │ Automotive   │  │
│                     │ Service Centers │►│ Machining    │►│ Aerospace    │  │
│                     │ (Cut-to-size)   │ │ (CNC, Tools) │ │ Equipment    │  │
│                     └─────────────────┘ └──────────────┘ └──────────────┘  │
│                            │                    │                           │
│                     ┌──────▼──────────┐ ┌──────▼────────┐ ┌──────────────┐  │
│                     │ Stockholders    │ │ Sheet Metal   │ │ Consumer     │  │
│                     │ (Inventory)     │►│ & Forming     │►│ Products     │  │
│                     │                 │ │               │ │ HVAC, etc.   │  │
│                     └─────────────────┘ └───────────────┘ └──────────────┘  │
│                                                                              │
│  SME FOCUS: Fabrication ◄──► Machining ◄──► Assembly ◄──► Services          │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Primary Position:** 
- **Upstream (Steel/Aluminum Production):** Dominated by large integrated mills (Emirates Steel, Ezz Steel, SABIC Steel)
- **Midstream (Steel Trading/Service Centers):** Mix of large traders and distributors
- **Downstream (Fabrication/Machining):** Primary SME domain - structural steel, precision machining, sheet metal

## 1.3 Subsector Taxonomy

### Subsector 1: Structural Steel Fabrication (structural_steel)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Structural Steel Fabrication |
| **Name (AR)** | تصنيع الهياكل المعدنية |
| **ISIC Classes** | 25.11 |
| **Typical Products** | Steel frames, beams, columns, trusses, bridges, industrial structures, towers |
| **Distinguishing Characteristics** | Project-based, construction-linked, heavy equipment, welding-intensive, certifications critical |

### Subsector 2: Architectural Metalwork (architectural_metal)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Architectural Metalwork |
| **Name (AR)** | الأعمال المعدنية المعمارية |
| **ISIC Classes** | 25.12 |
| **Typical Products** | Doors, windows, curtain walls, facades, railings, canopies, decorative metalwork |
| **Distinguishing Characteristics** | Design/aesthetic element, aluminum common, finishing critical, installation services |

### Subsector 3: Precision Machining & CNC (precision_machining)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Precision Machining & CNC |
| **Name (AR)** | التشغيل الدقيق والحاسب الآلي |
| **ISIC Classes** | 25.62 |
| **Typical Products** | Machined parts, components, prototypes, tooling, fixtures, spare parts |
| **Distinguishing Characteristics** | Technology-intensive, tight tolerances, diverse customers, skill-dependent, job shop model |

### Subsector 4: Sheet Metal Fabrication (sheet_metal)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Sheet Metal Fabrication |
| **Name (AR)** | تصنيع الصفائح المعدنية |
| **ISIC Classes** | 25.99, 25.29 |
| **Typical Products** | Enclosures, cabinets, HVAC ductwork, panels, housings, equipment covers |
| **Distinguishing Characteristics** | Laser/plasma cutting, bending, welding, powder coating, diverse applications |

### Subsector 5: Tanks & Pressure Vessels (tanks_vessels)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Tanks & Pressure Vessels |
| **Name (AR)** | الخزانات وأوعية الضغط |
| **ISIC Classes** | 25.29, 25.30 |
| **Typical Products** | Storage tanks, pressure vessels, heat exchangers, process equipment, silos |
| **Distinguishing Characteristics** | ASME/API codes, welding certifications, NDT testing, oil & gas market |

### Subsector 6: Wire & Metal Mesh Products (wire_mesh)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Wire & Metal Mesh Products |
| **Name (AR)** | منتجات الأسلاك والشبك المعدني |
| **ISIC Classes** | 25.93 |
| **Typical Products** | Chain link fencing, welded mesh, wire rope, nails, reinforcement mesh |
| **Distinguishing Characteristics** | Commodity products, construction demand, continuous production |

### Subsector 7: Metal Hardware & Fasteners (hardware_fasteners)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Metal Hardware & Fasteners |
| **Name (AR)** | الأدوات والمثبتات المعدنية |
| **ISIC Classes** | 25.72, 25.94 |
| **Typical Products** | Bolts, nuts, screws, hinges, locks, brackets, fittings |
| **Distinguishing Characteristics** | High volume, standards-driven, import competition, distribution |

### Subsector 8: Industrial Equipment & Machinery (industrial_equipment)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Industrial Equipment & Machinery |
| **Name (AR)** | المعدات والآلات الصناعية |
| **ISIC Classes** | 28.29, 28.93, 28.99 |
| **Typical Products** | Conveyors, material handling, food processing equipment, specialized machinery |
| **Distinguishing Characteristics** | Engineering-intensive, custom design, installation services, after-sales |

### Subsector 9: Metal Casting & Foundry (casting_foundry)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Metal Casting & Foundry |
| **Name (AR)** | صب المعادن والمسابك |
| **ISIC Classes** | 24.51, 24.52, 24.53, 24.54 |
| **Typical Products** | Cast iron parts, steel castings, aluminum castings, spare parts, components |
| **Distinguishing Characteristics** | Capital-intensive, pattern-making, heat/environmental challenges |

### Subsector 10: Surface Treatment & Coating (surface_treatment)

| Attribute | Value |
|-----------|-------|
| **Name (EN)** | Surface Treatment & Coating |
| **Name (AR)** | المعالجة السطحية والطلاء |
| **ISIC Classes** | 25.61 |
| **Typical Products** | Galvanizing, powder coating, anodizing, plating, painting |
| **Distinguishing Characteristics** | Service business, environmental compliance, quality-critical, batch processing |

## 1.4 Adjacent Sectors

| Sector | Relationship | Relevance Score | Interaction |
|--------|--------------|-----------------|-------------|
| Construction | Customer | 0.95 | Structural steel, architectural |
| Oil & Gas | Customer | 0.90 | Pressure vessels, piping, structures |
| Automotive | Customer | 0.80 | Parts, components, tooling |
| Industrial/Manufacturing | Customer | 0.85 | Equipment, machinery, maintenance |
| Aerospace | Customer | 0.65 | Precision parts (limited in MENA) |
| Power/Energy | Customer | 0.80 | Equipment, structures |
| Water/Utilities | Customer | 0.75 | Tanks, pipes, equipment |
| Steel Trading | Supplier | 0.90 | Raw material supply |

---

# Dimension 2: Financial Benchmarks

## 2.1 Revenue Benchmarks

### Revenue Distribution by Subsector

| Subsector | Median Revenue (USD) | P25 | P75 |
|-----------|---------------------|-----|-----|
| Structural Steel | $5,000,000 | $1,500,000 | $20,000,000 |
| Architectural Metalwork | $2,500,000 | $600,000 | $10,000,000 |
| Precision Machining | $1,500,000 | $400,000 | $6,000,000 |
| Sheet Metal | $2,000,000 | $500,000 | $8,000,000 |
| Tanks & Vessels | $4,000,000 | $1,000,000 | $15,000,000 |
| Wire & Mesh | $3,000,000 | $800,000 | $12,000,000 |
| Hardware & Fasteners | $2,500,000 | $600,000 | $10,000,000 |
| Industrial Equipment | $3,500,000 | $800,000 | $15,000,000 |
| Casting/Foundry | $2,000,000 | $500,000 | $8,000,000 |
| Surface Treatment | $1,200,000 | $300,000 | $5,000,000 |

### Revenue Growth Rates

| Performance Level | Annual Growth |
|-------------------|---------------|
| Sector Average | 6% |
| Top Quartile | 15%+ |
| Bottom Quartile | -3% |

**Growth Drivers:**
- Construction activity (giga projects, infrastructure)
- Oil & gas investments
- Industrial development/localization
- Maintenance/repair demand
- Import substitution initiatives

### Seasonality Pattern

| Attribute | Value |
|-----------|-------|
| **Pattern Type** | Moderate to Strong (construction-linked subsectors) |
| **Peak Periods** | Q1, Q4 (construction activity, budget cycles) |
| **Low Periods** | Summer months (Q3), Ramadan |
| **Revenue Variance** | ±20-25% from mean |
| **Notes** | Project-based work creates lumpiness. Oil & gas maintenance often in Q2/Q3. |

### Seasonality by Subsector

| Subsector | Seasonality | Key Driver |
|-----------|-------------|------------|
| Structural Steel | High | Construction projects |
| Architectural | High | Construction season |
| Precision Machining | Low-Medium | Diverse customer base |
| Tanks/Vessels | Medium | O&G project timing |
| Sheet Metal | Medium | Mixed customers |
| Wire/Mesh | High | Construction |
| Industrial Equipment | Low | Project-based |

## 2.2 Profitability Benchmarks

### Margin Benchmarks by Subsector

| Subsector | Gross Margin | Operating Margin | Net Margin |
|-----------|--------------|------------------|------------|
| Structural Steel | 15-22% | 6-12% | 3-8% |
| Architectural Metalwork | 22-32% | 10-18% | 6-12% |
| Precision Machining | 35-50% | 15-28% | 10-20% |
| Sheet Metal | 25-35% | 10-18% | 6-12% |
| Tanks & Vessels | 18-28% | 8-15% | 5-10% |
| Wire & Mesh | 15-22% | 6-12% | 3-8% |
| Hardware & Fasteners | 20-30% | 8-15% | 5-10% |
| Industrial Equipment | 30-45% | 15-25% | 10-18% |
| Casting/Foundry | 25-35% | 10-18% | 6-12% |
| Surface Treatment | 35-45% | 18-28% | 12-20% |

### Sector Blended Median

| Margin Type | Sector Median | Healthy Range | Top Quartile |
|-------------|---------------|---------------|--------------|
| **Gross Margin** | 28% | 18-45% | 38% |
| **Operating Margin** | 12% | 6-22% | 18% |
| **Net Margin** | 8% | 4-15% | 12% |
| **EBITDA Margin** | 15% | 8-25% | 20% |

### Project vs. Product Profitability

| Business Type | Typical Margin | Risk | Notes |
|---------------|----------------|------|-------|
| Project work (lump sum) | 12-20% bid | Variable actual | Execution risk |
| Project work (cost plus) | 8-15% markup | Lower | More predictable |
| Product (standard) | 20-35% | Lower | Volume-dependent |
| Product (custom) | 25-45% | Medium | Engineering content |
| Services (machining) | 35-50% | Low | Capacity-dependent |

## 2.3 Cost Structure

### Fabrication Business Cost Breakdown

| Cost Category | % of Revenue | Notes |
|---------------|--------------|-------|
| Raw Materials (Steel, Aluminum) | 35-50% | Largest cost, price-volatile |
| Direct Labor | 18-28% | Skill-dependent |
| Consumables (Welding, Tools) | 3-8% | Variable with output |
| Energy | 3-6% | Higher for foundry |
| Equipment Depreciation | 4-8% | Capital-intensive |
| Subcontracting | 5-12% | Coating, special processes |
| Overhead (Facilities, Admin) | 10-15% | Fixed costs |
| Selling & BD | 3-6% | Project development |

### Machining Business Cost Breakdown

| Cost Category | % of Revenue | Notes |
|---------------|--------------|-------|
| Raw Materials | 20-35% | Lower % due to value-add |
| Direct Labor | 25-35% | High skill requirements |
| Tooling & Consumables | 8-15% | Cutting tools, inserts |
| Energy | 4-7% | Machine operation |
| Equipment Depreciation | 8-15% | CNC intensive |
| Overhead | 12-18% | Programming, QC |

### Steel Price Impact

| Steel Type | Typical Price ($/ton) | Volatility | % of COGS |
|------------|----------------------|------------|-----------|
| Structural (HR Sections) | $600-$900 | High | 30-45% |
| Plate | $700-$1,000 | High | 35-50% |
| Sheet (CR/HR) | $800-$1,200 | High | 25-40% |
| Stainless | $2,500-$4,000 | Medium | 20-40% |
| Aluminum | $2,200-$3,000 | High | 25-45% |

## 2.4 Working Capital Benchmarks

| Metric | Fabrication | Machining | Trading |
|--------|-------------|-----------|---------|
| **DSO** | 75-120 days | 45-75 days | 60-90 days |
| **DIO** | 30-60 days | 30-45 days | 60-90 days |
| **DPO** | 45-75 days | 30-45 days | 45-60 days |
| **Cash Conversion Cycle** | 45-90 days | 30-60 days | 60-90 days |

### Working Capital Intensity

| Subsector | NWC % of Revenue | Notes |
|-----------|------------------|-------|
| Structural Steel | 25-40% | Progress billing helps |
| Precision Machining | 15-25% | Faster turnover |
| Tanks/Vessels | 25-35% | Project-based |
| Sheet Metal | 20-30% | Moderate |
| Wire/Mesh | 25-35% | Inventory-heavy |

### Working Capital Challenges

| Challenge | Subsectors Affected | Impact |
|-----------|---------------------|--------|
| Retention payments (5-10%) | Structural, architectural | Cash tied 12-24 months |
| Progress billing delays | Project-based | Cash flow gaps |
| Material price volatility | All | Pre-purchase pressure |
| Large project prepayment | Equipment | Advance requirement |
| Slow-moving inventory | Hardware, standard products | Tied capital |

## 2.5 Investment & Capital Requirements

### CapEx by Subsector

| Subsector | Initial Investment | % Revenue (Maintenance) | Asset Life |
|-----------|-------------------|------------------------|------------|
| Structural Steel | $500K-$5M | 5-8% | 15-20 years |
| Architectural | $300K-$2M | 4-6% | 12-15 years |
| Precision Machining | $500K-$5M | 6-10% | 10-15 years |
| Sheet Metal | $300K-$3M | 5-8% | 12-15 years |
| Tanks/Vessels | $500K-$4M | 5-7% | 15-20 years |
| Wire/Mesh | $500K-$5M | 4-6% | 15-20 years |
| Casting/Foundry | $1M-$10M | 6-10% | 15-25 years |
| Surface Treatment | $300K-$3M | 5-8% | 12-18 years |

### Key Equipment Costs

**Structural/Heavy Fabrication:**

| Equipment | Cost Range | Notes |
|-----------|------------|-------|
| Overhead Crane (10-50 ton) | $50K-$300K | Essential |
| Beam Line (CNC drill/cut) | $200K-$800K | Productivity driver |
| Plate Cutting (CNC plasma/flame) | $50K-$400K | Capacity driver |
| Section Bending | $50K-$300K | Curved work |
| Welding Stations | $5K-$50K each | Multiple needed |
| Shot Blasting | $50K-$300K | Surface prep |

**Precision Machining:**

| Equipment | Cost Range | Notes |
|-----------|------------|-------|
| CNC Machining Center (vertical) | $80K-$400K | Workhorse |
| CNC Machining Center (horizontal) | $150K-$800K | Higher productivity |
| CNC Lathe | $50K-$300K | Turning capability |
| 5-Axis CNC | $300K-$1M+ | Complex parts |
| EDM (Wire/Sink) | $80K-$400K | Precision/tooling |
| CMM (Coordinate Measuring) | $50K-$200K | Inspection |

**Sheet Metal:**

| Equipment | Cost Range | Notes |
|-----------|------------|-------|
| Laser Cutting | $150K-$800K | Primary cutting |
| Turret Punch | $100K-$400K | Hole patterns |
| Press Brake (CNC) | $80K-$400K | Bending |
| Shear | $30K-$150K | Straight cuts |
| Welding (TIG/MIG) | $5K-$30K each | Assembly |
| Powder Coating Line | $100K-$500K | Finishing |

## 2.6 Valuation Multiples

### Revenue & EBITDA Multiples

| Subsector | Revenue Multiple | EBITDA Multiple |
|-----------|------------------|-----------------|
| Structural Steel | 0.3-0.7x | 4-6x |
| Architectural | 0.4-0.8x | 4-7x |
| Precision Machining | 0.6-1.2x | 5-8x |
| Sheet Metal | 0.4-0.9x | 5-7x |
| Tanks/Vessels | 0.4-0.8x | 4-7x |
| Wire/Mesh | 0.3-0.6x | 4-6x |
| Industrial Equipment | 0.6-1.2x | 5-8x |
| Surface Treatment | 0.5-1.0x | 5-8x |

### Valuation Premium Factors

**Positive:**
- Modern equipment (CNC, automation)
- Certifications (ISO, ASME, API, AWS)
- Diversified customer base
- Recurring revenue (maintenance, service)
- Skilled workforce
- Strong backlog
- Technical capabilities
- Established relationships

**Discount Factors:**
- Customer concentration
- Old equipment/manual processes
- Key person dependency
- Project-to-project business
- Safety/environmental issues
- Weak financials/controls

---

# Dimension 3: Operational KPIs

## 3.1 Production Efficiency Metrics

### Overall Equipment Effectiveness (OEE)

| Equipment Type | Median OEE | Target OEE | World-Class |
|----------------|------------|------------|-------------|
| CNC Machining Center | 55% | 70% | 85%+ |
| Laser Cutting | 60% | 75% | 85%+ |
| Press Brake | 50% | 65% | 80%+ |
| Welding Stations | 40% | 55% | 70%+ |
| Crane Operations | 25% | 40% | 55%+ |

### OEE Components

| Component | Target | Key Factors |
|-----------|--------|-------------|
| **Availability** | >85% | Maintenance, setup time |
| **Performance** | >90% | Operating speed, minor stops |
| **Quality** | >98% | First-pass yield |

### Capacity Utilization

| Metric | Target | Warning | Notes |
|--------|--------|---------|-------|
| Machine Utilization | 70-80% | <55% | Allow maintenance buffer |
| Labor Utilization | 75-85% | <65% | Billable/direct hours |
| Shop Floor Sqm Utilization | >70% | <50% | Space efficiency |

## 3.2 Quality Metrics

### Fabrication Quality KPIs

| Metric | Definition | Target | Warning |
|--------|------------|--------|---------|
| **First Pass Yield** | Parts accepted first time | >95% | <90% |
| **Weld Rejection Rate** | Rejected welds / total welds | <3% | >5% |
| **Dimensional Accuracy** | Within tolerance | >98% | <95% |
| **NCR Rate** | Non-conformances per project | <2% | >5% |
| **Customer Complaints** | Per month/quarter | <3 | >5 |
| **Rework Hours** | % of productive hours | <5% | >10% |

### Machining Quality KPIs

| Metric | Definition | Target | Warning |
|--------|------------|--------|---------|
| **Scrap Rate** | Scrapped parts / total | <2% | >4% |
| **Dimensional CPK** | Process capability | >1.33 | <1.0 |
| **Surface Finish** | Within specification | >99% | <97% |
| **Tool Life Achievement** | Actual vs. expected | >90% | <80% |

### Welding Quality Standards

| Standard | Application | Requirement |
|----------|-------------|-------------|
| **AWS D1.1** | Structural steel | Procedure qualification, welder certification |
| **ASME Section IX** | Pressure vessels | Procedure and welder qualification |
| **EN ISO 15614** | Steel structures (EU) | Welding procedures |
| **API 1104** | Pipelines | Pipeline welding |

### Non-Destructive Testing (NDT)

| Test | Application | When Required |
|------|-------------|---------------|
| Visual (VT) | All welds | 100% |
| Magnetic Particle (MT) | Surface defects | Critical welds |
| Dye Penetrant (PT) | Surface defects | Non-magnetic materials |
| Ultrasonic (UT) | Internal defects | Pressure vessels, critical |
| Radiographic (RT) | Internal defects | Pressure vessels, code work |

## 3.3 Productivity Metrics

| Metric | Definition | Good | Top Quartile |
|--------|------------|------|--------------|
| **Revenue per Employee** | Total revenue / headcount | $60,000 | $90,000+ |
| **Tons per Employee (Structural)** | Output tonnage / headcount | 3-5 tons/month | 6+ tons/month |
| **Direct/Indirect Ratio** | Direct labor / indirect | 3:1 | 4:1+ |
| **Value Added per Hour** | (Revenue - Materials) / hours | $40+ | $60+ |
| **Shop Floor Productivity** | Output / shop floor area | Benchmark dependent | +25% vs. baseline |

### Productivity by Process

| Process | Typical Output | Benchmark |
|---------|----------------|-----------|
| Structural Fabrication | 15-30 tons/person/month | Complexity dependent |
| Sheet Metal | 200-500 parts/person/day | Size dependent |
| CNC Machining | 5-20 parts/hour | Complexity dependent |
| Welding | 20-50 meters/day/welder | Position, process |
| Assembly | Variable | Product dependent |

## 3.4 Project Performance KPIs (For Project-Based Work)

### Schedule Performance

| Metric | Target | Warning | Critical |
|--------|--------|---------|----------|
| **On-Time Delivery** | >90% | 80-90% | <80% |
| **Schedule Variance** | <5% delay | 5-15% | >15% |
| **Milestone Achievement** | >95% | 85-95% | <85% |

### Cost Performance

| Metric | Target | Warning | Critical |
|--------|--------|---------|----------|
| **Estimated vs. Actual Cost** | +/-5% | +/-10% | >15% variance |
| **Material Waste** | <5% | 5-10% | >10% |
| **Labor Efficiency** | >85% | 75-85% | <75% |

### Estimating Accuracy

| Metric | Target | Warning |
|--------|--------|---------|
| **Bid Accuracy** | +/-10% | >15% variance |
| **Material Estimate** | +/-5% | >10% variance |
| **Labor Estimate** | +/-10% | >15% variance |

## 3.5 Maintenance & Equipment KPIs

| Metric | Target | Warning |
|--------|--------|---------|
| **Planned Maintenance %** | >80% | <60% |
| **Unplanned Downtime** | <5% | >10% |
| **MTBF (Key Equipment)** | Increasing | Decreasing |
| **MTTR** | <4 hours | >8 hours |
| **Maintenance Cost** | 3-5% of asset value | >7% |
| **Tool Life Tracking** | Systematic | Ad hoc |

## 3.6 Safety KPIs

### Safety Metrics

| Metric | Target | Industry Average |
|--------|--------|------------------|
| **LTIF (Lost Time Injury Frequency)** | <2.0 | 4.0 |
| **TRIR (Total Recordable Incident Rate)** | <4.0 | 7.0 |
| **Near Miss Reporting** | >15/month | Culture dependent |
| **Safety Training Hours** | >20/year | 16 |
| **PPE Compliance** | 100% | 90%+ |

### Critical Safety Areas

| Hazard | Controls Required |
|--------|-------------------|
| Crane/Lifting | Certified operators, inspection, load limits |
| Welding | PPE, ventilation, fire watch |
| Grinding/Cutting | Guards, PPE, dust extraction |
| CNC/Machinery | Guards, lockout/tagout, training |
| Material Handling | Training, equipment, housekeeping |
| Confined Space | Permits, monitoring, rescue |
| Hot Work | Permits, fire prevention |
| Noise | PPE, monitoring, controls |

---

# Dimension 4: Regulatory Landscape

## 4.1 Business Licensing Requirements

### Manufacturing Licenses

| License | Issuing Authority | Countries | Validity | Cost |
|---------|-------------------|-----------|----------|------|
| **Industrial License** | Industry Ministry | All MENA | 5 years | $500-$5,000 |
| **Commercial Registration** | Commerce Ministry | All MENA | Variable | $200-$1,000 |
| **Municipality Permit** | Local Municipality | All MENA | 1 year | $100-$500 |
| **Environmental Permit** | Environment Authority | All MENA | 2-3 years | $200-$2,000 |
| **Civil Defense Permit** | Civil Defense | All MENA | 1 year | $100-$500 |

### Special Permits/Classifications

| Permit | Application | Countries |
|--------|-------------|-----------|
| **Contractor Classification** | Structural steel erection | Saudi, UAE, others |
| **Pressure Vessel License** | Tank/vessel manufacturing | All (ASME stamp) |
| **Welding Qualification** | Certified work | Per project requirement |
| **NDT Service License** | Testing services | Where applicable |

## 4.2 Quality & Process Certifications

### International Standards

| Standard | Application | Markets |
|----------|-------------|---------|
| **ISO 9001** | Quality management system | All markets |
| **ISO 3834** | Welding quality requirements | Structural, pressure |
| **ISO 14001** | Environmental management | Export, major customers |
| **ISO 45001** | Occupational health & safety | Major projects |
| **EN 1090** | Steel structures (CE marking) | EU export |

### Industry-Specific Certifications

| Certification | Application | Requirements |
|---------------|-------------|--------------|
| **ASME U Stamp** | Pressure vessels | Code compliance, authorized inspector |
| **ASME S Stamp** | Power boilers | Code compliance, authorized inspector |
| **ASME R Stamp** | Repairs | Repair procedures |
| **API Monogram** | Oil & gas equipment | API standards compliance |
| **AWS Certification** | Welding | Procedure and welder qualification |
| **AISC Certification** | Steel fabricator (US reference) | Quality system |

### Welding Certifications

| Standard | Application | Validity |
|----------|-------------|----------|
| **AWS D1.1** | Structural steel | 6 months - 2 years |
| **ASME Section IX** | Pressure vessels | Per procedure |
| **EN ISO 9606** | Welder qualification | 2 years + continuity |
| **API 1104** | Pipeline welding | Per procedure |

## 4.3 Product Standards

### Structural Steel Standards

| Standard | Application | Markets |
|----------|-------------|---------|
| **AISC 360** | Steel building design | US reference |
| **EN 1993 (Eurocode 3)** | Steel structures | EU, regional |
| **AWS D1.1** | Structural welding code | Global |
| **ASTM A36, A992, etc.** | Material specifications | Global |

### Pressure Vessel & Tank Standards

| Standard | Application | Notes |
|----------|-------------|-------|
| **ASME BPVC** | Pressure vessels, boilers | Global standard |
| **API 650** | Atmospheric storage tanks | Oil & gas |
| **API 620** | Low pressure tanks | Oil & gas |
| **EN 13445** | Unfired pressure vessels | EU |
| **PD 5500** | Pressure vessels | UK |

### Material Standards

| Material | Key Standards |
|----------|---------------|
| Structural Steel | ASTM A36, A572, A992, EN 10025 |
| Plate Steel | ASTM A516, A387, EN 10028 |
| Stainless Steel | ASTM A240, A312, EN 10088 |
| Aluminum | ASTM B209, EN 485 |

## 4.4 Environmental Regulations

### Environmental Requirements

| Area | Requirements | Enforcement |
|------|--------------|-------------|
| Air Emissions | Dust, welding fumes, coatings | Permit conditions |
| Waste Management | Metal scrap, hazardous waste | Licensed disposal |
| Water Discharge | Cooling water, treatment | Pre-treatment limits |
| Noise | Boundary limits | Measurement |
| Hazardous Materials | Storage, handling, disposal | Manifest tracking |

### Coating/Surface Treatment Environmental

| Process | Environmental Concerns | Requirements |
|---------|----------------------|--------------|
| Painting | VOC emissions | Ventilation, limits |
| Galvanizing | Zinc, acids | Treatment, disposal |
| Powder Coating | Limited | Collection systems |
| Anodizing | Acids, metals | Treatment, disposal |
| Plating | Heavy metals | Strict treatment |

## 4.5 Labor & Safety Regulations

### Workforce Requirements

| Country | Nationalization | Notes |
|---------|-----------------|-------|
| **Saudi Arabia** | Nitaqat quotas | Skilled trade exemptions limited |
| **UAE** | Emiratization targets | Technical roles emphasis |
| **Egypt** | Local hiring | Foreign worker limits |
| **Jordan** | Jordanian preference | Quotas apply |

### Safety Regulatory Requirements

| Requirement | Standard | Application |
|-------------|----------|-------------|
| PPE | Local regulations | Mandatory |
| Machine Guarding | Local/international | All machinery |
| Lifting Equipment | Inspection, certification | Cranes, hoists |
| Welding Safety | Ventilation, PPE, fire | All welding areas |
| Pressure Equipment | Testing, inspection | Vessels, compressors |
| Confined Space | Permit system | Tanks, vessels |

---

# Dimension 5: Competitive Dynamics

## 5.1 Market Structure

### Overall Market Characteristics

| Characteristic | Assessment |
|----------------|------------|
| **Structure Type** | Fragmented (fabrication), Concentrated (mills) |
| **CR4 (Fabrication)** | 15-25% |
| **CR4 (Steel Production)** | 60-80% |
| **Competition Type** | Price + capability |

### Competitive Landscape by Segment

| Segment | Local SMEs | Regional Large | International | Competition |
|---------|------------|----------------|---------------|-------------|
| Steel Mills | None | Dominant | Limited | Low (for SMEs) |
| Structural Fabrication | Many | Several | Limited | High |
| Precision Machining | Many | Few | Limited | High |
| Tanks/Vessels | Several | Several | Present | Medium-High |
| Architectural | Many | Few | Limited | High |
| Industrial Equipment | Few | Several | Present | Medium |

### Key Competitor Categories

| Category | Characteristics | Threat to SMEs |
|----------|-----------------|----------------|
| **Large Local Fabricators** | Scale, equipment, capacity | High (price, capacity) |
| **Regional Engineering Firms** | Technical capability, EPC | Medium (different segment) |
| **International EPCs** | Mega projects | Low (subcontracting opportunity) |
| **Sister SMEs** | Similar capabilities | Very High |
| **Import Competition** | Standard products | Medium-High |

## 5.2 Porter's Five Forces Analysis

### Overall Industry Attractiveness Score: 3.0/5 (Moderate)

### Force 1: Competitive Rivalry
**Intensity: HIGH (4/5)**

| Driver | Impact |
|--------|--------|
| Many fabricators | Price pressure |
| Project-based nature | Bid competition |
| Capacity fluctuations | Aggressive pricing in downturns |
| Low differentiation (some segments) | Commodity bidding |
| Fixed costs | Pressure to fill capacity |

**Implication for SMEs:** Differentiate through capability, quality, service, or specialization.

### Force 2: Threat of New Entrants
**Level: MEDIUM (3/5)**

| Barrier | Height | Description |
|---------|--------|-------------|
| Capital Requirements | Medium | $500K-$5M for basic setup |
| Technical Know-how | Medium-High | Welding, machining skills |
| Certifications | Medium-High | ASME, AWS, ISO take time |
| Customer Relationships | High | Trust, track record |
| Equipment Lead Time | Medium | 6-12 months for major equipment |

**Implication for SMEs:** Certifications and relationships are key barriers to defend.

### Force 3: Threat of Substitutes
**Level: LOW (2/5)**

| Substitute | Threat Level | Notes |
|------------|--------------|-------|
| Concrete structures | Low-Medium | Different applications |
| Plastic/Composite | Low | Niche applications |
| Prefabricated imports | Medium | Standard structures |
| 3D Printing (Metal) | Emerging | Future consideration |

**Implication for SMEs:** Limited substitution threat; focus on metal's advantages.

### Force 4: Supplier Power
**Level: HIGH (4/5)**

| Driver | Impact |
|--------|--------|
| Steel mill concentration | Limited negotiating power |
| Global price volatility | Cost unpredictability |
| Few local suppliers | Dependency |
| Quality variations | Limited alternatives |
| Specialty materials | Single sources |

**Implication for SMEs:** Build supplier relationships, consider volume aggregation, use price escalation clauses.

### Force 5: Buyer Power
**Level: MEDIUM-HIGH (3.5/5)**

| Driver | Impact |
|--------|--------|
| Large project owners | Negotiating power |
| Competitive bidding | Price pressure |
| Specification control | Compliance costs |
| Payment terms | Cash flow pressure |
| Multiple fabricator options | Easy to switch |

**Implication for SMEs:** Build value-added capabilities, develop relationships, diversify customer base.

## 5.3 Competitive Strategies for SMEs

### Successful SME Strategies

| Strategy | Description | Success Factors | Best Fit |
|----------|-------------|-----------------|----------|
| **Technical Specialization** | Focus on specific capability | Equipment, certifications, skill | Machining, pressure vessels |
| **Sector Focus** | Serve specific industry | Domain knowledge, relationships | O&G, power, food |
| **Quality Leadership** | Premium positioning | Certifications, systems, culture | Precision work |
| **Service Excellence** | Responsive, reliable | Culture, systems, location | All segments |
| **Capacity/Speed** | Fast turnaround | Equipment, efficiency | Job shop |
| **Turnkey Solutions** | Design + fabricate + install | Engineering capability | Equipment, structures |

### Specialization Examples

| Specialization | Focus Area | Competitive Advantage |
|----------------|------------|----------------------|
| O&G equipment | Pressure vessels, skids | ASME, API certifications |
| Food grade | Stainless, sanitary | Surface finish, compliance |
| Aerospace | Tight tolerance parts | Quality systems, NDT |
| Power generation | Turbine parts, structures | Certifications, scale |
| Mining equipment | Heavy fabrication, wear parts | Durability, service |
| Medical equipment | Precision, stainless | Cleanliness, accuracy |

## 5.4 Key Success Factors

| Factor | Importance | Typical SME Performance | Improvement Path |
|--------|------------|-------------------------|------------------|
| **Equipment Capability** | Critical | Variable | Investment planning |
| **Certifications** | Critical | Variable | Strategic certification |
| **Skilled Workforce** | Critical | Scarce | Training, retention |
| **Estimating Accuracy** | High | Variable | Systems, experience |
| **Project Management** | High | Weak | Training, tools |
| **Quality Systems** | High | Variable | ISO, industry standards |
| **Customer Relationships** | High | Strong locally | Expansion |
| **Financial Strength** | Medium-High | Variable | Controls, financing |

## 5.5 Market Trends

| Trend | Impact | Timeline | SME Opportunity |
|-------|--------|----------|-----------------|
| **Giga Projects (Saudi)** | Very Positive | 2024-2040 | Subcontracting, supply |
| **Local Content Requirements** | Positive | Growing | Import substitution |
| **Automation/Industry 4.0** | Mixed | Ongoing | Productivity improvement |
| **O&G Maintenance Spend** | Positive | Ongoing | Service contracts |
| **Renewable Energy** | Positive | Growing | Structures, equipment |
| **Modular Construction** | Growing | Emerging | Prefabrication capability |
| **Skilled Labor Shortage** | Negative | Ongoing | Automation investment |
| **Steel Price Volatility** | Negative | Ongoing | Pricing mechanisms |

### MENA-Specific Opportunities

| Opportunity | Description | Markets | Potential |
|-------------|-------------|---------|-----------|
| **NEOM/Giga Projects** | Massive infrastructure | Saudi Arabia | Very High |
| **O&G Maintenance** | Ongoing equipment needs | GCC | High |
| **Power Projects** | Generation, transmission | Egypt, Saudi, UAE | High |
| **Water Infrastructure** | Desalination, treatment | GCC | High |
| **Industrial Development** | Manufacturing growth | Saudi, Egypt | High |
| **Defense/Security** | Military equipment | Saudi, UAE | Medium |

---

*Continued in Part 2: Dimensions 6-11*
# RootRise Sector Knowledge Pack
# Metal Fabrication & Engineering
## Part 2: Dimensions 6-11

---

# Dimension 6: Digital Maturity Patterns

## 6.1 Current State Assessment

### Overall Digital Maturity

| Metric | Value |
|--------|-------|
| **Average Digital Maturity Score** | 32/100 |
| **Relative Position** | Behind manufacturing average |
| **Key Challenge** | Project-based nature, skilled trades mindset |

**Note:** Large steel mills and EPC contractors are often highly digitized. SME fabricators and job shops typically lag significantly.

### Maturity Distribution

| Level | % of SMEs | Characteristics |
|-------|-----------|-----------------|
| **Level 1 (Manual/Paper)** | 35% | Paper drawings, manual tracking |
| **Level 2 (Basic Digital)** | 40% | CAD, basic accounting, spreadsheets |
| **Level 3 (Connected)** | 18% | CAD/CAM, ERP modules, some automation |
| **Level 4 (Advanced)** | 6% | Integrated systems, data-driven |
| **Level 5 (Transformative)** | 1% | Digital twin, full automation |

### Digital Maturity by Subsector

| Subsector | Score | Notes |
|-----------|-------|-------|
| Precision Machining | 45/100 | CNC inherently digital |
| Sheet Metal | 40/100 | Laser/CAD/CAM common |
| Structural Steel | 32/100 | CAD adoption, manual fabrication |
| Tanks/Vessels | 35/100 | Design digital, shop floor manual |
| Architectural | 38/100 | Design-intensive |
| Wire/Mesh | 30/100 | Continuous production |
| Casting/Foundry | 28/100 | Traditional processes |
| Surface Treatment | 30/100 | Batch tracking challenges |

## 6.2 Core Systems Adoption

### Administrative Systems

| System | Adoption Rate | Common Solutions | Investment Range |
|--------|---------------|------------------|------------------|
| Accounting | 70% | QuickBooks, Sage, SAP B1 | $1K-$15K/year |
| Payroll/HR | 55% | Local solutions | $1K-$8K/year |
| Document Management | 35% | SharePoint, local | $0-$5K/year |
| ERP (Basic) | 25% | SAP B1, Odoo, local | $15K-$80K+ |
| Customer Management | 25% | Basic CRM | $2K-$15K/year |

### Engineering/Design Systems

| System | Adoption Rate | Common Solutions | Investment Range |
|--------|---------------|------------------|------------------|
| 2D CAD | 75% | AutoCAD, DraftSight | $2K-$8K/year |
| 3D CAD | 35% | SolidWorks, Inventor | $5K-$15K/year |
| CAM (Machining) | 60%* | Mastercam, Fusion | $5K-$20K/year |
| CAM (Sheet Metal) | 55%* | Lantek, SigmaNest | $5K-$25K/year |
| Structural Detailing | 40% | Tekla, SDS/2 | $10K-$30K/year |
| Vessel Design | 30% | Compress, PV Elite | $5K-$15K/year |
| Nesting Software | 50% | Various | $3K-$15K/year |

*Among subsectors where applicable

### Production/Shop Floor Systems

| System | Adoption Rate | Common Solutions | Investment Range |
|--------|---------------|------------------|------------------|
| Job Tracking | 30% | ERP modules, standalone | $5K-$25K |
| Production Scheduling | 20% | ERP, specialized | $5K-$30K |
| Quality Management | 25% | Dedicated QMS | $5K-$25K |
| Time/Attendance | 45% | Biometric, manual | $2K-$10K |
| Inventory Management | 40% | ERP modules | $5K-$20K |
| Machine Monitoring | 10% | IoT solutions | $10K-$50K |
| Maintenance (CMMS) | 15% | Fiix, UpKeep | $3K-$12K/year |

### Estimating/Quoting

| System | Adoption Rate | Common Solutions | Investment Range |
|--------|---------------|------------------|------------------|
| Spreadsheet-based | 60% | Excel | Minimal |
| Dedicated Estimating | 20% | Various | $5K-$30K |
| Integrated (ERP) | 15% | ERP modules | Part of ERP |
| BIM-based (Structural) | 10% | From 3D model | Software integration |

## 6.3 Functional Digitization Gaps

| Function | Current % Digital | Best Practice | Gap | Priority |
|----------|-------------------|---------------|-----|----------|
| Engineering/Design | 65% | 95% | 30% | High |
| Estimating/Quoting | 40% | 90% | 50% | Critical |
| Production Planning | 25% | 85% | 60% | Critical |
| Job Tracking | 30% | 90% | 60% | Critical |
| Quality Records | 35% | 95% | 60% | High |
| Inventory Control | 40% | 85% | 45% | High |
| Equipment Monitoring | 15% | 75% | 60% | Medium |
| Weld Documentation | 25% | 90% | 65% | High |
| Material Traceability | 30% | 95% | 65% | High |
| Customer Communication | 40% | 85% | 45% | Medium |

## 6.4 Automation Opportunities

### Process Automation Potential

| Process | Current State | Automation Potential | Impact | Technology |
|---------|---------------|---------------------|--------|------------|
| Material Cutting | Semi-automatic | 85% | High | CNC plasma/laser |
| Welding | Manual/semi | 60% | High | Robotic welding |
| Machining | CNC (partial) | 90% | High | Multi-axis CNC |
| Bending/Forming | Semi-automatic | 80% | Medium | CNC press brake |
| Material Handling | Manual/crane | 50% | Medium | Automated systems |
| Inspection | Manual | 40% | Medium | CMM, vision |
| Painting/Coating | Manual/batch | 50% | Medium | Automated lines |
| Assembly | Manual | 30% | Lower | Limited |

### Robotic Welding Opportunity

| Factor | Assessment |
|--------|------------|
| **Suitable Work** | Repetitive welds, high volume, consistent access |
| **Investment** | $100K-$500K for basic cell |
| **ROI Drivers** | Volume, weld intensity, labor cost |
| **Challenges** | Programming, fixturing, variety of work |
| **Current Adoption** | <5% of MENA SME fabricators |
| **Opportunity** | Medium (high volume producers) |

## 6.5 Industry 4.0 Technologies

| Technology | Maturity | MENA Adoption | Potential | Use Case |
|------------|----------|---------------|-----------|----------|
| CNC/DNC | Mature | 50%+ (machining) | High | Production efficiency |
| CAD/CAM Integration | Mature | 40%+ | High | Design-to-production |
| IoT Machine Monitoring | Growing | 10% | High | OEE improvement |
| Predictive Maintenance | Growing | <5% | Medium | Downtime reduction |
| Digital Twin | Emerging | <2% | Future | Simulation |
| AI/ML Optimization | Emerging | <5% | Medium | Process optimization |
| 3D Printing (Metal) | Growing | <5% | Medium | Prototypes, tooling |
| AR/VR | Emerging | <2% | Low-Medium | Training, assembly |

## 6.6 Digital Transformation Roadmap

### Phase 1: Foundation (0-12 months) - Investment: $15K-$50K

| Initiative | Outcome | Effort |
|------------|---------|--------|
| CAD standardization | Design efficiency | Medium |
| Basic job tracking | Visibility | Medium |
| Digital material certs | Traceability | Low |
| Basic production reporting | Data foundation | Medium |
| Estimating improvement | Win rate, accuracy | Medium |

### Phase 2: Integration (12-24 months) - Investment: $30K-$100K

| Initiative | Outcome | Effort |
|------------|---------|--------|
| ERP implementation | Process integration | High |
| CAD/CAM integration | Design-to-production | Medium |
| Quality management system | ISO support | Medium |
| Production scheduling | Efficiency | Medium |
| Machine monitoring (key equipment) | OEE data | Medium |

### Phase 3: Optimization (24-48 months) - Investment: $50K-$200K

| Initiative | Outcome | Effort |
|------------|---------|--------|
| Advanced scheduling | Optimization | High |
| Automation projects | Labor efficiency | High |
| Predictive maintenance | Reduced downtime | Medium |
| Advanced analytics | Data-driven decisions | High |
| Customer portal | Service improvement | Medium |

---

# Dimension 7: Workforce Norms

## 7.1 Organizational Sizing

### Headcount by Revenue

| Revenue Range | Total Employees | Production | Admin/Support |
|---------------|-----------------|------------|---------------|
| <$500K | 12 | 9 | 3 |
| $500K-$2M | 35 | 28 | 7 |
| $2M-$5M | 70 | 55 | 15 |
| $5M-$15M | 130 | 100 | 30 |
| >$15M | 250+ | 190+ | 60+ |

### Role Distribution (Typical)

| Role Category | % of Workforce | Notes |
|---------------|----------------|-------|
| Management | 5% | Owner, managers |
| Engineering/Technical | 10% | Engineers, drafters |
| Administrative | 8% | Finance, HR, admin |
| Supervisors | 8% | Shop supervisors, foremen |
| Skilled Trades | 45% | Welders, machinists, fitters |
| Semi-Skilled | 18% | Helpers, operators |
| Support | 6% | Warehouse, maintenance |

### Role Distribution by Subsector

| Subsector | Engineering | Production | Sales | Admin |
|-----------|-------------|------------|-------|-------|
| Structural Steel | 8% | 75% | 5% | 12% |
| Precision Machining | 12% | 68% | 8% | 12% |
| Tanks/Vessels | 12% | 70% | 6% | 12% |
| Sheet Metal | 10% | 72% | 6% | 12% |
| Industrial Equipment | 18% | 60% | 10% | 12% |

## 7.2 Compensation Benchmarks

### Management & Professional (Monthly USD)

| Role | Egypt | Jordan | Saudi Arabia | UAE |
|------|-------|--------|--------------|-----|
| General Manager | $2,500-$5,000 | $3,000-$6,000 | $8,000-$18,000 | $10,000-$22,000 |
| Production Manager | $1,500-$3,000 | $1,800-$3,500 | $6,000-$12,000 | $7,000-$15,000 |
| Engineering Manager | $1,500-$3,000 | $1,800-$3,500 | $6,000-$12,000 | $7,000-$15,000 |
| Quality Manager | $1,200-$2,500 | $1,400-$3,000 | $5,000-$10,000 | $6,000-$12,000 |
| Project Manager | $1,200-$2,500 | $1,500-$3,000 | $5,000-$10,000 | $6,000-$12,000 |
| Sales Manager | $1,200-$2,800 | $1,500-$3,200 | $5,000-$12,000 | $6,000-$14,000 |

### Engineering & Technical (Monthly USD)

| Role | Egypt | Jordan | Saudi Arabia | UAE |
|------|-------|--------|--------------|-----|
| Mechanical Engineer | $600-$1,200 | $700-$1,400 | $3,000-$6,000 | $3,500-$7,000 |
| Design Engineer | $600-$1,200 | $700-$1,400 | $3,000-$6,000 | $3,500-$7,000 |
| CAD/Draftsman | $400-$800 | $500-$900 | $2,000-$4,000 | $2,500-$5,000 |
| Estimator | $500-$1,000 | $600-$1,200 | $2,500-$5,000 | $3,000-$6,000 |
| QC Engineer | $500-$1,000 | $600-$1,100 | $2,500-$5,000 | $3,000-$6,000 |
| QC Inspector | $350-$700 | $400-$800 | $1,800-$3,500 | $2,200-$4,500 |
| NDT Technician | $500-$1,000 | $600-$1,200 | $2,500-$5,500 | $3,000-$6,500 |

### Skilled Trades (Monthly USD)

| Role | Egypt | Jordan | Saudi Arabia | UAE |
|------|-------|--------|--------------|-----|
| Certified Welder (6G) | $400-$800 | $500-$900 | $2,000-$4,000 | $2,500-$5,000 |
| Welder (Standard) | $300-$550 | $350-$650 | $1,200-$2,500 | $1,500-$3,000 |
| CNC Machinist | $400-$800 | $450-$850 | $2,000-$4,000 | $2,500-$5,000 |
| Manual Machinist | $300-$600 | $350-$700 | $1,500-$3,000 | $1,800-$3,500 |
| Fitter/Fabricator | $350-$650 | $400-$750 | $1,500-$3,000 | $1,800-$3,500 |
| Sheet Metal Worker | $300-$600 | $350-$700 | $1,400-$2,800 | $1,700-$3,200 |
| Pipe Fitter | $400-$750 | $450-$850 | $1,800-$3,500 | $2,200-$4,000 |
| Maintenance Technician | $350-$700 | $400-$800 | $1,800-$3,500 | $2,200-$4,500 |

### Production & Support (Monthly USD)

| Role | Egypt | Jordan | Saudi Arabia | UAE |
|------|-------|--------|--------------|-----|
| Supervisor/Foreman | $500-$1,000 | $600-$1,100 | $2,500-$4,500 | $3,000-$5,500 |
| Machine Operator | $250-$450 | $300-$550 | $1,200-$2,200 | $1,400-$2,600 |
| Helper/Laborer | $150-$280 | $180-$320 | $600-$1,000 | $700-$1,200 |
| Warehouse | $200-$400 | $250-$450 | $1,000-$1,800 | $1,200-$2,200 |
| Driver | $250-$450 | $300-$500 | $1,200-$2,000 | $1,400-$2,400 |

### Compensation Structure

| Component | % of Total | Notes |
|-----------|------------|-------|
| Basic Salary | 60-70% | Fixed monthly |
| Housing | 15-20% | Allowance or provided |
| Transport | 5-8% | Allowance or provided |
| Overtime | Variable | Project-dependent |
| Bonus/Incentive | 5-15% | Performance-based |

## 7.3 Skills Assessment

### Critical Skills Gap Analysis

| Skill | Importance | Availability | Gap Severity |
|-------|------------|--------------|--------------|
| **Certified Welders (6G/ASME)** | Critical | Scarce | Critical |
| **CNC Programming** | High | Limited | High |
| **CNC Operation** | Critical | Limited | High |
| **Mechanical Engineering** | High | Adequate | Medium |
| **CAD/Detailing** | High | Adequate | Medium |
| **NDT Technicians** | High | Scarce | High |
| **Estimating** | High | Scarce | High |
| **Project Management** | High | Limited | High |
| **Quality Control** | High | Limited | Medium |
| **Maintenance (CNC)** | High | Scarce | High |
| **PLC/Automation** | Medium | Scarce | High |

### Welding Certification Levels

| Level | Certification | Premium | Availability |
|-------|---------------|---------|--------------|
| Basic | Welder without certification | Baseline | Available |
| Intermediate | AWS/national certified | +20-40% | Limited |
| Advanced | 6G certified | +40-60% | Scarce |
| Specialist | ASME IX qualified | +50-80% | Very Scarce |
| Senior | Multiple codes/processes | +70-100% | Very Scarce |

### Technical Skills by Subsector

| Subsector | Core Technical Skills |
|-----------|----------------------|
| Structural Steel | Fit-up, structural welding, rigging, reading drawings |
| Precision Machining | CNC programming, setup, measuring, GD&T |
| Tanks/Vessels | Pressure welding, rolling, fitting, NDT awareness |
| Sheet Metal | Laser operation, press brake setup, TIG welding |
| Industrial Equipment | Fabrication, assembly, electrical basics, troubleshooting |

## 7.4 Labor Dynamics

### Turnover Rates

| Role Category | Annual Turnover | Key Factors |
|---------------|-----------------|-------------|
| Skilled Trades | 20-30% | Competition, project cycles |
| Semi-Skilled | 25-35% | Better opportunities |
| Technical | 15-25% | Career growth |
| Management | 10-15% | Stability, ownership |

### Absenteeism

| Metric | Typical | Target |
|--------|---------|--------|
| Overall Rate | 6-10% | <5% |
| Unplanned | 4-7% | <3% |
| Planned | 2-3% | Managed |

### Training Investment

| Category | Typical | Target |
|----------|---------|--------|
| Training Hours/Employee/Year | 16 | 32+ |
| Training Budget (% payroll) | 1-2% | 3-5% |
| Apprenticeship Programs | Rare | Needed |

### Recruitment Challenges

| Challenge | Severity | Mitigation |
|-----------|----------|------------|
| Certified welder shortage | Critical | Training, premium pay, sourcing |
| CNC skills scarcity | High | Training partnerships |
| Competition from O&G/construction | High | Total compensation, stability |
| Young worker attraction | High | Career paths, image |
| Geographic location | Medium | Transport, housing |
| Shift work acceptance | Medium | Premium pay, rotation |

## 7.5 Organizational Structure

### Typical Medium SME Structure

```
General Manager/Owner
├── Production Manager
│   ├── Shop Supervisor(s)
│   │   ├── Welders
│   │   ├── Fitters/Fabricators
│   │   └── Machine Operators
│   ├── Maintenance
│   └── Warehouse/Stores
├── Engineering Manager
│   ├── Design/Drafting
│   ├── Estimating
│   └── Project Engineers
├── Quality Manager
│   ├── QC Inspectors
│   └── NDT (if in-house)
├── Commercial/Sales Manager
│   ├── Sales
│   └── Procurement
└── Finance/Admin Manager
    ├── Accounts
    └── HR/Admin
```

### Span of Control

| Level | Typical Ratio | Notes |
|-------|---------------|-------|
| Manager : Supervisors | 1:3-5 | Depending on size |
| Supervisor : Workers | 1:10-15 | Trade dependent |
| QC Manager : Inspectors | 1:3-6 | Work volume dependent |
| Engineer : Draftsmen | 1:2-4 | Project nature dependent |

## 7.6 HR Maturity Assessment

### Overall HR Maturity: 35/100

### Common HR Gaps

| Gap | Prevalence | Impact |
|-----|------------|--------|
| No formal competency framework | 75% | Development gaps |
| Informal recruitment process | 65% | Quality of hires |
| Limited safety culture/training | 50% | Risk, compliance |
| No succession planning | 80% | Business continuity |
| Weak performance management | 60% | Accountability |
| Limited training programs | 65% | Skill gaps |
| No career paths defined | 70% | Retention |
| Certification tracking gaps | 55% | Compliance risk |

### Priority HR Improvements

| Initiative | Investment | Outcome |
|------------|------------|---------|
| Welder certification program | Medium | Quality, compliance |
| Safety training system | Medium | Risk reduction |
| Skills matrix development | Low | Resource planning |
| Performance review system | Low | Accountability |
| Apprenticeship program | Medium | Pipeline development |
| Certification tracking system | Low | Compliance |

---

# Dimension 8: Supply Chain Characteristics

## 8.1 Supply Chain Structure

```
┌────────────────────────────────────────────────────────────────────┐
│                METAL FABRICATION SUPPLY CHAIN                       │
├────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  UPSTREAM              MIDSTREAM              DOWNSTREAM            │
│                                                                     │
│  ┌─────────────┐      ┌─────────────┐       ┌─────────────┐       │
│  │ Steel Mills │      │ Traders/    │       │ Fabricator  │       │
│  │ (Emirates,  │─────►│ Service     │──────►│ SME         │       │
│  │ Ezz, etc.)  │      │ Centers     │       │             │       │
│  └─────────────┘      └─────────────┘       └──────┬──────┘       │
│                                                     │               │
│  ┌─────────────┐      ┌─────────────┐              │               │
│  │ Aluminum    │      │ Stockholders│              │               │
│  │ Smelters    │─────►│ (Inventory) │──────────────┤               │
│  └─────────────┘      └─────────────┘              │               │
│                                                     │               │
│  ┌─────────────┐      ┌─────────────┐       ┌──────▼──────┐       │
│  │ Import      │      │ Specialty   │       │ Subcontract │       │
│  │ (Commodity/ │─────►│ Suppliers   │──────►│ (Coating,   │       │
│  │ Specialty)  │      │             │       │  NDT, etc.) │       │
│  └─────────────┘      └─────────────┘       └──────┬──────┘       │
│                                                     │               │
│                                               ┌──────▼──────┐       │
│                                               │ End Customer│       │
│                                               │ (Project/   │       │
│                                               │  Product)   │       │
│                                               └─────────────┘       │
└────────────────────────────────────────────────────────────────────┘
```

## 8.2 Key Input Categories

### Raw Materials

| Category | % of COGS | Supplier Concentration | Source |
|----------|-----------|----------------------|--------|
| Steel (Structural) | 25-40% | Oligopoly | Local mills + imports |
| Steel (Plate) | 20-35% | Oligopoly | Local mills + imports |
| Steel (Sheet) | 15-30% | Oligopoly | Local mills + imports |
| Stainless Steel | 10-25% | Moderate | Mostly imports |
| Aluminum | 10-25% | Moderate | Regional + imports |
| Specialty Alloys | 5-15% | Fragmented | Imports |

### Consumables & Supplies

| Category | % of COGS | Supplier Concentration |
|----------|-----------|----------------------|
| Welding Consumables | 3-8% | Moderate |
| Cutting Tools/Inserts | 3-10% | Moderate |
| Abrasives | 1-3% | Fragmented |
| Gases | 2-4% | Oligopoly |
| Paints/Coatings | 2-5% | Moderate |
| Fasteners | 1-4% | Fragmented |

## 8.3 Major Steel Suppliers (MENA)

### Regional Steel Producers

| Producer | Country | Products | Market Position |
|----------|---------|----------|-----------------|
| Emirates Steel | UAE | Long products, rebar | Regional leader |
| Ezz Steel | Egypt | Long products, flat | Egypt dominant |
| SABIC Steel | Saudi Arabia | Long products | Saudi market |
| Hadeed (SABIC) | Saudi Arabia | Steel products | Major player |
| Qatar Steel | Qatar | Long products | GCC supply |
| United Steel (SULB) | Bahrain | Flat products | Regional |

### Steel Supply Characteristics

| Attribute | Local Mills | Traders | Direct Import |
|-----------|-------------|---------|---------------|
| Lead Time | 2-4 weeks | 1-2 weeks (ex-stock) | 6-12 weeks |
| Minimum Order | 25+ tons | 1-5 tons | Container load |
| Payment Terms | 30-60 days | 30-60 days | L/C, advance |
| Price | Mill price | Mill + margin | Variable |
| Quality | Consistent | Variable | Mill-dependent |

### Steel Price Volatility

| Metric | Value | Impact |
|--------|-------|--------|
| Annual Price Variation | ±20-40% | Major cost impact |
| Cycle Length | 6-18 months | Planning challenge |
| Price Index Reference | Platts, LME | Benchmark |
| Price Pass-Through | Difficult | Margin pressure |

## 8.4 Inventory Management

### Inventory Benchmarks

| Material Type | Typical Days | Target Days | Warning |
|---------------|--------------|-------------|---------|
| Steel (Structural) | 30-60 | 21-30 | >75 |
| Steel (Plate) | 30-45 | 21-30 | >60 |
| Steel (Sheet) | 21-45 | 14-30 | >60 |
| Stainless/Specialty | 30-60 | 21-45 | >90 |
| Welding Consumables | 30-45 | 21-30 | >60 |
| Cutting Tools | 30-60 | 21-45 | >90 |
| Work in Progress | 15-30 | 7-21 | >45 |
| Finished Goods | 7-21 | 3-14 | >30 |

### Inventory Challenges

| Challenge | Impact | Mitigation |
|-----------|--------|------------|
| Minimum order quantities | Over-stock of slow movers | Supplier negotiation |
| Project material specifics | Custom material purchase | Estimate accuracy |
| Price volatility | Buy/hold decisions | Clear policy |
| Import lead times | High safety stock | Planning improvement |
| Off-cut management | Waste, cash tied up | Nesting, tracking |

## 8.5 Subcontracting & Services

### Common Subcontracted Services

| Service | Reason for Outsourcing | Typical Lead Time |
|---------|----------------------|-------------------|
| Galvanizing | Capital intensive, specialized | 1-2 weeks |
| Powder Coating | Specialized equipment | 3-7 days |
| Heat Treatment | Specialized | 1-2 weeks |
| NDT Testing | Certification required | 1-3 days |
| Machining (overflow) | Capacity/capability | 1-2 weeks |
| Plating | Environmental, specialized | 1-3 weeks |
| Large Bending/Rolling | Equipment size | 1-2 weeks |

### Subcontractor Management

| Factor | Good Practice | Common Gap |
|--------|---------------|------------|
| Qualification | Approved vendor list | Ad hoc selection |
| Quality Control | Incoming inspection | Trust-based |
| Lead Time | Clear agreements | Unpredictable |
| Cost | Competitive quotes | Single source |
| Traceability | Documentation | Paper gaps |

## 8.6 Customer Segments

### B2B Customer Types

| Customer Type | Characteristics | Relationship |
|---------------|-----------------|--------------|
| EPC Contractors | Large projects, specifications | Subcontract, competitive bid |
| Industrial End Users | Maintenance, small projects | Direct, relationship |
| Construction Companies | Structural, architectural | Subcontract |
| O&G Operators | Maintenance, modifications | Direct, approved vendor |
| OEM Manufacturers | Components, parts | Supply agreement |
| Government/Utilities | Infrastructure | Tender, specifications |
| Trading Companies | Export | Relationship |

### Customer Concentration Risk

| Level | Top Customer % | Risk Level |
|-------|----------------|------------|
| Healthy | <15% | Low |
| Moderate | 15-30% | Medium |
| Concentrated | 30-50% | High |
| Critical | >50% | Very High |

### Payment Terms by Customer Type

| Customer Type | Typical Terms | Collection |
|---------------|---------------|------------|
| EPC Contractors | Progress billing, 30-60 days | 60-120 days actual |
| Industrial | 30-60 days | 45-90 days actual |
| Government | Per contract | Often delayed |
| Private | 30 days | 30-60 days actual |
| Export | L/C, advance | Per terms |

## 8.7 Supply Chain Risks

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Steel price spike | High | High | Escalation clauses, inventory |
| Supply disruption | Medium | High | Multiple suppliers |
| Quality issues | Medium | High | Inspection, qualified suppliers |
| Customer concentration | Medium | High | Diversification |
| Subcontractor failure | Medium | Medium | Backup vendors |
| Currency fluctuation | High | Medium | Pricing mechanisms |
| Logistics disruption | Low | Medium | Alternative routes |

---

# Dimension 9: Export / Market Access Requirements

## 9.1 Export Potential by Subsector

| Subsector | Export Potential | Current Export % | Key Markets |
|-----------|------------------|------------------|-------------|
| Structural Steel | Medium | 10-20% | Regional projects |
| Tanks/Vessels | Medium-High | 15-30% | Regional O&G |
| Precision Parts | Medium | 10-20% | Regional, Europe |
| Industrial Equipment | Medium | 15-25% | Regional |
| Wire/Mesh | Low-Medium | 5-15% | Regional, Africa |
| Hardware | Low | 5-10% | Regional |
| Architectural | Low | 5-10% | GCC inter-trade |

### Primary Export Markets

| Tier | Markets | Products |
|------|---------|----------|
| **Tier 1** | GCC inter-trade, Iraq, Jordan | Structural, equipment, vessels |
| **Tier 2** | Africa (Sudan, Ethiopia, Kenya) | Steel products, equipment |
| **Tier 3** | Europe (limited) | Precision parts, specialized |
| **Tier 4** | Asia (limited) | Niche products |

## 9.2 Export Documentation

### Standard Export Documents

| Document | Purpose | Required For |
|----------|---------|--------------|
| Commercial Invoice | Customs valuation | All exports |
| Packing List | Shipment details | All exports |
| Certificate of Origin | Origin verification | Most markets |
| Bill of Lading/AWB | Shipping document | All exports |
| Material Test Certificate | Material verification | Technical products |
| Quality Certificate | Quality confirmation | Per specification |
| Insurance Certificate | Cargo insurance | Per Incoterm |

### Technical Documentation

| Document | When Required | Notes |
|----------|---------------|-------|
| Mill Test Certificates | Steel products | Full traceability |
| Weld Procedure Specs | Welded products | Code compliance |
| Welder Qualifications | Welded products | Certification evidence |
| NDT Reports | Pressure equipment | Third-party |
| Dimensional Reports | Precision products | Inspection results |
| As-Built Drawings | Fabricated structures | Project requirement |

## 9.3 Certifications for Export

### Quality System Certifications

| Certification | Application | Investment | Timeline |
|---------------|-------------|------------|----------|
| ISO 9001 | Quality management | $10K-$25K | 4-8 months |
| ISO 3834 | Welding quality | $12K-$30K | 6-10 months |
| ISO 14001 | Environmental | $12K-$30K | 6-10 months |
| ISO 45001 | Health & safety | $10K-$25K | 6-10 months |

### Industry Certifications

| Certification | Application | Investment | Timeline |
|---------------|-------------|------------|----------|
| ASME U/S/R Stamps | Pressure vessels | $30K-$100K | 12-18 months |
| API Monogram | O&G equipment | $25K-$75K | 12-18 months |
| CE Marking (EN 1090) | EU export structures | $20K-$50K | 8-14 months |
| AWS Certification | Welding | $10K-$25K | 3-6 months |
| AISC Certification | Structural fabricator | $15K-$40K | 6-12 months |

### Personnel Certifications

| Certification | Role | Requirement |
|---------------|------|-------------|
| AWS CWI | Welding Inspector | ASME, structural |
| ASNT Level II/III | NDT Technician | Pressure equipment |
| ASME IX | Welders | Pressure vessels |
| EN ISO 9606 | Welders | EU export |

## 9.4 Market-Specific Requirements

### European Union

| Requirement | Application | Notes |
|-------------|-------------|-------|
| CE Marking | Structural steel | EN 1090 compliance |
| EN Standards | Design/fabrication | Eurocode compliance |
| Material Traceability | All products | Full documentation |
| Quality System | Manufacturing | ISO 3834 or equivalent |

### GCC Markets

| Requirement | Application | Notes |
|-------------|-------------|-------|
| GSO Standards | Products | Technical regulations |
| Local Registration | Doing business | Per country |
| Specification Compliance | Projects | Per tender |
| Pre-qualification | Contractors | Per client |

### Oil & Gas Sector

| Requirement | Application | Notes |
|-------------|-------------|-------|
| API Standards | Equipment | API monogram preferred |
| ASME Codes | Pressure equipment | U/S stamp required |
| Operator Approval | Vendor list | Pre-qualification |
| NACE Standards | Corrosion | Where applicable |

## 9.5 Trade Agreements

### Relevant Agreements

| Agreement | Benefit | Products |
|-----------|---------|----------|
| GAFTA | Zero tariffs Arab League | All products |
| GCC Common Market | Free trade within GCC | All products |
| EU Association | Preferential tariffs | Most products |
| AfCFTA | Emerging African access | All products |

### Rules of Origin

| Agreement | Local Content Requirement |
|-----------|--------------------------|
| GAFTA | 40% local value added |
| EU Association | Varies by product (often 60%) |
| GCC | GCC origin rules |

## 9.6 Export Support Programs

| Country | Programs | Support Type |
|---------|----------|--------------|
| **Saudi Arabia** | SIDF, Export Development | Financing, market access |
| **UAE** | Make it in Emirates, DED | Promotion, facilitation |
| **Egypt** | Export Subsidy, GAFI | Cash incentives, support |
| **Jordan** | Export Development | Market access support |

---

# Dimension 10: Product Standards & Quality Requirements

## 10.1 Structural Steel Standards

### Design Standards

| Standard | Application | Markets |
|----------|-------------|---------|
| AISC 360 | Steel building design | US reference, GCC |
| EN 1993 (Eurocode 3) | Steel structures | EU, international |
| BS 5950 | Steel structures | Legacy UK |
| Local Codes | Building codes | Per country |

### Fabrication Standards

| Standard | Application | Key Requirements |
|----------|-------------|------------------|
| AWS D1.1 | Structural welding | Procedures, welder qualification |
| EN 1090 | Steel structures (EU) | Execution class, CE marking |
| AISC 207 | Quality criteria | Fabricator certification |

### Dimensional Tolerances (Structural)

| Feature | Typical Tolerance | Standard Reference |
|---------|-------------------|-------------------|
| Length | ±3mm or ±1/8" | AWS D1.1, EN 1090 |
| Straightness | L/1000 | Product dependent |
| Cross-section | Per profile standard | Mill tolerances |
| Hole Location | ±1.5mm | Assembly requirements |

## 10.2 Pressure Vessel & Tank Standards

### Codes & Standards

| Code | Application | Jurisdiction |
|------|-------------|--------------|
| ASME BPVC Section VIII | Pressure vessels | Global |
| ASME BPVC Section I | Power boilers | Global |
| API 650 | Atmospheric tanks | O&G global |
| API 620 | Low pressure tanks | O&G global |
| EN 13445 | Unfired pressure vessels | EU |
| PD 5500 | Pressure vessels | UK |

### ASME Requirements

| Requirement | Description |
|-------------|-------------|
| Design | Code calculations, material selection |
| Materials | ASME approved materials |
| Welding | ASME Section IX qualification |
| Fabrication | Procedure compliance |
| NDE | Per code requirements |
| Pressure Test | Hydrostatic/pneumatic |
| Inspection | Authorized Inspector (AI) |
| Stamping | U/S stamp on nameplate |

### NDT Requirements (Pressure)

| Joint Type | Typical NDE | Extent |
|------------|-------------|--------|
| Category A (Longitudinal) | RT or UT | 100% typically |
| Category B (Circumferential) | RT or UT | Per joint efficiency |
| Category C (Flat head) | RT or UT | Per code |
| Category D (Nozzle) | MT or PT + RT/UT | Per code |

## 10.3 Machining Standards

### Dimensional Standards

| Standard | Application | Notes |
|----------|-------------|-------|
| ISO GPS System | Geometric tolerancing | International |
| ASME Y14.5 | GD&T | US reference |
| ISO 2768 | General tolerances | Default |
| Customer Spec | Per drawing | Priority |

### Surface Finish Standards

| Standard | Application |
|----------|-------------|
| ISO 4287 | Surface texture |
| ISO 1302 | Indication on drawings |
| Ra, Rz | Roughness parameters |

### Tolerance Classes

| Feature | Standard (m) | Precision (f) | High Precision (c) |
|---------|--------------|---------------|-------------------|
| Linear (up to 30mm) | ±0.2mm | ±0.1mm | ±0.05mm |
| Linear (30-120mm) | ±0.3mm | ±0.15mm | ±0.08mm |
| Linear (120-400mm) | ±0.5mm | ±0.2mm | ±0.12mm |
| Angular | ±1° | ±30' | ±10' |

## 10.4 Surface Treatment Standards

### Coating Standards

| Standard | Application | Notes |
|----------|-------------|-------|
| ISO 12944 | Corrosion protection | Environment classification |
| SSPC | Surface preparation | US reference |
| ISO 8501 | Visual standards | Surface cleanliness |
| ISO 2808 | Film thickness | Measurement |
| ASTM B117 | Salt spray testing | Corrosion testing |

### Surface Preparation Grades

| Grade | Description | Application |
|-------|-------------|-------------|
| Sa 3 | White metal blast | Critical, immersion |
| Sa 2.5 | Near-white blast | Most coatings |
| Sa 2 | Commercial blast | General |
| St 3 | Very thorough hand | Touch-up |
| St 2 | Thorough hand | Minor prep |

### Galvanizing Standards

| Standard | Application |
|----------|-------------|
| ISO 1461 | Hot-dip galvanizing |
| ASTM A123 | Hot-dip galvanizing (US) |
| ISO 14713 | Zinc coatings guidelines |

### Powder Coating Standards

| Standard | Application |
|----------|-------------|
| ISO 8130 | Powder coating materials |
| Qualicoat | Architectural aluminum |
| GSB | Quality standards |

## 10.5 Material Certification

### Mill Test Certificate Requirements

| Level | Content | Application |
|-------|---------|-------------|
| EN 10204 Type 2.1 | Declaration of compliance | Basic |
| EN 10204 Type 2.2 | Test report | Standard |
| EN 10204 Type 3.1 | Inspection certificate | Critical |
| EN 10204 Type 3.2 | Third-party inspection | ASME, critical |

### Material Traceability

| Requirement | Application | Method |
|-------------|-------------|--------|
| Heat Number Tracking | Pressure equipment | Hard stamp, records |
| Mill Certificates | All structural | Documentation |
| Material Verification | Critical applications | PMI testing |
| Cut List Tracking | Fabrication | Shop systems |

## 10.6 Inspection & Testing

### In-Process Inspection

| Checkpoint | Inspection | Method |
|------------|------------|--------|
| Material Receipt | Verify MTRs, visual | Documentation, inspection |
| Cut Parts | Dimensions | Tape, scale |
| Fit-up | Gap, alignment | Gauges |
| Welding | Visual, NDT | VT + per spec |
| Assembly | Dimensions, tolerances | Measuring equipment |
| Final | Complete checklist | Full inspection |

### Final Inspection Requirements

| Product Type | Typical Requirements |
|--------------|---------------------|
| Structural Steel | Dimensional, visual, weld |
| Pressure Vessels | Dimensional, NDE, pressure test, AI |
| Machined Parts | Dimensional, surface, CMM |
| Tanks | Dimensional, visual, leak test |
| Coated Products | Thickness, adhesion, visual |

---

# Dimension 11: MENA Regional Context

## 11.1 Country Market Profiles

### Saudi Arabia

| Attribute | Details |
|-----------|---------|
| **Market Size** | $12B+ metal fabrication & engineering |
| **Key Sectors** | Construction, O&G, infrastructure, industrial |
| **Major Opportunity** | NEOM, giga projects, Vision 2030 |
| **Local Content** | IKTVA, mandatory localization |
| **Key Cities** | Riyadh, Jeddah, Dammam, Jubail |
| **Regulatory** | SASO standards, contractor classification |

**Giga Projects Impact:**
- NEOM: $500B+ investment, massive steel demand
- Red Sea Project: Tourism infrastructure
- Qiddiya: Entertainment city
- Diriyah Gate: Cultural project
- Pipeline of projects through 2040+

### UAE

| Attribute | Details |
|-----------|---------|
| **Market Size** | $6B+ metal fabrication & engineering |
| **Key Sectors** | Construction, O&G, infrastructure |
| **Strength** | Quality fabricators, hub role |
| **Key Areas** | Abu Dhabi (O&G), Dubai (construction), JAFZA |
| **Regulatory** | ESMA standards |

### Egypt

| Attribute | Details |
|-----------|---------|
| **Market Size** | $4B+ metal fabrication & engineering |
| **Key Sectors** | Construction, industrial, export |
| **Cost Advantage** | Labor, some materials |
| **Export Focus** | Africa, regional |
| **Key Clusters** | 10th of Ramadan, 6th October, Alexandria |
| **Regulatory** | EOS standards |

### Jordan

| Attribute | Details |
|-----------|---------|
| **Market Size** | $1B+ metal fabrication |
| **Key Sectors** | Construction, phosphate industry |
| **Export Focus** | Iraq, regional |
| **Advantage** | Skilled workforce, location |
| **Regulatory** | JISM standards |

### Morocco

| Attribute | Details |
|-----------|---------|
| **Market Size** | $3B+ metal fabrication |
| **Key Sectors** | Automotive, aerospace, construction |
| **Export Focus** | Europe, Africa |
| **Advantage** | EU proximity, FTAs |
| **Clusters** | Casablanca, Tangier (automotive) |

## 11.2 Regional Market Comparison

### Market Size & Growth

| Country | Market Size | Growth Rate | SME Share |
|---------|-------------|-------------|-----------|
| Saudi Arabia | $12B+ | 8-12% | 30% |
| UAE | $6B+ | 4-6% | 35% |
| Egypt | $4B+ | 6-8% | 50% |
| Morocco | $3B+ | 5-7% | 45% |
| Jordan | $1B | 3-5% | 55% |

### Cost Position Index (UAE = 100)

| Cost Factor | UAE | Saudi | Egypt | Jordan | Morocco |
|-------------|-----|-------|-------|--------|---------|
| Labor (skilled) | 100 | 85 | 35 | 50 | 45 |
| Labor (unskilled) | 100 | 70 | 25 | 35 | 30 |
| Steel (local) | 100 | 95 | 95 | 105 | 100 |
| Electricity | 100 | 75 | 45 | 80 | 70 |
| Real Estate | 100 | 65 | 30 | 45 | 40 |

### Competitive Advantages

| Country | Key Advantages |
|---------|----------------|
| **Saudi Arabia** | Scale, projects, local content requirements |
| **UAE** | Quality, hub, logistics |
| **Egypt** | Cost, labor, Africa access |
| **Jordan** | Skills, regional trade, Iraq access |
| **Morocco** | EU access, automotive ecosystem |

## 11.3 Regional Opportunities

### High-Potential Opportunities

| Opportunity | Description | Markets | Potential |
|-------------|-------------|---------|-----------|
| **Giga Projects Supply** | Steel for mega developments | Saudi | Very High |
| **O&G Maintenance** | Ongoing equipment needs | GCC | High |
| **Infrastructure Investment** | Transport, utilities | Saudi, Egypt, UAE | High |
| **Industrial Localization** | Import substitution | Saudi, UAE | High |
| **Renewable Energy** | Solar, wind structures | Saudi, Egypt, Morocco | High |
| **Water Infrastructure** | Desalination, treatment | GCC | High |
| **Africa Export** | Gateway to African markets | Egypt, Morocco | Medium-High |

### Sector-Specific Opportunities

| Sector | Opportunity | Key Markets |
|--------|-------------|-------------|
| Construction | Structural steel for buildings, infrastructure | All |
| Oil & Gas | Equipment, maintenance, modifications | GCC |
| Power | Generation equipment, transmission | Saudi, Egypt |
| Water | Tanks, piping, equipment | GCC |
| Industrial | Equipment, machinery, maintenance | All |
| Automotive | Parts, tooling | Morocco, Egypt |

## 11.4 Regional Challenges

| Challenge | Severity | Markets | Mitigation |
|-----------|----------|---------|------------|
| **Steel Price Volatility** | High | All | Escalation clauses |
| **Skilled Labor Shortage** | High | All | Training, recruitment |
| **Competition from Imports** | Medium | All | Quality, service |
| **Payment Delays** | High | All except GCC | Credit management |
| **Nationalization Quotas** | Medium | Saudi, UAE | Compliance planning |
| **Project Volatility** | Medium | All | Customer diversification |
| **Energy Costs (non-GCC)** | Medium | Egypt, Jordan, Morocco | Efficiency |

## 11.5 Government Support Programs

### Saudi Arabia

| Program | Support Type | Benefit |
|---------|--------------|---------|
| SIDF (Industrial Development Fund) | Financing | Loans up to 75% of project |
| NIDLP | Industrial development | Incentives, infrastructure |
| Local Content (IKTVA) | Market access | Procurement preference |
| MODON | Industrial cities | Land, utilities, services |
| Kafalah | SME guarantee | Credit guarantee |

### UAE

| Program | Support Type | Benefit |
|---------|--------------|---------|
| Make it in Emirates | Manufacturing promotion | Incentives |
| Industrial Strategy | Sector development | Support programs |
| Free Zones (JAFZA, etc.) | Export/import | Tax advantages |
| Emirates Development Bank | Financing | Loans, guarantees |

### Egypt

| Program | Support Type | Benefit |
|---------|--------------|---------|
| Industrial Development | Manufacturing support | Incentives |
| Export Subsidy | Export promotion | Cash incentives |
| Free Zones | Export manufacturing | Tax benefits |
| GAFI | Investment facilitation | Licensing support |
| CBE Subsidized Loans | SME financing | Reduced interest |

## 11.6 Success Factors by Market

### Saudi Arabia
- Local content compliance (IKTVA registration)
- Contractor classification maintenance
- Giga project access (EPC relationships)
- Quality certifications (ISO, ASME)
- Saudization compliance

### UAE
- Quality positioning and certifications
- O&G sector approvals
- JAFZA/free zone presence for export
- Strong engineering capability
- Fast turnaround capability

### Egypt
- Cost competitiveness
- Export orientation and certifications
- Africa market development
- Strong technical capability
- Quality systems for international work

### Jordan
- Iraq market relationships
- Regional trade positioning
- Technical skills emphasis
- Competitive pricing
- Quality certifications

### Morocco
- EU market certifications (CE, EN)
- Automotive sector qualification
- French language capability
- Africa export development
- Cost competitiveness

---

## Agent Data Requirements Summary

### The Drucker (Supervisor)
- Subsector identification and characteristics
- Value chain positioning
- Country market context
- Strategic opportunities

### The Marvin (Diagnostic)
- OEE by equipment type
- Quality metrics (weld rejection, scrap)
- Project delivery performance
- Production KPIs

### The Graham (Finance)
- Margins by subsector and business type
- Steel price exposure and volatility
- Working capital intensity (retention, progress billing)
- Project profitability tracking

### The Ricardo (Export)
- Certification requirements (ASME, EN 1090)
- Market-specific requirements
- Trade agreements
- Export documentation

### The Lovelace (Digital)
- Low baseline score (32/100)
- CAD/CAM integration opportunity
- Job tracking and production systems
- Machine monitoring

### The Mayo (HR)
- Critical welder shortage
- Skilled trades compensation
- Certification tracking
- Training program needs

### The Ohno (Supply Chain)
- Steel supply chain (mills, traders, volatility)
- Price volatility management
- Subcontractor network
- Inventory management

### The Porter (Market)
- Five forces (HIGH supplier power, HIGH rivalry)
- Giga project opportunities
- Competitive positioning strategies
- Market entry requirements

### The Landor (Brand/Sales)
- Certifications as market differentiators
- Customer segment targeting
- Service differentiation
- Technical capability marketing

---

## Critical Thresholds Summary

### Financial Thresholds

| Metric | Good | Warning | Critical |
|--------|------|---------|----------|
| Gross Margin (Fabrication) | >22% | 15-22% | <15% |
| Gross Margin (Machining) | >35% | 25-35% | <25% |
| Net Margin | >8% | 4-8% | <4% |
| DSO | <75 days | 75-100 days | >100 days |
| Cash Conversion Cycle | <60 days | 60-90 days | >90 days |

### Operational Thresholds

| Metric | Good | Warning | Critical |
|--------|------|---------|----------|
| OEE (CNC) | >70% | 55-70% | <55% |
| OEE (Welding) | >55% | 40-55% | <40% |
| First Pass Yield | >95% | 90-95% | <90% |
| Weld Rejection Rate | <3% | 3-5% | >5% |
| On-Time Delivery | >90% | 80-90% | <80% |
| Project Cost Variance | <5% | 5-10% | >10% |

### Workforce Thresholds

| Metric | Good | Warning | Critical |
|--------|------|---------|----------|
| Skilled Trade Turnover | <20% | 20-30% | >30% |
| Certified Welder Ratio | >60% | 40-60% | <40% |
| Training Hours/Year | >24 | 16-24 | <16 |
| Safety (LTIF) | <2.0 | 2-4 | >4.0 |

### Digital Thresholds

| Metric | Good | Warning | Critical |
|--------|------|---------|----------|
| Digital Maturity Score | >45 | 30-45 | <30 |
| CAD/CAM Integration | Yes | Partial | No |
| Job Tracking System | Digital | Semi-digital | Paper |
| Quality Records | Digital | Mixed | Paper |

---

*End of Metal Fabrication & Engineering Sector Knowledge Pack*
*Document Version: 1.0 | December 2025*
