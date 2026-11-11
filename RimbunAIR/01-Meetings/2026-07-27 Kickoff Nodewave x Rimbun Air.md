---
tanggal: 2026-07-27
tipe: meeting
tags: [kickoff, scope, timeline]
---

# Kickoff — MRO ERP Development (Nodewave × Rimbun Air)

**Audiens:** 🟡 Tim Nodewave — Transkrip deck kickoff. Untuk tim Nodewave.

Peserta: tim Nodewave (lihat daftar Project Team di bawah) + tim Rimbun Air — **nama peserta Rimbun Air belum tercatat**

> **Isi note ini:** transkrip deck kickoff Nodewave — rujukan apa yang dijanjikan ke klien.
> Untuk scope yang saya kerjakan, buka [[Scope]].

## Konteks

Kick-off resmi project MRO/ERP. Isi note ini adalah **transkrip deck presentasi Nodewave**, bukan minutes of meeting — tidak ada catatan diskusi, respons klien, atau kesepakatan lisan. Kalau ada hal yang dibahas di luar deck, belum terekam di mana pun.

## Yang ditetapkan deck ini

- **Scope:** 10 modul MRO (kargo tidak termasuk), dibangun custom oleh Nodewave
- **Timeline:** 12 bulan sampai go-live + 6 bulan warranty & data migration
- **Metode:** agile per sub-modul, sign-off tertulis sebelum coding tiap sub-fitur
- **Tech stack:** Node.js/Go/Laravel · React/Next.js · Flutter · PostgreSQL · Docker/AWS
- **Kontrol:** daily sync, progress report 2-mingguan, live Excel tracker

## Konsekuensi yang perlu ditindaklanjuti

Deck ini bertabrakan dengan riset di `03-Knowledge/` pada 5 titik — lihat [[Rekonsiliasi Scope - Riset vs Kontrak]]. Paling mendesak: **migrasi data dijadwalkan bulan 12–18, yaitu setelah go-live** (K4).

Deck meminta 6 butir data dari Rimbun Air; daftar lengkap yang sebenarnya dibutuhkan ada di [[Checklist Data dari Rimbun Air]].

## Action items

*Daftar gabungan semua action item yang masih terbuka ada di [[Overview]]. Di sini disimpan versi aslinya beserta konteksnya.*

- [ ] Konfirmasi PIC tunggal Rimbun Air — PIC: Rigen — Due: minggu 1
- [ ] Kumpulkan process owner per modul — PIC: Rigen — Due: minggu 1
- [ ] Eskalasi urutan migrasi data (K4) — PIC: Eza — Due: sebelum work plan minggu 2
- [ ] Klarifikasi status offline-first & scope kargo (K1, K2) — PIC: Eza — Due: sebelum work plan minggu 2

---

# Transkrip Deck

## About Us

*Build Smarter · Scale Faster · AI Powered for Unstoppable Growth*

We deliver **ROI-driven digital transformation** for you!

| Metric | Description |
|---|---|
| **>5 Years** | of experience and continuous growth |
| **70+ Crew** | in a high-performance team |
| **50+ Clients** | across multiple industries |
| **5 Countries** | served — Japan, Singapore, Bangladesh, Malaysia |

**Partner Network:** Google Cloud Partner, AWS Partner Network, Microsoft Partner, GitHub

**Certification:** ISO 9001, ISO 27001, ISO 27701

### Our Digital Solution Ecosystem

- **Software & ERP Development** — Custom-built website or apps tailored to your business model, workflows, and growth strategy.
- **Big Data & AI Solutions** — Helps organizations collect, structure, analyze, and activate their data to be a Big Data Platform and AI Assistant.
- **Cybersecurity Consulting** — Enterprise security services including risk assessment, penetration testing, vulnerability scanning, and strategy & readiness planning.
- **IT Infrastructure, Network, & System Integrator** — End-to-end system integration covering infrastructure, cloud (SaaS), data centers, networks, and cybersecurity.
- **Supply Chain, RFID, & IoT Solutions** — Advanced RFID systems, WMS solutions, and custom Internet of Things development including computer vision, automation, and smart detection technologies.

### Our Highlighted Clients

HK Inovasi Untuk Solusi, Adhi, Danareksa, Pelindo, RSUD dr. Doris Sylvanus, Urban Move, HKI Infrastruktur, Lionel Express, Waskita Precast, PT. Santani Agro Mandiri, Indo Arsip, Duta Abadi Primantara, Voca Game, Denso, TJS Property, PT. Sentra Karya Mandiri, Hypernet (an XLSMART company), Perpustakaan Nasional Republik Indonesia, and many more.

**Overseas Clients:** Yasuda, Soleil, I'm Taxi

---

## Product Background and Information

### Understanding Your Requirements

Rimbun Air operates a fleet of aircraft for cargo and charter services. Today that runs on separate tools and manual coordination. Here is what we heard:

1. **Fragmented Systems** — Aircraft, maintenance, materials, and procurement are spread across spreadsheets and disconnected tools, with no single source of truth.
2. **Unmet Business Needs** — The current internal system does not yet meet all of the operation's business requirements.
3. **Digitalization & Documentation** — Business processes need to be digitalized end to end, with stronger and more reliable documentation.
4. **Manual Approvals** — Approvals are coordinated manually over chat and email, with no enforced authority limits and no audit trail.

### Why You Need This System

This is more than software. It is the control system for safe, compliant, and cost-efficient operations.

**Operational Benefit**
- Airworthiness assured with hard-time tracking, no missed deadlines
- Higher fleet availability for forecasted tasks
- Full governance with multi-layer approvals and an immutable audit trail

**Business & Financial Benefit**
- Lower cost of compliance by avoiding groundings, penalties and [[Glosarium#A|AOG]] losses
- One platform for engineering, materials, procurement and cost
- Faster, better decisions from a single source of truth

### Our Proposed Service: A Unified MRO Platform

**One system tailored for Rimbun Air**

**What Nodewave Will Deliver:**
- Built custom to Rimbun Air's fleet, bases, and standard operating procedures
- Comprehensive operational modules plus governance, fully integrated
- A web application with mobile access for work in the field
- A dynamic, no-code approval engine across every module
- An immutable audit trail for every record and decision

### Ten Operational Modules

Every continuing airworthiness and maintenance function, fully integrated.

| # | Module | Description |
|---|---|---|
| 01 | **Engineering & Configuration** | Aircraft master, as-built config, and component life limits |
| 02 | **Program & Planning** | Maintenance programs, forecasting, and work-package release |
| 03 | **Production & Execution** | Work orders and task-card execution on the floor |
| 04 | **Flight Ops Interface** | Flight hours and cycles that drive maintenance |
| 05 | **Material & Logistics** | Inventory, stock levels, reordering, and write-offs |
| 06 | **Procurement & Contract** | Vendors, RFQ, and purchase/repair/exchange orders |
| 07 | **Publication** | Technical publications with revision control |
| 08 | **Costing** | Cost capture per work order and per order |
| 09 | **Workshop (MRO)** | Component and in-house shop maintenance |
| 10 | **GSE** | Ground support equipment tracking and maintenance |

### Key System Highlights

Three capabilities that set the Governance Module apart.

**Dynamic Multi-Layer Approval**
- Adapts to requester, document type and value
- Configured in Settings, never hard-coded
- Every transaction routed and logged

**Sign-Ready Reports**
- One-click export to print-ready PDF
- Letterhead, reference numbers and signature blocks built in
- Locked and tamper-evident once approved

**Effortless User Experience**
- Modern dashboard with real-time KPIs
- Critical alerts surface first (AOG, [[Glosarium#L|LLP]] overdue)
- Search, filter and drill-down everywhere

### Capability Highlight: Dynamic Multi-Layer Approval

Approval adapts to who is requesting, which document it is, and how much it is worth.

**Flow:** Requester (Procurement · Staff) → Layer 1 · Chief (if ≥ IDR 50 Jt) → Layer 2 · Manager (if ≥ IDR 250 Jt) → Issued (approved & locked)

| Document Type | Layer 1 | Layer 2 | Trigger |
|---|---|---|---|
| Purchase Order | Chief | Manager | By value |
| Repair Order | Chief | Manager | By value |
| Material Write-off | Manager | Director | Always |
| Engineering Order (EO) | Manager | Director | Always |

### Capability Highlight: Sign-Ready Documents Generator

Every official document is ready to print and sign, straight from the system.

- One-click export to a print-ready PDF
- Letterhead, reference numbers, and signature blocks built in
- Locked once approved, and tamper-evident
- Covers Work Orders, [[Glosarium#C|CRS]], store issues, and PO/RO
- Saved automatically and audit-ready

### Capability Highlight: Effortless User Experience

Designed so field and office teams can use it right away.

- A modern dashboard with real-time KPIs
- Critical alerts surface first (AOG, LLP overdue)
- Search, filter, and drill-down everywhere
- Minimal training, built around real workflows

*Sample dashboard metrics: 4/6 Airworthy · 11 Due ≤30h · 5 Open WO · AOG critical: PK-RAG · LLP overdue*

### Prototype Preview: Operations Command Center

Fleet airworthiness, work orders, compliance, and pending approvals on one screen, across every base.

- **Your fleet at a glance** — Airworthiness, due tasks, and open work orders, live across every base.
- **Risk shown first** — AOG and LLP-overdue alerts are pushed to the top of the screen.
- **Approve in place** — Pending multi-layer approvals are actioned straight from the dashboard.

### Prototype Preview: Sample Screens

**Engineering & Configuration** — Full configuration and component-life control, with an immutable audit trail.

**Procurement & Contract** — Vendors, RFQ, and every order type, complete with multi-layer approval.

**Flight Operations** — Daily FH/FC utilization and defects captured automatically.

**Costing** — Labour and parts cost per aircraft, tracked year-to-date.

**Approval System**
- *Approval Pending* — A clear list of pending approvals, with each step and information.
- *Approval Governance* — Dynamic approval policies with no coding, reused across every module.

### Our Technology Stack

Modern, proven, and deploy-anywhere: the same engineering stack behind Nodewave's enterprise ERP platforms.

| Layer | Technologies |
|---|---|
| **Backend** | Node.js, Go, Laravel |
| **Web / Frontend** | React, Next.js, Desktop POS |
| **Mobile** | Flutter, Swift |
| **Database** | PostgreSQL, MongoDB, MySQL, Redis, Qdrant |
| **API & Messaging** | GraphQL, RabbitMQ |
| **Deployment** | Docker, AWS, Ubuntu |

*Flexible deploy on private cloud (VPC)*

---

## Project Information

### Scope of Work

What the project covers, and what sits outside it.

| Included in Scope | Not Included |
|---|---|
| Development of the 10 MRO modules | Go-live infrastructure, provided by the client (we assist with the setup) |
| Development environment hosted on Nodewave infrastructure | Development of modules outside the agreed scope |
| Data migration from the existing system database | Migration from Excel, Word, or paper records |
| Training at the Rimbun Air office or online | Training delivered through additional site visits |

*Full detail, deliverables, and commercial terms are defined in the contract.*

### Scope of Work & Timeline

A structured 12-month delivery to go-live, followed by 6 months of warranty and data migration phase.

| Phase | Duration | Activities |
|---|---|---|
| **Requirement Gathering** (Month 0–3) | 3 months | Process and data discovery; BPMN mapping; Solution blueprint and PRD sign-off |
| **Development** (Month 3–9) | 6 months | Build 10 modules; Iterative sprints and demos; Integrations and reports |
| **UAT, Training & Go-Live** (Month 9–12) | 3 months | UAT and defect fixing; Role-based user training; Cutover and go-live |
| **Warranty & Data Migration** (Month 12–18) | 6 months | Data migration from previous system; Warranty support and fixes; Hypercare and optimization |

**Go-Live: Month 12**

*Warranty covers bug fixes and non-functional adjustments only. New features or changes to the core/main flow are not included.*

### Requirement Gathering: Objectives & Expectations

We gather from your team, document it, and confirm it with you before any build starts.

**We Gather:**
- Interviews with your PIC
- SOPs, forms, documentation
- Existing tools and Excel data

**We Document & Confirm:** Requirement Gathering — Understand the flow, write it down, and validate it with your team.

**You Receive:**
- **BPMN** — End-to-end maps of how the business runs
- **PRD** — What the system must do, per module
- **Work plan & timeline** — Detailed delivery schedule you can track

**What we need from the Rimbun Air team:**
- **People available** — Process owners and managers in the interview slots
- **Documents and data** — SOPs, forms, approval limits, and sample Excel data
- **Timely confirmation** — BPMN and PRD reviewed within the agreed window

### Requirement Gathering Information

Months 0 to 3: map the overall flow first, then detail every flow and feature.

**01 Phasing**
- **Weeks 1–2 (Big picture):** Overall business flow mapped into BPMN, plus the detailed work plan
- **Week 3 – Month 3 (Deep dive):** Detailed requirements captured per flow and per feature

**02 How We Gather**
- Interviews with the PIC — Process owner of each flow
- SOP documentation — How the work is written today
- Policy and management — Rules and authority limits
- Current tools and Excel — How the work runs today

**03 Deliverables**
- Week 2 — **BPMN**: End-to-end process maps of the agreed flows
- Week 2 — **Development Work Plan**: Detailed build timeline and milestones
- Month 3 — **PRD**: Documented requirements per module

### Development Way: Agile Methodology

We build the system sub-module by sub-module. Each one runs through the same six-phase cycle and is signed off before the next begins.

1. **Requirement Discovery** — Interviews and discussions with your users
2. **Module PRD** — Scope, business rules, and acceptance criteria
3. **Design & Prototyping** — Clickable UI/UX prototype of that sub-module
4. **Prototype Sign-Off** — You approve before any code is written
5. **Development** — Built strictly to the signed-off scope
6. **Testing** — Internal QA, then your UAT per sub-module

**Iterative by sub-module:** Cycle repeats for every sub-module and feature. Nothing is built before the prototype is signed off, so each module is confirmed against your expectations as we go, instead of one big hand-over at the end of the project.

*(Agile vs. Waterfall comparison diagram included in original slides)*

### Module Confirmation and Sign-off Procedure

Every sub-feature is confirmed in writing before a single line of code is built.

1. **Single-feature PRD** — Requirements, business rules, and acceptance criteria
2. **Clickable Prototype** — A click-through of the real screens and flow
3. **Sign-Off Document** — Signed by user before build

**What happens after the sign-off:**

- **Signed on time:**
  - Development on that sub-feature starts immediately
  - The signed PRD and prototype become the test baseline
- **Sign-off on hold:**
  - The next sub-features wait in the queue
  - The overall development timeline shifts accordingly

### Sign-Off Document: Sample

One page per sub-feature: it declares that the PRD and the prototype are accepted.

**Sample Feature Sign-Off Form**
- Module: Procurement & Contract
- Sub-feature: Purchase Order approval
- PRD version: v1.2 – 14 Aug 2026
- Prototype: Reviewed 18 Aug 2026
- Declaration: "We confirm that the PRD and the clickable prototype above have been reviewed and are accepted for development."
- Signed by: Rimbun Air – PIC and Nodewave – PM

**Form structure:**
1. **Reference header** — Module, sub-feature, PRD version, and the prototype reviewed
2. **Acceptance declaration** — Confirms the PRD and prototype are accepted
3. **Two signatures** — Signed by the Rimbun Air PIC and the Nodewave PM, with the date
4. **What it unlocks** — Development starts, and the signed scope becomes the test baseline

*Any change or feature/flow addition requested after sign-off is handled as a change request and billed separately.*

### Project Control and Monitoring

Three reporting routines, plus written minutes for every meeting.

| Routine | Frequency | Description |
|---|---|---|
| **Live Work Plan** | After week 2 | Detailed plan and timeline, shared live with your team |
| **Daily Sync with PM** | Daily | Short daily call between our PM in charge and your team |
| **Progress Report** | Every 2 weeks | Written progress report plus a review session together |

**Minutes of Meeting (MoM) for every session:**
1. **Participant List** — Who attended and who they represent
2. **Discussion Points** — What was reviewed and clarified
3. **Action Items** — Task, owner, and target date
4. **Decision Log** — Every decision, with its date

### Project Coordination & Shared Material

Three shared channels, so information sits in one place and stays current.

1. **WhatsApp Group** — Day-to-day coordination between both teams. Quick questions and updates; escalation for urgent items.
2. **Live Excel Project Tracker** — Work plan and progress, viewable at any time. Tasks, owners, target dates; maintained by our PM.
3. **Shared Project Folder** — One place for every project document. BPMN, PRD, prototypes, MoM; signed sign-off documents.

### Project Team

| Role | Name |
|---|---|
| Project Director | Hardi |
| Business Support | Akil |
| Project Manager | Rigen |
| Product Manager | Eza & Wisnu |
| BPMN Consultant | Gama |
| Technical Lead | Rafi |
| UI/UX | Annisa, Shafa |
| Software Engineer | Andre, Wathan, Rama, Mikael, Dhito, Dony |
| Data Engineer | Pradipta |

### Need Information

What we need from the Rimbun Air team so the first weeks run on schedule.

| # | What We Need from Rimbun Air | Why We Need It | When |
|---|---|---|---|
| 1 | Project PIC / Project Manager | Single point of contact for decisions, coordination, and sign-off | At kick-off |
| 2 | Process owners per module | Engineering, planning, materials, procurement, and costing | Week 1 |
| 3 | Access to the current system | To see what exists today and what carries over | Week 1 |
| 4 | Sample data in Excel | Real formats and volumes for master and transaction data | Week 1 |
| 5 | SOP documentation | Written rules, forms, and approval limits | Week 1 |
| 6 | Confirmed meeting schedule | Daily sync slot and the two-weekly progress report slot | At kick-off |

---

## Elevate Together with Nodewave!

**Nodewave**

📍 APL Tower Central Park Lt. 19, Jl. Letjen S. Parman Kav. 28, Petamburan, Jakarta Barat – Indonesia

🌐 nodewave.id

📱 +62 811 258 280

*Partners: Google Cloud Partner, AWS Partner Network, Microsoft Partner, ISO 9001, ISO 27701*

---

> "The most important single aspect of software development is to be clear about what you are trying to build."
> — Bjarne Stroustrup
