# RootRise v6.0 Technical Infrastructure Blueprint

**Document Version:** 1.0  
**Date:** December 11, 2025  
**Author:** Tee (CTO)  
**For:** Ahmed El-Gazzar (Technical DevOps Lead)  
**Status:** Implementation Ready

---

## Executive Summary

This document provides the complete technical infrastructure specification for implementing The RootRise Pantheon—an AI-powered SME diagnostic platform. It translates our architectural vision into actionable implementation guidance, with every technical decision filtered through the lens of our **&I Philosophy**: AI + Human, not AI instead of Human.

### What This Document Covers

1. **&I Philosophy Integration** — How human-AI collaboration is embedded at every layer
2. **Memory Architecture** — Session, persistent, and cross-agent state management
3. **Vector Database Design** — Sector knowledge storage and retrieval with confidence metadata
4. **LangGraph Orchestration** — Multi-agent workflow with native HITL checkpoints
5. **Data Flow Architecture** — Complete system integration with human touchpoints
6. **API Specification** — REST endpoints including transparency and override capabilities
7. **Deployment Architecture** — Infrastructure requirements and operational principles
8. **Resource Estimates** — Compute, storage, and cost projections

### Key Metrics at a Glance

| Component | Specification |
|-----------|---------------|
| Total Agents | 11 (3 Core + 6 Add-On + 2 Utility) |
| Sector Knowledge Packs | 27+ sectors, ~1.5MB total |
| Dimensions per Sector | 11 knowledge dimensions |
| HITL Checkpoints | 4 validation gates |
| Target Diagnostic Time | 30 minutes (user interaction) |
| Target Processing Time | < 120 seconds (AI analysis) |

---

## Part 1: The &I Philosophy — Our Technical North Star

Before any infrastructure decision, we must understand what makes RootRise fundamentally different. We are not building AI that replaces human judgment—we are building AI that **augments** human intelligence while **preserving** human agency.

### 1.1 The &I Principle in Practice

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         THE &I PHILOSOPHY                                    │
│                 "AI + Human, Not AI Instead of Human"                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   AI EXCELS AT:                        HUMANS EXCEL AT:                      │
│   ├─ Pattern recognition at scale      ├─ Local market context              │
│   ├─ 24/7 consistent processing        ├─ Relationship building             │
│   ├─ Benchmarking across sectors       ├─ Cultural nuance                   │
│   ├─ Data synthesis from 11 dims       ├─ Strategic judgment calls          │
│   ├─ Consistency across diagnostics    ├─ Trust and credibility             │
│   └─ Predictive modeling               └─ Creative problem-solving          │
│                                                                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   INFRASTRUCTURE REQUIREMENTS:                                               │
│                                                                              │
│   ✓ Never pretend AI has human judgment                                      │
│   ✓ Always surface uncertainty and confidence levels                         │
│   ✓ Design explicit human-in-the-loop checkpoints as FEATURES                │
│   ✓ Enable human override at every stage                                     │
│   ✓ Preserve human agency in final decisions                                 │
│   ✓ Make AI reasoning transparent and explainable                            │
│   ✓ Support (not replace) local advisors and consultants                     │
│                                                                              │
│   PRACTICAL IMPLICATIONS:                                                    │
│                                                                              │
│   • HITL triggers are features, not failures                                 │
│   • Confidence scores must be surfaced, not hidden                           │
│   • "I don't know" is a valid and valuable AI response                       │
│   • Local context inputs should be solicited and weighted                    │
│   • Reports should INVITE interpretation, not DICTATE action                 │
│   • The system AUGMENTS SME owners, not replaces advisors                    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 &I Decision Framework

For every infrastructure component, we evaluate:

| Question | Implementation Implication |
|----------|---------------------------|
| Does this support human context injection? | Memory architecture must distinguish human-provided vs AI-inferred data |
| Do the APIs enable human override? | Every assessment endpoint needs corresponding override/inject endpoints |
| Are HITL checkpoints first-class? | LangGraph nodes must include conditional human routing |
| Does reporting invite interpretation? | Reports include confidence, alternatives, and "questions to consider" |
| Is AI uncertainty visible? | Every finding carries confidence metadata surfaced to UI |

---

## Part 2: Memory Architecture

The Pantheon requires a sophisticated memory system that supports session continuity, historical tracking, cross-agent communication, and crucially—human context injection with appropriate attribution.

### 2.1 Memory Layer Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                          MEMORY ARCHITECTURE                                 │
│                    (Human-AI Collaborative Memory)                           │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                    SHORT-TERM MEMORY (Session)                       │    │
│  │  Storage: Redis (TTL: 24 hours)                                      │    │
│  ├─────────────────────────────────────────────────────────────────────┤    │
│  │  • Conversation context within diagnostic session                    │    │
│  │  • User responses to questionnaire (progressive)                     │    │
│  │  • Agent findings accumulated during session                         │    │
│  │  • Current state of diagnostic workflow                              │    │
│  │  • [&I] Human clarifications and context injections                  │    │
│  │  • [&I] Human override flags with timestamps                         │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                    LONG-TERM MEMORY (Persistent)                     │    │
│  │  Storage: PostgreSQL + S3 (document store)                           │    │
│  ├─────────────────────────────────────────────────────────────────────┤    │
│  │  • SME profile (company info, sector, size, ownership)               │    │
│  │  • Historical diagnostic results (time series)                       │    │
│  │  • Benchmark comparisons over time                                   │    │
│  │  • User preferences and report settings                              │    │
│  │  • [&I] Human-provided local context (relationships, culture)        │    │
│  │  • [&I] Human annotations on past diagnostics                        │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                  CROSS-AGENT MEMORY (Shared State)                   │    │
│  │  Storage: LangGraph State Object (in-memory during execution)        │    │
│  ├─────────────────────────────────────────────────────────────────────┤    │
│  │  • How Graham's financial findings feed Porter's analysis            │    │
│  │  • How Marvin's operational data informs Mayo's HR assessment        │    │
│  │  • Shared SME context all agents can access                          │    │
│  │  • Conflict resolution when agents have different views              │    │
│  │  • [&I] Human override flags propagated to all agents                │    │
│  │  • [&I] "Human said X" vs "AI inferred X" distinction                │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                  SECTOR KNOWLEDGE (Vector Store)                     │    │
│  │  Storage: Qdrant (self-hosted) or Pinecone (managed)                 │    │
│  ├─────────────────────────────────────────────────────────────────────┤    │
│  │  • 27+ sector knowledge packs (11 dimensions each)                   │    │
│  │  • Benchmarks, regulations, KPIs by sector/subsector/country         │    │
│  │  • [&I] Source attribution for every data point                      │    │
│  │  • [&I] Confidence metadata on benchmark reliability                 │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Data Models

#### 2.2.1 DiagnosticSession (Short-Term Memory)

```typescript
// Primary session state object
// Storage: Redis with 24-hour TTL
// Key pattern: diagnostic:session:{session_id}

interface DiagnosticSession {
  // Session Identity
  session_id: string;                    // UUID v4
  sme_id: string;                        // Foreign key to SME profile
  created_at: string;                    // ISO 8601 timestamp
  updated_at: string;                    // Auto-updated on every change
  expires_at: string;                    // TTL timestamp
  
  // Workflow State
  status: DiagnosticStatus;
  current_phase: DiagnosticPhase;
  current_agent: string | null;          // Currently executing agent ID
  
  // Configuration (from UI selections)
  configuration: {
    selected_agents: string[];           // e.g., ["drucker", "marvin", "graham", "ricardo"]
    sector_id: string;                   // e.g., "food_bev_manufacturing"
    subsector_id?: string;               // e.g., "dairy_products"
    selected_lenses: string[];           // e.g., ["export_readiness", "profitability"]
    report_format: ReportFormat;
    language: "en" | "ar" | "bilingual";
    benchmark_set: BenchmarkSet;
    technical_depth: 1 | 2 | 3 | 4 | 5;
    visual_density: 1 | 2 | 3 | 4 | 5;
  };
  
  // Questionnaire Progress
  questionnaire: {
    total_questions: number;
    completed_questions: number;
    current_section: string;
    responses: QuestionnaireResponse[];
  };
  
  // Agent Execution State
  agent_execution: {
    execution_order: string[];           // Planned order
    completed_agents: string[];          // Finished agents
    pending_agents: string[];            // Not yet started
    current_agent_started_at?: string;   // When current agent began
  };
  
  // Agent Outputs (accumulated during session)
  agent_outputs: Record<string, AgentOutput>;
  
  // &I: Human Context Injections
  human_context: HumanContextInjection[];
  
  // &I: Human Overrides
  human_overrides: HumanOverride[];
  
  // &I: HITL Triggers (pending human review)
  pending_validations: ValidationTrigger[];
  
  // Audit Trail
  audit_log: AuditEntry[];
}

type DiagnosticStatus = 
  | "initialized"           // Session created, not started
  | "questionnaire"         // User answering questions
  | "processing"            // Agents executing
  | "validation_required"   // Waiting for human validation
  | "report_generation"     // Tufte generating report
  | "completed"             // Diagnostic finished
  | "abandoned"             // User abandoned session
  | "error";                // System error

type DiagnosticPhase =
  | "setup"                 // Agent/sector/lens selection
  | "data_collection"       // Questionnaire
  | "core_analysis"         // Marvin + Graham
  | "specialist_analysis"   // Add-on agents
  | "validation"            // Deming quality check
  | "synthesis"             // Tufte report generation
  | "delivery";             // Final report ready

interface QuestionnaireResponse {
  question_id: string;
  section: string;
  question_text: string;
  question_type: "multiple_choice" | "numeric" | "text" | "scale" | "file_upload";
  response: any;                         // Type depends on question_type
  user_confidence: number;               // 0-1: How confident user is in their answer
  answered_at: string;
  // &I: Human context flag
  includes_local_context: boolean;       // User indicated this has local nuance
}

interface AgentOutput {
  agent_id: string;
  agent_name: string;
  status: "pending" | "running" | "completed" | "error" | "validation_required";
  started_at?: string;
  completed_at?: string;
  execution_time_ms?: number;
  
  // Core Output
  output: any;                           // Agent-specific output schema (defined per agent)
  
  // &I: Confidence and Transparency
  confidence_score: number;              // 0-1 overall confidence
  confidence_breakdown: {
    dimension: string;
    confidence: number;
    data_coverage: number;               // What % of needed data was available
    evidence_count: number;              // How many data points support this
  }[];
  
  // &I: Reasoning Transparency
  reasoning_trace: {
    step: number;
    action: string;
    rationale: string;
    data_used: string[];
    confidence_at_step: number;
  }[];
  
  // &I: Validation Flags
  validation_flags: ValidationFlag[];
  human_validated: boolean;
  human_validator?: string;
  human_validation_timestamp?: string;
  
  // Cross-Agent Dependencies
  inputs_from_agents: string[];          // Which agents' outputs informed this
  outputs_to_agents: string[];           // Which agents will use this output
}

// &I: Human Context Injection Model
interface HumanContextInjection {
  injection_id: string;
  injected_at: string;
  injected_by: string;                   // User ID or "sme_owner"
  
  context_type: 
    | "local_market_knowledge"           // "In our region, suppliers typically..."
    | "relationship_context"             // "We have a strong relationship with..."
    | "cultural_factor"                  // "During Ramadan, our sales..."
    | "historical_context"               // "We tried X in 2022 and..."
    | "correction"                       // "Actually, our revenue is..."
    | "clarification";                   // "When I said X, I meant..."
  
  target_dimension?: string;             // Which dimension this relates to
  target_agent?: string;                 // Which agent should consider this
  
  content: string;                       // The actual context
  
  // How this affects AI reasoning
  weight_adjustment: "high" | "medium" | "low";  // How much to weight this
  override_ai_inference: boolean;        // Should this override AI conclusions?
}

// &I: Human Override Model
interface HumanOverride {
  override_id: string;
  created_at: string;
  created_by: string;
  
  override_type:
    | "score_adjustment"                 // "I disagree with this score"
    | "finding_rejection"                // "This finding is incorrect"
    | "recommendation_modification"      // "This recommendation needs adjustment"
    | "agent_skip"                       // "Skip this agent's analysis"
    | "confidence_override";             // "I'm more/less confident than AI"
  
  target_agent: string;
  target_finding?: string;               // Specific finding ID if applicable
  
  original_value: any;
  override_value: any;
  
  rationale: string;                     // Why the human is overriding
  
  // Audit
  acknowledged_by_system: boolean;
  applied_to_report: boolean;
}

// Validation trigger for HITL
interface ValidationTrigger {
  trigger_id: string;
  triggered_at: string;
  triggered_by_agent: string;
  
  trigger_type:
    | "low_confidence"                   // Agent confidence < threshold
    | "critical_finding"                 // Finding requires expert review
    | "cross_agent_conflict"             // Agents disagree
    | "data_gap"                         // Missing critical data
    | "high_stakes_recommendation"       // Recommendation > $X investment
    | "regulatory_concern"               // Compliance/legal flag
    | "anomaly_detected";                // SME metrics significantly off benchmark
  
  severity: "critical" | "high" | "medium" | "low";
  blocking: boolean;                     // Does this block report generation?
  
  description: string;
  affected_findings: string[];
  
  required_reviewer: "sme_owner" | "embedded_associate" | "senior_expert" | "domain_expert";
  
  // Resolution
  resolved: boolean;
  resolution?: {
    resolved_at: string;
    resolved_by: string;
    decision: "approved" | "modified" | "rejected" | "escalated";
    modifications?: any;
    notes?: string;
  };
}

interface AuditEntry {
  entry_id: string;
  timestamp: string;
  actor: "system" | "agent" | "human";
  actor_id: string;                      // Agent ID or User ID
  action: string;
  details: any;
  session_phase: DiagnosticPhase;
}
```

#### 2.2.2 SME Profile (Long-Term Memory)

```typescript
// Persistent SME profile
// Storage: PostgreSQL
// Table: sme_profiles

interface SMEProfile {
  // Identity
  sme_id: string;                        // UUID v4, primary key
  created_at: string;
  updated_at: string;
  
  // Company Information
  company_name: string;
  company_name_ar?: string;
  legal_entity_type: string;
  registration_number?: string;
  founding_year: number;
  
  // Location
  country: string;                       // ISO 3166-1 alpha-2
  city: string;
  address?: string;
  free_zone?: string;                    // If located in a free zone
  
  // Size
  employee_count: number;
  employee_count_verified: boolean;      // Has this been verified?
  annual_revenue_usd: number;
  revenue_currency_original: string;
  revenue_verified: boolean;
  
  // Classification
  sector_id: string;
  sector_name: string;
  subsector_id?: string;
  subsector_name?: string;
  sector_type: "industrial" | "services" | "hybrid";
  
  // Business Description
  business_description: string;
  business_description_ar?: string;
  products_services: string[];
  primary_customers: string[];           // e.g., ["B2B", "retail", "government"]
  
  // Ownership
  owner_profile: {
    name: string;
    role: string;
    years_in_business: number;
    education_level: string;
    previous_businesses?: number;
    succession_status: "not_addressed" | "identified" | "in_training" | "ready";
  };
  
  // &I: Human-Provided Local Context (accumulated over diagnostics)
  local_context: {
    context_id: string;
    category: string;
    content: string;
    added_at: string;
    added_by: string;
    still_relevant: boolean;             // Can be marked stale
  }[];
  
  // Diagnostic History
  diagnostic_count: number;
  last_diagnostic_at?: string;
  average_overall_score?: number;
  score_trend?: "improving" | "stable" | "declining";
}

// Diagnostic History Record (separate table, linked by sme_id)
interface DiagnosticRecord {
  record_id: string;
  sme_id: string;
  session_id: string;
  
  completed_at: string;
  
  // Configuration at time of diagnostic
  configuration_snapshot: {
    selected_agents: string[];
    sector_id: string;
    selected_lenses: string[];
  };
  
  // Results Summary
  overall_score: number;
  dimension_scores: {
    dimension: string;
    score: number;
    benchmark: number;
    gap: number;
  }[];
  
  // Key Findings (denormalized for quick access)
  top_strengths: string[];
  top_gaps: string[];
  top_recommendations: string[];
  
  // Report Reference
  report_storage_key: string;            // S3 key for full report
  
  // &I: Human Feedback on this Diagnostic
  human_feedback?: {
    accuracy_rating: 1 | 2 | 3 | 4 | 5;
    usefulness_rating: 1 | 2 | 3 | 4 | 5;
    implemented_recommendations: string[];
    feedback_notes?: string;
    feedback_at: string;
  };
}
```

### 2.3 Memory Access Patterns

```python
# Python pseudocode for memory access patterns

class MemoryManager:
    """
    Manages all memory layers for The Pantheon.
    Ensures &I principles are maintained in all memory operations.
    """
    
    def __init__(self, redis_client, postgres_pool, vector_store):
        self.session_store = redis_client      # Short-term
        self.profile_store = postgres_pool     # Long-term
        self.knowledge_store = vector_store    # Sector knowledge
    
    # ─────────────────────────────────────────────────────────────────
    # Session Memory (Short-Term)
    # ─────────────────────────────────────────────────────────────────
    
    async def create_session(self, sme_id: str, configuration: dict) -> DiagnosticSession:
        """Create a new diagnostic session."""
        session = DiagnosticSession(
            session_id=str(uuid.uuid4()),
            sme_id=sme_id,
            created_at=datetime.utcnow().isoformat(),
            status="initialized",
            configuration=configuration,
            # Initialize empty containers
            questionnaire={"responses": []},
            agent_outputs={},
            human_context=[],
            human_overrides=[],
            pending_validations=[],
            audit_log=[]
        )
        
        # Store with TTL
        await self.session_store.setex(
            f"diagnostic:session:{session.session_id}",
            86400,  # 24 hours
            session.to_json()
        )
        
        return session
    
    async def get_session(self, session_id: str) -> DiagnosticSession:
        """Retrieve session state."""
        data = await self.session_store.get(f"diagnostic:session:{session_id}")
        if not data:
            raise SessionNotFoundError(session_id)
        return DiagnosticSession.from_json(data)
    
    async def update_session(self, session: DiagnosticSession):
        """Update session state with audit logging."""
        session.updated_at = datetime.utcnow().isoformat()
        await self.session_store.setex(
            f"diagnostic:session:{session.session_id}",
            86400,
            session.to_json()
        )
    
    # &I: Human Context Injection
    async def inject_human_context(
        self, 
        session_id: str, 
        context: HumanContextInjection
    ):
        """
        Add human-provided context to a session.
        This is a core &I capability - humans can inject local knowledge
        that AI should consider in its analysis.
        """
        session = await self.get_session(session_id)
        
        # Add the context
        session.human_context.append(context)
        
        # Log this as an audit event
        session.audit_log.append(AuditEntry(
            timestamp=datetime.utcnow().isoformat(),
            actor="human",
            actor_id=context.injected_by,
            action="context_injection",
            details={
                "context_type": context.context_type,
                "target_agent": context.target_agent,
                "weight": context.weight_adjustment
            }
        ))
        
        await self.update_session(session)
        
        return context.injection_id
    
    # &I: Human Override
    async def apply_human_override(
        self,
        session_id: str,
        override: HumanOverride
    ):
        """
        Apply a human override to an AI finding.
        This is a core &I capability - humans can override AI conclusions.
        """
        session = await self.get_session(session_id)
        
        # Validate the override target exists
        if override.target_agent not in session.agent_outputs:
            raise OverrideTargetNotFoundError(override.target_agent)
        
        # Add the override
        session.human_overrides.append(override)
        
        # Mark the affected agent output as overridden
        session.agent_outputs[override.target_agent].human_validated = True
        
        # Log
        session.audit_log.append(AuditEntry(
            timestamp=datetime.utcnow().isoformat(),
            actor="human",
            actor_id=override.created_by,
            action="human_override",
            details={
                "override_type": override.override_type,
                "target_agent": override.target_agent,
                "original_value": override.original_value,
                "override_value": override.override_value,
                "rationale": override.rationale
            }
        ))
        
        await self.update_session(session)
    
    # ─────────────────────────────────────────────────────────────────
    # Profile Memory (Long-Term)
    # ─────────────────────────────────────────────────────────────────
    
    async def get_sme_profile(self, sme_id: str) -> SMEProfile:
        """Retrieve SME profile with historical context."""
        query = "SELECT * FROM sme_profiles WHERE sme_id = $1"
        row = await self.profile_store.fetchrow(query, sme_id)
        if not row:
            raise SMENotFoundError(sme_id)
        return SMEProfile.from_row(row)
    
    async def get_diagnostic_history(
        self, 
        sme_id: str, 
        limit: int = 5
    ) -> list[DiagnosticRecord]:
        """Get historical diagnostic records for trend analysis."""
        query = """
            SELECT * FROM diagnostic_records 
            WHERE sme_id = $1 
            ORDER BY completed_at DESC 
            LIMIT $2
        """
        rows = await self.profile_store.fetch(query, sme_id, limit)
        return [DiagnosticRecord.from_row(r) for r in rows]
    
    # ─────────────────────────────────────────────────────────────────
    # Cross-Agent Memory (Shared State)
    # ─────────────────────────────────────────────────────────────────
    
    def build_agent_context(
        self, 
        session: DiagnosticSession,
        target_agent: str
    ) -> dict:
        """
        Build the context object that will be passed to an agent.
        Includes outputs from upstream agents and human context.
        """
        context = {
            "session_id": session.session_id,
            "sme_profile": None,  # Will be populated
            "sector_intelligence": None,  # Will be populated from vector store
            "questionnaire_responses": session.questionnaire["responses"],
            
            # Outputs from other agents (filtered by dependency)
            "upstream_agent_outputs": {},
            
            # &I: Human context that applies to this agent
            "human_context": [
                c for c in session.human_context
                if c.target_agent is None or c.target_agent == target_agent
            ],
            
            # &I: Any overrides that affect this agent
            "applicable_overrides": [
                o for o in session.human_overrides
                if o.target_agent == target_agent
            ],
            
            # Configuration
            "active_lenses": session.configuration["selected_lenses"],
            "benchmark_set": session.configuration["benchmark_set"]
        }
        
        # Add upstream agent outputs based on dependency graph
        dependencies = AGENT_DEPENDENCIES.get(target_agent, [])
        for dep_agent in dependencies:
            if dep_agent in session.agent_outputs:
                output = session.agent_outputs[dep_agent]
                if output.status == "completed":
                    context["upstream_agent_outputs"][dep_agent] = {
                        "output": output.output,
                        "confidence_score": output.confidence_score,
                        "validation_flags": output.validation_flags,
                        "human_validated": output.human_validated
                    }
        
        return context
```

### 2.4 &I Memory Principles

| Principle | Implementation |
|-----------|----------------|
| **Human context is weighted appropriately vs AI inference** | `HumanContextInjection.weight_adjustment` allows humans to specify importance; agents check this before making conclusions |
| **User can correct/override any stored assumption** | `HumanOverride` model allows point-in-time corrections that propagate to dependent agents |
| **"Human said X" vs "AI inferred X" distinction maintained** | All context entries tagged with `source: "human" | "agent"` |
| **Memory transparency: user can see what system "remembers"** | API endpoint `GET /diagnostic/{id}/ai-assumptions` exposes all inferences |

---

## Part 3: Vector Database Design

The sector knowledge base is the intelligence layer that powers all diagnostic agents. It must support efficient retrieval while maintaining transparency about data provenance and confidence.

### 3.1 Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        VECTOR DATABASE ARCHITECTURE                          │
│                    (Supporting Transparent AI Reasoning)                     │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                      EMBEDDING PIPELINE                              │    │
│  │                                                                       │    │
│  │   Sector Pack    ──►  Chunker     ──►   Embedder    ──►   Qdrant     │    │
│  │   (Markdown)          (Semantic)        (OpenAI/       (Vector DB)   │    │
│  │                       (512-1024         Cohere)                       │    │
│  │                        tokens)                                        │    │
│  │                                                                       │    │
│  │   Metadata Extraction:                                                │    │
│  │   • sector_id, subsector_id, country_code                            │    │
│  │   • dimension (1-11)                                                  │    │
│  │   • data_type (benchmark, regulation, kpi, etc.)                     │    │
│  │   • source_id, source_reliability (0-1)                              │    │
│  │   • publication_date                                                  │    │
│  │   • [&I] confidence_score (how reliable is this data?)               │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                      RETRIEVAL PATTERNS                              │    │
│  │                                                                       │    │
│  │   Query Types:                                                        │    │
│  │                                                                       │    │
│  │   1. SECTOR BENCHMARK LOOKUP                                          │    │
│  │      Filter: sector_id + country + dimension                          │    │
│  │      "What's the gross margin benchmark for dairy in Egypt?"          │    │
│  │                                                                       │    │
│  │   2. REGULATORY SEARCH                                                │    │
│  │      Filter: sector_id + country + data_type="regulation"             │    │
│  │      "What export certifications needed for food to Saudi?"           │    │
│  │                                                                       │    │
│  │   3. KPI LOOKUP                                                       │    │
│  │      Filter: sector_id + dimension="operational_kpis"                 │    │
│  │      "What's a good OEE for textile manufacturing?"                   │    │
│  │                                                                       │    │
│  │   4. SEMANTIC SIMILARITY (Hybrid)                                     │    │
│  │      Vector similarity + keyword boost                                │    │
│  │      "Challenges facing family-owned food businesses in MENA"         │    │
│  │                                                                       │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                    &I RETRIEVAL PRINCIPLES                           │    │
│  │                                                                       │    │
│  │   • "Based on X source with Y confidence" attribution                 │    │
│  │   • When data is sparse/uncertain, surface that explicitly            │    │
│  │   • Local data (user-provided) vs general benchmarks flagged          │    │
│  │   • Human can request "show me what you're basing this on"            │    │
│  │   • Retrieval confidence scores surfaced to user                      │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Collection Schema

```python
# Qdrant Collection Configuration

from qdrant_client import QdrantClient
from qdrant_client.http import models

# Collection: sector_knowledge
sector_knowledge_schema = {
    "collection_name": "sector_knowledge",
    "vectors_config": {
        "size": 1536,           # OpenAI text-embedding-3-small dimension
        "distance": "Cosine"
    },
    "on_disk_payload": True,    # For large payloads
}

# Payload Schema (stored with each vector)
payload_schema = {
    # Identity
    "chunk_id": "string",           # Unique identifier for this chunk
    "sector_id": "string",          # e.g., "food_bev_manufacturing"
    "subsector_id": "string|null",  # e.g., "dairy_products"
    "sector_name": "string",        # Human-readable
    "sector_name_ar": "string",     # Arabic name
    
    # Classification
    "dimension": "integer",         # 1-11 (matching the 11-dimension framework)
    "dimension_name": "string",     # e.g., "Financial Benchmarks"
    "data_type": "string",          # benchmark | regulation | kpi | workforce | supply_chain | export | packaging | mena_context
    
    # Geographic Context
    "country_code": "string|null",  # ISO 3166-1 alpha-2, null if regional/global
    "country_name": "string|null",
    "applicable_countries": "array[string]",  # List of applicable countries
    
    # Content
    "content": "string",            # The actual text content
    "content_ar": "string|null",    # Arabic translation if available
    "heading_path": "string",       # e.g., "Financial Benchmarks > Profitability > Gross Margin"
    
    # &I: Source Attribution
    "source_id": "string",          # Reference to data source
    "source_name": "string",        # e.g., "CAPMAS Industry Report 2024"
    "source_type": "string",        # government | industry_association | research | proprietary
    "source_url": "string|null",
    "publication_date": "string",   # ISO date
    
    # &I: Confidence Metadata
    "source_reliability": "float",  # 0-1, how reliable is this source?
    "data_recency": "string",       # current | recent | dated | historical
    "confidence_score": "float",    # 0-1, overall confidence in this data point
    "confidence_rationale": "string", # Why this confidence level?
    
    # Retrieval Optimization
    "keywords": "array[string]",    # For hybrid search
    "isic_codes": "array[string]",  # Industry classification codes
    
    # Versioning
    "pack_version": "string",       # e.g., "1.0.0"
    "indexed_at": "string"          # When this was indexed
}

# Create indexes for filtered search
payload_indexes = [
    models.PayloadSchemaType.KEYWORD,  # sector_id
    models.PayloadSchemaType.KEYWORD,  # dimension
    models.PayloadSchemaType.KEYWORD,  # country_code
    models.PayloadSchemaType.KEYWORD,  # data_type
    models.PayloadSchemaType.FLOAT,    # confidence_score
]
```

### 3.3 Chunking Strategy

```python
from dataclasses import dataclass
from typing import List, Optional
import hashlib

@dataclass
class SectorKnowledgeChunk:
    """
    Represents a semantic chunk from a sector knowledge pack.
    Designed for optimal RAG retrieval while maintaining &I transparency.
    """
    chunk_id: str
    content: str
    content_ar: Optional[str]
    
    # Hierarchy
    sector_id: str
    subsector_id: Optional[str]
    dimension: int
    dimension_name: str
    heading_path: str
    
    # Geographic
    country_code: Optional[str]
    applicable_countries: List[str]
    
    # Source Attribution (&I)
    source_id: str
    source_name: str
    source_type: str
    source_reliability: float
    publication_date: str
    
    # Confidence (&I)
    confidence_score: float
    confidence_rationale: str


class SectorKnowledgeChunker:
    """
    Chunks sector knowledge packs into retrieval-optimized segments.
    
    Chunking Philosophy:
    - Semantic boundaries: Don't split mid-concept
    - Target size: 512-1024 tokens (fits in context window with room for synthesis)
    - Overlap: 50-100 tokens for continuity
    - Metadata preservation: Every chunk carries full attribution
    """
    
    def __init__(
        self,
        target_chunk_size: int = 800,
        chunk_overlap: int = 100,
        min_chunk_size: int = 200
    ):
        self.target_chunk_size = target_chunk_size
        self.chunk_overlap = chunk_overlap
        self.min_chunk_size = min_chunk_size
    
    def chunk_sector_pack(
        self,
        sector_pack: dict,
        sector_id: str
    ) -> List[SectorKnowledgeChunk]:
        """
        Process a complete sector knowledge pack into chunks.
        
        Chunking by dimension ensures:
        1. Clear attribution (which dimension does this come from?)
        2. Efficient filtered retrieval (query specific dimensions)
        3. Appropriate context (benchmarks stay with benchmarks)
        """
        chunks = []
        
        # Dimension mapping
        dimension_mapping = {
            "industry_classification": (1, "Industry Classification"),
            "financial_benchmarks": (2, "Financial Benchmarks"),
            "operational_kpis": (3, "Operational KPIs"),
            "regulatory_landscape": (4, "Regulatory Landscape"),
            "competitive_dynamics": (5, "Competitive Dynamics"),
            "digital_maturity": (6, "Digital Maturity"),
            "workforce_norms": (7, "Workforce Norms"),
            "supply_chain": (8, "Supply Chain"),
            "export_requirements": (9, "Export Requirements"),
            "packaging_labeling": (10, "Packaging & Labeling"),
            "mena_context": (11, "MENA Regional Context")
        }
        
        # Process each dimension
        for dim_key, (dim_num, dim_name) in dimension_mapping.items():
            if dim_key not in sector_pack:
                continue
            
            dim_data = sector_pack[dim_key]
            dim_chunks = self._chunk_dimension(
                dim_data,
                sector_id,
                dim_num,
                dim_name,
                sector_pack.get("metadata", {})
            )
            chunks.extend(dim_chunks)
        
        # Process subsector overrides
        for subsector in sector_pack.get("subsectors", []):
            subsector_chunks = self._chunk_subsector(
                subsector,
                sector_id,
                sector_pack.get("metadata", {})
            )
            chunks.extend(subsector_chunks)
        
        return chunks
    
    def _chunk_dimension(
        self,
        dim_data: dict,
        sector_id: str,
        dim_num: int,
        dim_name: str,
        metadata: dict
    ) -> List[SectorKnowledgeChunk]:
        """
        Chunk a single dimension, respecting semantic boundaries.
        """
        chunks = []
        
        # Flatten the dimension data into text blocks with paths
        text_blocks = self._flatten_to_blocks(dim_data, dim_name)
        
        for block in text_blocks:
            # Determine source attribution
            source_info = self._extract_source_info(block, metadata)
            
            # Split if too long, respecting sentence boundaries
            if len(block["text"]) > self.target_chunk_size * 4:  # ~4 chars per token
                sub_chunks = self._split_block(block["text"])
            else:
                sub_chunks = [block["text"]]
            
            for i, chunk_text in enumerate(sub_chunks):
                if len(chunk_text) < self.min_chunk_size:
                    continue
                
                chunk_id = self._generate_chunk_id(
                    sector_id, dim_num, block["path"], i
                )
                
                chunks.append(SectorKnowledgeChunk(
                    chunk_id=chunk_id,
                    content=chunk_text,
                    content_ar=block.get("text_ar"),
                    sector_id=sector_id,
                    subsector_id=None,
                    dimension=dim_num,
                    dimension_name=dim_name,
                    heading_path=block["path"],
                    country_code=block.get("country_code"),
                    applicable_countries=metadata.get("applicable_countries", []),
                    source_id=source_info["source_id"],
                    source_name=source_info["source_name"],
                    source_type=source_info["source_type"],
                    source_reliability=source_info["reliability"],
                    publication_date=source_info["publication_date"],
                    confidence_score=self._calculate_confidence(source_info),
                    confidence_rationale=self._generate_confidence_rationale(source_info)
                ))
        
        return chunks
    
    def _calculate_confidence(self, source_info: dict) -> float:
        """
        Calculate confidence score based on source characteristics.
        
        &I Principle: Be transparent about data reliability.
        """
        base_score = source_info["reliability"]
        
        # Recency adjustment
        recency = source_info.get("recency", "dated")
        recency_adjustment = {
            "current": 0.0,
            "recent": -0.05,
            "dated": -0.15,
            "historical": -0.25
        }.get(recency, -0.1)
        
        # Source type adjustment
        source_type = source_info["source_type"]
        type_adjustment = {
            "government": 0.05,      # Official sources get slight boost
            "research": 0.0,
            "industry_association": 0.0,
            "proprietary": -0.05     # Internal data slightly less verifiable
        }.get(source_type, 0.0)
        
        final_score = max(0.0, min(1.0, base_score + recency_adjustment + type_adjustment))
        return round(final_score, 2)
    
    def _generate_confidence_rationale(self, source_info: dict) -> str:
        """
        Generate human-readable confidence explanation.
        
        &I Principle: Explain why we're confident (or not).
        """
        parts = []
        
        reliability = source_info["reliability"]
        if reliability >= 0.9:
            parts.append("highly reliable source")
        elif reliability >= 0.7:
            parts.append("generally reliable source")
        else:
            parts.append("source reliability limited")
        
        source_type = source_info["source_type"]
        type_desc = {
            "government": "official government publication",
            "research": "peer-reviewed research",
            "industry_association": "industry association data",
            "proprietary": "proprietary data"
        }.get(source_type, "other source")
        parts.append(type_desc)
        
        recency = source_info.get("recency", "unknown")
        if recency == "current":
            parts.append("published within 6 months")
        elif recency == "recent":
            parts.append("published within 2 years")
        elif recency == "dated":
            parts.append("published 2-5 years ago")
        elif recency == "historical":
            parts.append("historical data (5+ years)")
        
        return "; ".join(parts)
    
    def _generate_chunk_id(
        self,
        sector_id: str,
        dimension: int,
        path: str,
        index: int
    ) -> str:
        """Generate deterministic chunk ID for deduplication."""
        content = f"{sector_id}:{dimension}:{path}:{index}"
        return hashlib.md5(content.encode()).hexdigest()[:16]
```

### 3.4 Retrieval Implementation

```python
from typing import List, Optional, Dict
from dataclasses import dataclass
from qdrant_client import QdrantClient
from qdrant_client.http import models

@dataclass
class RetrievalResult:
    """
    Result from knowledge retrieval with full &I transparency.
    """
    chunk_id: str
    content: str
    
    # Relevance
    similarity_score: float          # Vector similarity (0-1)
    
    # Attribution (&I)
    source_name: str
    source_type: str
    publication_date: str
    
    # Confidence (&I)
    confidence_score: float
    confidence_rationale: str
    
    # Context
    sector_id: str
    dimension_name: str
    heading_path: str
    country_code: Optional[str]


class SectorKnowledgeRetriever:
    """
    Retrieves relevant sector knowledge for agent queries.
    
    &I Principles:
    - Always return source attribution
    - Surface confidence levels
    - Allow humans to see "what the AI is basing this on"
    - Acknowledge when data is sparse or uncertain
    """
    
    def __init__(
        self,
        qdrant_client: QdrantClient,
        embedding_model,
        collection_name: str = "sector_knowledge"
    ):
        self.client = qdrant_client
        self.embedder = embedding_model
        self.collection = collection_name
    
    async def retrieve_for_agent(
        self,
        agent_id: str,
        query: str,
        sector_id: str,
        subsector_id: Optional[str] = None,
        country_code: Optional[str] = None,
        dimensions: Optional[List[int]] = None,
        top_k: int = 10,
        min_confidence: float = 0.5
    ) -> Dict:
        """
        Retrieve relevant knowledge for a specific agent.
        
        Returns both the results AND metadata about retrieval quality
        (for &I transparency).
        """
        # Get dimensions this agent needs
        if dimensions is None:
            dimensions = AGENT_DIMENSION_MAPPING.get(agent_id, list(range(1, 12)))
        
        # Build filter
        filter_conditions = [
            models.FieldCondition(
                key="sector_id",
                match=models.MatchValue(value=sector_id)
            ),
            models.FieldCondition(
                key="dimension",
                match=models.MatchAny(any=dimensions)
            ),
            models.FieldCondition(
                key="confidence_score",
                range=models.Range(gte=min_confidence)
            )
        ]
        
        # Add country filter if specified
        if country_code:
            filter_conditions.append(
                models.FieldCondition(
                    key="applicable_countries",
                    match=models.MatchAny(any=[country_code, "global"])
                )
            )
        
        # Add subsector filter if specified
        if subsector_id:
            filter_conditions.append(
                models.FieldCondition(
                    key="subsector_id",
                    match=models.MatchAny(any=[subsector_id, None])
                )
            )
        
        # Generate query embedding
        query_vector = await self.embedder.embed(query)
        
        # Search
        results = self.client.search(
            collection_name=self.collection,
            query_vector=query_vector,
            query_filter=models.Filter(must=filter_conditions),
            limit=top_k,
            with_payload=True,
            score_threshold=0.6  # Minimum similarity
        )
        
        # Convert to RetrievalResult objects
        retrieval_results = []
        for hit in results:
            retrieval_results.append(RetrievalResult(
                chunk_id=hit.payload["chunk_id"],
                content=hit.payload["content"],
                similarity_score=hit.score,
                source_name=hit.payload["source_name"],
                source_type=hit.payload["source_type"],
                publication_date=hit.payload["publication_date"],
                confidence_score=hit.payload["confidence_score"],
                confidence_rationale=hit.payload["confidence_rationale"],
                sector_id=hit.payload["sector_id"],
                dimension_name=hit.payload["dimension_name"],
                heading_path=hit.payload["heading_path"],
                country_code=hit.payload.get("country_code")
            ))
        
        # Calculate retrieval quality metrics (&I transparency)
        retrieval_metadata = self._calculate_retrieval_quality(
            retrieval_results,
            dimensions,
            sector_id,
            country_code
        )
        
        return {
            "results": retrieval_results,
            "retrieval_metadata": retrieval_metadata
        }
    
    def _calculate_retrieval_quality(
        self,
        results: List[RetrievalResult],
        requested_dimensions: List[int],
        sector_id: str,
        country_code: Optional[str]
    ) -> Dict:
        """
        Calculate metrics about retrieval quality for &I transparency.
        
        This allows us to tell the user/agent:
        - "We found strong evidence for X"
        - "Data is sparse for dimension Y"
        - "No country-specific data, using regional benchmarks"
        """
        if not results:
            return {
                "overall_confidence": 0.0,
                "data_coverage": "none",
                "dimension_coverage": {},
                "warnings": ["No relevant data found in knowledge base"],
                "recommendation": "Consider requesting human expert input"
            }
        
        # Coverage by dimension
        covered_dimensions = set(r.dimension_name for r in results)
        dimension_coverage = {
            dim: dim in covered_dimensions 
            for dim in requested_dimensions
        }
        
        # Average confidence
        avg_confidence = sum(r.confidence_score for r in results) / len(results)
        
        # Country specificity
        country_specific = any(
            r.country_code == country_code for r in results
        ) if country_code else None
        
        # Generate warnings (&I transparency)
        warnings = []
        
        if avg_confidence < 0.6:
            warnings.append(f"Average data confidence is low ({avg_confidence:.0%})")
        
        missing_dims = [d for d, covered in dimension_coverage.items() if not covered]
        if missing_dims:
            warnings.append(f"No data found for dimensions: {missing_dims}")
        
        if country_code and not country_specific:
            warnings.append(f"No {country_code}-specific data, using regional benchmarks")
        
        old_data = [r for r in results if "5+ years" in r.confidence_rationale]
        if len(old_data) > len(results) / 2:
            warnings.append("Much of the available data is dated (5+ years old)")
        
        return {
            "overall_confidence": round(avg_confidence, 2),
            "data_coverage": "strong" if len(results) >= 5 else "moderate" if len(results) >= 3 else "limited",
            "dimension_coverage": dimension_coverage,
            "country_specific_data": country_specific,
            "result_count": len(results),
            "avg_similarity": round(sum(r.similarity_score for r in results) / len(results), 2),
            "warnings": warnings,
            "sources_used": list(set(r.source_name for r in results))
        }


# Agent-to-Dimension Mapping
AGENT_DIMENSION_MAPPING = {
    "drucker": [1, 11],                    # Industry Classification, MENA Context
    "marvin": [1, 3, 4, 7, 8],             # Classification, Ops KPIs, Regulatory, Workforce, Supply Chain
    "graham": [2, 1, 11],                   # Financial Benchmarks, Classification, MENA
    "ricardo": [9, 10, 4, 11],             # Export, Packaging, Regulatory, MENA
    "lovelace": [6, 3, 7],                  # Digital Maturity, Ops KPIs, Workforce
    "mayo": [7, 1, 11],                     # Workforce, Classification, MENA
    "ohno": [8, 3, 6, 7],                   # Supply Chain, Ops KPIs, Digital, Workforce
    "porter": [5, 1, 2, 11],                # Competitive, Classification, Financial, MENA
    "landor": [10, 9, 11],                  # Packaging, Export, MENA
    "tufte": list(range(1, 12)),            # All dimensions (for report generation)
    "deming": list(range(1, 12)),           # All dimensions (for validation)
}
```

### 3.5 Vector Database Resource Requirements

| Resource | Specification | Rationale |
|----------|---------------|-----------|
| **Storage** | ~5GB initial, scalable to 50GB | 27 sectors × ~2000 chunks × 1.5KB avg + embeddings |
| **RAM** | 8GB minimum, 16GB recommended | In-memory indexing for fast retrieval |
| **Collection Count** | 1 primary (sector_knowledge), 1 auxiliary (custom_context) | Keep simple, use filters |
| **Embedding Model** | OpenAI text-embedding-3-small (1536 dims) | Good balance of quality/cost |
| **Embedding Cost** | ~$0.02 per 1M tokens | One-time indexing cost ~$5 |
| **Query Latency** | <100ms p95 | With proper indexing |

---

## Part 4: LangGraph Orchestration

The Pantheon's multi-agent workflow is implemented using LangGraph, which provides native support for stateful, checkpointed workflows with human-in-the-loop capabilities—essential for our &I philosophy.

### 4.1 Graph Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       LANGGRAPH ORCHESTRATION                                │
│                   (Human-in-the-Loop Native Design)                          │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   ┌─────────────┐                                                           │
│   │   START     │                                                           │
│   └──────┬──────┘                                                           │
│          │                                                                   │
│          ▼                                                                   │
│   ┌─────────────┐      GATE 1: Data Quality                                 │
│   │  DRUCKER    │◄─── Human can pause/redirect at any point                 │
│   │(Orchestrator)│                                                          │
│   └──────┬──────┘                                                           │
│          │                                                                   │
│          │ Route to Core Agents                                              │
│          │                                                                   │
│   ┌──────┴──────┐                                                           │
│   │             │                                                            │
│   ▼             ▼                                                            │
│ ┌─────────┐ ┌─────────┐                                                     │
│ │ MARVIN  │ │ GRAHAM  │   ◄── Parallel Execution                            │
│ │(Diag)   │ │(Finance)│                                                     │
│ └────┬────┘ └────┬────┘                                                     │
│      │           │                                                           │
│      └─────┬─────┘                                                           │
│            │                                                                 │
│            ▼                                                                 │
│     ┌─────────────┐     GATE 2: Finding Validation                          │
│     │  HITL Node  │◄─── Confidence < 70%? Cross-agent conflict?             │
│     │ (Conditional)│     Human review required                              │
│     └──────┬──────┘                                                         │
│            │                                                                 │
│            │ If validated, continue                                          │
│            ▼                                                                 │
│   ┌─────────────────────────────────────────┐                               │
│   │          ADD-ON AGENTS (Parallel)        │                               │
│   │                                          │                               │
│   │  ┌────────┐ ┌────────┐ ┌────────┐       │                               │
│   │  │RICARDO │ │LOVELACE│ │  MAYO  │       │                               │
│   │  │(Export)│ │(Digital)│ │  (HR)  │       │                               │
│   │  └────────┘ └────────┘ └────────┘       │                               │
│   │                                          │                               │
│   │  ┌────────┐ ┌────────┐ ┌────────┐       │                               │
│   │  │  OHNO  │ │ PORTER │ │ LANDOR │       │  ◄── Only selected agents     │
│   │  │(Supply)│ │(Market)│ │(Packag)│       │      execute                   │
│   │  └────────┘ └────────┘ └────────┘       │                               │
│   │                                          │                               │
│   └──────────────────┬──────────────────────┘                               │
│                      │                                                       │
│                      ▼                                                       │
│               ┌─────────────┐   GATE 3: Strategic Validation                 │
│               │  HITL Node  │◄── High-cost recommendations?                  │
│               │ (Conditional)│   Major pivot suggested?                      │
│               └──────┬──────┘                                               │
│                      │                                                       │
│                      ▼                                                       │
│               ┌─────────────┐                                               │
│               │   DEMING    │◄── Quality Validation                         │
│               │  (Quality)  │    Cross-checks all outputs                   │
│               └──────┬──────┘                                               │
│                      │                                                       │
│                      ▼                                                       │
│               ┌─────────────┐                                               │
│               │   TUFTE     │◄── Report Generation                          │
│               │  (Reports)  │    Synthesizes all findings                   │
│               └──────┬──────┘                                               │
│                      │                                                       │
│                      ▼                                                       │
│               ┌─────────────┐   GATE 4: Final Sign-off                      │
│               │  HITL Node  │◄── SME Owner reviews report                   │
│               │   (Final)   │    before delivery                            │
│               └──────┬──────┘                                               │
│                      │                                                       │
│                      ▼                                                       │
│               ┌─────────────┐                                               │
│               │    END      │                                               │
│               └─────────────┘                                               │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 4.2 State Definition

```python
from typing import TypedDict, Annotated, List, Dict, Any, Optional
from langgraph.graph import StateGraph, END
from langgraph.prebuilt import ToolNode
from langgraph.checkpoint.sqlite import SqliteSaver
import operator

# LangGraph State Schema
class PantheonState(TypedDict):
    """
    The shared state object that flows through the entire graph.
    All agents read from and write to this state.
    """
    # Session Context
    session_id: str
    sme_id: str
    
    # SME Profile (loaded at start)
    sme_profile: Dict[str, Any]
    
    # Configuration
    selected_agents: List[str]
    sector_id: str
    subsector_id: Optional[str]
    selected_lenses: List[str]
    benchmark_set: str
    language: str
    
    # Sector Intelligence (loaded at start)
    sector_intelligence: Dict[str, Any]
    
    # Questionnaire Responses
    questionnaire_responses: List[Dict[str, Any]]
    
    # Agent Outputs (accumulated)
    # Using Annotated with operator.add for append-style updates
    agent_outputs: Annotated[Dict[str, Dict], operator.or_]
    
    # &I: Human Context Injections
    human_context: List[Dict[str, Any]]
    
    # &I: Human Overrides
    human_overrides: List[Dict[str, Any]]
    
    # &I: Validation Triggers (pending)
    pending_validations: List[Dict[str, Any]]
    
    # &I: Resolved Validations
    resolved_validations: List[Dict[str, Any]]
    
    # Execution Tracking
    current_phase: str
    execution_order: List[str]
    completed_agents: List[str]
    
    # Error Handling
    errors: List[Dict[str, Any]]
    
    # Final Report (populated by Tufte)
    final_report: Optional[Dict[str, Any]]
    
    # Audit Trail
    audit_log: Annotated[List[Dict], operator.add]


# Initial state factory
def create_initial_state(
    session_id: str,
    sme_profile: Dict,
    configuration: Dict,
    questionnaire_responses: List[Dict],
    sector_intelligence: Dict
) -> PantheonState:
    """Create the initial state for a diagnostic run."""
    return PantheonState(
        session_id=session_id,
        sme_id=sme_profile["sme_id"],
        sme_profile=sme_profile,
        selected_agents=configuration["selected_agents"],
        sector_id=configuration["sector_id"],
        subsector_id=configuration.get("subsector_id"),
        selected_lenses=configuration["selected_lenses"],
        benchmark_set=configuration["benchmark_set"],
        language=configuration["language"],
        sector_intelligence=sector_intelligence,
        questionnaire_responses=questionnaire_responses,
        agent_outputs={},
        human_context=[],
        human_overrides=[],
        pending_validations=[],
        resolved_validations=[],
        current_phase="initialization",
        execution_order=[],
        completed_agents=[],
        errors=[],
        final_report=None,
        audit_log=[]
    )
```

### 4.3 Node Implementations

```python
from langgraph.graph import StateGraph
from langchain_core.messages import HumanMessage, AIMessage
from langchain_openai import ChatOpenAI
import asyncio

class PantheonGraph:
    """
    The main orchestration graph for The Pantheon diagnostic system.
    """
    
    def __init__(
        self,
        llm: ChatOpenAI,
        memory_manager: MemoryManager,
        knowledge_retriever: SectorKnowledgeRetriever,
        checkpoint_saver: SqliteSaver
    ):
        self.llm = llm
        self.memory = memory_manager
        self.retriever = knowledge_retriever
        self.checkpointer = checkpoint_saver
        
        # Build the graph
        self.graph = self._build_graph()
    
    def _build_graph(self) -> StateGraph:
        """Build the LangGraph workflow."""
        
        # Initialize graph with state schema
        workflow = StateGraph(PantheonState)
        
        # ─────────────────────────────────────────────────────────────
        # Add Nodes
        # ─────────────────────────────────────────────────────────────
        
        # Core Agents
        workflow.add_node("drucker", self._drucker_node)
        workflow.add_node("marvin", self._marvin_node)
        workflow.add_node("graham", self._graham_node)
        
        # Add-On Agents
        workflow.add_node("ricardo", self._ricardo_node)
        workflow.add_node("lovelace", self._lovelace_node)
        workflow.add_node("mayo", self._mayo_node)
        workflow.add_node("ohno", self._ohno_node)
        workflow.add_node("porter", self._porter_node)
        workflow.add_node("landor", self._landor_node)
        
        # Utility Agents
        workflow.add_node("deming", self._deming_node)
        workflow.add_node("tufte", self._tufte_node)
        
        # &I: Human-in-the-Loop Nodes
        workflow.add_node("hitl_gate_1", self._hitl_data_quality)
        workflow.add_node("hitl_gate_2", self._hitl_finding_validation)
        workflow.add_node("hitl_gate_3", self._hitl_strategic_validation)
        workflow.add_node("hitl_gate_4", self._hitl_final_signoff)
        
        # Parallel execution coordinator
        workflow.add_node("addon_coordinator", self._addon_coordinator)
        
        # ─────────────────────────────────────────────────────────────
        # Add Edges
        # ─────────────────────────────────────────────────────────────
        
        # Entry point
        workflow.set_entry_point("drucker")
        
        # Drucker routes to Gate 1
        workflow.add_edge("drucker", "hitl_gate_1")
        
        # Gate 1 conditional routing
        workflow.add_conditional_edges(
            "hitl_gate_1",
            self._route_gate_1,
            {
                "proceed": "core_parallel",
                "human_required": "hitl_gate_1",  # Loop back for human input
                "error": END
            }
        )
        
        # Parallel core agent execution
        workflow.add_node("core_parallel", self._core_parallel_executor)
        workflow.add_edge("core_parallel", "hitl_gate_2")
        
        # Gate 2 conditional routing
        workflow.add_conditional_edges(
            "hitl_gate_2",
            self._route_gate_2,
            {
                "proceed": "addon_coordinator",
                "human_required": "hitl_gate_2",
                "skip_addons": "deming"  # If no add-ons selected
            }
        )
        
        # Add-on coordinator routes based on selected agents
        workflow.add_conditional_edges(
            "addon_coordinator",
            self._route_addons,
            {
                "addon_parallel": "addon_parallel_executor",
                "no_addons": "hitl_gate_3"
            }
        )
        
        workflow.add_node("addon_parallel_executor", self._addon_parallel_executor)
        workflow.add_edge("addon_parallel_executor", "hitl_gate_3")
        
        # Gate 3 conditional routing
        workflow.add_conditional_edges(
            "hitl_gate_3",
            self._route_gate_3,
            {
                "proceed": "deming",
                "human_required": "hitl_gate_3"
            }
        )
        
        # Deming → Tufte → Gate 4
        workflow.add_edge("deming", "tufte")
        workflow.add_edge("tufte", "hitl_gate_4")
        
        # Gate 4 final routing
        workflow.add_conditional_edges(
            "hitl_gate_4",
            self._route_gate_4,
            {
                "complete": END,
                "revision_required": "tufte"  # Regenerate report if needed
            }
        )
        
        return workflow.compile(checkpointer=self.checkpointer)
    
    # ─────────────────────────────────────────────────────────────────
    # Core Agent Nodes
    # ─────────────────────────────────────────────────────────────────
    
    async def _drucker_node(self, state: PantheonState) -> Dict:
        """
        The Drucker (Supervisor) - Orchestrates the diagnostic flow.
        
        Responsibilities:
        - Validate session configuration
        - Plan agent execution order
        - Provide cross-cutting context
        """
        # Log entry
        audit_entry = {
            "timestamp": datetime.utcnow().isoformat(),
            "agent": "drucker",
            "action": "start_orchestration",
            "details": {
                "selected_agents": state["selected_agents"],
                "sector_id": state["sector_id"]
            }
        }
        
        # Load Drucker prompt
        drucker_prompt = load_agent_prompt("drucker")
        
        # Build context
        context = {
            "sme_profile": state["sme_profile"],
            "configuration": {
                "agents": state["selected_agents"],
                "lenses": state["selected_lenses"],
                "sector": state["sector_id"]
            },
            "questionnaire_summary": self._summarize_questionnaire(
                state["questionnaire_responses"]
            )
        }
        
        # Execute Drucker
        response = await self.llm.ainvoke([
            {"role": "system", "content": drucker_prompt},
            {"role": "user", "content": f"Plan diagnostic for: {json.dumps(context)}"}
        ])
        
        # Parse Drucker's plan
        plan = self._parse_drucker_response(response.content)
        
        return {
            "current_phase": "core_analysis",
            "execution_order": plan["execution_order"],
            "agent_outputs": {
                "drucker": {
                    "status": "completed",
                    "output": plan,
                    "confidence_score": 1.0,  # Planning is deterministic
                    "validation_flags": []
                }
            },
            "audit_log": [audit_entry]
        }
    
    async def _marvin_node(self, state: PantheonState) -> Dict:
        """
        The Marvin (Diagnostics) - Operational assessment.
        """
        # Retrieve relevant sector knowledge
        knowledge = await self.retriever.retrieve_for_agent(
            agent_id="marvin",
            query=f"Operational KPIs and benchmarks for {state['sector_id']}",
            sector_id=state["sector_id"],
            country_code=state["sme_profile"]["country"],
            dimensions=[1, 3, 4, 7, 8]  # Classification, Ops, Regulatory, Workforce, Supply
        )
        
        # Load Marvin prompt
        marvin_prompt = load_agent_prompt("marvin")
        
        # Build context including human injections (&I)
        relevant_human_context = [
            hc for hc in state["human_context"]
            if hc.get("target_agent") in [None, "marvin"]
        ]
        
        context = {
            "sme_profile": state["sme_profile"],
            "questionnaire_responses": state["questionnaire_responses"],
            "sector_intelligence": knowledge["results"],
            "retrieval_quality": knowledge["retrieval_metadata"],
            "human_context": relevant_human_context,  # &I
            "active_lenses": state["selected_lenses"]
        }
        
        # Execute Marvin
        response = await self.llm.ainvoke([
            {"role": "system", "content": marvin_prompt},
            {"role": "user", "content": f"Conduct operational diagnostic: {json.dumps(context)}"}
        ])
        
        # Parse Marvin's assessment
        assessment = self._parse_marvin_response(response.content)
        
        # Check for validation triggers (&I)
        validation_triggers = self._check_marvin_triggers(assessment)
        
        return {
            "agent_outputs": {
                "marvin": {
                    "status": "completed" if not validation_triggers else "validation_required",
                    "output": assessment,
                    "confidence_score": assessment["overall_confidence"],
                    "confidence_breakdown": assessment["dimension_confidences"],
                    "validation_flags": validation_triggers,
                    "reasoning_trace": assessment.get("reasoning_trace", []),
                    "sources_used": [r.source_name for r in knowledge["results"][:5]]
                }
            },
            "pending_validations": validation_triggers,
            "audit_log": [{
                "timestamp": datetime.utcnow().isoformat(),
                "agent": "marvin",
                "action": "diagnostic_complete",
                "details": {
                    "overall_score": assessment["overall_score"],
                    "confidence": assessment["overall_confidence"],
                    "triggers": len(validation_triggers)
                }
            }]
        }
    
    # ... Similar implementations for other agents ...
    
    # ─────────────────────────────────────────────────────────────────
    # &I: Human-in-the-Loop Nodes
    # ─────────────────────────────────────────────────────────────────
    
    async def _hitl_gate_1(self, state: PantheonState) -> Dict:
        """
        Gate 1: Data Quality Check
        
        Triggers HITL if:
        - Questionnaire coverage < 70%
        - Critical data inconsistencies detected
        - Unverified claims in responses
        """
        triggers = []
        
        # Check questionnaire coverage
        coverage = self._calculate_questionnaire_coverage(
            state["questionnaire_responses"],
            state["sector_id"]
        )
        
        if coverage < 0.7:
            triggers.append({
                "trigger_id": str(uuid.uuid4()),
                "trigger_type": "data_gap",
                "severity": "high",
                "blocking": True,
                "description": f"Questionnaire coverage is {coverage:.0%}, minimum 70% required for reliable assessment",
                "required_reviewer": "embedded_associate",
                "resolution_options": [
                    "Request additional information from SME",
                    "Proceed with limited data (mark findings as low confidence)",
                    "Cancel diagnostic"
                ]
            })
        
        # Check for inconsistencies
        inconsistencies = self._detect_inconsistencies(state["questionnaire_responses"])
        if len(inconsistencies) > 3:
            triggers.append({
                "trigger_id": str(uuid.uuid4()),
                "trigger_type": "data_quality",
                "severity": "high",
                "blocking": True,
                "description": f"Detected {len(inconsistencies)} inconsistent responses",
                "affected_questions": inconsistencies,
                "required_reviewer": "embedded_associate"
            })
        
        return {
            "pending_validations": triggers if triggers else [],
            "current_phase": "validation" if triggers else "core_analysis"
        }
    
    def _route_gate_1(self, state: PantheonState) -> str:
        """Route based on Gate 1 validation status."""
        pending = [
            v for v in state.get("pending_validations", [])
            if v.get("blocking", False) and not v.get("resolved", False)
        ]
        
        if pending:
            return "human_required"
        return "proceed"
    
    async def _hitl_gate_2(self, state: PantheonState) -> Dict:
        """
        Gate 2: Finding Validation
        
        Triggers HITL if:
        - Agent confidence < 70% on critical finding
        - Cross-agent contradiction detected
        - Financial distress signals
        """
        triggers = []
        
        # Check Marvin's confidence
        marvin_output = state["agent_outputs"].get("marvin", {})
        if marvin_output.get("confidence_score", 1.0) < 0.7:
            triggers.append({
                "trigger_id": str(uuid.uuid4()),
                "trigger_type": "low_confidence",
                "severity": "high",
                "blocking": False,  # Can proceed but flag for review
                "description": f"Marvin's confidence is {marvin_output['confidence_score']:.0%}",
                "required_reviewer": "senior_expert",
                "agent": "marvin"
            })
        
        # Check Graham's financial assessment
        graham_output = state["agent_outputs"].get("graham", {})
        if graham_output:
            financial_health = graham_output.get("output", {}).get("financial_health_score", 100)
            if financial_health < 40:
                triggers.append({
                    "trigger_id": str(uuid.uuid4()),
                    "trigger_type": "critical_finding",
                    "severity": "critical",
                    "blocking": True,  # Cannot proceed without review
                    "description": f"Financial distress signals detected (score: {financial_health})",
                    "required_reviewer": "senior_expert",
                    "agent": "graham"
                })
        
        # Check for cross-agent conflicts
        conflicts = self._detect_agent_conflicts(state["agent_outputs"])
        for conflict in conflicts:
            triggers.append({
                "trigger_id": str(uuid.uuid4()),
                "trigger_type": "cross_agent_conflict",
                "severity": "high",
                "blocking": False,
                "description": conflict["description"],
                "agents_involved": conflict["agents"],
                "required_reviewer": "senior_expert"
            })
        
        return {
            "pending_validations": triggers,
            "current_phase": "validation" if triggers else "specialist_analysis"
        }
    
    async def _hitl_gate_3(self, state: PantheonState) -> Dict:
        """
        Gate 3: Strategic Validation
        
        Triggers HITL if:
        - Total recommended investment > $50K
        - Major business pivot suggested
        - Custom lens selected (ensure system can address)
        """
        triggers = []
        
        # Aggregate recommendations from all agents
        total_investment = 0
        major_recommendations = []
        
        for agent_id, output in state["agent_outputs"].items():
            if output.get("status") != "completed":
                continue
            
            agent_output = output.get("output", {})
            recommendations = agent_output.get("recommendations", [])
            
            for rec in recommendations:
                cost = rec.get("estimated_cost_usd", 0)
                total_investment += cost
                
                if cost > 25000 or rec.get("impact_level") == "transformational":
                    major_recommendations.append({
                        "agent": agent_id,
                        "recommendation": rec["title"],
                        "cost": cost,
                        "impact": rec.get("impact_level")
                    })
        
        if total_investment > 50000:
            triggers.append({
                "trigger_id": str(uuid.uuid4()),
                "trigger_type": "high_stakes_recommendation",
                "severity": "medium",
                "blocking": False,
                "description": f"Total recommended investment is ${total_investment:,.0f}",
                "details": major_recommendations,
                "required_reviewer": "senior_expert"
            })
        
        return {
            "pending_validations": triggers,
            "current_phase": "validation" if triggers else "synthesis"
        }
    
    async def _hitl_gate_4(self, state: PantheonState) -> Dict:
        """
        Gate 4: Final Sign-off
        
        Always triggers for SME owner to review final report.
        This is a non-blocking checkpoint that allows feedback.
        """
        return {
            "pending_validations": [{
                "trigger_id": str(uuid.uuid4()),
                "trigger_type": "final_review",
                "severity": "low",
                "blocking": False,
                "description": "Report ready for SME owner review",
                "required_reviewer": "sme_owner"
            }],
            "current_phase": "delivery"
        }


# ─────────────────────────────────────────────────────────────────────────
# HITL Trigger Conditions Summary
# ─────────────────────────────────────────────────────────────────────────

HITL_TRIGGER_CONDITIONS = {
    "gate_1_data_quality": {
        "questionnaire_coverage_below": 0.70,
        "inconsistencies_threshold": 3,
        "unverified_claims_threshold": 2,
        "handler": "embedded_associate",
        "blocking": True
    },
    "gate_2_finding_validation": {
        "agent_confidence_below": 0.70,
        "financial_distress_score_below": 40,
        "cross_agent_variance_above": 20,
        "handler": "senior_expert",
        "blocking_for": ["financial_distress", "regulatory_violation"]
    },
    "gate_3_strategic_validation": {
        "total_investment_above": 50000,
        "single_recommendation_above": 25000,
        "transformational_change_detected": True,
        "handler": "senior_expert",
        "blocking": False
    },
    "gate_4_final_signoff": {
        "always_trigger": True,
        "handler": "sme_owner",
        "blocking": False,
        "allows_feedback": True
    }
}
```

### 4.4 Parallel Execution

```python
async def _core_parallel_executor(self, state: PantheonState) -> Dict:
    """
    Execute Marvin and Graham in parallel.
    
    Both core agents run simultaneously since they have
    different input dependencies and can work independently.
    """
    # Create tasks for parallel execution
    tasks = [
        self._marvin_node(state),
        self._graham_node(state)
    ]
    
    # Execute in parallel
    results = await asyncio.gather(*tasks, return_exceptions=True)
    
    # Merge results
    merged_outputs = {}
    merged_validations = []
    merged_audit = []
    
    for result in results:
        if isinstance(result, Exception):
            # Handle error
            merged_outputs["error"] = str(result)
            continue
        
        merged_outputs.update(result.get("agent_outputs", {}))
        merged_validations.extend(result.get("pending_validations", []))
        merged_audit.extend(result.get("audit_log", []))
    
    return {
        "agent_outputs": merged_outputs,
        "pending_validations": merged_validations,
        "audit_log": merged_audit,
        "completed_agents": ["marvin", "graham"]
    }


async def _addon_parallel_executor(self, state: PantheonState) -> Dict:
    """
    Execute selected add-on agents in parallel.
    
    Only agents in selected_agents are executed.
    """
    addon_agents = ["ricardo", "lovelace", "mayo", "ohno", "porter", "landor"]
    selected_addons = [
        a for a in state["selected_agents"]
        if a in addon_agents
    ]
    
    if not selected_addons:
        return {}
    
    # Map agent IDs to their execution functions
    agent_functions = {
        "ricardo": self._ricardo_node,
        "lovelace": self._lovelace_node,
        "mayo": self._mayo_node,
        "ohno": self._ohno_node,
        "porter": self._porter_node,
        "landor": self._landor_node
    }
    
    # Create tasks
    tasks = [
        agent_functions[agent_id](state)
        for agent_id in selected_addons
    ]
    
    # Execute in parallel
    results = await asyncio.gather(*tasks, return_exceptions=True)
    
    # Merge results
    merged_outputs = {}
    merged_validations = []
    merged_audit = []
    
    for i, result in enumerate(results):
        agent_id = selected_addons[i]
        
        if isinstance(result, Exception):
            merged_outputs[agent_id] = {
                "status": "error",
                "error": str(result)
            }
            continue
        
        merged_outputs.update(result.get("agent_outputs", {}))
        merged_validations.extend(result.get("pending_validations", []))
        merged_audit.extend(result.get("audit_log", []))
    
    return {
        "agent_outputs": merged_outputs,
        "pending_validations": merged_validations,
        "audit_log": merged_audit,
        "completed_agents": state.get("completed_agents", []) + selected_addons
    }
```

### 4.5 Checkpointing and Resume

```python
# Enable human-in-the-loop with checkpointing
from langgraph.checkpoint.sqlite import SqliteSaver
from langgraph.graph import StateGraph

# Initialize checkpointer
checkpointer = SqliteSaver.from_conn_string("checkpoints.db")

# Compile graph with checkpointing
compiled_graph = workflow.compile(
    checkpointer=checkpointer,
    interrupt_before=["hitl_gate_1", "hitl_gate_2", "hitl_gate_3", "hitl_gate_4"]
)

# Running a diagnostic with interrupts
async def run_diagnostic_with_hitl(
    session_id: str,
    initial_state: PantheonState
):
    """
    Run a diagnostic that can pause for human input.
    """
    config = {"configurable": {"thread_id": session_id}}
    
    # Start execution
    async for event in compiled_graph.astream(
        initial_state,
        config=config,
        stream_mode="values"
    ):
        current_state = event
        
        # Check if we hit a validation gate
        if current_state.get("pending_validations"):
            blocking_validations = [
                v for v in current_state["pending_validations"]
                if v.get("blocking", False) and not v.get("resolved", False)
            ]
            
            if blocking_validations:
                # Return state for human review
                return {
                    "status": "waiting_for_human",
                    "session_id": session_id,
                    "pending_validations": blocking_validations,
                    "current_state": current_state
                }
    
    # Completed successfully
    return {
        "status": "completed",
        "session_id": session_id,
        "final_report": current_state.get("final_report")
    }


async def resume_after_human_input(
    session_id: str,
    validation_responses: List[Dict]
):
    """
    Resume a paused diagnostic after human validation.
    """
    config = {"configurable": {"thread_id": session_id}}
    
    # Get current state
    current_state = compiled_graph.get_state(config)
    
    # Apply human responses
    resolved_validations = []
    for response in validation_responses:
        validation = next(
            v for v in current_state.values["pending_validations"]
            if v["trigger_id"] == response["trigger_id"]
        )
        
        validation["resolved"] = True
        validation["resolution"] = response
        resolved_validations.append(validation)
    
    # Update state with resolutions
    updated_state = {
        **current_state.values,
        "resolved_validations": current_state.values.get("resolved_validations", []) + resolved_validations,
        "pending_validations": [
            v for v in current_state.values["pending_validations"]
            if v["trigger_id"] not in [r["trigger_id"] for r in resolved_validations]
        ]
    }
    
    # Resume execution
    async for event in compiled_graph.astream(
        None,  # None means resume from checkpoint
        config=config,
        stream_mode="values"
    ):
        current_state = event
        
        # Check for more validation gates
        if current_state.get("pending_validations"):
            blocking = [
                v for v in current_state["pending_validations"]
                if v.get("blocking") and not v.get("resolved")
            ]
            if blocking:
                return {
                    "status": "waiting_for_human",
                    "pending_validations": blocking
                }
    
    return {
        "status": "completed",
        "final_report": current_state.get("final_report")
    }
```

---

## Part 5: API Specification

The API layer exposes all Pantheon capabilities while ensuring &I principles are maintained through explicit transparency and override endpoints.

### 5.1 API Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                            API ARCHITECTURE                                  │
│                       (Human Agency Preserved)                               │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │                         API GATEWAY                                  │   │
│   │                   (FastAPI + Rate Limiting)                          │   │
│   └──────────────────────────┬──────────────────────────────────────────┘   │
│                              │                                               │
│         ┌────────────────────┼────────────────────┐                         │
│         │                    │                    │                         │
│         ▼                    ▼                    ▼                         │
│   ┌───────────┐       ┌───────────┐       ┌───────────┐                    │
│   │ Diagnostic│       │    SME    │       │Transparency│                    │
│   │ Endpoints │       │ Endpoints │       │ Endpoints  │                    │
│   │           │       │           │       │   (&I)     │                    │
│   └───────────┘       └───────────┘       └───────────┘                    │
│                                                                              │
│   Diagnostic:                SME:              Transparency:                 │
│   • /initiate               • /register        • /reasoning                  │
│   • /respond                • /profile         • /confidence-map             │
│   • /status                 • /history         • /sources                    │
│   • /report                 • /local-context   • /uncertainties              │
│   • /feedback               • /ai-assumptions  • /explain/{finding}          │
│                                                                              │
│   &I Override:              &I Context:        Admin:                        │
│   • /pause                  • /inject-context  • /sector-packs               │
│   • /override               • /inject-local    • /health                     │
│   • /skip-agent                                • /metrics                    │
│   • /request-human-review                                                    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 5.2 OpenAPI Specification

```yaml
openapi: 3.1.0
info:
  title: RootRise Pantheon API
  version: 1.0.0
  description: |
    API for the RootRise AI-powered SME diagnostic platform.
    
    ## &I Philosophy
    This API is designed with the &I Philosophy at its core:
    - AI + Human, not AI instead of Human
    - Every finding includes confidence scores
    - Human override capabilities at every stage
    - Full transparency into AI reasoning
    
    ## Authentication
    All endpoints require Bearer token authentication.

servers:
  - url: https://api.rootrise.ai/v1
    description: Production
  - url: https://staging-api.rootrise.ai/v1
    description: Staging

tags:
  - name: Diagnostic
    description: Core diagnostic workflow endpoints
  - name: SME
    description: SME profile management
  - name: Transparency
    description: "&I transparency endpoints - see what the AI is thinking"
  - name: Override
    description: "&I human override capabilities"
  - name: Admin
    description: System administration

paths:
  # ─────────────────────────────────────────────────────────────────
  # DIAGNOSTIC ENDPOINTS
  # ─────────────────────────────────────────────────────────────────
  
  /diagnostic/initiate:
    post:
      tags: [Diagnostic]
      summary: Start a new diagnostic session
      description: |
        Initializes a new diagnostic session for an SME.
        Returns a session ID for subsequent operations.
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [sme_id, configuration]
              properties:
                sme_id:
                  type: string
                  format: uuid
                configuration:
                  type: object
                  required: [selected_agents, sector_id, selected_lenses]
                  properties:
                    selected_agents:
                      type: array
                      items:
                        type: string
                        enum: [drucker, marvin, graham, ricardo, lovelace, mayo, ohno, porter, landor]
                      minItems: 2
                      description: "Core agents (drucker, marvin, graham) are always included"
                    sector_id:
                      type: string
                      example: "food_bev_manufacturing"
                    subsector_id:
                      type: string
                      nullable: true
                    selected_lenses:
                      type: array
                      items:
                        type: string
                      example: ["export_readiness", "profitability"]
                    report_format:
                      type: string
                      enum: [executive_summary, detailed, presentation, dashboard]
                      default: detailed
                    language:
                      type: string
                      enum: [en, ar, bilingual]
                      default: en
                    benchmark_set:
                      type: string
                      enum: [mena_regional, industry_specific, global, custom]
                      default: mena_regional
      responses:
        '201':
          description: Session created
          content:
            application/json:
              schema:
                type: object
                properties:
                  session_id:
                    type: string
                    format: uuid
                  status:
                    type: string
                    enum: [initialized]
                  questionnaire_url:
                    type: string
                    format: uri
                    description: URL to begin questionnaire
                  estimated_completion_time:
                    type: string
                    example: "30 minutes"
  
  /diagnostic/{session_id}/respond:
    post:
      tags: [Diagnostic]
      summary: Submit questionnaire responses
      description: |
        Submit answers to diagnostic questionnaire.
        Can be called multiple times as user progresses.
      parameters:
        - name: session_id
          in: path
          required: true
          schema:
            type: string
            format: uuid
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [responses]
              properties:
                responses:
                  type: array
                  items:
                    type: object
                    required: [question_id, response]
                    properties:
                      question_id:
                        type: string
                      response:
                        oneOf:
                          - type: string
                          - type: number
                          - type: array
                            items:
                              type: string
                      user_confidence:
                        type: number
                        minimum: 0
                        maximum: 1
                        description: "How confident is the user in this answer (0-1)"
                      includes_local_context:
                        type: boolean
                        description: "&I: User indicates this response has local nuance"
                complete:
                  type: boolean
                  description: "Set to true when questionnaire is complete"
      responses:
        '200':
          description: Responses recorded
          content:
            application/json:
              schema:
                type: object
                properties:
                  progress:
                    type: object
                    properties:
                      completed:
                        type: integer
                      total:
                        type: integer
                      coverage:
                        type: number
                        description: "Percentage of required questions answered"
                  next_section:
                    type: string
                    nullable: true
                  status:
                    type: string
                    enum: [questionnaire, processing, completed]
  
  /diagnostic/{session_id}/status:
    get:
      tags: [Diagnostic]
      summary: Get diagnostic session status
      description: |
        Returns current status of the diagnostic session including:
        - Overall progress
        - Which agents have completed
        - Any pending validations (HITL triggers)
        - Confidence scores so far
      parameters:
        - name: session_id
          in: path
          required: true
          schema:
            type: string
            format: uuid
      responses:
        '200':
          description: Session status
          content:
            application/json:
              schema:
                type: object
                properties:
                  session_id:
                    type: string
                  status:
                    type: string
                    enum: [initialized, questionnaire, processing, validation_required, report_generation, completed, abandoned, error]
                  current_phase:
                    type: string
                  progress:
                    type: object
                    properties:
                      agents_completed:
                        type: array
                        items:
                          type: string
                      agents_pending:
                        type: array
                        items:
                          type: string
                      overall_percentage:
                        type: number
                  # &I: Show validation requirements
                  pending_validations:
                    type: array
                    items:
                      $ref: '#/components/schemas/ValidationTrigger'
                  # &I: Early confidence indicators
                  preliminary_confidence:
                    type: number
                    description: "Overall confidence so far (0-1)"
                  estimated_remaining_time:
                    type: string
  
  /diagnostic/{session_id}/report:
    get:
      tags: [Diagnostic]
      summary: Get completed diagnostic report
      description: |
        Retrieves the final diagnostic report after completion.
        
        ## &I Note
        The report includes:
        - Confidence scores for every finding
        - Source attribution for benchmarks
        - Areas of uncertainty flagged
        - Questions for the SME to consider
      parameters:
        - name: session_id
          in: path
          required: true
          schema:
            type: string
            format: uuid
        - name: format
          in: query
          schema:
            type: string
            enum: [json, pdf, docx, html]
            default: json
      responses:
        '200':
          description: Diagnostic report
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/DiagnosticReport'
            application/pdf:
              schema:
                type: string
                format: binary
  
  # ─────────────────────────────────────────────────────────────────
  # &I OVERRIDE ENDPOINTS
  # ─────────────────────────────────────────────────────────────────
  
  /diagnostic/{session_id}/pause:
    post:
      tags: [Override]
      summary: Pause diagnostic for human review
      description: |
        **&I Capability**: Allows human to pause the diagnostic at any point
        to review progress, inject context, or redirect analysis.
      parameters:
        - name: session_id
          in: path
          required: true
          schema:
            type: string
            format: uuid
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                reason:
                  type: string
                  description: "Why is the diagnostic being paused?"
                pause_after_current_agent:
                  type: boolean
                  default: true
                  description: "Wait for current agent to finish before pausing"
      responses:
        '200':
          description: Diagnostic paused
          content:
            application/json:
              schema:
                type: object
                properties:
                  status:
                    type: string
                    const: "paused"
                  current_state_summary:
                    type: object
                    description: "Summary of progress so far"
                  resume_url:
                    type: string
                    format: uri
  
  /diagnostic/{session_id}/override:
    post:
      tags: [Override]
      summary: Override an AI finding
      description: |
        **&I Capability**: Allows human to override any AI-generated finding.
        
        The override is logged in the audit trail and reflected in the final report
        with clear attribution: "AI assessed X, human validated as Y".
      parameters:
        - name: session_id
          in: path
          required: true
          schema:
            type: string
            format: uuid
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [override_type, target_agent, rationale]
              properties:
                override_type:
                  type: string
                  enum: [score_adjustment, finding_rejection, recommendation_modification, confidence_override]
                target_agent:
                  type: string
                  description: "Which agent's output to override"
                target_finding_id:
                  type: string
                  description: "Specific finding ID if applicable"
                original_value:
                  description: "What the AI concluded"
                override_value:
                  description: "What the human is overriding to"
                rationale:
                  type: string
                  minLength: 10
                  description: "Explanation for the override (required for audit)"
      responses:
        '200':
          description: Override applied
          content:
            application/json:
              schema:
                type: object
                properties:
                  override_id:
                    type: string
                  status:
                    type: string
                    const: "applied"
                  affected_downstream:
                    type: array
                    items:
                      type: string
                    description: "Agents that will re-evaluate based on this override"
  
  /diagnostic/{session_id}/inject-context:
    post:
      tags: [Override]
      summary: Inject human context into analysis
      description: |
        **&I Capability**: Allows human to inject local knowledge, cultural context,
        or relationship information that the AI should consider.
        
        Examples:
        - "In our region, suppliers typically require 60-day payment terms"
        - "We have a strategic relationship with Company X"
        - "Ramadan significantly impacts our sales pattern"
      parameters:
        - name: session_id
          in: path
          required: true
          schema:
            type: string
            format: uuid
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [context_type, content]
              properties:
                context_type:
                  type: string
                  enum: [local_market_knowledge, relationship_context, cultural_factor, historical_context, correction, clarification]
                target_dimension:
                  type: string
                  description: "Which dimension this relates to"
                target_agent:
                  type: string
                  description: "Which agent should especially consider this"
                content:
                  type: string
                  minLength: 10
                  description: "The context to inject"
                weight_adjustment:
                  type: string
                  enum: [high, medium, low]
                  default: medium
                  description: "How much weight to give this context"
                override_ai_inference:
                  type: boolean
                  default: false
                  description: "Should this override conflicting AI conclusions?"
      responses:
        '201':
          description: Context injected
          content:
            application/json:
              schema:
                type: object
                properties:
                  injection_id:
                    type: string
                  status:
                    type: string
                    const: "applied"
                  agents_notified:
                    type: array
                    items:
                      type: string
  
  /diagnostic/{session_id}/request-human-review:
    post:
      tags: [Override]
      summary: Request human expert review
      description: |
        **&I Capability**: Explicitly request human expert review of 
        specific findings or the overall diagnostic.
      parameters:
        - name: session_id
          in: path
          required: true
          schema:
            type: string
            format: uuid
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [review_type]
              properties:
                review_type:
                  type: string
                  enum: [specific_finding, agent_output, overall_diagnostic]
                target_ids:
                  type: array
                  items:
                    type: string
                  description: "Specific findings/agents to review"
                reviewer_expertise:
                  type: string
                  enum: [financial_expert, industry_expert, regional_expert, senior_advisor]
                urgency:
                  type: string
                  enum: [standard, priority, urgent]
                  default: standard
                notes:
                  type: string
                  description: "What should the reviewer focus on?"
      responses:
        '202':
          description: Review requested
          content:
            application/json:
              schema:
                type: object
                properties:
                  review_id:
                    type: string
                  estimated_response_time:
                    type: string
                  status:
                    type: string
                    const: "pending_review"
  
  # ─────────────────────────────────────────────────────────────────
  # &I TRANSPARENCY ENDPOINTS
  # ─────────────────────────────────────────────────────────────────
  
  /diagnostic/{session_id}/reasoning:
    get:
      tags: [Transparency]
      summary: Get AI reasoning trace
      description: |
        **&I Transparency**: Returns the step-by-step reasoning trace
        for how the AI arrived at its conclusions.
        
        "Show your work" for AI analysis.
      parameters:
        - name: session_id
          in: path
          required: true
          schema:
            type: string
            format: uuid
        - name: agent_id
          in: query
          schema:
            type: string
          description: "Filter to specific agent's reasoning"
      responses:
        '200':
          description: Reasoning trace
          content:
            application/json:
              schema:
                type: object
                properties:
                  agents:
                    type: object
                    additionalProperties:
                      type: array
                      items:
                        type: object
                        properties:
                          step:
                            type: integer
                          action:
                            type: string
                          rationale:
                            type: string
                          data_used:
                            type: array
                            items:
                              type: string
                          confidence_at_step:
                            type: number
  
  /diagnostic/{session_id}/confidence-map:
    get:
      tags: [Transparency]
      summary: Get confidence scores across all findings
      description: |
        **&I Transparency**: Returns a map of confidence scores
        for every dimension and finding.
        
        Helps identify where AI is certain vs uncertain.
      parameters:
        - name: session_id
          in: path
          required: true
          schema:
            type: string
            format: uuid
      responses:
        '200':
          description: Confidence map
          content:
            application/json:
              schema:
                type: object
                properties:
                  overall_confidence:
                    type: number
                  by_dimension:
                    type: object
                    additionalProperties:
                      type: object
                      properties:
                        confidence:
                          type: number
                        data_coverage:
                          type: number
                        key_uncertainties:
                          type: array
                          items:
                            type: string
                  low_confidence_findings:
                    type: array
                    items:
                      type: object
                      properties:
                        finding_id:
                          type: string
                        finding_summary:
                          type: string
                        confidence:
                          type: number
                        why_uncertain:
                          type: string
  
  /diagnostic/{session_id}/sources:
    get:
      tags: [Transparency]
      summary: Get data sources used
      description: |
        **&I Transparency**: Returns all data sources that
        informed the diagnostic.
        
        "What is the AI basing this on?"
      parameters:
        - name: session_id
          in: path
          required: true
          schema:
            type: string
            format: uuid
      responses:
        '200':
          description: Source list
          content:
            application/json:
              schema:
                type: object
                properties:
                  questionnaire_responses:
                    type: integer
                    description: "Number of user responses used"
                  sector_knowledge:
                    type: array
                    items:
                      type: object
                      properties:
                        source_name:
                          type: string
                        source_type:
                          type: string
                        publication_date:
                          type: string
                        reliability:
                          type: number
                        data_points_used:
                          type: integer
                  human_context_injections:
                    type: integer
                    description: "Number of human context injections"
                  benchmark_sets:
                    type: array
                    items:
                      type: string
  
  /diagnostic/{session_id}/uncertainties:
    get:
      tags: [Transparency]
      summary: Get what AI doesn't know
      description: |
        **&I Transparency**: Returns explicit acknowledgment of
        what the AI doesn't know or is uncertain about.
        
        Gaps in data, low-confidence areas, assumptions made.
      parameters:
        - name: session_id
          in: path
          required: true
          schema:
            type: string
            format: uuid
      responses:
        '200':
          description: Uncertainties list
          content:
            application/json:
              schema:
                type: object
                properties:
                  data_gaps:
                    type: array
                    items:
                      type: object
                      properties:
                        dimension:
                          type: string
                        what_missing:
                          type: string
                        impact:
                          type: string
                        recommendation:
                          type: string
                  assumptions_made:
                    type: array
                    items:
                      type: object
                      properties:
                        assumption:
                          type: string
                        based_on:
                          type: string
                        confidence:
                          type: number
                        how_to_verify:
                          type: string
                  areas_needing_human_judgment:
                    type: array
                    items:
                      type: object
                      properties:
                        area:
                          type: string
                        why_human_needed:
                          type: string
                        questions_to_consider:
                          type: array
                          items:
                            type: string
  
  /diagnostic/{session_id}/explain/{finding_id}:
    get:
      tags: [Transparency]
      summary: Explain a specific finding
      description: |
        **&I Transparency**: Get detailed explanation of how
        a specific finding was derived.
        
        Includes data sources, reasoning chain, confidence factors.
      parameters:
        - name: session_id
          in: path
          required: true
          schema:
            type: string
            format: uuid
        - name: finding_id
          in: path
          required: true
          schema:
            type: string
      responses:
        '200':
          description: Finding explanation
          content:
            application/json:
              schema:
                type: object
                properties:
                  finding_id:
                    type: string
                  finding_summary:
                    type: string
                  agent_source:
                    type: string
                  explanation:
                    type: object
                    properties:
                      plain_english:
                        type: string
                        description: "Non-technical explanation"
                      data_inputs:
                        type: array
                        items:
                          type: object
                          properties:
                            source:
                              type: string
                            value:
                              type: string
                            weight:
                              type: number
                      reasoning_chain:
                        type: array
                        items:
                          type: string
                      benchmark_comparison:
                        type: object
                        properties:
                          sme_value:
                            type: string
                          benchmark_value:
                            type: string
                          benchmark_source:
                            type: string
                      confidence_factors:
                        type: object
                        properties:
                          positive:
                            type: array
                            items:
                              type: string
                          negative:
                            type: array
                            items:
                              type: string
                      alternative_interpretations:
                        type: array
                        items:
                          type: string
                        description: "Other ways to interpret this data"

# ─────────────────────────────────────────────────────────────────
# COMPONENT SCHEMAS
# ─────────────────────────────────────────────────────────────────

components:
  schemas:
    ValidationTrigger:
      type: object
      properties:
        trigger_id:
          type: string
        trigger_type:
          type: string
          enum: [low_confidence, critical_finding, cross_agent_conflict, data_gap, high_stakes_recommendation, regulatory_concern, anomaly_detected]
        severity:
          type: string
          enum: [critical, high, medium, low]
        blocking:
          type: boolean
          description: "Does this block progress until resolved?"
        description:
          type: string
        required_reviewer:
          type: string
          enum: [sme_owner, embedded_associate, senior_expert, domain_expert]
        resolution_options:
          type: array
          items:
            type: string
    
    DiagnosticReport:
      type: object
      properties:
        report_id:
          type: string
        session_id:
          type: string
        generated_at:
          type: string
          format: date-time
        sme_name:
          type: string
        sector:
          type: string
        
        # Overall Results
        overall_score:
          type: number
          minimum: 0
          maximum: 100
        overall_confidence:
          type: number
          minimum: 0
          maximum: 1
          description: "&I: How confident is the AI in this assessment?"
        
        # Executive Summary
        executive_summary:
          type: object
          properties:
            headline:
              type: string
            key_strengths:
              type: array
              items:
                type: string
            critical_gaps:
              type: array
              items:
                type: string
            top_recommendations:
              type: array
              items:
                type: string
        
        # Dimension Scores
        dimension_scores:
          type: array
          items:
            type: object
            properties:
              dimension:
                type: string
              score:
                type: number
              benchmark:
                type: number
              gap:
                type: number
              confidence:
                type: number
              findings:
                type: array
                items:
                  type: object
                  properties:
                    finding_id:
                      type: string
                    title:
                      type: string
                    description:
                      type: string
                    confidence:
                      type: number
                    evidence:
                      type: array
                      items:
                        type: string
        
        # &I Transparency Section
        ai_transparency:
          type: object
          properties:
            data_coverage:
              type: string
              description: "How complete was the input data?"
            key_assumptions:
              type: array
              items:
                type: string
            areas_of_uncertainty:
              type: array
              items:
                type: string
            human_inputs:
              type: integer
              description: "Number of human context injections"
            human_overrides:
              type: integer
              description: "Number of human overrides applied"
        
        # Action Plan
        action_plan:
          type: object
          properties:
            total_actions:
              type: integer
            quick_wins:
              type: array
              items:
                $ref: '#/components/schemas/ActionItem'
            transformation_roadmap:
              type: array
              items:
                $ref: '#/components/schemas/ActionItem'
    
    ActionItem:
      type: object
      properties:
        action_id:
          type: string
        title:
          type: string
        description:
          type: string
        category:
          type: string
        effort_level:
          type: string
          enum: [low, medium, high]
        impact_level:
          type: string
          enum: [low, medium, high]
        timeline_days:
          type: integer
        estimated_cost_usd:
          type: number
        expected_outcome:
          type: string
        confidence:
          type: number
          description: "&I: How confident is the AI in this recommendation?"
        source_agent:
          type: string

  securitySchemes:
    bearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT

security:
  - bearerAuth: []
```

---

## Part 6: Deployment Architecture

### 6.1 Infrastructure Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        DEPLOYMENT ARCHITECTURE                               │
│                      (&I Operational Philosophy)                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                         LOAD BALANCER                                │    │
│  │                    (AWS ALB / CloudFlare)                            │    │
│  └───────────────────────────────┬─────────────────────────────────────┘    │
│                                  │                                          │
│  ┌───────────────────────────────┼─────────────────────────────────────┐    │
│  │                         API LAYER                                    │    │
│  │                                                                       │    │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐                   │    │
│  │  │  FastAPI    │  │  FastAPI    │  │  FastAPI    │   (Auto-scaling)  │    │
│  │  │  Instance 1 │  │  Instance 2 │  │  Instance N │                   │    │
│  │  └─────────────┘  └─────────────┘  └─────────────┘                   │    │
│  │                                                                       │    │
│  └───────────────────────────────┬─────────────────────────────────────┘    │
│                                  │                                          │
│  ┌───────────────────────────────┼─────────────────────────────────────┐    │
│  │                      MESSAGE QUEUE                                   │    │
│  │                     (Redis / RabbitMQ)                               │    │
│  │                                                                       │    │
│  │  Queues:                                                              │    │
│  │  • diagnostic_sessions       - New diagnostic requests                │    │
│  │  • agent_tasks               - Individual agent executions            │    │
│  │  • hitl_validations          - Human review requests                  │    │
│  │  • report_generation         - Report creation jobs                   │    │
│  │                                                                       │    │
│  └───────────────────────────────┬─────────────────────────────────────┘    │
│                                  │                                          │
│  ┌───────────────────────────────┼─────────────────────────────────────┐    │
│  │                     WORKER LAYER                                     │    │
│  │                                                                       │    │
│  │  ┌─────────────────────────────────────────────────────────────┐     │    │
│  │  │              LANGGRAPH WORKERS                               │     │    │
│  │  │                                                               │     │    │
│  │  │  ┌───────────┐  ┌───────────┐  ┌───────────┐                 │     │    │
│  │  │  │ Worker 1  │  │ Worker 2  │  │ Worker N  │  (Auto-scaling) │     │    │
│  │  │  │           │  │           │  │           │                 │     │    │
│  │  │  │ LangGraph │  │ LangGraph │  │ LangGraph │                 │     │    │
│  │  │  │ Runtime   │  │ Runtime   │  │ Runtime   │                 │     │    │
│  │  │  └───────────┘  └───────────┘  └───────────┘                 │     │    │
│  │  │                                                               │     │    │
│  │  └─────────────────────────────────────────────────────────────┘     │    │
│  │                                                                       │    │
│  └───────────────────────────────┬─────────────────────────────────────┘    │
│                                  │                                          │
│  ┌───────────────────────────────┴─────────────────────────────────────┐    │
│  │                        DATA LAYER                                    │    │
│  │                                                                       │    │
│  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐                │    │
│  │  │  PostgreSQL  │  │    Redis     │  │   Qdrant     │                │    │
│  │  │              │  │              │  │              │                │    │
│  │  │  • SME       │  │  • Sessions  │  │  • Sector    │                │    │
│  │  │    Profiles  │  │  • Cache     │  │    Knowledge │                │    │
│  │  │  • History   │  │  • Rate      │  │  • Embeddings│                │    │
│  │  │  • Reports   │  │    Limits    │  │              │                │    │
│  │  └──────────────┘  └──────────────┘  └──────────────┘                │    │
│  │                                                                       │    │
│  │  ┌──────────────┐  ┌──────────────┐                                  │    │
│  │  │     S3       │  │   SQLite     │                                  │    │
│  │  │              │  │              │                                  │    │
│  │  │  • Reports   │  │  • LangGraph │                                  │    │
│  │  │  • Documents │  │   Checkpts   │                                  │    │
│  │  │  • Exports   │  │              │                                  │    │
│  │  └──────────────┘  └──────────────┘                                  │    │
│  │                                                                       │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                      EXTERNAL SERVICES                               │    │
│  │                                                                       │    │
│  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐                │    │
│  │  │   OpenAI     │  │   Cohere     │  │  SendGrid    │                │    │
│  │  │              │  │              │  │              │                │    │
│  │  │  • GPT-4     │  │  • Embed     │  │  • Emails    │                │    │
│  │  │  • Agents    │  │  • Rerank    │  │  • Alerts    │                │    │
│  │  └──────────────┘  └──────────────┘  └──────────────┘                │    │
│  │                                                                       │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 6.2 Resource Requirements

#### Compute Requirements

| Component | Instance Type | Count | Monthly Cost (Est.) |
|-----------|--------------|-------|---------------------|
| **API Servers** | t3.medium (2 vCPU, 4GB) | 2-4 (auto-scale) | $60-120 |
| **LangGraph Workers** | c6i.large (2 vCPU, 4GB) | 2-6 (auto-scale) | $120-360 |
| **Database (PostgreSQL)** | db.t3.medium (2 vCPU, 4GB) | 1 | $50 |
| **Cache (Redis)** | cache.t3.medium | 1 | $45 |
| **Vector DB (Qdrant)** | t3.large (2 vCPU, 8GB) | 1 | $60 |
| **Load Balancer** | ALB | 1 | $25 |

**Estimated Compute Total: $360-660/month**

#### Storage Requirements

| Storage Type | Size | Monthly Cost (Est.) |
|--------------|------|---------------------|
| **PostgreSQL Storage** | 100GB SSD | $12 |
| **Redis Storage** | 10GB | Included |
| **Qdrant Storage** | 50GB SSD | $6 |
| **S3 (Reports)** | 500GB | $12 |
| **S3 (Checkpoints)** | 100GB | $2 |

**Estimated Storage Total: $32/month**

#### External API Costs

| Service | Usage Estimate | Monthly Cost (Est.) |
|---------|----------------|---------------------|
| **OpenAI GPT-4o** | 100 diagnostics × 50K tokens | $250 |
| **OpenAI Embeddings** | One-time + incremental | $5 |
| **SendGrid** | 1000 emails | $15 |

**Estimated API Total: $270/month**

#### Total Infrastructure Estimate

| Category | Monthly Cost |
|----------|--------------|
| Compute | $360-660 |
| Storage | $32 |
| External APIs | $270 |
| **Total** | **$662-962/month** |

*Note: Costs will vary based on usage. Estimates based on 100 diagnostics/month.*

### 6.3 &I Operational Principles

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       &I OPERATIONAL PRINCIPLES                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  1. GRACEFUL DEGRADATION                                                     │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │  If AI uncertain → Escalate to human, don't guess                    │    │
│  │  If data sparse → Acknowledge gaps, don't hallucinate                │    │
│  │  If system overloaded → Queue with transparency ("You're #5...")     │    │
│  │  If agent fails → Provide partial results with clear limitations     │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  2. HUMAN ACCOUNTABILITY                                                     │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │  Clear audit trail of AI suggestions vs human decisions              │    │
│  │  Human can always see "what AI recommended"                          │    │
│  │  Final actions require human confirmation                            │    │
│  │  Reports clearly mark AI-generated vs human-validated                │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  3. CONTINUOUS LEARNING (With Human Oversight)                               │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │  Human feedback improves future diagnostics                          │    │
│  │  BUT humans validate what the system "learned"                       │    │
│  │  No autonomous model updates without human review                    │    │
│  │  Learning happens through curated knowledge pack updates             │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  4. TRANSPARENCY METRICS (Dashboard)                                         │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │  Track HITL trigger frequency → Are we escalating appropriately?     │    │
│  │  Track human override frequency → Is AI calibrated correctly?        │    │
│  │  Track confidence accuracy → When AI is confident, is it right?      │    │
│  │  Track user satisfaction with AI explanations                        │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 6.4 Monitoring and Alerts

```yaml
# Prometheus Alerting Rules for &I Metrics

groups:
  - name: pantheon_ai_health
    rules:
      # Alert if HITL triggers spike (may indicate calibration issue)
      - alert: HITLTriggerRateHigh
        expr: rate(hitl_triggers_total[1h]) > 0.5
        for: 30m
        labels:
          severity: warning
        annotations:
          summary: "HITL trigger rate elevated"
          description: "More than 50% of diagnostics triggering human review"
      
      # Alert if override rate is high (AI may need recalibration)
      - alert: HumanOverrideRateHigh
        expr: rate(human_overrides_total[1d]) / rate(diagnostics_completed_total[1d]) > 0.3
        for: 1h
        labels:
          severity: warning
        annotations:
          summary: "Human override rate is high"
          description: "More than 30% of diagnostics have human overrides"
      
      # Alert if confidence calibration is off
      - alert: ConfidenceCalibrationDrift
        expr: |
          abs(
            avg(confidence_score{outcome="correct"}) -
            avg(confidence_score{outcome="incorrect"})
          ) < 0.2
        for: 1d
        labels:
          severity: warning
        annotations:
          summary: "Confidence calibration may be drifting"
          description: "Confidence scores not differentiating correct from incorrect findings"
      
      # Alert if agents are taking too long
      - alert: AgentExecutionSlow
        expr: histogram_quantile(0.95, rate(agent_execution_duration_seconds_bucket[5m])) > 60
        for: 10m
        labels:
          severity: warning
        annotations:
          summary: "Agent execution is slow"
          description: "95th percentile agent execution time exceeds 60 seconds"
```

---

## Part 7: Resource Estimates Summary

### 7.1 Development Resources

| Phase | Duration | Team | Cost Estimate |
|-------|----------|------|---------------|
| **Phase 1: Core Infrastructure** | 4 weeks | Ahmed + 1 Backend | $15,000 |
| Memory architecture, Vector DB setup, Basic API | | | |
| **Phase 2: LangGraph Integration** | 3 weeks | Ahmed + 1 ML Engineer | $12,000 |
| Graph implementation, Agent nodes, HITL gates | | | |
| **Phase 3: Agent Prompts Integration** | 2 weeks | Ahmed + Tee | $8,000 |
| Prompt loading, Output parsing, Validation | | | |
| **Phase 4: API Development** | 3 weeks | Ahmed + 1 Backend | $12,000 |
| Full REST API, WebSocket for real-time updates | | | |
| **Phase 5: Testing & QA** | 2 weeks | Team | $8,000 |
| Integration tests, Load tests, Security audit | | | |
| **Phase 6: Deployment** | 1 week | Ahmed + DevOps | $4,000 |
| Infrastructure setup, CI/CD, Monitoring | | | |

**Total Development: ~15 weeks, ~$59,000**

### 7.2 Ongoing Operational Costs

| Category | Monthly Cost | Annual Cost |
|----------|--------------|-------------|
| Infrastructure | $660 | $7,920 |
| OpenAI API | $270 | $3,240 |
| Monitoring (DataDog/similar) | $100 | $1,200 |
| Support & Maintenance | $2,000 | $24,000 |
| **Total** | **$3,030** | **$36,360** |

### 7.3 Scaling Projections

| Diagnostics/Month | Infrastructure | API Costs | Total Monthly |
|-------------------|----------------|-----------|---------------|
| 100 | $660 | $270 | $930 |
| 500 | $1,200 | $1,350 | $2,550 |
| 1,000 | $2,000 | $2,700 | $4,700 |
| 5,000 | $5,000 | $13,500 | $18,500 |

---

## Part 8: Implementation Checklist for Ahmed

### Week 1-2: Foundation

- [ ] Set up PostgreSQL with SME profile schema
- [ ] Set up Redis for session management
- [ ] Set up Qdrant vector database
- [ ] Create base FastAPI application structure
- [ ] Implement authentication/authorization

### Week 3-4: Memory Architecture

- [ ] Implement DiagnosticSession model
- [ ] Implement MemoryManager class
- [ ] Create human context injection endpoints
- [ ] Create human override endpoints
- [ ] Write unit tests for memory operations

### Week 5-7: LangGraph Implementation

- [ ] Implement PantheonState schema
- [ ] Create Drucker node (orchestrator)
- [ ] Create Marvin node (diagnostics)
- [ ] Create Graham node (finance)
- [ ] Implement parallel execution coordinator
- [ ] Implement HITL gates (4 gates)
- [ ] Set up checkpointing with SQLite
- [ ] Test graph execution end-to-end

### Week 8-9: Add-On Agents

- [ ] Implement Ricardo, Lovelace, Mayo nodes
- [ ] Implement Ohno, Porter, Landor nodes
- [ ] Implement Deming (quality) node
- [ ] Implement Tufte (reports) node
- [ ] Test parallel add-on execution

### Week 10-11: Vector Database

- [ ] Create chunking pipeline
- [ ] Index all sector knowledge packs
- [ ] Implement retrieval patterns
- [ ] Add confidence metadata
- [ ] Test retrieval quality

### Week 12-13: API Development

- [ ] Implement all diagnostic endpoints
- [ ] Implement transparency endpoints
- [ ] Implement override endpoints
- [ ] Add WebSocket for real-time updates
- [ ] Generate OpenAPI documentation

### Week 14: Testing

- [ ] Integration tests
- [ ] Load testing (100 concurrent diagnostics)
- [ ] Security audit
- [ ] &I metrics validation

### Week 15: Deployment

- [ ] Set up AWS infrastructure
- [ ] Configure CI/CD pipeline
- [ ] Set up monitoring and alerting
- [ ] Deploy to staging
- [ ] Production deployment

---

## Appendix A: Agent Dependency Graph

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
       │  (Diag)  │              │(Finance) │
       └────┬─────┘              └────┬─────┘
            │                         │
    ┌───────┼───────┐         ┌──────┼──────┐
    │       │       │         │      │      │
    ▼       ▼       ▼         ▼      ▼      ▼
┌──────┐┌──────┐┌──────┐ ┌──────┐┌──────┐┌──────┐
│OHNO  ││MAYO  ││LOVELCE││PORTER││RICARDO││LANDOR│
│Supply││ HR   ││Digital││Market││Export ││Packag│
└──┬───┘└──┬───┘└───┬───┘└──┬───┘└───┬───┘└───┬──┘
   │       │        │       │        │        │
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

## Appendix B: Glossary

| Term | Definition |
|------|------------|
| **&I Philosophy** | AI + Human collaboration principle: AI augments, never replaces, human judgment |
| **HITL** | Human-in-the-Loop - checkpoints where human review is triggered |
| **The Pantheon** | Collective name for RootRise's 11 AI agents |
| **Sector Knowledge Pack** | Structured intelligence file containing benchmarks, regulations, KPIs for a specific industry |
| **Validation Gate** | One of 4 HITL checkpoints in the diagnostic workflow |
| **Confidence Score** | 0-1 metric indicating AI certainty in a finding |
| **Human Context Injection** | User-provided local knowledge that AI incorporates |
| **Human Override** | User correction of an AI-generated finding |

---

*Document prepared by Tee (CTO) for Ahmed El-Gazzar (Technical DevOps Lead)*  
*RootRise by DEVONEERS - December 2025*
