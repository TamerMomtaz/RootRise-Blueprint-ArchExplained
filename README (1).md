# RootRise Technical Documentation Hub

**Version:** 6.0  
**Last Updated:** January 2026  
**Status:** Production-Ready Architecture  

---

## 🚀 What is RootRise?

RootRise is an AI-powered SME transformation platform that delivers comprehensive business diagnostics in **2 minutes** versus traditional 6-month consulting engagements. Built by DEVONEERS with 30+ years of MENA region SME expertise.

### The Three Configuration Layers

```
┌─────────────────────────────────────────────────────────────────┐
│                    ROOTRISE v6.0 ARCHITECTURE                    │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  LAYER 1: THE PANTHEON           "WHO analyzes?"                │
│  └─ 11 specialist AI agents named after business pioneers       │
│                                                                  │
│  LAYER 2: MY SECTOR              "WITH WHAT context?"           │
│  └─ 31 industry sectors with MENA-specific intelligence         │
│                                                                  │
│  LAYER 3: THE &EYE               "TOWARD WHAT goal?"            │
│  └─ 17 transformation lenses for goal-focused analysis          │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## 📁 Documentation Structure

### `/architecture`
Core technical specifications for implementation.

| Document | Description |
|----------|-------------|
| [Infrastructure Blueprint v1.1](architecture/RootRise_Infrastructure_Blueprint_v1.1.md) | Complete technical architecture (87 KB) |
| [Infrastructure QuickRef v1.1](architecture/RootRise_Infrastructure_QuickRef_v1.1.md) | One-page implementation reference |

### `/agents`
The Pantheon - 11 specialist AI agents.

| Document | Description |
|----------|-------------|
| [Core Agent Prompts](agents/RootRise_Core_Agent_Prompts.md) | Drucker, Marvin, Graham (always active) |
| [Add-On Agent Prompts](agents/RootRise_AddOn_Agent_Prompts.md) | Ricardo, Lovelace, Mayo, Ohno, Porter, Landor |
| [Utility Agent Prompts](agents/RootRise_Utility_Agent_Prompts.md) | Deming, Tufte (validation & reporting) |

### `/Sector Knowledge V2 2026`
31 industry sectors with comprehensive intelligence.

| Document | Description |
|----------|-------------|
| [Sector Knowledge Framework v2](Sector%20Knowledge%20V2%202026/RootRise_Sector_Knowledge_Framework_v2.md) | Schema and structure guide |
| [31 Sector Files](Sector%20Knowledge%20V2%202026/) | Complete sector packs (~85 KB each) |

### `/Lenses`
The &Eye - 17 transformation lenses.

| Document | Description |
|----------|-------------|
| [Lens Framework v2](Lenses/RootRise_Eye_Lens_Framework_v2.md) | Complete lens system guide |
| [EYE-000: The Crema](Lenses/EYE-000_The_Crema.md) | Quick wins lens (signature feature) |
| [EYE-001 through EYE-015](Lenses/) | 15 standard transformation lenses |
| [EYE-CUSTOM: Custom Objective](Lenses/EYE-CUSTOM_Custom_Objective.md) | User-defined goals |

### `/resources`
Quick references and supplementary materials.

| Document | Description |
|----------|-------------|
| [Agent QuickRef](resources/RootRise_Agent_QuickRef.md) | All 11 agents at a glance |
| [Lens Index](resources/RootRise_Lens_Index.md) | All 17 lenses at a glance |
| [Sector Index](resources/RootRise_Sector_Index.md) | All 31 sectors at a glance |

### `/Presentations`
Investor decks and partner materials.

| Document | Description |
|----------|-------------|
| DEVONEERS_RootRise_EBRD_Star_Venture.pdf | EBRD pitch deck |
| DEVONEERS_-_RootRise_-_Dec_2025.pdf | Latest investor deck |
| RootRise_by_DEVONEERS_v2_compressed.pdf | Main investor presentation |
| RootRise_Orchestrated_Breaking_the_Mold.pdf | Multi-agent architecture |
| RootRise_Architecture_Upgrade.pdf | Technical architecture |

### `/Design`
Visual design system and brand assets.

| Document | Description |
|----------|-------------|
| Color System | Official brand colors and usage |
| Architecture Visualizations | System diagrams |

---

## 🔢 Quick Stats

| Component | Count | Status |
|-----------|-------|--------|
| **AI Agents** | 11 | ✅ Production-ready |
| **Industry Sectors** | 31 | ✅ Complete |
| **Transformation Lenses** | 17 | ✅ Complete |
| **Countries Covered** | 6 | EG, SA, AE, JO, LB, MA |
| **Diagnostic Questions** | 145 | 10 sections |

---

## 🎯 Key Documents to Start

### For Technical Implementation (Ahmed)
1. [Infrastructure Blueprint v1.1](architecture/RootRise_Infrastructure_Blueprint_v1.1.md) - Start here
2. [Core Agent Prompts](agents/RootRise_Core_Agent_Prompts.md) - Agent specifications
3. [Sector Knowledge Framework v2](Sector%20Knowledge%20V2%202026/RootRise_Sector_Knowledge_Framework_v2.md) - Data structure

### For Understanding the System
1. [Agent QuickRef](resources/RootRise_Agent_QuickRef.md) - Meet the Pantheon
2. [Lens Index](resources/RootRise_Lens_Index.md) - Understand The &Eye
3. [Sector Index](resources/RootRise_Sector_Index.md) - See all sectors

### For Investors/Partners
1. Main investor presentation in `/Presentations`
2. EBRD Star Venture deck

---

## 🏗️ Architecture Overview

```
                         ┌──────────────────┐
                         │    THE DRUCKER   │
                         │   (Supervisor)   │
                         └────────┬─────────┘
                                  │
                    ┌─────────────┼─────────────┐
                    │             │             │
              ┌─────▼─────┐ ┌─────▼─────┐ ┌─────▼─────┐
              │  MARVIN   │ │  GRAHAM   │ │  ADD-ON   │
              │  (Ops)    │ │ (Finance) │ │  AGENTS   │
              └───────────┘ └───────────┘ └───────────┘
                                  │
                         ┌────────▼────────┐
                         │    THE DEMING   │
                         │  (Validation)   │
                         └────────┬────────┘
                                  │
                         ┌────────▼────────┐
                         │    THE TUFTE    │
                         │   (Reports)     │
                         └─────────────────┘
```

---

## 📞 Team

| Role | Person | Focus |
|------|--------|-------|
| **CEO** | Ruba | Strategy, Brand, Design |
| **CSO** | Alla | User Experience, Flexibility |
| **CTO** | Tee | Technical Architecture, Product |
| **DevOps Lead** | Ahmed El-Gazzar | Implementation |

---

## 📝 Version History

| Version | Date | Changes |
|---------|------|---------|
| 6.0 | Jan 2026 | Added The Crema, Custom Objective lens, 31 sectors complete, Blueprint v1.1 |
| 5.0 | Dec 2025 | Initial agent prompts, sector framework, lens system |

---

## 🔗 Links

- **Documentation Hub:** [GitHub Pages](https://tamermomtaz.github.io/RootRise-Blueprint-ArchExplained/)
- **Repository:** [GitHub](https://github.com/TamerMomtaz/RootRise-Blueprint-ArchExplained)

---

*Built with the &I Philosophy: AI + Human collaboration, not replacement.*
