# RootRise Diagnostic Questionnaire Schema
## Version 1.0 | December 2025

---

# Table of Contents

1. [Schema Overview](#1-schema-overview)
2. [Master Data Model](#2-master-data-model)
3. [Section 1: Business Profile](#3-section-1-business-profile)
4. [Section 2: Financial Health](#4-section-2-financial-health)
5. [Section 3: Operations & Production](#5-section-3-operations--production)
6. [Section 4: Digital Maturity](#6-section-4-digital-maturity)
7. [Section 5: Workforce & HR](#7-section-5-workforce--hr)
8. [Section 6: Market & Competition](#8-section-6-market--competition)
9. [Section 7: Supply Chain](#9-section-7-supply-chain)
10. [Section 8: Export Readiness](#10-section-8-export-readiness)
11. [Section 9: Brand & Marketing](#11-section-9-brand--marketing)
12. [Section 10: Compliance & Certifications](#12-section-10-compliance--certifications)
13. [Conditional Logic Rules](#13-conditional-logic-rules)
14. [Validation Rules](#14-validation-rules)
15. [Agent Data Mapping](#15-agent-data-mapping)
16. [Implementation Guide](#16-implementation-guide)

---

# 1. Schema Overview

## 1.1 Purpose

This questionnaire schema defines the complete set of questions presented to SME owners during the RootRise diagnostic process. The schema maps every question to specific diagnostic agents, ensuring data flows correctly through The Pantheon multi-agent system.

## 1.2 Design Principles

| Principle | Description |
|-----------|-------------|
| **Conversational** | Questions feel like a consultation, not a form |
| **Progressive** | Core questions first, detailed questions unlock based on responses |
| **Agent-Aligned** | Every question maps to specific agent data requirements |
| **&I Philosophy** | Human context injection points throughout |
| **MENA-Ready** | Arabic translations, regional context options |
| **Time-Respectful** | 20-30 minutes total, with save/resume capability |

## 1.3 Question Types

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
  | 'country_select'     // Country dropdown
  | 'sector_select'      // Sector/subsector cascading
  | 'human_context';     // Open field for user expertise injection
```

## 1.4 Estimated Completion Times

| Section | Questions | Est. Time | Condition |
|---------|-----------|-----------|-----------|
| Business Profile | 15 | 3 min | Always |
| Financial Health | 20 | 5 min | Always |
| Operations | 18 | 4 min | Always |
| Digital Maturity | 12 | 3 min | If Add-on selected |
| Workforce | 14 | 3 min | If Add-on selected |
| Market | 10 | 2 min | If Add-on selected |
| Supply Chain | 12 | 3 min | If Add-on selected |
| Export | 15 | 4 min | If Add-on selected |
| Brand | 10 | 2 min | If Add-on selected |
| Compliance | 8 | 2 min | Contextual |
| **TOTAL (Core)** | **53** | **12 min** | - |
| **TOTAL (Full)** | **134** | **31 min** | - |

---

# 2. Master Data Model

## 2.1 Question Schema

```typescript
interface Question {
  // Identity
  id: string;                           // Unique ID: "BP_001", "FH_012"
  section: SectionCode;                 // Section code: "BP", "FH", "OP", etc.
  subsection?: string;                  // Optional grouping within section
  order: number;                        // Display order within section
  
  // Content
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
  
  // &I Philosophy
  allows_human_context: boolean;        // Can user add explanatory note
  human_context_prompt?: {
    en: string;
    ar: string;
  };
  confidence_impact: 'high' | 'medium' | 'low';  // How much this affects confidence
}

interface QuestionOption {
  value: string;                        // Stored value
  label: {
    en: string;
    ar: string;
  };
  score?: number;                       // Optional numeric value for calculations
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

type SectionCode = 'BP' | 'FH' | 'OP' | 'DM' | 'WF' | 'MK' | 'SC' | 'EX' | 'BR' | 'CC';
type AgentCode = 'DRUCKER' | 'MARVIN' | 'GRAHAM' | 'LOVELACE' | 'MAYO' | 'PORTER' | 'OHNO' | 'RICARDO' | 'LANDOR' | 'DEMING' | 'TUFTE';
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

# 3. Section 1: Business Profile

**Section Code:** `BP`
**Primary Agents:** Drucker (Supervisor), All Agents
**Estimated Time:** 3 minutes
**Condition:** Always shown

## 3.1 Questions

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

BP_002:
  text:
    en: "What is your company's trade name or brand name (if different)?"
    ar: "ما هو الاسم التجاري أو العلامة التجارية لشركتك (إن كان مختلفاً)؟"
  type: text_short
  required: false
  agents: [DRUCKER, LANDOR]
  data_field: trade_name
  confidence_impact: low

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
    - { value: "MA", label: { en: "Morocco", ar: "المغرب" } }
    - { value: "TN", label: { en: "Tunisia", ar: "تونس" } }
    - { value: "LB", label: { en: "Lebanon", ar: "لبنان" } }
    - { value: "OTHER", label: { en: "Other", ar: "أخرى" } }
  agents: [DRUCKER, RICARDO]
  data_field: headquarters_country
  dimension: 11
  confidence_impact: high

BP_004:
  text:
    en: "What year was your company founded?"
    ar: "في أي سنة تأسست شركتك؟"
  type: numeric
  numeric_config:
    min: 1900
    max: 2025
    format: integer
  required: true
  agents: [DRUCKER, GRAHAM]
  data_field: founding_year
  confidence_impact: medium

BP_005:
  text:
    en: "Which industry best describes your company's primary business?"
    ar: "ما هو القطاع الذي يصف عمل شركتك الرئيسي بشكل أفضل؟"
  type: sector_select
  required: true
  options:
    # Food & Beverage Manufacturing
    - value: "FBM"
      label: { en: "Food & Beverage Manufacturing", ar: "تصنيع الأغذية والمشروبات" }
      triggers_followup: [BP_005a_FBM]
    # Light Manufacturing
    - value: "LMT"
      label: { en: "Light Manufacturing / Textiles", ar: "الصناعات الخفيفة / المنسوجات" }
      triggers_followup: [BP_005a_LMT]
    # Tech / Digital
    - value: "TDS"
      label: { en: "Tech / Digital Services", ar: "التكنولوجيا / الخدمات الرقمية" }
      triggers_followup: [BP_005a_TDS]
    # Healthcare
    - value: "HCR"
      label: { en: "Healthcare & Medical", ar: "الرعاية الصحية والطبية" }
      triggers_followup: [BP_005a_HCR]
    # Construction
    - value: "CON"
      label: { en: "Construction & Building", ar: "البناء والتشييد" }
      triggers_followup: [BP_005a_CON]
    # Retail & Trade
    - value: "RET"
      label: { en: "Retail & Trade", ar: "التجزئة والتجارة" }
      triggers_followup: [BP_005a_RET]
    # Professional Services
    - value: "PRO"
      label: { en: "Professional Services", ar: "الخدمات المهنية" }
      triggers_followup: [BP_005a_PRO]
    # Other sectors...
    - value: "OTH"
      label: { en: "Other", ar: "أخرى" }
      triggers_followup: [BP_005a_OTH]
  agents: [DRUCKER, ALL]
  data_field: primary_sector
  dimension: 1
  confidence_impact: high

BP_005a_FBM:
  text:
    en: "What type of food & beverage products do you manufacture?"
    ar: "ما نوع منتجات الأغذية والمشروبات التي تصنعها؟"
  type: multiple_choice
  required: true
  conditional:
    - { question_id: BP_005, operator: "equals", value: "FBM" }
  options:
    - { value: "dairy", label: { en: "Dairy Products", ar: "منتجات الألبان" } }
    - { value: "baked", label: { en: "Baked Goods", ar: "المخبوزات" } }
    - { value: "beverages", label: { en: "Beverages (non-alcoholic)", ar: "المشروبات (غير كحولية)" } }
    - { value: "snacks", label: { en: "Snacks & Confectionery", ar: "الوجبات الخفيفة والحلويات" } }
    - { value: "sauces", label: { en: "Sauces & Condiments", ar: "الصلصات والتوابل" } }
    - { value: "meat", label: { en: "Meat & Poultry Processing", ar: "معالجة اللحوم والدواجن" } }
    - { value: "frozen", label: { en: "Frozen Foods", ar: "الأغذية المجمدة" } }
    - { value: "organic", label: { en: "Organic / Health Foods", ar: "الأغذية العضوية / الصحية" } }
    - { value: "other", label: { en: "Other", ar: "أخرى" } }
  agents: [DRUCKER, MARVIN, OHNO]
  data_field: subsector
  dimension: 1
  confidence_impact: high

BP_005a_LMT:
  text:
    en: "What type of textiles or light manufacturing do you produce?"
    ar: "ما نوع المنسوجات أو الصناعات الخفيفة التي تنتجها؟"
  type: multiple_choice
  required: true
  conditional:
    - { question_id: BP_005, operator: "equals", value: "LMT" }
  options:
    - { value: "apparel", label: { en: "Apparel / Clothing", ar: "الملابس" } }
    - { value: "home_textiles", label: { en: "Home Textiles", ar: "منسوجات منزلية" } }
    - { value: "technical", label: { en: "Technical Textiles", ar: "منسوجات تقنية" } }
    - { value: "leather", label: { en: "Leather Goods", ar: "المنتجات الجلدية" } }
    - { value: "footwear", label: { en: "Footwear", ar: "الأحذية" } }
    - { value: "accessories", label: { en: "Fashion Accessories", ar: "إكسسوارات الموضة" } }
    - { value: "other", label: { en: "Other", ar: "أخرى" } }
  agents: [DRUCKER, MARVIN, OHNO]
  data_field: subsector
  dimension: 1
  confidence_impact: high

BP_005a_TDS:
  text:
    en: "What type of technology or digital services do you provide?"
    ar: "ما نوع خدمات التكنولوجيا أو الخدمات الرقمية التي تقدمها؟"
  type: multiple_choice
  required: true
  conditional:
    - { question_id: BP_005, operator: "equals", value: "TDS" }
  options:
    - { value: "saas", label: { en: "SaaS / Software Products", ar: "البرمجيات كخدمة / منتجات برمجية" } }
    - { value: "dev_services", label: { en: "Custom Software Development", ar: "تطوير البرمجيات المخصصة" } }
    - { value: "mobile", label: { en: "Mobile App Development", ar: "تطوير تطبيقات الهاتف" } }
    - { value: "data_ai", label: { en: "Data / AI / Analytics", ar: "البيانات / الذكاء الاصطناعي / التحليلات" } }
    - { value: "cloud", label: { en: "Cloud Services / Infrastructure", ar: "الخدمات السحابية / البنية التحتية" } }
    - { value: "cybersecurity", label: { en: "Cybersecurity", ar: "الأمن السيبراني" } }
    - { value: "digital_marketing", label: { en: "Digital Marketing / MarTech", ar: "التسويق الرقمي" } }
    - { value: "ecommerce", label: { en: "E-commerce Platform", ar: "منصة التجارة الإلكترونية" } }
    - { value: "fintech", label: { en: "FinTech", ar: "التقنية المالية" } }
    - { value: "other", label: { en: "Other", ar: "أخرى" } }
  agents: [DRUCKER, MARVIN, LOVELACE]
  data_field: subsector
  dimension: 1
  confidence_impact: high

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
    en: "Feel free to describe your specific responsibilities or decision-making authority"
    ar: "يمكنك وصف مسؤولياتك المحددة أو صلاحياتك في اتخاذ القرارات"

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

BP_009a:
  text:
    en: "Which countries do you currently operate in or sell to?"
    ar: "في أي دول تعمل حالياً أو تبيع فيها؟"
  type: multiple_choice
  required: false
  conditional:
    - { question_id: BP_009, operator: "in", value: ["regional_mena", "international"] }
  options:
    # MENA Countries
    - { value: "EG", label: { en: "Egypt", ar: "مصر" } }
    - { value: "SA", label: { en: "Saudi Arabia", ar: "السعودية" } }
    - { value: "AE", label: { en: "UAE", ar: "الإمارات" } }
    - { value: "JO", label: { en: "Jordan", ar: "الأردن" } }
    - { value: "KW", label: { en: "Kuwait", ar: "الكويت" } }
    - { value: "QA", label: { en: "Qatar", ar: "قطر" } }
    - { value: "BH", label: { en: "Bahrain", ar: "البحرين" } }
    - { value: "OM", label: { en: "Oman", ar: "عُمان" } }
    - { value: "MA", label: { en: "Morocco", ar: "المغرب" } }
    - { value: "TN", label: { en: "Tunisia", ar: "تونس" } }
    - { value: "LB", label: { en: "Lebanon", ar: "لبنان" } }
    - { value: "IQ", label: { en: "Iraq", ar: "العراق" } }
    # International (if BP_009 = international)
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
    en: "Any specific context about these priorities? (e.g., 'We lost a major customer' or 'New regulation coming')"
    ar: "أي سياق محدد حول هذه الأولويات؟"

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
  human_context_prompt:
    en: "Please share any specific situation or goal driving this diagnostic"
    ar: "يرجى مشاركة أي موقف أو هدف محدد يدفع هذا التشخيص"

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
  human_context_prompt:
    en: "This helps us focus the diagnostic on what matters most to you"
    ar: "هذا يساعدنا على تركيز التشخيص على ما يهمك أكثر"

BP_014:
  text:
    en: "Is there anything special about your business we should know upfront?"
    ar: "هل هناك شيء خاص بعملك يجب أن نعرفه مسبقاً؟"
  type: human_context
  required: false
  description:
    en: "Share any unique circumstances, recent changes, or context that would help us understand your business better. This is your opportunity to tell us what the numbers might not show."
    ar: "شارك أي ظروف فريدة أو تغييرات حديثة أو سياق يساعدنا على فهم عملك بشكل أفضل."
  agents: [DRUCKER, ALL]
  data_field: human_context_business_profile
  confidence_impact: high

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
```

---

# 4. Section 2: Financial Health

**Section Code:** `FH`
**Primary Agent:** Graham (The Alchemist)
**Estimated Time:** 5 minutes
**Condition:** Always shown (Core)

## 4.1 Questions

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
  human_context_prompt:
    en: "Note if this is exact, estimated, or if there are seasonal variations"
    ar: "أذكر إذا كان هذا دقيقاً أو تقديرياً أو إذا كانت هناك تغييرات موسمية"

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
    - { value: "EUR", label: { en: "Euro (EUR)", ar: "اليورو" } }
    - { value: "GBP", label: { en: "British Pound (GBP)", ar: "الجنيه الإسترليني" } }
    - { value: "OTHER", label: { en: "Other", ar: "أخرى" } }
  agents: [GRAHAM]
  data_field: reporting_currency
  confidence_impact: medium

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
      triggers_followup: [FH_010a]
    - value: "angel"
      label: { en: "Yes, angel investors", ar: "نعم، مستثمرين ملائكيين" }
      triggers_followup: [FH_010b]
    - value: "vc"
      label: { en: "Yes, venture capital", ar: "نعم، رأس مال مخاطر" }
      triggers_followup: [FH_010b]
    - value: "bank_loan"
      label: { en: "Yes, bank loan", ar: "نعم، قرض بنكي" }
      triggers_followup: [FH_010c]
    - value: "multiple"
      label: { en: "Multiple types", ar: "أنواع متعددة" }
      triggers_followup: [FH_010a, FH_010b, FH_010c]
  agents: [GRAHAM]
  data_field: funding_history
  dimension: 2
  confidence_impact: medium

FH_010a:
  text:
    en: "What is the total value of grants you've received?"
    ar: "ما هي القيمة الإجمالية للمنح التي حصلت عليها؟"
  type: currency
  required: false
  conditional:
    - { question_id: FH_010, operator: "in", value: ["grants", "multiple"] }
  numeric_config:
    min: 0
    currency: "USD"
  agents: [GRAHAM]
  data_field: grants_received
  confidence_impact: medium

FH_010b:
  text:
    en: "What is your current valuation or latest round valuation?"
    ar: "ما هو تقييم شركتك الحالي أو تقييم آخر جولة؟"
  type: currency
  required: false
  conditional:
    - { question_id: FH_010, operator: "in", value: ["angel", "vc", "multiple"] }
  numeric_config:
    min: 0
    currency: "USD"
  agents: [GRAHAM]
  data_field: company_valuation
  confidence_impact: medium

FH_010c:
  text:
    en: "What is your current outstanding debt balance?"
    ar: "ما هو رصيد ديونك الحالي؟"
  type: currency
  required: false
  conditional:
    - { question_id: FH_010, operator: "in", value: ["bank_loan", "multiple"] }
  numeric_config:
    min: 0
    currency: "USD"
  agents: [GRAHAM]
  data_field: outstanding_debt
  confidence_impact: medium

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
      triggers_followup: [FH_011a]
    - value: "actively_seeking"
      label: { en: "Yes, actively seeking", ar: "نعم، أبحث بشكل نشط" }
      triggers_followup: [FH_011a, FH_011b]
    - value: "in_process"
      label: { en: "Currently in fundraising process", ar: "حالياً في عملية جمع التمويل" }
      triggers_followup: [FH_011a, FH_011b]
  agents: [GRAHAM]
  data_field: funding_seeking
  confidence_impact: medium

FH_011a:
  text:
    en: "What type of funding are you seeking?"
    ar: "ما نوع التمويل الذي تبحث عنه؟"
  type: multiple_choice
  required: false
  conditional:
    - { question_id: FH_011, operator: "in", value: ["exploring", "actively_seeking", "in_process"] }
  options:
    - { value: "equity", label: { en: "Equity investment", ar: "استثمار في حقوق الملكية" } }
    - { value: "debt", label: { en: "Debt / Loan", ar: "دين / قرض" } }
    - { value: "grants", label: { en: "Grants", ar: "منح" } }
    - { value: "convertible", label: { en: "Convertible notes / SAFE", ar: "سندات قابلة للتحويل" } }
    - { value: "revenue_based", label: { en: "Revenue-based financing", ar: "تمويل قائم على الإيرادات" } }
  agents: [GRAHAM]
  data_field: funding_type_sought
  confidence_impact: medium

FH_011b:
  text:
    en: "How much funding are you seeking?"
    ar: "كم من التمويل تبحث عنه؟"
  type: currency
  required: false
  conditional:
    - { question_id: FH_011, operator: "in", value: ["actively_seeking", "in_process"] }
  numeric_config:
    min: 0
    currency: "USD"
  agents: [GRAHAM]
  data_field: funding_amount_sought
  confidence_impact: medium

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
    - { value: "excel", label: { en: "Spreadsheets (Excel/Sheets)", ar: "جداول بيانات" }, score: 30 }
    - { value: "paper", label: { en: "Paper records", ar: "سجلات ورقية" }, score: 10 }
  agents: [GRAHAM, LOVELACE]
  data_field: accounting_system
  dimension: 6
  confidence_impact: medium

FH_014:
  text:
    en: "How often do you review financial reports?"
    ar: "كم مرة تراجع التقارير المالية؟"
  type: single_choice
  required: true
  options:
    - { value: "daily", label: { en: "Daily", ar: "يومياً" }, score: 100 }
    - { value: "weekly", label: { en: "Weekly", ar: "أسبوعياً" }, score: 90 }
    - { value: "monthly", label: { en: "Monthly", ar: "شهرياً" }, score: 80 }
    - { value: "quarterly", label: { en: "Quarterly", ar: "كل ربع سنة" }, score: 50 }
    - { value: "annually", label: { en: "Annually", ar: "سنوياً" }, score: 20 }
    - { value: "rarely", label: { en: "Rarely / As needed", ar: "نادراً / عند الحاجة" }, score: 10 }
  agents: [GRAHAM, MARVIN]
  data_field: financial_review_frequency
  dimension: 2
  confidence_impact: medium

FH_015:
  text:
    en: "Do you have a formal annual budget?"
    ar: "هل لديك ميزانية سنوية رسمية؟"
  type: single_choice
  required: true
  options:
    - { value: "detailed", label: { en: "Yes, detailed by department/project", ar: "نعم، مفصلة حسب القسم/المشروع" }, score: 100 }
    - { value: "high_level", label: { en: "Yes, high-level budget", ar: "نعم، ميزانية عامة" }, score: 70 }
    - { value: "informal", label: { en: "Informal planning only", ar: "تخطيط غير رسمي فقط" }, score: 30 }
    - { value: "none", label: { en: "No formal budget", ar: "لا توجد ميزانية رسمية" }, score: 10 }
  agents: [GRAHAM]
  data_field: budgeting_practice
  dimension: 2
  confidence_impact: medium

FH_016:
  text:
    en: "What is your biggest financial challenge right now?"
    ar: "ما هو أكبر تحدٍ مالي تواجهه الآن؟"
  type: multiple_choice
  required: true
  options:
    - { value: "cash_flow", label: { en: "Cash flow / Working capital", ar: "التدفق النقدي / رأس المال العامل" } }
    - { value: "access_credit", label: { en: "Access to credit / loans", ar: "الوصول إلى الائتمان / القروض" } }
    - { value: "profitability", label: { en: "Improving profitability", ar: "تحسين الربحية" } }
    - { value: "collections", label: { en: "Collecting receivables", ar: "تحصيل المستحقات" } }
    - { value: "cost_control", label: { en: "Cost control", ar: "التحكم في التكاليف" } }
    - { value: "currency_risk", label: { en: "Currency fluctuations", ar: "تقلبات العملة" } }
    - { value: "pricing", label: { en: "Pricing strategy", ar: "استراتيجية التسعير" } }
    - { value: "none", label: { en: "No significant challenges", ar: "لا توجد تحديات كبيرة" } }
  agents: [GRAHAM]
  data_field: financial_challenges
  confidence_impact: high
  allows_human_context: true
  human_context_prompt:
    en: "Please elaborate on your biggest financial challenge"
    ar: "يرجى التوضيح حول أكبر تحدٍ مالي لديك"

FH_017:
  text:
    en: "What percentage of your costs are fixed vs. variable?"
    ar: "ما نسبة تكاليفك الثابتة مقابل المتغيرة؟"
  type: slider
  required: true
  scale_config:
    min: 0
    max: 100
    step: 10
    labels:
      min: { en: "0% Fixed / 100% Variable", ar: "0% ثابت / 100% متغير" }
      max: { en: "100% Fixed / 0% Variable", ar: "100% ثابت / 0% متغير" }
  agents: [GRAHAM]
  data_field: fixed_variable_cost_ratio
  dimension: 2
  confidence_impact: medium

FH_018:
  text:
    en: "Do you use any financial KPIs to track performance?"
    ar: "هل تستخدم أي مؤشرات أداء مالية لتتبع الأداء؟"
  type: multiple_choice
  required: true
  options:
    - { value: "gross_margin", label: { en: "Gross margin", ar: "هامش الربح الإجمالي" } }
    - { value: "net_margin", label: { en: "Net profit margin", ar: "هامش صافي الربح" } }
    - { value: "revenue_growth", label: { en: "Revenue growth rate", ar: "معدل نمو الإيرادات" } }
    - { value: "cac", label: { en: "Customer acquisition cost (CAC)", ar: "تكلفة اكتساب العميل" } }
    - { value: "ltv", label: { en: "Customer lifetime value (LTV)", ar: "القيمة الدائمة للعميل" } }
    - { value: "burn_rate", label: { en: "Burn rate", ar: "معدل الحرق" } }
    - { value: "roas", label: { en: "Return on ad spend (ROAS)", ar: "العائد على الإنفاق الإعلاني" } }
    - { value: "none", label: { en: "None formally tracked", ar: "لا يتم تتبع أي منها رسمياً" } }
  agents: [GRAHAM, DEMING]
  data_field: financial_kpis_tracked
  dimension: 2
  confidence_impact: medium

FH_019:
  text:
    en: "How would you rate your company's overall financial health?"
    ar: "كيف تقيّم الصحة المالية الإجمالية لشركتك؟"
  type: scale
  required: true
  scale_config:
    min: 1
    max: 5
    step: 1
    labels:
      min: { en: "Critical - Struggling to survive", ar: "حرج - نكافح للبقاء" }
      mid: { en: "Stable - Managing but tight", ar: "مستقر - ندير لكن بضيق" }
      max: { en: "Strong - Healthy growth", ar: "قوي - نمو صحي" }
  agents: [GRAHAM, DEMING]
  data_field: self_assessment_financial
  confidence_impact: medium

FH_020:
  text:
    en: "Is there any financial context we should know that the numbers might not show?"
    ar: "هل هناك أي سياق مالي يجب أن نعرفه قد لا تظهره الأرقام؟"
  type: human_context
  required: false
  description:
    en: "Examples: seasonal patterns, one-time events, pending deals, currency impact, recent changes"
    ar: "أمثلة: أنماط موسمية، أحداث لمرة واحدة، صفقات معلقة، تأثير العملة، تغييرات حديثة"
  agents: [GRAHAM]
  data_field: human_context_financial
  confidence_impact: high
```

---

# 5. Section 3: Operations & Production

**Section Code:** `OP`
**Primary Agent:** Marvin (The Sentinel)
**Estimated Time:** 4 minutes
**Condition:** Always shown (Core)

## 5.1 Questions

```yaml
OP_001:
  text:
    en: "Which best describes your company's primary business model?"
    ar: "ما الذي يصف نموذج عمل شركتك الأساسي بشكل أفضل؟"
  type: single_choice
  required: true
  options:
    - value: "manufacturing"
      label: { en: "Manufacturing / Production", ar: "تصنيع / إنتاج" }
      triggers_followup: [OP_001a_mfg]
    - value: "service"
      label: { en: "Service delivery", ar: "تقديم الخدمات" }
      triggers_followup: [OP_001a_svc]
    - value: "trading"
      label: { en: "Trading / Distribution", ar: "تجارة / توزيع" }
    - value: "software"
      label: { en: "Software / SaaS", ar: "برمجيات / SaaS" }
      triggers_followup: [OP_001a_sw]
    - value: "hybrid"
      label: { en: "Hybrid (products + services)", ar: "هجين (منتجات + خدمات)" }
      triggers_followup: [OP_001a_mfg, OP_001a_svc]
  agents: [MARVIN, DRUCKER]
  data_field: business_model_type
  dimension: 1
  confidence_impact: high

OP_001a_mfg:
  text:
    en: "What is your current production capacity utilization?"
    ar: "ما هو معدل استخدام طاقتك الإنتاجية الحالي؟"
  type: single_choice
  required: true
  conditional:
    - { question_id: OP_001, operator: "in", value: ["manufacturing", "hybrid"] }
  options:
    - { value: "under_50", label: { en: "Under 50%", ar: "أقل من 50%" }, score: 25 }
    - { value: "50_70", label: { en: "50-70%", ar: "50-70%" }, score: 60 }
    - { value: "70_85", label: { en: "70-85%", ar: "70-85%" }, score: 85 }
    - { value: "85_95", label: { en: "85-95%", ar: "85-95%" }, score: 95 }
    - { value: "over_95", label: { en: "Over 95% (at capacity)", ar: "أكثر من 95% (بكامل الطاقة)" }, score: 75 }
  agents: [MARVIN, OHNO]
  data_field: capacity_utilization
  dimension: 3
  confidence_impact: high

OP_001a_svc:
  text:
    en: "What is your average service delivery time?"
    ar: "ما هو متوسط وقت تقديم الخدمة لديك؟"
  type: single_choice
  required: true
  conditional:
    - { question_id: OP_001, operator: "in", value: ["service", "hybrid"] }
  options:
    - { value: "immediate", label: { en: "Immediate / Same day", ar: "فوري / نفس اليوم" } }
    - { value: "1_3_days", label: { en: "1-3 days", ar: "1-3 أيام" } }
    - { value: "1_week", label: { en: "Within 1 week", ar: "خلال أسبوع" } }
    - { value: "2_4_weeks", label: { en: "2-4 weeks", ar: "2-4 أسابيع" } }
    - { value: "over_month", label: { en: "More than 1 month", ar: "أكثر من شهر" } }
  agents: [MARVIN]
  data_field: service_delivery_time
  dimension: 3
  confidence_impact: medium

OP_001a_sw:
  text:
    en: "What is your current uptime/availability percentage?"
    ar: "ما هي نسبة التشغيل/التوفر الحالية لديك؟"
  type: single_choice
  required: true
  conditional:
    - { question_id: OP_001, operator: "in", value: ["software"] }
  options:
    - { value: "99_9", label: { en: "99.9%+ (Three nines)", ar: "99.9%+ (ثلاثة تسعات)" }, score: 100 }
    - { value: "99_5", label: { en: "99.5-99.9%", ar: "99.5-99.9%" }, score: 90 }
    - { value: "99", label: { en: "99-99.5%", ar: "99-99.5%" }, score: 80 }
    - { value: "95_99", label: { en: "95-99%", ar: "95-99%" }, score: 60 }
    - { value: "under_95", label: { en: "Under 95%", ar: "أقل من 95%" }, score: 30 }
    - { value: "not_tracked", label: { en: "Not formally tracked", ar: "لا يتم تتبعها رسمياً" }, score: 10 }
  agents: [MARVIN, LOVELACE]
  data_field: uptime_percentage
  dimension: 3
  confidence_impact: medium

OP_002:
  text:
    en: "How would you describe your operational processes?"
    ar: "كيف تصف عملياتك التشغيلية؟"
  type: single_choice
  required: true
  options:
    - { value: "ad_hoc", label: { en: "Ad-hoc / As needed", ar: "حسب الحاجة" }, score: 10 }
    - { value: "informal", label: { en: "Informal but consistent", ar: "غير رسمية لكن متسقة" }, score: 30 }
    - { value: "documented", label: { en: "Documented SOPs", ar: "إجراءات موثقة" }, score: 60 }
    - { value: "optimized", label: { en: "Documented & continuously improved", ar: "موثقة ومحسنة باستمرار" }, score: 80 }
    - { value: "certified", label: { en: "Certified (ISO, etc.)", ar: "معتمدة (ISO، إلخ)" }, score: 100 }
  agents: [MARVIN, DEMING]
  data_field: process_maturity
  dimension: 3
  confidence_impact: high

OP_003:
  text:
    en: "Do you have documented Standard Operating Procedures (SOPs)?"
    ar: "هل لديك إجراءات تشغيل قياسية موثقة (SOPs)؟"
  type: single_choice
  required: true
  options:
    - { value: "comprehensive", label: { en: "Yes, for all key processes", ar: "نعم، لجميع العمليات الرئيسية" }, score: 100 }
    - { value: "some", label: { en: "Yes, for some processes", ar: "نعم، لبعض العمليات" }, score: 60 }
    - { value: "outdated", label: { en: "Yes, but outdated", ar: "نعم، لكنها قديمة" }, score: 30 }
    - { value: "none", label: { en: "No documented SOPs", ar: "لا توجد إجراءات موثقة" }, score: 10 }
  agents: [MARVIN]
  data_field: sop_coverage
  dimension: 3
  confidence_impact: medium

OP_004:
  text:
    en: "What quality control measures do you have in place?"
    ar: "ما هي إجراءات مراقبة الجودة لديك؟"
  type: multiple_choice
  required: true
  options:
    - { value: "incoming_inspection", label: { en: "Incoming material inspection", ar: "فحص المواد الواردة" } }
    - { value: "in_process", label: { en: "In-process quality checks", ar: "فحوصات جودة أثناء الإنتاج" } }
    - { value: "final_inspection", label: { en: "Final product inspection", ar: "فحص المنتج النهائي" } }
    - { value: "statistical", label: { en: "Statistical quality control (SQC)", ar: "مراقبة جودة إحصائية" } }
    - { value: "customer_feedback", label: { en: "Customer feedback loops", ar: "حلقات ملاحظات العملاء" } }
    - { value: "automated", label: { en: "Automated testing/monitoring", ar: "اختبار/مراقبة آلية" } }
    - { value: "none", label: { en: "No formal QC process", ar: "لا توجد عملية جودة رسمية" } }
  agents: [MARVIN, DEMING]
  data_field: quality_control_measures
  dimension: 3
  confidence_impact: high

OP_005:
  text:
    en: "What is your product/service defect or error rate?"
    ar: "ما هو معدل العيوب أو الأخطاء في منتجاتك/خدماتك؟"
  type: single_choice
  required: true
  options:
    - { value: "under_1", label: { en: "Under 1%", ar: "أقل من 1%" }, score: 95 }
    - { value: "1_3", label: { en: "1-3%", ar: "1-3%" }, score: 80 }
    - { value: "3_5", label: { en: "3-5%", ar: "3-5%" }, score: 60 }
    - { value: "5_10", label: { en: "5-10%", ar: "5-10%" }, score: 40 }
    - { value: "over_10", label: { en: "Over 10%", ar: "أكثر من 10%" }, score: 20 }
    - { value: "not_tracked", label: { en: "Not formally tracked", ar: "لا يتم تتبعها" }, score: 10 }
  agents: [MARVIN, DEMING]
  data_field: defect_rate
  dimension: 3
  confidence_impact: high

OP_006:
  text:
    en: "How do you track and manage orders/projects?"
    ar: "كيف تتبع وتدير الطلبات/المشاريع؟"
  type: single_choice
  required: true
  options:
    - { value: "erp", label: { en: "ERP system", ar: "نظام ERP" }, score: 100 }
    - { value: "project_mgmt", label: { en: "Project management software", ar: "برنامج إدارة المشاريع" }, score: 80 }
    - { value: "crm", label: { en: "CRM system", ar: "نظام CRM" }, score: 70 }
    - { value: "spreadsheet", label: { en: "Spreadsheets", ar: "جداول بيانات" }, score: 40 }
    - { value: "manual", label: { en: "Manual/Paper-based", ar: "يدوي/ورقي" }, score: 15 }
    - { value: "informal", label: { en: "Informal tracking", ar: "تتبع غير رسمي" }, score: 10 }
  agents: [MARVIN, LOVELACE]
  data_field: order_tracking_system
  dimension: 6
  confidence_impact: medium

OP_007:
  text:
    en: "What percentage of orders/projects are delivered on time?"
    ar: "ما نسبة الطلبات/المشاريع التي يتم تسليمها في الوقت المحدد؟"
  type: single_choice
  required: true
  options:
    - { value: "95_plus", label: { en: "95%+ (Excellent)", ar: "95%+ (ممتاز)" }, score: 95 }
    - { value: "90_95", label: { en: "90-95%", ar: "90-95%" }, score: 85 }
    - { value: "80_90", label: { en: "80-90%", ar: "80-90%" }, score: 70 }
    - { value: "70_80", label: { en: "70-80%", ar: "70-80%" }, score: 55 }
    - { value: "under_70", label: { en: "Under 70%", ar: "أقل من 70%" }, score: 30 }
    - { value: "not_tracked", label: { en: "Not tracked", ar: "لا يتم تتبعها" }, score: 10 }
  agents: [MARVIN, OHNO]
  data_field: on_time_delivery_rate
  dimension: 3
  confidence_impact: high

OP_008:
  text:
    en: "Do you have any operational certifications?"
    ar: "هل لديك أي شهادات تشغيلية؟"
  type: multiple_choice
  required: true
  options:
    - { value: "iso_9001", label: { en: "ISO 9001 (Quality Management)", ar: "ISO 9001 (إدارة الجودة)" } }
    - { value: "iso_14001", label: { en: "ISO 14001 (Environmental)", ar: "ISO 14001 (البيئة)" } }
    - { value: "iso_22000", label: { en: "ISO 22000 / HACCP (Food Safety)", ar: "ISO 22000 / HACCP (سلامة الغذاء)" } }
    - { value: "iso_45001", label: { en: "ISO 45001 (Occupational Health)", ar: "ISO 45001 (الصحة المهنية)" } }
    - { value: "iso_27001", label: { en: "ISO 27001 (Information Security)", ar: "ISO 27001 (أمن المعلومات)" } }
    - { value: "halal", label: { en: "Halal certification", ar: "شهادة حلال" } }
    - { value: "organic", label: { en: "Organic certification", ar: "شهادة عضوية" } }
    - { value: "industry_specific", label: { en: "Industry-specific certification", ar: "شهادة خاصة بالصناعة" } }
    - { value: "none", label: { en: "No certifications", ar: "لا توجد شهادات" } }
    - { value: "in_progress", label: { en: "Currently pursuing certification", ar: "نعمل حالياً على الحصول على شهادة" } }
  agents: [MARVIN, RICARDO, DEMING]
  data_field: operational_certifications
  dimension: 4
  confidence_impact: high

OP_009:
  text:
    en: "How do you handle customer complaints or issues?"
    ar: "كيف تتعامل مع شكاوى العملاء أو المشاكل؟"
  type: single_choice
  required: true
  options:
    - { value: "formal_system", label: { en: "Formal ticketing/tracking system", ar: "نظام تتبع رسمي" }, score: 100 }
    - { value: "crm_tracked", label: { en: "Tracked in CRM", ar: "متتبعة في CRM" }, score: 80 }
    - { value: "documented", label: { en: "Documented process but manual", ar: "عملية موثقة لكن يدوية" }, score: 60 }
    - { value: "informal", label: { en: "Informal handling", ar: "تعامل غير رسمي" }, score: 30 }
    - { value: "reactive", label: { en: "Reactive only", ar: "تفاعلي فقط" }, score: 15 }
  agents: [MARVIN, DEMING]
  data_field: complaint_handling
  dimension: 3
  confidence_impact: medium

OP_010:
  text:
    en: "What is your customer satisfaction rate or NPS?"
    ar: "ما هو معدل رضا العملاء أو NPS؟"
  type: single_choice
  required: true
  options:
    - { value: "excellent", label: { en: "Excellent (NPS 50+ or 90%+ satisfaction)", ar: "ممتاز (NPS 50+ أو رضا 90%+)" }, score: 95 }
    - { value: "good", label: { en: "Good (NPS 30-50 or 80-90%)", ar: "جيد (NPS 30-50 أو 80-90%)" }, score: 75 }
    - { value: "average", label: { en: "Average (NPS 0-30 or 70-80%)", ar: "متوسط (NPS 0-30 أو 70-80%)" }, score: 50 }
    - { value: "below_average", label: { en: "Below average (negative NPS or under 70%)", ar: "أقل من المتوسط" }, score: 25 }
    - { value: "not_measured", label: { en: "Not measured", ar: "غير مقاس" }, score: 10 }
  agents: [MARVIN, DEMING, PORTER]
  data_field: customer_satisfaction
  dimension: 3
  confidence_impact: high

OP_011:
  text:
    en: "What is your customer retention rate (repeat customers)?"
    ar: "ما هو معدل الاحتفاظ بالعملاء (العملاء المتكررون)؟"
  type: single_choice
  required: true
  options:
    - { value: "over_90", label: { en: "Over 90%", ar: "أكثر من 90%" }, score: 95 }
    - { value: "80_90", label: { en: "80-90%", ar: "80-90%" }, score: 80 }
    - { value: "70_80", label: { en: "70-80%", ar: "70-80%" }, score: 65 }
    - { value: "60_70", label: { en: "60-70%", ar: "60-70%" }, score: 50 }
    - { value: "under_60", label: { en: "Under 60%", ar: "أقل من 60%" }, score: 30 }
    - { value: "not_tracked", label: { en: "Not tracked", ar: "غير متتبع" }, score: 10 }
    - { value: "na", label: { en: "N/A (one-time purchases typical)", ar: "لا ينطبق (مشتريات لمرة واحدة)" }, score: 50 }
  agents: [MARVIN, GRAHAM, PORTER]
  data_field: customer_retention_rate
  dimension: 3
  confidence_impact: medium

OP_012:
  text:
    en: "How do you measure and track operational performance?"
    ar: "كيف تقيس وتتبع الأداء التشغيلي؟"
  type: multiple_choice
  required: true
  options:
    - { value: "dashboard", label: { en: "Real-time dashboards", ar: "لوحات معلومات في الوقت الحقيقي" } }
    - { value: "weekly_reports", label: { en: "Weekly reports", ar: "تقارير أسبوعية" } }
    - { value: "monthly_reviews", label: { en: "Monthly KPI reviews", ar: "مراجعات KPI شهرية" } }
    - { value: "manual_tracking", label: { en: "Manual tracking", ar: "تتبع يدوي" } }
    - { value: "ad_hoc", label: { en: "Ad-hoc / As needed", ar: "حسب الحاجة" } }
    - { value: "none", label: { en: "No formal tracking", ar: "لا يوجد تتبع رسمي" } }
  agents: [MARVIN, DEMING]
  data_field: performance_tracking_methods
  dimension: 3
  confidence_impact: medium

OP_013:
  text:
    en: "What are your top 3 operational challenges?"
    ar: "ما هي أهم 3 تحديات تشغيلية لديك؟"
  type: multiple_choice
  required: true
  options:
    - { value: "capacity", label: { en: "Capacity constraints", ar: "قيود الطاقة" } }
    - { value: "quality", label: { en: "Quality consistency", ar: "اتساق الجودة" } }
    - { value: "efficiency", label: { en: "Process efficiency", ar: "كفاءة العمليات" } }
    - { value: "delivery", label: { en: "On-time delivery", ar: "التسليم في الوقت المحدد" } }
    - { value: "cost", label: { en: "Cost control", ar: "التحكم في التكاليف" } }
    - { value: "equipment", label: { en: "Equipment/Technology", ar: "المعدات/التكنولوجيا" } }
    - { value: "skills", label: { en: "Skilled labor availability", ar: "توفر العمالة الماهرة" } }
    - { value: "documentation", label: { en: "Documentation/Processes", ar: "التوثيق/العمليات" } }
    - { value: "none", label: { en: "No significant challenges", ar: "لا توجد تحديات كبيرة" } }
  agents: [MARVIN]
  data_field: operational_challenges
  confidence_impact: high
  allows_human_context: true
  human_context_prompt:
    en: "Tell us more about your operational challenges"
    ar: "أخبرنا المزيد عن تحدياتك التشغيلية"

OP_014:
  text:
    en: "Do you have contingency plans for operational disruptions?"
    ar: "هل لديك خطط طوارئ للاضطرابات التشغيلية؟"
  type: single_choice
  required: true
  options:
    - { value: "comprehensive", label: { en: "Yes, comprehensive business continuity plans", ar: "نعم، خطط استمرارية أعمال شاملة" }, score: 100 }
    - { value: "partial", label: { en: "Yes, for some critical areas", ar: "نعم، لبعض المجالات الحرجة" }, score: 60 }
    - { value: "informal", label: { en: "Informal / Not documented", ar: "غير رسمية / غير موثقة" }, score: 30 }
    - { value: "none", label: { en: "No contingency plans", ar: "لا توجد خطط طوارئ" }, score: 10 }
  agents: [MARVIN]
  data_field: contingency_planning
  dimension: 3
  confidence_impact: medium

OP_015:
  text:
    en: "How would you rate your overall operational efficiency?"
    ar: "كيف تقيّم كفاءتك التشغيلية الإجمالية؟"
  type: scale
  required: true
  scale_config:
    min: 1
    max: 5
    step: 1
    labels:
      min: { en: "Very inefficient", ar: "غير كفء جداً" }
      mid: { en: "Average", ar: "متوسط" }
      max: { en: "Highly efficient", ar: "كفء جداً" }
  agents: [MARVIN, DEMING]
  data_field: self_assessment_operations
  confidence_impact: medium

OP_016:
  text:
    en: "What would have the biggest impact on improving your operations?"
    ar: "ما الذي سيكون له أكبر تأثير على تحسين عملياتك؟"
  type: single_choice
  required: true
  options:
    - { value: "automation", label: { en: "Automation / Technology", ar: "الأتمتة / التكنولوجيا" } }
    - { value: "training", label: { en: "Staff training", ar: "تدريب الموظفين" } }
    - { value: "processes", label: { en: "Better processes / SOPs", ar: "عمليات أفضل" } }
    - { value: "equipment", label: { en: "Better equipment", ar: "معدات أفضل" } }
    - { value: "capacity", label: { en: "More capacity", ar: "طاقة أكبر" } }
    - { value: "quality_systems", label: { en: "Quality management systems", ar: "أنظمة إدارة الجودة" } }
    - { value: "supply_chain", label: { en: "Supply chain improvements", ar: "تحسينات سلسلة التوريد" } }
  agents: [MARVIN]
  data_field: improvement_priority
  confidence_impact: medium

OP_017:
  text:
    en: "Is there anything about your operations we should know that typical questions might miss?"
    ar: "هل هناك شيء حول عملياتك يجب أن نعرفه قد تفوته الأسئلة المعتادة؟"
  type: human_context
  required: false
  description:
    en: "Share any unique operational context: specialized equipment, unusual processes, seasonal factors, etc."
    ar: "شارك أي سياق تشغيلي فريد: معدات متخصصة، عمليات غير عادية، عوامل موسمية، إلخ."
  agents: [MARVIN]
  data_field: human_context_operations
  confidence_impact: high
```

---

*[Continuing with remaining sections...]*

# 6. Section 4: Digital Maturity

**Section Code:** `DM`
**Primary Agent:** Lovelace (The Weaver)
**Estimated Time:** 3 minutes
**Condition:** If Digital Agent Add-on selected OR sector = Tech

## 6.1 Questions

```yaml
DM_001:
  text:
    en: "How would you describe your company's overall digital maturity?"
    ar: "كيف تصف النضج الرقمي الإجمالي لشركتك؟"
  type: single_choice
  required: true
  options:
    - { value: "digital_native", label: { en: "Digital-native (built digital-first)", ar: "رقمي أصلاً" }, score: 100 }
    - { value: "advanced", label: { en: "Advanced (fully digitized operations)", ar: "متقدم" }, score: 85 }
    - { value: "developing", label: { en: "Developing (key systems digital)", ar: "يتطور" }, score: 60 }
    - { value: "basic", label: { en: "Basic (some digital tools)", ar: "أساسي" }, score: 35 }
    - { value: "traditional", label: { en: "Traditional (mostly manual)", ar: "تقليدي" }, score: 10 }
  agents: [LOVELACE, DRUCKER]
  data_field: digital_maturity_level
  dimension: 6
  confidence_impact: high

DM_002:
  text:
    en: "Which business systems do you currently use?"
    ar: "ما هي أنظمة الأعمال التي تستخدمها حالياً؟"
  type: multiple_choice
  required: true
  options:
    - { value: "erp", label: { en: "ERP (Enterprise Resource Planning)", ar: "نظام ERP" } }
    - { value: "crm", label: { en: "CRM (Customer Relationship Management)", ar: "نظام CRM" } }
    - { value: "accounting", label: { en: "Accounting Software", ar: "برنامج محاسبة" } }
    - { value: "hrms", label: { en: "HR Management System", ar: "نظام إدارة الموارد البشرية" } }
    - { value: "inventory", label: { en: "Inventory Management", ar: "إدارة المخزون" } }
    - { value: "project_mgmt", label: { en: "Project Management", ar: "إدارة المشاريع" } }
    - { value: "ecommerce", label: { en: "E-commerce Platform", ar: "منصة تجارة إلكترونية" } }
    - { value: "bi", label: { en: "Business Intelligence / Analytics", ar: "ذكاء أعمال / تحليلات" } }
    - { value: "communication", label: { en: "Team Communication (Slack, Teams)", ar: "تواصل الفريق" } }
    - { value: "document_mgmt", label: { en: "Document Management", ar: "إدارة المستندات" } }
    - { value: "none", label: { en: "None / Basic office tools only", ar: "لا شيء / أدوات مكتبية فقط" } }
  agents: [LOVELACE]
  data_field: current_systems
  dimension: 6
  confidence_impact: high

DM_003:
  text:
    en: "How well integrated are your business systems?"
    ar: "ما مدى تكامل أنظمة أعمالك؟"
  type: single_choice
  required: true
  options:
    - { value: "fully_integrated", label: { en: "Fully integrated (single platform or APIs)", ar: "متكاملة تماماً" }, score: 100 }
    - { value: "mostly_integrated", label: { en: "Mostly integrated with some gaps", ar: "متكاملة في الغالب" }, score: 70 }
    - { value: "partially_integrated", label: { en: "Partially integrated (manual transfers)", ar: "متكاملة جزئياً" }, score: 40 }
    - { value: "siloed", label: { en: "Siloed (no integration)", ar: "منعزلة (بدون تكامل)" }, score: 15 }
    - { value: "na", label: { en: "N/A (single system only)", ar: "لا ينطبق" }, score: 50 }
  agents: [LOVELACE]
  data_field: system_integration_level
  dimension: 6
  confidence_impact: medium

DM_004:
  text:
    en: "Do you have a company website?"
    ar: "هل لديك موقع إلكتروني للشركة؟"
  type: single_choice
  required: true
  options:
    - value: "ecommerce"
      label: { en: "Yes, with e-commerce capability", ar: "نعم، مع إمكانية التجارة الإلكترونية" }
      score: 100
      triggers_followup: [DM_004a]
    - value: "interactive"
      label: { en: "Yes, interactive (forms, booking, etc.)", ar: "نعم، تفاعلي" }
      score: 80
      triggers_followup: [DM_004a]
    - value: "informational"
      label: { en: "Yes, informational only", ar: "نعم، معلوماتي فقط" }
      score: 50
    - value: "outdated"
      label: { en: "Yes, but outdated", ar: "نعم، لكن قديم" }
      score: 25
    - value: "none"
      label: { en: "No website", ar: "لا يوجد موقع" }
      score: 5
  agents: [LOVELACE, LANDOR]
  data_field: website_status
  dimension: 6
  confidence_impact: medium

DM_004a:
  text:
    en: "What percentage of your sales come from online channels?"
    ar: "ما نسبة مبيعاتك التي تأتي من القنوات الإلكترونية؟"
  type: single_choice
  required: false
  conditional:
    - { question_id: DM_004, operator: "in", value: ["ecommerce", "interactive"] }
  options:
    - { value: "0_10", label: { en: "0-10%", ar: "0-10%" } }
    - { value: "10_25", label: { en: "10-25%", ar: "10-25%" } }
    - { value: "25_50", label: { en: "25-50%", ar: "25-50%" } }
    - { value: "50_75", label: { en: "50-75%", ar: "50-75%" } }
    - { value: "75_100", label: { en: "75-100%", ar: "75-100%" } }
  agents: [LOVELACE, GRAHAM]
  data_field: online_sales_percentage
  dimension: 6
  confidence_impact: medium

DM_005:
  text:
    en: "How do you manage customer data and communications?"
    ar: "كيف تدير بيانات العملاء والتواصل معهم؟"
  type: single_choice
  required: true
  options:
    - { value: "advanced_crm", label: { en: "Advanced CRM with automation", ar: "CRM متقدم مع أتمتة" }, score: 100 }
    - { value: "basic_crm", label: { en: "Basic CRM system", ar: "نظام CRM أساسي" }, score: 70 }
    - { value: "spreadsheet", label: { en: "Spreadsheets / Contact lists", ar: "جداول بيانات / قوائم جهات اتصال" }, score: 35 }
    - { value: "informal", label: { en: "Informal / Memory-based", ar: "غير رسمي / ذاكرة" }, score: 10 }
  agents: [LOVELACE, LANDOR]
  data_field: customer_data_management
  dimension: 6
  confidence_impact: medium

DM_006:
  text:
    en: "What level of data analytics do you use?"
    ar: "ما مستوى تحليلات البيانات التي تستخدمها؟"
  type: single_choice
  required: true
  options:
    - { value: "predictive", label: { en: "Predictive analytics / AI/ML", ar: "تحليلات تنبؤية / AI/ML" }, score: 100 }
    - { value: "advanced", label: { en: "Advanced analytics (BI tools, dashboards)", ar: "تحليلات متقدمة" }, score: 80 }
    - { value: "basic", label: { en: "Basic reporting (standard reports)", ar: "تقارير أساسية" }, score: 50 }
    - { value: "manual", label: { en: "Manual analysis (spreadsheets)", ar: "تحليل يدوي" }, score: 25 }
    - { value: "none", label: { en: "Little to no analytics", ar: "قليل أو لا يوجد" }, score: 5 }
  agents: [LOVELACE]
  data_field: analytics_maturity
  dimension: 6
  confidence_impact: medium

DM_007:
  text:
    en: "How is your data stored and backed up?"
    ar: "كيف يتم تخزين بياناتك ونسخها احتياطياً؟"
  type: single_choice
  required: true
  options:
    - { value: "cloud_automated", label: { en: "Cloud with automated backups", ar: "سحابة مع نسخ احتياطي تلقائي" }, score: 100 }
    - { value: "cloud_manual", label: { en: "Cloud with manual backups", ar: "سحابة مع نسخ احتياطي يدوي" }, score: 70 }
    - { value: "local_backup", label: { en: "Local servers with backup", ar: "خوادم محلية مع نسخ احتياطي" }, score: 50 }
    - { value: "local_no_backup", label: { en: "Local storage, irregular backup", ar: "تخزين محلي، نسخ احتياطي غير منتظم" }, score: 20 }
    - { value: "scattered", label: { en: "Scattered / No central storage", ar: "مبعثر / لا تخزين مركزي" }, score: 5 }
  agents: [LOVELACE]
  data_field: data_storage
  dimension: 6
  confidence_impact: medium

DM_008:
  text:
    en: "What cybersecurity measures do you have in place?"
    ar: "ما هي تدابير الأمن السيبراني لديك؟"
  type: multiple_choice
  required: true
  options:
    - { value: "firewall", label: { en: "Firewall / Network security", ar: "جدار حماية / أمن الشبكة" } }
    - { value: "antivirus", label: { en: "Antivirus / Endpoint protection", ar: "مكافحة الفيروسات" } }
    - { value: "mfa", label: { en: "Multi-factor authentication", ar: "مصادقة متعددة العوامل" } }
    - { value: "encryption", label: { en: "Data encryption", ar: "تشفير البيانات" } }
    - { value: "access_control", label: { en: "Access controls / Role-based permissions", ar: "التحكم في الوصول" } }
    - { value: "security_training", label: { en: "Employee security training", ar: "تدريب أمني للموظفين" } }
    - { value: "incident_response", label: { en: "Incident response plan", ar: "خطة الاستجابة للحوادث" } }
    - { value: "none", label: { en: "No formal measures", ar: "لا توجد تدابير رسمية" } }
  agents: [LOVELACE]
  data_field: cybersecurity_measures
  dimension: 6
  confidence_impact: high

DM_009:
  text:
    en: "What is your biggest digital/technology challenge?"
    ar: "ما هو أكبر تحدٍ رقمي/تكنولوجي لديك؟"
  type: multiple_choice
  required: true
  options:
    - { value: "budget", label: { en: "Budget constraints", ar: "قيود الميزانية" } }
    - { value: "skills", label: { en: "Lack of technical skills", ar: "نقص المهارات التقنية" } }
    - { value: "integration", label: { en: "System integration issues", ar: "مشاكل تكامل الأنظمة" } }
    - { value: "adoption", label: { en: "User adoption / Change management", ar: "تبني المستخدمين / إدارة التغيير" } }
    - { value: "selection", label: { en: "Choosing the right tools", ar: "اختيار الأدوات المناسبة" } }
    - { value: "data_quality", label: { en: "Data quality / Migration", ar: "جودة البيانات / الترحيل" } }
    - { value: "security", label: { en: "Security concerns", ar: "مخاوف أمنية" } }
    - { value: "none", label: { en: "No significant challenges", ar: "لا توجد تحديات كبيرة" } }
  agents: [LOVELACE]
  data_field: digital_challenges
  confidence_impact: high
  allows_human_context: true
  human_context_prompt:
    en: "Tell us more about your digital transformation journey"
    ar: "أخبرنا المزيد عن رحلة التحول الرقمي لديك"

DM_010:
  text:
    en: "Do you have dedicated IT staff or resources?"
    ar: "هل لديك موظفون أو موارد تكنولوجيا معلومات مخصصون؟"
  type: single_choice
  required: true
  options:
    - { value: "internal_team", label: { en: "Yes, internal IT department/team", ar: "نعم، قسم/فريق IT داخلي" }, score: 100 }
    - { value: "dedicated_person", label: { en: "Yes, dedicated IT person", ar: "نعم، شخص IT مخصص" }, score: 70 }
    - { value: "outsourced", label: { en: "Outsourced IT support", ar: "دعم IT خارجي" }, score: 50 }
    - { value: "part_time", label: { en: "Part-time / Shared responsibility", ar: "دوام جزئي / مسؤولية مشتركة" }, score: 30 }
    - { value: "none", label: { en: "No dedicated IT resources", ar: "لا توجد موارد IT مخصصة" }, score: 10 }
  agents: [LOVELACE, MAYO]
  data_field: it_resources
  dimension: 6
  confidence_impact: medium

DM_011:
  text:
    en: "What are your digital priorities for the next 12 months?"
    ar: "ما هي أولوياتك الرقمية لـ 12 شهراً القادمة؟"
  type: multiple_choice
  required: true
  options:
    - { value: "new_systems", label: { en: "Implement new systems", ar: "تطبيق أنظمة جديدة" } }
    - { value: "automation", label: { en: "Automate manual processes", ar: "أتمتة العمليات اليدوية" } }
    - { value: "ecommerce", label: { en: "Develop e-commerce capabilities", ar: "تطوير قدرات التجارة الإلكترونية" } }
    - { value: "analytics", label: { en: "Improve data analytics", ar: "تحسين تحليلات البيانات" } }
    - { value: "security", label: { en: "Strengthen cybersecurity", ar: "تعزيز الأمن السيبراني" } }
    - { value: "cloud", label: { en: "Move to cloud", ar: "الانتقال إلى السحابة" } }
    - { value: "ai", label: { en: "Adopt AI/ML tools", ar: "تبني أدوات AI/ML" } }
    - { value: "none", label: { en: "No specific priorities", ar: "لا توجد أولويات محددة" } }
  agents: [LOVELACE]
  data_field: digital_priorities
  confidence_impact: medium

DM_012:
  text:
    en: "Is there any digital context or history that would help us understand your situation better?"
    ar: "هل هناك أي سياق أو تاريخ رقمي يساعدنا على فهم وضعك بشكل أفضل؟"
  type: human_context
  required: false
  description:
    en: "Examples: failed implementations, specific technology constraints, upcoming projects, unique requirements"
    ar: "أمثلة: تطبيقات فاشلة، قيود تكنولوجية محددة، مشاريع قادمة، متطلبات فريدة"
  agents: [LOVELACE]
  data_field: human_context_digital
  confidence_impact: high
```

---

*[I'll continue creating the remaining sections: Workforce & HR, Market & Competition, Supply Chain, Export Readiness, Brand & Marketing, Compliance & Certifications, plus the Conditional Logic, Validation, Agent Mapping, and Implementation sections...]*

# 7. Section 5: Workforce & HR

**Section Code:** `WF`
**Primary Agent:** Mayo (The Cultivator)
**Estimated Time:** 3 minutes
**Condition:** If HR Agent Add-on selected

## 7.1 Questions

```yaml
WF_001:
  text:
    en: "What is your current workforce composition?"
    ar: "ما هو تكوين قوتك العاملة الحالي؟"
  type: matrix
  required: true
  matrix_config:
    rows:
      - { id: "full_time", label: { en: "Full-time employees", ar: "موظفون بدوام كامل" } }
      - { id: "part_time", label: { en: "Part-time employees", ar: "موظفون بدوام جزئي" } }
      - { id: "contractors", label: { en: "Contractors / Freelancers", ar: "متعاقدون / مستقلون" } }
      - { id: "seasonal", label: { en: "Seasonal workers", ar: "عمال موسميون" } }
    columns:
      - { id: "count", type: "numeric", label: { en: "Number", ar: "العدد" } }
  agents: [MAYO]
  data_field: workforce_composition
  dimension: 7
  confidence_impact: high

WF_002:
  text:
    en: "What is your annual employee turnover rate?"
    ar: "ما هو معدل دوران الموظفين السنوي؟"
  type: single_choice
  required: true
  options:
    - { value: "under_5", label: { en: "Under 5%", ar: "أقل من 5%" }, score: 100 }
    - { value: "5_10", label: { en: "5-10%", ar: "5-10%" }, score: 85 }
    - { value: "10_20", label: { en: "10-20%", ar: "10-20%" }, score: 65 }
    - { value: "20_30", label: { en: "20-30%", ar: "20-30%" }, score: 45 }
    - { value: "over_30", label: { en: "Over 30%", ar: "أكثر من 30%" }, score: 25 }
    - { value: "not_tracked", label: { en: "Not tracked", ar: "غير متتبع" }, score: 10 }
  agents: [MAYO]
  data_field: turnover_rate
  dimension: 7
  confidence_impact: high

WF_003:
  text:
    en: "How do you manage HR and payroll?"
    ar: "كيف تدير الموارد البشرية وكشوف المرتبات؟"
  type: single_choice
  required: true
  options:
    - { value: "hrms", label: { en: "Full HRMS / HCM system", ar: "نظام HRMS / HCM كامل" }, score: 100 }
    - { value: "payroll_software", label: { en: "Payroll software + manual HR", ar: "برنامج رواتب + HR يدوي" }, score: 60 }
    - { value: "outsourced", label: { en: "Outsourced to service provider", ar: "خارجي لمزود خدمة" }, score: 50 }
    - { value: "spreadsheet", label: { en: "Spreadsheets", ar: "جداول بيانات" }, score: 25 }
    - { value: "manual", label: { en: "Manual / Paper-based", ar: "يدوي / ورقي" }, score: 10 }
  agents: [MAYO, LOVELACE]
  data_field: hr_management_system
  dimension: 7
  confidence_impact: medium

WF_004:
  text:
    en: "Do you have documented HR policies and procedures?"
    ar: "هل لديك سياسات وإجراءات موارد بشرية موثقة؟"
  type: single_choice
  required: true
  options:
    - { value: "comprehensive", label: { en: "Yes, comprehensive employee handbook", ar: "نعم، دليل موظف شامل" }, score: 100 }
    - { value: "some", label: { en: "Yes, some key policies documented", ar: "نعم، بعض السياسات الرئيسية موثقة" }, score: 60 }
    - { value: "outdated", label: { en: "Yes, but outdated", ar: "نعم، لكن قديمة" }, score: 30 }
    - { value: "none", label: { en: "No formal documentation", ar: "لا توجد وثائق رسمية" }, score: 10 }
  agents: [MAYO]
  data_field: hr_documentation
  dimension: 7
  confidence_impact: medium

WF_005:
  text:
    en: "What training and development programs do you offer?"
    ar: "ما برامج التدريب والتطوير التي تقدمها؟"
  type: multiple_choice
  required: true
  options:
    - { value: "onboarding", label: { en: "Structured onboarding program", ar: "برنامج تأهيل منظم" } }
    - { value: "skills_training", label: { en: "Technical/Skills training", ar: "تدريب تقني/مهارات" } }
    - { value: "leadership", label: { en: "Leadership development", ar: "تطوير القيادة" } }
    - { value: "external", label: { en: "External courses/certifications", ar: "دورات/شهادات خارجية" } }
    - { value: "mentoring", label: { en: "Mentoring programs", ar: "برامج إرشاد" } }
    - { value: "cross_training", label: { en: "Cross-training", ar: "تدريب متقاطع" } }
    - { value: "informal", label: { en: "Informal / On-the-job only", ar: "غير رسمي / أثناء العمل فقط" } }
    - { value: "none", label: { en: "No formal programs", ar: "لا توجد برامج رسمية" } }
  agents: [MAYO]
  data_field: training_programs
  dimension: 7
  confidence_impact: medium

WF_006:
  text:
    en: "How do you measure employee performance?"
    ar: "كيف تقيس أداء الموظفين؟"
  type: single_choice
  required: true
  options:
    - { value: "continuous", label: { en: "Continuous feedback with goals/OKRs", ar: "ملاحظات مستمرة مع أهداف/OKRs" }, score: 100 }
    - { value: "regular_reviews", label: { en: "Regular performance reviews (quarterly+)", ar: "مراجعات أداء منتظمة (ربع سنوية+)" }, score: 80 }
    - { value: "annual", label: { en: "Annual reviews only", ar: "مراجعات سنوية فقط" }, score: 50 }
    - { value: "informal", label: { en: "Informal feedback only", ar: "ملاحظات غير رسمية فقط" }, score: 25 }
    - { value: "none", label: { en: "No formal process", ar: "لا توجد عملية رسمية" }, score: 10 }
  agents: [MAYO]
  data_field: performance_management
  dimension: 7
  confidence_impact: medium

WF_007:
  text:
    en: "What are your biggest workforce challenges?"
    ar: "ما هي أكبر تحديات القوى العاملة لديك؟"
  type: multiple_choice
  required: true
  options:
    - { value: "recruitment", label: { en: "Finding qualified candidates", ar: "إيجاد مرشحين مؤهلين" } }
    - { value: "retention", label: { en: "Employee retention", ar: "الاحتفاظ بالموظفين" } }
    - { value: "skills_gap", label: { en: "Skills gaps", ar: "فجوات المهارات" } }
    - { value: "productivity", label: { en: "Productivity issues", ar: "مشاكل الإنتاجية" } }
    - { value: "engagement", label: { en: "Employee engagement/morale", ar: "مشاركة/معنويات الموظفين" } }
    - { value: "compensation", label: { en: "Compensation competitiveness", ar: "تنافسية التعويضات" } }
    - { value: "succession", label: { en: "Succession planning", ar: "تخطيط التعاقب" } }
    - { value: "compliance", label: { en: "Labor law compliance", ar: "الامتثال لقوانين العمل" } }
    - { value: "none", label: { en: "No significant challenges", ar: "لا توجد تحديات كبيرة" } }
  agents: [MAYO]
  data_field: workforce_challenges
  confidence_impact: high
  allows_human_context: true
  human_context_prompt:
    en: "Tell us more about your workforce situation"
    ar: "أخبرنا المزيد عن وضع القوى العاملة لديك"

WF_008:
  text:
    en: "How competitive is your compensation compared to the market?"
    ar: "ما مدى تنافسية تعويضاتك مقارنة بالسوق؟"
  type: single_choice
  required: true
  options:
    - { value: "above_market", label: { en: "Above market (top 25%)", ar: "فوق السوق (أعلى 25%)" }, score: 100 }
    - { value: "at_market", label: { en: "At market average", ar: "متوسط السوق" }, score: 70 }
    - { value: "slightly_below", label: { en: "Slightly below market", ar: "أقل قليلاً من السوق" }, score: 40 }
    - { value: "below_market", label: { en: "Below market", ar: "أقل من السوق" }, score: 20 }
    - { value: "dont_know", label: { en: "Don't know", ar: "لا أعرف" }, score: 10 }
  agents: [MAYO]
  data_field: compensation_competitiveness
  dimension: 7
  confidence_impact: medium

WF_009:
  text:
    en: "Do you have any key-person risk (critical knowledge held by few individuals)?"
    ar: "هل لديك مخاطر الشخص الرئيسي (معرفة حرجة محفوظة لدى أفراد قليلين)؟"
  type: single_choice
  required: true
  options:
    - { value: "none", label: { en: "No, knowledge is well distributed", ar: "لا، المعرفة موزعة جيداً" }, score: 100 }
    - { value: "low", label: { en: "Low risk, backups in place", ar: "مخاطر منخفضة، يوجد بدائل" }, score: 75 }
    - { value: "moderate", label: { en: "Moderate risk, some key dependencies", ar: "مخاطر معتدلة، بعض التبعيات الرئيسية" }, score: 45 }
    - { value: "high", label: { en: "High risk, critical dependencies on individuals", ar: "مخاطر عالية، تبعيات حرجة على أفراد" }, score: 20 }
  agents: [MAYO]
  data_field: key_person_risk
  dimension: 7
  confidence_impact: high

WF_010:
  text:
    en: "How would you rate overall employee satisfaction?"
    ar: "كيف تقيّم رضا الموظفين بشكل عام؟"
  type: scale
  required: true
  scale_config:
    min: 1
    max: 5
    step: 1
    labels:
      min: { en: "Very dissatisfied", ar: "غير راضين جداً" }
      mid: { en: "Neutral", ar: "محايد" }
      max: { en: "Very satisfied", ar: "راضون جداً" }
  agents: [MAYO, DEMING]
  data_field: employee_satisfaction
  confidence_impact: medium

WF_011:
  text:
    en: "Is there any workforce context that standard questions might miss?"
    ar: "هل هناك أي سياق للقوى العاملة قد تفوته الأسئلة القياسية؟"
  type: human_context
  required: false
  description:
    en: "Examples: cultural factors, recent reorganization, union relationships, specialized workforce needs"
    ar: "أمثلة: عوامل ثقافية، إعادة تنظيم حديثة، علاقات نقابية، احتياجات قوى عاملة متخصصة"
  agents: [MAYO]
  data_field: human_context_workforce
  confidence_impact: high
```

---

# 8-12. Remaining Sections (Abbreviated for Space)

*The following sections follow the same structure. For brevity, I'm providing the section summaries with key question counts:*

## Section 6: Market & Competition (MK)
**Primary Agent:** Porter (The Strategist)
**Questions:** 10
- MK_001: Market size and growth
- MK_002: Target customer segments
- MK_003: Competitive landscape
- MK_004: Market share position
- MK_005: Competitive advantages
- MK_006: Pricing strategy
- MK_007: Go-to-market channels
- MK_008: Competitive threats
- MK_009: Market trends awareness
- MK_010: Human context - market

## Section 7: Supply Chain (SC)
**Primary Agent:** Ohno (The Flow Master)
**Questions:** 12
- SC_001: Supply chain complexity
- SC_002: Number of key suppliers
- SC_003: Supplier dependency
- SC_004: Inventory management approach
- SC_005: Inventory turns
- SC_006: Lead times
- SC_007: Supply chain disruption risk
- SC_008: Supplier relationships
- SC_009: Logistics management
- SC_010: Supply chain technology
- SC_011: Supply chain challenges
- SC_012: Human context - supply chain

## Section 8: Export Readiness (EX)
**Primary Agent:** Ricardo (The Navigator)
**Questions:** 15
- EX_001: Current export status
- EX_002: Export markets (current/target)
- EX_003: Export percentage of revenue
- EX_004: Export certifications
- EX_005: International compliance
- EX_006: Export documentation capability
- EX_007: Currency management
- EX_008: International logistics
- EX_009: Trade agreements knowledge
- EX_010: Export barriers
- EX_011: International marketing
- EX_012: Export partnerships
- EX_013: Government export support
- EX_014: Export priorities
- EX_015: Human context - export

## Section 9: Brand & Marketing (BR)
**Primary Agent:** Landor (The Herald)
**Questions:** 10
- BR_001: Brand awareness level
- BR_002: Brand identity (logo, guidelines)
- BR_003: Marketing channels used
- BR_004: Marketing budget
- BR_005: Social media presence
- BR_006: Content marketing
- BR_007: Marketing metrics tracked
- BR_008: Customer acquisition approach
- BR_009: Brand challenges
- BR_010: Human context - brand

## Section 10: Compliance & Certifications (CC)
**Primary Agent:** Marvin, Ricardo (shared)
**Questions:** 8
- CC_001: Business license status
- CC_002: Industry-specific certifications
- CC_003: Quality certifications
- CC_004: Environmental compliance
- CC_005: Labor law compliance
- CC_006: Data privacy compliance
- CC_007: Upcoming certification needs
- CC_008: Human context - compliance

---

# 13. Conditional Logic Rules

## 13.1 Logic Engine Configuration

```typescript
interface ConditionalRule {
  question_id: string;              // Question that triggers this rule
  operator: ConditionalOperator;    // Comparison operator
  value: string | string[] | number; // Value(s) to compare against
  action: 'show' | 'hide' | 'require' | 'skip_section';
}

type ConditionalOperator = 
  | 'equals'           // Exact match
  | 'not_equals'       // Not equal
  | 'in'               // Value in array
  | 'not_in'           // Value not in array
  | 'greater_than'     // Numeric comparison
  | 'less_than'        // Numeric comparison
  | 'contains'         // Array contains value
  | 'is_empty'         // Value is null/empty
  | 'is_not_empty';    // Value exists
```

## 13.2 Section-Level Conditions

```yaml
# Show Digital Maturity section if:
DM_SECTION:
  conditions:
    - OR:
      - { question_id: ADDON_SELECTION, operator: "contains", value: "digital" }
      - { question_id: BP_005, operator: "equals", value: "TDS" }  # Tech sector

# Show Export section if:
EX_SECTION:
  conditions:
    - OR:
      - { question_id: ADDON_SELECTION, operator: "contains", value: "export" }
      - { question_id: BP_009, operator: "in", value: ["regional_mena", "international"] }
      - { question_id: BP_010, operator: "contains", value: "export" }  # Export in priorities

# Show HR section if:
WF_SECTION:
  conditions:
    - OR:
      - { question_id: ADDON_SELECTION, operator: "contains", value: "hr" }
      - { question_id: BP_006, operator: "in", value: ["51-100", "101-250", "251-500", "500+"] }

# Show Supply Chain section if:
SC_SECTION:
  conditions:
    - OR:
      - { question_id: ADDON_SELECTION, operator: "contains", value: "supply_chain" }
      - { question_id: OP_001, operator: "in", value: ["manufacturing", "trading", "hybrid"] }
```

## 13.3 Financial Distress Early Warning

```yaml
# Trigger HITL Gate if financial distress indicators detected
FINANCIAL_DISTRESS_CHECK:
  triggers:
    - AND:
      - { question_id: FH_005, operator: "in", value: ["significant_loss", "moderate_loss"] }
      - { question_id: FH_006, operator: "in", value: ["0-1", "1-3"] }
  action: "trigger_hitl_gate"
  hitl_reason: "Financial distress indicators detected - recommend human advisor review"
```

---

# 14. Validation Rules

## 14.1 Field-Level Validation

```typescript
interface ValidationRule {
  type: ValidationType;
  params?: Record<string, any>;
  message: { en: string; ar: string };
}

type ValidationType = 
  | 'required'
  | 'min_length'
  | 'max_length'
  | 'min_value'
  | 'max_value'
  | 'pattern'           // Regex
  | 'email'
  | 'url'
  | 'phone'
  | 'min_selections'    // For multiple choice
  | 'max_selections'
  | 'custom';           // Custom validation function
```

## 14.2 Cross-Field Validation

```yaml
# Revenue should be reasonable for employee count
REVENUE_EMPLOYEE_CHECK:
  fields: [FH_001, BP_006]
  rule: |
    revenue_per_employee = FH_001.value / BP_006.score
    IF revenue_per_employee < 10000 OR revenue_per_employee > 1000000:
      warning: "Revenue per employee seems unusual - please verify"
  severity: warning  # Not blocking

# Gross margin should be >= net margin
MARGIN_CONSISTENCY:
  fields: [FH_004, FH_005]
  rule: |
    IF FH_004.score < FH_005.score AND FH_004.value != "unsure" AND FH_005.value != "unsure":
      error: "Net margin cannot exceed gross margin"
  severity: error  # Blocking
```

---

# 15. Agent Data Mapping

## 15.1 Agent Input Requirements

```yaml
DRUCKER:  # The Supervisor
  required_fields:
    - BP_001  # Company name
    - BP_003  # Country
    - BP_005  # Sector
    - BP_006  # Employee count
    - BP_010  # Strategic priorities
  optional_fields:
    - BP_013  # Primary challenge
    - BP_014  # Human context

GRAHAM:  # The Alchemist (Finance)
  required_fields:
    - FH_001  # Revenue
    - FH_003  # Revenue growth
    - FH_004  # Gross margin
    - FH_005  # Net margin
    - FH_006  # Cash runway
  optional_fields:
    - FH_010  # Funding history
    - FH_012  # Audit status
    - FH_020  # Human context

MARVIN:  # The Sentinel (Operations)
  required_fields:
    - OP_001  # Business model
    - OP_002  # Process maturity
    - OP_005  # Defect rate
    - OP_007  # On-time delivery
  optional_fields:
    - OP_008  # Certifications
    - OP_017  # Human context

LOVELACE:  # The Weaver (Digital)
  required_fields:
    - DM_001  # Digital maturity
    - DM_002  # Current systems
  optional_fields:
    - DM_006  # Analytics maturity
    - DM_012  # Human context

MAYO:  # The Cultivator (HR)
  required_fields:
    - WF_001  # Workforce composition
    - WF_002  # Turnover rate
  optional_fields:
    - WF_007  # Challenges
    - WF_011  # Human context

PORTER:  # The Strategist (Market)
  required_fields:
    - MK_001  # Market size
    - MK_003  # Competitive landscape
  optional_fields:
    - MK_010  # Human context

OHNO:  # The Flow Master (Supply Chain)
  required_fields:
    - SC_002  # Number of suppliers
    - SC_005  # Inventory turns
  optional_fields:
    - SC_012  # Human context

RICARDO:  # The Navigator (Export)
  required_fields:
    - EX_001  # Export status
  conditional_required:  # Required if exporting
    - EX_002  # Export markets
    - EX_004  # Export certifications
  optional_fields:
    - EX_015  # Human context

LANDOR:  # The Herald (Brand)
  required_fields:
    - BR_001  # Brand awareness
    - BR_003  # Marketing channels
  optional_fields:
    - BR_010  # Human context

DEMING:  # Quality Orchestrator
  aggregates_from:
    - All self_assessment_* fields
    - All *_challenges fields
    - All human_context_* fields

TUFTE:  # Report Generator
  receives:
    - All agent outputs
    - All human_context_* fields
    - Confidence scores from all agents
```

---

# 16. Implementation Guide

## 16.1 API Endpoint Structure

```python
# FastAPI Questionnaire Endpoints

@router.post("/questionnaire/start")
async def start_questionnaire(
    sme_id: str,
    language: str = "en",
    selected_addons: List[str] = []
) -> QuestionnaireSession:
    """Initialize a new questionnaire session"""
    
@router.get("/questionnaire/{session_id}/section/{section_code}")
async def get_section_questions(
    session_id: str,
    section_code: str
) -> List[Question]:
    """Get all questions for a section with conditional logic applied"""

@router.post("/questionnaire/{session_id}/respond")
async def submit_response(
    session_id: str,
    question_id: str,
    response: ResponseValue,
    human_context: Optional[str] = None
) -> ResponseResult:
    """Submit a single response, returns validation result and next question"""

@router.post("/questionnaire/{session_id}/section/{section_code}/complete")
async def complete_section(
    session_id: str,
    section_code: str
) -> SectionCompletion:
    """Mark section complete, run cross-field validations"""

@router.get("/questionnaire/{session_id}/progress")
async def get_progress(session_id: str) -> Progress:
    """Get completion status and estimated time remaining"""

@router.post("/questionnaire/{session_id}/complete")
async def complete_questionnaire(session_id: str) -> QuestionnaireCompletion:
    """Finalize questionnaire, trigger diagnostic agents"""
```

## 16.2 Frontend Integration Notes

```typescript
// React component structure suggestion

interface QuestionnaireState {
  session_id: string;
  current_section: SectionCode;
  current_question_index: number;
  responses: Record<string, ResponseValue>;
  human_context: Record<string, string>;
  validation_errors: Record<string, string>;
  progress: number;
}

// Progressive disclosure: Show one question at a time
// Save response on each submission (auto-save)
// Show human context prompt expansion on relevant questions
// Display progress bar and time estimate
// Support RTL layout for Arabic
```

## 16.3 Data Quality Scoring

```python
def calculate_data_quality_score(responses: Dict[str, ResponseValue]) -> float:
    """
    Calculate overall data quality score for HITL Gate 1
    
    Factors:
    - Completion rate (required vs answered)
    - Human context provided
    - "Not sure" / "Not tracked" selections
    - Internal consistency
    """
    
    total_weight = 0
    quality_score = 0
    
    for question_id, response in responses.items():
        question = get_question(question_id)
        weight = 1.0 if question.confidence_impact == 'high' else 0.5
        
        # Penalize "not sure" responses
        if response in ['unsure', 'not_tracked', 'dont_know']:
            quality_score += weight * 0.3
        # Bonus for human context
        elif question.allows_human_context and human_context.get(question_id):
            quality_score += weight * 1.2
        else:
            quality_score += weight * 1.0
            
        total_weight += weight
    
    return quality_score / total_weight if total_weight > 0 else 0
```

---

# Appendix A: Question ID Reference

| Section | Code | ID Range | Question Count |
|---------|------|----------|----------------|
| Business Profile | BP | BP_001 - BP_015 | 15 + 4 conditional |
| Financial Health | FH | FH_001 - FH_020 | 20 + 5 conditional |
| Operations | OP | OP_001 - OP_017 | 17 + 3 conditional |
| Digital Maturity | DM | DM_001 - DM_012 | 12 + 1 conditional |
| Workforce | WF | WF_001 - WF_011 | 11 |
| Market | MK | MK_001 - MK_010 | 10 |
| Supply Chain | SC | SC_001 - SC_012 | 12 |
| Export | EX | EX_001 - EX_015 | 15 + 2 conditional |
| Brand | BR | BR_001 - BR_010 | 10 |
| Compliance | CC | CC_001 - CC_008 | 8 |
| **TOTAL** | - | - | **~145 questions** |

---

# Appendix B: Localization Keys

All question text is stored with both `en` (English) and `ar` (Arabic) translations. The questionnaire engine should:

1. Default to user's browser language or explicit preference
2. Support mid-session language switching
3. Store responses in language-neutral format (value IDs)
4. Render RTL layout for Arabic

---

*Document Version: 1.0*
*Last Updated: December 2025*
*Author: RootRise Product Team*
