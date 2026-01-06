# RootRise Agent Quick Reference

**Version:** 1.0  
**Last Updated:** January 5, 2026  
**Total Agents:** 11 (3 Core + 6 Add-On + 2 Utility)  

---

## The Pantheon at a Glance

| Agent | Named After | Domain | Badge | Always Active? |
|-------|-------------|--------|-------|----------------|
| **The Drucker** | Peter Drucker | Supervisor | CORE | ✅ Yes |
| **The Marvin** | Marvin Bower | Operations | CORE | ✅ Yes |
| **The Graham** | Benjamin Graham | Finance | CORE | ✅ Yes |
| **The Ricardo** | David Ricardo | Export & Trade | ADD-ON | User selects |
| **The Lovelace** | Ada Lovelace | Digital & Tech | ADD-ON | User selects |
| **The Mayo** | Elton Mayo | HR & Organization | ADD-ON | User selects |
| **The Ohno** | Taiichi Ohno | Supply Chain & Lean | ADD-ON | User selects |
| **The Porter** | Michael Porter | Market & Competition | ADD-ON | User selects |
| **The Landor** | Walter Landor | Packaging & Brand | ADD-ON | User selects |
| **The Deming** | W. Edwards Deming | Quality Validation | UTILITY | ✅ Yes |
| **The Tufte** | Edward Tufte | Report Generation | UTILITY | ✅ Yes |

---

## Core Agents (Always Execute)

### The Drucker — Supervisor Agent
| Attribute | Value |
|-----------|-------|
| **Named After** | Peter Drucker (1909-2005) — Father of Modern Management |
| **Domain** | Orchestration & Planning |
| **Primary Function** | Coordinates diagnostic flow, interprets lenses, routes to specialists |
| **Sector Dimensions** | 1 (Industry Classification), 11 (MENA Context) |
| **Icon** | 🎯 |

**Responsibilities:**
- Initialize diagnostic session
- Process lens configuration
- Determine agent execution order
- Handle custom lens interpretation
- Coordinate HITL gates

---

### The Marvin — Diagnostics Agent
| Attribute | Value |
|-----------|-------|
| **Named After** | Marvin Bower (1903-2003) — McKinsey Architect |
| **Domain** | Operational Diagnostics |
| **Primary Function** | Assesses operations, processes, quality, efficiency |
| **Sector Dimensions** | 1, 3, 4, 7, 8 |
| **Icon** | 🔍 |

**Assesses:**
- Process maturity and documentation
- Quality management systems
- Operational efficiency metrics
- Regulatory compliance gaps
- Workforce operational capabilities

---

### The Graham — Finance Agent
| Attribute | Value |
|-----------|-------|
| **Named After** | Benjamin Graham (1894-1976) — Father of Value Investing |
| **Domain** | Financial Analysis |
| **Primary Function** | Evaluates financial health, funding readiness, capital structure |
| **Sector Dimensions** | 2, 1, 11 |
| **Icon** | 💰 |

**Assesses:**
- Financial health and stability
- Profitability and margin analysis
- Working capital management
- Funding readiness
- Investment attractiveness

---

## Add-On Agents (User Selects)

### The Ricardo — Export & Trade Agent
| Attribute | Value |
|-----------|-------|
| **Named After** | David Ricardo (1772-1823) — Comparative Advantage Theory |
| **Domain** | Export & International Trade |
| **Primary Function** | Assesses export readiness, international compliance, market entry |
| **Sector Dimensions** | 9, 10, 4, 11 |
| **Icon** | 🌍 |
| **Auto-Selected By** | EYE-001 (Export Readiness) |

**Assesses:**
- Export certification requirements
- Target market opportunities
- Trade compliance and documentation
- International logistics readiness
- Currency and payment considerations

---

### The Lovelace — Digital & Technology Agent
| Attribute | Value |
|-----------|-------|
| **Named After** | Ada Lovelace (1815-1852) — First Computer Programmer |
| **Domain** | Digital & Technology |
| **Primary Function** | Evaluates digital maturity, tech stack, automation opportunities |
| **Sector Dimensions** | 6, 3, 7 |
| **Icon** | 💻 |
| **Auto-Selected By** | EYE-003 (Digital Transformation), EYE-010 (Innovation) |

**Assesses:**
- Digital maturity level
- Current technology stack
- Automation opportunities
- Data readiness
- Digital skills gaps

---

### The Mayo — HR & Organization Agent
| Attribute | Value |
|-----------|-------|
| **Named After** | Elton Mayo (1880-1949) — Human Relations Movement |
| **Domain** | HR & Organization Development |
| **Primary Function** | Evaluates workforce, culture, organizational structure |
| **Sector Dimensions** | 7, 1, 11 |
| **Icon** | 👥 |
| **Auto-Selected By** | EYE-007 (Workforce), EYE-014 (Succession) |

**Assesses:**
- Organizational structure effectiveness
- Workforce capabilities and gaps
- Culture and engagement
- Succession readiness
- Owner/key person dependency

---

### The Ohno — Supply Chain & Lean Agent
| Attribute | Value |
|-----------|-------|
| **Named After** | Taiichi Ohno (1912-1990) — Toyota Production System Creator |
| **Domain** | Supply Chain & Lean Operations |
| **Primary Function** | Identifies waste, optimizes supply chain, implements lean principles |
| **Sector Dimensions** | 8, 3, 6, 7 |
| **Icon** | 🔗 |
| **Auto-Selected By** | EYE-004 (Operations), EYE-008 (Supply Chain), EYE-012 (Cost) |

**Assesses:**
- Supply chain efficiency
- Waste identification (8 types)
- Inventory management
- Logistics optimization
- Lean implementation readiness

---

### The Porter — Market & Competition Agent
| Attribute | Value |
|-----------|-------|
| **Named After** | Michael Porter (1947-) — Competitive Strategy Pioneer |
| **Domain** | Market & Competitive Strategy |
| **Primary Function** | Analyzes competitive position, market dynamics, strategic options |
| **Sector Dimensions** | 5, 1, 2, 11 |
| **Icon** | 📊 |
| **Auto-Selected By** | EYE-002 (Investment), EYE-005 (Market), EYE-015 (M&A) |

**Assesses:**
- Competitive positioning
- Market dynamics (Five Forces)
- Strategic differentiation
- Growth opportunities
- Partnership/M&A attractiveness

---

### The Landor — Packaging & Brand Agent
| Attribute | Value |
|-----------|-------|
| **Named After** | Walter Landor (1913-1995) — Brand Design Pioneer |
| **Domain** | Packaging, Labeling & Brand Compliance |
| **Primary Function** | Evaluates packaging for export markets, brand positioning |
| **Sector Dimensions** | 10, 9, 11 |
| **Icon** | 🎨 |
| **Auto-Selected By** | EYE-001 (Export), EYE-006 (Brand) |

**Assesses:**
- Packaging compliance by market
- Labeling requirements
- Brand visual identity
- Export packaging readiness
- Sustainability packaging

---

## Utility Agents (Always Execute)

### The Deming — Quality Validation Agent
| Attribute | Value |
|-----------|-------|
| **Named After** | W. Edwards Deming (1900-1993) — Quality Management Pioneer |
| **Domain** | Cross-Agent Quality Validation |
| **Primary Function** | Validates findings across agents, ensures consistency, flags conflicts |
| **Sector Dimensions** | All (1-11) |
| **Icon** | ✓ |

**Responsibilities:**
- Cross-validate agent findings
- Identify conflicts between agents
- Calculate confidence scores
- Flag items for HITL review
- Ensure recommendation consistency

---

### The Tufte — Report Generation Agent
| Attribute | Value |
|-----------|-------|
| **Named After** | Edward Tufte (1942-) — Information Visualization Pioneer |
| **Domain** | Report Synthesis & Visualization |
| **Primary Function** | Generates final reports, applies lens priorities, creates visualizations |
| **Sector Dimensions** | All (1-11) |
| **Icon** | 📄 |

**Responsibilities:**
- Synthesize all agent findings
- Apply lens-based prioritization
- Generate executive summaries
- Create data visualizations
- Format final deliverable

---

## Agent-to-Dimension Mapping

```
AGENT           DIMENSIONS ACCESSED
─────────────────────────────────────────
Drucker         1, 11
Marvin          1, 3, 4, 7, 8
Graham          2, 1, 11
Ricardo         9, 10, 4, 11
Lovelace        6, 3, 7
Mayo            7, 1, 11
Ohno            8, 3, 6, 7
Porter          5, 1, 2, 11
Landor          10, 9, 11
Deming          All (1-11)
Tufte           All (1-11)
```

**Dimension Key:**
1. Industry Classification | 2. Financial Benchmarks | 3. Operational KPIs
4. Regulatory Landscape | 5. Competitive Dynamics | 6. Digital Maturity
7. Workforce Norms | 8. Supply Chain | 9. Export Requirements
10. Packaging & Labeling | 11. MENA Regional Context

---

## Execution Flow

```
                    ┌──────────────┐
                    │   DRUCKER    │
                    │ (Supervisor) │
                    └──────┬───────┘
                           │
              ┌────────────┴────────────┐
              │                         │
              ▼                         ▼
       ┌──────────┐              ┌──────────┐
       │  MARVIN  │              │  GRAHAM  │
       │  (Ops)   │              │(Finance) │
       └────┬─────┘              └────┬─────┘
            │                         │
    ┌───────┼───────┐         ┌──────┼──────┐
    ▼       ▼       ▼         ▼      ▼      ▼
┌──────┐┌──────┐┌──────┐ ┌──────┐┌──────┐┌──────┐
│OHNO  ││MAYO  ││LOVELCE││PORTER││RICARDO││LANDOR│
│Supply││ HR   ││Digital││Market││Export ││Packag│
└──┬───┘└──┬───┘└───┬───┘└──┬───┘└───┬───┘└───┬──┘
   └───────┴────────┴───────┴────────┴────────┘
                         │
                         ▼
                  ┌──────────┐
                  │  DEMING  │
                  │(Quality) │
                  └────┬─────┘
                       │
                       ▼
                  ┌──────────┐
                  │  TUFTE   │
                  │(Reports) │
                  └──────────┘
```

---

## File Reference

| File | Description |
|------|-------------|
| `RootRise_Core_Agent_Prompts.md` | Drucker, Marvin, Graham prompts |
| `RootRise_AddOn_Agent_Prompts.md` | 6 specialist agent prompts |
| `RootRise_Utility_Agent_Prompts.md` | Deming, Tufte prompts |
| `RootRise_Infrastructure_Blueprint_v1.1.md` | Complete technical specification |

---

*11 agents. 6 industry pioneers. One unified intelligence system.*
