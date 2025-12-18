# RootRise Infrastructure Blueprint - Quick Reference

## For Ahmed El-Gazzar | December 2025

---

## 🎯 What We're Building

An AI-powered SME diagnostic platform with 11 specialized agents that:
- Compresses 6-month consulting engagements into 30-minute assessments
- Maintains human agency at every decision point (&I Philosophy)
- Supports 27+ industry sectors across MENA region

---

## 🏗️ Core Components

### 1. The Agents (11 Total)

**Core (Always Run):**
| Agent | Role | Named After |
|-------|------|-------------|
| Drucker | Orchestrator/Supervisor | Peter Drucker |
| Marvin | Operational Diagnostics | Marvin Bower |
| Graham | Financial Analysis | Benjamin Graham |

**Add-On (User Selects):**
| Agent | Role | Named After |
|-------|------|-------------|
| Ricardo | Export & Trade | David Ricardo |
| Lovelace | Digital & Technology | Ada Lovelace |
| Mayo | HR & Organization | Elton Mayo |
| Ohno | Supply Chain & Lean | Taiichi Ohno |
| Porter | Market & Competition | Michael Porter |
| Landor | Packaging & Labeling | Walter Landor |

**Utility (Always Run):**
| Agent | Role | Named After |
|-------|------|-------------|
| Deming | Quality Validation | W. Edwards Deming |
| Tufte | Report Generation | Edward Tufte |

### 2. HITL Gates (4 Checkpoints)

| Gate | Purpose | Triggers When |
|------|---------|---------------|
| Gate 1 | Data Quality | Coverage < 70%, inconsistencies |
| Gate 2 | Finding Validation | Confidence < 70%, conflicts |
| Gate 3 | Strategic Review | Recommendations > $50K |
| Gate 4 | Final Sign-off | Always (SME reviews report) |

### 3. Technology Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| API | FastAPI | REST endpoints |
| Orchestration | LangGraph | Multi-agent workflow |
| Session Store | Redis | Short-term memory |
| Database | PostgreSQL | Long-term storage |
| Vector DB | Qdrant | Sector knowledge |
| Object Store | S3 | Reports, documents |
| LLM | OpenAI GPT-4o | Agent intelligence |

---

## 📊 Key Data Models

### DiagnosticSession (Redis)
```
session_id, sme_id, status, configuration
questionnaire_responses[]
agent_outputs{}
human_context[]        // &I: User-injected context
human_overrides[]      // &I: User corrections
pending_validations[]  // HITL triggers
```

### SMEProfile (PostgreSQL)
```
sme_id, company_name, country, sector_id
employee_count, annual_revenue_usd
owner_profile{}
local_context[]        // &I: Accumulated human knowledge
diagnostic_history[]
```

### Vector Chunk (Qdrant)
```
chunk_id, content, sector_id, dimension
source_name, source_reliability
confidence_score, confidence_rationale  // &I: Transparency
```

---

## 🔄 Execution Flow

```
User → API → Drucker → [HITL Gate 1]
                           ↓
              [Marvin + Graham] (parallel)
                           ↓
                    [HITL Gate 2]
                           ↓
              [Add-On Agents] (parallel)
                           ↓
                    [HITL Gate 3]
                           ↓
                       Deming
                           ↓
                       Tufte
                           ↓
                    [HITL Gate 4]
                           ↓
                    Final Report
```

---

## 🔑 Key API Endpoints

### Core Diagnostic
```
POST /diagnostic/initiate
POST /diagnostic/{id}/respond
GET  /diagnostic/{id}/status
GET  /diagnostic/{id}/report
```

### &I Override (Human Agency)
```
POST /diagnostic/{id}/pause
POST /diagnostic/{id}/override
POST /diagnostic/{id}/inject-context
POST /diagnostic/{id}/request-human-review
```

### &I Transparency
```
GET /diagnostic/{id}/reasoning
GET /diagnostic/{id}/confidence-map
GET /diagnostic/{id}/sources
GET /diagnostic/{id}/uncertainties
GET /diagnostic/{id}/explain/{finding}
```

---

## 💰 Resource Estimates

### Infrastructure (Monthly @ 100 diagnostics)
| Component | Cost |
|-----------|------|
| Compute (API + Workers) | $180-480 |
| Databases | $155 |
| Storage | $32 |
| OpenAI API | $270 |
| **Total** | **~$660-960** |

### Development Timeline
| Phase | Duration |
|-------|----------|
| Core Infrastructure | 4 weeks |
| LangGraph Integration | 3 weeks |
| Agent Integration | 2 weeks |
| API Development | 3 weeks |
| Testing | 2 weeks |
| Deployment | 1 week |
| **Total** | **~15 weeks** |

---

## ✅ Implementation Priorities

### Week 1-2
- [ ] PostgreSQL + Redis setup
- [ ] Base FastAPI structure
- [ ] Authentication

### Week 3-4
- [ ] Session management
- [ ] Memory manager
- [ ] Human context/override endpoints

### Week 5-7
- [ ] LangGraph state schema
- [ ] Core agent nodes
- [ ] HITL gates
- [ ] Checkpointing

### Week 8-9
- [ ] Add-on agent nodes
- [ ] Utility agent nodes
- [ ] Parallel execution

### Week 10-11
- [ ] Vector DB indexing
- [ ] Retrieval implementation
- [ ] Confidence metadata

### Week 12-13
- [ ] Full API
- [ ] WebSocket updates
- [ ] Documentation

### Week 14-15
- [ ] Testing
- [ ] Deployment
- [ ] Monitoring

---

## 🎯 &I Philosophy Checklist

For every component, verify:

- [ ] Human can pause/redirect at any point
- [ ] Confidence scores are visible, not hidden
- [ ] "I don't know" is a valid response
- [ ] Human context is weighted appropriately
- [ ] Overrides are logged and respected
- [ ] Reasoning is explainable
- [ ] Reports invite interpretation, not dictate

---

## 📁 Key Project Files

| File | Content |
|------|---------|
| `RootRise_Core_Agent_Prompts.md` | Drucker, Marvin, Graham prompts |
| `RootRise_AddOn_Agent_Prompts.md` | 6 specialist agent prompts |
| `RootRise_Utility_Agent_Prompts.md` | Tufte, Deming prompts |
| `RootRise_Sector_Knowledge_Framework.md` | 11-dimension schema |
| `RootRise_Sector_*_Complete.md` | 27+ sector knowledge packs |

---

*Full details in: `RootRise_Infrastructure_Blueprint_v1.md`*
