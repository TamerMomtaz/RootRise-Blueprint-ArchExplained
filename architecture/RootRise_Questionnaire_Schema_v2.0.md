# RootRise Diagnostic Questionnaire Schema

**Version:** 2.0  
**Date:** January 2026  
**Author:** Tee (The Ionganic Orchestrator - TIO)  
**For:** Ahmed El-Gazzar (Technical DevOps Lead)  
**Status:** Production Ready

---

# Table of Contents

1. [Schema Overview](#1-schema-overview)
2. [Master Data Model](#2-master-data-model)
3. [Pre-Questionnaire: Lens Selection (LS)](#3-pre-questionnaire-lens-selection)
4. [Section 1: Business Profile (BP)](#4-section-1-business-profile)
5. [Section 2: Financial Health (FH)](#5-section-2-financial-health)
6. [Section 3: Operations & Production (OP)](#6-section-3-operations--production)
7. [Section 4: Digital Maturity (DM)](#7-section-4-digital-maturity)
8. [Section 5: Workforce & HR (WF)](#8-section-5-workforce--hr)
9. [Section 6: Market & Competition (MK)](#9-section-6-market--competition)
10. [Section 7: Supply Chain (SC)](#10-section-7-supply-chain)
11. [Section 8: Export Readiness (EX)](#11-section-8-export-readiness)
12. [Section 9: Brand & Marketing (BR)](#12-section-9-brand--marketing)
13. [Section 10: Compliance & Certifications (CC)](#13-section-10-compliance--certifications)
14. [Section 11: Quick Win Assessment (QW)](#14-section-11-quick-win-assessment)
15. [Conditional Logic Rules](#15-conditional-logic-rules)
16. [Lens-Based Routing](#16-lens-based-routing)
17. [Validation Rules](#17-validation-rules)
18. [Agent Data Mapping](#18-agent-data-mapping)
19. [Implementation Guide](#19-implementation-guide)

---

# 1. Schema Overview

## 1.1 Purpose

This questionnaire schema defines the complete set of questions presented to SME owners during the RootRise diagnostic process. The schema maps every question to specific diagnostic agents and transformation lenses, ensuring data flows correctly through The Pantheon multi-agent system and supports The &Eye lens prioritization.

## 1.2 What's New in v2.0

| Feature | v1.0 | v2.0 |
|---------|------|------|
| **Lens Integration** | Not included | Full 17-lens support |
| **Pre-Questionnaire** | None | Lens selection flow (LS section) |
| **Quick Win Section** | Not included | Dedicated QW section for The Crema |
| **Countries** | 7 (incl. Tunisia) | 6 (EG, SA, AE, JO, LB, MA) |
| **Total Questions** | ~145 | ~160 |
| **Lens Relevance** | Not tracked | Per-question lens mapping |
| **Quick Win Indicators** | Not tracked | Per-question effort/impact markers |

## 1.3 Design Principles

| Principle | Description |
|-----------|-------------|
| **Conversational** | Questions feel like a consultation, not a form |
| **Progressive** | Core questions first, detailed questions unlock based on responses |
| **Lens-Driven** | Questions adapt based on selected transformation lenses |
| **Agent-Aligned** | Every question maps to specific agent data requirements |
| **&I Philosophy** | Human context injection points throughout |
| **MENA-Ready** | Arabic translations, regional context options |
| **Time-Respectful** | 20-30 minutes total, with save/resume capability |
| **Quick-Win Enabled** | Captures data needed for Crema filtering |

## 1.4 Question Types

```typescript
type QuestionType = 
  | 'single_choice'      // Radio buttons - one selection
  | 'multiple_choice'    // Checkboxes - multiple selections
  | 'scale'              // 1-5 or 1-10 rating
  | 'numeric'            // Number input with optional range
  | 'currency'           // Number input formatted as currency
  | 'percentage'         // Number input 0-100
  | 'text_short'         // Single line text
  | 'text_long'          // Multi-line text
  | 'date'               // Date picker
  | 'date_range'         // Start/end date
  | 'file_upload'        // Document upload
  | 'matrix'             // Grid of related questions
  | 'ranking'            // Drag-to-rank items
  | 'slider'             // Visual slider with labels
  | 'yes_no'             // Boolean with optional "Not Sure"
  | 'country_select'     // Country dropdown (6 MENA countries)
  | 'sector_select'      // Sector/subsector cascading (31 sectors)
  | 'lens_select'        // Lens selection (17 lenses)
  | 'human_context';     // Open field for user expertise injection
```

## 1.5 Estimated Completion Times

| Section | Code | Questions | Est. Time | Condition |
|---------|------|-----------|-----------|-----------|
| Lens Selection | LS | 4 | 1 min | Always (Pre-questionnaire) |
| Business Profile | BP | 15 | 3 min | Always (Core) |
| Financial Health | FH | 20 | 5 min | Always (Core) |
| Operations | OP | 18 | 4 min | Always (Core) |
| Digital Maturity | DM | 13 | 3 min | If lens/agent requires |
| Workforce | WF | 11 | 3 min | If lens/agent requires |
| Market | MK | 10 | 2 min | If lens/agent requires |
| Supply Chain | SC | 12 | 3 min | If lens/agent requires |
| Export | EX | 15 | 4 min | If lens/agent requires |
| Brand | BR | 10 | 2 min | If lens/agent requires |
| Compliance | CC | 8 | 2 min | Contextual |
| Quick Win Assessment | QW | 10 | 2 min | If Crema active |
| **TOTAL (Core)** | - | **~57** | **~13 min** | - |
| **TOTAL (Full)** | - | **~160** | **~34 min** | - |

## 1.6 The Three-Layer Integration

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    QUESTIONNAIRE ↔ THREE LAYERS                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  PRE-QUESTIONNAIRE: LENS SELECTION (The &Eye)                               │
│  ├─ User selects transformation goal(s) from The &Eye (17 lenses)           │
│  ├─ The Crema (EYE-CREMA) recommended by default                            │
│  ├─ Lens selection determines which sections are shown                      │
│  └─ Lens selection auto-includes relevant agents                            │
│                                                                              │
│  QUESTIONNAIRE: DATA COLLECTION                                             │
│  ├─ Core sections always shown (BP, FH, OP)                                 │
│  ├─ Add-on sections shown based on lens selection                           │
│  ├─ Questions tagged with lens_relevance for prioritization                 │
│  └─ Quick Win section (QW) shown if Crema is active                         │
│                                                                              │
│  POST-QUESTIONNAIRE: AGENT ROUTING (The Pantheon)                           │
│  ├─ Data routed to selected agents in The Pantheon (11 agents)              │
│  ├─ Sector context loaded from My Sector (31 sectors)                       │
│  └─ Lens priorities applied to agent outputs                                │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```


---

# 2. Master Data Model

## 2.1 Question Schema

```typescript
interface Question {
  // Identity
  id: string;                           // Unique ID: "LS_001", "BP_001", "QW_003"
  section: SectionCode;                 // Section code
  subsection?: string;                  // Optional grouping within section
  order: number;                        // Display order within section
  
  // Content (Bilingual)
  text: {
    en: string;                         // English question text
    ar: string;                         // Arabic question text
  };
  description?: {
    en: string;                         // Helper text / clarification
    ar: string;
  };
  placeholder?: {
    en: string;                         // Input placeholder
    ar: string;
  };
  
  // Type & Options
  type: QuestionType;
  options?: QuestionOption[];           // For choice-based questions
  scale_config?: ScaleConfig;           // For scale/slider questions
  numeric_config?: NumericConfig;       // For numeric questions
  matrix_config?: MatrixConfig;         // For matrix questions
  
  // Behavior
  required: boolean;
  conditional?: ConditionalRule[];      // Show/hide based on other answers
  validation?: ValidationRule[];        // Input validation rules
  
  // Agent Mapping
  agents: AgentCode[];                  // Which agents consume this data
  data_field: string;                   // Field name in agent input schema
  dimension?: number;                   // Sector Knowledge dimension (1-11)
  
  // NEW in v2.0: Lens Integration
  lens_relevance: LensRelevance[];      // Which lenses prioritize this question
  quick_win_indicator?: boolean;        // Does this help identify quick wins?
  effort_indicator?: boolean;           // Does this indicate implementation effort?
  
  // &I Philosophy
  allows_human_context: boolean;        // Can user add explanatory note
  human_context_prompt?: {
    en: string;
    ar: string;
  };
  confidence_impact: 'high' | 'medium' | 'low';
}

interface LensRelevance {
  lens_id: string;                      // e.g., "EYE-001", "EYE-CREMA"
  relevance: 'primary' | 'secondary' | 'context';
  weight_multiplier?: number;           // How much to weight in lens scoring
}

interface QuestionOption {
  value: string;                        // Stored value
  label: {
    en: string;
    ar: string;
  };
  score?: number;                       // Optional numeric value for calculations
  effort_level?: 'low' | 'medium' | 'high';  // NEW: For Crema scoring
  triggers_followup?: string[];         // Question IDs to show if selected
}

interface ScaleConfig {
  min: number;
  max: number;
  step: number;
  labels: {
    min: { en: string; ar: string };
    max: { en: string; ar: string };
    mid?: { en: string; ar: string };
  };
}

interface NumericConfig {
  min?: number;
  max?: number;
  unit?: string;
  currency?: string;                    // ISO 4217 code
  format?: 'integer' | 'decimal' | 'percentage';
}

type SectionCode = 'LS' | 'BP' | 'FH' | 'OP' | 'DM' | 'WF' | 'MK' | 'SC' | 'EX' | 'BR' | 'CC' | 'QW';

type AgentCode = 'DRUCKER' | 'MARVIN' | 'GRAHAM' | 'LOVELACE' | 'MAYO' 
  | 'PORTER' | 'OHNO' | 'RICARDO' | 'LANDOR' | 'DEMING' | 'TUFTE';

type LensCode = 'EYE-CREMA' | 'EYE-001' | 'EYE-002' | 'EYE-003' | 'EYE-004' 
  | 'EYE-005' | 'EYE-006' | 'EYE-007' | 'EYE-008' | 'EYE-009' | 'EYE-010' 
  | 'EYE-011' | 'EYE-012' | 'EYE-013' | 'EYE-014' | 'EYE-015' | 'EYE-CUSTOM';
```

## 2.2 Response Schema

```typescript
interface QuestionnaireResponse {
  session_id: string;
  sme_id: string;
  started_at: string;                   // ISO 8601
  completed_at?: string;
  current_section: SectionCode;
  progress_percentage: number;
  language: 'en' | 'ar';
  
  // NEW in v2.0: Lens Configuration
  lens_configuration: {
    selected_lenses: LensCode[];        // User's selected lenses
    crema_active: boolean;              // Is The Crema filtering enabled?
    custom_objective?: string;          // If EYE-CUSTOM selected
  };
  
  responses: {
    [question_id: string]: ResponseValue;
  };
  
  human_context_notes: {
    [question_id: string]: string;      // User's explanatory notes
  };
  
  metadata: {
    completion_time_seconds: number;
    sections_completed: SectionCode[];
    skipped_optional: string[];         // Question IDs skipped
    auto_selected_agents: AgentCode[];  // Agents auto-selected by lenses
  };
}

type ResponseValue = 
  | string 
  | number 
  | boolean 
  | string[]                            // Multiple choice
  | { [key: string]: string | number }  // Matrix
  | { start: string; end: string };     // Date range
```

---

# 3. Pre-Questionnaire: Lens Selection

**Section Code:** `LS`  
**Purpose:** Capture user's transformation goal before questionnaire begins  
**Estimated Time:** 1 minute  
**Condition:** Always shown first (before main questionnaire)

## 3.1 Lens Selection Flow

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         LENS SELECTION FLOW                                  │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  STEP 1: Welcome & Context                                                  │
│  "What transformation are you working toward?"                              │
│                                                                              │
│  STEP 2: Featured Lens (Recommended)                                        │
│  ☕ The Crema - Quick Wins (30-60-90 days)                                  │
│  [✓ Recommended] "Show me what I can achieve quickly"                      │
│                                                                              │
│  STEP 3: Primary Goal Selection                                             │
│  "Select your main transformation goal:"                                    │
│  ○ 🌍 I want to sell internationally (Export Readiness)                    │
│  ○ 💰 I want to attract investment (Investment Readiness)                  │
│  ○ 💻 I want to modernize with technology (Digital Transformation)         │
│  ○ ⚙️ I want to improve operations (Operational Excellence)                │
│  ○ 📈 I want to grow my market (Market Expansion)                          │
│  ... (all 15 standard lenses)                                               │
│  ○ ✨ I have a different goal (Custom Objective)                           │
│                                                                              │
│  STEP 4: Secondary Goals (Optional)                                         │
│  "Any additional focus areas?" (max 2 more)                                 │
│                                                                              │
│  STEP 5: Custom Objective Input (if selected)                               │
│  "Describe your specific goal in your own words..."                         │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 3.2 Questions

```yaml
LS_001:
  text:
    en: "What transformation are you working toward?"
    ar: "ما هو التحول الذي تسعى إليه؟"
  description:
    en: "Select the goal that best matches your current priority. This helps us focus the diagnostic on what matters most to you."
    ar: "اختر الهدف الذي يتوافق مع أولويتك الحالية. هذا يساعدنا على تركيز التشخيص على ما يهمك أكثر."
  type: single_choice
  required: true
  options:
    # Growth Category
    - value: "EYE-001"
      label: 
        en: "🌍 I want to sell internationally (Export Readiness)"
        ar: "🌍 أريد البيع دولياً (جاهزية التصدير)"
    - value: "EYE-002"
      label: 
        en: "💰 I want to attract investment (Investment Readiness)"
        ar: "💰 أريد جذب الاستثمار (جاهزية الاستثمار)"
    - value: "EYE-005"
      label: 
        en: "📈 I want to grow my market presence (Market Expansion)"
        ar: "📈 أريد زيادة حضوري في السوق (التوسع في السوق)"
    - value: "EYE-006"
      label: 
        en: "🎨 I want to strengthen my brand (Brand Building)"
        ar: "🎨 أريد تعزيز علامتي التجارية (بناء العلامة التجارية)"
    # Operations Category
    - value: "EYE-003"
      label: 
        en: "💻 I want to modernize with technology (Digital Transformation)"
        ar: "💻 أريد التحديث بالتكنولوجيا (التحول الرقمي)"
    - value: "EYE-004"
      label: 
        en: "⚙️ I want to improve operational efficiency (Operational Excellence)"
        ar: "⚙️ أريد تحسين الكفاءة التشغيلية (التميز التشغيلي)"
    - value: "EYE-012"
      label: 
        en: "📊 I want to reduce costs (Cost Optimization)"
        ar: "📊 أريد تقليل التكاليف (تحسين التكاليف)"
    # Impact Category
    - value: "EYE-007"
      label: 
        en: "👥 I want to develop my workforce (Workforce Development)"
        ar: "👥 أريد تطوير قوتي العاملة (تطوير القوى العاملة)"
    - value: "EYE-008"
      label: 
        en: "🔗 I want to optimize my supply chain (Supply Chain Optimization)"
        ar: "🔗 أريد تحسين سلسلة التوريد (تحسين سلسلة التوريد)"
    - value: "EYE-009"
      label: 
        en: "🌱 I want to improve sustainability (Sustainability & ESG)"
        ar: "🌱 أريد تحسين الاستدامة (الاستدامة والحوكمة)"
    - value: "EYE-010"
      label: 
        en: "💡 I want to innovate products/services (Innovation & R&D)"
        ar: "💡 أريد الابتكار في المنتجات/الخدمات (الابتكار والبحث)"
    - value: "EYE-011"
      label: 
        en: "⭐ I want to improve customer experience (Customer Experience)"
        ar: "⭐ أريد تحسين تجربة العميل (تجربة العميل)"
    - value: "EYE-013"
      label: 
        en: "🛡️ I want to manage risks better (Risk & Resilience)"
        ar: "🛡️ أريد إدارة المخاطر بشكل أفضل (المخاطر والمرونة)"
    # Transition Category
    - value: "EYE-014"
      label: 
        en: "👤 I'm planning leadership transition (Succession & Governance)"
        ar: "👤 أخطط لانتقال القيادة (الخلافة والحوكمة)"
    - value: "EYE-015"
      label: 
        en: "🤝 I'm exploring partnerships or M&A (Partnership & M&A)"
        ar: "🤝 أستكشف الشراكات أو الاستحواذ (الشراكات والاستحواذ)"
    # Custom
    - value: "EYE-CUSTOM"
      label: 
        en: "✨ I have a different specific goal (Custom Objective)"
        ar: "✨ لدي هدف محدد مختلف (هدف مخصص)"
      triggers_followup: [LS_004]
  agents: [DRUCKER]
  data_field: primary_lens
  confidence_impact: high
  lens_relevance: []  # Meta-question, affects all lenses

LS_002:
  text:
    en: "Would you like quick wins highlighted?"
    ar: "هل تريد تسليط الضوء على المكاسب السريعة؟"
  description:
    en: "The Crema ☕ identifies what you can achieve in 30-60-90 days with minimal effort. Recommended for all users."
    ar: "الكريما ☕ تحدد ما يمكنك تحقيقه في 30-60-90 يوماً بأقل جهد. موصى به لجميع المستخدمين."
  type: single_choice
  required: true
  options:
    - value: "yes"
      label: 
        en: "☕ Yes, show me quick wins (recommended)"
        ar: "☕ نعم، أظهر لي المكاسب السريعة (موصى به)"
      score: 1
    - value: "no"
      label: 
        en: "No, focus only on comprehensive transformation"
        ar: "لا، ركز فقط على التحول الشامل"
      score: 0
  agents: [DRUCKER]
  data_field: crema_active
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-CREMA", relevance: "primary" }

LS_003:
  text:
    en: "Any additional focus areas? (Optional - select up to 2)"
    ar: "أي مجالات تركيز إضافية؟ (اختياري - اختر حتى 2)"
  description:
    en: "You can add secondary goals to get a more comprehensive view."
    ar: "يمكنك إضافة أهداف ثانوية للحصول على رؤية أكثر شمولاً."
  type: multiple_choice
  required: false
  validation:
    - type: "max_selections"
      params: { max: 2 }
      message: 
        en: "Select up to 2 additional goals"
        ar: "اختر حتى هدفين إضافيين"
  options:
    # Same options as LS_001, dynamically filtered based on LS_001 response
    - value: "EYE-001"
      label: { en: "🌍 Export Readiness", ar: "🌍 جاهزية التصدير" }
    - value: "EYE-002"
      label: { en: "💰 Investment Readiness", ar: "💰 جاهزية الاستثمار" }
    - value: "EYE-003"
      label: { en: "💻 Digital Transformation", ar: "💻 التحول الرقمي" }
    - value: "EYE-004"
      label: { en: "⚙️ Operational Excellence", ar: "⚙️ التميز التشغيلي" }
    - value: "EYE-005"
      label: { en: "📈 Market Expansion", ar: "📈 التوسع في السوق" }
    - value: "EYE-006"
      label: { en: "🎨 Brand Building", ar: "🎨 بناء العلامة التجارية" }
    - value: "EYE-007"
      label: { en: "👥 Workforce Development", ar: "👥 تطوير القوى العاملة" }
    - value: "EYE-008"
      label: { en: "🔗 Supply Chain Optimization", ar: "🔗 تحسين سلسلة التوريد" }
    - value: "EYE-009"
      label: { en: "🌱 Sustainability & ESG", ar: "🌱 الاستدامة" }
    - value: "EYE-010"
      label: { en: "💡 Innovation & R&D", ar: "💡 الابتكار والبحث" }
    - value: "EYE-011"
      label: { en: "⭐ Customer Experience", ar: "⭐ تجربة العميل" }
    - value: "EYE-012"
      label: { en: "📊 Cost Optimization", ar: "📊 تحسين التكاليف" }
    - value: "EYE-013"
      label: { en: "🛡️ Risk & Resilience", ar: "🛡️ المخاطر والمرونة" }
    - value: "EYE-014"
      label: { en: "👤 Succession & Governance", ar: "👤 الخلافة والحوكمة" }
    - value: "EYE-015"
      label: { en: "🤝 Partnership & M&A", ar: "🤝 الشراكات والاستحواذ" }
  agents: [DRUCKER]
  data_field: secondary_lenses
  confidence_impact: medium
  lens_relevance: []

LS_004:
  text:
    en: "Describe your specific transformation goal"
    ar: "صف هدف التحول الخاص بك"
  description:
    en: "Tell us in your own words what you're trying to achieve. Be as specific as possible - this helps our AI configure the right analysis. (50-500 characters)"
    ar: "أخبرنا بكلماتك الخاصة ما تحاول تحقيقه. كن محدداً قدر الإمكان. (50-500 حرف)"
  type: text_long
  required: true
  conditional:
    - question_id: "LS_001"
      operator: "equals"
      value: "EYE-CUSTOM"
  validation:
    - type: "min_length"
      params: { min: 50 }
      message: 
        en: "Please provide at least 50 characters"
        ar: "يرجى تقديم 50 حرفاً على الأقل"
    - type: "max_length"
      params: { max: 500 }
      message: 
        en: "Maximum 500 characters"
        ar: "الحد الأقصى 500 حرف"
  placeholder:
    en: "Example: I want to become a certified supplier to multinational food companies in the Gulf region, focusing on organic dairy products..."
    ar: "مثال: أريد أن أصبح مورداً معتمداً للشركات الغذائية متعددة الجنسيات في منطقة الخليج، مع التركيز على منتجات الألبان العضوية..."
  agents: [DRUCKER]
  data_field: custom_objective_description
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-CUSTOM", relevance: "primary" }
```

---

# 4. Section 1: Business Profile

**Section Code:** `BP`  
**Primary Agents:** Drucker (Supervisor), All Agents  
**Estimated Time:** 3 minutes  
**Condition:** Always shown (Core)

## 4.1 Questions

```yaml
BP_001:
  text:
    en: "What is your company's legal name?"
    ar: "ما هو الاسم القانوني لشركتك؟"
  type: text_short
  required: true
  agents: [DRUCKER]
  data_field: company_name
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "secondary" }
    - { lens_id: "EYE-015", relevance: "secondary" }

BP_002:
  text:
    en: "What is your company's trade name or brand name (if different)?"
    ar: "ما هو الاسم التجاري أو العلامة التجارية لشركتك (إن كان مختلفاً)؟"
  type: text_short
  required: false
  agents: [DRUCKER, LANDOR]
  data_field: trade_name
  confidence_impact: low
  lens_relevance:
    - { lens_id: "EYE-006", relevance: "primary" }

BP_003:
  text:
    en: "In which country is your company headquartered?"
    ar: "في أي دولة يقع المقر الرئيسي لشركتك؟"
  type: country_select
  required: true
  options:
    - { value: "EG", label: { en: "Egypt", ar: "مصر" } }
    - { value: "SA", label: { en: "Saudi Arabia", ar: "المملكة العربية السعودية" } }
    - { value: "AE", label: { en: "United Arab Emirates", ar: "الإمارات العربية المتحدة" } }
    - { value: "JO", label: { en: "Jordan", ar: "الأردن" } }
    - { value: "LB", label: { en: "Lebanon", ar: "لبنان" } }
    - { value: "MA", label: { en: "Morocco", ar: "المغرب" } }
  agents: [DRUCKER, RICARDO]
  data_field: headquarters_country
  dimension: 11
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-001", relevance: "primary" }
    - { lens_id: "EYE-005", relevance: "secondary" }

BP_004:
  text:
    en: "What year was your company founded?"
    ar: "في أي سنة تأسست شركتك؟"
  type: numeric
  numeric_config:
    min: 1900
    max: 2026
    format: integer
  required: true
  agents: [DRUCKER, GRAHAM]
  data_field: founding_year
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "secondary" }
    - { lens_id: "EYE-014", relevance: "primary" }

BP_005:
  text:
    en: "Which industry best describes your company's primary business?"
    ar: "ما هو القطاع الذي يصف عمل شركتك الرئيسي بشكل أفضل؟"
  type: sector_select
  required: true
  description:
    en: "Select from 31 sectors. This determines which industry benchmarks and regulations apply."
    ar: "اختر من 31 قطاعاً. هذا يحدد المعايير واللوائح المطبقة."
  options:
    # Industrial Sectors (14)
    - value: "agriculture_agribusiness"
      label: { en: "Agriculture & Agribusiness", ar: "الزراعة والأعمال الزراعية" }
    - value: "automotive"
      label: { en: "Automotive", ar: "السيارات" }
    - value: "chemicals_plastics"
      label: { en: "Chemicals, Plastics & Specialty", ar: "الكيماويات والبلاستيك" }
    - value: "construction_building"
      label: { en: "Construction & Building", ar: "البناء والتشييد" }
    - value: "electronics_manufacturing"
      label: { en: "Electronics Manufacturing", ar: "تصنيع الإلكترونيات" }
    - value: "energy_utilities"
      label: { en: "Energy & Utilities", ar: "الطاقة والمرافق" }
    - value: "filling_bottling"
      label: { en: "Filling & Bottling", ar: "التعبئة والتغليف" }
    - value: "food_beverage_manufacturing"
      label: { en: "Food & Beverage Manufacturing", ar: "تصنيع الأغذية والمشروبات" }
    - value: "furniture_manufacturing"
      label: { en: "Furniture Manufacturing", ar: "تصنيع الأثاث" }
    - value: "metal_fabrication"
      label: { en: "Metal Fabrication & Manufacturing", ar: "تصنيع المعادن" }
    - value: "paper_printing"
      label: { en: "Paper & Printing", ar: "الورق والطباعة" }
    - value: "pharmaceuticals"
      label: { en: "Pharmaceuticals Manufacturing", ar: "تصنيع الأدوية" }
    - value: "plastics_manufacturing"
      label: { en: "Plastics Manufacturing", ar: "تصنيع البلاستيك" }
    - value: "textiles_apparel"
      label: { en: "Textiles & Apparel", ar: "المنسوجات والملابس" }
    # Services Sectors (15)
    - value: "beauty_wellness"
      label: { en: "Beauty & Wellness", ar: "الجمال والعافية" }
    - value: "education_training"
      label: { en: "Education & Training", ar: "التعليم والتدريب" }
    - value: "environmental_services"
      label: { en: "Environmental Services", ar: "الخدمات البيئية" }
    - value: "financial_services"
      label: { en: "Financial Services", ar: "الخدمات المالية" }
    - value: "healthcare_services"
      label: { en: "Healthcare Services", ar: "الخدمات الصحية" }
    - value: "hospitality_tourism"
      label: { en: "Hospitality & Tourism", ar: "الضيافة والسياحة" }
    - value: "logistics_transportation"
      label: { en: "Logistics & Transportation", ar: "اللوجستيات والنقل" }
    - value: "maintenance_repair"
      label: { en: "Maintenance & Repair Services", ar: "خدمات الصيانة والإصلاح" }
    - value: "professional_services"
      label: { en: "Professional Services", ar: "الخدمات المهنية" }
    - value: "real_estate"
      label: { en: "Real Estate", ar: "العقارات" }
    - value: "retail_commerce"
      label: { en: "Retail & Commerce", ar: "التجزئة والتجارة" }
    - value: "security_services"
      label: { en: "Security Services", ar: "خدمات الأمن" }
    - value: "technology_it"
      label: { en: "Technology & IT Services", ar: "التكنولوجيا وخدمات المعلومات" }
    - value: "telecommunications"
      label: { en: "Telecommunications", ar: "الاتصالات" }
    - value: "trading_distribution"
      label: { en: "Trading & Distribution", ar: "التجارة والتوزيع" }
    # Creative & Micro (2)
    - value: "creative_industries"
      label: { en: "Creative Industries", ar: "الصناعات الإبداعية" }
    - value: "home_based_micro"
      label: { en: "Home-Based & Micro Enterprise", ar: "المشاريع المنزلية والصغيرة" }
  agents: [DRUCKER, ALL]
  data_field: primary_sector
  dimension: 1
  confidence_impact: high
  lens_relevance: []  # All lenses need sector

BP_006:
  text:
    en: "How many full-time employees does your company currently have?"
    ar: "كم عدد الموظفين بدوام كامل في شركتك حالياً؟"
  type: single_choice
  required: true
  options:
    - { value: "1-10", label: { en: "1-10 employees", ar: "1-10 موظفين" }, score: 5 }
    - { value: "11-50", label: { en: "11-50 employees", ar: "11-50 موظف" }, score: 30 }
    - { value: "51-100", label: { en: "51-100 employees", ar: "51-100 موظف" }, score: 75 }
    - { value: "101-250", label: { en: "101-250 employees", ar: "101-250 موظف" }, score: 175 }
    - { value: "251-500", label: { en: "251-500 employees", ar: "251-500 موظف" }, score: 375 }
    - { value: "500+", label: { en: "500+ employees", ar: "أكثر من 500 موظف" }, score: 500 }
  agents: [DRUCKER, MAYO, GRAHAM]
  data_field: employee_count
  dimension: 7
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }
    - { lens_id: "EYE-002", relevance: "secondary" }
    - { lens_id: "EYE-014", relevance: "secondary" }

BP_007:
  text:
    en: "What is your role in the company?"
    ar: "ما هو دورك في الشركة؟"
  type: single_choice
  required: true
  options:
    - { value: "founder_ceo", label: { en: "Founder / CEO", ar: "المؤسس / الرئيس التنفيذي" } }
    - { value: "co_founder", label: { en: "Co-Founder / Partner", ar: "شريك مؤسس" } }
    - { value: "cfo_finance", label: { en: "CFO / Finance Director", ar: "المدير المالي" } }
    - { value: "coo_operations", label: { en: "COO / Operations Director", ar: "مدير العمليات" } }
    - { value: "general_manager", label: { en: "General Manager", ar: "المدير العام" } }
    - { value: "department_head", label: { en: "Department Head", ar: "رئيس قسم" } }
    - { value: "other", label: { en: "Other", ar: "أخرى" } }
  agents: [DRUCKER]
  data_field: respondent_role
  confidence_impact: medium
  allows_human_context: true
  human_context_prompt:
    en: "Feel free to describe your specific responsibilities"
    ar: "يمكنك وصف مسؤولياتك المحددة"
  lens_relevance:
    - { lens_id: "EYE-014", relevance: "primary" }

BP_008:
  text:
    en: "What is your company's legal structure?"
    ar: "ما هو الشكل القانوني لشركتك؟"
  type: single_choice
  required: true
  options:
    - { value: "sole_proprietorship", label: { en: "Sole Proprietorship", ar: "مؤسسة فردية" } }
    - { value: "partnership", label: { en: "Partnership", ar: "شراكة" } }
    - { value: "llc", label: { en: "Limited Liability Company (LLC)", ar: "شركة ذات مسؤولية محدودة" } }
    - { value: "joint_stock", label: { en: "Joint Stock Company", ar: "شركة مساهمة" } }
    - { value: "free_zone", label: { en: "Free Zone Entity", ar: "كيان منطقة حرة" } }
    - { value: "branch", label: { en: "Branch of Foreign Company", ar: "فرع لشركة أجنبية" } }
    - { value: "other", label: { en: "Other", ar: "أخرى" } }
  agents: [DRUCKER, GRAHAM]
  data_field: legal_structure
  dimension: 4
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "primary" }
    - { lens_id: "EYE-015", relevance: "primary" }
    - { lens_id: "EYE-014", relevance: "secondary" }

BP_009:
  text:
    en: "Do you have operations or sales in multiple countries?"
    ar: "هل لديك عمليات أو مبيعات في دول متعددة؟"
  type: single_choice
  required: true
  options:
    - value: "single_country"
      label: { en: "No, we operate in one country only", ar: "لا، نعمل في دولة واحدة فقط" }
    - value: "regional_mena"
      label: { en: "Yes, multiple MENA countries", ar: "نعم، في عدة دول في المنطقة" }
      triggers_followup: [BP_009a]
    - value: "international"
      label: { en: "Yes, including outside MENA", ar: "نعم، بما في ذلك خارج المنطقة" }
      triggers_followup: [BP_009a, BP_009b]
  agents: [DRUCKER, RICARDO]
  data_field: geographic_scope
  dimension: 9
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-001", relevance: "primary" }
    - { lens_id: "EYE-005", relevance: "primary" }

BP_009a:
  text:
    en: "Which countries do you currently operate in or sell to?"
    ar: "في أي دول تعمل حالياً أو تبيع فيها؟"
  type: multiple_choice
  required: false
  conditional:
    - { question_id: "BP_009", operator: "in", value: ["regional_mena", "international"] }
  options:
    - { value: "EG", label: { en: "Egypt", ar: "مصر" } }
    - { value: "SA", label: { en: "Saudi Arabia", ar: "السعودية" } }
    - { value: "AE", label: { en: "UAE", ar: "الإمارات" } }
    - { value: "JO", label: { en: "Jordan", ar: "الأردن" } }
    - { value: "KW", label: { en: "Kuwait", ar: "الكويت" } }
    - { value: "QA", label: { en: "Qatar", ar: "قطر" } }
    - { value: "BH", label: { en: "Bahrain", ar: "البحرين" } }
    - { value: "OM", label: { en: "Oman", ar: "عُمان" } }
    - { value: "MA", label: { en: "Morocco", ar: "المغرب" } }
    - { value: "LB", label: { en: "Lebanon", ar: "لبنان" } }
    - { value: "IQ", label: { en: "Iraq", ar: "العراق" } }
    - { value: "EU", label: { en: "European Union", ar: "الاتحاد الأوروبي" } }
    - { value: "US", label: { en: "United States", ar: "الولايات المتحدة" } }
    - { value: "UK", label: { en: "United Kingdom", ar: "المملكة المتحدة" } }
    - { value: "AFRICA", label: { en: "Africa (Sub-Saharan)", ar: "أفريقيا (جنوب الصحراء)" } }
    - { value: "ASIA", label: { en: "Asia-Pacific", ar: "آسيا والمحيط الهادئ" } }
    - { value: "OTHER", label: { en: "Other regions", ar: "مناطق أخرى" } }
  agents: [RICARDO, DRUCKER]
  data_field: operating_countries
  dimension: 11
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-001", relevance: "primary" }

BP_009b:
  text:
    en: "What percentage of your revenue comes from international sales?"
    ar: "ما نسبة إيراداتك التي تأتي من المبيعات الدولية؟"
  type: single_choice
  required: false
  conditional:
    - { question_id: "BP_009", operator: "equals", value: "international" }
  options:
    - { value: "under_10", label: { en: "Under 10%", ar: "أقل من 10%" } }
    - { value: "10_25", label: { en: "10-25%", ar: "10-25%" } }
    - { value: "25_50", label: { en: "25-50%", ar: "25-50%" } }
    - { value: "over_50", label: { en: "Over 50%", ar: "أكثر من 50%" } }
  agents: [RICARDO, GRAHAM]
  data_field: international_revenue_percentage
  dimension: 9
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-001", relevance: "primary" }

BP_010:
  text:
    en: "What are your company's top 3 strategic priorities for the next 12 months?"
    ar: "ما هي أهم 3 أولويات استراتيجية لشركتك في الـ 12 شهراً القادمة؟"
  type: ranking
  required: true
  options:
    - { value: "revenue_growth", label: { en: "Increase revenue / sales", ar: "زيادة الإيرادات / المبيعات" } }
    - { value: "profitability", label: { en: "Improve profitability", ar: "تحسين الربحية" } }
    - { value: "operational_efficiency", label: { en: "Improve operational efficiency", ar: "تحسين الكفاءة التشغيلية" } }
    - { value: "digital_transformation", label: { en: "Digital transformation", ar: "التحول الرقمي" } }
    - { value: "market_expansion", label: { en: "Expand to new markets", ar: "التوسع في أسواق جديدة" } }
    - { value: "new_products", label: { en: "Launch new products / services", ar: "إطلاق منتجات / خدمات جديدة" } }
    - { value: "talent", label: { en: "Attract & retain talent", ar: "جذب والحفاظ على الكفاءات" } }
    - { value: "funding", label: { en: "Secure funding / investment", ar: "الحصول على تمويل / استثمار" } }
    - { value: "export", label: { en: "Start or increase exports", ar: "بدء أو زيادة التصدير" } }
    - { value: "certifications", label: { en: "Obtain certifications", ar: "الحصول على شهادات" } }
    - { value: "sustainability", label: { en: "Improve sustainability", ar: "تحسين الاستدامة" } }
  agents: [DRUCKER, ALL]
  data_field: strategic_priorities
  confidence_impact: high
  allows_human_context: true
  human_context_prompt:
    en: "Any specific context about these priorities?"
    ar: "أي سياق محدد حول هذه الأولويات؟"
  lens_relevance: []

BP_011:
  text:
    en: "What prompted you to seek a business diagnostic today?"
    ar: "ما الذي دفعك للحصول على تشخيص أعمال اليوم؟"
  type: multiple_choice
  required: true
  options:
    - { value: "growth_planning", label: { en: "Planning for growth", ar: "التخطيط للنمو" } }
    - { value: "challenges", label: { en: "Facing specific challenges", ar: "مواجهة تحديات محددة" } }
    - { value: "funding_prep", label: { en: "Preparing for funding round", ar: "التحضير لجولة تمويل" } }
    - { value: "export_readiness", label: { en: "Exploring export opportunities", ar: "استكشاف فرص التصدير" } }
    - { value: "digital_upgrade", label: { en: "Considering digital upgrades", ar: "التفكير في ترقيات رقمية" } }
    - { value: "performance_check", label: { en: "Regular performance check", ar: "فحص أداء دوري" } }
    - { value: "partner_requirement", label: { en: "Partner or program requirement", ar: "متطلب من شريك أو برنامج" } }
    - { value: "other", label: { en: "Other reason", ar: "سبب آخر" } }
  agents: [DRUCKER]
  data_field: diagnostic_motivation
  confidence_impact: medium
  allows_human_context: true
  lens_relevance: []

BP_012:
  text:
    en: "How would you rate your overall business performance over the past 12 months?"
    ar: "كيف تقيّم أداء عملك بشكل عام خلال الـ 12 شهراً الماضية؟"
  type: scale
  required: true
  scale_config:
    min: 1
    max: 5
    step: 1
    labels:
      min: { en: "Very Poor", ar: "سيء جداً" }
      mid: { en: "Average", ar: "متوسط" }
      max: { en: "Excellent", ar: "ممتاز" }
  agents: [DRUCKER, DEMING]
  data_field: self_assessment_overall
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-CREMA", relevance: "primary" }

BP_013:
  text:
    en: "What is the single biggest challenge your business faces right now?"
    ar: "ما هو أكبر تحدٍ تواجهه شركتك الآن؟"
  type: text_long
  required: false
  agents: [DRUCKER, ALL]
  data_field: primary_challenge
  confidence_impact: high
  allows_human_context: true
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-CREMA", relevance: "primary" }

BP_014:
  text:
    en: "Is there anything special about your business we should know upfront?"
    ar: "هل هناك شيء خاص بعملك يجب أن نعرفه مسبقاً؟"
  type: human_context
  required: false
  description:
    en: "Share any unique circumstances, recent changes, or context that would help us understand your business better."
    ar: "شارك أي ظروف فريدة أو تغييرات حديثة أو سياق يساعدنا على فهم عملك بشكل أفضل."
  agents: [DRUCKER, ALL]
  data_field: human_context_business_profile
  confidence_impact: high
  lens_relevance: []

BP_015:
  text:
    en: "How did you hear about RootRise?"
    ar: "كيف سمعت عن RootRise؟"
  type: single_choice
  required: false
  options:
    - { value: "referral", label: { en: "Referral from another business", ar: "إحالة من شركة أخرى" } }
    - { value: "partner_program", label: { en: "Partner program (UNIDO, accelerator, etc.)", ar: "برنامج شريك" } }
    - { value: "social_media", label: { en: "Social media", ar: "وسائل التواصل الاجتماعي" } }
    - { value: "search", label: { en: "Web search", ar: "البحث على الإنترنت" } }
    - { value: "event", label: { en: "Event or conference", ar: "حدث أو مؤتمر" } }
    - { value: "other", label: { en: "Other", ar: "أخرى" } }
  agents: []
  data_field: acquisition_source
  confidence_impact: low
  lens_relevance: []
```

---

# 5. Section 2: Financial Health

**Section Code:** `FH`  
**Primary Agent:** Graham (The Alchemist)  
**Estimated Time:** 5 minutes  
**Condition:** Always shown (Core)

## 5.1 Questions

```yaml
FH_001:
  text:
    en: "What was your company's total revenue in the last complete fiscal year?"
    ar: "ما هو إجمالي إيرادات شركتك في آخر سنة مالية كاملة؟"
  type: currency
  required: true
  numeric_config:
    min: 0
    currency: "USD"
  description:
    en: "If you report in local currency, we'll convert it. Enter your best estimate if exact figures aren't available."
    ar: "إذا كنت تبلغ بالعملة المحلية، سنقوم بالتحويل. أدخل أفضل تقدير لديك."
  agents: [GRAHAM, DRUCKER]
  data_field: annual_revenue
  dimension: 2
  confidence_impact: high
  allows_human_context: true
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "primary" }
    - { lens_id: "EYE-012", relevance: "primary" }
    - { lens_id: "EYE-015", relevance: "primary" }

FH_002:
  text:
    en: "What currency do you primarily report your finances in?"
    ar: "ما هي العملة التي تستخدمها بشكل رئيسي في تقاريرك المالية؟"
  type: single_choice
  required: true
  options:
    - { value: "USD", label: { en: "US Dollar (USD)", ar: "الدولار الأمريكي" } }
    - { value: "EGP", label: { en: "Egyptian Pound (EGP)", ar: "الجنيه المصري" } }
    - { value: "SAR", label: { en: "Saudi Riyal (SAR)", ar: "الريال السعودي" } }
    - { value: "AED", label: { en: "UAE Dirham (AED)", ar: "الدرهم الإماراتي" } }
    - { value: "JOD", label: { en: "Jordanian Dinar (JOD)", ar: "الدينار الأردني" } }
    - { value: "MAD", label: { en: "Moroccan Dirham (MAD)", ar: "الدرهم المغربي" } }
    - { value: "LBP", label: { en: "Lebanese Pound (LBP)", ar: "الليرة اللبنانية" } }
    - { value: "EUR", label: { en: "Euro (EUR)", ar: "اليورو" } }
    - { value: "GBP", label: { en: "British Pound (GBP)", ar: "الجنيه الإسترليني" } }
    - { value: "OTHER", label: { en: "Other", ar: "أخرى" } }
  agents: [GRAHAM]
  data_field: reporting_currency
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-001", relevance: "secondary" }

FH_003:
  text:
    en: "How did your revenue change compared to the previous year?"
    ar: "كيف تغيرت إيراداتك مقارنة بالسنة السابقة؟"
  type: single_choice
  required: true
  options:
    - { value: "declined_significantly", label: { en: "Declined more than 20%", ar: "انخفضت أكثر من 20%" }, score: -25 }
    - { value: "declined_moderately", label: { en: "Declined 10-20%", ar: "انخفضت 10-20%" }, score: -15 }
    - { value: "declined_slightly", label: { en: "Declined less than 10%", ar: "انخفضت أقل من 10%" }, score: -5 }
    - { value: "stable", label: { en: "Roughly stable (±5%)", ar: "مستقرة تقريباً" }, score: 0 }
    - { value: "grew_slightly", label: { en: "Grew less than 10%", ar: "نمت أقل من 10%" }, score: 5 }
    - { value: "grew_moderately", label: { en: "Grew 10-25%", ar: "نمت 10-25%" }, score: 15 }
    - { value: "grew_significantly", label: { en: "Grew 25-50%", ar: "نمت 25-50%" }, score: 35 }
    - { value: "grew_rapidly", label: { en: "Grew more than 50%", ar: "نمت أكثر من 50%" }, score: 50 }
    - { value: "first_year", label: { en: "First year of operation", ar: "أول سنة تشغيل" }, score: 0 }
  agents: [GRAHAM, DRUCKER]
  data_field: revenue_growth_yoy
  dimension: 2
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "primary" }
    - { lens_id: "EYE-005", relevance: "primary" }

FH_004:
  text:
    en: "What is your company's gross profit margin?"
    ar: "ما هو هامش الربح الإجمالي لشركتك؟"
  type: single_choice
  required: true
  description:
    en: "Gross profit = Revenue minus Cost of Goods Sold (COGS)"
    ar: "الربح الإجمالي = الإيرادات ناقص تكلفة البضائع المباعة"
  options:
    - { value: "negative", label: { en: "Negative (loss on products)", ar: "سالب (خسارة على المنتجات)" }, score: -1 }
    - { value: "0-10", label: { en: "0-10%", ar: "0-10%" }, score: 5 }
    - { value: "10-20", label: { en: "10-20%", ar: "10-20%" }, score: 15 }
    - { value: "20-30", label: { en: "20-30%", ar: "20-30%" }, score: 25 }
    - { value: "30-40", label: { en: "30-40%", ar: "30-40%" }, score: 35 }
    - { value: "40-50", label: { en: "40-50%", ar: "40-50%" }, score: 45 }
    - { value: "50+", label: { en: "More than 50%", ar: "أكثر من 50%" }, score: 55 }
    - { value: "unsure", label: { en: "Not sure", ar: "غير متأكد" }, score: 0 }
  agents: [GRAHAM]
  data_field: gross_margin
  dimension: 2
  confidence_impact: high
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-012", relevance: "primary" }
    - { lens_id: "EYE-002", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

FH_005:
  text:
    en: "What is your company's net profit margin (after all expenses)?"
    ar: "ما هو هامش صافي الربح لشركتك (بعد كل المصاريف)؟"
  type: single_choice
  required: true
  options:
    - { value: "significant_loss", label: { en: "Significant loss (more than -20%)", ar: "خسارة كبيرة (أكثر من -20%)" }, score: -25 }
    - { value: "moderate_loss", label: { en: "Moderate loss (-10% to -20%)", ar: "خسارة معتدلة (-10% إلى -20%)" }, score: -15 }
    - { value: "small_loss", label: { en: "Small loss (0% to -10%)", ar: "خسارة صغيرة (0% إلى -10%)" }, score: -5 }
    - { value: "breakeven", label: { en: "Breakeven (around 0%)", ar: "نقطة التعادل (حوالي 0%)" }, score: 0 }
    - { value: "1-5", label: { en: "1-5%", ar: "1-5%" }, score: 3 }
    - { value: "5-10", label: { en: "5-10%", ar: "5-10%" }, score: 7 }
    - { value: "10-15", label: { en: "10-15%", ar: "10-15%" }, score: 12 }
    - { value: "15-20", label: { en: "15-20%", ar: "15-20%" }, score: 17 }
    - { value: "20+", label: { en: "More than 20%", ar: "أكثر من 20%" }, score: 25 }
    - { value: "unsure", label: { en: "Not sure", ar: "غير متأكد" }, score: 0 }
  agents: [GRAHAM]
  data_field: net_margin
  dimension: 2
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "primary" }
    - { lens_id: "EYE-012", relevance: "primary" }

FH_006:
  text:
    en: "How many months could your business survive if revenue stopped today?"
    ar: "كم شهراً يمكن لعملك البقاء إذا توقفت الإيرادات اليوم؟"
  type: single_choice
  required: true
  description:
    en: "This measures your cash runway - cash reserves divided by monthly burn rate"
    ar: "هذا يقيس احتياطيك النقدي - الاحتياطيات النقدية مقسومة على معدل الإنفاق الشهري"
  options:
    - { value: "0-1", label: { en: "Less than 1 month", ar: "أقل من شهر" }, score: 5 }
    - { value: "1-3", label: { en: "1-3 months", ar: "1-3 أشهر" }, score: 15 }
    - { value: "3-6", label: { en: "3-6 months", ar: "3-6 أشهر" }, score: 35 }
    - { value: "6-12", label: { en: "6-12 months", ar: "6-12 شهر" }, score: 65 }
    - { value: "12+", label: { en: "More than 12 months", ar: "أكثر من 12 شهر" }, score: 90 }
    - { value: "unsure", label: { en: "Not sure", ar: "غير متأكد" }, score: 0 }
  agents: [GRAHAM]
  data_field: cash_runway_months
  dimension: 2
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "primary" }
    - { lens_id: "EYE-013", relevance: "primary" }

FH_007:
  text:
    en: "What percentage of your revenue comes from your top 3 customers?"
    ar: "ما نسبة إيراداتك التي تأتي من أكبر 3 عملاء؟"
  type: single_choice
  required: true
  description:
    en: "Customer concentration affects business risk"
    ar: "تركز العملاء يؤثر على مخاطر الأعمال"
  options:
    - { value: "0-20", label: { en: "Less than 20%", ar: "أقل من 20%" }, score: 90 }
    - { value: "20-40", label: { en: "20-40%", ar: "20-40%" }, score: 70 }
    - { value: "40-60", label: { en: "40-60%", ar: "40-60%" }, score: 50 }
    - { value: "60-80", label: { en: "60-80%", ar: "60-80%" }, score: 30 }
    - { value: "80+", label: { en: "More than 80%", ar: "أكثر من 80%" }, score: 10 }
  agents: [GRAHAM, PORTER]
  data_field: customer_concentration
  dimension: 2
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "primary" }
    - { lens_id: "EYE-013", relevance: "primary" }
    - { lens_id: "EYE-005", relevance: "secondary" }

FH_008:
  text:
    en: "How quickly do customers typically pay you after invoicing?"
    ar: "كم من الوقت يستغرق العملاء عادةً للدفع بعد الفاتورة؟"
  type: single_choice
  required: true
  options:
    - { value: "prepaid", label: { en: "Prepaid / At delivery", ar: "مسبق الدفع / عند التسليم" }, score: 100 }
    - { value: "0-30", label: { en: "Within 30 days", ar: "خلال 30 يوم" }, score: 80 }
    - { value: "30-60", label: { en: "30-60 days", ar: "30-60 يوم" }, score: 60 }
    - { value: "60-90", label: { en: "60-90 days", ar: "60-90 يوم" }, score: 40 }
    - { value: "90+", label: { en: "More than 90 days", ar: "أكثر من 90 يوم" }, score: 20 }
    - { value: "irregular", label: { en: "Very irregular / Often delayed", ar: "غير منتظم / متأخر في الغالب" }, score: 10 }
  agents: [GRAHAM]
  data_field: days_sales_outstanding
  dimension: 2
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-012", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

FH_009:
  text:
    en: "How do you typically pay your suppliers?"
    ar: "كيف تدفع عادةً لمورديك؟"
  type: single_choice
  required: true
  options:
    - { value: "prepaid", label: { en: "Prepaid / Cash on delivery", ar: "مسبق الدفع / نقداً عند التسليم" }, score: 20 }
    - { value: "0-30", label: { en: "Within 30 days", ar: "خلال 30 يوم" }, score: 40 }
    - { value: "30-60", label: { en: "30-60 days", ar: "30-60 يوم" }, score: 60 }
    - { value: "60-90", label: { en: "60-90 days", ar: "60-90 يوم" }, score: 80 }
    - { value: "90+", label: { en: "More than 90 days", ar: "أكثر من 90 يوم" }, score: 90 }
  agents: [GRAHAM, OHNO]
  data_field: days_payables_outstanding
  dimension: 2
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "secondary" }
    - { lens_id: "EYE-012", relevance: "secondary" }

FH_010:
  text:
    en: "Has your company received external funding or investment?"
    ar: "هل حصلت شركتك على تمويل أو استثمار خارجي؟"
  type: single_choice
  required: true
  options:
    - value: "none"
      label: { en: "No, entirely self-funded (bootstrapped)", ar: "لا، ممولة ذاتياً بالكامل" }
    - value: "fam_friends"
      label: { en: "Yes, from family & friends", ar: "نعم، من العائلة والأصدقاء" }
    - value: "grants"
      label: { en: "Yes, grants or competitions", ar: "نعم، منح أو مسابقات" }
    - value: "angel"
      label: { en: "Yes, angel investors", ar: "نعم، مستثمرين ملائكيين" }
    - value: "vc"
      label: { en: "Yes, venture capital", ar: "نعم، رأس مال مخاطر" }
    - value: "bank_loan"
      label: { en: "Yes, bank loan", ar: "نعم، قرض بنكي" }
    - value: "dfi"
      label: { en: "Yes, development finance (DFI)", ar: "نعم، تمويل تنموي" }
    - value: "multiple"
      label: { en: "Multiple types", ar: "أنواع متعددة" }
  agents: [GRAHAM]
  data_field: funding_history
  dimension: 2
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "primary" }

FH_011:
  text:
    en: "Are you currently seeking additional funding?"
    ar: "هل تبحث حالياً عن تمويل إضافي؟"
  type: single_choice
  required: true
  options:
    - value: "not_seeking"
      label: { en: "No, not currently", ar: "لا، ليس حالياً" }
    - value: "exploring"
      label: { en: "Exploring options", ar: "أستكشف الخيارات" }
    - value: "actively_seeking"
      label: { en: "Yes, actively seeking", ar: "نعم، أبحث بشكل نشط" }
    - value: "in_process"
      label: { en: "Currently in fundraising process", ar: "حالياً في عملية جمع التمويل" }
  agents: [GRAHAM]
  data_field: funding_seeking
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "primary" }

FH_012:
  text:
    en: "Do you have audited financial statements?"
    ar: "هل لديك قوائم مالية مدققة؟"
  type: single_choice
  required: true
  options:
    - { value: "yes_big4", label: { en: "Yes, by Big 4 firm", ar: "نعم، من شركة Big 4" }, score: 100 }
    - { value: "yes_reputable", label: { en: "Yes, by reputable local firm", ar: "نعم، من شركة محلية معروفة" }, score: 80 }
    - { value: "yes_basic", label: { en: "Yes, basic audit", ar: "نعم، تدقيق أساسي" }, score: 60 }
    - { value: "reviewed", label: { en: "Reviewed (not audited)", ar: "مراجعة (غير مدققة)" }, score: 40 }
    - { value: "compiled", label: { en: "Compiled by accountant", ar: "معدة من قبل محاسب" }, score: 30 }
    - { value: "internal", label: { en: "Internal records only", ar: "سجلات داخلية فقط" }, score: 20 }
    - { value: "none", label: { en: "No formal statements", ar: "لا توجد قوائم رسمية" }, score: 5 }
  agents: [GRAHAM]
  data_field: financial_audit_status
  dimension: 2
  confidence_impact: high
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

FH_013:
  text:
    en: "What accounting system or software do you use?"
    ar: "ما نظام أو برنامج المحاسبة الذي تستخدمه؟"
  type: single_choice
  required: true
  options:
    - { value: "erp_tier1", label: { en: "Enterprise ERP (SAP, Oracle, Microsoft Dynamics)", ar: "نظام ERP مؤسسي" }, score: 100 }
    - { value: "erp_mid", label: { en: "Mid-market ERP (Odoo, ERPNext, NetSuite)", ar: "نظام ERP متوسط" }, score: 80 }
    - { value: "cloud_accounting", label: { en: "Cloud accounting (QuickBooks, Xero, Zoho)", ar: "محاسبة سحابية" }, score: 70 }
    - { value: "local_software", label: { en: "Local accounting software", ar: "برنامج محاسبة محلي" }, score: 50 }
    - { value: "spreadsheets", label: { en: "Spreadsheets (Excel, Google Sheets)", ar: "جداول بيانات" }, score: 30 }
    - { value: "manual", label: { en: "Manual / Paper-based", ar: "يدوي / ورقي" }, score: 10 }
  agents: [GRAHAM, LOVELACE]
  data_field: accounting_system
  dimension: 3
  confidence_impact: medium
  quick_win_indicator: true  # System upgrade = quick win
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital
    - { lens_id: "EYE-002", relevance: "secondary" }  # Investment - systems matter
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

FH_014:
  text:
    en: "What is your biggest financial challenge right now?"
    ar: "ما هو أكبر تحدٍ مالي تواجهه الآن؟"
  type: multiple_choice
  required: true
  options:
    - { value: "cash_flow", label: { en: "Cash flow management", ar: "إدارة التدفق النقدي" } }
    - { value: "access_capital", label: { en: "Access to capital", ar: "الوصول إلى رأس المال" } }
    - { value: "profitability", label: { en: "Improving profitability", ar: "تحسين الربحية" } }
    - { value: "cost_control", label: { en: "Controlling costs", ar: "التحكم في التكاليف" } }
    - { value: "pricing", label: { en: "Pricing strategy", ar: "استراتيجية التسعير" } }
    - { value: "collections", label: { en: "Collecting receivables", ar: "تحصيل المستحقات" } }
    - { value: "forex", label: { en: "Currency / FX exposure", ar: "التعرض للعملات" } }
    - { value: "reporting", label: { en: "Financial reporting / visibility", ar: "التقارير المالية / الرؤية" } }
    - { value: "none", label: { en: "No major financial challenges", ar: "لا تحديات مالية كبيرة" } }
  agents: [GRAHAM]
  data_field: financial_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  human_context_prompt:
    en: "Tell us more about this challenge"
    ar: "أخبرنا المزيد عن هذا التحدي"
  lens_relevance:
    - { lens_id: "EYE-012", relevance: "primary" }  # Cost
    - { lens_id: "EYE-CREMA", relevance: "primary" }  # Quick wins

FH_015:
  text:
    en: "How would you rate your confidence in your financial data?"
    ar: "كيف تقيّم ثقتك في بياناتك المالية؟"
  type: scale
  required: true
  scale_config:
    min: 1
    max: 5
    step: 1
    labels:
      min: { en: "Not confident at all", ar: "غير واثق على الإطلاق" }
      mid: { en: "Somewhat confident", ar: "واثق إلى حد ما" }
      max: { en: "Very confident", ar: "واثق جداً" }
  agents: [GRAHAM, DEMING]
  data_field: financial_data_confidence
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "secondary" }  # Investment

FH_016:
  text:
    en: "What is your current debt-to-equity ratio?"
    ar: "ما هي نسبة الدين إلى حقوق الملكية الحالية؟"
  type: single_choice
  required: false
  description:
    en: "Total debt divided by total equity. If unsure, select 'Not sure'."
    ar: "إجمالي الدين مقسوماً على إجمالي حقوق الملكية. إذا لم تكن متأكداً، اختر 'غير متأكد'."
  options:
    - { value: "0-0.5", label: { en: "0-0.5 (Low leverage)", ar: "0-0.5 (رافعة منخفضة)" }, score: 90 }
    - { value: "0.5-1", label: { en: "0.5-1 (Moderate)", ar: "0.5-1 (معتدلة)" }, score: 70 }
    - { value: "1-2", label: { en: "1-2 (Higher)", ar: "1-2 (أعلى)" }, score: 50 }
    - { value: "2+", label: { en: "Over 2 (High leverage)", ar: "أكثر من 2 (رافعة عالية)" }, score: 30 }
    - { value: "unsure", label: { en: "Not sure", ar: "غير متأكد" }, score: 0 }
  agents: [GRAHAM]
  data_field: debt_equity_ratio
  dimension: 2
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "primary" }  # Investment
    - { lens_id: "EYE-013", relevance: "primary" }  # Risk

FH_017:
  text:
    en: "How do you currently manage your budget and forecasting?"
    ar: "كيف تدير ميزانيتك والتوقعات حالياً؟"
  type: single_choice
  required: true
  options:
    - { value: "no_budget", label: { en: "No formal budget", ar: "لا توجد ميزانية رسمية" }, score: 10 }
    - { value: "annual_only", label: { en: "Annual budget only", ar: "ميزانية سنوية فقط" }, score: 40 }
    - { value: "quarterly", label: { en: "Quarterly review", ar: "مراجعة ربع سنوية" }, score: 60 }
    - { value: "monthly", label: { en: "Monthly review and adjustment", ar: "مراجعة وتعديل شهري" }, score: 80 }
    - { value: "rolling_forecast", label: { en: "Rolling forecast with scenarios", ar: "توقعات متجددة مع سيناريوهات" }, score: 100 }
  agents: [GRAHAM]
  data_field: budgeting_practice
  dimension: 4
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "secondary" }  # Investment
    - { lens_id: "EYE-004", relevance: "secondary" }  # Operations

FH_018:
  text:
    en: "Do you track unit economics for your products or services?"
    ar: "هل تتتبع اقتصاديات الوحدة لمنتجاتك أو خدماتك؟"
  type: single_choice
  required: true
  description:
    en: "Unit economics = understanding cost and revenue per customer, product, or transaction"
    ar: "اقتصاديات الوحدة = فهم التكلفة والإيرادات لكل عميل أو منتج أو معاملة"
  options:
    - { value: "no", label: { en: "No, we don't track this", ar: "لا، لا نتتبع هذا" }, score: 10 }
    - { value: "basic", label: { en: "Basic understanding", ar: "فهم أساسي" }, score: 40 }
    - { value: "detailed", label: { en: "Yes, detailed tracking", ar: "نعم، تتبع مفصل" }, score: 80 }
    - { value: "optimized", label: { en: "Yes, actively optimizing", ar: "نعم، نحسنها بشكل فعال" }, score: 100 }
  agents: [GRAHAM, MARVIN]
  data_field: unit_economics_tracking
  dimension: 2
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "primary" }  # Investment - unit economics critical
    - { lens_id: "EYE-012", relevance: "primary" }  # Cost

FH_019:
  text:
    en: "What is your approximate monthly operating expenses (OpEx)?"
    ar: "ما هي مصاريفك التشغيلية الشهرية التقريبية؟"
  type: currency
  required: false
  numeric_config:
    min: 0
    currency: "USD"
  agents: [GRAHAM]
  data_field: monthly_opex
  dimension: 2
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-012", relevance: "primary" }  # Cost

FH_020:
  text:
    en: "Is there anything else about your financial situation we should know?"
    ar: "هل هناك أي شيء آخر عن وضعك المالي يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any context that would help us understand your financial position better - recent changes, unusual circumstances, plans in progress."
    ar: "شارك أي سياق يساعدنا على فهم وضعك المالي بشكل أفضل."
  agents: [GRAHAM]
  data_field: human_context_financial
  confidence_impact: high
  lens_relevance: []

---

# 6. Section 3: Operations & Production

**Section Code:** `OP`  
**Primary Agents:** Marvin (Optimizer), Ohno (Supply Chain), Deming (Quality)  
**Estimated Time:** 4 minutes  
**Condition:** Always shown (Core)

## 6.1 Questions

```yaml
OP_001:
  text:
    en: "What is your company's primary business model?"
    ar: "ما هو نموذج عملك الرئيسي؟"
  type: single_choice
  required: true
  options:
    - { value: "manufacturing", label: { en: "Manufacturing / Production", ar: "تصنيع / إنتاج" } }
    - { value: "services", label: { en: "Services", ar: "خدمات" } }
    - { value: "trading", label: { en: "Trading / Distribution", ar: "تجارة / توزيع" } }
    - { value: "hybrid_mfg_svc", label: { en: "Manufacturing + Services", ar: "تصنيع + خدمات" } }
    - { value: "hybrid_trade_svc", label: { en: "Trading + Services", ar: "تجارة + خدمات" } }
    - { value: "platform", label: { en: "Platform / Marketplace", ar: "منصة / سوق" } }
    - { value: "saas", label: { en: "SaaS / Subscription", ar: "برمجيات كخدمة / اشتراك" } }
  agents: [MARVIN, DRUCKER]
  data_field: business_model
  dimension: 1
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }  # Operations

OP_002:
  text:
    en: "Do you own or operate production facilities?"
    ar: "هل تملك أو تدير مرافق إنتاج؟"
  type: single_choice
  required: true
  conditional:
    - { question_id: "OP_001", operator: "in", value: ["manufacturing", "hybrid_mfg_svc"] }
  options:
    - value: "owned"
      label: { en: "Yes, owned facilities", ar: "نعم، مرافق مملوكة" }
      triggers_followup: [OP_002a]
    - value: "leased"
      label: { en: "Yes, leased facilities", ar: "نعم، مرافق مؤجرة" }
      triggers_followup: [OP_002a]
    - value: "outsourced"
      label: { en: "No, fully outsourced production", ar: "لا، إنتاج خارجي بالكامل" }
    - value: "mixed"
      label: { en: "Mixed (some owned, some outsourced)", ar: "مختلط" }
      triggers_followup: [OP_002a]
  agents: [MARVIN, OHNO]
  data_field: facility_ownership
  dimension: 6
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }  # Operations
    - { lens_id: "EYE-012", relevance: "secondary" }  # Cost

OP_002a:
  text:
    en: "What is your total production floor area?"
    ar: "ما هي مساحة أرضية الإنتاج الإجمالية؟"
  type: single_choice
  required: false
  conditional:
    - { question_id: "OP_002", operator: "in", value: ["owned", "leased", "mixed"] }
  options:
    - { value: "under_500", label: { en: "Under 500 sqm", ar: "أقل من 500 متر مربع" } }
    - { value: "500_1000", label: { en: "500-1,000 sqm", ar: "500-1,000 متر مربع" } }
    - { value: "1000_5000", label: { en: "1,000-5,000 sqm", ar: "1,000-5,000 متر مربع" } }
    - { value: "5000_10000", label: { en: "5,000-10,000 sqm", ar: "5,000-10,000 متر مربع" } }
    - { value: "over_10000", label: { en: "Over 10,000 sqm", ar: "أكثر من 10,000 متر مربع" } }
  agents: [MARVIN]
  data_field: production_area
  dimension: 6
  confidence_impact: low
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "secondary" }

OP_003:
  text:
    en: "How would you rate your current operational efficiency?"
    ar: "كيف تقيّم كفاءتك التشغيلية الحالية؟"
  type: scale
  required: true
  scale_config:
    min: 1
    max: 5
    step: 1
    labels:
      min: { en: "Very inefficient - significant waste", ar: "غير كفء جداً - هدر كبير" }
      mid: { en: "Average", ar: "متوسط" }
      max: { en: "Highly efficient - lean operations", ar: "كفء جداً - عمليات رشيقة" }
  agents: [MARVIN, DEMING]
  data_field: operational_efficiency_self_rating
  dimension: 6
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }  # Operations
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

OP_004:
  text:
    en: "What percentage of your production capacity are you currently utilizing?"
    ar: "ما نسبة طاقتك الإنتاجية التي تستخدمها حالياً؟"
  type: single_choice
  required: true
  conditional:
    - { question_id: "OP_001", operator: "in", value: ["manufacturing", "hybrid_mfg_svc"] }
  options:
    - { value: "under_50", label: { en: "Under 50%", ar: "أقل من 50%" }, score: 25 }
    - { value: "50_70", label: { en: "50-70%", ar: "50-70%" }, score: 60 }
    - { value: "70_85", label: { en: "70-85%", ar: "70-85%" }, score: 78 }
    - { value: "85_95", label: { en: "85-95%", ar: "85-95%" }, score: 90 }
    - { value: "over_95", label: { en: "Over 95% (at capacity)", ar: "أكثر من 95% (عند الطاقة القصوى)" }, score: 95 }
    - { value: "unsure", label: { en: "Not sure", ar: "غير متأكد" }, score: 0 }
  agents: [MARVIN]
  data_field: capacity_utilization
  dimension: 6
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }  # Operations
    - { lens_id: "EYE-005", relevance: "secondary" }  # Market - can you grow?

OP_005:
  text:
    en: "Do you track Overall Equipment Effectiveness (OEE) or similar metrics?"
    ar: "هل تتتبع الفعالية الإجمالية للمعدات (OEE) أو مقاييس مماثلة؟"
  type: single_choice
  required: true
  conditional:
    - { question_id: "OP_001", operator: "in", value: ["manufacturing", "hybrid_mfg_svc"] }
  description:
    en: "OEE measures availability, performance, and quality of production equipment"
    ar: "OEE تقيس التوفر والأداء والجودة لمعدات الإنتاج"
  options:
    - { value: "no_tracking", label: { en: "No, we don't track this", ar: "لا، لا نتتبع هذا" }, score: 10 }
    - { value: "informal", label: { en: "Informally / manually", ar: "بشكل غير رسمي / يدوي" }, score: 30 }
    - { value: "basic", label: { en: "Basic tracking", ar: "تتبع أساسي" }, score: 50 }
    - { value: "detailed", label: { en: "Detailed tracking with targets", ar: "تتبع مفصل مع أهداف" }, score: 80 }
    - { value: "realtime", label: { en: "Real-time monitoring with alerts", ar: "مراقبة فورية مع تنبيهات" }, score: 100 }
  agents: [MARVIN, DEMING]
  data_field: oee_tracking
  dimension: 3
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }  # Operations
    - { lens_id: "EYE-003", relevance: "secondary" }  # Digital

OP_006:
  text:
    en: "What is your typical product defect or rework rate?"
    ar: "ما هو معدل العيوب أو إعادة العمل النموذجي لمنتجاتك؟"
  type: single_choice
  required: true
  conditional:
    - { question_id: "OP_001", operator: "in", value: ["manufacturing", "hybrid_mfg_svc"] }
  options:
    - { value: "under_1", label: { en: "Under 1%", ar: "أقل من 1%" }, score: 95 }
    - { value: "1_3", label: { en: "1-3%", ar: "1-3%" }, score: 80 }
    - { value: "3_5", label: { en: "3-5%", ar: "3-5%" }, score: 60 }
    - { value: "5_10", label: { en: "5-10%", ar: "5-10%" }, score: 40 }
    - { value: "over_10", label: { en: "Over 10%", ar: "أكثر من 10%" }, score: 20 }
    - { value: "not_measured", label: { en: "Not measured", ar: "غير مقاس" }, score: 0 }
  agents: [DEMING, MARVIN]
  data_field: defect_rate
  dimension: 6
  confidence_impact: medium
  quick_win_indicator: true  # High defect rate = quality quick wins
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }  # Operations
    - { lens_id: "EYE-012", relevance: "primary" }  # Cost - quality cost
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

OP_007:
  text:
    en: "What production or operations management methodology do you follow?"
    ar: "ما منهجية إدارة الإنتاج أو العمليات التي تتبعها؟"
  type: multiple_choice
  required: true
  options:
    - { value: "none", label: { en: "No formal methodology", ar: "لا توجد منهجية رسمية" } }
    - { value: "lean", label: { en: "Lean Manufacturing", ar: "التصنيع الرشيق" } }
    - { value: "six_sigma", label: { en: "Six Sigma", ar: "سيكس سيجما" } }
    - { value: "tpm", label: { en: "Total Productive Maintenance (TPM)", ar: "الصيانة الإنتاجية الشاملة" } }
    - { value: "tqm", label: { en: "Total Quality Management (TQM)", ar: "إدارة الجودة الشاملة" } }
    - { value: "agile", label: { en: "Agile / Scrum", ar: "أجايل / سكرام" } }
    - { value: "iso", label: { en: "ISO standards-based", ar: "قائمة على معايير ISO" } }
    - { value: "custom", label: { en: "Custom / hybrid approach", ar: "نهج مخصص / مختلط" } }
  agents: [MARVIN, DEMING]
  data_field: operations_methodology
  dimension: 4
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }  # Operations

OP_008:
  text:
    en: "How do you currently schedule and plan production or service delivery?"
    ar: "كيف تخطط وتجدول الإنتاج أو تقديم الخدمات حالياً؟"
  type: single_choice
  required: true
  options:
    - { value: "manual_adhoc", label: { en: "Manual / Ad-hoc", ar: "يدوي / حسب الحاجة" }, score: 10 }
    - { value: "spreadsheets", label: { en: "Spreadsheets", ar: "جداول بيانات" }, score: 30 }
    - { value: "basic_software", label: { en: "Basic planning software", ar: "برنامج تخطيط أساسي" }, score: 50 }
    - { value: "mrp_erp", label: { en: "MRP/ERP system", ar: "نظام MRP/ERP" }, score: 80 }
    - { value: "advanced_aps", label: { en: "Advanced Planning & Scheduling (APS)", ar: "تخطيط وجدولة متقدمة" }, score: 100 }
  agents: [MARVIN, LOVELACE]
  data_field: production_planning_system
  dimension: 3
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }  # Operations
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital

OP_009:
  text:
    en: "What is your average order fulfillment or delivery time?"
    ar: "ما هو متوسط وقت تنفيذ الطلب أو التسليم؟"
  type: single_choice
  required: true
  options:
    - { value: "same_day", label: { en: "Same day", ar: "نفس اليوم" } }
    - { value: "1_3_days", label: { en: "1-3 days", ar: "1-3 أيام" } }
    - { value: "1_week", label: { en: "About 1 week", ar: "حوالي أسبوع" } }
    - { value: "2_4_weeks", label: { en: "2-4 weeks", ar: "2-4 أسابيع" } }
    - { value: "1_3_months", label: { en: "1-3 months", ar: "1-3 أشهر" } }
    - { value: "over_3_months", label: { en: "Over 3 months", ar: "أكثر من 3 أشهر" } }
    - { value: "varies", label: { en: "Varies significantly", ar: "يختلف بشكل كبير" } }
  agents: [MARVIN, OHNO]
  data_field: lead_time
  dimension: 6
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }  # Operations
    - { lens_id: "EYE-011", relevance: "secondary" }  # Customer Experience

OP_010:
  text:
    en: "What is your on-time delivery rate?"
    ar: "ما هو معدل التسليم في الوقت المحدد؟"
  type: single_choice
  required: true
  options:
    - { value: "under_70", label: { en: "Under 70%", ar: "أقل من 70%" }, score: 35 }
    - { value: "70_80", label: { en: "70-80%", ar: "70-80%" }, score: 75 }
    - { value: "80_90", label: { en: "80-90%", ar: "80-90%" }, score: 85 }
    - { value: "90_95", label: { en: "90-95%", ar: "90-95%" }, score: 93 }
    - { value: "over_95", label: { en: "Over 95%", ar: "أكثر من 95%" }, score: 97 }
    - { value: "not_tracked", label: { en: "Not tracked", ar: "غير مُتتبع" }, score: 0 }
  agents: [MARVIN, OHNO, DEMING]
  data_field: on_time_delivery
  dimension: 6
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }  # Operations
    - { lens_id: "EYE-011", relevance: "primary" }  # Customer Experience
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

OP_011:
  text:
    en: "How do you manage inventory?"
    ar: "كيف تدير المخزون؟"
  type: single_choice
  required: true
  options:
    - { value: "no_system", label: { en: "No formal system", ar: "لا يوجد نظام رسمي" }, score: 10 }
    - { value: "periodic_count", label: { en: "Periodic manual counts", ar: "جرد يدوي دوري" }, score: 30 }
    - { value: "spreadsheets", label: { en: "Spreadsheet tracking", ar: "تتبع بجداول البيانات" }, score: 40 }
    - { value: "basic_software", label: { en: "Basic inventory software", ar: "برنامج مخزون أساسي" }, score: 60 }
    - { value: "integrated_erp", label: { en: "Integrated with ERP", ar: "متكامل مع ERP" }, score: 85 }
    - { value: "wms", label: { en: "Full WMS with barcode/RFID", ar: "نظام WMS كامل مع باركود/RFID" }, score: 100 }
  agents: [OHNO, MARVIN, LOVELACE]
  data_field: inventory_management
  dimension: 3
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain
    - { lens_id: "EYE-003", relevance: "secondary" }  # Digital
    - { lens_id: "EYE-012", relevance: "secondary" }  # Cost

OP_012:
  text:
    en: "What is your current inventory turnover (times per year)?"
    ar: "ما هو معدل دوران المخزون الحالي (مرات في السنة)؟"
  type: single_choice
  required: false
  description:
    en: "How many times you sell and replace inventory in a year"
    ar: "كم مرة تبيع وتستبدل المخزون في السنة"
  options:
    - { value: "under_2", label: { en: "Under 2 times", ar: "أقل من مرتين" }, score: 20 }
    - { value: "2_4", label: { en: "2-4 times", ar: "2-4 مرات" }, score: 40 }
    - { value: "4_8", label: { en: "4-8 times", ar: "4-8 مرات" }, score: 60 }
    - { value: "8_12", label: { en: "8-12 times", ar: "8-12 مرة" }, score: 80 }
    - { value: "over_12", label: { en: "Over 12 times", ar: "أكثر من 12 مرة" }, score: 100 }
    - { value: "unsure", label: { en: "Not sure", ar: "غير متأكد" }, score: 0 }
  agents: [OHNO, GRAHAM]
  data_field: inventory_turnover
  dimension: 6
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain
    - { lens_id: "EYE-012", relevance: "secondary" }  # Cost

OP_013:
  text:
    en: "What quality management certifications do you hold?"
    ar: "ما شهادات إدارة الجودة التي تملكها؟"
  type: multiple_choice
  required: true
  options:
    - { value: "none", label: { en: "None currently", ar: "لا توجد حالياً" } }
    - { value: "iso9001", label: { en: "ISO 9001 (Quality Management)", ar: "ISO 9001 (إدارة الجودة)" } }
    - { value: "iso14001", label: { en: "ISO 14001 (Environmental)", ar: "ISO 14001 (البيئة)" } }
    - { value: "iso45001", label: { en: "ISO 45001 (Health & Safety)", ar: "ISO 45001 (الصحة والسلامة)" } }
    - { value: "iso22000", label: { en: "ISO 22000 / FSSC 22000 (Food Safety)", ar: "ISO 22000 (سلامة الغذاء)" } }
    - { value: "haccp", label: { en: "HACCP", ar: "HACCP" } }
    - { value: "gmp", label: { en: "GMP (Good Manufacturing Practice)", ar: "GMP (ممارسات التصنيع الجيدة)" } }
    - { value: "other", label: { en: "Other industry-specific", ar: "أخرى خاصة بالصناعة" } }
  agents: [DEMING, MARVIN]
  data_field: quality_certifications
  dimension: 4
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-001", relevance: "primary" }  # Export - certifications critical
    - { lens_id: "EYE-004", relevance: "secondary" }  # Operations

OP_014:
  text:
    en: "How do you handle maintenance of equipment and machinery?"
    ar: "كيف تتعامل مع صيانة المعدات والآلات؟"
  type: single_choice
  required: true
  conditional:
    - { question_id: "OP_001", operator: "in", value: ["manufacturing", "hybrid_mfg_svc"] }
  options:
    - { value: "reactive", label: { en: "Reactive (fix when broken)", ar: "تفاعلية (إصلاح عند الكسر)" }, score: 20 }
    - { value: "scheduled", label: { en: "Scheduled / Calendar-based", ar: "مجدولة / حسب التقويم" }, score: 50 }
    - { value: "preventive", label: { en: "Preventive (usage-based)", ar: "وقائية (حسب الاستخدام)" }, score: 70 }
    - { value: "predictive", label: { en: "Predictive (data-driven)", ar: "تنبؤية (مبنية على البيانات)" }, score: 90 }
    - { value: "tpm", label: { en: "Total Productive Maintenance", ar: "الصيانة الإنتاجية الشاملة" }, score: 100 }
  agents: [MARVIN, LOVELACE]
  data_field: maintenance_approach
  dimension: 6
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }  # Operations
    - { lens_id: "EYE-003", relevance: "secondary" }  # Digital - predictive

OP_015:
  text:
    en: "What is your biggest operational challenge right now?"
    ar: "ما هو أكبر تحدٍ تشغيلي تواجهه الآن؟"
  type: multiple_choice
  required: true
  options:
    - { value: "capacity", label: { en: "Capacity constraints", ar: "قيود الطاقة الإنتاجية" } }
    - { value: "quality", label: { en: "Quality issues", ar: "مشاكل الجودة" } }
    - { value: "cost", label: { en: "High operating costs", ar: "تكاليف تشغيل عالية" } }
    - { value: "labor", label: { en: "Labor availability / skills", ar: "توفر / مهارات العمالة" } }
    - { value: "equipment", label: { en: "Equipment reliability", ar: "موثوقية المعدات" } }
    - { value: "materials", label: { en: "Material availability / cost", ar: "توفر / تكلفة المواد" } }
    - { value: "delivery", label: { en: "Meeting delivery times", ar: "الالتزام بمواعيد التسليم" } }
    - { value: "scaling", label: { en: "Scaling operations", ar: "توسيع العمليات" } }
    - { value: "systems", label: { en: "Lack of systems / visibility", ar: "نقص الأنظمة / الرؤية" } }
    - { value: "none", label: { en: "No major challenges", ar: "لا تحديات كبيرة" } }
  agents: [MARVIN, DRUCKER]
  data_field: operational_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  human_context_prompt:
    en: "Tell us more about this challenge"
    ar: "أخبرنا المزيد عن هذا التحدي"
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }  # Operations
    - { lens_id: "EYE-CREMA", relevance: "primary" }  # Quick wins

OP_016:
  text:
    en: "How do you ensure health and safety in your operations?"
    ar: "كيف تضمن الصحة والسلامة في عملياتك؟"
  type: single_choice
  required: true
  options:
    - { value: "informal", label: { en: "Informal / basic precautions", ar: "غير رسمي / احتياطات أساسية" }, score: 20 }
    - { value: "documented", label: { en: "Documented procedures", ar: "إجراءات موثقة" }, score: 50 }
    - { value: "trained", label: { en: "Regular training + audits", ar: "تدريب منتظم + تدقيق" }, score: 75 }
    - { value: "certified", label: { en: "Certified system (ISO 45001)", ar: "نظام معتمد (ISO 45001)" }, score: 100 }
  agents: [MARVIN, MAYO]
  data_field: safety_management
  dimension: 7
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "secondary" }  # Workforce
    - { lens_id: "EYE-013", relevance: "secondary" }  # Risk

OP_017:
  text:
    en: "Do you have documented Standard Operating Procedures (SOPs)?"
    ar: "هل لديك إجراءات تشغيل موحدة موثقة (SOPs)؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "No documented SOPs", ar: "لا توجد إجراءات موثقة" }, score: 10 }
    - { value: "some", label: { en: "Some processes documented", ar: "بعض العمليات موثقة" }, score: 40 }
    - { value: "most", label: { en: "Most processes documented", ar: "معظم العمليات موثقة" }, score: 70 }
    - { value: "all_basic", label: { en: "All documented, updated occasionally", ar: "كلها موثقة، تحديث عرضي" }, score: 85 }
    - { value: "all_maintained", label: { en: "All documented, regularly maintained", ar: "كلها موثقة وتحديث منتظم" }, score: 100 }
  agents: [MARVIN, DEMING]
  data_field: sop_documentation
  dimension: 4
  confidence_impact: medium
  quick_win_indicator: true  # SOP creation = quick win
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }  # Operations
    - { lens_id: "EYE-007", relevance: "secondary" }  # Workforce - training
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

OP_018:
  text:
    en: "Is there anything unique about your operations we should know?"
    ar: "هل هناك شيء فريد حول عملياتك يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any special circumstances, recent changes, or context about your operations"
    ar: "شارك أي ظروف خاصة أو تغييرات حديثة أو سياق حول عملياتك"
  agents: [MARVIN, DRUCKER]
  data_field: human_context_operations
  confidence_impact: high
  lens_relevance: []

---

# 7. Section 4: Digital Maturity

**Section Code:** `DM`  
**Primary Agent:** Lovelace (The Digitizer)  
**Estimated Time:** 3 minutes  
**Condition:** Show if lens requires (EYE-003, EYE-010) OR Crema active OR agent auto-selected

## 7.1 Questions

```yaml
DM_001:
  text:
    en: "How would you rate your company's overall digital maturity?"
    ar: "كيف تقيّم النضج الرقمي الإجمالي لشركتك؟"
  type: scale
  required: true
  scale_config:
    min: 1
    max: 5
    step: 1
    labels:
      min: { en: "Digital Beginner - Mostly manual processes", ar: "مبتدئ رقمياً - عمليات يدوية في الغالب" }
      mid: { en: "Developing - Some digital tools", ar: "متطور - بعض الأدوات الرقمية" }
      max: { en: "Digital Leader - Fully integrated", ar: "قائد رقمي - متكامل بالكامل" }
  agents: [LOVELACE, DRUCKER]
  data_field: digital_maturity_self_rating
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital
    - { lens_id: "EYE-010", relevance: "secondary" }  # Innovation

DM_002:
  text:
    en: "What core business systems do you currently use?"
    ar: "ما أنظمة الأعمال الأساسية التي تستخدمها حالياً؟"
  type: multiple_choice
  required: true
  options:
    - { value: "erp", label: { en: "ERP System", ar: "نظام ERP" } }
    - { value: "crm", label: { en: "CRM System", ar: "نظام CRM" } }
    - { value: "accounting", label: { en: "Accounting Software", ar: "برنامج محاسبة" } }
    - { value: "hrms", label: { en: "HR Management System", ar: "نظام إدارة الموارد البشرية" } }
    - { value: "inventory", label: { en: "Inventory Management", ar: "إدارة المخزون" } }
    - { value: "pos", label: { en: "Point of Sale (POS)", ar: "نقطة البيع" } }
    - { value: "ecommerce", label: { en: "E-commerce Platform", ar: "منصة تجارة إلكترونية" } }
    - { value: "project_mgmt", label: { en: "Project Management Tool", ar: "أداة إدارة المشاريع" } }
    - { value: "bi_analytics", label: { en: "BI / Analytics Tool", ar: "أداة ذكاء الأعمال / التحليلات" } }
    - { value: "collab", label: { en: "Collaboration Tools (Slack, Teams)", ar: "أدوات تعاون" } }
    - { value: "none", label: { en: "None - using spreadsheets/manual", ar: "لا شيء - استخدام جداول/يدوي" } }
  agents: [LOVELACE]
  data_field: core_systems
  dimension: 3
  confidence_impact: high
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

DM_003:
  text:
    en: "How integrated are your business systems?"
    ar: "ما مدى تكامل أنظمة أعمالك؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "Not integrated - data silos", ar: "غير متكاملة - صوامع بيانات" }, score: 10 }
    - { value: "manual", label: { en: "Manual data transfer between systems", ar: "نقل بيانات يدوي بين الأنظمة" }, score: 30 }
    - { value: "partial", label: { en: "Some systems integrated", ar: "بعض الأنظمة متكاملة" }, score: 50 }
    - { value: "mostly", label: { en: "Most systems integrated", ar: "معظم الأنظمة متكاملة" }, score: 75 }
    - { value: "fully", label: { en: "Fully integrated ecosystem", ar: "نظام بيئي متكامل بالكامل" }, score: 100 }
  agents: [LOVELACE]
  data_field: system_integration
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital

DM_004:
  text:
    en: "Do you have a company website?"
    ar: "هل لديك موقع إلكتروني للشركة؟"
  type: single_choice
  required: true
  options:
    - value: "no"
      label: { en: "No website", ar: "لا يوجد موقع" }
      score: 0
    - value: "basic"
      label: { en: "Basic informational site", ar: "موقع معلوماتي أساسي" }
      score: 30
    - value: "professional"
      label: { en: "Professional site with regular updates", ar: "موقع احترافي مع تحديثات منتظمة" }
      score: 60
    - value: "ecommerce"
      label: { en: "E-commerce enabled", ar: "مُمكّن للتجارة الإلكترونية" }
      score: 80
      triggers_followup: [DM_004a]
    - value: "full_digital"
      label: { en: "Full digital experience (portal, app)", ar: "تجربة رقمية كاملة (بوابة، تطبيق)" }
      score: 100
      triggers_followup: [DM_004a]
  agents: [LOVELACE, LANDOR]
  data_field: website_status
  dimension: 3
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital
    - { lens_id: "EYE-006", relevance: "secondary" }  # Brand
    - { lens_id: "EYE-011", relevance: "secondary" }  # Customer Experience

DM_004a:
  text:
    en: "What percentage of your sales come through digital channels?"
    ar: "ما نسبة مبيعاتك التي تأتي من القنوات الرقمية؟"
  type: single_choice
  required: false
  conditional:
    - { question_id: "DM_004", operator: "in", value: ["ecommerce", "full_digital"] }
  options:
    - { value: "under_10", label: { en: "Under 10%", ar: "أقل من 10%" } }
    - { value: "10_25", label: { en: "10-25%", ar: "10-25%" } }
    - { value: "25_50", label: { en: "25-50%", ar: "25-50%" } }
    - { value: "50_75", label: { en: "50-75%", ar: "50-75%" } }
    - { value: "over_75", label: { en: "Over 75%", ar: "أكثر من 75%" } }
  agents: [LOVELACE, PORTER]
  data_field: digital_sales_percentage
  dimension: 9
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital
    - { lens_id: "EYE-005", relevance: "secondary" }  # Market

DM_005:
  text:
    en: "How do you currently use data in decision-making?"
    ar: "كيف تستخدم البيانات حالياً في اتخاذ القرارات؟"
  type: single_choice
  required: true
  options:
    - { value: "intuition", label: { en: "Mostly intuition / experience", ar: "في الغالب حدس / خبرة" }, score: 10 }
    - { value: "basic_reports", label: { en: "Basic reports (sales, financials)", ar: "تقارير أساسية" }, score: 30 }
    - { value: "regular_analytics", label: { en: "Regular analytics review", ar: "مراجعة تحليلات منتظمة" }, score: 55 }
    - { value: "dashboards", label: { en: "Dashboards with KPIs", ar: "لوحات معلومات مع مؤشرات" }, score: 75 }
    - { value: "advanced", label: { en: "Advanced analytics / predictive", ar: "تحليلات متقدمة / تنبؤية" }, score: 100 }
  agents: [LOVELACE, TUFTE]
  data_field: data_decision_making
  dimension: 3
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

DM_006:
  text:
    en: "Have you implemented or explored AI/Machine Learning in your business?"
    ar: "هل طبقت أو استكشفت الذكاء الاصطناعي/التعلم الآلي في عملك؟"
  type: single_choice
  required: true
  options:
    - { value: "not_considered", label: { en: "Not considered yet", ar: "لم نفكر فيه بعد" }, score: 0 }
    - { value: "exploring", label: { en: "Exploring possibilities", ar: "نستكشف الإمكانيات" }, score: 25 }
    - { value: "piloting", label: { en: "Piloting / Testing", ar: "تجريب / اختبار" }, score: 50 }
    - { value: "limited_use", label: { en: "Limited production use", ar: "استخدام إنتاجي محدود" }, score: 75 }
    - { value: "core_operations", label: { en: "Core to operations", ar: "أساسي للعمليات" }, score: 100 }
  agents: [LOVELACE]
  data_field: ai_ml_adoption
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital
    - { lens_id: "EYE-010", relevance: "primary" }  # Innovation

DM_007:
  text:
    en: "How do you manage cybersecurity?"
    ar: "كيف تدير الأمن السيبراني؟"
  type: single_choice
  required: true
  options:
    - { value: "basic", label: { en: "Basic (antivirus, passwords)", ar: "أساسي (مضاد فيروسات، كلمات مرور)" }, score: 20 }
    - { value: "intermediate", label: { en: "Firewall + regular backups", ar: "جدار حماية + نسخ احتياطية" }, score: 45 }
    - { value: "comprehensive", label: { en: "Security policies + training", ar: "سياسات أمنية + تدريب" }, score: 70 }
    - { value: "advanced", label: { en: "Security monitoring + incident response", ar: "مراقبة أمنية + استجابة للحوادث" }, score: 90 }
    - { value: "certified", label: { en: "Certified (ISO 27001)", ar: "معتمد (ISO 27001)" }, score: 100 }
  agents: [LOVELACE]
  data_field: cybersecurity_level
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital
    - { lens_id: "EYE-013", relevance: "primary" }  # Risk

DM_008:
  text:
    en: "What is your annual IT/technology budget as % of revenue?"
    ar: "ما هي ميزانيتك السنوية لتكنولوجيا المعلومات كنسبة من الإيرادات؟"
  type: single_choice
  required: false
  options:
    - { value: "under_1", label: { en: "Under 1%", ar: "أقل من 1%" } }
    - { value: "1_3", label: { en: "1-3%", ar: "1-3%" } }
    - { value: "3_5", label: { en: "3-5%", ar: "3-5%" } }
    - { value: "5_10", label: { en: "5-10%", ar: "5-10%" } }
    - { value: "over_10", label: { en: "Over 10%", ar: "أكثر من 10%" } }
    - { value: "unsure", label: { en: "Not sure", ar: "غير متأكد" } }
  agents: [LOVELACE, GRAHAM]
  data_field: it_budget_percentage
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital

DM_009:
  text:
    en: "Do you have dedicated IT staff?"
    ar: "هل لديك موظفون متخصصون في تكنولوجيا المعلومات؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "No dedicated IT staff", ar: "لا يوجد موظفون متخصصون" } }
    - { value: "shared", label: { en: "Part-time / shared role", ar: "دوام جزئي / دور مشترك" } }
    - { value: "one", label: { en: "One IT person", ar: "شخص واحد لتكنولوجيا المعلومات" } }
    - { value: "team", label: { en: "Small IT team (2-5)", ar: "فريق IT صغير (2-5)" } }
    - { value: "department", label: { en: "IT department", ar: "قسم تكنولوجيا المعلومات" } }
    - { value: "outsourced", label: { en: "Outsourced to provider", ar: "مُسند لمزود خارجي" } }
  agents: [LOVELACE, MAYO]
  data_field: it_staffing
  dimension: 7
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital
    - { lens_id: "EYE-007", relevance: "secondary" }  # Workforce

DM_010:
  text:
    en: "What are your biggest technology challenges?"
    ar: "ما هي أكبر تحدياتك التكنولوجية؟"
  type: multiple_choice
  required: true
  options:
    - { value: "budget", label: { en: "Limited budget", ar: "ميزانية محدودة" } }
    - { value: "skills", label: { en: "Lack of technical skills", ar: "نقص المهارات التقنية" } }
    - { value: "integration", label: { en: "System integration", ar: "تكامل الأنظمة" } }
    - { value: "adoption", label: { en: "User adoption / resistance", ar: "اعتماد المستخدم / المقاومة" } }
    - { value: "legacy", label: { en: "Legacy systems", ar: "أنظمة قديمة" } }
    - { value: "security", label: { en: "Security concerns", ar: "مخاوف أمنية" } }
    - { value: "vendors", label: { en: "Finding right vendors", ar: "إيجاد الموردين المناسبين" } }
    - { value: "roi", label: { en: "Unclear ROI", ar: "عائد استثمار غير واضح" } }
    - { value: "none", label: { en: "No major challenges", ar: "لا تحديات كبيرة" } }
  agents: [LOVELACE]
  data_field: technology_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  human_context_prompt:
    en: "Tell us more about these challenges"
    ar: "أخبرنا المزيد عن هذه التحديات"
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital
    - { lens_id: "EYE-CREMA", relevance: "primary" }

DM_011:
  text:
    en: "How ready is your workforce to adopt new digital tools?"
    ar: "ما مدى استعداد قوتك العاملة لتبني أدوات رقمية جديدة؟"
  type: scale
  required: true
  scale_config:
    min: 1
    max: 5
    step: 1
    labels:
      min: { en: "Very resistant to change", ar: "مقاومة كبيرة للتغيير" }
      mid: { en: "Mixed - some ready, some resistant", ar: "مختلط" }
      max: { en: "Eager to adopt new tools", ar: "متحمسون لتبني أدوات جديدة" }
  agents: [LOVELACE, MAYO]
  data_field: digital_readiness_workforce
  dimension: 7
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital
    - { lens_id: "EYE-007", relevance: "secondary" }  # Workforce

DM_012:
  text:
    en: "Do you have a digital transformation strategy or roadmap?"
    ar: "هل لديك استراتيجية أو خارطة طريق للتحول الرقمي؟"
  type: single_choice
  required: true
  options:
    - { value: "no", label: { en: "No formal strategy", ar: "لا توجد استراتيجية رسمية" }, score: 10 }
    - { value: "thinking", label: { en: "Starting to think about it", ar: "بدأنا التفكير فيها" }, score: 30 }
    - { value: "informal", label: { en: "Informal plans", ar: "خطط غير رسمية" }, score: 50 }
    - { value: "documented", label: { en: "Documented strategy", ar: "استراتيجية موثقة" }, score: 75 }
    - { value: "executing", label: { en: "Active execution with KPIs", ar: "تنفيذ نشط مع مؤشرات" }, score: 100 }
  agents: [LOVELACE, DRUCKER]
  data_field: digital_strategy
  dimension: 4
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }  # Digital

DM_013:
  text:
    en: "Is there anything specific about your technology situation we should know?"
    ar: "هل هناك أي شيء محدد حول وضعك التكنولوجي يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any ongoing projects, recent implementations, or specific needs"
    ar: "شارك أي مشاريع جارية أو تطبيقات حديثة أو احتياجات محددة"
  agents: [LOVELACE]
  data_field: human_context_digital
  confidence_impact: high
  lens_relevance: []

---

# 8. Section 5: Workforce & HR

**Section Code:** `WF`  
**Primary Agent:** Mayo (The People Person)  
**Estimated Time:** 3 minutes  
**Condition:** Show if lens requires (EYE-007, EYE-014) OR Crema active OR agent auto-selected

## 8.1 Questions

```yaml
WF_001:
  text:
    en: "How would you describe your workforce composition?"
    ar: "كيف تصف تكوين قوتك العاملة؟"
  type: single_choice
  required: true
  options:
    - { value: "mostly_unskilled", label: { en: "Mostly unskilled / entry-level", ar: "في الغالب غير ماهرة / مبتدئة" } }
    - { value: "mixed_skills", label: { en: "Mixed skill levels", ar: "مستويات مهارة مختلطة" } }
    - { value: "mostly_skilled", label: { en: "Mostly skilled / technical", ar: "في الغالب ماهرة / تقنية" } }
    - { value: "professional", label: { en: "Mostly professional / white collar", ar: "في الغالب مهنية / وظائف مكتبية" } }
    - { value: "highly_specialized", label: { en: "Highly specialized / expert", ar: "متخصصة جداً / خبراء" } }
  agents: [MAYO]
  data_field: workforce_composition
  dimension: 7
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }  # Workforce

WF_002:
  text:
    en: "What is your annual employee turnover rate?"
    ar: "ما هو معدل دوران الموظفين السنوي؟"
  type: single_choice
  required: true
  options:
    - { value: "under_5", label: { en: "Under 5%", ar: "أقل من 5%" }, score: 95 }
    - { value: "5_10", label: { en: "5-10%", ar: "5-10%" }, score: 85 }
    - { value: "10_20", label: { en: "10-20%", ar: "10-20%" }, score: 70 }
    - { value: "20_30", label: { en: "20-30%", ar: "20-30%" }, score: 50 }
    - { value: "over_30", label: { en: "Over 30%", ar: "أكثر من 30%" }, score: 25 }
    - { value: "unsure", label: { en: "Not sure", ar: "غير متأكد" }, score: 0 }
  agents: [MAYO]
  data_field: turnover_rate
  dimension: 7
  confidence_impact: medium
  quick_win_indicator: true  # High turnover = retention quick wins
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }  # Workforce
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

WF_003:
  text:
    en: "Do you have a formal HR function or department?"
    ar: "هل لديك وظيفة أو قسم موارد بشرية رسمي؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "No - owner handles HR", ar: "لا - المالك يتولى الموارد البشرية" }, score: 10 }
    - { value: "part_time", label: { en: "Part-time / shared role", ar: "دوام جزئي / دور مشترك" }, score: 30 }
    - { value: "one_person", label: { en: "One dedicated HR person", ar: "شخص واحد مخصص للموارد البشرية" }, score: 50 }
    - { value: "small_team", label: { en: "Small HR team (2-5)", ar: "فريق موارد بشرية صغير" }, score: 75 }
    - { value: "department", label: { en: "Full HR department", ar: "قسم موارد بشرية كامل" }, score: 100 }
  agents: [MAYO]
  data_field: hr_function
  dimension: 4
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }  # Workforce

WF_004:
  text:
    en: "How do you recruit new employees?"
    ar: "كيف توظف موظفين جدد؟"
  type: multiple_choice
  required: true
  options:
    - { value: "word_of_mouth", label: { en: "Word of mouth / referrals", ar: "التوصيات / الإحالات" } }
    - { value: "job_boards", label: { en: "Job boards / websites", ar: "مواقع التوظيف" } }
    - { value: "social_media", label: { en: "Social media (LinkedIn, etc.)", ar: "وسائل التواصل الاجتماعي" } }
    - { value: "agencies", label: { en: "Recruitment agencies", ar: "وكالات التوظيف" } }
    - { value: "campus", label: { en: "Campus / university recruitment", ar: "التوظيف من الجامعات" } }
    - { value: "internal", label: { en: "Internal promotions first", ar: "الترقيات الداخلية أولاً" } }
    - { value: "walk_ins", label: { en: "Walk-ins / direct applications", ar: "المتقدمون مباشرة" } }
  agents: [MAYO]
  data_field: recruitment_methods
  dimension: 7
  confidence_impact: low
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }  # Workforce

WF_005:
  text:
    en: "Do you have formal training and development programs?"
    ar: "هل لديك برامج تدريب وتطوير رسمية؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "No formal training", ar: "لا يوجد تدريب رسمي" }, score: 10 }
    - { value: "on_job", label: { en: "On-the-job only", ar: "أثناء العمل فقط" }, score: 30 }
    - { value: "occasional", label: { en: "Occasional training", ar: "تدريب عرضي" }, score: 50 }
    - { value: "regular", label: { en: "Regular training programs", ar: "برامج تدريب منتظمة" }, score: 75 }
    - { value: "comprehensive", label: { en: "Comprehensive L&D with career paths", ar: "تعلم وتطوير شامل مع مسارات وظيفية" }, score: 100 }
  agents: [MAYO]
  data_field: training_programs
  dimension: 7
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }  # Workforce
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

WF_006:
  text:
    en: "How do you manage employee performance?"
    ar: "كيف تدير أداء الموظفين؟"
  type: single_choice
  required: true
  options:
    - { value: "informal", label: { en: "Informal / ad-hoc", ar: "غير رسمي / حسب الحاجة" }, score: 20 }
    - { value: "annual", label: { en: "Annual review only", ar: "مراجعة سنوية فقط" }, score: 40 }
    - { value: "regular", label: { en: "Regular reviews (quarterly/semi-annual)", ar: "مراجعات منتظمة" }, score: 65 }
    - { value: "goals_based", label: { en: "Goals-based with metrics", ar: "قائمة على الأهداف مع مقاييس" }, score: 85 }
    - { value: "continuous", label: { en: "Continuous feedback culture", ar: "ثقافة ملاحظات مستمرة" }, score: 100 }
  agents: [MAYO]
  data_field: performance_management
  dimension: 4
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }  # Workforce

WF_007:
  text:
    en: "What are your biggest workforce challenges?"
    ar: "ما هي أكبر تحديات قوتك العاملة؟"
  type: multiple_choice
  required: true
  options:
    - { value: "finding_talent", label: { en: "Finding qualified talent", ar: "إيجاد كفاءات مؤهلة" } }
    - { value: "retention", label: { en: "Retaining good employees", ar: "الحفاظ على الموظفين الجيدين" } }
    - { value: "skills_gap", label: { en: "Skills gaps in current team", ar: "فجوات المهارات في الفريق الحالي" } }
    - { value: "productivity", label: { en: "Productivity / motivation", ar: "الإنتاجية / التحفيز" } }
    - { value: "labor_costs", label: { en: "High labor costs", ar: "تكاليف العمالة المرتفعة" } }
    - { value: "compliance", label: { en: "Labor law compliance", ar: "الامتثال لقوانين العمل" } }
    - { value: "succession", label: { en: "Succession / leadership pipeline", ar: "الخلافة / خط أنابيب القيادة" } }
    - { value: "culture", label: { en: "Company culture issues", ar: "مشاكل ثقافة الشركة" } }
    - { value: "none", label: { en: "No major challenges", ar: "لا تحديات كبيرة" } }
  agents: [MAYO]
  data_field: workforce_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  human_context_prompt:
    en: "Tell us more about these challenges"
    ar: "أخبرنا المزيد عن هذه التحديات"
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }  # Workforce
    - { lens_id: "EYE-014", relevance: "secondary" }  # Succession
    - { lens_id: "EYE-CREMA", relevance: "primary" }

WF_008:
  text:
    en: "Do you have clear organizational structure and job descriptions?"
    ar: "هل لديك هيكل تنظيمي واضح وأوصاف وظيفية؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "No - roles are flexible", ar: "لا - الأدوار مرنة" }, score: 20 }
    - { value: "basic", label: { en: "Basic structure, informal descriptions", ar: "هيكل أساسي، أوصاف غير رسمية" }, score: 40 }
    - { value: "documented", label: { en: "Documented structure + job descriptions", ar: "هيكل موثق + أوصاف وظيفية" }, score: 70 }
    - { value: "comprehensive", label: { en: "Comprehensive with career ladders", ar: "شامل مع سلالم وظيفية" }, score: 100 }
  agents: [MAYO]
  data_field: org_structure_clarity
  dimension: 4
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }  # Workforce
    - { lens_id: "EYE-014", relevance: "secondary" }  # Succession

WF_009:
  text:
    en: "How would you describe your company culture?"
    ar: "كيف تصف ثقافة شركتك؟"
  type: single_choice
  required: true
  options:
    - { value: "hierarchical", label: { en: "Traditional / Hierarchical", ar: "تقليدية / هرمية" } }
    - { value: "family", label: { en: "Family-like / Close-knit", ar: "عائلية / متماسكة" } }
    - { value: "results_oriented", label: { en: "Results-oriented / Competitive", ar: "موجهة للنتائج / تنافسية" } }
    - { value: "innovative", label: { en: "Innovative / Entrepreneurial", ar: "مبتكرة / ريادية" } }
    - { value: "collaborative", label: { en: "Collaborative / Team-focused", ar: "تعاونية / تركز على الفريق" } }
    - { value: "developing", label: { en: "Still developing culture", ar: "لا تزال تطور الثقافة" } }
  agents: [MAYO]
  data_field: company_culture
  dimension: 7
  confidence_impact: low
  allows_human_context: true
  human_context_prompt:
    en: "Describe what makes your culture unique"
    ar: "صف ما يجعل ثقافتك فريدة"
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }  # Workforce

WF_010:
  text:
    en: "Do you have a succession plan for key positions?"
    ar: "هل لديك خطة خلافة للمناصب الرئيسية؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "No succession planning", ar: "لا يوجد تخطيط للخلافة" }, score: 10 }
    - { value: "informal", label: { en: "Informal / in owner's head", ar: "غير رسمي / في ذهن المالك" }, score: 30 }
    - { value: "partial", label: { en: "Some key roles have successors", ar: "بعض الأدوار الرئيسية لها خلفاء" }, score: 60 }
    - { value: "documented", label: { en: "Documented for all key roles", ar: "موثقة لجميع الأدوار الرئيسية" }, score: 85 }
    - { value: "active", label: { en: "Active development of successors", ar: "تطوير نشط للخلفاء" }, score: 100 }
  agents: [MAYO, DRUCKER]
  data_field: succession_planning
  dimension: 4
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-014", relevance: "primary" }  # Succession
    - { lens_id: "EYE-007", relevance: "secondary" }  # Workforce

WF_011:
  text:
    en: "Is there anything else about your workforce we should know?"
    ar: "هل هناك أي شيء آخر عن قوتك العاملة يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any unique circumstances, recent changes, or context about your team"
    ar: "شارك أي ظروف فريدة أو تغييرات حديثة أو سياق حول فريقك"
  agents: [MAYO]
  data_field: human_context_workforce
  confidence_impact: high
  lens_relevance: []

---

# 9. Section 6: Market & Competition

**Section Code:** `MK`  
**Primary Agent:** Porter (The Strategist)  
**Estimated Time:** 2 minutes  
**Condition:** Show if lens requires (EYE-005, EYE-011, EYE-015) OR agent auto-selected

## 9.1 Questions

```yaml
MK_001:
  text:
    en: "Who are your primary target customers?"
    ar: "من هم عملاؤك المستهدفون الرئيسيون؟"
  type: multiple_choice
  required: true
  options:
    - { value: "b2b_large", label: { en: "Large enterprises", ar: "مؤسسات كبيرة" } }
    - { value: "b2b_sme", label: { en: "Small/Medium businesses", ar: "شركات صغيرة ومتوسطة" } }
    - { value: "b2b_government", label: { en: "Government / Public sector", ar: "حكومة / قطاع عام" } }
    - { value: "b2c_mass", label: { en: "Mass consumers", ar: "المستهلكين عامة" } }
    - { value: "b2c_premium", label: { en: "Premium / affluent consumers", ar: "مستهلكين فاخرين" } }
    - { value: "b2c_niche", label: { en: "Niche consumer segment", ar: "شريحة مستهلكين متخصصة" } }
    - { value: "distributors", label: { en: "Distributors / Resellers", ar: "موزعين / بائعين" } }
    - { value: "mixed", label: { en: "Mixed B2B and B2C", ar: "مختلط B2B و B2C" } }
  agents: [PORTER]
  data_field: target_customers
  dimension: 9
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-005", relevance: "primary" }  # Market
    - { lens_id: "EYE-011", relevance: "primary" }  # Customer Experience
    - { lens_id: "EYE-006", relevance: "secondary" }  # Brand

MK_002:
  text:
    en: "How would you describe your competitive position in your main market?"
    ar: "كيف تصف موقفك التنافسي في سوقك الرئيسي؟"
  type: single_choice
  required: true
  options:
    - { value: "market_leader", label: { en: "Market leader", ar: "قائد السوق" }, score: 100 }
    - { value: "top_3", label: { en: "Among top 3 players", ar: "ضمن أفضل 3 لاعبين" }, score: 85 }
    - { value: "strong_player", label: { en: "Strong player, but not top 3", ar: "لاعب قوي، لكن ليس ضمن أفضل 3" }, score: 70 }
    - { value: "niche_leader", label: { en: "Leader in our niche", ar: "قائد في مجالنا المتخصص" }, score: 75 }
    - { value: "emerging", label: { en: "Emerging / growing competitor", ar: "منافس ناشئ / ينمو" }, score: 50 }
    - { value: "small_player", label: { en: "Small player in fragmented market", ar: "لاعب صغير في سوق مجزأ" }, score: 30 }
    - { value: "new_entrant", label: { en: "New entrant", ar: "داخل جديد" }, score: 20 }
  agents: [PORTER]
  data_field: competitive_position
  dimension: 9
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-005", relevance: "primary" }  # Market
    - { lens_id: "EYE-002", relevance: "secondary" }  # Investment

MK_003:
  text:
    en: "How many direct competitors do you have?"
    ar: "كم عدد المنافسين المباشرين لديك؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "None - we're unique", ar: "لا يوجد - نحن فريدون" } }
    - { value: "1_3", label: { en: "1-3 competitors", ar: "1-3 منافسين" } }
    - { value: "4_10", label: { en: "4-10 competitors", ar: "4-10 منافسين" } }
    - { value: "many", label: { en: "Many (fragmented market)", ar: "كثير (سوق مجزأ)" } }
    - { value: "unsure", label: { en: "Not sure", ar: "غير متأكد" } }
  agents: [PORTER]
  data_field: competitor_count
  dimension: 9
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-005", relevance: "primary" }  # Market

MK_004:
  text:
    en: "What is your primary competitive advantage?"
    ar: "ما هي ميزتك التنافسية الرئيسية؟"
  type: multiple_choice
  required: true
  options:
    - { value: "price", label: { en: "Lower price / cost leader", ar: "سعر أقل / قائد التكلفة" } }
    - { value: "quality", label: { en: "Superior quality", ar: "جودة متفوقة" } }
    - { value: "service", label: { en: "Better customer service", ar: "خدمة عملاء أفضل" } }
    - { value: "speed", label: { en: "Faster delivery / turnaround", ar: "تسليم / استجابة أسرع" } }
    - { value: "innovation", label: { en: "Innovation / unique products", ar: "ابتكار / منتجات فريدة" } }
    - { value: "relationships", label: { en: "Strong customer relationships", ar: "علاقات قوية مع العملاء" } }
    - { value: "location", label: { en: "Geographic location / access", ar: "الموقع الجغرافي / الوصول" } }
    - { value: "brand", label: { en: "Brand / reputation", ar: "العلامة التجارية / السمعة" } }
    - { value: "specialized", label: { en: "Specialized expertise", ar: "خبرة متخصصة" } }
    - { value: "unclear", label: { en: "Not clearly defined", ar: "غير محددة بوضوح" } }
  agents: [PORTER, LANDOR]
  data_field: competitive_advantage
  dimension: 9
  confidence_impact: high
  allows_human_context: true
  human_context_prompt:
    en: "Tell us more about what makes you different"
    ar: "أخبرنا المزيد عما يميزك"
  lens_relevance:
    - { lens_id: "EYE-005", relevance: "primary" }  # Market
    - { lens_id: "EYE-006", relevance: "primary" }  # Brand

MK_005:
  text:
    en: "What is your estimated market share?"
    ar: "ما هي حصتك السوقية المقدرة؟"
  type: single_choice
  required: false
  options:
    - { value: "under_1", label: { en: "Under 1%", ar: "أقل من 1%" } }
    - { value: "1_5", label: { en: "1-5%", ar: "1-5%" } }
    - { value: "5_10", label: { en: "5-10%", ar: "5-10%" } }
    - { value: "10_25", label: { en: "10-25%", ar: "10-25%" } }
    - { value: "25_50", label: { en: "25-50%", ar: "25-50%" } }
    - { value: "over_50", label: { en: "Over 50%", ar: "أكثر من 50%" } }
    - { value: "unsure", label: { en: "Not sure", ar: "غير متأكد" } }
  agents: [PORTER]
  data_field: market_share
  dimension: 9
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-005", relevance: "primary" }  # Market

MK_006:
  text:
    en: "How do you primarily acquire new customers?"
    ar: "كيف تستحوذ بشكل رئيسي على عملاء جدد؟"
  type: multiple_choice
  required: true
  options:
    - { value: "referrals", label: { en: "Referrals / Word of mouth", ar: "إحالات / كلام شفهي" } }
    - { value: "direct_sales", label: { en: "Direct sales team", ar: "فريق مبيعات مباشر" } }
    - { value: "digital_marketing", label: { en: "Digital marketing", ar: "تسويق رقمي" } }
    - { value: "social_media", label: { en: "Social media", ar: "وسائل التواصل الاجتماعي" } }
    - { value: "trade_shows", label: { en: "Trade shows / events", ar: "معارض / فعاليات" } }
    - { value: "partnerships", label: { en: "Partnerships / distributors", ar: "شراكات / موزعون" } }
    - { value: "tenders", label: { en: "Tenders / RFPs", ar: "مناقصات / طلبات عروض" } }
    - { value: "inbound", label: { en: "Inbound / customers find us", ar: "وارد / العملاء يجدوننا" } }
  agents: [PORTER, LANDOR]
  data_field: customer_acquisition
  dimension: 9
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-005", relevance: "primary" }  # Market
    - { lens_id: "EYE-006", relevance: "secondary" }  # Brand

MK_007:
  text:
    en: "How satisfied are your customers generally?"
    ar: "ما مدى رضا عملائك بشكل عام؟"
  type: single_choice
  required: true
  options:
    - { value: "very_high", label: { en: "Very high - strong loyalty", ar: "عالي جداً - ولاء قوي" }, score: 95 }
    - { value: "high", label: { en: "High - repeat customers", ar: "عالي - عملاء متكررون" }, score: 80 }
    - { value: "moderate", label: { en: "Moderate - some complaints", ar: "معتدل - بعض الشكاوى" }, score: 60 }
    - { value: "mixed", label: { en: "Mixed - varies by segment", ar: "مختلط - يختلف حسب الشريحة" }, score: 50 }
    - { value: "low", label: { en: "Lower than we'd like", ar: "أقل مما نريد" }, score: 35 }
    - { value: "dont_measure", label: { en: "We don't measure this", ar: "لا نقيس هذا" }, score: 0 }
  agents: [PORTER, DEMING]
  data_field: customer_satisfaction
  dimension: 9
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-011", relevance: "primary" }  # Customer Experience
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

MK_008:
  text:
    en: "Do you track customer metrics like NPS, retention rate, or lifetime value?"
    ar: "هل تتتبع مقاييس العملاء مثل NPS أو معدل الاحتفاظ أو القيمة الدائمة؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "No - don't track these", ar: "لا - لا نتتبع هذه" }, score: 10 }
    - { value: "basic", label: { en: "Basic tracking (sales only)", ar: "تتبع أساسي (مبيعات فقط)" }, score: 30 }
    - { value: "some", label: { en: "Some metrics tracked", ar: "بعض المقاييس متتبعة" }, score: 55 }
    - { value: "comprehensive", label: { en: "Comprehensive tracking", ar: "تتبع شامل" }, score: 80 }
    - { value: "advanced", label: { en: "Advanced with predictive analytics", ar: "متقدم مع تحليلات تنبؤية" }, score: 100 }
  agents: [PORTER, LOVELACE]
  data_field: customer_metrics_tracking
  dimension: 3
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-011", relevance: "primary" }  # Customer Experience
    - { lens_id: "EYE-003", relevance: "secondary" }  # Digital

MK_009:
  text:
    en: "What are your main market challenges?"
    ar: "ما هي تحديات السوق الرئيسية لديك؟"
  type: multiple_choice
  required: true
  options:
    - { value: "competition", label: { en: "Intense competition", ar: "منافسة شديدة" } }
    - { value: "price_pressure", label: { en: "Price pressure", ar: "ضغط الأسعار" } }
    - { value: "awareness", label: { en: "Low brand awareness", ar: "وعي منخفض بالعلامة التجارية" } }
    - { value: "reach", label: { en: "Reaching new customers", ar: "الوصول إلى عملاء جدد" } }
    - { value: "market_shrinking", label: { en: "Shrinking market", ar: "سوق متقلص" } }
    - { value: "regulations", label: { en: "Regulatory challenges", ar: "تحديات تنظيمية" } }
    - { value: "changing_needs", label: { en: "Changing customer needs", ar: "احتياجات العملاء المتغيرة" } }
    - { value: "substitutes", label: { en: "Substitute products/services", ar: "منتجات / خدمات بديلة" } }
    - { value: "none", label: { en: "No major challenges", ar: "لا تحديات كبيرة" } }
  agents: [PORTER]
  data_field: market_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  human_context_prompt:
    en: "Tell us more about these challenges"
    ar: "أخبرنا المزيد عن هذه التحديات"
  lens_relevance:
    - { lens_id: "EYE-005", relevance: "primary" }  # Market
    - { lens_id: "EYE-CREMA", relevance: "primary" }

MK_010:
  text:
    en: "Is there anything else about your market or customers we should know?"
    ar: "هل هناك أي شيء آخر عن سوقك أو عملائك يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any market trends, customer insights, or competitive dynamics"
    ar: "شارك أي اتجاهات سوقية أو رؤى عملاء أو ديناميكيات تنافسية"
  agents: [PORTER]
  data_field: human_context_market
  confidence_impact: high
  lens_relevance: []

---

# 10. Section 7: Supply Chain

**Section Code:** `SC`  
**Primary Agent:** Ohno (The Flow Master)  
**Estimated Time:** 3 minutes  
**Condition:** Show if lens requires (EYE-008) OR manufacturing/trading business model

## 10.1 Questions

```yaml
SC_001:
  text:
    en: "How many key suppliers do you work with?"
    ar: "كم عدد الموردين الرئيسيين الذين تعمل معهم؟"
  type: single_choice
  required: true
  options:
    - { value: "1_5", label: { en: "1-5 suppliers", ar: "1-5 موردين" } }
    - { value: "6_20", label: { en: "6-20 suppliers", ar: "6-20 مورد" } }
    - { value: "21_50", label: { en: "21-50 suppliers", ar: "21-50 مورد" } }
    - { value: "50_100", label: { en: "50-100 suppliers", ar: "50-100 مورد" } }
    - { value: "over_100", label: { en: "Over 100 suppliers", ar: "أكثر من 100 مورد" } }
  agents: [OHNO]
  data_field: supplier_count
  dimension: 8
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain

SC_002:
  text:
    en: "What percentage of your supplies come from your top 3 suppliers?"
    ar: "ما نسبة الإمدادات التي تأتي من أكبر 3 موردين؟"
  type: single_choice
  required: true
  options:
    - { value: "under_30", label: { en: "Under 30%", ar: "أقل من 30%" }, score: 85 }
    - { value: "30_50", label: { en: "30-50%", ar: "30-50%" }, score: 70 }
    - { value: "50_70", label: { en: "50-70%", ar: "50-70%" }, score: 50 }
    - { value: "over_70", label: { en: "Over 70%", ar: "أكثر من 70%" }, score: 30 }
  agents: [OHNO]
  data_field: supplier_concentration
  dimension: 8
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain
    - { lens_id: "EYE-013", relevance: "secondary" }  # Risk

SC_003:
  text:
    en: "Where do you primarily source your materials or inputs?"
    ar: "من أين تحصل بشكل رئيسي على موادك أو مدخلاتك؟"
  type: multiple_choice
  required: true
  options:
    - { value: "local_same_city", label: { en: "Local (same city/region)", ar: "محلي (نفس المدينة/المنطقة)" } }
    - { value: "domestic", label: { en: "Domestic (same country)", ar: "محلي (نفس الدولة)" } }
    - { value: "mena_regional", label: { en: "Regional (MENA)", ar: "إقليمي (الشرق الأوسط)" } }
    - { value: "europe", label: { en: "Europe", ar: "أوروبا" } }
    - { value: "china_asia", label: { en: "China / Asia", ar: "الصين / آسيا" } }
    - { value: "us_americas", label: { en: "US / Americas", ar: "أمريكا" } }
    - { value: "other", label: { en: "Other regions", ar: "مناطق أخرى" } }
  agents: [OHNO, RICARDO]
  data_field: sourcing_geography
  dimension: 8
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain
    - { lens_id: "EYE-001", relevance: "secondary" }  # Export - supply chain for export

SC_004:
  text:
    en: "How reliable are your suppliers in terms of on-time delivery?"
    ar: "ما مدى موثوقية مورديك من حيث التسليم في الوقت المحدد؟"
  type: single_choice
  required: true
  options:
    - { value: "very_reliable", label: { en: "Very reliable (95%+ on time)", ar: "موثوق جداً (95%+ في الوقت)" }, score: 95 }
    - { value: "reliable", label: { en: "Reliable (85-95% on time)", ar: "موثوق (85-95% في الوقت)" }, score: 90 }
    - { value: "moderate", label: { en: "Moderate (70-85% on time)", ar: "معتدل (70-85% في الوقت)" }, score: 77 }
    - { value: "unreliable", label: { en: "Often delayed", ar: "متأخر في كثير من الأحيان" }, score: 50 }
    - { value: "very_unreliable", label: { en: "Very unreliable", ar: "غير موثوق جداً" }, score: 30 }
  agents: [OHNO]
  data_field: supplier_reliability
  dimension: 8
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

SC_005:
  text:
    en: "Do you have formal supplier evaluation and qualification processes?"
    ar: "هل لديك عمليات رسمية لتقييم وتأهيل الموردين؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "No formal process", ar: "لا توجد عملية رسمية" }, score: 10 }
    - { value: "basic", label: { en: "Basic price/quality check", ar: "فحص أساسي للسعر/الجودة" }, score: 35 }
    - { value: "documented", label: { en: "Documented evaluation criteria", ar: "معايير تقييم موثقة" }, score: 60 }
    - { value: "comprehensive", label: { en: "Comprehensive with audits", ar: "شامل مع تدقيقات" }, score: 85 }
    - { value: "certified", label: { en: "Certified supplier program", ar: "برنامج موردين معتمد" }, score: 100 }
  agents: [OHNO, DEMING]
  data_field: supplier_evaluation
  dimension: 4
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain

SC_006:
  text:
    en: "How do you manage logistics and distribution?"
    ar: "كيف تدير اللوجستيات والتوزيع؟"
  type: single_choice
  required: true
  options:
    - { value: "in_house", label: { en: "In-house fleet", ar: "أسطول داخلي" } }
    - { value: "3pl", label: { en: "Third-party logistics (3PL)", ar: "لوجستيات طرف ثالث" } }
    - { value: "courier", label: { en: "Courier/shipping services", ar: "خدمات بريد سريع/شحن" } }
    - { value: "customer_pickup", label: { en: "Customer pickup", ar: "استلام العميل" } }
    - { value: "mixed", label: { en: "Mixed approach", ar: "نهج مختلط" } }
    - { value: "na", label: { en: "Not applicable (services)", ar: "غير قابل للتطبيق (خدمات)" } }
  agents: [OHNO]
  data_field: logistics_model
  dimension: 8
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain

SC_007:
  text:
    en: "What is your typical lead time from suppliers?"
    ar: "ما هو وقت التسليم النموذجي من الموردين؟"
  type: single_choice
  required: true
  options:
    - { value: "same_day", label: { en: "Same day", ar: "نفس اليوم" } }
    - { value: "1_3_days", label: { en: "1-3 days", ar: "1-3 أيام" } }
    - { value: "1_2_weeks", label: { en: "1-2 weeks", ar: "1-2 أسبوع" } }
    - { value: "2_4_weeks", label: { en: "2-4 weeks", ar: "2-4 أسابيع" } }
    - { value: "1_3_months", label: { en: "1-3 months", ar: "1-3 أشهر" } }
    - { value: "over_3_months", label: { en: "Over 3 months", ar: "أكثر من 3 أشهر" } }
    - { value: "varies", label: { en: "Varies significantly", ar: "يختلف بشكل كبير" } }
  agents: [OHNO]
  data_field: supplier_lead_time
  dimension: 8
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain

SC_008:
  text:
    en: "Have you experienced significant supply chain disruptions in the past 2 years?"
    ar: "هل تعرضت لاضطرابات كبيرة في سلسلة التوريد في العامين الماضيين؟"
  type: single_choice
  required: true
  options:
    - value: "none"
      label: { en: "No significant disruptions", ar: "لا اضطرابات كبيرة" }
    - value: "minor"
      label: { en: "Minor disruptions", ar: "اضطرابات طفيفة" }
    - value: "moderate"
      label: { en: "Moderate - caused some delays", ar: "معتدلة - تسببت في بعض التأخيرات" }
      triggers_followup: [SC_008a]
    - value: "significant"
      label: { en: "Significant - major impact on operations", ar: "كبيرة - تأثير كبير على العمليات" }
      triggers_followup: [SC_008a]
  agents: [OHNO]
  data_field: supply_chain_disruptions
  dimension: 8
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain
    - { lens_id: "EYE-013", relevance: "primary" }  # Risk

SC_008a:
  text:
    en: "What caused these supply chain disruptions?"
    ar: "ما الذي تسبب في هذه الاضطرابات؟"
  type: multiple_choice
  required: false
  conditional:
    - { question_id: "SC_008", operator: "in", value: ["moderate", "significant"] }
  options:
    - { value: "covid", label: { en: "COVID-related", ar: "متعلقة بكوفيد" } }
    - { value: "shipping", label: { en: "Shipping/logistics issues", ar: "مشاكل الشحن/اللوجستيات" } }
    - { value: "supplier_failure", label: { en: "Supplier failure/closure", ar: "فشل/إغلاق المورد" } }
    - { value: "geopolitical", label: { en: "Geopolitical/trade issues", ar: "مشاكل جيوسياسية/تجارية" } }
    - { value: "currency", label: { en: "Currency/payment issues", ar: "مشاكل العملة/الدفع" } }
    - { value: "quality", label: { en: "Quality problems", ar: "مشاكل الجودة" } }
    - { value: "demand_surge", label: { en: "Unexpected demand surge", ar: "ارتفاع مفاجئ في الطلب" } }
    - { value: "other", label: { en: "Other", ar: "أخرى" } }
  agents: [OHNO]
  data_field: disruption_causes
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain

SC_009:
  text:
    en: "Do you have backup suppliers for critical materials?"
    ar: "هل لديك موردون بديلون للمواد الحرجة؟"
  type: single_choice
  required: true
  options:
    - { value: "no", label: { en: "No backup suppliers", ar: "لا يوجد موردون بديلون" }, score: 20 }
    - { value: "some", label: { en: "For some materials", ar: "لبعض المواد" }, score: 55 }
    - { value: "most", label: { en: "For most critical materials", ar: "لمعظم المواد الحرجة" }, score: 80 }
    - { value: "all", label: { en: "For all critical materials", ar: "لجميع المواد الحرجة" }, score: 100 }
  agents: [OHNO]
  data_field: backup_suppliers
  dimension: 8
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain
    - { lens_id: "EYE-013", relevance: "primary" }  # Risk

SC_010:
  text:
    en: "How do you share information with suppliers?"
    ar: "كيف تشارك المعلومات مع الموردين؟"
  type: single_choice
  required: true
  options:
    - { value: "phone_email", label: { en: "Phone/email only", ar: "هاتف/بريد إلكتروني فقط" }, score: 20 }
    - { value: "shared_docs", label: { en: "Shared documents/spreadsheets", ar: "مستندات/جداول مشتركة" }, score: 40 }
    - { value: "portal", label: { en: "Supplier portal", ar: "بوابة الموردين" }, score: 70 }
    - { value: "integrated", label: { en: "Integrated systems (EDI, API)", ar: "أنظمة متكاملة" }, score: 100 }
  agents: [OHNO, LOVELACE]
  data_field: supplier_communication
  dimension: 3
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain
    - { lens_id: "EYE-003", relevance: "secondary" }  # Digital

SC_011:
  text:
    en: "What are your biggest supply chain challenges?"
    ar: "ما هي أكبر تحديات سلسلة التوريد لديك؟"
  type: multiple_choice
  required: true
  options:
    - { value: "cost", label: { en: "Rising costs", ar: "ارتفاع التكاليف" } }
    - { value: "reliability", label: { en: "Supplier reliability", ar: "موثوقية الموردين" } }
    - { value: "quality", label: { en: "Quality consistency", ar: "اتساق الجودة" } }
    - { value: "lead_times", label: { en: "Long lead times", ar: "أوقات تسليم طويلة" } }
    - { value: "visibility", label: { en: "Lack of visibility", ar: "نقص الرؤية" } }
    - { value: "capacity", label: { en: "Supplier capacity", ar: "طاقة الموردين" } }
    - { value: "currency", label: { en: "Currency fluctuations", ar: "تقلبات العملة" } }
    - { value: "compliance", label: { en: "Compliance requirements", ar: "متطلبات الامتثال" } }
    - { value: "none", label: { en: "No major challenges", ar: "لا تحديات كبيرة" } }
  agents: [OHNO]
  data_field: supply_chain_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  human_context_prompt:
    en: "Tell us more about these challenges"
    ar: "أخبرنا المزيد عن هذه التحديات"
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }  # Supply Chain
    - { lens_id: "EYE-CREMA", relevance: "primary" }

SC_012:
  text:
    en: "Is there anything else about your supply chain we should know?"
    ar: "هل هناك أي شيء آخر عن سلسلة التوريد يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any unique circumstances, ongoing initiatives, or specific concerns"
    ar: "شارك أي ظروف فريدة أو مبادرات جارية أو مخاوف محددة"
  agents: [OHNO]
  data_field: human_context_supply_chain
  confidence_impact: high
  lens_relevance: []spreadsheets", label: { en: "Spreadsheets (Excel, Google Sheets)", ar: "جداول بيانات" }, score: 30 }
    - { value: "paper", label: { en: "Paper-based / Manual", ar: "ورقي / يدوي" }, score: 10 }
  agents: [GRAHAM, LOVELACE]
  data_field: accounting_system
  dimension: 5
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }
    - { lens_id: "EYE-002", relevance: "secondary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

FH_014:
  text:
    en: "What is your biggest financial challenge right now?"
    ar: "ما هو أكبر تحدٍ مالي تواجهه الآن؟"
  type: multiple_choice
  required: true
  options:
    - { value: "cash_flow", label: { en: "Cash flow management", ar: "إدارة التدفق النقدي" } }
    - { value: "profitability", label: { en: "Improving profitability", ar: "تحسين الربحية" } }
    - { value: "access_capital", label: { en: "Access to capital / funding", ar: "الوصول إلى رأس المال / التمويل" } }
    - { value: "cost_control", label: { en: "Controlling costs", ar: "التحكم في التكاليف" } }
    - { value: "pricing", label: { en: "Pricing strategy", ar: "استراتيجية التسعير" } }
    - { value: "collections", label: { en: "Collecting receivables", ar: "تحصيل المستحقات" } }
    - { value: "currency", label: { en: "Currency fluctuations", ar: "تقلبات العملة" } }
    - { value: "tax", label: { en: "Tax optimization", ar: "تحسين الضرائب" } }
    - { value: "none", label: { en: "No major challenges", ar: "لا توجد تحديات كبيرة" } }
  agents: [GRAHAM]
  data_field: financial_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  lens_relevance:
    - { lens_id: "EYE-012", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "primary" }

FH_015:
  text:
    en: "What percentage of your costs are fixed vs variable?"
    ar: "ما نسبة تكاليفك الثابتة مقابل المتغيرة؟"
  type: slider
  required: true
  scale_config:
    min: 0
    max: 100
    step: 10
    labels:
      min: { en: "All Variable (0% Fixed)", ar: "كلها متغيرة" }
      mid: { en: "50/50", ar: "50/50" }
      max: { en: "All Fixed (100% Fixed)", ar: "كلها ثابتة" }
  agents: [GRAHAM, OHNO]
  data_field: fixed_cost_ratio
  dimension: 2
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-012", relevance: "primary" }
    - { lens_id: "EYE-004", relevance: "secondary" }

FH_016:
  text:
    en: "Do you have a formal annual budget?"
    ar: "هل لديك ميزانية سنوية رسمية؟"
  type: single_choice
  required: true
  options:
    - { value: "detailed", label: { en: "Yes, detailed with monthly tracking", ar: "نعم، مفصلة مع متابعة شهرية" }, score: 100 }
    - { value: "basic", label: { en: "Yes, basic annual budget", ar: "نعم، ميزانية سنوية أساسية" }, score: 70 }
    - { value: "informal", label: { en: "Informal / In my head", ar: "غير رسمية / في ذهني" }, score: 30 }
    - { value: "none", label: { en: "No budget", ar: "لا توجد ميزانية" }, score: 10 }
  agents: [GRAHAM]
  data_field: budgeting_practice
  dimension: 4
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "secondary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

FH_017:
  text:
    en: "How often do you review financial performance?"
    ar: "كم مرة تراجع الأداء المالي؟"
  type: single_choice
  required: true
  options:
    - { value: "real_time", label: { en: "Real-time / Dashboard", ar: "فوري / لوحة معلومات" }, score: 100 }
    - { value: "weekly", label: { en: "Weekly", ar: "أسبوعياً" }, score: 90 }
    - { value: "monthly", label: { en: "Monthly", ar: "شهرياً" }, score: 70 }
    - { value: "quarterly", label: { en: "Quarterly", ar: "ربع سنوي" }, score: 50 }
    - { value: "annually", label: { en: "Annually", ar: "سنوياً" }, score: 30 }
    - { value: "rarely", label: { en: "Rarely / When needed", ar: "نادراً / عند الحاجة" }, score: 10 }
  agents: [GRAHAM, DEMING]
  data_field: financial_review_frequency
  dimension: 4
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "secondary" }
    - { lens_id: "EYE-002", relevance: "secondary" }

FH_018:
  text:
    en: "What financial KPIs do you currently track?"
    ar: "ما هي مؤشرات الأداء المالية التي تتابعها حالياً؟"
  type: multiple_choice
  required: true
  options:
    - { value: "revenue", label: { en: "Revenue / Sales", ar: "الإيرادات / المبيعات" } }
    - { value: "gross_margin", label: { en: "Gross margin", ar: "هامش الربح الإجمالي" } }
    - { value: "net_profit", label: { en: "Net profit", ar: "صافي الربح" } }
    - { value: "cash_flow", label: { en: "Cash flow", ar: "التدفق النقدي" } }
    - { value: "ar_aging", label: { en: "Accounts receivable aging", ar: "أعمار المستحقات" } }
    - { value: "inventory_turnover", label: { en: "Inventory turnover", ar: "معدل دوران المخزون" } }
    - { value: "unit_economics", label: { en: "Unit economics / CAC / LTV", ar: "اقتصاديات الوحدة" } }
    - { value: "burn_rate", label: { en: "Burn rate / Runway", ar: "معدل الحرق / المدة" } }
    - { value: "none", label: { en: "We don't track KPIs formally", ar: "لا نتابع مؤشرات بشكل رسمي" } }
  agents: [GRAHAM, DEMING]
  data_field: financial_kpis_tracked
  dimension: 4
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "primary" }
    - { lens_id: "EYE-003", relevance: "secondary" }

FH_019:
  text:
    en: "What are your top 3 cost categories as a percentage of revenue?"
    ar: "ما هي أكبر 3 فئات تكلفة كنسبة مئوية من الإيرادات؟"
  type: matrix
  required: true
  matrix_config:
    rows:
      - { value: "raw_materials", label: { en: "Raw materials / COGS", ar: "المواد الخام / تكلفة البضائع" } }
      - { value: "labor", label: { en: "Labor / Salaries", ar: "العمالة / الرواتب" } }
      - { value: "rent", label: { en: "Rent / Facilities", ar: "الإيجار / المرافق" } }
      - { value: "utilities", label: { en: "Utilities (energy, water)", ar: "المرافق (طاقة، مياه)" } }
      - { value: "marketing", label: { en: "Marketing / Sales", ar: "التسويق / المبيعات" } }
      - { value: "logistics", label: { en: "Logistics / Shipping", ar: "اللوجستيات / الشحن" } }
      - { value: "finance_costs", label: { en: "Finance costs (interest)", ar: "تكاليف التمويل (الفوائد)" } }
      - { value: "other", label: { en: "Other", ar: "أخرى" } }
    columns:
      - { value: "percentage", type: "percentage", label: { en: "% of Revenue", ar: "% من الإيرادات" } }
  agents: [GRAHAM, OHNO]
  data_field: cost_breakdown
  dimension: 2
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-012", relevance: "primary" }
    - { lens_id: "EYE-004", relevance: "secondary" }

FH_020:
  text:
    en: "Is there anything about your financial situation we should understand better?"
    ar: "هل هناك شيء عن وضعك المالي يجب أن نفهمه بشكل أفضل؟"
  type: human_context
  required: false
  description:
    en: "Share any context that might not show in the numbers - recent changes, unusual circumstances, or plans."
    ar: "شارك أي سياق قد لا يظهر في الأرقام - تغييرات حديثة، ظروف غير عادية، أو خطط."
  agents: [GRAHAM]
  data_field: human_context_financial
  confidence_impact: high
  lens_relevance: []
```

---

# 6. Section 3: Operations & Production

**Section Code:** `OP`  
**Primary Agent:** Ohno (The Sensei)  
**Estimated Time:** 4 minutes  
**Condition:** Always shown (Core)

## 6.1 Questions

```yaml
OP_001:
  text:
    en: "What type of business model best describes your company?"
    ar: "ما نوع نموذج الأعمال الذي يصف شركتك بشكل أفضل؟"
  type: single_choice
  required: true
  options:
    - value: "manufacturing"
      label: { en: "Manufacturing / Production", ar: "التصنيع / الإنتاج" }
      triggers_followup: [OP_002, OP_003, OP_008, OP_009, OP_010]
    - value: "trading"
      label: { en: "Trading / Distribution", ar: "التجارة / التوزيع" }
    - value: "services"
      label: { en: "Services", ar: "الخدمات" }
    - value: "retail"
      label: { en: "Retail", ar: "التجزئة" }
    - value: "hybrid"
      label: { en: "Hybrid (multiple models)", ar: "مختلط (نماذج متعددة)" }
      triggers_followup: [OP_002, OP_003]
  agents: [OHNO, DRUCKER]
  data_field: business_model_type
  dimension: 1
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }

OP_002:
  text:
    en: "What is your current production capacity utilization?"
    ar: "ما هو معدل استخدام طاقتك الإنتاجية الحالية؟"
  type: single_choice
  required: false
  conditional:
    - { question_id: "OP_001", operator: "in", value: ["manufacturing", "hybrid"] }
  options:
    - { value: "under_50", label: { en: "Under 50%", ar: "أقل من 50%" }, score: 25 }
    - { value: "50_70", label: { en: "50-70%", ar: "50-70%" }, score: 60 }
    - { value: "70_85", label: { en: "70-85%", ar: "70-85%" }, score: 77 }
    - { value: "85_95", label: { en: "85-95% (optimal)", ar: "85-95% (مثالي)" }, score: 90 }
    - { value: "over_95", label: { en: "Over 95% (at capacity)", ar: "أكثر من 95% (بأقصى طاقة)" }, score: 85 }
    - { value: "unsure", label: { en: "Not sure", ar: "غير متأكد" }, score: 0 }
  agents: [OHNO, DEMING]
  data_field: capacity_utilization
  dimension: 3
  confidence_impact: high
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }
    - { lens_id: "EYE-012", relevance: "secondary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

OP_003:
  text:
    en: "How would you rate the age and condition of your key equipment?"
    ar: "كيف تقيّم عمر وحالة معداتك الرئيسية؟"
  type: single_choice
  required: false
  conditional:
    - { question_id: "OP_001", operator: "in", value: ["manufacturing", "hybrid"] }
  options:
    - { value: "modern", label: { en: "Modern and well-maintained (< 5 years)", ar: "حديثة وبحالة جيدة (< 5 سنوات)" }, score: 90 }
    - { value: "good", label: { en: "Good condition (5-10 years)", ar: "حالة جيدة (5-10 سنوات)" }, score: 70 }
    - { value: "aging", label: { en: "Aging but functional (10-15 years)", ar: "قديمة ولكن تعمل (10-15 سنة)" }, score: 50 }
    - { value: "needs_upgrade", label: { en: "Needs significant upgrade (> 15 years)", ar: "تحتاج ترقية كبيرة (> 15 سنة)" }, score: 30 }
    - { value: "mixed", label: { en: "Mixed - some new, some old", ar: "مختلطة - بعضها جديد وبعضها قديم" }, score: 50 }
  agents: [OHNO]
  data_field: equipment_condition
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }
    - { lens_id: "EYE-003", relevance: "secondary" }

OP_004:
  text:
    en: "How do you currently manage inventory?"
    ar: "كيف تدير المخزون حالياً؟"
  type: single_choice
  required: true
  options:
    - { value: "erp", label: { en: "ERP/Inventory management system", ar: "نظام ERP / إدارة المخزون" }, score: 90 }
    - { value: "software", label: { en: "Dedicated inventory software", ar: "برنامج مخزون مخصص" }, score: 70 }
    - { value: "spreadsheet", label: { en: "Spreadsheets", ar: "جداول بيانات" }, score: 40 }
    - { value: "manual", label: { en: "Manual / Paper-based", ar: "يدوي / ورقي" }, score: 20 }
    - { value: "na", label: { en: "N/A - Service business", ar: "غير منطبق - أعمال خدمية" }, score: 0 }
  agents: [OHNO, LOVELACE]
  data_field: inventory_management
  dimension: 5
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }
    - { lens_id: "EYE-004", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

OP_005:
  text:
    en: "Do you have documented standard operating procedures (SOPs)?"
    ar: "هل لديك إجراءات تشغيل موحدة موثقة (SOPs)؟"
  type: single_choice
  required: true
  options:
    - { value: "comprehensive", label: { en: "Yes, comprehensive and regularly updated", ar: "نعم، شاملة ومحدثة بانتظام" }, score: 100 }
    - { value: "basic", label: { en: "Yes, basic SOPs for key processes", ar: "نعم، إجراءات أساسية للعمليات الرئيسية" }, score: 70 }
    - { value: "partial", label: { en: "Partially documented", ar: "موثقة جزئياً" }, score: 40 }
    - { value: "informal", label: { en: "No, processes are informal / in people's heads", ar: "لا، العمليات غير رسمية / في أذهان الناس" }, score: 20 }
  agents: [OHNO, DEMING]
  data_field: sop_documentation
  dimension: 3
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }
    - { lens_id: "EYE-007", relevance: "secondary" }
    - { lens_id: "EYE-CREMA", relevance: "primary" }

OP_006:
  text:
    en: "How do you measure and track quality?"
    ar: "كيف تقيس وتتابع الجودة؟"
  type: multiple_choice
  required: true
  options:
    - { value: "qms", label: { en: "Formal QMS (ISO 9001 or equivalent)", ar: "نظام إدارة جودة رسمي" } }
    - { value: "inspection", label: { en: "Regular inspection points", ar: "نقاط فحص منتظمة" } }
    - { value: "defect_tracking", label: { en: "Defect tracking system", ar: "نظام تتبع العيوب" } }
    - { value: "customer_feedback", label: { en: "Customer feedback / complaints", ar: "ملاحظات العملاء / الشكاوى" } }
    - { value: "statistical", label: { en: "Statistical process control", ar: "التحكم الإحصائي بالعمليات" } }
    - { value: "informal", label: { en: "Informal / Ad-hoc", ar: "غير رسمي / حسب الحاجة" } }
    - { value: "none", label: { en: "No formal quality tracking", ar: "لا يوجد تتبع جودة رسمي" } }
  agents: [OHNO, DEMING]
  data_field: quality_management
  dimension: 3
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }
    - { lens_id: "EYE-001", relevance: "secondary" }

OP_007:
  text:
    en: "What is your on-time delivery rate?"
    ar: "ما هو معدل التسليم في الوقت المحدد؟"
  type: single_choice
  required: true
  options:
    - { value: "excellent", label: { en: "> 98%", ar: "> 98%" }, score: 98 }
    - { value: "very_good", label: { en: "95-98%", ar: "95-98%" }, score: 96 }
    - { value: "good", label: { en: "90-95%", ar: "90-95%" }, score: 92 }
    - { value: "fair", label: { en: "80-90%", ar: "80-90%" }, score: 85 }
    - { value: "needs_work", label: { en: "70-80%", ar: "70-80%" }, score: 75 }
    - { value: "poor", label: { en: "< 70%", ar: "< 70%" }, score: 60 }
    - { value: "unsure", label: { en: "Not tracked", ar: "غير متتبع" }, score: 0 }
  agents: [OHNO, DEMING]
  data_field: on_time_delivery
  dimension: 6
  confidence_impact: high
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }
    - { lens_id: "EYE-011", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

OP_008:
  text:
    en: "What is your approximate defect or rework rate?"
    ar: "ما هو معدل العيوب أو إعادة العمل التقريبي لديك؟"
  type: single_choice
  required: false
  conditional:
    - { question_id: "OP_001", operator: "in", value: ["manufacturing", "hybrid"] }
  options:
    - { value: "excellent", label: { en: "< 1% (excellent)", ar: "< 1% (ممتاز)" }, score: 95 }
    - { value: "good", label: { en: "1-3% (good)", ar: "1-3% (جيد)" }, score: 80 }
    - { value: "moderate", label: { en: "3-5% (needs improvement)", ar: "3-5% (يحتاج تحسين)" }, score: 60 }
    - { value: "high", label: { en: "5-10% (high)", ar: "5-10% (عالي)" }, score: 40 }
    - { value: "very_high", label: { en: "> 10% (very high)", ar: "> 10% (عالي جداً)" }, score: 20 }
    - { value: "unsure", label: { en: "Not measured", ar: "غير مقاس" }, score: 0 }
  agents: [OHNO, DEMING]
  data_field: defect_rate
  dimension: 3
  confidence_impact: high
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }
    - { lens_id: "EYE-012", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

OP_009:
  text:
    en: "How do you handle equipment maintenance?"
    ar: "كيف تتعامل مع صيانة المعدات؟"
  type: single_choice
  required: false
  conditional:
    - { question_id: "OP_001", operator: "in", value: ["manufacturing", "hybrid"] }
  options:
    - { value: "predictive", label: { en: "Predictive maintenance (IoT/sensors)", ar: "صيانة تنبؤية" }, score: 100 }
    - { value: "preventive", label: { en: "Scheduled preventive maintenance", ar: "صيانة وقائية مجدولة" }, score: 80 }
    - { value: "mixed", label: { en: "Mix of preventive and reactive", ar: "مزيج من الوقائية والتفاعلية" }, score: 60 }
    - { value: "reactive", label: { en: "Mostly reactive (fix when broken)", ar: "تفاعلية في الغالب (إصلاح عند التعطل)" }, score: 30 }
  agents: [OHNO]
  data_field: maintenance_approach
  dimension: 3
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }
    - { lens_id: "EYE-003", relevance: "secondary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

OP_010:
  text:
    en: "What percentage of your production downtime is unplanned?"
    ar: "ما نسبة وقت التوقف غير المخطط له في إنتاجك؟"
  type: single_choice
  required: false
  conditional:
    - { question_id: "OP_001", operator: "in", value: ["manufacturing", "hybrid"] }
  options:
    - { value: "minimal", label: { en: "< 2% (minimal)", ar: "< 2% (ضئيل)" }, score: 95 }
    - { value: "low", label: { en: "2-5% (good)", ar: "2-5% (جيد)" }, score: 80 }
    - { value: "moderate", label: { en: "5-10% (average)", ar: "5-10% (متوسط)" }, score: 60 }
    - { value: "high", label: { en: "10-20% (high)", ar: "10-20% (عالي)" }, score: 40 }
    - { value: "very_high", label: { en: "> 20% (very high)", ar: "> 20% (عالي جداً)" }, score: 20 }
    - { value: "unsure", label: { en: "Not tracked", ar: "غير متتبع" }, score: 0 }
  agents: [OHNO]
  data_field: unplanned_downtime
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }
    - { lens_id: "EYE-012", relevance: "secondary" }

OP_011:
  text:
    en: "What is your average lead time from order to delivery?"
    ar: "ما هو متوسط وقت التسليم من الطلب إلى التوصيل؟"
  type: single_choice
  required: true
  options:
    - { value: "same_day", label: { en: "Same day", ar: "نفس اليوم" } }
    - { value: "1_3_days", label: { en: "1-3 days", ar: "1-3 أيام" } }
    - { value: "1_week", label: { en: "About 1 week", ar: "حوالي أسبوع" } }
    - { value: "2_weeks", label: { en: "1-2 weeks", ar: "1-2 أسبوع" } }
    - { value: "1_month", label: { en: "2-4 weeks", ar: "2-4 أسابيع" } }
    - { value: "over_month", label: { en: "More than a month", ar: "أكثر من شهر" } }
    - { value: "varies", label: { en: "Varies significantly by product", ar: "يختلف بشكل كبير حسب المنتج" } }
  agents: [OHNO, PORTER]
  data_field: lead_time
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }
    - { lens_id: "EYE-011", relevance: "secondary" }

OP_012:
  text:
    en: "Do you use any lean or continuous improvement methodologies?"
    ar: "هل تستخدم أي منهجيات التحسين المستمر أو اللين؟"
  type: multiple_choice
  required: true
  options:
    - { value: "lean", label: { en: "Lean Manufacturing", ar: "التصنيع الرشيق" } }
    - { value: "six_sigma", label: { en: "Six Sigma", ar: "ستة سيجما" } }
    - { value: "tpm", label: { en: "Total Productive Maintenance (TPM)", ar: "الصيانة الإنتاجية الشاملة" } }
    - { value: "kaizen", label: { en: "Kaizen / Continuous improvement", ar: "كايزن / التحسين المستمر" } }
    - { value: "5s", label: { en: "5S", ar: "5S" } }
    - { value: "tqm", label: { en: "Total Quality Management", ar: "إدارة الجودة الشاملة" } }
    - { value: "none", label: { en: "None formally", ar: "لا شيء بشكل رسمي" } }
  agents: [OHNO, DEMING]
  data_field: improvement_methodologies
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }

OP_013:
  text:
    en: "What operational KPIs do you regularly track?"
    ar: "ما هي مؤشرات الأداء التشغيلية التي تتابعها بانتظام؟"
  type: multiple_choice
  required: true
  options:
    - { value: "oee", label: { en: "OEE (Overall Equipment Effectiveness)", ar: "الفعالية الكلية للمعدات" } }
    - { value: "cycle_time", label: { en: "Cycle time", ar: "وقت الدورة" } }
    - { value: "throughput", label: { en: "Throughput / Units produced", ar: "الإنتاجية / الوحدات المنتجة" } }
    - { value: "scrap_rate", label: { en: "Scrap / Waste rate", ar: "معدل الخردة / الهدر" } }
    - { value: "labor_productivity", label: { en: "Labor productivity", ar: "إنتاجية العمالة" } }
    - { value: "energy_consumption", label: { en: "Energy consumption", ar: "استهلاك الطاقة" } }
    - { value: "safety", label: { en: "Safety incidents", ar: "حوادث السلامة" } }
    - { value: "none", label: { en: "No formal KPI tracking", ar: "لا يوجد تتبع رسمي" } }
  agents: [OHNO, DEMING]
  data_field: operational_kpis
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }
    - { lens_id: "EYE-003", relevance: "secondary" }

OP_014:
  text:
    en: "What is your biggest operational challenge?"
    ar: "ما هو أكبر تحدٍ تشغيلي لديك؟"
  type: multiple_choice
  required: true
  options:
    - { value: "capacity", label: { en: "Not enough capacity to meet demand", ar: "عدم كفاية الطاقة لتلبية الطلب" } }
    - { value: "quality", label: { en: "Quality consistency", ar: "اتساق الجودة" } }
    - { value: "efficiency", label: { en: "Operational efficiency / waste", ar: "الكفاءة التشغيلية / الهدر" } }
    - { value: "labor", label: { en: "Finding skilled labor", ar: "إيجاد عمالة ماهرة" } }
    - { value: "equipment", label: { en: "Equipment reliability", ar: "موثوقية المعدات" } }
    - { value: "supply", label: { en: "Supply chain issues", ar: "مشاكل سلسلة التوريد" } }
    - { value: "costs", label: { en: "Rising operating costs", ar: "ارتفاع تكاليف التشغيل" } }
    - { value: "technology", label: { en: "Outdated technology", ar: "التكنولوجيا القديمة" } }
    - { value: "none", label: { en: "No major challenges", ar: "لا توجد تحديات كبيرة" } }
  agents: [OHNO]
  data_field: operational_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "primary" }

OP_015:
  text:
    en: "Do you have a formal workplace safety program?"
    ar: "هل لديك برنامج سلامة مهنية رسمي؟"
  type: single_choice
  required: true
  options:
    - { value: "certified", label: { en: "Yes, certified (OHSAS/ISO 45001)", ar: "نعم، معتمد" }, score: 100 }
    - { value: "formal", label: { en: "Yes, formal program", ar: "نعم، برنامج رسمي" }, score: 80 }
    - { value: "basic", label: { en: "Basic safety measures", ar: "إجراءات سلامة أساسية" }, score: 50 }
    - { value: "minimal", label: { en: "Minimal / Informal", ar: "ضئيل / غير رسمي" }, score: 20 }
  agents: [OHNO, MAYO]
  data_field: safety_program
  dimension: 7
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "secondary" }
    - { lens_id: "EYE-009", relevance: "secondary" }

OP_016:
  text:
    en: "How energy-efficient are your operations?"
    ar: "ما مدى كفاءة استهلاك الطاقة في عملياتك؟"
  type: single_choice
  required: true
  options:
    - { value: "leader", label: { en: "Industry leader in efficiency", ar: "رائد في الكفاءة" }, score: 100 }
    - { value: "good", label: { en: "Above average", ar: "فوق المتوسط" }, score: 80 }
    - { value: "average", label: { en: "Average for our industry", ar: "متوسط لصناعتنا" }, score: 60 }
    - { value: "needs_work", label: { en: "Below average", ar: "تحت المتوسط" }, score: 40 }
    - { value: "poor", label: { en: "Significant room for improvement", ar: "مجال كبير للتحسين" }, score: 20 }
    - { value: "unsure", label: { en: "Not sure / Not measured", ar: "غير متأكد / غير مقاس" }, score: 0 }
  agents: [OHNO]
  data_field: energy_efficiency
  dimension: 10
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-009", relevance: "primary" }
    - { lens_id: "EYE-012", relevance: "secondary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

OP_017:
  text:
    en: "What is your inventory turnover rate?"
    ar: "ما هو معدل دوران المخزون لديك؟"
  type: single_choice
  required: false
  conditional:
    - { question_id: "OP_004", operator: "not_equals", value: "na" }
  options:
    - { value: "high", label: { en: "High (> 12x per year)", ar: "عالي (> 12 مرة سنوياً)" }, score: 90 }
    - { value: "good", label: { en: "Good (6-12x per year)", ar: "جيد (6-12 مرة سنوياً)" }, score: 70 }
    - { value: "moderate", label: { en: "Moderate (3-6x per year)", ar: "متوسط (3-6 مرات سنوياً)" }, score: 50 }
    - { value: "low", label: { en: "Low (< 3x per year)", ar: "منخفض (< 3 مرات سنوياً)" }, score: 30 }
    - { value: "unsure", label: { en: "Not sure", ar: "غير متأكد" }, score: 0 }
  agents: [OHNO, GRAHAM]
  data_field: inventory_turnover
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-004", relevance: "primary" }
    - { lens_id: "EYE-012", relevance: "secondary" }

OP_018:
  text:
    en: "Is there anything unique about your operations we should know?"
    ar: "هل هناك شيء فريد في عملياتك يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any special capabilities, constraints, or operational context."
    ar: "شارك أي قدرات خاصة أو قيود أو سياق تشغيلي."
  agents: [OHNO]
  data_field: human_context_operations
  confidence_impact: high
  lens_relevance: []
```

---

# 7. Section 4: Digital Maturity

**Section Code:** `DM`  
**Primary Agent:** Lovelace (The Digitizer)  
**Estimated Time:** 3 minutes  
**Condition:** Show if lens requires (EYE-003, EYE-010) OR Crema active OR agent auto-selected

## 7.1 Questions

```yaml
DM_001:
  text:
    en: "How would you rate your company's overall digital maturity?"
    ar: "كيف تقيّم النضج الرقمي الإجمالي لشركتك؟"
  type: scale
  required: true
  scale_config:
    min: 1
    max: 5
    step: 1
    labels:
      min: { en: "Digital Beginner - Mostly manual processes", ar: "مبتدئ رقمياً - عمليات يدوية في الغالب" }
      mid: { en: "Developing - Some digital tools", ar: "متطور - بعض الأدوات الرقمية" }
      max: { en: "Digital Leader - Fully integrated", ar: "قائد رقمي - متكامل بالكامل" }
  agents: [LOVELACE, DRUCKER]
  data_field: digital_maturity_self_rating
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }
    - { lens_id: "EYE-010", relevance: "secondary" }

DM_002:
  text:
    en: "What core business systems do you currently use?"
    ar: "ما أنظمة الأعمال الأساسية التي تستخدمها حالياً؟"
  type: multiple_choice
  required: true
  options:
    - { value: "erp", label: { en: "ERP System", ar: "نظام ERP" } }
    - { value: "crm", label: { en: "CRM System", ar: "نظام CRM" } }
    - { value: "accounting", label: { en: "Accounting Software", ar: "برنامج محاسبة" } }
    - { value: "hrms", label: { en: "HR Management System", ar: "نظام إدارة الموارد البشرية" } }
    - { value: "inventory", label: { en: "Inventory Management", ar: "إدارة المخزون" } }
    - { value: "pos", label: { en: "Point of Sale (POS)", ar: "نقطة البيع" } }
    - { value: "ecommerce", label: { en: "E-commerce Platform", ar: "منصة تجارة إلكترونية" } }
    - { value: "project_mgmt", label: { en: "Project Management Tool", ar: "أداة إدارة المشاريع" } }
    - { value: "bi_analytics", label: { en: "BI / Analytics Tool", ar: "أداة ذكاء الأعمال / التحليلات" } }
    - { value: "collab", label: { en: "Collaboration Tools (Slack, Teams)", ar: "أدوات تعاون" } }
    - { value: "none", label: { en: "None - using spreadsheets/manual", ar: "لا شيء - استخدام جداول/يدوي" } }
  agents: [LOVELACE]
  data_field: core_systems
  dimension: 3
  confidence_impact: high
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

DM_003:
  text:
    en: "How integrated are your business systems?"
    ar: "ما مدى تكامل أنظمة أعمالك؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "Not integrated - data silos", ar: "غير متكاملة - صوامع بيانات" }, score: 10 }
    - { value: "manual", label: { en: "Manual data transfer between systems", ar: "نقل بيانات يدوي بين الأنظمة" }, score: 30 }
    - { value: "partial", label: { en: "Some systems integrated", ar: "بعض الأنظمة متكاملة" }, score: 50 }
    - { value: "mostly", label: { en: "Most systems integrated", ar: "معظم الأنظمة متكاملة" }, score: 75 }
    - { value: "fully", label: { en: "Fully integrated ecosystem", ar: "نظام بيئي متكامل بالكامل" }, score: 100 }
  agents: [LOVELACE]
  data_field: system_integration
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }

DM_004:
  text:
    en: "Do you have a company website?"
    ar: "هل لديك موقع إلكتروني للشركة؟"
  type: single_choice
  required: true
  options:
    - { value: "no", label: { en: "No website", ar: "لا يوجد موقع" }, score: 0 }
    - { value: "basic", label: { en: "Basic informational site", ar: "موقع معلوماتي أساسي" }, score: 30 }
    - { value: "professional", label: { en: "Professional site with regular updates", ar: "موقع احترافي مع تحديثات منتظمة" }, score: 60 }
    - { value: "ecommerce", label: { en: "E-commerce enabled", ar: "مُمكّن للتجارة الإلكترونية" }, score: 80 }
    - { value: "full_digital", label: { en: "Full digital experience (portal, app)", ar: "تجربة رقمية كاملة (بوابة، تطبيق)" }, score: 100 }
  agents: [LOVELACE, LANDOR]
  data_field: website_status
  dimension: 3
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }
    - { lens_id: "EYE-006", relevance: "secondary" }

DM_005:
  text:
    en: "How do you currently use data in decision-making?"
    ar: "كيف تستخدم البيانات حالياً في اتخاذ القرارات؟"
  type: single_choice
  required: true
  options:
    - { value: "intuition", label: { en: "Mostly intuition / experience", ar: "في الغالب حدس / خبرة" }, score: 10 }
    - { value: "basic_reports", label: { en: "Basic reports (sales, financials)", ar: "تقارير أساسية" }, score: 30 }
    - { value: "regular_analytics", label: { en: "Regular analytics review", ar: "مراجعة تحليلات منتظمة" }, score: 55 }
    - { value: "dashboards", label: { en: "Dashboards with KPIs", ar: "لوحات معلومات مع مؤشرات" }, score: 75 }
    - { value: "advanced", label: { en: "Advanced analytics / predictive", ar: "تحليلات متقدمة / تنبؤية" }, score: 100 }
  agents: [LOVELACE, TUFTE]
  data_field: data_decision_making
  dimension: 3
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

DM_006:
  text:
    en: "Have you implemented or explored AI/Machine Learning in your business?"
    ar: "هل طبقت أو استكشفت الذكاء الاصطناعي/التعلم الآلي في عملك؟"
  type: single_choice
  required: true
  options:
    - { value: "not_considered", label: { en: "Not considered yet", ar: "لم نفكر فيه بعد" }, score: 0 }
    - { value: "exploring", label: { en: "Exploring possibilities", ar: "نستكشف الإمكانيات" }, score: 25 }
    - { value: "piloting", label: { en: "Piloting / Testing", ar: "تجريب / اختبار" }, score: 50 }
    - { value: "limited_use", label: { en: "Limited production use", ar: "استخدام إنتاجي محدود" }, score: 75 }
    - { value: "core_operations", label: { en: "Core to operations", ar: "أساسي للعمليات" }, score: 100 }
  agents: [LOVELACE]
  data_field: ai_ml_adoption
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }
    - { lens_id: "EYE-010", relevance: "primary" }

DM_007:
  text:
    en: "How do you manage cybersecurity?"
    ar: "كيف تدير الأمن السيبراني؟"
  type: single_choice
  required: true
  options:
    - { value: "basic", label: { en: "Basic (antivirus, passwords)", ar: "أساسي (مضاد فيروسات، كلمات مرور)" }, score: 20 }
    - { value: "intermediate", label: { en: "Firewall + regular backups", ar: "جدار حماية + نسخ احتياطية" }, score: 45 }
    - { value: "comprehensive", label: { en: "Security policies + training", ar: "سياسات أمنية + تدريب" }, score: 70 }
    - { value: "advanced", label: { en: "Security monitoring + incident response", ar: "مراقبة أمنية + استجابة للحوادث" }, score: 90 }
    - { value: "certified", label: { en: "Certified (ISO 27001)", ar: "معتمد (ISO 27001)" }, score: 100 }
  agents: [LOVELACE]
  data_field: cybersecurity_level
  dimension: 3
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }
    - { lens_id: "EYE-013", relevance: "primary" }

DM_008:
  text:
    en: "What are your biggest technology challenges?"
    ar: "ما هي أكبر تحدياتك التكنولوجية؟"
  type: multiple_choice
  required: true
  options:
    - { value: "budget", label: { en: "Limited budget", ar: "ميزانية محدودة" } }
    - { value: "skills", label: { en: "Lack of technical skills", ar: "نقص المهارات التقنية" } }
    - { value: "integration", label: { en: "System integration", ar: "تكامل الأنظمة" } }
    - { value: "adoption", label: { en: "User adoption / resistance", ar: "اعتماد المستخدم / المقاومة" } }
    - { value: "legacy", label: { en: "Legacy systems", ar: "أنظمة قديمة" } }
    - { value: "security", label: { en: "Security concerns", ar: "مخاوف أمنية" } }
    - { value: "vendors", label: { en: "Finding right vendors", ar: "إيجاد الموردين المناسبين" } }
    - { value: "roi", label: { en: "Unclear ROI", ar: "عائد استثمار غير واضح" } }
    - { value: "none", label: { en: "No major challenges", ar: "لا تحديات كبيرة" } }
  agents: [LOVELACE]
  data_field: technology_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "primary" }

DM_009:
  text:
    en: "Do you have a digital transformation strategy?"
    ar: "هل لديك استراتيجية للتحول الرقمي؟"
  type: single_choice
  required: true
  options:
    - { value: "no", label: { en: "No formal strategy", ar: "لا توجد استراتيجية رسمية" }, score: 10 }
    - { value: "thinking", label: { en: "Starting to think about it", ar: "بدأنا التفكير فيها" }, score: 30 }
    - { value: "informal", label: { en: "Informal plans", ar: "خطط غير رسمية" }, score: 50 }
    - { value: "documented", label: { en: "Documented strategy", ar: "استراتيجية موثقة" }, score: 75 }
    - { value: "executing", label: { en: "Active execution with KPIs", ar: "تنفيذ نشط مع مؤشرات" }, score: 100 }
  agents: [LOVELACE, DRUCKER]
  data_field: digital_strategy
  dimension: 4
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-003", relevance: "primary" }

DM_010:
  text:
    en: "Is there anything specific about your technology situation we should know?"
    ar: "هل هناك أي شيء محدد حول وضعك التكنولوجي يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any ongoing projects, recent implementations, or specific needs"
    ar: "شارك أي مشاريع جارية أو تطبيقات حديثة أو احتياجات محددة"
  agents: [LOVELACE]
  data_field: human_context_digital
  confidence_impact: high
  lens_relevance: []
```

---

# 8. Section 5: Workforce & HR

**Section Code:** `WF`  
**Primary Agent:** Mayo (The People Person)  
**Estimated Time:** 3 minutes  
**Condition:** Show if lens requires (EYE-007, EYE-014) OR Crema active OR agent auto-selected

## 8.1 Questions

```yaml
WF_001:
  text:
    en: "How would you describe your workforce composition?"
    ar: "كيف تصف تكوين قوتك العاملة؟"
  type: single_choice
  required: true
  options:
    - { value: "mostly_unskilled", label: { en: "Mostly unskilled / entry-level", ar: "في الغالب غير ماهرة / مبتدئة" } }
    - { value: "mixed_skills", label: { en: "Mixed skill levels", ar: "مستويات مهارة مختلطة" } }
    - { value: "mostly_skilled", label: { en: "Mostly skilled / technical", ar: "في الغالب ماهرة / تقنية" } }
    - { value: "professional", label: { en: "Mostly professional / white collar", ar: "في الغالب مهنية / وظائف مكتبية" } }
    - { value: "highly_specialized", label: { en: "Highly specialized / expert", ar: "متخصصة جداً / خبراء" } }
  agents: [MAYO]
  data_field: workforce_composition
  dimension: 7
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }

WF_002:
  text:
    en: "What is your annual employee turnover rate?"
    ar: "ما هو معدل دوران الموظفين السنوي؟"
  type: single_choice
  required: true
  options:
    - { value: "under_5", label: { en: "Under 5%", ar: "أقل من 5%" }, score: 95 }
    - { value: "5_10", label: { en: "5-10%", ar: "5-10%" }, score: 85 }
    - { value: "10_20", label: { en: "10-20%", ar: "10-20%" }, score: 70 }
    - { value: "20_30", label: { en: "20-30%", ar: "20-30%" }, score: 50 }
    - { value: "over_30", label: { en: "Over 30%", ar: "أكثر من 30%" }, score: 25 }
    - { value: "unsure", label: { en: "Not sure", ar: "غير متأكد" }, score: 0 }
  agents: [MAYO]
  data_field: turnover_rate
  dimension: 7
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

WF_003:
  text:
    en: "Do you have formal training and development programs?"
    ar: "هل لديك برامج تدريب وتطوير رسمية؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "No formal training", ar: "لا يوجد تدريب رسمي" }, score: 10 }
    - { value: "on_job", label: { en: "On-the-job only", ar: "أثناء العمل فقط" }, score: 30 }
    - { value: "occasional", label: { en: "Occasional training", ar: "تدريب عرضي" }, score: 50 }
    - { value: "regular", label: { en: "Regular training programs", ar: "برامج تدريب منتظمة" }, score: 75 }
    - { value: "comprehensive", label: { en: "Comprehensive L&D with career paths", ar: "تعلم وتطوير شامل مع مسارات وظيفية" }, score: 100 }
  agents: [MAYO]
  data_field: training_programs
  dimension: 7
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

WF_004:
  text:
    en: "What are your biggest workforce challenges?"
    ar: "ما هي أكبر تحديات قوتك العاملة؟"
  type: multiple_choice
  required: true
  options:
    - { value: "finding_talent", label: { en: "Finding qualified talent", ar: "إيجاد كفاءات مؤهلة" } }
    - { value: "retention", label: { en: "Retaining good employees", ar: "الحفاظ على الموظفين الجيدين" } }
    - { value: "skills_gap", label: { en: "Skills gaps in current team", ar: "فجوات المهارات في الفريق الحالي" } }
    - { value: "productivity", label: { en: "Productivity / motivation", ar: "الإنتاجية / التحفيز" } }
    - { value: "labor_costs", label: { en: "High labor costs", ar: "تكاليف العمالة المرتفعة" } }
    - { value: "compliance", label: { en: "Labor law compliance", ar: "الامتثال لقوانين العمل" } }
    - { value: "succession", label: { en: "Succession / leadership pipeline", ar: "الخلافة / خط أنابيب القيادة" } }
    - { value: "culture", label: { en: "Company culture issues", ar: "مشاكل ثقافة الشركة" } }
    - { value: "none", label: { en: "No major challenges", ar: "لا تحديات كبيرة" } }
  agents: [MAYO]
  data_field: workforce_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  lens_relevance:
    - { lens_id: "EYE-007", relevance: "primary" }
    - { lens_id: "EYE-014", relevance: "secondary" }
    - { lens_id: "EYE-CREMA", relevance: "primary" }

WF_005:
  text:
    en: "Do you have a succession plan for key positions?"
    ar: "هل لديك خطة خلافة للمناصب الرئيسية؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "No succession planning", ar: "لا يوجد تخطيط للخلافة" }, score: 10 }
    - { value: "informal", label: { en: "Informal / in owner's head", ar: "غير رسمي / في ذهن المالك" }, score: 30 }
    - { value: "partial", label: { en: "Some key roles have successors", ar: "بعض الأدوار الرئيسية لها خلفاء" }, score: 60 }
    - { value: "documented", label: { en: "Documented for all key roles", ar: "موثقة لجميع الأدوار الرئيسية" }, score: 85 }
    - { value: "active", label: { en: "Active development of successors", ar: "تطوير نشط للخلفاء" }, score: 100 }
  agents: [MAYO, DRUCKER]
  data_field: succession_planning
  dimension: 4
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-014", relevance: "primary" }
    - { lens_id: "EYE-007", relevance: "secondary" }

WF_006:
  text:
    en: "Is there anything else about your workforce we should know?"
    ar: "هل هناك أي شيء آخر عن قوتك العاملة يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any unique circumstances, recent changes, or context about your team"
    ar: "شارك أي ظروف فريدة أو تغييرات حديثة أو سياق حول فريقك"
  agents: [MAYO]
  data_field: human_context_workforce
  confidence_impact: high
  lens_relevance: []
```

---

# 9. Section 6: Market & Competition

**Section Code:** `MK`  
**Primary Agent:** Porter (The Strategist)  
**Estimated Time:** 2 minutes  
**Condition:** Show if lens requires (EYE-005, EYE-011, EYE-015) OR agent auto-selected

## 9.1 Questions

```yaml
MK_001:
  text:
    en: "Who are your primary target customers?"
    ar: "من هم عملاؤك المستهدفون الرئيسيون؟"
  type: multiple_choice
  required: true
  options:
    - { value: "b2b_large", label: { en: "Large enterprises", ar: "مؤسسات كبيرة" } }
    - { value: "b2b_sme", label: { en: "Small/Medium businesses", ar: "شركات صغيرة ومتوسطة" } }
    - { value: "b2b_government", label: { en: "Government / Public sector", ar: "حكومة / قطاع عام" } }
    - { value: "b2c_mass", label: { en: "Mass consumers", ar: "المستهلكين عامة" } }
    - { value: "b2c_premium", label: { en: "Premium / affluent consumers", ar: "مستهلكين فاخرين" } }
    - { value: "distributors", label: { en: "Distributors / Resellers", ar: "موزعين / بائعين" } }
    - { value: "mixed", label: { en: "Mixed B2B and B2C", ar: "مختلط B2B و B2C" } }
  agents: [PORTER]
  data_field: target_customers
  dimension: 9
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-005", relevance: "primary" }
    - { lens_id: "EYE-011", relevance: "primary" }

MK_002:
  text:
    en: "How would you describe your competitive position?"
    ar: "كيف تصف موقفك التنافسي؟"
  type: single_choice
  required: true
  options:
    - { value: "market_leader", label: { en: "Market leader", ar: "قائد السوق" }, score: 100 }
    - { value: "top_3", label: { en: "Among top 3 players", ar: "ضمن أفضل 3 لاعبين" }, score: 85 }
    - { value: "strong_player", label: { en: "Strong player, but not top 3", ar: "لاعب قوي، لكن ليس ضمن أفضل 3" }, score: 70 }
    - { value: "niche_leader", label: { en: "Leader in our niche", ar: "قائد في مجالنا المتخصص" }, score: 75 }
    - { value: "emerging", label: { en: "Emerging / growing competitor", ar: "منافس ناشئ / ينمو" }, score: 50 }
    - { value: "small_player", label: { en: "Small player in fragmented market", ar: "لاعب صغير في سوق مجزأ" }, score: 30 }
  agents: [PORTER]
  data_field: competitive_position
  dimension: 9
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-005", relevance: "primary" }
    - { lens_id: "EYE-002", relevance: "secondary" }

MK_003:
  text:
    en: "What is your primary competitive advantage?"
    ar: "ما هي ميزتك التنافسية الرئيسية؟"
  type: multiple_choice
  required: true
  options:
    - { value: "price", label: { en: "Lower price / cost leader", ar: "سعر أقل / قائد التكلفة" } }
    - { value: "quality", label: { en: "Superior quality", ar: "جودة متفوقة" } }
    - { value: "service", label: { en: "Better customer service", ar: "خدمة عملاء أفضل" } }
    - { value: "speed", label: { en: "Faster delivery / turnaround", ar: "تسليم / استجابة أسرع" } }
    - { value: "innovation", label: { en: "Innovation / unique products", ar: "ابتكار / منتجات فريدة" } }
    - { value: "relationships", label: { en: "Strong customer relationships", ar: "علاقات قوية مع العملاء" } }
    - { value: "brand", label: { en: "Brand / reputation", ar: "العلامة التجارية / السمعة" } }
    - { value: "unclear", label: { en: "Not clearly defined", ar: "غير محددة بوضوح" } }
  agents: [PORTER, LANDOR]
  data_field: competitive_advantage
  dimension: 9
  confidence_impact: high
  allows_human_context: true
  lens_relevance:
    - { lens_id: "EYE-005", relevance: "primary" }
    - { lens_id: "EYE-006", relevance: "primary" }

MK_004:
  text:
    en: "How satisfied are your customers generally?"
    ar: "ما مدى رضا عملائك بشكل عام؟"
  type: single_choice
  required: true
  options:
    - { value: "very_high", label: { en: "Very high - strong loyalty", ar: "عالي جداً - ولاء قوي" }, score: 95 }
    - { value: "high", label: { en: "High - repeat customers", ar: "عالي - عملاء متكررون" }, score: 80 }
    - { value: "moderate", label: { en: "Moderate - some complaints", ar: "معتدل - بعض الشكاوى" }, score: 60 }
    - { value: "mixed", label: { en: "Mixed - varies by segment", ar: "مختلط - يختلف حسب الشريحة" }, score: 50 }
    - { value: "low", label: { en: "Lower than we'd like", ar: "أقل مما نريد" }, score: 35 }
    - { value: "dont_measure", label: { en: "We don't measure this", ar: "لا نقيس هذا" }, score: 0 }
  agents: [PORTER, DEMING]
  data_field: customer_satisfaction
  dimension: 9
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-011", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

MK_005:
  text:
    en: "What are your main market challenges?"
    ar: "ما هي تحديات السوق الرئيسية لديك؟"
  type: multiple_choice
  required: true
  options:
    - { value: "competition", label: { en: "Intense competition", ar: "منافسة شديدة" } }
    - { value: "price_pressure", label: { en: "Price pressure", ar: "ضغط الأسعار" } }
    - { value: "awareness", label: { en: "Low brand awareness", ar: "وعي منخفض بالعلامة التجارية" } }
    - { value: "reach", label: { en: "Reaching new customers", ar: "الوصول إلى عملاء جدد" } }
    - { value: "changing_needs", label: { en: "Changing customer needs", ar: "احتياجات العملاء المتغيرة" } }
    - { value: "substitutes", label: { en: "Substitute products/services", ar: "منتجات / خدمات بديلة" } }
    - { value: "none", label: { en: "No major challenges", ar: "لا تحديات كبيرة" } }
  agents: [PORTER]
  data_field: market_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  lens_relevance:
    - { lens_id: "EYE-005", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "primary" }

MK_006:
  text:
    en: "Is there anything else about your market we should know?"
    ar: "هل هناك أي شيء آخر عن سوقك يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any market trends, customer insights, or competitive dynamics"
    ar: "شارك أي اتجاهات سوقية أو رؤى عملاء أو ديناميكيات تنافسية"
  agents: [PORTER]
  data_field: human_context_market
  confidence_impact: high
  lens_relevance: []
```

---

# 10. Section 7: Supply Chain

**Section Code:** `SC`  
**Primary Agent:** Ohno (The Flow Master)  
**Estimated Time:** 3 minutes  
**Condition:** Show if lens requires (EYE-008) OR manufacturing/trading business model

## 10.1 Questions

```yaml
SC_001:
  text:
    en: "How many key suppliers do you work with?"
    ar: "كم عدد الموردين الرئيسيين الذين تعمل معهم؟"
  type: single_choice
  required: true
  options:
    - { value: "1_5", label: { en: "1-5 suppliers", ar: "1-5 موردين" } }
    - { value: "6_20", label: { en: "6-20 suppliers", ar: "6-20 مورد" } }
    - { value: "21_50", label: { en: "21-50 suppliers", ar: "21-50 مورد" } }
    - { value: "over_50", label: { en: "Over 50 suppliers", ar: "أكثر من 50 مورد" } }
  agents: [OHNO]
  data_field: supplier_count
  dimension: 8
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }

SC_002:
  text:
    en: "How reliable are your suppliers?"
    ar: "ما مدى موثوقية مورديك؟"
  type: single_choice
  required: true
  options:
    - { value: "very_reliable", label: { en: "Very reliable (95%+ on time)", ar: "موثوق جداً (95%+ في الوقت)" }, score: 95 }
    - { value: "reliable", label: { en: "Reliable (85-95% on time)", ar: "موثوق (85-95% في الوقت)" }, score: 90 }
    - { value: "moderate", label: { en: "Moderate (70-85% on time)", ar: "معتدل (70-85% في الوقت)" }, score: 77 }
    - { value: "unreliable", label: { en: "Often delayed", ar: "متأخر في كثير من الأحيان" }, score: 50 }
  agents: [OHNO]
  data_field: supplier_reliability
  dimension: 8
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

SC_003:
  text:
    en: "Do you have backup suppliers for critical materials?"
    ar: "هل لديك موردون بديلون للمواد الحرجة؟"
  type: single_choice
  required: true
  options:
    - { value: "no", label: { en: "No backup suppliers", ar: "لا يوجد موردون بديلون" }, score: 20 }
    - { value: "some", label: { en: "For some materials", ar: "لبعض المواد" }, score: 55 }
    - { value: "most", label: { en: "For most critical materials", ar: "لمعظم المواد الحرجة" }, score: 80 }
    - { value: "all", label: { en: "For all critical materials", ar: "لجميع المواد الحرجة" }, score: 100 }
  agents: [OHNO]
  data_field: backup_suppliers
  dimension: 8
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }
    - { lens_id: "EYE-013", relevance: "primary" }

SC_004:
  text:
    en: "What are your biggest supply chain challenges?"
    ar: "ما هي أكبر تحديات سلسلة التوريد لديك؟"
  type: multiple_choice
  required: true
  options:
    - { value: "cost", label: { en: "Rising costs", ar: "ارتفاع التكاليف" } }
    - { value: "reliability", label: { en: "Supplier reliability", ar: "موثوقية الموردين" } }
    - { value: "quality", label: { en: "Quality consistency", ar: "اتساق الجودة" } }
    - { value: "lead_times", label: { en: "Long lead times", ar: "أوقات تسليم طويلة" } }
    - { value: "visibility", label: { en: "Lack of visibility", ar: "نقص الرؤية" } }
    - { value: "currency", label: { en: "Currency fluctuations", ar: "تقلبات العملة" } }
    - { value: "none", label: { en: "No major challenges", ar: "لا تحديات كبيرة" } }
  agents: [OHNO]
  data_field: supply_chain_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  lens_relevance:
    - { lens_id: "EYE-008", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "primary" }

SC_005:
  text:
    en: "Is there anything else about your supply chain we should know?"
    ar: "هل هناك أي شيء آخر عن سلسلة التوريد يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any unique circumstances, ongoing initiatives, or specific concerns"
    ar: "شارك أي ظروف فريدة أو مبادرات جارية أو مخاوف محددة"
  agents: [OHNO]
  data_field: human_context_supply_chain
  confidence_impact: high
  lens_relevance: []
```

---

# 11. Section 8: Export Readiness

**Section Code:** `EX`  
**Primary Agents:** Ricardo (The Globalizer), Landor (The Storyteller)  
**Estimated Time:** 4 minutes  
**Condition:** Show if lens requires (EYE-001) OR user indicated export interest

## 11.1 Questions

```yaml
EX_001:
  text:
    en: "Are you currently exporting or have you exported in the past?"
    ar: "هل تصدّر حالياً أو صدّرت في الماضي؟"
  type: single_choice
  required: true
  options:
    - { value: "never", label: { en: "Never exported", ar: "لم أصدّر أبداً" } }
    - { value: "tried_stopped", label: { en: "Tried but stopped", ar: "حاولت لكن توقفت" } }
    - { value: "occasional", label: { en: "Occasional / opportunistic exports", ar: "تصدير عرضي / انتهازي" } }
    - { value: "regular", label: { en: "Regular exports (part of strategy)", ar: "تصدير منتظم (جزء من الاستراتيجية)" } }
    - { value: "export_focused", label: { en: "Export-focused (majority of sales)", ar: "يركز على التصدير (غالبية المبيعات)" } }
  agents: [RICARDO]
  data_field: export_status
  dimension: 9
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-001", relevance: "primary" }

EX_002:
  text:
    en: "Which markets are you interested in entering or expanding into?"
    ar: "ما الأسواق التي تهتم بدخولها أو التوسع فيها؟"
  type: multiple_choice
  required: true
  options:
    - { value: "GCC", label: { en: "GCC countries", ar: "دول الخليج" } }
    - { value: "LEVANT", label: { en: "Levant (Jordan, Lebanon, Iraq)", ar: "بلاد الشام" } }
    - { value: "NORTH_AFRICA", label: { en: "North Africa", ar: "شمال أفريقيا" } }
    - { value: "AFRICA_SUB", label: { en: "Sub-Saharan Africa", ar: "أفريقيا جنوب الصحراء" } }
    - { value: "EUROPE", label: { en: "European Union", ar: "الاتحاد الأوروبي" } }
    - { value: "US_CANADA", label: { en: "US / Canada", ar: "أمريكا / كندا" } }
    - { value: "ASIA", label: { en: "Asia-Pacific", ar: "آسيا والمحيط الهادئ" } }
    - { value: "UNSURE", label: { en: "Not sure yet", ar: "غير متأكد بعد" } }
  agents: [RICARDO]
  data_field: target_export_markets
  dimension: 11
  confidence_impact: high
  allows_human_context: true
  lens_relevance:
    - { lens_id: "EYE-001", relevance: "primary" }

EX_003:
  text:
    en: "What certifications do you have for export?"
    ar: "ما الشهادات التي تملكها للتصدير؟"
  type: multiple_choice
  required: true
  options:
    - { value: "none", label: { en: "None currently", ar: "لا توجد حالياً" } }
    - { value: "iso9001", label: { en: "ISO 9001", ar: "ISO 9001" } }
    - { value: "iso22000", label: { en: "ISO 22000 / FSSC 22000", ar: "ISO 22000" } }
    - { value: "haccp", label: { en: "HACCP", ar: "HACCP" } }
    - { value: "halal", label: { en: "Halal certification", ar: "شهادة حلال" } }
    - { value: "organic", label: { en: "Organic certification", ar: "شهادة عضوية" } }
    - { value: "ce", label: { en: "CE marking", ar: "علامة CE" } }
    - { value: "other", label: { en: "Other industry-specific", ar: "أخرى خاصة بالصناعة" } }
  agents: [RICARDO, DEMING]
  data_field: export_certifications
  dimension: 10
  confidence_impact: high
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-001", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "secondary" }

EX_004:
  text:
    en: "What are your biggest export challenges?"
    ar: "ما هي أكبر تحديات التصدير لديك؟"
  type: multiple_choice
  required: true
  options:
    - { value: "market_knowledge", label: { en: "Finding buyers / market knowledge", ar: "إيجاد مشترين / معرفة السوق" } }
    - { value: "certification", label: { en: "Getting required certifications", ar: "الحصول على الشهادات المطلوبة" } }
    - { value: "pricing", label: { en: "Pricing competitively", ar: "التسعير بشكل تنافسي" } }
    - { value: "logistics", label: { en: "Logistics and shipping", ar: "اللوجستيات والشحن" } }
    - { value: "payment_risk", label: { en: "Payment collection / risk", ar: "تحصيل المدفوعات / المخاطر" } }
    - { value: "regulations", label: { en: "Understanding regulations", ar: "فهم اللوائح" } }
    - { value: "capacity", label: { en: "Production capacity", ar: "الطاقة الإنتاجية" } }
    - { value: "none", label: { en: "No major concerns", ar: "لا مخاوف كبيرة" } }
  agents: [RICARDO]
  data_field: export_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  lens_relevance:
    - { lens_id: "EYE-001", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "primary" }

EX_005:
  text:
    en: "Is there anything else about your export goals we should know?"
    ar: "هل هناك أي شيء آخر عن أهدافك التصديرية يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any specific markets of interest, ongoing initiatives, or unique circumstances"
    ar: "شارك أي أسواق محددة تهمك أو مبادرات جارية أو ظروف فريدة"
  agents: [RICARDO]
  data_field: human_context_export
  confidence_impact: high
  lens_relevance: []
```

---

# 12. Section 9: Brand & Marketing

**Section Code:** `BR`  
**Primary Agent:** Landor (The Storyteller)  
**Estimated Time:** 2 minutes  
**Condition:** Show if lens requires (EYE-006) OR agent auto-selected

## 12.1 Questions

```yaml
BR_001:
  text:
    en: "How would you describe your brand awareness?"
    ar: "كيف تصف الوعي بعلامتك التجارية؟"
  type: single_choice
  required: true
  options:
    - { value: "unknown", label: { en: "Largely unknown", ar: "غير معروفة إلى حد كبير" }, score: 10 }
    - { value: "niche", label: { en: "Known within niche", ar: "معروفة ضمن مجال محدد" }, score: 40 }
    - { value: "moderate", label: { en: "Moderate awareness", ar: "وعي معتدل" }, score: 60 }
    - { value: "well_known", label: { en: "Well known", ar: "معروفة جيداً" }, score: 80 }
    - { value: "market_leader", label: { en: "Market leader / household name", ar: "قائد السوق / اسم معروف" }, score: 100 }
  agents: [LANDOR, PORTER]
  data_field: brand_awareness
  dimension: 9
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-006", relevance: "primary" }
    - { lens_id: "EYE-005", relevance: "secondary" }

BR_002:
  text:
    en: "Do you have a defined brand strategy?"
    ar: "هل لديك استراتيجية علامة تجارية محددة؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "No formal brand strategy", ar: "لا توجد استراتيجية علامة تجارية رسمية" }, score: 10 }
    - { value: "informal", label: { en: "Informal / in owner's head", ar: "غير رسمية / في ذهن المالك" }, score: 30 }
    - { value: "basic", label: { en: "Basic positioning defined", ar: "مكانة أساسية محددة" }, score: 55 }
    - { value: "documented", label: { en: "Documented brand strategy", ar: "استراتيجية علامة تجارية موثقة" }, score: 80 }
    - { value: "comprehensive", label: { en: "Comprehensive with brand guidelines", ar: "شاملة مع إرشادات العلامة التجارية" }, score: 100 }
  agents: [LANDOR]
  data_field: brand_strategy
  dimension: 4
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-006", relevance: "primary" }

BR_003:
  text:
    en: "What marketing channels do you currently use?"
    ar: "ما قنوات التسويق التي تستخدمها حالياً؟"
  type: multiple_choice
  required: true
  options:
    - { value: "none", label: { en: "No active marketing", ar: "لا تسويق نشط" } }
    - { value: "word_of_mouth", label: { en: "Word of mouth only", ar: "كلام شفهي فقط" } }
    - { value: "social_media", label: { en: "Social media", ar: "وسائل التواصل الاجتماعي" } }
    - { value: "website", label: { en: "Website / SEO", ar: "موقع إلكتروني / SEO" } }
    - { value: "paid_digital", label: { en: "Paid digital ads", ar: "إعلانات رقمية مدفوعة" } }
    - { value: "traditional", label: { en: "Traditional media", ar: "وسائل إعلام تقليدية" } }
    - { value: "trade_shows", label: { en: "Trade shows / events", ar: "معارض / فعاليات" } }
    - { value: "direct_sales", label: { en: "Direct sales outreach", ar: "التواصل المباشر للمبيعات" } }
  agents: [LANDOR, PORTER]
  data_field: marketing_channels
  dimension: 9
  confidence_impact: medium
  lens_relevance:
    - { lens_id: "EYE-006", relevance: "primary" }
    - { lens_id: "EYE-005", relevance: "secondary" }

BR_004:
  text:
    en: "What are your biggest marketing challenges?"
    ar: "ما هي أكبر تحديات التسويق لديك؟"
  type: multiple_choice
  required: true
  options:
    - { value: "budget", label: { en: "Limited budget", ar: "ميزانية محدودة" } }
    - { value: "awareness", label: { en: "Building awareness", ar: "بناء الوعي" } }
    - { value: "differentiation", label: { en: "Standing out from competitors", ar: "التميز عن المنافسين" } }
    - { value: "digital_skills", label: { en: "Digital marketing skills", ar: "مهارات التسويق الرقمي" } }
    - { value: "content", label: { en: "Creating quality content", ar: "إنشاء محتوى عالي الجودة" } }
    - { value: "leads", label: { en: "Generating quality leads", ar: "توليد عملاء محتملين" } }
    - { value: "none", label: { en: "No major challenges", ar: "لا تحديات كبيرة" } }
  agents: [LANDOR]
  data_field: marketing_challenges
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  lens_relevance:
    - { lens_id: "EYE-006", relevance: "primary" }
    - { lens_id: "EYE-CREMA", relevance: "primary" }

BR_005:
  text:
    en: "Is there anything else about your brand we should know?"
    ar: "هل هناك أي شيء آخر عن علامتك التجارية يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any unique brand story, upcoming campaigns, or specific needs"
    ar: "شارك أي قصة علامة تجارية فريدة أو حملات قادمة أو احتياجات محددة"
  agents: [LANDOR]
  data_field: human_context_brand
  confidence_impact: high
  lens_relevance: []
```

---

# 13. Section 10: Compliance & Certifications

**Section Code:** `CC`  
**Primary Agents:** Deming (The Perfectionist), Various  
**Estimated Time:** 2 minutes  
**Condition:** Contextual - show based on sector and lens requirements

## 13.1 Questions

```yaml
CC_001:
  text:
    en: "Is your company registered and compliant with local regulations?"
    ar: "هل شركتك مسجلة ومتوافقة مع اللوائح المحلية؟"
  type: single_choice
  required: true
  options:
    - { value: "fully_compliant", label: { en: "Fully registered and compliant", ar: "مسجلة ومتوافقة بالكامل" }, score: 100 }
    - { value: "mostly_compliant", label: { en: "Mostly compliant, minor gaps", ar: "متوافقة في الغالب، ثغرات طفيفة" }, score: 75 }
    - { value: "working_on", label: { en: "Working on compliance", ar: "نعمل على الامتثال" }, score: 50 }
    - { value: "informal", label: { en: "Informal / not fully registered", ar: "غير رسمي / غير مسجل بالكامل" }, score: 25 }
  agents: [DEMING, DRUCKER]
  data_field: business_compliance
  dimension: 10
  confidence_impact: high
  lens_relevance:
    - { lens_id: "EYE-002", relevance: "primary" }
    - { lens_id: "EYE-001", relevance: "primary" }

CC_002:
  text:
    en: "Do you have contracts in place with major customers and suppliers?"
    ar: "هل لديك عقود مع العملاء والموردين الرئيسيين؟"
  type: single_choice
  required: true
  options:
    - { value: "all", label: { en: "Yes, all major relationships", ar: "نعم، جميع العلاقات الرئيسية" }, score: 100 }
    - { value: "most", label: { en: "Most relationships", ar: "معظم العلاقات" }, score: 75 }
    - { value: "some", label: { en: "Some relationships", ar: "بعض العلاقات" }, score: 45 }
    - { value: "few", label: { en: "Few / informal arrangements", ar: "قليل / ترتيبات غير رسمية" }, score: 20 }
  agents: [DEMING, GRAHAM]
  data_field: contract_coverage
  dimension: 4
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-013", relevance: "primary" }
    - { lens_id: "EYE-002", relevance: "secondary" }

CC_003:
  text:
    en: "Do you have appropriate business insurance?"
    ar: "هل لديك تأمين أعمال مناسب؟"
  type: single_choice
  required: true
  options:
    - { value: "comprehensive", label: { en: "Comprehensive coverage", ar: "تغطية شاملة" }, score: 100 }
    - { value: "basic", label: { en: "Basic coverage", ar: "تغطية أساسية" }, score: 60 }
    - { value: "minimal", label: { en: "Minimal / required only", ar: "الحد الأدنى / المطلوب فقط" }, score: 35 }
    - { value: "none", label: { en: "No business insurance", ar: "لا يوجد تأمين أعمال" }, score: 10 }
  agents: [DEMING, GRAHAM]
  data_field: insurance_coverage
  dimension: 10
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-013", relevance: "primary" }
    - { lens_id: "EYE-002", relevance: "secondary" }

CC_004:
  text:
    en: "Is there anything about compliance we should know?"
    ar: "هل هناك أي شيء عن الامتثال يجب أن نعرفه؟"
  type: human_context
  required: false
  description:
    en: "Share any compliance challenges, certification goals, or regulatory concerns"
    ar: "شارك أي تحديات امتثال أو أهداف شهادات أو مخاوف تنظيمية"
  agents: [DEMING]
  data_field: human_context_compliance
  confidence_impact: high
  lens_relevance: []
```

---

# 14. Section 11: Quick Win Assessment

**Section Code:** `QW`  
**Primary Agents:** Drucker (Supervisor), All Agents  
**Estimated Time:** 2 minutes  
**Condition:** Show if The Crema (EYE-CREMA) is active  
**Purpose:** Capture data specifically for Crema quick-win filtering (30-60-90 day opportunities)

## 14.1 Overview

This section is NEW in v2.0 and specifically supports The Crema feature. Questions here help identify:
- Which recommendations can be implemented quickly
- What internal resources are available
- Decision-making speed and authority
- Willingness to act on quick wins

## 14.2 Questions

```yaml
QW_001:
  text:
    en: "How quickly can you typically make business decisions?"
    ar: "ما مدى سرعة اتخاذك لقرارات الأعمال عادةً؟"
  type: single_choice
  required: true
  description:
    en: "This helps us identify which recommendations you can act on quickly"
    ar: "هذا يساعدنا على تحديد التوصيات التي يمكنك تنفيذها بسرعة"
  options:
    - { value: "immediate", label: { en: "I can decide immediately", ar: "يمكنني أن أقرر فوراً" }, effort_level: "low", score: 100 }
    - { value: "days", label: { en: "Within a few days", ar: "خلال بضعة أيام" }, effort_level: "low", score: 80 }
    - { value: "weeks", label: { en: "1-2 weeks", ar: "1-2 أسبوع" }, effort_level: "medium", score: 60 }
    - { value: "month", label: { en: "About a month", ar: "حوالي شهر" }, effort_level: "medium", score: 40 }
    - { value: "longer", label: { en: "More than a month", ar: "أكثر من شهر" }, effort_level: "high", score: 20 }
    - { value: "board_approval", label: { en: "Need board/partner approval", ar: "أحتاج موافقة مجلس/شريك" }, effort_level: "high", score: 15 }
  agents: [DRUCKER]
  data_field: decision_speed
  confidence_impact: high
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-CREMA", relevance: "primary" }

QW_002:
  text:
    en: "What budget could you allocate to quick improvements in the next 90 days?"
    ar: "ما الميزانية التي يمكنك تخصيصها للتحسينات السريعة في الـ 90 يوماً القادمة؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "No additional budget available", ar: "لا توجد ميزانية إضافية" }, effort_level: "high", score: 10 }
    - { value: "minimal", label: { en: "Under $1,000", ar: "أقل من 1,000 دولار" }, effort_level: "low", score: 40 }
    - { value: "small", label: { en: "$1,000 - $5,000", ar: "1,000 - 5,000 دولار" }, effort_level: "low", score: 60 }
    - { value: "moderate", label: { en: "$5,000 - $20,000", ar: "5,000 - 20,000 دولار" }, effort_level: "medium", score: 80 }
    - { value: "significant", label: { en: "$20,000 - $50,000", ar: "20,000 - 50,000 دولار" }, effort_level: "medium", score: 90 }
    - { value: "substantial", label: { en: "Over $50,000", ar: "أكثر من 50,000 دولار" }, effort_level: "high", score: 100 }
  agents: [GRAHAM, DRUCKER]
  data_field: quick_improvement_budget
  confidence_impact: high
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-CREMA", relevance: "primary" }

QW_003:
  text:
    en: "Do you have staff time available to implement changes?"
    ar: "هل لديك وقت موظفين متاح لتنفيذ التغييرات؟"
  type: single_choice
  required: true
  options:
    - { value: "dedicated_team", label: { en: "Yes, can dedicate people full-time", ar: "نعم، يمكنني تخصيص أشخاص بدوام كامل" }, effort_level: "low", score: 100 }
    - { value: "part_time", label: { en: "Yes, part-time availability", ar: "نعم، توفر بدوام جزئي" }, effort_level: "low", score: 75 }
    - { value: "limited", label: { en: "Limited - everyone is stretched", ar: "محدود - الجميع مشغولون" }, effort_level: "medium", score: 45 }
    - { value: "owner_only", label: { en: "Only myself (owner)", ar: "أنا فقط (المالك)" }, effort_level: "medium", score: 35 }
    - { value: "none", label: { en: "No available capacity", ar: "لا توجد طاقة متاحة" }, effort_level: "high", score: 15 }
  agents: [MAYO, DRUCKER]
  data_field: staff_availability
  confidence_impact: high
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-CREMA", relevance: "primary" }

QW_004:
  text:
    en: "How open is your team to change?"
    ar: "ما مدى انفتاح فريقك على التغيير؟"
  type: scale
  required: true
  scale_config:
    min: 1
    max: 5
    step: 1
    labels:
      min: { en: "Very resistant - prefer status quo", ar: "مقاوم جداً - يفضل الوضع الحالي" }
      mid: { en: "Mixed - depends on the change", ar: "مختلط - يعتمد على التغيير" }
      max: { en: "Very open - eager to improve", ar: "منفتح جداً - متحمس للتحسين" }
  agents: [MAYO, DRUCKER]
  data_field: change_readiness
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-CREMA", relevance: "primary" }
    - { lens_id: "EYE-007", relevance: "secondary" }

QW_005:
  text:
    en: "What type of quick wins would be most valuable to you?"
    ar: "ما نوع المكاسب السريعة الأكثر قيمة لك؟"
  type: ranking
  required: true
  description:
    en: "Rank these in order of importance to help us prioritize recommendations"
    ar: "رتّب هذه حسب الأهمية لمساعدتنا في ترتيب التوصيات"
  options:
    - { value: "cost_savings", label: { en: "Cost savings / efficiency", ar: "توفير التكاليف / الكفاءة" } }
    - { value: "revenue_growth", label: { en: "Revenue growth", ar: "نمو الإيرادات" } }
    - { value: "risk_reduction", label: { en: "Risk reduction", ar: "تقليل المخاطر" } }
    - { value: "customer_satisfaction", label: { en: "Customer satisfaction", ar: "رضا العملاء" } }
    - { value: "employee_productivity", label: { en: "Employee productivity", ar: "إنتاجية الموظفين" } }
    - { value: "compliance", label: { en: "Compliance / certifications", ar: "الامتثال / الشهادات" } }
  agents: [DRUCKER]
  data_field: quick_win_priorities
  confidence_impact: high
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-CREMA", relevance: "primary" }

QW_006:
  text:
    en: "What's the one thing you'd fix first if you could?"
    ar: "ما الشيء الوحيد الذي ستصلحه أولاً إذا استطعت؟"
  type: text_long
  required: false
  description:
    en: "This helps us understand your immediate priorities and pain points"
    ar: "هذا يساعدنا على فهم أولوياتك الفورية ونقاط الألم"
  agents: [DRUCKER]
  data_field: first_priority_fix
  confidence_impact: high
  quick_win_indicator: true
  allows_human_context: true
  lens_relevance:
    - { lens_id: "EYE-CREMA", relevance: "primary" }

QW_007:
  text:
    en: "How committed are you to acting on recommendations from this diagnostic?"
    ar: "ما مدى التزامك بالتصرف بناءً على توصيات هذا التشخيص؟"
  type: scale
  required: true
  scale_config:
    min: 1
    max: 5
    step: 1
    labels:
      min: { en: "Just exploring - no commitment", ar: "أستكشف فقط - لا التزام" }
      mid: { en: "Will consider recommendations", ar: "سأنظر في التوصيات" }
      max: { en: "Highly committed - ready to act", ar: "ملتزم جداً - جاهز للتصرف" }
  agents: [DRUCKER]
  data_field: action_commitment
  confidence_impact: high
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-CREMA", relevance: "primary" }
```

QW_008:
  text:
    en: "Have you tried to implement improvements before that didn't work?"
    ar: "هل حاولت تنفيذ تحسينات من قبل ولم تنجح؟"
  type: single_choice
  required: true
  options:
    - value: "no"
      label: { en: "No, haven't tried major changes", ar: "لا، لم أحاول تغييرات كبيرة" }
    - value: "yes_resource"
      label: { en: "Yes, failed due to resource constraints", ar: "نعم، فشلت بسبب قيود الموارد" }
    - value: "yes_resistance"
      label: { en: "Yes, faced team resistance", ar: "نعم، واجهت مقاومة الفريق" }
    - value: "yes_wrong_fit"
      label: { en: "Yes, solutions weren't right fit", ar: "نعم، الحلول لم تكن مناسبة" }
    - value: "yes_execution"
      label: { en: "Yes, execution problems", ar: "نعم، مشاكل في التنفيذ" }
    - value: "yes_successful"
      label: { en: "Yes, and most were successful", ar: "نعم، ومعظمها نجحت" }
  agents: [DRUCKER]
  data_field: past_improvement_attempts
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-CREMA", relevance: "primary" }

QW_009:
  text:
    en: "Do you have access to external support (consultants, mentors, advisors)?"
    ar: "هل لديك إمكانية الوصول إلى دعم خارجي (استشاريون، مرشدون، مستشارون)؟"
  type: single_choice
  required: true
  options:
    - { value: "strong_network", label: { en: "Yes, strong support network", ar: "نعم، شبكة دعم قوية" }, effort_level: "low", score: 100 }
    - { value: "some", label: { en: "Some trusted advisors", ar: "بعض المستشارين الموثوقين" }, effort_level: "low", score: 70 }
    - { value: "limited", label: { en: "Limited access", ar: "وصول محدود" }, effort_level: "medium", score: 45 }
    - { value: "none", label: { en: "No external support", ar: "لا يوجد دعم خارجي" }, effort_level: "high", score: 20 }
  agents: [DRUCKER]
  data_field: external_support
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-CREMA", relevance: "primary" }

QW_010:
  text:
    en: "Which tools or systems could you adopt quickly (within 30 days)?"
    ar: "ما الأدوات أو الأنظمة التي يمكنك اعتمادها بسرعة (خلال 30 يوماً)؟"
  type: multiple_choice
  required: true
  options:
    - { value: "accounting", label: { en: "Better accounting software", ar: "برنامج محاسبة أفضل" } }
    - { value: "crm", label: { en: "Customer management (CRM)", ar: "إدارة العملاء" } }
    - { value: "project", label: { en: "Project management", ar: "إدارة المشاريع" } }
    - { value: "communication", label: { en: "Team communication", ar: "تواصل الفريق" } }
    - { value: "marketing", label: { en: "Marketing / social media", ar: "تسويق / وسائل التواصل" } }
    - { value: "inventory", label: { en: "Inventory tracking", ar: "تتبع المخزون" } }
    - { value: "hr", label: { en: "HR / payroll", ar: "موارد بشرية / رواتب" } }
    - { value: "analytics", label: { en: "Dashboards / analytics", ar: "لوحات معلومات / تحليلات" } }
    - { value: "none", label: { en: "None - not ready for new tools", ar: "لا شيء - غير مستعد لأدوات جديدة" } }
  agents: [LOVELACE, DRUCKER]
  data_field: quick_tool_adoption
  confidence_impact: medium
  quick_win_indicator: true
  lens_relevance:
    - { lens_id: "EYE-CREMA", relevance: "primary" }
    - { lens_id: "EYE-003", relevance: "secondary" }
```

---

# 15. Conditional Logic Rules

This section defines the branching logic that controls which questions appear based on previous answers.

## 15.1 Core Conditionals

```yaml
conditional_rules:
  
  # Business Model Branching
  manufacturing_questions:
    trigger: { question_id: "OP_001", operator: "in", value: ["manufacturing", "hybrid_mfg_svc"] }
    show_questions: [OP_002, OP_002a, OP_004, OP_005, OP_006, OP_014]
    show_sections: [SC]  # Supply Chain section
    
  services_questions:
    trigger: { question_id: "OP_001", operator: "in", value: ["services", "platform", "saas"] }
    hide_questions: [OP_002, OP_002a, OP_004, OP_005, OP_006, OP_014, OP_012]
    
  # Export Status Branching
  export_active:
    trigger: { question_id: "EX_001", operator: "in", value: ["occasional", "regular", "export_focused"] }
    show_questions: [EX_002, EX_003, EX_004, EX_005, EX_006, EX_007, EX_008, EX_009, EX_010, EX_011, EX_012, EX_013, EX_014, EX_015]
    
  export_never:
    trigger: { question_id: "EX_001", operator: "equals", value: "never" }
    show_questions: [EX_004, EX_005, EX_013]  # Just interest and challenges
    skip_questions: [EX_002, EX_003, EX_006, EX_007, EX_008, EX_009, EX_010, EX_011, EX_012, EX_014]
    
  export_stopped:
    trigger: { question_id: "EX_001", operator: "equals", value: "tried_stopped" }
    show_questions: [EX_001a, EX_004, EX_005, EX_013]
    
  # Funding-Related Branching
  has_funding_history:
    trigger: { question_id: "FH_010", operator: "not_equals", value: "none" }
    show_questions: [FH_010a, FH_010b]
    
  seeking_funding:
    trigger: { question_id: "FH_011", operator: "in", value: ["actively_seeking", "considering"] }
    show_questions: [FH_011a]
    
  # E-commerce Branching
  has_ecommerce:
    trigger: { question_id: "DM_004", operator: "in", value: ["ecommerce", "full_digital"] }
    show_questions: [DM_004a]
    
  # Supply Chain Disruption Branching
  had_disruptions:
    trigger: { question_id: "SC_008", operator: "in", value: ["moderate", "significant"] }
    show_questions: [SC_008a]
    
  # Lens Selection Branching
  custom_lens_selected:
    trigger: { question_id: "LS_001", operator: "equals", value: "EYE-CUSTOM" }
    show_questions: [LS_003]
```

## 15.2 Sector-Based Conditionals

```yaml
sector_conditionals:
  
  food_sector:
    trigger: { question_id: "BP_005", operator: "equals", value: "food_processing" }
    show_questions: [BP_005a]
    add_relevance:
      - { section: "CC", weight_multiplier: 1.5 }  # Compliance more important
      - { question_id: "EX_005", priority: "high" }  # Food certifications
    
  technology_sector:
    trigger: { question_id: "BP_005", operator: "equals", value: "technology" }
    show_questions: [BP_005b]
    add_relevance:
      - { section: "DM", weight_multiplier: 1.3 }  # Digital maturity more important
      
  textile_sector:
    trigger: { question_id: "BP_005", operator: "equals", value: "textiles" }
    show_questions: [BP_005c]
    add_relevance:
      - { section: "SC", weight_multiplier: 1.2 }  # Supply chain important
      - { section: "EX", weight_multiplier: 1.3 }  # Export focus
      
  agriculture_sector:
    trigger: { question_id: "BP_005", operator: "equals", value: "agriculture" }
    show_questions: [BP_005d]
    add_relevance:
      - { question_id: "EX_005", priority: "high" }  # Certifications
      - { question_id: "SC_003", priority: "high" }  # Sourcing
```

## 15.3 Country-Based Conditionals

```yaml
country_conditionals:
  
  egypt:
    trigger: { question_id: "BP_003", operator: "equals", value: "EG" }
    adjustments:
      - { question_id: "FH_002", default: "EGP" }
      - { question_id: "CC_002", note: "Tax season reminder" }
      
  saudi_arabia:
    trigger: { question_id: "BP_003", operator: "equals", value: "SA" }
    adjustments:
      - { question_id: "FH_002", default: "SAR" }
      - { question_id: "EX_005", add_option: "saso" }  # SASO certification
      
  uae:
    trigger: { question_id: "BP_003", operator: "equals", value: "AE" }
    adjustments:
      - { question_id: "FH_002", default: "AED" }
      - { question_id: "BP_008", add_option: "freezone" }
      
  jordan:
    trigger: { question_id: "BP_003", operator: "equals", value: "JO" }
    adjustments:
      - { question_id: "FH_002", default: "JOD" }
      
  lebanon:
    trigger: { question_id: "BP_003", operator: "equals", value: "LB" }
    adjustments:
      - { question_id: "FH_002", default: "USD" }  # Dollarized economy
      - { question_id: "FH_005", note: "Consider economic context" }
      
  morocco:
    trigger: { question_id: "BP_003", operator: "equals", value: "MA" }
    adjustments:
      - { question_id: "FH_002", default: "MAD" }
      - { question_id: "EX_004", highlight: ["EUROPE", "AFRICA_SUB"] }
```

---

# 16. Lens-Based Routing

This section defines how the selected lens(es) affect question routing, weighting, and agent activation.

## 16.1 Lens Configuration

```yaml
lens_configurations:
  
  EYE-001:  # Export Expansion
    name: "Export Expansion"
    primary_sections: [EX, CC, BR]
    secondary_sections: [OP, SC, DM]
    required_questions: [EX_001, EX_004, EX_005, EX_013]
    primary_agents: [RICARDO, LANDOR]
    weight_adjustments:
      - { section: "EX", multiplier: 1.5 }
      - { section: "CC", multiplier: 1.3 }
      - { question_id: "BR_011", multiplier: 1.4 }  # Export marketing
      
  EYE-002:  # Investment Readiness
    name: "Investment Readiness"
    primary_sections: [FH, CC, OP]
    secondary_sections: [MK, DM]
    required_questions: [FH_001, FH_003, FH_004, FH_010, FH_011, CC_001, CC_002]
    primary_agents: [GRAHAM, DRUCKER]
    weight_adjustments:
      - { section: "FH", multiplier: 1.5 }
      - { section: "CC", multiplier: 1.4 }
      - { question_id: "FH_018", multiplier: 1.5 }  # Unit economics
      
  EYE-003:  # Digital Transformation
    name: "Digital Transformation"
    primary_sections: [DM, OP]
    secondary_sections: [WF, MK]
    required_questions: [DM_001, DM_002, DM_003, DM_005, DM_010, DM_012]
    primary_agents: [LOVELACE, MARVIN]
    weight_adjustments:
      - { section: "DM", multiplier: 1.5 }
      - { question_id: "OP_008", multiplier: 1.3 }  # Planning systems
      - { question_id: "OP_011", multiplier: 1.3 }  # Inventory systems
      
  EYE-004:  # Operations Excellence
    name: "Operations Excellence"
    primary_sections: [OP, SC]
    secondary_sections: [DM, WF]
    required_questions: [OP_001, OP_003, OP_004, OP_005, OP_006, OP_015]
    primary_agents: [MARVIN, OHNO, DEMING]
    weight_adjustments:
      - { section: "OP", multiplier: 1.5 }
      - { section: "SC", multiplier: 1.3 }
      
  EYE-005:  # Market Expansion
    name: "Market Expansion"
    primary_sections: [MK, BR]
    secondary_sections: [DM, OP]
    required_questions: [MK_001, MK_002, MK_004, MK_006, MK_009]
    primary_agents: [PORTER, LANDOR]
    weight_adjustments:
      - { section: "MK", multiplier: 1.5 }
      - { section: "BR", multiplier: 1.3 }
      
  EYE-006:  # Brand Building
    name: "Brand Building"
    primary_sections: [BR, MK]
    secondary_sections: [DM]
    required_questions: [BR_001, BR_002, BR_003, BR_005, BR_008]
    primary_agents: [LANDOR, PORTER]
    weight_adjustments:
      - { section: "BR", multiplier: 1.5 }
      - { question_id: "MK_004", multiplier: 1.3 }  # Competitive advantage
      
  EYE-007:  # Workforce Development
    name: "Workforce Development"
    primary_sections: [WF]
    secondary_sections: [OP, DM]
    required_questions: [WF_001, WF_002, WF_005, WF_006, WF_007, WF_008]
    primary_agents: [MAYO]
    weight_adjustments:
      - { section: "WF", multiplier: 1.5 }
      
  EYE-008:  # Supply Chain Optimization
    name: "Supply Chain Optimization"
    primary_sections: [SC, OP]
    secondary_sections: [DM]
    required_questions: [SC_001, SC_002, SC_004, SC_005, SC_009, SC_011]
    primary_agents: [OHNO, MARVIN]
    weight_adjustments:
      - { section: "SC", multiplier: 1.5 }
      - { question_id: "OP_011", multiplier: 1.3 }  # Inventory
      
  EYE-009:  # Sustainability & ESG
    name: "Sustainability & ESG"
    primary_sections: [OP, CC]
    secondary_sections: [SC, BR]
    required_questions: [OP_013, OP_016, CC_006, SC_003]
    primary_agents: [DEMING, MARVIN]
    weight_adjustments:
      - { question_id: "OP_013", multiplier: 1.5 }  # ISO 14001
      - { question_id: "OP_016", multiplier: 1.3 }  # Safety
      
  EYE-010:  # Innovation & R&D
    name: "Innovation & R&D"
    primary_sections: [DM, OP]
    secondary_sections: [MK, WF]
    required_questions: [DM_006, DM_010, MK_004]
    primary_agents: [LOVELACE, PORTER]
    weight_adjustments:
      - { question_id: "DM_006", multiplier: 1.5 }  # AI adoption
      
  EYE-011:  # Customer Experience
    name: "Customer Experience"
    primary_sections: [MK, BR]
    secondary_sections: [DM, OP]
    required_questions: [MK_001, MK_007, MK_008, OP_009, OP_010]
    primary_agents: [PORTER, LANDOR]
    weight_adjustments:
      - { question_id: "MK_007", multiplier: 1.5 }  # Customer satisfaction
      - { question_id: "MK_008", multiplier: 1.5 }  # Customer metrics
      
  EYE-012:  # Cost Optimization
    name: "Cost Optimization"
    primary_sections: [FH, OP, SC]
    secondary_sections: [WF]
    required_questions: [FH_004, FH_019, OP_003, SC_002, SC_011]
    primary_agents: [GRAHAM, MARVIN, OHNO]
    weight_adjustments:
      - { question_id: "FH_004", multiplier: 1.5 }  # Gross margin
      - { question_id: "FH_019", multiplier: 1.3 }  # OpEx
      
  EYE-013:  # Risk Management
    name: "Risk Management"
    primary_sections: [CC, FH, SC]
    secondary_sections: [OP]
    required_questions: [CC_005, CC_006, FH_016, SC_008, SC_009]
    primary_agents: [DEMING, GRAHAM]
    weight_adjustments:
      - { section: "CC", multiplier: 1.4 }
      - { question_id: "SC_009", multiplier: 1.5 }  # Backup suppliers
      
  EYE-014:  # Succession Planning
    name: "Succession Planning"
    primary_sections: [WF, CC]
    secondary_sections: [FH]
    required_questions: [WF_008, WF_010, CC_007]
    primary_agents: [MAYO, DRUCKER]
    weight_adjustments:
      - { question_id: "WF_010", multiplier: 1.5 }  # Succession planning
      - { question_id: "WF_008", multiplier: 1.3 }  # Org structure
      
  EYE-015:  # Partnership Development
    name: "Partnership Development"
    primary_sections: [MK, SC]
    secondary_sections: [BR]
    required_questions: [MK_006, SC_001, SC_005]
    primary_agents: [PORTER, OHNO]
    weight_adjustments:
      - { question_id: "MK_006", multiplier: 1.3 }  # Customer acquisition
      
  EYE-CREMA:  # The Crema (Quick Wins)
    name: "The Crema - Quick Wins"
    primary_sections: [QW]
    secondary_sections: [ALL]  # All sections contribute to quick wins
    required_questions: [QW_001, QW_002, QW_003, QW_005, QW_010]
    primary_agents: [DRUCKER]  # All agents contribute
    weight_adjustments:
      - { section: "QW", multiplier: 2.0 }  # Double weight for quick win section
    special_processing:
      filter_by: "quick_win_indicator"
      effort_level_routing: true
      time_horizon: [30, 60, 90]
      
  EYE-CUSTOM:  # Custom Objective
    name: "Custom Objective"
    primary_sections: []  # Determined by user input
    required_questions: [LS_003]  # Custom objective text
    primary_agents: [DRUCKER]  # Orchestrator assigns
    weight_adjustments: []  # Dynamic based on objective analysis
```

## 16.2 Multi-Lens Combinations

```yaml
lens_combinations:
  
  # Common combinations and their interactions
  export_investment:
    lenses: [EYE-001, EYE-002]
    synergy_sections: [CC, FH]
    combined_weight: 1.6
    note: "Export + Investment focus on compliance and financial readiness"
    
  digital_operations:
    lenses: [EYE-003, EYE-004]
    synergy_sections: [OP, DM]
    combined_weight: 1.5
    note: "Digital + Operations focus on system-enabled efficiency"
    
  market_brand:
    lenses: [EYE-005, EYE-006]
    synergy_sections: [MK, BR]
    combined_weight: 1.5
    note: "Market + Brand focus on competitive positioning"
    
  crema_any:
    lenses: [EYE-CREMA, ANY]
    behavior: "Crema filters recommendations from primary lens"
    quick_win_filter: true
```

---

# 17. Validation Rules

This section defines input validation, business logic validation, and data quality checks.

## 17.1 Input Validation

```yaml
input_validation:
  
  text_fields:
    BP_001:  # Legal name
      min_length: 2
      max_length: 200
      pattern: "^[\\p{L}\\p{N}\\s\\-\\.\\,\\&]+$"
      error_message:
        en: "Please enter a valid company name"
        ar: "يرجى إدخال اسم شركة صالح"
        
    BP_002:  # Trade name
      min_length: 1
      max_length: 100
      allow_empty: true
      
  numeric_fields:
    FH_001:  # Annual revenue
      min: 0
      max: 10000000000  # 10B cap
      allow_zero: true
      
    FH_019:  # Monthly OpEx
      min: 0
      max: 100000000
      
    BP_004:  # Founding year
      min: 1800
      max: current_year
      
  percentage_fields:
    validation: { min: 0, max: 100, decimals: 1 }
    applies_to: [FH_003, FH_004, FH_005, OP_004, EX_003]
    
  scale_fields:
    validation: { min: 1, max: 5, step: 1, integers_only: true }
    applies_to: [BP_012, OP_003, DM_001, WF_002, MK_007]
    
  ranking_fields:
    validation: { no_duplicates: true, all_items_ranked: true }
    applies_to: [BP_010, QW_005]
```

## 17.2 Business Logic Validation

```yaml
business_logic_validation:
  
  financial_consistency:
    - rule: "gross_margin >= net_margin"
      fields: [FH_004, FH_005]
      error_message:
        en: "Gross margin should be greater than or equal to net margin"
        ar: "هامش الربح الإجمالي يجب أن يكون أكبر من أو يساوي صافي الهامش"
        
    - rule: "cash_runway_months * monthly_opex <= annual_revenue * 2"
      fields: [FH_006, FH_019, FH_001]
      severity: "warning"
      message:
        en: "Cash runway seems inconsistent with revenue and expenses"
        
  operational_consistency:
    - rule: "if capacity_utilization > 95% then no_major_capacity_constraint"
      fields: [OP_004, OP_015]
      severity: "warning"
      message:
        en: "High capacity utilization typically indicates capacity constraints"
        
  export_consistency:
    - rule: "if export_focused then export_revenue >= 50%"
      fields: [EX_001, EX_003]
      severity: "warning"
      
  date_consistency:
    - rule: "founding_year <= current_year"
      fields: [BP_004]
```

## 17.3 Data Quality Scoring

```yaml
data_quality_scoring:
  
  completeness:
    weight: 0.4
    calculation: "answered_questions / total_questions"
    thresholds:
      excellent: 0.95
      good: 0.85
      acceptable: 0.70
      poor: 0.50
      
  confidence:
    weight: 0.3
    factors:
      - "unsure_responses"  # Penalty for "not sure" answers
      - "numeric_precision"  # Bonus for exact numbers vs ranges
      - "human_context_provided"  # Bonus for context
      
  consistency:
    weight: 0.3
    checks:
      - "cross_field_validation"
      - "temporal_consistency"
      - "financial_ratios"
```

---

# 18. Agent Data Mapping

This section defines how questionnaire responses map to agent inputs and dimension scores.

## 18.1 Primary Agent Mappings

```yaml
agent_data_mapping:
  
  DRUCKER:  # The Supervisor
    primary_inputs:
      - BP_010  # Strategic priorities
      - BP_011  # Diagnostic motivation
      - BP_013  # Primary challenge
      - QW_001  # Decision speed
      - QW_005  # Quick win priorities
      - QW_010  # Action commitment
    secondary_inputs:
      - BP_007  # Respondent role
      - BP_012  # Self-assessment
    outputs:
      - orchestration_weights
      - agent_activation_sequence
      - report_structure
      
  GRAHAM:  # The Numbers Whisperer
    primary_inputs:
      - FH_001 through FH_020  # All financial section
      - QW_002  # Quick improvement budget
    secondary_inputs:
      - BP_006  # Employee count (for ratio analysis)
      - OP_012  # Inventory turnover
    outputs:
      - dimension_2_score  # Financial Health
      - financial_benchmark_comparison
      - investment_readiness_score
      
  MARVIN:  # The Optimizer
    primary_inputs:
      - OP_001 through OP_018  # All operations section
    secondary_inputs:
      - DM_002  # Core systems (for ops integration)
      - SC_011  # Supply chain challenges
    outputs:
      - dimension_6_score  # Operations Performance
      - efficiency_opportunities
      - process_improvement_roadmap
      
  LOVELACE:  # The Digitizer
    primary_inputs:
      - DM_001 through DM_013  # All digital section
      - FH_013  # Accounting system
      - OP_008  # Production planning system
      - OP_011  # Inventory management
    secondary_inputs:
      - WF_011  # Digital readiness
      - QW_010  # Quick tool adoption
    outputs:
      - dimension_3_score  # Digital Maturity
      - technology_roadmap
      - digital_quick_wins
      
  MAYO:  # The People Person
    primary_inputs:
      - WF_001 through WF_011  # All workforce section
      - QW_003  # Staff availability
      - QW_004  # Change readiness
    secondary_inputs:
      - BP_006  # Employee count
      - OP_016  # Safety management
    outputs:
      - dimension_7_score  # Workforce & Culture
      - hr_development_plan
      - retention_recommendations
      
  PORTER:  # The Strategist
    primary_inputs:
      - MK_001 through MK_010  # All market section
      - BP_009  # Geographic scope
    secondary_inputs:
      - BR_001  # Brand awareness
      - EX_004  # Target export markets
    outputs:
      - dimension_9_score  # Market Position
      - competitive_analysis
      - growth_strategy
      
  OHNO:  # The Flow Master
    primary_inputs:
      - SC_001 through SC_012  # All supply chain section
      - OP_009  # Lead time
      - OP_010  # On-time delivery
      - OP_011  # Inventory management
    secondary_inputs:
      - EX_006  # Export logistics
    outputs:
      - dimension_8_score  # Supply Chain
      - supply_chain_optimization_plan
      - risk_mitigation_recommendations
      
  DEMING:  # The Perfectionist
    primary_inputs:
      - OP_006  # Defect rate
      - OP_007  # Operations methodology
      - OP_013  # Quality certifications
      - OP_017  # SOPs
      - CC_001 through CC_008  # Compliance section
    secondary_inputs:
      - EX_005  # Export certifications
      - SC_005  # Supplier evaluation
    outputs:
      - dimension_4_score  # Systems & Processes
      - dimension_10_score  # Compliance & Governance
      - quality_improvement_roadmap
      
  RICARDO:  # The Globalizer
    primary_inputs:
      - EX_001 through EX_015  # All export section
    secondary_inputs:
      - BP_009  # Geographic scope
      - SC_003  # Sourcing geography
    outputs:
      - dimension_11_score  # Export Readiness
      - market_entry_recommendations
      - export_action_plan
      
  LANDOR:  # The Storyteller
    primary_inputs:
      - BR_001 through BR_010  # All brand section
      - EX_011  # Export marketing materials
    secondary_inputs:
      - MK_004  # Competitive advantage
      - DM_004  # Website status
    outputs:
      - brand_strategy_recommendations
      - marketing_action_plan
      - communication_framework
      
  TUFTE:  # The Visualizer
    primary_inputs:
      - ALL_SECTIONS  # Receives all data for visualization
    outputs:
      - dimension_radar_chart
      - benchmark_comparisons
      - progress_tracking_dashboards
```

## 18.2 Dimension Score Calculations

```yaml
dimension_calculations:
  
  D1_Business_Profile:
    primary_questions: [BP_001, BP_003, BP_004, BP_005, BP_006, BP_008]
    weight_distribution:
      company_maturity: 0.3  # From founding year
      company_size: 0.3  # From employee count
      legal_structure: 0.2
      geographic_scope: 0.2
      
  D2_Financial_Health:
    primary_questions: [FH_001, FH_003, FH_004, FH_005, FH_006, FH_016, FH_018]
    weight_distribution:
      revenue_growth: 0.2
      profitability: 0.25
      cash_position: 0.2
      leverage: 0.15
      unit_economics: 0.2
    benchmark_by: [sector, country, size]
    
  D3_Digital_Maturity:
    primary_questions: [DM_001, DM_002, DM_003, DM_005, DM_006, DM_007, DM_012]
    weight_distribution:
      self_assessment: 0.15
      systems_adoption: 0.25
      integration: 0.2
      data_usage: 0.2
      cybersecurity: 0.1
      strategy: 0.1
      
  D4_Systems_Processes:
    primary_questions: [OP_007, OP_017, FH_017, CC_007, WF_006]
    weight_distribution:
      methodology: 0.25
      documentation: 0.25
      budgeting: 0.2
      policies: 0.15
      performance_mgmt: 0.15
      
  D5_Product_Service:
    primary_questions: [OP_001, EX_010, MK_004]
    weight_distribution:
      business_model: 0.4
      product_adaptation: 0.3
      differentiation: 0.3
      
  D6_Operations:
    primary_questions: [OP_003, OP_004, OP_005, OP_006, OP_010, OP_014]
    weight_distribution:
      efficiency: 0.2
      capacity: 0.15
      oee: 0.2
      quality: 0.2
      delivery: 0.15
      maintenance: 0.1
      
  D7_Workforce:
    primary_questions: [WF_001, WF_002, WF_005, WF_006, WF_008, WF_009]
    weight_distribution:
      composition: 0.15
      retention: 0.2
      training: 0.2
      performance: 0.15
      structure: 0.15
      culture: 0.15
      
  D8_Supply_Chain:
    primary_questions: [SC_002, SC_004, SC_005, SC_009, SC_010]
    weight_distribution:
      concentration: 0.2
      reliability: 0.25
      evaluation: 0.2
      resilience: 0.2
      communication: 0.15
      
  D9_Market:
    primary_questions: [MK_002, MK_004, MK_005, MK_007, MK_008]
    weight_distribution:
      position: 0.25
      advantage: 0.25
      share: 0.15
      satisfaction: 0.2
      metrics: 0.15
      
  D10_Compliance:
    primary_questions: [CC_001, CC_002, CC_003, CC_004, CC_005, CC_006]
    weight_distribution:
      business: 0.2
      tax: 0.2
      labor: 0.2
      licenses: 0.15
      contracts: 0.15
      insurance: 0.1
      
  D11_Export:
    primary_questions: [EX_001, EX_003, EX_005, EX_009, EX_012]
    weight_distribution:
      status: 0.2
      revenue: 0.2
      certifications: 0.25
      documentation: 0.2
      regulatory: 0.15
```

---

# 19. Implementation Guide

This section provides guidance for frontend implementation and backend processing.

## 19.1 Frontend Implementation

```yaml
frontend_guidelines:
  
  question_rendering:
    - Use progressive disclosure based on conditional logic
    - Show estimated completion time per section
    - Implement auto-save every 30 seconds
    - Support bilingual toggle (EN/AR) at any point
    
  input_types:
    single_choice:
      component: "RadioGroup"
      behavior: "Select one, auto-advance on selection"
      
    multiple_choice:
      component: "CheckboxGroup"
      behavior: "Select multiple, require explicit continue"
      max_selections: "defined per question"
      
    scale:
      component: "Slider or RadioGroup"
      show_labels: true
      animate_selection: true
      
    ranking:
      component: "DragAndDrop"
      behavior: "Reorder items by importance"
      
    currency:
      component: "NumberInput with currency selector"
      format: "locale-aware"
      
    percentage:
      component: "NumberInput with % suffix"
      validation: "0-100"
      
    text_short:
      component: "TextInput"
      max_chars: 200
      
    text_long:
      component: "TextArea"
      max_chars: 1000
      
    human_context:
      component: "TextArea with prompt"
      show_prompt: true
      optional_emphasis: true
      
  accessibility:
    - WCAG 2.1 AA compliance
    - RTL support for Arabic
    - Keyboard navigation
    - Screen reader optimization
    - High contrast mode support
```

## 19.2 State Management

```yaml
state_management:
  
  response_state:
    structure:
      session_id: "uuid"
      user_id: "uuid"
      lens_selection:
        primary: "EYE-XXX"
        secondary: ["EYE-XXX"]
        crema_active: boolean
      responses:
        - question_id: "string"
          value: "any"
          human_context: "string | null"
          timestamp: "ISO datetime"
          confidence: "number"
      progress:
        current_section: "string"
        completed_sections: ["string"]
        completion_percentage: "number"
      metadata:
        started_at: "ISO datetime"
        last_updated: "ISO datetime"
        locale: "en | ar"
        platform: "web | mobile"
        
  persistence:
    local_storage: true  # For offline support
    sync_interval: "30 seconds"
    conflict_resolution: "latest_timestamp_wins"
```

## 19.3 API Endpoints

```yaml
api_specification:
  
  endpoints:
    
    POST /questionnaire/start:
      request:
        user_id: string
        locale: "en" | "ar"
      response:
        session_id: string
        lens_selection_questions: Question[]
        
    POST /questionnaire/lens:
      request:
        session_id: string
        primary_lens: string
        secondary_lenses: string[]
        crema_active: boolean
      response:
        sections: Section[]
        estimated_time: number
        
    POST /questionnaire/response:
      request:
        session_id: string
        question_id: string
        value: any
        human_context?: string
      response:
        success: boolean
        next_questions?: Question[]
        validation_errors?: Error[]
        
    GET /questionnaire/progress/{session_id}:
      response:
        completion_percentage: number
        sections_complete: string[]
        estimated_remaining: number
        
    POST /questionnaire/submit:
      request:
        session_id: string
      response:
        diagnostic_id: string
        processing_status: "queued" | "processing"
        estimated_completion: number
```

## 19.4 Processing Pipeline

```yaml
processing_pipeline:
  
  stages:
    
    1_validation:
      - Input validation
      - Business logic checks
      - Data quality scoring
      duration: "< 1 second"
      
    2_enrichment:
      - Lookup sector benchmarks
      - Apply country context
      - Calculate derived metrics
      duration: "< 2 seconds"
      
    3_dimension_scoring:
      - Calculate 11 dimension scores
      - Apply lens weights
      - Generate confidence intervals
      duration: "< 3 seconds"
      
    4_agent_processing:
      - Route data to relevant agents
      - Parallel agent analysis
      - Aggregate recommendations
      duration: "5-15 seconds per agent"
      
    5_crema_filtering:
      - If Crema active:
        - Filter by quick_win_indicator
        - Sort by effort_level
        - Assign to 30/60/90 day buckets
      duration: "< 2 seconds"
      
    6_report_generation:
      - Compile diagnostic report
      - Generate visualizations
      - Create action plan
      duration: "< 5 seconds"
      
    7_delivery:
      - Store in database
      - Notify user
      - Queue for follow-up
      duration: "< 1 second"
```

---

# Appendix A: Question Count Summary

```yaml
question_counts:
  
  by_section:
    LS: 3    # Pre-Questionnaire: Lens Selection
    BP: 15   # Business Profile
    FH: 20   # Financial Health
    OP: 18   # Operations & Production
    DM: 13   # Digital Maturity
    WF: 11   # Workforce & HR
    MK: 10   # Market & Competition
    SC: 12   # Supply Chain
    EX: 15   # Export Readiness
    BR: 10   # Brand & Marketing
    CC: 8    # Compliance & Certifications
    QW: 10   # Quick Win Assessment (NEW)
    
  totals:
    all_questions: 145
    with_followups: ~160
    required_minimum: ~50  # With aggressive conditional logic
    typical_completion: ~80-100  # Depends on lens and sector
    
  by_type:
    single_choice: 85
    multiple_choice: 32
    scale: 15
    text_short: 2
    text_long: 1
    human_context: 12
    currency: 3
    percentage: 5
    ranking: 2
```

---

# Appendix B: Change Log

```yaml
changelog:
  
  v2.0.0 (January 2026):
    author: "Tee (The Ionganic Orchestrator - TIO)"
    changes:
      - Added Pre-Questionnaire Lens Selection section (LS_001-LS_003)
      - Added Quick Win Assessment section (QW_001-QW_010)
      - Added lens_relevance field to all questions
      - Added quick_win_indicator field for Crema filtering
      - Added effort_level to QuestionOption schema
      - Updated country list to 6 countries (EG, SA, AE, JO, LB, MA)
      - Removed Tunisia from country coverage
      - Added human_context_prompt field for &I integration
      - Added allows_human_context field
      - Enhanced conditional logic with lens-based routing
      - Added comprehensive validation rules
      - Added agent data mapping documentation
      - Updated TypeScript interfaces
      - Added bilingual (EN/AR) support throughout
      - Version aligned with 31 sector knowledge packs v2.0
      
  v1.0.0 (December 2025):
    author: "RootRise Product Team"
    changes:
      - Initial production release
      - 10 core sections
      - ~145 questions
      - Basic conditional logic
```

---

# Appendix C: Integration Points

```yaml
integration_points:
  
  sector_knowledge_packs:
    version: "v2.0"
    count: 31
    integration: "BP_005 sector selection triggers pack loading"
    
  lens_system:
    version: "v1.2"
    count: 17
    integration: "LS_001 lens selection routes to lens configurations"
    
  agent_architecture:
    version: "v1.1"
    count: 11
    integration: "Agent mappings defined in Section 18"
    
  blueprint:
    version: "v1.2"
    integration: "Schema implements Blueprint specifications"
```

---

*Document generated: January 2026*
*RootRise Questionnaire Schema v2.0*
*Part of the RootRise &I SME Transformation Platform*
