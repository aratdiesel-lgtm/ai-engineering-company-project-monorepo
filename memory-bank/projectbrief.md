# HealthCore Project Brief

## Company

HealthCore is an ambulatory healthcare network founded in Austin, Texas. It operates 12 clinics: nine in the United States (Texas, Florida, and Georgia) and three in the United Kingdom (London and Manchester). The company has approximately 200 employees and annual revenue of about $28 million. It is led by Dr. Sandra Okonkwo, a physician and CEO.

HealthCore serves primary care, specialist consultations, chronic disease management, and preventive health programs. Its promise of accessible care includes same-day appointments, extended hours, and bilingual staff in US markets. Its clinics have grown faster than the systems supporting them.

## HealthCore Digital

Dr. Okonkwo created HealthCore Digital to build the systems, workflows, and intelligent tools needed for secure, efficient, patient-centered operations. The work must account for two countries, distinct regulatory regimes, and clinical systems that were acquired or built independently.

## Department needs and current constraints

- **Clinical Operations — Dr. Marcus Reid:** Leads about 120 clinicians across 12 sites. US and UK clinics use different, disconnected EHR platforms and local processes. Clinicians spend about 35 minutes per day on documentation; patient records do not follow patients reliably between sites. Needs include a unified EHR-facing API, clinical documentation assistance, cross-site visibility, and operational metrics by clinic.
- **Patient Experience and Access — Priya Nair:** Leads this function from London. There is no shared online booking system; patients book by phone or reception. Network no-shows are about 22%, representing approximately $1.8 million in lost appointment capacity annually. Proactive reminders, risk-based outreach, rescheduling, and access metrics are needed.
- **Revenue Cycle and Billing — Tom Callahan:** US claim denials are about 14%, above the cited industry range of 5-8%, with manual submissions and inconsistent coding. UK private-pay billing and a small NHS contract are managed separately. The organization lacks a unified view of collections and denials.
- **Compliance and Data Governance — Claire Whitfield:** HealthCore must meet HIPAA obligations in the US and UK GDPR obligations in the UK. EHR access records are separate and audit trails are incomplete; responding to patient data requests requires manual work across systems. Systems and data flows require jurisdiction-aware review, access controls, and traceability.
- **People and Workforce — Diane Foster:** Supports about 200 staff across 12 sites and two employment-law environments. Clinical roles take an average of 47 days to fill; onboarding is manual and continuing medical education (CME) hours are tracked in spreadsheets. Credential checks, onboarding, training, and workforce metrics are current needs.
- **Technology — James Osei:** Leads a six-person team in Austin. The estate includes two EHR platforms, a US billing platform, a UK billing spreadsheet, phone-based US appointment scheduling, and manual UK calendars. There is no shared data layer, centralized telemetry, or centralized logging. Integration and monitoring must fit this constrained team and existing systems.
- **Executive Leadership — Dr. Sandra Okonkwo:** Receives delayed, inconsistent weekly reports and cannot readily see network-wide metrics such as no-shows, claim denials, revenue, or patient satisfaction. Executive reporting needs consistent definitions and timely, traceable data.

## Current milestone scope

This milestone establishes governance and AI-ready project context: a reliable HealthCore briefing, repository-specific agent instructions, and a memory bank that keeps future work aligned with the company and monorepo. It does **not** create product applications, APIs, agents, workflows, datasets, or infrastructure. Product implementation requires a separately approved milestone and must follow the relevant folder guidance.

## Working principles

- Treat `BRIEFING.md` as the primary source for HealthCore facts; do not replace them with generic company or healthcare placeholders.
- Preserve patient privacy and regulatory obligations in all design and implementation decisions.
- Keep claims and metrics tied to the briefing; identify assumptions rather than presenting them as facts.
- Keep this milestone focused on context and governance, not product code.
