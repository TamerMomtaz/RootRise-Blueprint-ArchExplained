# EYE-CREMA: The Crema — Quick Wins Lens

## Lens Overview

```
╔═══════════════════════════════════════════════════════════════════════════════╗
║                                                                               ║
║                    THE &EYE — THE CREMA (FEATURED LENS)                       ║
║                                                                               ║
║                          "Quick Wins in 30-60-90 Days"                        ║
║                                                                               ║
╠═══════════════════════════════════════════════════════════════════════════════╣
║                                                                               ║
║   LENS ID:        EYE-CREMA                                                   ║
║   LENS NAME:      The Crema                                                   ║
║   CATEGORY:       Featured (Pre-selected by default)                          ║
║   PRIMARY FOCUS:  Extract highest-value, lowest-effort quick wins             ║
║                                                                               ║
║   CORE QUESTION:  What can I fix RIGHT NOW — in 30, 60, or 90 days —         ║
║                   with minimal effort and maximum visible impact?             ║
║                                                                               ║
║   KEY INSIGHT:    The "cream of the crop" rises to the top. Before diving    ║
║                   into deep transformation, capture the quick wins that       ║
║                   build momentum, demonstrate value, and fund bigger changes. ║
║                                                                               ║
║   DIFFERENTIATOR: While other diagnostic tools deliver overwhelming reports,  ║
║                   The Crema gives you a prioritized action list you can       ║
║                   start executing TODAY.                                      ║
║                                                                               ║
╚═══════════════════════════════════════════════════════════════════════════════╝
```

---

## Lens Philosophy

### Why The Crema Exists

Most SME diagnostic tools deliver comprehensive reports that overwhelm business owners. They identify 50 problems, 30 opportunities, and 100 recommendations — leaving the SME paralyzed by choice. Where do you start? What matters most? What can you actually do with limited resources?

**The Crema solves this.** Named after the rich, golden foam that rises to the top of a perfectly pulled espresso, The Crema extracts only the highest-value, lowest-effort improvements from your diagnostic. These are the actions that:

- Can be implemented in 30, 60, or 90 days
- Require low to medium effort
- Deliver high or very high impact
- Create visible results for stakeholders
- Build momentum for deeper transformation
- Often self-fund larger initiatives through savings or revenue gains

### The Momentum Principle

Transformation fails when it starts too big. The Crema embodies the momentum principle:

```
SMALL WINS → STAKEHOLDER CONFIDENCE → RESOURCES FOR BIGGER WINS → TRANSFORMATION

Day 1-30:   Fix obvious inefficiencies, plug cash leaks, quick process fixes
Day 31-60:  Implement systems improvements, early automation, cost reductions  
Day 61-90:  Launch growth initiatives, strategic improvements, visible changes
```

### When The Crema is Most Valuable

The Crema lens is especially powerful when:

- **Building stakeholder confidence** — Show investors, boards, or partners that you can execute
- **Limited resources** — Focus energy on what matters most right now
- **Paralysis by analysis** — Cut through complexity to clear next steps
- **Demonstrating early value** — Prove ROI before committing to larger programs
- **Funding transformation** — Quick wins often generate the cash for bigger changes
- **Team motivation** — Nothing builds momentum like visible wins

---

## Technical Specification

### Lens Configuration

```yaml
lens_id: "eye_crema"
display_name: "The Crema"
display_name_ar: "الكريما"
category: "featured"
icon: "☕"
accent_color: "#F5C563"  # Gold

# User-facing content
user_statement: "I want quick wins NOW"
user_statement_ar: "أريد مكاسب سريعة الآن"

short_description: "Quick Wins Focus — 30-60-90 Day Actions"
detailed_description: |
  The Crema extracts the highest-value, lowest-effort improvements from your 
  diagnostic. These are the "cream of the crop" — actions that can be implemented 
  quickly and show visible results to stakeholders. Ideal for building momentum 
  before deeper transformation, or for demonstrating early value to funders/investors.

focus_tags:
  - "30-60-90 Days"
  - "Low Effort"
  - "High Impact"
  - "Visible Results"
  - "Momentum Building"

# Behavior configuration
is_featured: true
is_default_selected: true     # Pre-selected for all diagnostics
can_be_deselected: true       # User can turn it off if desired
spans_full_width: true        # UI: Spans full width at top of lens selection
allows_combination: true      # Can be combined with other lenses
```

### Quick Win Criteria

The Crema filters all diagnostic findings through strict criteria:

```typescript
interface QuickWinCriteria {
  // Time constraints
  timeline: {
    max_days: 90;
    buckets: [30, 60, 90];  // Categorize into 30/60/90 day actions
  };
  
  // Effort constraints
  effort: {
    allowed_levels: ["low", "medium"];  // Exclude high-effort items
    exclude: ["high", "very_high"];
  };
  
  // Impact requirements
  impact: {
    required_levels: ["high", "very_high"];  // Only high-impact items
    exclude: ["low", "medium"];
  };
  
  // Additional filters
  additional: {
    requires_external_resources: false;     // Prefer internal execution
    requires_major_investment: false;       // Prefer low-cost actions
    requires_organizational_change: false;  // Prefer tactical over strategic
  };
}
```

### Agent Priority Adjustments

The Crema reprioritizes agents toward those most likely to identify quick wins:

```yaml
agent_priority_adjustments:
  # Primary agents for quick wins
  - agent_id: "ohno"
    weight_multiplier: 1.5
    reason: "Waste reduction and lean improvements yield fastest wins"
    focus_dimensions:
      - "waste_identification"
      - "process_quick_fixes"
      - "efficiency_low_hanging_fruit"
      - "cost_reduction_immediate"
  
  - agent_id: "graham"
    weight_multiplier: 1.4
    reason: "Cash flow improvements and cost savings are immediately visible"
    focus_dimensions:
      - "cash_flow_quick_fixes"
      - "cost_leaks"
      - "pricing_adjustments"
      - "working_capital_improvements"
  
  - agent_id: "marvin"
    weight_multiplier: 1.3
    reason: "Operational quick fixes span all dimensions"
    focus_dimensions:
      - "process_improvements"
      - "quality_quick_wins"
      - "bottleneck_removal"
      - "documentation_gaps"
  
  # Supporting agents
  - agent_id: "lovelace"
    weight_multiplier: 1.2
    reason: "Automation and digital quick wins can have immediate impact"
    focus_dimensions:
      - "automation_opportunities"
      - "tool_adoption"
      - "digital_quick_fixes"
  
  - agent_id: "mayo"
    weight_multiplier: 1.1
    reason: "HR quick wins like training and process documentation"
    focus_dimensions:
      - "training_gaps"
      - "role_clarity"
      - "communication_improvements"
  
  # Lower priority for quick wins (these are typically strategic)
  - agent_id: "porter"
    weight_multiplier: 0.8
    reason: "Strategic positioning takes time to implement"
  
  - agent_id: "ricardo"
    weight_multiplier: 0.8
    reason: "Export readiness is typically a longer journey"
  
  - agent_id: "landor"
    weight_multiplier: 0.9
    reason: "Packaging changes can be quick if scope is limited"

# No auto-select for The Crema (it's featured, works with existing selection)
auto_select_agents: []
```

### Report Configuration

```yaml
report_section_order:
  - "crema_executive_summary"      # The 5 most impactful quick wins
  - "30_day_action_plan"           # Immediate actions
  - "60_day_action_plan"           # Near-term actions  
  - "90_day_action_plan"           # Quarter-end actions
  - "momentum_metrics"             # How to measure early wins
  - "stakeholder_communication"    # How to report progress
  - "resource_requirements"        # What you need to execute
  - "risk_mitigation"              # What could go wrong
  - "transition_to_deep_dive"      # When you're ready for more

content_prioritization:
  lead_with:
    - "quick_wins_summary"
    - "immediate_actions"
    - "visible_impact_items"
  
  emphasize:
    - "cost_savings_opportunities"
    - "efficiency_improvements"
    - "cash_flow_enhancements"
    - "stakeholder_visible_wins"
  
  de_emphasize:
    - "long_term_strategy"
    - "complex_implementations"
    - "multi_year_roadmaps"
    - "major_investments"
    - "organizational_restructuring"
  
  appendix_candidates:
    - "detailed_assessments"
    - "methodology_notes"
    - "full_diagnostic_findings"

formatting_rules:
  quick_wins_prominent: true
  include_timeline_visual: true
  show_effort_impact_matrix: true
  score_card_style: "action_focused"
  max_items_per_timeframe: 5        # Top 5 per 30/60/90 bucket
```

---

## Output Structure

### The Crema Report Format

When The Crema lens is active, the report leads with a distinctive structure:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        THE CREMA — YOUR QUICK WINS                          │
│                     [Company Name] | [Date] | [Sector]                      │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  YOUR TOP 5 QUICK WINS                                                      │
│  ════════════════════                                                       │
│                                                                             │
│  1. [Title] ─────────────────────────────────────────────────               │
│     Impact: ████████░░ HIGH    Effort: ██░░░░░░░░ LOW                       │
│     Timeline: 30 days          Est. Savings: $XX,XXX                        │
│     → [One-sentence action description]                                     │
│                                                                             │
│  2. [Title] ─────────────────────────────────────────────────               │
│     Impact: ████████░░ HIGH    Effort: ████░░░░░░ MEDIUM                    │
│     Timeline: 45 days          Est. Savings: $XX,XXX                        │
│     → [One-sentence action description]                                     │
│                                                                             │
│  ... (3 more)                                                               │
│                                                                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  30-DAY ACTION PLAN                                                         │
│  ══════════════════                                                         │
│  □ Action 1: [Description] — Owner: [Role] — Target: [Date]                 │
│  □ Action 2: [Description] — Owner: [Role] — Target: [Date]                 │
│  □ Action 3: [Description] — Owner: [Role] — Target: [Date]                 │
│                                                                             │
│  60-DAY ACTION PLAN                                                         │
│  ══════════════════                                                         │
│  □ Action 1: [Description] — Owner: [Role] — Target: [Date]                 │
│  □ Action 2: [Description] — Owner: [Role] — Target: [Date]                 │
│                                                                             │
│  90-DAY ACTION PLAN                                                         │
│  ══════════════════                                                         │
│  □ Action 1: [Description] — Owner: [Role] — Target: [Date]                 │
│  □ Action 2: [Description] — Owner: [Role] — Target: [Date]                 │
│                                                                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  MOMENTUM METRICS — How to Track Your Progress                              │
│  ═════════════════════════════════════════════                              │
│  • [Metric 1]: Current [X] → Target [Y] by Day 30                           │
│  • [Metric 2]: Current [X] → Target [Y] by Day 60                           │
│  • [Metric 3]: Current [X] → Target [Y] by Day 90                           │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### Quick Win Item Schema

```typescript
interface QuickWinItem {
  // Identity
  id: string;
  title: string;
  title_ar: string;
  
  // Classification
  category: "cost_reduction" | "revenue_enhancement" | "efficiency" | 
            "quality" | "compliance" | "customer" | "workforce";
  source_agent: string;           // Which agent identified this
  source_finding_id: string;      // Link to underlying finding
  
  // Prioritization scores
  impact_score: number;           // 1-10
  impact_level: "high" | "very_high";
  effort_score: number;           // 1-10
  effort_level: "low" | "medium";
  
  // Timeline
  timeline_days: number;          // 1-90
  timeline_bucket: 30 | 60 | 90;
  
  // Action details
  action_description: string;
  action_description_ar: string;
  action_steps: string[];
  owner_role: string;             // Suggested responsible role
  
  // Expected outcomes
  expected_outcome: string;
  quantified_benefit?: {
    type: "cost_savings" | "revenue_increase" | "time_savings" | "risk_reduction";
    amount: number;
    currency: string;
    confidence: number;           // 0-1
  };
  
  // Dependencies
  dependencies: string[];         // Other quick wins or prerequisites
  risks: string[];                // What could prevent success
  
  // Tracking
  success_metrics: {
    metric: string;
    current_value: string;
    target_value: string;
    measurement_method: string;
  }[];
}
```

---

## Integration with Other Lenses

### The Crema as a Filter

When The Crema is combined with other lenses (e.g., Export Readiness), it acts as a **filter** on those lenses:

```
User selects: The Crema + Export Readiness

Result: 
  → Export Readiness findings are evaluated
  → Only findings meeting Quick Win Criteria are highlighted
  → Report leads with "Export Quick Wins" (30-60-90 day export improvements)
  → Full export roadmap moves to appendix
```

### Combination Behavior

```typescript
interface CremaCombinationBehavior {
  // When combined with other lenses
  combination_mode: "filter";    // The Crema filters other lens findings
  
  // Priority
  takes_report_lead: true;       // Crema section always appears first
  
  // Content handling
  other_lens_content: {
    quick_win_items: "promote_to_crema_section";
    non_quick_win_items: "include_in_appendix";
    long_term_roadmap: "include_in_appendix";
  };
  
  // Special messaging
  combination_message: |
    "Your {other_lens} diagnostic has been filtered through The Crema to 
    highlight quick wins. Full {other_lens} analysis is available in the 
    detailed report section.";
}
```

---

## UI Behavior

### Lens Selection Screen

```yaml
ui_specification:
  position: "top"                 # Appears at top of lens selection
  width: "full"                   # Spans full width (not in grid)
  
  visual_treatment:
    background: "gradient_gold"   # Stand out from other lenses
    border: "2px solid var(--bronze-gold)"
    badge: "FEATURED"
    icon_size: "large"
  
  default_state:
    selected: true                # Pre-checked
    expanded: false               # Description collapsed by default
  
  interaction:
    click_to_deselect: true       # Clicking toggles off
    show_impact_preview: true     # "Filters all findings to quick wins"
```

### The Crema Toggle

```typescript
// Ensure toggle works correctly (addresses known bug from old framework)
function handleCremaToggle(currentState: LensSelectionState): LensSelectionState {
  const isCurrentlySelected = currentState.selected_lenses.includes('eye_crema');
  
  if (isCurrentlySelected) {
    // DESELECT: Remove The Crema
    return {
      ...currentState,
      selected_lenses: currentState.selected_lenses.filter(l => l !== 'eye_crema'),
      crema_active: false
    };
  } else {
    // SELECT: Add The Crema
    return {
      ...currentState,
      selected_lenses: ['eye_crema', ...currentState.selected_lenses],
      crema_active: true
    };
  }
}
```

---

## MENA Regional Context

### Quick Win Categories by Region

Different MENA markets have different "typical" quick wins:

```yaml
regional_quick_win_patterns:
  egypt:
    common_quick_wins:
      - "Working capital optimization (high DSO typical)"
      - "Energy cost reduction (subsidized but often wasted)"
      - "Documentation and process formalization"
      - "Digital payment adoption (reducing cash handling)"
    typical_timeline: "30-90 days achievable with focused effort"
  
  saudi_arabia:
    common_quick_wins:
      - "Saudization compliance improvements"
      - "VAT optimization (often overpaying)"
      - "Labor productivity improvements"
      - "Government program enrollment (support available)"
    typical_timeline: "Government programs may extend to 120 days"
  
  uae:
    common_quick_wins:
      - "Free zone benefit optimization"
      - "Multi-channel digital presence"
      - "Supply chain consolidation"
      - "Service standardization"
    typical_timeline: "60-90 days typical for implementation"
  
  jordan:
    common_quick_wins:
      - "Export documentation preparation"
      - "Quality certification quick-track"
      - "Cost structure optimization"
      - "Regional market positioning"
    typical_timeline: "45-90 days with focused execution"
  
  lebanon:
    common_quick_wins:
      - "Currency management improvements"
      - "Cash flow optimization (critical)"
      - "Supply chain resilience"
      - "Digital/remote capability building"
    typical_timeline: "30-60 days due to urgency"
  
  morocco:
    common_quick_wins:
      - "Africa market positioning"
      - "French market compliance"
      - "Quality system implementation"
      - "Digital transformation basics"
    typical_timeline: "60-90 days achievable"
```

---

## Success Metrics

### How to Measure The Crema's Value

```yaml
crema_success_metrics:
  execution_rate:
    definition: "Percentage of recommended quick wins actually implemented"
    target: ">70%"
    measurement: "Follow-up survey at 90 days"
  
  time_to_first_win:
    definition: "Days from diagnostic to first completed quick win"
    target: "<30 days"
    measurement: "SME self-report or advisor confirmation"
  
  quantified_impact:
    definition: "Measured financial impact of implemented quick wins"
    target: ">$10,000 or >5% cost reduction"
    measurement: "SME financial reporting"
  
  momentum_continuation:
    definition: "SMEs who proceed to deeper transformation after quick wins"
    target: ">50%"
    measurement: "Conversion to full diagnostic or program enrollment"
  
  stakeholder_satisfaction:
    definition: "SME rating of actionability of recommendations"
    target: ">4.5/5"
    measurement: "Post-diagnostic survey"
```

---

## Document Metadata

```yaml
document_type: "Lens Specification"
lens_id: "eye_crema"
version: "2.0"
created: "2025-12-11"
updated: "2026-01-05"
status: "Production Ready"
author: "Tee (CTO)"

related_documents:
  - "RootRise_Eye_Lens_Framework_v2.md"
  - "RootRise_Infrastructure_Blueprint_v1.1.md"
  - "RootRise_Core_Agent_Prompts.md"
  - "RootRise_Utility_Agent_Prompts.md"

changelog:
  - version: "2.0"
    date: "2026-01-05"
    changes:
      - "Restored from original framework after accidental removal"
      - "Enhanced with MENA regional quick win patterns"
      - "Added combination behavior with other lenses"
      - "Fixed UI toggle bug specification"
      - "Added success metrics framework"
  - version: "1.0"
    date: "2025-12-11"
    changes:
      - "Initial creation as part of Lens Framework"
```

---

*The Crema — Because transformation starts with momentum, and momentum starts with quick wins.*
