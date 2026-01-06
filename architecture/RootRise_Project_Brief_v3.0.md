# RootRise Platform Development — Master Project Brief
**Last Updated:** January 6, 2026  
**Document Version:** 3.0  
**Status:** Active Development — Documentation Phase Complete

---

## 🎯 Executive Summary

RootRise is an AI-powered SME transformation platform operating under DEVONEERS, targeting the MENA region. The platform uses a multi-agent AI architecture ("The Pantheon") combined with a lens-based diagnostic system to deliver personalized growth roadmaps for SMEs across 31 industry sectors in 6 countries.

**Core Differentiator:** The "&I Philosophy" — AI provides intelligence, humans provide wisdom. Together, they create transformation that actually works. This addresses the 89% failure rate of digital transformation initiatives by keeping humans central to the process.

---

## 👥 Leadership Team & Roles

| Name | Role | Primary Focus |
|------|------|---------------|
| **Ruba** | Co-Founder & CEO | Strategic direction, brand positioning, design system, visual identity |
| **Alaa** | Co-Founder & CSO | Strategy, user experience, multi-agent flexibility, "made for me" vision |
| **Tee** | Product Creative Strategist | "The Ionganic Orchestrator (TIO)" |
---

## 🏗️ Platform Architecture (January 2026)

### Three-Layer System

```
┌─────────────────────────────────────────────────────────────────┐
│                    LAYER 1: LENS SYSTEM                         │
│  17 Strategic Lenses (15 Standard + Crema + Custom)             │
│  User selects transformation focus → Routes questionnaire       │
├─────────────────────────────────────────────────────────────────┤
│                    LAYER 2: THE PANTHEON                        │
│  11 Specialist AI Agents with Named Personas                    │
│  Each agent has expertise domain + personality + methodology    │
├─────────────────────────────────────────────────────────────────┤
│                    LAYER 3: KNOWLEDGE BASE                      │
│  31 Sector Knowledge Packs v2.0                                 │
│  6-Country Coverage (EG, SA, AE, JO, LB, MA)                   │
│  Industry benchmarks, regulations, success patterns             │
└─────────────────────────────────────────────────────────────────┘
```

---

## 🔭 The Lens System (17 Lenses)

Lenses determine the diagnostic focus, question routing, agent activation, and recommendation prioritization.

### Standard Lenses (EYE-001 to EYE-015)

| Code | Name | Primary Focus | Primary Agents |
|------|------|---------------|----------------|
| EYE-001 | Export Expansion | International market entry | Ricardo, Landor |
| EYE-002 | Investment Readiness | Funding preparation | Graham, Drucker |
| EYE-003 | Digital Transformation | Technology adoption | Lovelace, Marvin |
| EYE-004 | Operational Excellence | Efficiency & quality | Marvin, Ohno, Deming |
| EYE-005 | Market Expansion | Growth & positioning | Porter, Landor |
| EYE-006 | Brand Building | Identity & communication | Landor, Porter |
| EYE-007 | Workforce Development | HR & culture | Mayo |
| EYE-008 | Supply Chain Optimization | Logistics & sourcing | Ohno, Marvin |
| EYE-009 | Sustainability & ESG | Environmental & social | Deming, Marvin |
| EYE-010 | Innovation & R&D | New products & services | Lovelace, Porter |
| EYE-011 | Customer Experience | Service & satisfaction | Porter, Landor |
| EYE-012 | Cost Optimization | Profitability improvement | Graham, Marvin, Ohno |
| EYE-013 | Risk & Resilience | Risk management | Deming, Graham |
| EYE-014 | Succession & Governance | Leadership transition | Mayo, Drucker |
| EYE-015 | Partnership & M&A | Strategic alliances | Porter, Ohno |

### Special Lenses

| Code | Name | Purpose |
|------|------|---------|
| EYE-000 / EYE-CREMA | The Crema | Quick wins filter — 30/60/90 day actionable recommendations |
| EYE-CUSTOM | Custom Objective | User-defined transformation goal with AI routing |

### Lens Selection Flow
1. User enters questionnaire
2. Shown lens selection screen with guidance
3. Primary lens chosen (determines main focus)
4. Crema recommended by default (can disable)
5. Optional: Select up to 2 secondary lenses
6. Questions route based on lens configuration

---

## 🏛️ The Pantheon (11 AI Agents)

### Agent Architecture

```
                         ┌─────────────┐
                         │   DRUCKER   │
                         │ Supervisor  │
                         └──────┬──────┘
                                │
        ┌───────────────────────┼───────────────────────┐
        │                       │                       │
   ┌────┴────┐            ┌─────┴─────┐           ┌────┴────┐
   │ GRAHAM  │            │  MARVIN   │           │  PORTER │
   │ Finance │            │ Operations│           │ Strategy│
   └────┬────┘            └─────┬─────┘           └────┬────┘
        │                       │                      │
   ┌────┴────┐    ┌────────┬────┴────┬────────┐  ┌────┴────┐
   │LOVELACE │    │  OHNO  │  DEMING │  MAYO  │  │ RICARDO │
   │ Digital │    │ Supply │ Quality │   HR   │  │ Export  │
   └─────────┘    └────────┴─────────┴────────┘  └────┬────┘
                                                      │
                                                 ┌────┴────┐
                                                 │ LANDOR  │
                                                 │  Brand  │
                                                 └────┬────┘
                                                      │
                                                 ┌────┴────┐
                                                 │  TUFTE  │
                                                 │  Visual │
                                                 └─────────┘
```

### Agent Profiles

| Agent | Full Name | Persona | Domain | Methodology |
|-------|-----------|---------|--------|-------------|
| **DRUCKER** | Peter Drucker | The Conductor | Orchestration & Strategy | Management by Objectives |
| **GRAHAM** | Benjamin Graham | The Numbers Whisperer | Financial Analysis | Value Investing Principles |
| **MARVIN** | The Paranoid Android | The Optimizer | Operations & Efficiency | Lean Manufacturing |
| **LOVELACE** | Ada Lovelace | The Digitizer | Technology & Digital | Digital Maturity Models |
| **MAYO** | Elton Mayo | The People Person | HR & Culture | Human Relations Theory |
| **PORTER** | Michael Porter | The Strategist | Market & Competition | Five Forces, Value Chain |
| **OHNO** | Taiichi Ohno | The Flow Master | Supply Chain & Logistics | Toyota Production System |
| **DEMING** | W. Edwards Deming | The Perfectionist | Quality & Compliance | PDCA, 14 Points |
| **RICARDO** | David Ricardo | The Globalizer | Export & Trade | Comparative Advantage |
| **LANDOR** | Walter Landor | The Storyteller | Brand & Marketing | Brand Architecture |
| **TUFTE** | Edward Tufte | The Visualizer | Data Visualization | Information Design |

### Agent Activation Rules
- **Drucker** always active (orchestration)
- **Graham** always active (financial baseline)
- Other agents activated based on:
  - Selected lens(es)
  - Sector requirements
  - Questionnaire responses
  - Confidence thresholds

---

## 📦 Sector Knowledge Packs (31 Sectors v2.0)

### Coverage by Category

**Manufacturing & Production (8)**
- Food Processing & Beverages
- Textiles & Apparel
- Building Materials & Construction Products
- Chemicals & Plastics
- Pharmaceuticals & Medical Devices
- Electronics & Electrical Equipment
- Automotive Parts & Assembly
- Metal Fabrication & Machinery

**Services (8)**
- Professional Services (Legal, Accounting, Consulting)
- Healthcare Services
- Education & Training
- Hospitality & Tourism
- Transportation & Logistics
- Financial Services (Non-Banking)
- Creative & Media Services
- Facility Management & Security

**Technology (4)**
- Software Development & IT Services
- E-commerce & Digital Platforms
- FinTech
- CleanTech & Renewable Energy

**Trade & Retail (4)**
- Wholesale Distribution
- Retail Trade
- Import/Export Trading
- Franchising & Licensing

**Primary Industries (4)**
- Agriculture & Agribusiness
- Fishing & Aquaculture
- Mining & Quarrying
- Oil & Gas Services

**Specialized (3)**
- Real Estate Development
- Waste Management & Recycling
- Artisanal & Handicrafts

### Knowledge Pack Structure (Each Sector)
```yaml
sector_overview:
  definition, subsectors, value_chain, size_indicators

regional_landscape:
  egypt, saudi_arabia, uae, jordan, lebanon, morocco
  # Each with: market_size, key_players, regulations, opportunities, challenges

operational_benchmarks:
  financial_metrics, operational_metrics, quality_metrics, growth_metrics

diagnostic_focus:
  priority_dimensions, key_questions, red_flags, quick_wins

transformation_pathways:
  digital, export, investment, operational, workforce

agent_instructions:
  DRUCKER, GRAHAM, MARVIN, LOVELACE, MAYO, PORTER, OHNO, DEMING, RICARDO, LANDOR
```

---

## 🌍 Geographic Coverage (6 Countries)

| Country | Code | Currency | Key Characteristics |
|---------|------|----------|---------------------|
| **Egypt** | EG | EGP | Largest SME base, manufacturing hub, currency volatility |
| **Saudi Arabia** | SA | SAR | Vision 2030, Saudization requirements, premium market |
| **UAE** | AE | AED | Free zones, trading hub, high digital maturity |
| **Jordan** | JO | JOD | Services focus, regional stability, qualified workforce |
| **Lebanon** | LB | USD* | Dollarized economy, diaspora networks, crisis context |
| **Morocco** | MA | MAD | EU proximity, automotive cluster, Africa gateway |

*Tunisia removed from coverage in January 2026 to align with sector pack depth*

---

## 📋 Questionnaire System (v2.0)

### Structure
- **Pre-Questionnaire:** Lens Selection (3 questions)
- **11 Core Sections:** ~145 base questions
- **Quick Win Assessment:** 10 questions (if Crema active)
- **Total with conditionals:** ~160 questions
- **Typical completion:** 80-100 questions (based on routing)

### Sections

| Code | Section | Questions | Time |
|------|---------|-----------|------|
| LS | Lens Selection | 3 | 1 min |
| BP | Business Profile | 15 | 3 min |
| FH | Financial Health | 20 | 5 min |
| OP | Operations & Production | 18 | 4 min |
| DM | Digital Maturity | 13 | 3 min |
| WF | Workforce & HR | 11 | 3 min |
| MK | Market & Competition | 10 | 2 min |
| SC | Supply Chain | 12 | 3 min |
| EX | Export Readiness | 15 | 4 min |
| BR | Brand & Marketing | 10 | 2 min |
| CC | Compliance & Certifications | 8 | 2 min |
| QW | Quick Win Assessment | 10 | 2 min |

### Key v2.0 Features
- `lens_relevance` field on every question
- `quick_win_indicator` for Crema filtering
- `effort_level` in options for 30/60/90 day bucketing
- `human_context_prompt` for &I philosophy integration
- Full bilingual support (EN/AR)

---

## 💡 The &I Philosophy

### Core Concept
> "AI provides the intelligence. Humans provide the wisdom. Together, they create transformation that actually works."

### Why It Matters
- **89%** of digital transformation initiatives fail
- Primary cause: Technology imposed without human buy-in
- RootRise keeps humans central to every recommendation

### &I in Practice

| Component | AI Contribution | Human Contribution |
|-----------|-----------------|-------------------|
| **Diagnostics** | Pattern recognition, benchmarking | Context, nuance, "why" behind numbers |
| **Recommendations** | Data-driven options, prioritization | Strategic judgment, relationship factors |
| **Implementation** | Progress tracking, alerts | Execution, adaptation, relationship building |
| **Validation** | Consistency checking | Real-world feasibility assessment |

### Human Context Fields
Throughout the questionnaire, users can add context:
- "Tell us more about this challenge"
- "What makes your situation unique?"
- "Any context that would help us understand better?"

This human input directly influences agent recommendations.

---

## 🎨 Design System (Ruba's Color System v1.0)

### Primary Brand Colors — Bronze/Gold Metallic

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| Bronze Gold | `#B8904A` | Primary CTAs, active states |
| Light Bronze Gold | `#C4965F` | Hover states |
| Deep Bronze | `#9D7E3A` | Active elements |
| Bronze Metallic | `#D4A574` | Gradient overlays |

### Dark Mode Backgrounds — Navy/Charcoal

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| Dark Navy Charcoal | `#0F1419` | Main background |
| Blue-Gray | `#1E2F3E` | Cards & panels |
| Section Dark | `#2B3F52` | Secondary sections |
| Border Dark | `#3A4A5A` | Borders |

### Accent Colors — Bright Teal/Cyan

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| Bright Teal Cyan | `#5DD4C3` | Key highlights, selections |
| Light Bright Teal | `#7DE3D1` | Hover variant |
| Teal Glow | `#4FC5B2` | Glow effects |
| Deep Teal | `#2A5C5C` | DEVONEERS brand |

### Light Mode Colors — Warm Cream/Beige

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| Warm Cream | `#F5F1E8` | Primary light background |
| Sandy Beige | `#EDE8DD` | Subtle variations |
| Pure White | `#FFFFFF` | Cards & inputs |
| Light Beige | `#E8E3D8` | Form sections |

### Mode Usage
- **Dark Mode:** Landing pages, hero sections, agent selection
- **Light Mode:** Forms, questionnaires, interactive sections

---

## 📁 Documentation Inventory (January 2026)

### Core Architecture Documents

| Document | Version | Size | Purpose |
|----------|---------|------|---------|
| RootRise_Infrastructure_Blueprint | v1.2 | 82KB | Complete system architecture |
| RootRise_Infrastructure_QuickRef | v1.2 | 7KB | Quick reference guide |
| RootRise_Questionnaire_Schema | v2.0 | 255KB | Full questionnaire specification |

### Lens Documents (18 files)

| Document | Size | Description |
|----------|------|-------------|
| EYE-000_The_Crema.md | 23KB | Quick wins system |
| EYE-001_Export_Readiness.md | 16KB | Export lens |
| EYE-002_Investment_Readiness.md | 45KB | Investment lens |
| EYE-003_Digital_Transformation.md | 14KB | Digital lens |
| EYE-004 through EYE-015 | ~60KB each | Standard lenses |
| EYE-CREMA_Quick_Wins.md | 22KB | Crema implementation |
| EYE-CUSTOM_Custom_Objective.md | 19KB | Custom lens |

### Sector Knowledge Packs (31 files)

Format: `SECTOR-XXX_[Name]_v2.0.md`

Examples:
- SECTOR-001_Food_Processing_Beverages_v2.0.md
- SECTOR-002_Textiles_Apparel_v2.0.md
- SECTOR-031_Artisanal_Handicrafts_v2.0.md

### Supporting Documents

| Document | Purpose |
|----------|---------|
| RootRise_Agent_QuickRef.md | Agent quick reference |
| RootRise_Questionnaire_Architecture_Decisions.md | Design rationale |
| docs.json | GitHub Pages metadata |

---

## 📊 Key Metrics & Impact Claims

| Metric | Value | Context |
|--------|-------|---------|
| SME Network | 200+ | Current relationships (Tee's network) |
| Jobs Impacted | 12,450 | Through SME growth |
| GDP Contribution | $45M | Economic impact |
| MENA Countries | 6 | Geographic reach |
| Due Diligence Time Saved | 85% | For investors |
| Digital Transformation Failure Rate | 89% | Problem we solve |
| Success Rate Improvement | 3x | Our value prop |
| Sector Coverage | 31 | Industry knowledge packs |
| AI Agents | 11 | The Pantheon |
| Strategic Lenses | 17 | Transformation focuses |

---

## 🎯 Value Propositions by Audience

### For SMEs
- AI diagnostics in 30 minutes
- Personalized growth roadmaps
- Quick wins in 30/60/90 days (The Crema)
- Resource & funding matching
- Expert validation through &I approach

### For Investors
- AI-powered deal scoring
- 85% faster due diligence
- Portfolio health monitoring
- Exit readiness tracking
- Standardized assessment across sectors

### For Governments
- Sector-wide analytics
- Job creation tracking
- GDP contribution metrics
- Policy impact modeling
- SDG alignment reporting

---

## 🔧 Technical Decisions

### Current Stack (MVP)
- Static HTML for website
- Markdown documentation
- GitHub Pages hosting
- No backend yet

### Planned Architecture
- Multi-agent orchestration system
- Vector database for knowledge packs
- Real-time questionnaire engine
- Dashboard with visualization (Tufte-inspired)

### Documentation Standards
- YAML-style schemas in markdown
- Bilingual (EN/AR) throughout
- Version controlled
- Cross-referenced

---

## 📅 Development Timeline

### Completed (Dec 2025 - Jan 2026)
- [x] 31 Sector Knowledge Packs v2.0
- [x] 11 Agent Architecture (The Pantheon)
- [x] 17 Lens System
- [x] Questionnaire Schema v2.0
- [x] Infrastructure Blueprint v1.2
- [x] Color System v1.0
- [x] Website V18.1

### In Progress
- [ ] GitHub documentation upload
- [ ] docs.json generation
- [ ] Final validation review

### Upcoming
- [ ] Backend architecture design
- [ ] Agent orchestration implementation
- [ ] Questionnaire UI development
- [ ] Dashboard development
- [ ] Arabic RTL support
- [ ] Mobile optimization

---

## 🔗 Key Relationships & Integrations

### External Partnerships (Potential)
- EBRD Star Venture Programme
- Dubai Future Foundation
- CIARN (gender-transformative AI initiatives)

### Integration Points
- Sector packs ↔ Questionnaire (BP_005 triggers pack loading)
- Lenses ↔ Questions (LS_001 routes to configurations)
- Agents ↔ Dimensions (mapped in schema Section 18)
- Blueprint ↔ All components (master reference)

---

## 📝 Terminology Reference

| Term | Definition |
|------|------------|
| **The Pantheon** | The 11 AI agents collectively |
| **The Crema** | Quick-win filtering system (30/60/90 days) |
| **&I Philosophy** | AI + Human collaboration approach |
| **TIO** | The Ionganic Orchestrator (Tee's methodology) |
| **TeerAIned** | Tee + AI + Trained — human-AI collaboration concept |
| **Lens** | Strategic focus that shapes the diagnostic |
| **Dimension** | Scoring category (11 total) |
| **Sector Pack** | Industry-specific knowledge base |

---

## 🔍 How to Use This Document

1. **Starting a new conversation:** Upload this document for full context
2. **After major updates:** Request an updated version
3. **For handoffs:** Share with team members or AI assistants
4. **For reference:** Search by section headers

---

## 📜 Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Dec 4, 2025 | Team | Initial comprehensive brief |
| 1.1 | Dec 5, 2025 | Team | Corrected team roles |
| 2.0 | Dec 5, 2025 | Ruba | Added complete Color System v1.0 |
| **3.0** | **Jan 6, 2026** | **Tee** | Major overhaul: Added Pantheon (11 agents), Lens System (17 lenses), 31 Sector Packs v2.0, Questionnaire v2.0, Blueprint v1.2, 6-country alignment, &I Philosophy expansion, complete documentation inventory |

---

## 📎 Quick Links (GitHub)

*To be populated after upload:*
- Documentation Index: `/docs/index.html`
- Blueprint: `/docs/architecture/RootRise_Infrastructure_Blueprint_v1.2.md`
- Questionnaire Schema: `/docs/questionnaire/RootRise_Questionnaire_Schema_v2.0.md`
- Sector Packs: `/docs/sectors/`
- Lens Documents: `/docs/lenses/`

---

*This document is maintained by Tee (Product Creative Strategist). Last updated: January 6, 2026.*
*Part of the RootRise &I SME Transformation Platform by DEVONEERS.*
