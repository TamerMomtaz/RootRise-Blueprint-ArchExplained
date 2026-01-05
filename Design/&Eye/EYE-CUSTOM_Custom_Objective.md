# EYE-CUSTOM: Custom Objective Lens

## Lens Overview

```
╔═══════════════════════════════════════════════════════════════════════════════╗
║                                                                               ║
║                    THE &EYE — CUSTOM OBJECTIVE LENS                           ║
║                                                                               ║
║                      "Your Goal. Your Transformation."                        ║
║                                                                               ║
╠═══════════════════════════════════════════════════════════════════════════════╣
║                                                                               ║
║   LENS ID:        EYE-CUSTOM                                                  ║
║   LENS NAME:      Custom Objective                                            ║
║   CATEGORY:       Custom                                                      ║
║   PRIMARY FOCUS:  User-defined transformation objective                       ║
║                                                                               ║
║   USER STATEMENT: "I have a specific goal that doesn't fit the standard       ║
║                    lenses — let me describe what I'm trying to achieve."      ║
║                                                                               ║
║   KEY INSIGHT:    Every SME is unique. While our 15 standard lenses cover     ║
║                   the most common transformation objectives, some businesses  ║
║                   have specific goals that require a tailored approach.       ║
║                   The Custom Objective lens uses AI to interpret the user's   ║
║                   goal and dynamically configure agent priorities.            ║
║                                                                               ║
╚═══════════════════════════════════════════════════════════════════════════════╝
```

---

## Lens Philosophy

### Why Custom Objectives Matter

The &I Philosophy at the heart of RootRise emphasizes human agency — the SME owner knows their business best. While our standard lenses capture common transformation patterns, the Custom Objective lens acknowledges that:

1. **Every business is unique** — Some goals don't fit neatly into predefined categories
2. **Context matters** — The same business might need different focus at different times
3. **User knows best** — The SME owner understands nuances we can't anticipate
4. **Flexibility builds trust** — Not forcing users into boxes shows respect for their expertise

### When to Use Custom Objective

| Use Case | Example |
|----------|---------|
| Niche transformation | "I want to transition from B2C to B2B" |
| Combined objectives | "I want to grow exports while preparing for family succession" |
| Industry-specific | "I want to become a preferred supplier for automotive OEMs" |
| Time-bound goals | "I want to be acquisition-ready within 18 months" |
| Recovery scenarios | "I want to recover from a major customer loss" |
| Opportunity capture | "I want to capitalize on a new regulation in my sector" |

---

## Lens Configuration

### Technical Specification

```yaml
lens_id: "eye_custom"
display_name: "Custom Objective"
display_name_ar: "هدف مخصص"
category: "custom"
is_featured: false
is_default_selected: false
allows_combination: false  # Custom lens is exclusive
icon: "✨"
accent_color: "#B8904A"  # Bronze Gold

user_statement:
  en: "I have a specific goal"
  ar: "لدي هدف محدد"

short_description:
  en: "Define your own transformation objective"
  ar: "حدد هدف التحول الخاص بك"

detailed_description:
  en: |
    For goals not covered by the 15 predefined lenses. Describe your specific
    objective, and the system will interpret it to prioritize the relevant
    aspects of the diagnostic. Our AI will analyze your goal and configure
    the appropriate agent priorities, report structure, and recommendations.
  ar: |
    للأهداف غير المشمولة في العدسات الـ 15 المحددة مسبقاً. صف هدفك المحدد،
    وسيقوم النظام بتفسيره لإعطاء الأولوية للجوانب ذات الصلة من التشخيص.

focus_tags:
  - "User-Defined"
  - "Flexible"
  - "AI-Interpreted"
```

### User Input Requirements

```yaml
requires_user_input: true

user_input_config:
  prompt:
    en: "Describe your specific transformation goal:"
    ar: "صف هدف التحول المحدد الخاص بك:"
  
  input_type: "textarea"
  min_length: 50
  max_length: 1000
  
  placeholder:
    en: "Example: I want to become a certified supplier to multinational food companies in the Gulf region, which requires meeting specific food safety standards and building production capacity for larger orders..."
    ar: "مثال: أريد أن أصبح مورداً معتمداً لشركات الأغذية متعددة الجنسيات في منطقة الخليج..."
  
  guidance:
    en: |
      Be as specific as possible. Include:
      • What you want to achieve
      • Why this goal matters to your business
      • Any timeline constraints
      • Specific challenges you're facing
    ar: |
      كن محدداً قدر الإمكان. قم بتضمين:
      • ما تريد تحقيقه
      • لماذا هذا الهدف مهم لعملك
      • أي قيود زمنية
      • التحديات المحددة التي تواجهها
```

---

## AI Interpretation System

### How Custom Objectives Are Processed

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    CUSTOM OBJECTIVE INTERPRETATION FLOW                      │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   USER INPUT                                                                 │
│   └─► "I want to become a certified supplier to multinational food          │
│        companies in the Gulf region..."                                      │
│                                                                              │
│                              ↓                                               │
│                                                                              │
│   THE DRUCKER (Supervisor) INTERPRETS                                        │
│   ├─► Identifies key themes: supplier certification, food safety,           │
│   │   Gulf market, production capacity                                       │
│   ├─► Maps to relevant agents: Ricardo, Landor, Ohno, Marvin                │
│   ├─► Determines dimension priorities: Export, Packaging, Operations        │
│   └─► Generates custom lens configuration                                   │
│                                                                              │
│                              ↓                                               │
│                                                                              │
│   GENERATED LENS CONFIGURATION                                               │
│   ├─► Agent weights: Ricardo (1.5), Landor (1.4), Ohno (1.3), Marvin (1.2) │
│   ├─► Focus dimensions: certifications, packaging_compliance, quality       │
│   ├─► Report structure: certification_roadmap, capacity_assessment...       │
│   └─► Quick win filter: certification_quick_starts, quality_basics          │
│                                                                              │
│                              ↓                                               │
│                                                                              │
│   DIAGNOSTIC PROCEEDS                                                        │
│   └─► All agents execute with custom-interpreted priorities                  │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### Drucker Interpretation Prompt

```yaml
interpretation_agent: "drucker"

interpretation_prompt: |
  You are The Drucker, the supervisor agent for RootRise diagnostics.
  
  The user has selected a Custom Objective lens with the following goal:
  
  <user_goal>
  {user_custom_description}
  </user_goal>
  
  Based on this goal, determine:
  
  1. AGENT PRIORITIES
     For each of the 8 specialist agents, assign a weight multiplier (0.5-1.5):
     - drucker, marvin, graham (Core)
     - ricardo, lovelace, mayo, ohno, porter, landor (Add-On)
     
     Higher weight = more relevant to the user's goal
     
  2. FOCUS DIMENSIONS
     Which of the 11 sector knowledge dimensions are most relevant?
     1. Industry Classification
     2. Financial Benchmarks
     3. Operational KPIs
     4. Regulatory Landscape
     5. Competitive Dynamics
     6. Digital Maturity
     7. Workforce Norms
     8. Supply Chain
     9. Export Requirements
     10. Packaging & Labeling
     11. MENA Regional Context
     
  3. REPORT STRUCTURE
     What sections should lead the report for this goal?
     What content should be emphasized?
     What can be de-emphasized?
     
  4. QUICK WIN FOCUS (if The Crema is also selected)
     What types of quick wins are most relevant to this goal?
     
  5. AUTO-SELECT AGENTS
     Which Add-On agents should be automatically included based on this goal?
  
  Respond in structured JSON format.
```

### Interpretation Output Schema

```typescript
interface CustomLensInterpretation {
  // Metadata
  interpretation_id: string;
  original_description: string;
  interpreted_at: string;
  confidence_score: number;  // 0-1
  
  // Theme extraction
  identified_themes: string[];
  primary_objective: string;
  secondary_objectives: string[];
  
  // Agent configuration
  agent_weights: {
    drucker: number;
    marvin: number;
    graham: number;
    ricardo: number;
    lovelace: number;
    mayo: number;
    ohno: number;
    porter: number;
    landor: number;
  };
  
  auto_select_agents: string[];
  
  // Dimension priorities
  dimension_priorities: {
    dimension_id: number;
    dimension_name: string;
    priority: "high" | "medium" | "low";
    relevance_explanation: string;
  }[];
  
  // Report configuration
  report_structure: {
    lead_sections: string[];
    emphasized_sections: string[];
    de_emphasized_sections: string[];
  };
  
  // Quick win configuration (if Crema active)
  quick_win_focus: {
    priority_categories: string[];
    filter_adjustments: string[];
  };
  
  // Similar standard lenses
  similar_standard_lenses: {
    lens_id: string;
    similarity_score: number;
    overlap_areas: string[];
  }[];
  
  // Human review flag
  requires_human_review: boolean;
  review_reason?: string;
}
```

---

## Validation & Guardrails

### Input Validation

```typescript
interface CustomObjectiveValidation {
  // Length validation
  min_length: 50;
  max_length: 1000;
  
  // Content validation
  prohibited_content: [
    "illegal_activities",
    "harmful_intent",
    "off_topic"
  ];
  
  // Clarity validation
  requires_specificity: true;
  vague_input_handling: "request_clarification";
  
  // Validation messages
  messages: {
    too_short: "Please provide more detail about your transformation goal (minimum 50 characters).";
    too_long: "Please condense your goal description (maximum 1000 characters).";
    too_vague: "Your goal seems broad. Can you be more specific about what you want to achieve?";
    off_topic: "This goal doesn't appear to be related to business transformation. Please describe a business objective.";
  };
}
```

### Interpretation Confidence

```typescript
interface ConfidenceThresholds {
  // If confidence is low, suggest alternatives
  low_confidence_threshold: 0.6;
  low_confidence_action: "suggest_similar_standard_lenses";
  
  // If confidence is very low, require human review
  very_low_confidence_threshold: 0.4;
  very_low_confidence_action: "flag_for_human_review";
  
  // If confidence is high, proceed automatically
  high_confidence_threshold: 0.8;
  high_confidence_action: "proceed_with_interpretation";
}
```

---

## UI Behavior

### Custom Objective Selection Flow

```typescript
interface CustomObjectiveUIFlow {
  // Step 1: User selects Custom Objective
  on_select: {
    action: "show_input_modal";
    modal_title: "Define Your Custom Objective";
  };
  
  // Step 2: User enters description
  input_modal: {
    prompt: "Describe your specific transformation goal";
    guidance_visible: true;
    example_toggle: true;
    character_counter: true;
    submit_button: "Interpret My Goal";
  };
  
  // Step 3: AI interprets (with loading state)
  interpretation: {
    loading_message: "Analyzing your goal and configuring your diagnostic...";
    loading_duration_estimate: "5-10 seconds";
  };
  
  // Step 4: Show interpretation preview
  interpretation_preview: {
    show_identified_themes: true;
    show_agent_priorities: true;
    show_similar_lenses: true;
    allow_adjustments: true;
    confirm_button: "Proceed with This Configuration";
    cancel_button: "Try Different Description";
  };
  
  // Step 5: Proceed or revise
  on_confirm: "add_to_lens_configuration";
  on_cancel: "return_to_input_modal";
}
```

### Exclusivity Behavior

```typescript
interface CustomLensExclusivity {
  // Custom lens cannot be combined with standard lenses
  allows_combination_with_standard: false;
  
  // Exception: Can be combined with The Crema
  allows_combination_with_crema: true;
  
  // If user has standard lenses selected
  on_select_with_existing: {
    action: "show_warning";
    warning_message: "Custom Objective replaces your current lens selection. The Crema (if selected) will still apply. Continue?";
    confirm_action: "replace_standard_lenses";
    cancel_action: "keep_existing";
  };
}
```

---

## Integration with Architecture

### LangGraph State Extension

```typescript
interface DiagnosticState {
  // ... existing fields ...
  
  // Custom lens fields
  custom_lens_configuration?: {
    // User input
    user_description: string;
    
    // Interpretation
    interpretation: CustomLensInterpretation;
    
    // Computed configuration
    computed_agent_weights: Record<string, number>;
    computed_report_structure: ReportStructure;
    
    // Audit
    interpretation_timestamp: string;
    confidence_score: number;
  };
}
```

### API Endpoints

```yaml
# Interpret custom objective
POST /api/v1/lenses/interpret-custom
Request:
  description: string
  sector_id: string
  include_crema: boolean
Response:
  interpretation: CustomLensInterpretation
  confidence_score: number
  similar_lenses: SimilarLens[]
  proceed_recommended: boolean

# Adjust interpretation
POST /api/v1/lenses/adjust-custom-interpretation
Request:
  interpretation_id: string
  adjustments:
    agent_weight_overrides?: Record<string, number>
    additional_focus_areas?: string[]
    remove_focus_areas?: string[]
Response:
  adjusted_interpretation: CustomLensInterpretation

# Confirm custom lens
POST /api/v1/lenses/confirm-custom
Request:
  interpretation_id: string
Response:
  lens_configuration: LensConfiguration
  ready_for_diagnostic: boolean
```

---

## Examples

### Example 1: B2B Transition

**User Input:**
> "I want to transition from selling directly to consumers (B2C) to becoming a supplier for businesses (B2B). This means changing my packaging sizes, adjusting pricing for bulk orders, and building relationships with purchasing departments."

**Interpretation:**
```json
{
  "identified_themes": ["B2B transition", "packaging changes", "bulk pricing", "business development"],
  "primary_objective": "B2C to B2B business model transition",
  "agent_weights": {
    "porter": 1.5,
    "landor": 1.4,
    "graham": 1.3,
    "ohno": 1.2,
    "marvin": 1.1,
    "mayo": 1.0,
    "lovelace": 0.9,
    "ricardo": 0.8
  },
  "auto_select_agents": ["porter", "landor"],
  "similar_standard_lenses": [
    { "lens_id": "eye_005", "name": "Market Expansion", "similarity": 0.7 }
  ]
}
```

### Example 2: Recovery Scenario

**User Input:**
> "We lost our biggest customer (40% of revenue) last month. I need to stabilize cash flow, find replacement customers quickly, and diversify our customer base so this never happens again."

**Interpretation:**
```json
{
  "identified_themes": ["customer loss recovery", "cash flow crisis", "customer diversification", "risk mitigation"],
  "primary_objective": "Recovery from major customer loss",
  "agent_weights": {
    "graham": 1.5,
    "porter": 1.4,
    "marvin": 1.2,
    "ohno": 1.1,
    "mayo": 1.0,
    "lovelace": 0.9,
    "ricardo": 0.8,
    "landor": 0.8
  },
  "auto_select_agents": ["porter"],
  "dimension_priorities": [
    { "dimension_id": 2, "dimension_name": "Financial Benchmarks", "priority": "high" },
    { "dimension_id": 5, "dimension_name": "Competitive Dynamics", "priority": "high" }
  ]
}
```

---

## Document Metadata

```yaml
document_type: "Lens Specification"
lens_id: "eye_custom"
version: "2.0"
last_updated: "2026-01-05"
status: "Production Ready"
author: "Tee (CTO)"
for: "Ahmed El-Gazzar (Technical DevOps Lead)"

companion_documents:
  - "RootRise_Eye_Lens_Framework_v2.md"
  - "RootRise_Infrastructure_Blueprint_v1.1.md"
  - "EYE-000_The_Crema.md"
```

---

*Custom Objective — Because your business, your goals, your transformation.*
