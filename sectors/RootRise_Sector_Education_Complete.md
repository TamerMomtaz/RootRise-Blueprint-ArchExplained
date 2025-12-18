# RootRise Sector Knowledge Pack
# Education & Training
## Version 1.0 | December 2025

---

# Document Information

| Attribute | Value |
|-----------|-------|
| **Sector ID** | `education_training` |
| **Version** | 1.0 |
| **Last Updated** | December 2025 |
| **Status** | Active |
| **ISIC Rev.4 Divisions** | 85 (Education) |
| **Primary Markets** | Egypt, Saudi Arabia, UAE, Jordan, Morocco |
| **SME Employee Range** | 5-250 |
| **SME Revenue Range** | $100K - $25M |

## Sector Overview

Education & Training in MENA is experiencing **transformative growth** driven by demographic dynamics (60%+ population under 30), government investment in human capital, skills gaps across industries, and digital learning acceleration. The sector spans early childhood through professional development, with particular SME opportunity in vocational training, corporate learning, and EdTech.

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                    EDUCATION & TRAINING VALUE CHAIN                              │
├─────────────────────────────────────────────────────────────────────────────────┤
│                                                                                  │
│   FORMAL EDUCATION                    PROFESSIONAL TRAINING                     │
│   ────────────────                    ─────────────────────                     │
│                                                                                  │
│   ┌──────────────┐                    ┌──────────────────────┐                  │
│   │ K-12 SCHOOLS │                    │  CORPORATE TRAINING  │                  │
│   │ • Private    │                    │  • In-house programs │                  │
│   │ • International│                  │  • External providers│                  │
│   │ • Bilingual  │                    │  • Leadership dev    │                  │
│   └──────┬───────┘                    └──────────┬───────────┘                  │
│          │                                       │                              │
│          ▼                                       ▼                              │
│   ┌──────────────┐                    ┌──────────────────────┐                  │
│   │ HIGHER ED    │                    │  VOCATIONAL/TVET     │                  │
│   │ • Universities│                   │  • Technical skills  │                  │
│   │ • Colleges   │                    │  • Trade certificates│                  │
│   │ • Graduate   │                    │  • Apprenticeships   │                  │
│   └──────────────┘                    └──────────────────────┘                  │
│                                                                                  │
│   ENABLING SEGMENTS                   DELIVERY CHANNELS                         │
│   ─────────────────                   ──────────────────                        │
│   ┌──────────────┐                    ┌──────────────────────┐                  │
│   │ EDTECH       │                    │  • Face-to-face      │                  │
│   │ • LMS        │                    │  • Online/Virtual    │                  │
│   │ • E-learning │                    │  • Blended/Hybrid    │                  │
│   │ • Assessment │                    │  • Mobile learning   │                  │
│   │ • Content    │                    │  • Microlearning     │                  │
│   └──────────────┘                    └──────────────────────┘                  │
│                                                                                  │
│   KEY MENA CHARACTERISTICS:                                                     │
│   • Young population (60%+ under 30) = massive demand                          │
│   • Government investment (Vision 2030, Egypt 2030)                            │
│   • Skills mismatch driving vocational focus                                   │
│   • Arabic + English bilingual requirements                                    │
│   • Gender-specific considerations (evolving)                                  │
│   • EdTech adoption accelerated post-COVID                                     │
│   • Nationalization programs (Saudization) creating training demand           │
│                                                                                  │
└─────────────────────────────────────────────────────────────────────────────────┘
```

## Applicable Countries

| Country Code | Country Name | Student Population | Education GDP % |
|--------------|--------------|-------------------|-----------------|
| EG | Egypt | ~25 million | 4-5% |
| SA | Saudi Arabia | ~8 million | 5-7% |
| AE | UAE | ~1.5 million | 4-5% |
| JO | Jordan | ~2.5 million | 4-5% |
| MA | Morocco | ~8 million | 5-6% |

---

# Dimension 1: Industry Classification

## 1.1 ISIC Rev.4 Classification

### Primary ISIC Codes

| Division | Description | SME Relevance |
|----------|-------------|---------------|
| **85** | Education | **Very High** |

### Detailed Class Breakdown

**Division 85 - Education:**

| Class | Description | SME Relevance |
|-------|-------------|---------------|
| 8510 | Pre-primary and primary education | High |
| **8521** | **General secondary education** | **High** |
| **8522** | **Technical and vocational secondary** | **Very High** |
| 8530 | Higher education | Medium |
| **8541** | **Sports and recreation education** | **High** |
| **8542** | **Cultural education** | **High** |
| **8549** | **Other education n.e.c.** | **Very High** |
| **8550** | **Educational support activities** | **Very High** |

## 1.2 Subsector Taxonomy

```json
{
  "subsectors": [
    {
      "subsector_id": "private_k12",
      "subsector_name": "Private K-12 Schools",
      "subsector_name_ar": "المدارس الخاصة",
      "description": "Private primary and secondary schools including international curricula",
      "isic_codes": ["8510", "8521"],
      "typical_sme_size": "50-250 employees",
      "typical_sme_revenue": "$1M-$25M",
      "mena_market_size_estimate": "$25-35 billion",
      "growth_rate_5yr": "6-10%",
      "key_segments": ["International curriculum", "National private", "Bilingual"]
    },
    {
      "subsector_id": "early_childhood",
      "subsector_name": "Early Childhood Education (ECE)",
      "subsector_name_ar": "التعليم المبكر",
      "description": "Nurseries, preschools, kindergartens",
      "isic_codes": ["8510"],
      "typical_sme_size": "5-50 employees",
      "typical_sme_revenue": "$100K-$3M",
      "mena_market_size_estimate": "$5-8 billion",
      "growth_rate_5yr": "8-15%",
      "key_segments": ["Premium nurseries", "Community preschools", "Franchise"]
    },
    {
      "subsector_id": "vocational_tvet",
      "subsector_name": "Vocational & Technical Training (TVET)",
      "subsector_name_ar": "التدريب المهني والتقني",
      "description": "Technical skills training, trade certifications, apprenticeships",
      "isic_codes": ["8522", "8549"],
      "typical_sme_size": "10-100 employees",
      "typical_sme_revenue": "$200K-$10M",
      "mena_market_size_estimate": "$8-15 billion",
      "growth_rate_5yr": "10-18%",
      "key_segments": ["Technical trades", "Healthcare skills", "Hospitality", "IT"]
    },
    {
      "subsector_id": "corporate_training",
      "subsector_name": "Corporate Training & Development",
      "subsector_name_ar": "التدريب المؤسسي",
      "description": "Professional development, leadership training, skills programs",
      "isic_codes": ["8549", "8550"],
      "typical_sme_size": "5-80 employees",
      "typical_sme_revenue": "$200K-$15M",
      "mena_market_size_estimate": "$4-8 billion",
      "growth_rate_5yr": "8-15%",
      "key_segments": ["Leadership", "Technical skills", "Soft skills", "Compliance"]
    },
    {
      "subsector_id": "language_training",
      "subsector_name": "Language Training",
      "subsector_name_ar": "تعليم اللغات",
      "description": "English language, Arabic for non-natives, other languages",
      "isic_codes": ["8549"],
      "typical_sme_size": "5-60 employees",
      "typical_sme_revenue": "$100K-$5M",
      "mena_market_size_estimate": "$3-5 billion",
      "growth_rate_5yr": "6-12%",
      "key_segments": ["English (EFL)", "Arabic", "Business language", "Test prep"]
    },
    {
      "subsector_id": "test_prep",
      "subsector_name": "Test Preparation & Tutoring",
      "subsector_name_ar": "التحضير للاختبارات والدروس الخصوصية",
      "description": "SAT, IELTS, GMAT, school exam preparation, private tutoring",
      "isic_codes": ["8549", "8550"],
      "typical_sme_size": "3-40 employees",
      "typical_sme_revenue": "$100K-$3M",
      "mena_market_size_estimate": "$2-4 billion",
      "growth_rate_5yr": "8-15%",
      "key_segments": ["University admission", "Professional certification", "School support"]
    },
    {
      "subsector_id": "edtech_platforms",
      "subsector_name": "EdTech & E-Learning Platforms",
      "subsector_name_ar": "تقنيات التعليم",
      "description": "Online learning platforms, LMS, digital content, assessment tools",
      "isic_codes": ["8549", "8550"],
      "typical_sme_size": "10-100 employees",
      "typical_sme_revenue": "$200K-$20M",
      "mena_market_size_estimate": "$3-6 billion",
      "growth_rate_5yr": "20-35%",
      "key_segments": ["B2B (schools/corporate)", "B2C (consumer)", "Content", "Assessment"]
    },
    {
      "subsector_id": "professional_certification",
      "subsector_name": "Professional Certification & Licensing",
      "subsector_name_ar": "الشهادات المهنية",
      "description": "Professional certifications (PMP, CPA, CFA), licensing programs",
      "isic_codes": ["8549"],
      "typical_sme_size": "5-50 employees",
      "typical_sme_revenue": "$200K-$8M",
      "mena_market_size_estimate": "$1-3 billion",
      "growth_rate_5yr": "10-18%",
      "key_segments": ["Finance", "Project management", "IT", "HR", "Industry-specific"]
    },
    {
      "subsector_id": "enrichment_activities",
      "subsector_name": "Enrichment & Extracurricular",
      "subsector_name_ar": "الأنشطة الإثرائية",
      "description": "Arts, music, sports, STEM clubs, coding for kids",
      "isic_codes": ["8541", "8542", "8549"],
      "typical_sme_size": "5-40 employees",
      "typical_sme_revenue": "$100K-$3M",
      "mena_market_size_estimate": "$2-4 billion",
      "growth_rate_5yr": "12-20%",
      "key_segments": ["STEM/Robotics", "Arts/Music", "Sports academies", "Coding"]
    },
    {
      "subsector_id": "special_needs",
      "subsector_name": "Special Education & Learning Support",
      "subsector_name_ar": "التعليم الخاص وصعوبات التعلم",
      "description": "Special needs education, learning disabilities support, therapy",
      "isic_codes": ["8510", "8549"],
      "typical_sme_size": "10-60 employees",
      "typical_sme_revenue": "$200K-$5M",
      "mena_market_size_estimate": "$1-2 billion",
      "growth_rate_5yr": "12-20%",
      "key_segments": ["Learning centers", "Therapy services", "Inclusive education support"]
    }
  ]
}
```

## 1.3 Education Segments by Level

### Formal Education Levels

| Level | Age Range | Duration | Key Providers |
|-------|-----------|----------|---------------|
| Early Childhood (ECE) | 0-5 years | 2-4 years | Nurseries, preschools |
| Primary | 6-11 years | 6 years | Public, private schools |
| Middle/Prep | 12-14 years | 3 years | Public, private schools |
| Secondary | 15-17 years | 3 years | General, vocational tracks |
| Higher Education | 18+ years | 3-6 years | Universities, colleges |
| Postgraduate | 22+ years | 1-5 years | Universities, institutes |

### Curriculum Types (K-12)

| Curriculum | Languages | Key Markets | Fee Range (Annual) |
|------------|-----------|-------------|-------------------|
| National/Government | Arabic | All MENA | Free-$500 |
| National Private | Arabic + English | All MENA | $1,000-5,000 |
| American | English | UAE, Saudi, Egypt | $5,000-30,000 |
| British | English | UAE, Saudi, Egypt | $5,000-35,000 |
| IB (International Baccalaureate) | English | UAE, Saudi | $10,000-40,000 |
| French | French + Arabic | Morocco, Egypt | $3,000-15,000 |
| Indian | English | UAE, Saudi | $2,000-8,000 |
| Pakistani | English/Urdu | UAE, Saudi | $2,000-6,000 |

## 1.4 Training Delivery Models

| Model | Description | Cost Structure | Best For |
|-------|-------------|----------------|----------|
| Classroom/ILT | Instructor-led training | High (venue, trainer) | Complex skills, networking |
| Virtual ILT (VILT) | Live online instruction | Medium | Geographic spread |
| Self-Paced E-Learning | Asynchronous online | Low per learner | Scale, compliance |
| Blended | Mix of online + classroom | Medium | Comprehensive programs |
| Coaching/Mentoring | 1:1 or small group | High per person | Executive development |
| On-the-Job | Workplace learning | Embedded cost | Practical skills |
| Microlearning | Short, focused modules | Low | Reinforcement, mobile |

## 1.5 Value Chain Position

| Position | Description | Typical SME Type | Margin Profile |
|----------|-------------|------------------|----------------|
| **Content Creator** | Develop curriculum/materials | Publishers, EdTech | 40-70% |
| **Platform Provider** | LMS, delivery technology | EdTech companies | 60-80% (SaaS) |
| **Training Provider** | Deliver programs | Training centers, schools | 15-35% |
| **Certification Body** | Assess and certify | Testing centers | 30-50% |
| **Aggregator/Broker** | Connect learners to programs | Marketplaces | 15-30% commission |
| **Support Services** | Admin, recruitment, placement | Service providers | 20-40% |

## 1.6 Adjacent Sectors

| Adjacent Sector | Relationship | Integration Level |
|-----------------|--------------|-------------------|
| **Healthcare** | Medical training, nursing schools | High |
| **Hospitality** | Hospitality training academies | High |
| **Technology** | IT training, coding bootcamps | Very High |
| **Financial Services** | Finance certifications | High |
| **Human Resources** | Talent development | Very High |
| **Real Estate** | School/campus development | Medium |

---

# Dimension 2: Financial Benchmarks

## 2.1 Revenue Metrics

### Private K-12 Schools

| Metric | Budget School | Mid-Tier | Premium | International |
|--------|--------------|----------|---------|---------------|
| **Annual Fee/Student** | $1,000-3,000 | $3,000-8,000 | $8,000-20,000 | $15,000-40,000 |
| **Revenue/Student (Total)** | $1,200-3,500 | $3,500-9,000 | $9,000-25,000 | $18,000-50,000 |
| **Students/Teacher** | 25-35 | 18-25 | 12-20 | 10-18 |
| **Revenue/Teacher** | $30-80K | $60-150K | $100-300K | $150-500K |
| **Occupancy (Enrollment/Capacity)** | 85-95% | 80-95% | 75-90% | 70-90% |

### Training Centers

| Metric | Language Center | Vocational | Corporate Training | Test Prep |
|--------|----------------|------------|-------------------|-----------|
| **Revenue/Student/Year** | $500-3,000 | $1,000-8,000 | $500-5,000 | $300-2,000 |
| **Revenue/Trainer Hour** | $30-80 | $40-150 | $80-300 | $50-150 |
| **Revenue/sqm/month** | $50-150 | $40-120 | $80-250 | $60-180 |
| **Utilization (Room/Time)** | 40-70% | 50-80% | 30-60% | 50-75% |

### EdTech Platforms

| Metric | B2C Platform | B2B Platform | Content Provider |
|--------|-------------|--------------|------------------|
| **ARPU (Monthly)** | $10-50 | $5-20/user | License-based |
| **ARPU (Annual)** | $80-400 | $50-200/user | $1-10K/client |
| **CAC** | $20-100 | $200-2,000 | $500-5,000 |
| **LTV:CAC** | 2-5x | 3-8x | 5-15x |
| **Churn (Monthly)** | 5-15% | 2-8% | 10-25% annual |

## 2.2 Profitability Benchmarks

### Private Schools

| Metric | Budget | Mid-Tier | Premium | International |
|--------|--------|----------|---------|---------------|
| **Teacher Salaries** | 45-55% | 40-50% | 35-45% | 35-45% |
| **Facilities/Rent** | 10-15% | 12-18% | 15-22% | 15-25% |
| **Admin/Support Staff** | 10-15% | 10-15% | 10-15% | 10-15% |
| **Teaching Materials** | 3-6% | 4-8% | 5-10% | 5-12% |
| **Marketing** | 2-5% | 3-7% | 4-8% | 5-10% |
| **Utilities** | 3-6% | 3-5% | 3-5% | 3-6% |
| **EBITDA Margin** | 8-15% | 12-20% | 15-25% | 15-28% |
| **Net Margin** | 3-10% | 8-15% | 10-20% | 10-22% |

### Training Centers

| Metric | Language | Vocational | Corporate | Test Prep |
|--------|----------|------------|-----------|-----------|
| **Trainer/Instructor Cost** | 35-50% | 30-45% | 25-40% | 30-45% |
| **Facilities** | 12-20% | 15-25% | 8-15% | 12-18% |
| **Materials/Content** | 5-10% | 8-15% | 10-20% | 8-15% |
| **Marketing/Sales** | 8-15% | 5-12% | 10-20% | 10-18% |
| **Admin** | 8-12% | 8-12% | 8-12% | 8-12% |
| **EBITDA Margin** | 12-22% | 15-28% | 18-35% | 15-25% |
| **Net Margin** | 6-15% | 8-18% | 12-25% | 8-18% |

### EdTech

| Metric | B2C | B2B | Content |
|--------|-----|-----|---------|
| **Content/Product** | 15-30% | 20-35% | 30-50% |
| **Technology** | 15-25% | 20-30% | 10-20% |
| **Sales/Marketing** | 25-45% | 20-35% | 15-25% |
| **Support** | 5-12% | 8-15% | 5-10% |
| **G&A** | 10-15% | 10-15% | 10-15% |
| **Gross Margin** | 60-80% | 65-85% | 50-70% |
| **EBITDA Margin** | -20% to +15% | 0-25% | 10-30% |

## 2.3 Cost Structure Details

### School Cost Breakdown

| Cost Category | Description | % of Revenue |
|---------------|-------------|--------------|
| **Personnel (Teaching)** | Teachers, teaching assistants | 35-50% |
| **Personnel (Non-Teaching)** | Admin, support, security | 10-18% |
| **Facilities** | Rent/mortgage, maintenance | 10-22% |
| **Utilities** | Electricity, water, HVAC | 3-6% |
| **Curriculum/Materials** | Textbooks, supplies, licenses | 3-10% |
| **Technology** | IT infrastructure, software | 2-5% |
| **Marketing/Admissions** | Student recruitment | 2-8% |
| **Insurance** | Liability, property | 1-3% |
| **Professional Development** | Teacher training | 1-3% |
| **Accreditation/Licensing** | Regulatory compliance | 0.5-2% |

### Training Center Cost Breakdown

| Cost Category | Fixed/Variable | % of Revenue |
|---------------|----------------|--------------|
| Trainers/Instructors | Semi-variable | 25-45% |
| Facility Rent | Fixed | 10-20% |
| Content Development | Semi-fixed | 5-15% |
| Marketing | Variable | 8-18% |
| Technology | Semi-fixed | 3-8% |
| Admin Staff | Fixed | 8-15% |
| Materials/Consumables | Variable | 3-8% |
| Certification Fees | Variable | 2-5% |

## 2.4 Working Capital Requirements

### Cash Flow Characteristics

| Subsector | Collection Pattern | Payment Pattern | Working Capital |
|-----------|-------------------|-----------------|-----------------|
| Schools | Term-based (advance) | Monthly salaries | Low (5-10%) |
| Vocational | Course-based | Per program | Medium (10-15%) |
| Corporate Training | Project-based (30-60 DSO) | Trainer fees | Medium-High (15-25%) |
| Test Prep | Enrollment-based | Ongoing | Low (5-10%) |
| EdTech B2C | Subscription | Tech + Content | Medium (10-20%) |
| EdTech B2B | Annual contracts | Development | High (20-30%) |

### Seasonality

| Segment | Peak Period | Low Period | Variance |
|---------|-------------|------------|----------|
| K-12 Schools | Aug-Sep (enrollment) | Jun-Jul | Moderate |
| Vocational | Sep-Oct, Jan-Feb | Ramadan, summer | High |
| Corporate | Q1, Q4 | Ramadan, summer | High |
| Test Prep | Pre-exam periods | Post-exam | Very High |
| Language | Continuous | Ramadan, summer | Moderate |

## 2.5 Capital Requirements

### School Startup

| School Type | Land/Building | FF&E | Working Capital | Total |
|-------------|---------------|------|-----------------|-------|
| Nursery (50 children) | $200K-1M | $50-150K | $50-100K | $300K-1.3M |
| Small School (200 students) | $500K-3M | $150-500K | $100-300K | $750K-4M |
| Medium School (500 students) | $2-8M | $500K-2M | $300-800K | $3-11M |
| Large School (1,000+ students) | $5-20M | $1-5M | $500K-2M | $7-27M |
| International (Premium) | $10-50M | $3-10M | $1-3M | $14-63M |

### Training Center Startup

| Type | Size (sqm) | Cost/sqm | Equipment | Total |
|------|-----------|----------|-----------|-------|
| Language Center | 200-500 | $500-1,000 | $30-80K | $130-580K |
| Vocational Center | 500-2,000 | $600-1,500 | $100-500K | $400K-3.5M |
| Corporate Training | 300-800 | $800-2,000 | $50-150K | $290K-1.75M |
| Test Prep Center | 200-400 | $400-800 | $30-60K | $110-380K |

## 2.6 Valuation Multiples

| Subsector | Revenue Multiple | EBITDA Multiple | Key Drivers |
|-----------|------------------|-----------------|-------------|
| Private Schools | 1-3x | 6-12x | Reputation, enrollment, location |
| Nurseries/ECE | 1-2.5x | 5-10x | Brand, occupancy, location |
| Vocational Training | 0.8-2x | 5-10x | Accreditation, placement rates |
| Corporate Training | 0.5-1.5x | 4-8x | Client relationships, IP |
| Test Prep | 0.5-1.5x | 4-8x | Brand, results, scale |
| EdTech (Growth) | 3-10x | 15-40x | Growth rate, retention, TAM |
| EdTech (Mature) | 1-4x | 8-15x | Profitability, retention |

---

# Dimension 3: Operational KPIs

## 3.1 School KPIs

### Enrollment & Capacity

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Enrollment Rate** | Students/Capacity | <75% | 75-85% | 85-92% | >92% |
| **Retention Rate** | Re-enrollment YoY | <80% | 80-88% | 88-94% | >94% |
| **Attrition Rate** | Mid-year withdrawals | >8% | 4-8% | 2-4% | <2% |
| **Waitlist Ratio** | Waitlist/Available spots | <0.5 | 0.5-1 | 1-2 | >2 |
| **Application Conversion** | Enrolled/Applications | <40% | 40-55% | 55-70% | >70% |

### Academic Performance

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Pass Rate** | Students passing | <80% | 80-90% | 90-96% | >96% |
| **External Exam Results** | Above national average | Below | Average | Above | Top 10% |
| **University Placement** | % to target universities | <50% | 50-70% | 70-85% | >85% |
| **Learning Progress** | Assessment gains | Below target | On target | Above | Exceptional |

### Teacher Quality

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Teacher Turnover** | Annual replacement | >25% | 15-25% | 8-15% | <8% |
| **Teacher Qualification** | % with required credentials | <85% | 85-92% | 92-98% | >98% |
| **Student:Teacher Ratio** | Students per teacher | >25 | 20-25 | 15-20 | <15 |
| **Professional Development** | Hours/teacher/year | <20 | 20-40 | 40-60 | >60 |

### Parent/Student Satisfaction

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Parent Satisfaction** | Survey score | <70% | 70-80% | 80-90% | >90% |
| **NPS** | Net Promoter Score | <20 | 20-40 | 40-60 | >60 |
| **Complaint Rate** | Per 100 students | >10 | 5-10 | 2-5 | <2 |
| **Parent Engagement** | Event attendance | <40% | 40-60% | 60-80% | >80% |

## 3.2 Training Center KPIs

### Enrollment & Utilization

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Enrollment/Class** | Average class size | <8 | 8-12 | 12-18 | 18-25 |
| **Room Utilization** | Hours used/available | <40% | 40-55% | 55-70% | >70% |
| **Trainer Utilization** | Billable hours/available | <50% | 50-65% | 65-80% | >80% |
| **Course Fill Rate** | Enrolled/Capacity | <60% | 60-75% | 75-90% | >90% |

### Training Effectiveness

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Completion Rate** | Finish program | <70% | 70-82% | 82-92% | >92% |
| **Certification Pass Rate** | First-time pass | <60% | 60-75% | 75-88% | >88% |
| **Post-Training Assessment** | Knowledge improvement | <20% | 20-35% | 35-50% | >50% |
| **Skill Application** | Using skills at work | <40% | 40-60% | 60-80% | >80% |

### Business Impact (Corporate)

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **ROI (Kirkpatrick L4)** | Business impact/cost | <1.5x | 1.5-3x | 3-5x | >5x |
| **Performance Improvement** | Measured outcomes | <10% | 10-20% | 20-35% | >35% |
| **Behavior Change** | Observable application | <30% | 30-50% | 50-70% | >70% |
| **Manager Satisfaction** | Sponsor feedback | <70% | 70-80% | 80-90% | >90% |

### Learner Experience

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Satisfaction Score** | Post-training survey | <3.5/5 | 3.5-4/5 | 4-4.5/5 | >4.5/5 |
| **NPS** | Recommendation | <30 | 30-50 | 50-70 | >70 |
| **Instructor Rating** | Trainer evaluation | <3.8/5 | 3.8-4.2/5 | 4.2-4.6/5 | >4.6/5 |
| **Referral Rate** | From past students | <10% | 10-20% | 20-35% | >35% |

## 3.3 EdTech Platform KPIs

### Engagement

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **DAU/MAU** | Daily/monthly active | <15% | 15-25% | 25-40% | >40% |
| **Session Duration** | Time per visit | <5 min | 5-12 min | 12-25 min | >25 min |
| **Course Completion** | Finish started courses | <20% | 20-40% | 40-60% | >60% |
| **Content Consumption** | Lessons/user/month | <5 | 5-15 | 15-30 | >30 |

### Growth & Retention

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Monthly Growth** | New users | <5% | 5-12% | 12-25% | >25% |
| **Activation Rate** | Complete onboarding | <30% | 30-50% | 50-70% | >70% |
| **Monthly Churn** | Subscription cancellation | >12% | 8-12% | 4-8% | <4% |
| **Net Revenue Retention** | Expansion - Churn | <90% | 90-100% | 100-115% | >115% |

### Learning Outcomes

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Assessment Pass Rate** | Quizzes/tests | <60% | 60-75% | 75-88% | >88% |
| **Skill Certification** | Earn credentials | <20% | 20-40% | 40-60% | >60% |
| **Learning Velocity** | Progress per week | Below target | On target | Above | 150%+ |

## 3.4 Placement & Employment KPIs (Vocational)

| KPI | Definition | Poor | Average | Good | Excellent |
|-----|------------|------|---------|------|-----------|
| **Placement Rate** | Employed within 6 months | <50% | 50-65% | 65-80% | >80% |
| **Placement in Field** | Job matches training | <40% | 40-60% | 60-80% | >80% |
| **Starting Salary** | vs. market average | Below | Average | Above | Top 25% |
| **Employer Satisfaction** | Hiring company feedback | <70% | 70-80% | 80-90% | >90% |
| **Time to Employment** | Months after completion | >6 | 4-6 | 2-4 | <2 |

---

*End of Part 1 - Continue to Part 2 for Dimensions 4-7*
# Dimension 4: Regulatory Landscape

## 4.1 Business Licenses & Permits

### School Licenses

| License Type | Issuing Authority | Validity | Cost Range |
|--------------|-------------------|----------|------------|
| School Operating License | Ministry of Education | 1-5 years | $5,000-50,000 |
| Curriculum Accreditation | Education Authority | 3-5 years | $5,000-30,000 |
| Building Safety Certificate | Civil Defense | Annual | $500-3,000 |
| Health & Safety Permit | Health Authority | Annual | $500-2,000 |
| Municipality/Zoning Permit | Local Municipality | Annual | $500-5,000 |
| International Accreditation | IB, Cambridge, etc. | 3-5 years | $10,000-50,000 |

### Training Center Licenses

| License Type | Issuing Authority | Validity | Cost Range |
|--------------|-------------------|----------|------------|
| Training Institute License | Education/Labor Ministry | 1-3 years | $2,000-15,000 |
| Vocational Training License | TVET Authority | 1-3 years | $2,000-20,000 |
| Professional Training License | Professional Council | 1-3 years | $1,000-10,000 |
| Trade License | Commerce Ministry | Annual | $500-3,000 |
| Foreign Curriculum License | Education Authority | 1-3 years | $5,000-25,000 |

### EdTech Licenses

| License Type | Issuing Authority | Validity | Cost Range |
|--------------|-------------------|----------|------------|
| E-Learning Platform License | Education Ministry | 1-3 years | $2,000-15,000 |
| Content Approval | Education Authority | Per content | $500-5,000 |
| Data Protection Registration | Data Authority | Annual | $500-3,000 |
| Payment Gateway Integration | Central Bank | Ongoing | $2,000-10,000 |

## 4.2 Accreditation Requirements

### School Accreditation

| Accreditor | Type | Recognition | Process Time |
|------------|------|-------------|--------------|
| National MOE | Government | Mandatory | 3-12 months |
| CIS (Council of International Schools) | International | Prestigious | 2-4 years |
| NEASC | US regional | US recognition | 2-4 years |
| BSO (British Schools Overseas) | British | UK recognition | 1-2 years |
| IB Authorization | International Baccalaureate | IB programs | 2-3 years |
| Cambridge International | British curriculum | A-Levels, IGCSE | 1-2 years |

### Training Accreditation

| Type | Bodies | Requirements |
|------|--------|--------------|
| National TVET | National skills authority | Curriculum, facilities, trainers |
| Industry Certification | Professional bodies (PMI, CIPD) | Authorized Training Partner |
| International Quality | ISO 29993 (Learning services) | Quality management system |
| Sector-Specific | Industry regulators | Sector requirements |

## 4.3 Compliance Requirements

### School Compliance

| Requirement | Standard | Frequency |
|-------------|----------|-----------|
| Teacher Licensing | Ministry credentials | Per hire |
| Curriculum Approval | MOE framework | Annual/per change |
| Student Records | Data protection | Ongoing |
| Child Protection | Safeguarding policy | Annual review |
| Fire Safety | Building code | Annual inspection |
| Health Standards | Student/staff health | Annual |
| Financial Reporting | Regulatory standards | Annual |

### Training Compliance

| Requirement | Standard | Frequency |
|-------------|----------|-----------|
| Trainer Qualifications | Certification requirements | Per trainer |
| Facilities Standards | Health & safety | Annual inspection |
| Course Approval | Content registration | Per program |
| Student Data | Privacy regulations | Ongoing |
| Advertising Standards | Truthful marketing | Ongoing |
| Consumer Protection | Refund policies | Ongoing |

## 4.4 Certifications

| Certification | Purpose | Cost Range | Validity |
|---------------|---------|------------|----------|
| ISO 9001 | Quality management | $3,000-15,000 | 3 years |
| ISO 21001 | Educational organizations | $5,000-20,000 | 3 years |
| ISO 29993 | Learning services | $5,000-20,000 | 3 years |
| KHDA Rating (UAE) | School quality | N/A (inspection) | Annual |
| COGNIA (AdvancED) | School accreditation | $10,000-30,000 | 5 years |
| TESOL/CELTA | Language teaching | $1,500-3,000/trainer | Lifetime |

## 4.5 Regulatory Bodies by Country

### Egypt

| Authority | Responsibility |
|-----------|---------------|
| Ministry of Education | K-12 regulation |
| Ministry of Higher Education | Universities, colleges |
| NAQAAE | Quality assurance |
| Technical Education Authority | TVET |
| Private Schools Department | Private school licensing |

### Saudi Arabia

| Authority | Responsibility |
|-----------|---------------|
| Ministry of Education | All education levels |
| Education & Training Evaluation Commission | Quality assurance |
| Technical & Vocational Training Corporation (TVTC) | TVET |
| Human Resources Development Fund (HRDF/Hadaf) | Training subsidies |
| National Center for Assessment | Testing |

### UAE

| Authority | Responsibility |
|-----------|---------------|
| Ministry of Education | Federal education |
| KHDA (Dubai) | Dubai private schools |
| ADEK (Abu Dhabi) | Abu Dhabi education |
| NQA | Qualifications framework |
| Knowledge Fund | Higher education |

### Jordan

| Authority | Responsibility |
|-----------|---------------|
| Ministry of Education | K-12 |
| Ministry of Higher Education | Universities |
| Vocational Training Corporation | TVET |
| AQACHEI | Quality assurance |
| Private Education Directorate | Private schools |

### Morocco

| Authority | Responsibility |
|-----------|---------------|
| Ministry of National Education | K-12 |
| Ministry of Higher Education | Universities |
| OFPPT | Vocational training |
| ANEAQ | Quality assurance |
| ANAPEC | Employment/training link |

## 4.6 Teacher/Trainer Requirements

### Teacher Licensing by Country

| Country | Minimum Qualification | Additional Requirements |
|---------|----------------------|------------------------|
| Egypt | Bachelor's + Education diploma | Ministry registration |
| Saudi | Bachelor's + Teaching certificate | MOE license, background check |
| UAE | Bachelor's + Teaching credential | Attestation, CAP exam (Dubai) |
| Jordan | Bachelor's + Education studies | Ministry certification |
| Morocco | Bachelor's + Teacher training | CRMEF certification |

### Trainer Requirements

| Training Type | Qualification | Experience | Certification |
|---------------|---------------|------------|---------------|
| Vocational | Diploma/Bachelor's in field | 3-5 years industry | Train-the-Trainer |
| Corporate (Soft Skills) | Bachelor's + credentials | 5-10 years relevant | ATD, CIPD preferred |
| Technical (IT, etc.) | Vendor certification | 3-5 years technical | Industry certs |
| Language | Bachelor's + TESOL/CELTA | 2-3 years teaching | TESOL/CELTA/DELTA |
| Professional Cert | Subject expert | 5-10 years practice | Professional designation |

---

# Dimension 5: Competitive Dynamics

## 5.1 Market Structure

| Subsector | Concentration | Market Leaders | Fragmentation |
|-----------|---------------|----------------|---------------|
| Private Schools (Premium) | Medium | GEMS, Aldar, Taaleem | Group-dominated |
| Private Schools (Mid-tier) | Low | Many local operators | Highly fragmented |
| Nurseries/ECE | Low | Some franchise chains | Very fragmented |
| Corporate Training | Low | Big 4, boutiques | Fragmented |
| Language Schools | Medium | British Council, Berlitz, locals | Moderate |
| Test Prep | Medium | Kaplan, ETS, local brands | Moderate |
| EdTech | Medium (consolidating) | Coursera, Udemy, regional | Consolidating |
| Vocational | Low-Medium | Government + private | Mixed |

## 5.2 Porter's Five Forces

```
┌─────────────────────────────────────────────────────────────────────┐
│              EDUCATION FIVE FORCES SUMMARY                          │
├─────────────────────────────────────────────────────────────────────┤
│                                                                      │
│                  NEW ENTRANTS: 2/5                                  │
│                  (Capital intensive; accreditation barriers)        │
│                        │                                            │
│                        ▼                                            │
│   SUPPLIER POWER ────────────► INDUSTRY ◄───── BUYER POWER         │
│       3/5                      RIVALRY           3/5               │
│   (Quality teachers              3.5/5       (Price sensitivity,    │
│    in demand)               (Growing capacity,   but quality        │
│                              differentiation)    matters)           │
│                        │                                            │
│                        ▼                                            │
│                SUBSTITUTES: 3/5                                     │
│                (Online learning, free content, self-study)          │
│                                                                      │
│   OVERALL ATTRACTIVENESS: MODERATE-GOOD                             │
│   Key: Quality + Outcomes + Reputation + Location                   │
└─────────────────────────────────────────────────────────────────────┘
```

### Force Details

| Force | Rating | Key Factors |
|-------|--------|-------------|
| **New Entrants** | 2/5 | High capital; accreditation time; reputation building |
| **Supplier Power** | 3/5 | Quality teachers scarce; technology vendors moderate |
| **Buyer Power** | 3/5 | Price-sensitive but quality-focused; information asymmetry |
| **Substitutes** | 3/5 | Free online content; self-study; peer learning |
| **Rivalry** | 3.5/5 | Growing capacity; some price competition; differentiation possible |

## 5.3 Competitive Strategies

| Strategy | Description | Best For | Requirements |
|----------|-------------|----------|--------------|
| Academic Excellence | Focus on results | Ambitious families | Top teachers, resources |
| International Curriculum | Global recognition | Expat/mobile families | Accreditation, investment |
| Value Leader | Quality at lower price | Price-sensitive | Efficiency, scale |
| Niche Specialist | Specific segment | Defined market | Deep expertise |
| Technology-Enabled | Digital-first delivery | Scale seekers | Tech investment |
| Outcomes-Focused | Employment/results | Vocational, professional | Industry partnerships |
| Community-Based | Local relationships | Community schools | Engagement, location |

## 5.4 Industry Trends

| Trend | Impact | Timeframe | SME Opportunity |
|-------|--------|-----------|-----------------|
| **Skills-Based Learning** | Move from degrees to skills | 2-5 years | Certification programs |
| **EdTech Adoption** | Blended learning norm | Ongoing | Technology integration |
| **Personalized Learning** | AI-adaptive content | 2-7 years | Differentiated offerings |
| **Micro-Credentials** | Stackable certificates | 2-5 years | Short programs |
| **Corporate Upskilling** | Continuous learning | Ongoing | Corporate partnerships |
| **STEM/Coding Focus** | Technical skills demand | Ongoing | STEM programs |
| **Arabic + English Bilingual** | Market demand | Ongoing | Bilingual offerings |
| **Social-Emotional Learning** | Whole-child education | 2-5 years | SEL integration |
| **Nationalization Training** | Saudization, etc. | Ongoing | Compliance training |

## 5.5 Major Player Landscape

### School Groups (K-12)

| Group | Markets | Schools | Positioning |
|-------|---------|---------|-------------|
| GEMS Education | UAE, Egypt, Saudi | 60+ | Multi-segment |
| Taaleem | UAE | 25+ | Premium |
| Aldar Education | UAE | 30+ | Abu Dhabi focus |
| International Schools Group | Saudi | 10+ | Expatriate |
| SABIS | Regional | 70+ (global) | Proprietary curriculum |
| Cognita | Regional | Growing | Global network |

### Training/EdTech

| Company | Segment | Presence | Model |
|---------|---------|----------|-------|
| British Council | Language | Pan-MENA | International brand |
| Berlitz | Language | Pan-MENA | Franchise + owned |
| New Horizons | IT Training | Pan-MENA | Franchise |
| Coursera | EdTech | Global | B2C + B2B |
| Udemy | EdTech | Global | Marketplace |
| Noon Academy | EdTech | Saudi, Egypt | K-12 tutoring |
| Almentor | EdTech | MENA | Arabic content |

## 5.6 Market-Specific Dynamics

| Country | Market Size | Key Driver | Opportunity |
|---------|-------------|------------|-------------|
| **Saudi Arabia** | $30-40B | Vision 2030, nationalization | Vocational, corporate |
| **UAE** | $8-12B | Expat population, quality | International, premium |
| **Egypt** | $15-25B | Population size, demand | Private schools, EdTech |
| **Morocco** | $8-12B | French + Arabic, TVET | Vocational, languages |
| **Jordan** | $3-5B | Regional hub, skilled workforce | Corporate, professional |

---

# Dimension 6: Digital Maturity

## 6.1 Technology Adoption Benchmarks

| Subsector | Current Adoption | Digital Leaders | Digital Laggards | Key Gap |
|-----------|------------------|-----------------|------------------|---------|
| International Schools | High | 70% | 10% | Integration |
| Private Schools (Local) | Medium | 35% | 40% | LMS, admin |
| Nurseries | Low | 15% | 60% | Parent communication |
| Corporate Training | Medium-High | 50% | 25% | Blended delivery |
| Language Schools | Medium | 40% | 35% | Online options |
| Vocational | Low-Medium | 25% | 50% | Simulation, e-learning |
| EdTech (by definition) | High | 80% | 5% | AI/Personalization |

## 6.2 Digital Maturity Levels

```
┌─────────────────────────────────────────────────────────────────────────────┐
│              EDUCATION DIGITAL MATURITY LEVELS                               │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  LEVEL 1: TRADITIONAL (Score 0-20)                                          │
│  • Paper-based admin, no LMS, basic website only                           │
│  • Typical: Traditional schools, small centers                             │
│                                                                              │
│  LEVEL 2: BASIC DIGITAL (Score 21-40)                                       │
│  • Basic SIS/admin software, email communication, social media             │
│  • Typical: Most private schools, language centers                         │
│                                                                              │
│  LEVEL 3: CONNECTED (Score 41-60)                                           │
│  • LMS for courses, parent portal, online enrollment, basic analytics      │
│  • Typical: Progressive schools, training centers                          │
│                                                                              │
│  LEVEL 4: INTEGRATED (Score 61-80)                                          │
│  • Blended learning, integrated systems, data-driven decisions, automation │
│  • Typical: International schools, leading training providers              │
│                                                                              │
│  LEVEL 5: INTELLIGENT (Score 81-100)                                        │
│  • AI-adaptive learning, predictive analytics, fully personalized          │
│  • Typical: EdTech leaders, innovative schools                             │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 6.3 Core Technology Systems

### School Systems

| System | Priority | Investment Range | Payback | MENA Adoption |
|--------|----------|------------------|---------|---------------|
| SIS (Student Information System) | Critical | $5K-100K | 6-12 mo | 65% |
| LMS (Learning Management System) | High | $3K-50K/year | 6-18 mo | 45% |
| Parent Communication App | High | $2K-20K | 3-6 mo | 40% |
| Assessment Platform | High | $3K-30K | 6-18 mo | 35% |
| Accounting/ERP | Critical | $5K-50K | 12-24 mo | 55% |
| Online Admission | Medium-High | $5K-30K | 6-12 mo | 30% |
| Classroom Technology | Medium | $500-5K/room | 12-24 mo | Variable |
| Security/CCTV | High | $10K-100K | Safety | 70% |

### Training Center Systems

| System | Priority | Investment Range | Payback | MENA Adoption |
|--------|----------|------------------|---------|---------------|
| TMS (Training Management) | Critical | $5K-50K | 6-12 mo | 40% |
| LMS/E-Learning Platform | High | $3K-30K/year | 6-18 mo | 50% |
| CRM | High | $2K-20K | 6-12 mo | 35% |
| Virtual Classroom | High | $1K-10K/year | 3-6 mo | 55% |
| Assessment/Testing | Medium-High | $2K-20K | 6-18 mo | 40% |
| Content Authoring | Medium | $3K-20K | 12-24 mo | 25% |
| Certification Tracking | Medium | $2K-15K | 6-12 mo | 30% |

### EdTech Stack

| Component | Purpose | Example Tools |
|-----------|---------|---------------|
| LMS Core | Content delivery | Moodle, Canvas, Blackboard |
| Video Platform | Live/recorded | Zoom, MS Teams, proprietary |
| Assessment Engine | Testing | Questionmark, custom |
| Content Authoring | Course creation | Articulate, Adobe Captivate |
| Analytics | Learning analytics | Custom, LMS built-in |
| Mobile | App delivery | React Native, Flutter |
| Payments | Monetization | Stripe, local gateways |
| CRM/Marketing | User management | HubSpot, Salesforce |

## 6.4 High-Impact Digital Interventions

| Subsector | Priority 1 | Priority 2 | Priority 3 | Impact |
|-----------|------------|------------|------------|--------|
| Schools | Parent app | LMS integration | Online enrollment | 20-30% efficiency |
| Training | Online booking | Blended delivery | CRM | 25-40% scale |
| Vocational | E-learning modules | Simulation | Digital assessment | 30-50% reach |
| Corporate | Virtual delivery | LMS + tracking | Analytics | 40-60% cost |
| EdTech | Personalization | Mobile-first | AI tutoring | Competitive edge |

## 6.5 E-Learning Platforms

### LMS Options

| Platform | Type | Cost (Annual) | Best For |
|----------|------|---------------|----------|
| Moodle | Open source | $2K-20K (hosting) | Budget, customization |
| Canvas | Commercial | $5-15/student | K-12, higher ed |
| Blackboard | Enterprise | $10-30/student | Universities |
| Google Classroom | Free/Workspace | $0-6/user | Schools, basic |
| Microsoft Teams Education | Free/365 | $0-12/user | Microsoft schools |
| Thinkific | Course platform | $500-5K/year | Course creators |
| Teachable | Course platform | $500-3K/year | Individual instructors |

### Virtual Classroom

| Platform | Cost | Features | Best For |
|----------|------|----------|----------|
| Zoom | $15-25/host/mo | Breakouts, recording | All segments |
| MS Teams | Bundled | Integration | Microsoft schools |
| Google Meet | Bundled | Simple | Google schools |
| Webex | $15-30/host/mo | Enterprise | Corporate |
| BigBlueButton | Open source | LMS integration | Budget |

---

# Dimension 7: Workforce Norms

## 7.1 Organizational Structures

### Small School (200-400 students, 30-50 employees)
```
              Principal/Head
                    │
       ┌────────────┼────────────┐
       │            │            │
   Academic      Admin        Student
    Head         Manager      Support
       │            │            │
   Teachers     Finance      Counselor
   (15-25)      HR/Ops       Social
               Maintenance   Worker
```

### Training Center (20-40 employees)
```
              General Manager
                    │
       ┌────────────┼────────────┐
       │            │            │
   Training     Sales/        Operations
    Manager    Marketing         │
       │            │         Finance
   Trainers    BD/Sales       Admin
   (10-20)    Marketing       Facilities
```

### EdTech Company (20-50 employees)
```
              CEO/Founder
                    │
       ┌────────────┼────────────┬────────────┐
       │            │            │            │
   Product     Engineering   Marketing/    Operations
   (Content)                   Sales           │
       │            │            │          Customer
   Instructional  Developers   Digital      Success
   Designers      QA          Sales       Support
   SMEs                       B2B/B2C     Finance
```

## 7.2 Key Roles

### School Roles

| Role | Responsibilities | Experience | Education |
|------|------------------|------------|-----------|
| Principal/Head | School leadership, P&L | 10-15 years | Master's preferred |
| Academic Head | Curriculum, teacher quality | 8-12 years | Master's + teaching |
| Department Head | Subject leadership | 5-8 years | Bachelor's + teaching |
| Teacher | Instruction, assessment | 2-8 years | Bachelor's + credential |
| Teaching Assistant | Classroom support | 0-3 years | Diploma preferred |
| School Counselor | Student wellbeing | 3-5 years | Psychology/counseling |
| Admissions Manager | Enrollment, marketing | 3-5 years | Bachelor's |
| Operations Manager | Facilities, admin | 5-8 years | Bachelor's |

### Training Center Roles

| Role | Responsibilities | Experience | Certifications |
|------|------------------|------------|----------------|
| Center Manager | P&L, operations | 8-12 years | Industry + management |
| Training Manager | Program delivery | 5-10 years | Train-the-Trainer |
| Lead Trainer | Subject expert delivery | 5-10 years | Subject certification |
| Trainer | Program delivery | 3-8 years | Subject + training |
| Training Coordinator | Logistics, scheduling | 2-5 years | Admin experience |
| Sales Executive | Client acquisition | 2-5 years | Sales experience |
| Content Developer | Material creation | 3-7 years | Instructional design |

### EdTech Roles

| Role | Responsibilities | Experience | Skills |
|------|------------------|------------|--------|
| Product Manager | Product strategy | 3-7 years | Product, education |
| Instructional Designer | Learning design | 3-6 years | ID methodology |
| Content Developer | Course creation | 2-5 years | Subject expertise |
| Learning Engineer | Platform development | 3-7 years | Technical |
| Customer Success | User engagement | 2-5 years | Support, education |
| Growth/Marketing | User acquisition | 3-6 years | Digital marketing |
| Data Analyst | Learning analytics | 2-5 years | Analytics, education |

## 7.3 Compensation Benchmarks (USD/month)

### Egypt

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| School Principal | $1,200-2,000 | $2,000-4,000 | $4,000-8,000 |
| Teacher (Local) | $250-400 | $400-700 | $700-1,200 |
| Teacher (International) | $800-1,500 | $1,500-2,500 | $2,500-4,000 |
| Corporate Trainer | $500-800 | $800-1,500 | $1,500-3,000 |
| EdTech PM | $600-1,000 | $1,000-2,000 | $2,000-4,000 |

### Saudi Arabia

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| School Principal | $5,000-8,000 | $8,000-15,000 | $15,000-25,000 |
| Teacher (National) | $2,000-3,500 | $3,500-5,500 | $5,500-8,000 |
| Teacher (International) | $3,000-5,000 | $5,000-8,000 | $8,000-12,000 |
| Corporate Trainer | $3,000-5,000 | $5,000-9,000 | $9,000-15,000 |
| EdTech PM | $3,500-6,000 | $6,000-10,000 | $10,000-18,000 |

### UAE

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| School Principal | $8,000-12,000 | $12,000-20,000 | $20,000-35,000 |
| Teacher (Local hire) | $2,500-4,000 | $4,000-6,500 | $6,500-10,000 |
| Teacher (Int'l package) | $4,000-6,500 | $6,500-10,000 | $10,000-15,000 |
| Corporate Trainer | $4,000-6,500 | $6,500-11,000 | $11,000-18,000 |
| EdTech PM | $5,000-8,000 | $8,000-14,000 | $14,000-22,000 |

### Jordan

| Role | Entry | Experienced | Senior |
|------|-------|-------------|--------|
| School Principal | $1,500-2,500 | $2,500-4,500 | $4,500-8,000 |
| Teacher | $400-700 | $700-1,200 | $1,200-2,000 |
| Corporate Trainer | $700-1,200 | $1,200-2,200 | $2,200-4,000 |
| EdTech PM | $800-1,500 | $1,500-3,000 | $3,000-5,500 |

## 7.4 Skills Gap Analysis

| Skill Area | Availability | Demand | Gap Severity |
|------------|--------------|--------|--------------|
| STEM Teachers | Low | Very High | **Critical** |
| EdTech/Digital Skills | Low | Very High | **Critical** |
| Special Education | Very Low | High | **Critical** |
| English Language (Quality) | Medium | Very High | **High** |
| Instructional Design | Low | High | **High** |
| Data/Analytics | Low | Growing | **High** |
| Vocational Trainers | Low | High | **High** |
| Leadership/Management | Medium | High | **Medium** |
| Arabic Content Creation | Medium | Growing | **Medium** |

## 7.5 Labor Market Characteristics

| Characteristic | Egypt | Saudi Arabia | UAE | Jordan |
|---------------|-------|--------------|-----|--------|
| Local vs Expat Teachers | 95%+ local | 50/50 | 20/80 | 80/20 |
| Teacher Turnover | 15-25% | 20-35% | 25-40% | 15-25% |
| Female Teachers | 65-75% | 50-60% | 60-70% | 60-70% |
| Teacher Unions | Active | No | No | Limited |
| Pension System | Government | Yes | End of service | Government |
| Housing Allowance | Rare | Common | Common | Sometimes |

## 7.6 HR KPIs

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| Teacher Turnover | >30% | 20-30% | 10-20% | <10% |
| Teacher Satisfaction | <60% | 60-72% | 72-85% | >85% |
| Students/Admin Staff | <50 | 50-80 | 80-120 | >120 |
| Training Hours/Year | <20 | 20-40 | 40-60 | >60 |
| Internal Promotion % | <15% | 15-30% | 30-45% | >45% |
| Qualified Teacher % | <85% | 85-92% | 92-98% | >98% |

---

*End of Part 2 - Continue to Part 3 for Dimensions 8-11*
# Dimension 8: Supply Chain

## 8.1 Input Categories

### School Inputs

| Category | % of Costs | Import Dependency | Key Suppliers |
|----------|-----------|-------------------|---------------|
| Teaching Staff | 35-50% | Low-Medium | Recruitment agencies |
| Curriculum/Textbooks | 3-10% | Medium-High | Publishers, curriculum bodies |
| Technology/Software | 2-5% | High (80%+) | EdTech vendors, hardware |
| Facilities/Utilities | 10-22% | Low | Local providers |
| Learning Materials | 2-5% | Medium | Suppliers, importers |
| Furniture/Equipment | 1-3% | Medium-High | Office/school suppliers |
| Food Services (if applicable) | 3-8% | Low | Catering, local suppliers |

### Training Center Inputs

| Category | % of Revenue | Key Considerations |
|----------|-------------|-------------------|
| Trainers/Instructors | 25-45% | Quality, availability |
| Content/Curriculum | 5-15% | Licensed vs proprietary |
| Technology | 3-10% | LMS, virtual tools |
| Facilities | 10-20% | Location, quality |
| Materials/Consumables | 2-8% | Per-student cost |
| Certification Fees | 2-5% | Pass-through to certifying body |

### EdTech Inputs

| Category | % of Revenue | Key Sources |
|----------|-------------|-------------|
| Content Development | 15-35% | Internal, freelancers, partners |
| Technology/Hosting | 10-25% | Cloud providers (AWS, GCP) |
| Marketing/CAC | 20-40% | Digital, partnerships |
| Personnel | 25-40% | Technical, content, support |

## 8.2 Content & Curriculum Supply

### Curriculum Providers

| Provider Type | Examples | Model |
|---------------|----------|-------|
| International Curriculum | Cambridge, IB, College Board | Licensing fees |
| Textbook Publishers | Pearson, McGraw-Hill, local | Per-student purchase |
| EdTech Content | Coursera, Khan Academy | License/subscription |
| Professional Bodies | PMI, CIPD, CFA Institute | Authorized materials |
| Custom Development | In-house, consultants | Development cost |

### Content Licensing Models

| Model | Cost Structure | Rights |
|-------|---------------|--------|
| Per-Student License | $10-100/student/year | Usage rights |
| Institutional License | $5K-100K/year | Unlimited users |
| Perpetual License | One-time purchase | Permanent, no updates |
| Revenue Share | 20-40% of revenue | Co-branded |
| White Label | License fee + royalty | Full customization |

## 8.3 Supplier Management

### Key Supplier Relationships

| Supplier Type | Payment Terms | Relationship |
|---------------|---------------|--------------|
| Curriculum Bodies | Annual license | Long-term contract |
| Publishers | Per order, 30-60 days | Volume agreements |
| Technology Vendors | Annual subscription | Service agreements |
| Staffing Agencies | Per placement (1-2 months salary) | Ongoing |
| Facilities | Monthly/quarterly | Lease agreements |
| Catering | Monthly | Service contracts |

### Quality Assurance

| Area | Standard | Frequency |
|------|----------|-----------|
| Curriculum Alignment | Framework compliance | Annual review |
| Teacher Qualifications | Credential verification | Per hire |
| Content Accuracy | Expert review | Per update |
| Technology Security | Data protection | Ongoing |
| Facility Standards | Safety, learning environment | Regular inspection |

## 8.4 Procurement Models

### School Procurement

| Category | Model | Considerations |
|----------|-------|----------------|
| Textbooks | Bulk purchase, annual | Publisher terms, currency |
| Technology | Multi-year contracts | Support, upgrades |
| Uniforms | Vendor partnerships | Parent convenience |
| Supplies | Annual tenders | Cost, quality |
| Services | Contracts | Performance-based |

### Training Procurement

| Category | Model | Considerations |
|----------|-------|----------------|
| Content | License or develop | Cost vs customization |
| Trainers | Employ vs contract | Flexibility vs cost |
| Facilities | Own vs rent | Utilization, capital |
| Technology | SaaS vs on-premise | Scale, control |
| Certifications | Partner vs reseller | Margins, requirements |

## 8.5 Outsourcing Considerations

| Function | Outsource Option | Typical Decision |
|----------|------------------|------------------|
| Facility Management | FM companies | Large institutions |
| Security | Security firms | All sizes |
| Transportation | Bus companies | Schools |
| Catering | Catering companies | Medium-large |
| IT Support | MSPs | Small-medium |
| Marketing | Agencies | Variable |
| HR/Payroll | HR service providers | Growing trend |
| Assessment | Testing centers | Professional certification |

---

# Dimension 9: Export Requirements

## 9.1 Education Export Opportunities

### International Student Recruitment

| Opportunity | Requirements | Target Markets |
|-------------|--------------|----------------|
| University Pathway | Accreditation, partnerships | Africa, Asia |
| Language Programs | Quality certification | Regional, global |
| Professional Training | Industry recognition | GCC, Africa |
| Online Programs | E-learning infrastructure | Global |

### Corporate Training Export

| Service | Requirements | Markets |
|---------|--------------|---------|
| Regional Training Hub | Facilities, accreditation | MENA corporates |
| Certified Programs | International authorization | Regional |
| Custom Corporate | Client relationships | MNCs in region |
| Train-the-Trainer | Methodology, IP | Corporate clients |

## 9.2 Cross-Border Considerations

### Regulatory Recognition

| Element | Requirement |
|---------|-------------|
| Degree Recognition | Bilateral agreements, equivalency |
| Professional Certification | International body standards |
| Quality Assurance | Accreditation recognition |
| Visa/Immigration | Student visa support |

### Online Delivery

| Consideration | Requirements |
|---------------|--------------|
| Data Localization | Comply with destination country |
| Payment Processing | Multi-currency, local options |
| Content Localization | Language, cultural adaptation |
| Time Zone | Synchronous vs asynchronous |
| Accreditation | Recognition in target markets |

## 9.3 International Partnerships

| Partnership Type | Structure | Benefits |
|------------------|-----------|----------|
| Franchise | Brand + curriculum license | Market access |
| Joint Venture | Shared ownership | Local knowledge |
| Licensing | Content/program license | Asset-light expansion |
| Articulation | Credit transfer agreements | Student pipeline |
| Consortium | Multi-institution collaboration | Resources, recognition |

## 9.4 International Certifications for Export

| Certification | Purpose | Recognition |
|---------------|---------|-------------|
| AACSB | Business school accreditation | Global |
| ABET | Engineering programs | Global |
| ACBSP | Business programs | Global |
| EQUIS | Business school | European, global |
| QS Rating | University ranking | Global visibility |
| British Council Partner | Language programs | Global |

---

# Dimension 10: Packaging & Labeling

## 10.1 Program Packaging

### School Programs

| Package Type | Components | Target |
|--------------|------------|--------|
| Full Academic Program | Tuition, materials, activities | Standard enrollment |
| Premium Package | Academic + enrichment + meals | Premium segment |
| Scholarship Package | Subsidized tuition | Merit/need-based |
| Sibling Discount | Multi-child pricing | Family retention |
| Early Bird | Advance payment discount | Cash flow |

### Training Programs

| Package Type | Components | Pricing Model |
|--------------|------------|---------------|
| Single Course | Individual program | Per course |
| Certificate Program | Multiple courses + certification | Program fee |
| Subscription | Unlimited access | Monthly/annual |
| Corporate Package | Custom + volume | Per employee/seat |
| Bundle | Multiple related courses | Discounted bundle |

### EdTech Packages

| Package Type | Features | Pricing |
|--------------|----------|---------|
| Freemium | Basic access | Free |
| Individual | Full features, single user | Monthly/annual |
| Family/Group | Multiple users | Per family |
| Institutional | Admin tools, analytics | Per student |
| Enterprise | Full platform, customization | Custom |

## 10.2 Marketing Collateral

### School Marketing

| Material | Purpose | Channels |
|----------|---------|----------|
| Prospectus/Brochure | Overview, programs | Physical, digital |
| Website | Information, application | Online |
| Virtual Tour | Campus experience | Digital |
| Open Day | Direct engagement | In-person |
| Social Media | Awareness, engagement | Facebook, Instagram |
| Alumni Success | Credibility | All channels |

### Training Marketing

| Material | Purpose | Channels |
|----------|---------|----------|
| Course Catalog | Program details | Physical, digital |
| Case Studies | ROI demonstration | B2B sales |
| Success Stories | Social proof | All channels |
| Sample Content | Trial experience | Digital |
| Corporate Proposal | Custom solutions | B2B direct |
| Brochures | Event distribution | Physical |

## 10.3 Certificate Design

### Academic Certificates

| Element | Requirement |
|---------|-------------|
| Institution Name | Official, accredited name |
| Student Name | Verified identity |
| Program/Degree | Official designation |
| Date | Completion date |
| Signatures | Authorized signatories |
| Seal/Logo | Official emblems |
| Registration Number | Verification code |
| Security Features | Anti-fraud (for degrees) |

### Professional Certificates

| Element | Requirement |
|---------|-------------|
| Certifying Body | International/national |
| Designation | Official credential name |
| Validity | Expiry date if applicable |
| CEU/CPD | Continuing education units |
| Digital Verification | Online verification link |
| Digital Badges | LinkedIn, credentials |

## 10.4 Digital Credentials

| Platform | Use Case | Features |
|----------|----------|----------|
| Credly/Acclaim | Digital badges | Verification, sharing |
| LinkedIn Learning | Course certificates | Profile integration |
| Blockchain Credentials | Tamper-proof | Permanent verification |
| Digital Diplomas | Degree verification | Secure, verifiable |

---

# Dimension 11: MENA Regional Context

## 11.1 Country Profiles

### Egypt

| Attribute | Details |
|-----------|---------|
| **Student Population** | ~25 million |
| **Education Spend** | 4-5% of GDP |
| **Key Segments** | Private K-12, language, professional |
| **Challenges** | Quality, infrastructure, affordability |
| **Opportunities** | EdTech scale, vocational, private schools |
| **Regulatory** | Ministry oversight, growing private sector |

### Saudi Arabia

| Attribute | Details |
|-----------|---------|
| **Student Population** | ~8 million |
| **Education Spend** | 5-7% of GDP (highest in region) |
| **Key Segments** | K-12, TVET (nationalization), corporate |
| **Vision 2030 Impact** | Massive reform, privatization |
| **Opportunities** | Vocational (Saudization), EdTech, corporate |
| **Regulatory** | Significant government investment |

### UAE

| Attribute | Details |
|-----------|---------|
| **Student Population** | ~1.5 million |
| **Education Spend** | 4-5% of GDP |
| **Key Segments** | International schools, professional, EdTech |
| **Characteristics** | Most developed private sector |
| **Opportunities** | Premium schools, corporate, EdTech hub |
| **Regulatory** | KHDA/ADEK quality frameworks |

### Jordan

| Attribute | Details |
|-----------|---------|
| **Student Population** | ~2.5 million |
| **Education Spend** | 4-5% of GDP |
| **Key Segments** | Private schools, languages, TVET |
| **Characteristics** | Regional education hub, skilled workforce |
| **Opportunities** | Corporate training, languages, online |
| **Regulatory** | Growing private sector |

### Morocco

| Attribute | Details |
|-----------|---------|
| **Student Population** | ~8 million |
| **Education Spend** | 5-6% of GDP |
| **Key Segments** | French/Arabic, TVET, private schools |
| **Characteristics** | French influence, TVET emphasis |
| **Opportunities** | Vocational, languages, private schools |
| **Regulatory** | OFPPT for vocational |

## 11.2 Vision 2030 Education Impact (Saudi Arabia)

### Key Initiatives

| Initiative | Description | Impact |
|------------|-------------|--------|
| School Privatization | Transfer government schools | Private sector growth |
| TVET Expansion | Vocational training emphasis | Training demand |
| Saudization Training | Nationalization support | Corporate training |
| EdTech Investment | Digital learning push | Technology adoption |
| Quality Framework | Accountability measures | Standards improvement |
| International Schools | Expanding access | Market growth |

### Targets

| Metric | Current | 2030 Target |
|--------|---------|-------------|
| Private School Enrollment | 10-12% | 25%+ |
| TVET Enrollment | 15-20% | 40%+ |
| Digital Learning Adoption | 30-40% | 80%+ |
| International Students (Higher Ed) | Limited | Top 5 destination |

## 11.3 Skills & Training Demand

### National Priorities by Country

| Country | Priority Sectors | Training Demand |
|---------|-----------------|-----------------|
| Saudi | Tourism, entertainment, tech | High (nationalization) |
| UAE | Tech, finance, healthcare | Medium-high (diversification) |
| Egypt | Manufacturing, tech, services | High (employment) |
| Jordan | IT, healthcare, services | Medium (regional hub) |
| Morocco | Automotive, aerospace, services | High (FDI-driven) |

### Skills Gap Training Opportunities

| Skill Area | Demand Driver | Training Opportunity |
|------------|--------------|---------------------|
| Digital/IT | Digital transformation | Bootcamps, certification |
| Data/Analytics | Business need | Professional programs |
| Hospitality | Tourism growth | Vocational programs |
| Healthcare | Sector growth | Technical training |
| Manufacturing | Industry 4.0 | Technical upskilling |
| Languages | Global business | Corporate, individual |
| Soft Skills | Workplace readiness | Corporate training |

## 11.4 Business Culture Considerations

| Aspect | Consideration |
|--------|---------------|
| Academic Calendars | September start (most), varies |
| Religious Observance | Ramadan reduced hours |
| Friday/Saturday Weekend | Gulf countries |
| Gender | Single-gender options available |
| Language of Instruction | Arabic + English/French |
| Family Involvement | High parent engagement expected |
| Status Consciousness | International credentials valued |
| Network Importance | Alumni, family networks |

## 11.5 Regulatory Environment

| Aspect | Characteristics |
|--------|-----------------|
| Government Role | Strong, but privatizing |
| Quality Assurance | Improving frameworks |
| Curriculum Control | National requirements + flexibility |
| Foreign Investment | Increasingly open |
| Online Education | Growing acceptance |
| Professional Recognition | Bilateral agreements |

## 11.6 Strategic Opportunities

| Opportunity | Markets | Potential | Requirements |
|-------------|---------|-----------|--------------|
| TVET/Vocational | All, esp. Saudi | **Very High** | Industry partnerships |
| EdTech/E-Learning | All | **Very High** | Arabic content, technology |
| Corporate Training | All | **High** | Quality, relationships |
| International Schools | UAE, Saudi, Egypt | **High** | Accreditation, capital |
| Language Training | All | **High** | Quality instructors |
| Professional Certification | All | **High** | Authorizations |
| STEM/Coding Education | All | **High** | Curriculum, teachers |
| Special Education | All | **Medium-High** | Specialized expertise |

---

# Document Summary

## Sector Overview

**Education & Training** in MENA represents:

**Market Size & Growth:**
- ~$80-120 billion total market
- 60%+ population under 30 = massive demographic demand
- Government prioritization (5-7% of GDP in Saudi)
- Double-digit EdTech growth (20-35%)

**Key Characteristics:**
- High government involvement transitioning to private
- Skills mismatch driving vocational demand
- Arabic + English bilingual requirements
- EdTech adoption accelerated post-COVID
- Nationalization programs creating training demand
- Quality premium growing

**SME Landscape:**
- Private schools: Capital-intensive but high margins
- Training centers: Lower capital, relationship-driven
- EdTech: High growth, tech-enabled scale
- Nurseries/ECE: Fragmented, franchise opportunities
- Test prep/tutoring: Resilient demand

**Priority Subsectors:**
1. **Vocational/TVET** - Nationalization demand, skills gaps
2. **EdTech Platforms** - 20-35% growth, scale opportunity
3. **Corporate Training** - Upskilling mandate
4. **Early Childhood** - Underserved, growing demand
5. **Language Training** - Consistent demand

## Critical Insights for SME Diagnostics

### Key Success Factors

1. **Quality & Outcomes** - Results matter more than inputs
2. **Accreditation** - Credibility through recognition
3. **Teacher/Trainer Quality** - Most critical input
4. **Digital Enablement** - No longer optional
5. **Industry Partnerships** - For vocational, corporate
6. **Student/Parent Experience** - Service differentiator

### Red Flags to Assess

- High teacher turnover (>30%)
- Low enrollment/occupancy (<75%)
- Missing accreditations
- No digital strategy
- Poor placement rates (vocational)
- Declining NPS/satisfaction

### Upside Indicators

- Waitlists (demand exceeds capacity)
- High retention (>90%)
- Strong outcomes (placement, exam results)
- Digital maturity
- Industry partnerships
- Quality faculty retention

## Agent Usage Guide

| Agent | Primary Dimensions | Key Data Points |
|-------|-------------------|-----------------|
| **The Drucker** | 1, 11 | Subsector classification, regional context |
| **The Marvin** | 3, 4 | Enrollment KPIs, accreditation compliance |
| **The Graham** | 2 | Revenue/student, margins, valuation |
| **The Ricardo** | 9, 10 | Export potential, program packaging |
| **The Lovelace** | 6 | EdTech adoption, LMS, digital maturity |
| **The Mayo** | 7 | Teacher compensation, skills gaps |
| **The Ohno** | 8 | Curriculum supply, procurement |
| **The Porter** | 5 | Competition, school groups, EdTech trends |
| **The Landor** | 10 | Program packaging, certificate design |

## Cross-Sector Integration

Education & Training connects to virtually every other sector through workforce development:

| Connected Sector | Integration Point |
|------------------|-------------------|
| Hospitality | Hospitality training academies |
| Healthcare | Nursing schools, medical training |
| Technology | IT bootcamps, coding education |
| Manufacturing | Technical/vocational programs |
| Retail | Customer service training |
| Financial Services | Professional certifications (CFA, CPA) |
| Construction | Trade skills, safety training |
| Logistics | Technical/operational training |

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | December 2025 | RootRise Product Team | Initial release |

---

*This document is part of the RootRise Sector Knowledge Pack series, providing comprehensive sector intelligence for The Pantheon multi-agent diagnostic system.*
