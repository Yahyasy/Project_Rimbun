---
tipe: konteks
modul: umum
diperbarui: 2026-11-11
sumber:
  - Rimbun Air Requirements.xlsx
  - Deskripsi Project Claude
tags: [mro]
aliases: [Project MRO Rimbun Air, Ringkasan]
---
# Ringkasan Proyek

| Aspek | Isi |
|---|---|
| Klien | PT. Rimbun Abadi Aviasi (**Rimbun Air**), operator kargo dan penumpang dengan armada B737, ATR 72, dan DHC-6 ([[Armada & Tipe Pesawat]]) |
| Vendor | Nodewave |
| Sistem | Sistem MRO (Maintenance, Repair, Overhaul) terdiri dari 10 modul bisnis + System Setting & Governance + Managerial Reports ([[Peta Modul & PM]]) |
| Fase proyek | Clear konteks → requirement gathering (deep dive, activity diagram, user flow, ERD, class diagram, menu dan detail menu, wireframe, prototype) → development → QA → go live → maintenance |
| Fase sekarang (11 Nov 2026) | Requirement gathering tahap akhir: desain hi-fi direvisi per gelombang dan direview klien; target sesi gathering ditutup lalu sisa butir diselesaikan lewat konfirmasi tertulis |
| Lingkup Yahya | Service 2 *Maintenance and Flight* (diserahterimakan dari PM Eja): [[M2 Overview|Modul 2]], [[M3 Overview|Modul 3]], [[M4 Overview|Modul 4]]; ditambah [[SSG Overview|System Setting & Governance (RBAC)]] untuk seluruh aktor |
| Narasumber klien | Pak Andi dan Mas Bobi ([[Stakeholder & Kontak]]) |

## Linimasa

| Tanggal | Peristiwa | Modul |
|---|---|---|
| Agu 2026 | Handover service Maintenance & Flight dari PM Eja; context clearing dari activity diagram legacy "PPC – Maintenance – Inspector" dan CMM | M2, M3, M4 |
| 14 Sep | Review sitemap menu, sitemap screen, dan ERD Modul 2 bersama Bobi dan Pak Andi | M2 |
| 24 Sep | Interview awal Flight Operations Interfacing (Pak Andi, direkam); RFQ, Integrasi, Role & NFR dijawab tertulis | M4 |
| 30 Sep | Design Brief M2 v2.0, Daftar Konfirmasi M2 (K) | M2 |
| 7 Okt | Design Brief M3 v1.0 | M3 |
| 8–9 Okt | Keputusan lintas modul: M4 penulis tunggal transaksi komponen dan pemegang DMI; RQ di M4, RFQ di Procurement | M2, M3, M4 |
| 13 Okt | Review desain klien Modul 2 (R01–R57) | M2 |
| 16 Okt | PRD System Setting & Governance (RBAC) | SSG |
| 19 Okt | Review klien Modul 3: Modul 3 menjadi 1 sub-modul; CRS ke Workshop, OTA ke Modul 1 | M3 |
| 22–28 Okt | Review prototype Modul 4 per sub-modul (AFML, Defect & Deferred, CML, Component Transaction, Reliability) | M4 (+ M2, M3) |
| 29–30 Okt | Design Brief M2 v3.0; Knowledge Base M2 dan M3 | M2, M3 |
| 1 Nov | Review hi-fi Modul 3 (142 komentar); Design Brief M3 v2.0 | M3 |
| 2–3 Nov | Review RQ & Procurement; Flow Detail Modul 4; review desain Modul 4 (268 frame) | M4 |
| 4–6 Nov | Keputusan AFML, Fluid, konfirmasi Modul 4 dan DMI; Design Brief M4 v2 | M4 |
| 5 Nov | Konfirmasi RBAC (toggle, riwayat toggle, penugasan di luar base); PoC 69/69 | SSG |
| 8 Nov | Review desain Modul 2 setelah revisi; konfirmasi PM (ATA 4 digit, tipe pesawat di M2) | M2 |
| 9 Nov | Decision Log Modul 2; sesi review desain hasil revisi dengan klien | M2 |

## Artefak per modul

| Artefak | M2 | M3 | M4 | SSG |
|---|---|---|---|---|
| ERD | ERD v7 (Lucid) + sheet field | ERD (Lucid) | ERD per sub-modul | 26 entitas (workbook, `schema.sql`) |
| Sitemap menu / screen | v2 (berdasar ERD v7, belum resmi) | Lucid | Lucid (Sitemap Screen v1, 12 Okt) | 15 menu (PRD) |
| User flow / user story | Flow A Perencanaan, Flow B Eksekusi; user story | User flow Lucid; user story | User story; Flow Detail 3 Nov | Alur onboarding & tanda tangan (PRD) |
| Design Brief | v3.0 (29 Okt) | v2.0 (1 Nov, upd 5 Nov) | v2 (Nov) | — (wireframe menyusul) |
| Hi-fi dan review | Figma; review 29 Okt dan 8 Nov | Hi-fi; review 1 Nov | Rimbun_Air_9/10 + Claude Design; review 3 Nov | — |
| Keputusan | [[M2 Decision Register]] | [[M3 Decision Register]] | [[M4 Decision Register]] | [[SSG Workflow SoD Aturan & NFR]] |

Tautan semua artefak ada di [[Workspace Lucid Figma Drive]] dan [[Register Dokumen Sumber]].
