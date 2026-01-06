# RootRise v6.0 — Infrastructure Quick Reference

**Version:** 1.2 | **Updated:** January 6, 2026 | **Author:** Tee (The Ionganic Orchestrator - TIO)

---

## The Three Layers at a Glance

```
┌─────────────────────────────────────────────────────────────────┐
│  LAYER 1: THE PANTHEON        │  WHO analyzes?                 │
│  11 Agents                    │  3 Core + 6 Add-On + 2 Utility │
├───────────────────────────────┼────────────────────────────────┤
│  LAYER 2: MY SECTOR           │  WITH WHAT context?            │
│  31 Sectors                   │  11 dimensions × 6 countries   │
├───────────────────────────────┼────────────────────────────────┤
│  LAYER 3: THE &EYE            │  TOWARD WHAT goal?             │
│  17 Lenses                    │  1 Featured + 15 Std + 1 Custom│
└─────────────────────────────────────────────────────────────────┘
```

---

## Agents Quick Reference

### Core Agents (Always Active)
| Agent | Domain | Icon |
|-------|--------|------|
| **Drucker** | Supervisor & Orchestration | 🎯 |
| **Marvin** | Operational Diagnostics | 🔍 |
| **Graham** | Financial Analysis | 💰 |

### Add-On Agents (User Selects)
| Agent | Domain | Icon | Auto-Selected By |
|-------|--------|------|------------------|
| **Ricardo** | Export & Trade | 🌍 | EYE-001 Export |
| **Lovelace** | Digital & Technology | 💻 | EYE-003 Digital |
| **Mayo** | HR & Organization | 👥 | EYE-007 Workforce, EYE-014 Succession |
| **Ohno** | Supply Chain & Lean | 🔗 | EYE-004 Ops, EYE-008 Supply, EYE-012 Cost |
| **Porter** | Market & Competition | 📊 | EYE-002 Investment, EYE-005 Market, EYE-015 M&A |
| **Landor** | Packaging & Brand | 🎨 | EYE-001 Export, EYE-006 Brand |

### Utility Agents (Always Active)
| Agent | Domain | Icon |
|-------|--------|------|
| **Deming** | Quality Validation | ✓ |
| **Tufte** | Report Generation | 📄 |

---

## Lenses Quick Reference

### Featured (Pre-selected)
| ID | Name | Icon | Focus |
|----|------|------|-------|
| **EYE-CREMA** | The Crema | ☕ | Quick wins in 30-60-90 days |

### Growth (4 lenses)
| ID | Name | Icon | Core Question |
|----|------|------|---------------|
| **EYE-001** | Export Readiness | 🌍 | Ready to sell internationally? |
| **EYE-002** | Investment Readiness | 💰 | Ready for investors? |
| **EYE-005** | Market Expansion | 📈 | Growth opportunities? |
| **EYE-006** | Brand Building | 🎨 | Brand strong enough? |

### Operations (3 lenses)
| ID | Name | Icon | Core Question |
|----|------|------|---------------|
| **EYE-003** | Digital Transformation | 💻 | Digitally mature? |
| **EYE-004** | Operational Excellence | ⚙️ | Operations efficient? |
| **EYE-012** | Cost Optimization | 📊 | Where are cost leaks? |

### Impact (6 lenses)
| ID | Name | Icon | Core Question |
|----|------|------|---------------|
| **EYE-007** | Workforce Development | 👥 | Team optimized? |
| **EYE-008** | Supply Chain | 🔗 | Supply chain resilient? |
| **EYE-009** | Sustainability & ESG | 🌱 | Sustainable practices? |
| **EYE-010** | Innovation & R&D | 💡 | Ready to innovate? |
| **EYE-011** | Customer Experience | ⭐ | Customers happy? |
| **EYE-013** | Risk & Resilience | 🛡️ | Prepared for disruption? |

### Transition (2 lenses)
| ID | Name | Icon | Core Question |
|----|------|------|---------------|
| **EYE-014** | Succession & Governance | 👤 | Leadership transition ready? |
| **EYE-015** | Partnership & M&A | 🤝 | Deal ready? |

### Custom
| ID | Name | Icon | Behavior |
|----|------|------|----------|
| **EYE-CUSTOM** | Custom Objective | ✨ | AI interprets user goal |

---

## Lens Selection Rules

```
THE CREMA (EYE-CREMA)
├─ Pre-selected by default
├─ Can be deselected
├─ Combines with ALL lenses
└─ Acts as FILTER (extracts quick wins)

STANDARD LENSES (EYE-001 to EYE-015)
├─ Select up to 3 simultaneously
├─ Can combine with each other
└─ Can combine with The Crema

CUSTOM LENS (EYE-CUSTOM)
├─ EXCLUSIVE - cannot combine with standard
├─ CAN combine with The Crema
└─ Requires AI interpretation of user goal
```

---

## Sectors Quick Reference

| Type | Count | Examples |
|------|-------|----------|
| **Industrial** | 14 | Food & Beverage, Textiles, Automotive, Pharma |
| **Services** | 15 | Healthcare, Retail, Tech, Professional Services |
| **Creative** | 1 | Creative Industries |
| **Micro** | 1 | Home-Based & Micro Enterprise |
| **TOTAL** | **31** | |

### Countries Covered
EG (Egypt) | SA (Saudi Arabia) | AE (UAE) | JO (Jordan) | LB (Lebanon) | MA (Morocco)

---

## Key Metrics

| Metric | Value |
|--------|-------|
| Total Agents | 11 |
| Transformation Lenses | 17 |
| Sector Knowledge Packs | 31 |
| Dimensions per Sector | 11 + Growth Pathways + Strategic Summary |
| Questionnaire Sections | 10 |
| Total Questions | ~145 |
| HITL Checkpoints | 4 |
| Target Diagnostic Time | 30 min (user) |
| Target Processing Time | < 120 sec (AI) |

---

## Technology Stack

| Component | Technology |
|-----------|------------|
| API | FastAPI |
| Orchestration | LangGraph |
| Database | PostgreSQL |
| Session Store | Redis |
| Vector DB | Qdrant |
| Object Store | S3 |
| LLM | OpenAI GPT-4o |
| Embeddings | text-embedding-3-small |

---

## HITL Gates

| Gate | Trigger | Handler |
|------|---------|---------|
| **Gate 1** | Data quality < 70%, Custom lens | Associate |
| **Gate 2** | Confidence < 70%, Cross-agent conflict | Senior Expert |
| **Gate 3** | Investment > $50K, Major pivot | Senior Expert |
| **Gate 4** | Always (final review) | SME Owner |

---

## Document References

| Document | Purpose |
|----------|---------|
| `RootRise_Infrastructure_Blueprint_v1.2.md` | Complete technical spec |
| `RootRise_Eye_Lens_Framework_v2.md` | Lens system details |
| `RootRise_Sector_Knowledge_Framework_v2.md` | Sector structure |
| `RootRise_Core_Agent_Prompts.md` | Drucker, Marvin, Graham |
| `RootRise_AddOn_Agent_Prompts.md` | 6 specialist agents |
| `RootRise_Utility_Agent_Prompts.md` | Deming, Tufte |
| `EYE-000_The_Crema.md` | Quick wins lens |
| `EYE-CUSTOM_Custom_Objective.md` | Custom lens |

---

**Version 1.2** | Changes from v1.1: Added The Crema, Custom Objective, updated lens count to 17, fixed lens numbering
