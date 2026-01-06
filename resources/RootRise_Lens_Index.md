# RootRise Transformation Lens Index

**Version:** 1.0  
**Last Updated:** January 5, 2026  
**Total Lenses:** 17 (1 Featured + 15 Standard + 1 Custom)  

---

## Quick Reference

| ID | Name | Category | Icon | User Statement | Primary Agents |
|----|------|----------|------|----------------|----------------|
| **EYE-CREMA** | The &Eye Crema | Featured | ☕ | Quick wins in 30-60-90 days | Ohno, Graham |
| **EYE-001** | Export Readiness | Growth | 🌍 | I want to sell internationally | Ricardo, Landor |
| **EYE-002** | Investment Readiness | Growth | 💰 | I want to raise capital | Graham, Porter |
| **EYE-003** | Digital Transformation | Operations | 💻 | I want to modernize | Lovelace, Marvin |
| **EYE-004** | Operational Excellence | Operations | ⚙️ | I want to run better | Marvin, Ohno |
| **EYE-005** | Market Expansion | Growth | 📈 | I want to grow my market | Porter, Ricardo |
| **EYE-006** | Brand Building | Growth | 🎨 | I want to strengthen my brand | Landor, Porter |
| **EYE-007** | Workforce Development | Impact | 👥 | I want to build my team | Mayo, Marvin |
| **EYE-008** | Supply Chain Optimization | Impact | 🔗 | I want efficient supply chain | Ohno, Ricardo |
| **EYE-009** | Sustainability & ESG | Impact | 🌱 | I want to be sustainable | Marvin, Ohno |
| **EYE-010** | Innovation & R&D | Impact | 💡 | I want to innovate | Lovelace, Porter |
| **EYE-011** | Customer Experience | Impact | ⭐ | I want happier customers | Porter, Lovelace |
| **EYE-012** | Cost Optimization | Operations | 📊 | I want better margins | Graham, Ohno |
| **EYE-013** | Risk & Resilience | Impact | 🛡️ | I want to be prepared | Marvin, Ohno |
| **EYE-014** | Succession & Governance | Transition | 👤 | I want to transition leadership | Graham, Mayo |
| **EYE-015** | Partnership & M&A | Transition | 🤝 | I want to find a partner | Graham, Porter |
| **EYE-CUSTOM** | Custom Objective | Custom | ✨ | I have a specific goal | (AI-determined) |

---

## Lenses by Category

### Featured (Pre-selected by default)
| Lens | Focus | Combines With |
|------|-------|---------------|
| **The &Eye Crema** | 30-60-90 day quick wins | All lenses (acts as filter) |

### Growth (4 lenses)
| Lens | Focus | Auto-Selects |
|------|-------|--------------|
| Export Readiness | International market entry | Ricardo, Landor |
| Investment Readiness | Investor attraction, valuation | Porter |
| Market Expansion | Domestic & regional growth | Porter |
| Brand Building | Brand positioning, identity | Landor, Porter |

### Operations (3 lenses)
| Lens | Focus | Auto-Selects |
|------|-------|--------------|
| Digital Transformation | Tech modernization | Lovelace |
| Operational Excellence | Process optimization | Ohno |
| Cost Optimization | Margin improvement | Ohno |

### Impact (6 lenses)
| Lens | Focus | Auto-Selects |
|------|-------|--------------|
| Workforce Development | Team building, HR | Mayo |
| Supply Chain Optimization | Logistics efficiency | Ohno |
| Sustainability & ESG | Environmental, social, governance | Ohno |
| Innovation & R&D | Product development | Lovelace |
| Customer Experience | Service quality | Porter |
| Risk & Resilience | Business continuity | None |

### Transition (2 lenses)
| Lens | Focus | Auto-Selects |
|------|-------|--------------|
| Succession & Governance | Leadership transition | Mayo |
| Partnership & M&A | Strategic deals, exit | Porter |

### Custom (1 lens)
| Lens | Focus | Behavior |
|------|-------|----------|
| Custom Objective | User-defined goal | Exclusive (except Crema) |

---

## Selection Rules

### The Crema
- ✅ Pre-selected by default
- ✅ Can be deselected
- ✅ Combines with ALL other lenses
- ✅ Acts as a FILTER (prioritizes quick wins)

### Standard Lenses
- ✅ Can select up to 3 simultaneously
- ✅ Can combine with each other
- ✅ Can combine with The Crema

### Custom Objective
- ❌ Cannot combine with standard lenses
- ✅ Can combine with The Crema
- ✅ AI interprets user description to configure agents

---

## Agent Priority Matrix (Simplified)

```
                  Graham | Marvin | Ricardo | Lovelace | Mayo | Ohno | Porter | Landor
─────────────────────────────────────────────────────────────────────────────────────
EYE-CREMA           ★★     ★        -         -        -      ★★★     -        -
EYE-001 Export       -      -       ★★★       -        -       ★      -       ★★★
EYE-002 Investment  ★★★     ★        -         -        ★       -     ★★        -
EYE-003 Digital      -      ★        -        ★★★       ★       -      -        -
EYE-004 Operations   -     ★★        -         ★        -      ★★★     -        -
EYE-005 Market       ★      -        ★         -        -       -     ★★★       -
EYE-006 Brand        -      -        -         ★        -       -      ★★      ★★★
EYE-007 Workforce    ★      ★        -         -       ★★★      -       -        -
EYE-008 Supply       -      ★        ★         -        -      ★★★      -        ★
EYE-009 ESG          ★     ★★        -         -        ★      ★★       -        ★
EYE-010 Innovation   -      ★        -        ★★★       -       -      ★★        -
EYE-011 Customer     -      ★        -         ★★       -       -      ★★        ★
EYE-012 Cost        ★★★     ★        -         -        -      ★★       ★        -
EYE-013 Risk         ★     ★★        -         -        -      ★★       -        -
EYE-014 Succession  ★★      ★        -         -       ★★★      -       -        -
EYE-015 M&A         ★★★     ★        -         -        ★       -      ★★        -

★★★ = Primary (1.4-1.5x weight)  |  ★★ = Secondary (1.2-1.3x)  |  ★ = Support (1.0-1.1x)
```

---

## File Reference

| File | Description |
|------|-------------|
| `EYE-000_The_Crema.md` | Featured quick wins lens |
| `EYE-001_Export_Readiness.md` | Export lens specification |
| `EYE-002_Investment_Readiness.md` | Investment lens specification |
| `EYE-003_Digital_Transformation.md` | Digital lens specification |
| `EYE-004_Operational_Excellence.md` | Operations lens specification |
| `EYE-005_Market_Expansion.md` | Market lens specification |
| `EYE-006_Brand_Building.md` | Brand lens specification |
| `EYE-007_Workforce_Development.md` | Workforce lens specification |
| `EYE-008_Supply_Chain_Optimization.md` | Supply chain lens specification |
| `EYE-009_Sustainability_ESG.md` | ESG lens specification |
| `EYE-010_Innovation_RD.md` | Innovation lens specification |
| `EYE-011_Customer_Experience.md` | Customer lens specification |
| `EYE-012_Cost_Optimization.md` | Cost lens specification |
| `EYE-013_Risk_Resilience.md` | Risk lens specification |
| `EYE-014_Succession_Governance.md` | Succession lens specification |
| `EYE-015_Partnership_MA.md` | M&A lens specification |
| `EYE-CUSTOM_Custom_Objective.md` | Custom lens specification |
| `RootRise_Eye_Lens_Framework_v2.md` | Complete framework document |

---

## Category Colors (UI Reference)

| Category | Color | Hex |
|----------|-------|-----|
| Featured | Gold | `#F5C563` |
| Growth | Bright Teal | `#5DD4C3` |
| Operations | Steel Blue | `#4A90A4` |
| Impact | Leaf Green | `#7CB342` |
| Transition | Warm Brown | `#8B7355` |
| Custom | Bronze Gold | `#B8904A` |

---

*17 lenses. 6 categories. Infinite transformation paths.*
