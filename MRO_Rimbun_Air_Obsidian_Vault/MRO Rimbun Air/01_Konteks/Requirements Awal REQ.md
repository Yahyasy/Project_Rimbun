---
tipe: konteks
modul: umum
diperbarui: 2026-11-11
sumber:
  - Rimbun Air Requirements.xlsx (REQ DETAILS, ORG STRUCTURE, Copy of user, Copy of jabatan)
tags: [mro, m2, m3, m4]
aliases: [REQ, Rimbun Air Requirements, Traceability REQ]
---
# Requirements Awal (REQ) dan Ketertelusurannya

Sheet **REQ DETAILS** di `Rimbun Air Requirements.xlsx` adalah daftar kebutuhan awal klien per modul, dikelompokkan menjadi *Booking engine* (entri/master), *Form*, *Tools*, dan *Report*. Tabel di bawah menelusuri setiap butir untuk tiga modul Yahya ke tempatnya di sistem sekarang. Butir yang tidak ditemukan tempatnya berarti celah.

## Modul 2 — Maintenance Program & Planning

| Kelompok | Butir REQ | Sekarang ada di | Status |
|---|---|---|---|
| Booking | Task card number | Nomor task card di Task Library ([[M2 SM1 Maintenance Program#Task Library dan Form Task]]) | Final |
| Booking | Task card material required | Task Part (100% / OC) dan Material & Tool di Task Library; part 100% otomatis ke Material Required WO | Final (M2 no 38, 43) |
| Booking | Technical Document number: AD (Authority), SB/SL (Manufacture), EO (internal) | Dikelola di **Modul 1**; task asal EO tampil read-only di Task Library | Pindah (M2 no 1–2) |
| Booking | Check-pack Master | [[M2 SM3 Check Pack & Out of Phase]] | Final |
| Form | Task card | Master di Task Library; eksekusi di WO Modul 3 | Final (M2 no 4) |
| Tools | Forecast Task | Forecast Dashboard, grup MP Task | Final |
| Tools | Forecast ADSB | Grup AD/SB & EO di forecast (data dari M1) | Final |
| Tools | Forecast Deferred (berhubungan dengan MEL) | Grup DMI read-only dari Modul 4, batas due date | Final (M2 no 53–54) |
| Tools | Forecast Check-pack | WCF Priority → Create Check Pack from Selection | Final |
| Tools | Forecast HT | Menu Hard Time + grup HT di forecast | Final (M2 no 46) |
| Report | LDND report | Report Center – LDND | Desain sebagian |
| Report | ADSB report | Report Center – SB/AD | Desain sebagian |
| Report | HT report | Report Center – HT (pindah dari M1) | Final |
| Report | Check-pack report | Report Center – Check-pack | Final |

## Modul 3 — Production & Execution

| Kelompok | Butir REQ | Sekarang ada di | Status |
|---|---|---|---|
| Booking | Work Order Master (penomoran otomatis) | Form WO + Work Order Number Setup / master format nomor | Lokasi master menunggu C17 |
| Booking | Non routine card (penomoran otomatis) | NRC (nomor induk + "-NRC-01") dan Ad-hoc Task Card (nomor WO + "-AH-01") | Final (konsep), Usulan (format) |
| Booking | Task card material required additional | Material Required per task card, boleh ditambah/dikurangi | Final (B-58) |
| Form | Work Order | Form WO, Detail WO ([[M3 Work Order]]) | Final |
| Form | Control Sheet / Control Job card / Control Task card | Cetak Control Sheet dengan kolom Engineer dan RII | Final (B-46) |
| Form | Return to Service | Cetak RTS satu lembar per WO (CRS dipindah ke Workshop) | Final (B-49, B-02) |
| Form | Closing & cancel Task card | Popup Close / Cancel task card ([[M3 Task Card di WO]]) | Final |
| Tools | WO In progress Monitoring | Work Order List, status Work in Progress otomatis | Final |
| Tools | WO Sign in & Sign Out | Sign-in nama engineer per task card tanpa jam; jam kerja tetap di kertas | Final (B-19, B-21) |
| Tools | Closing & cancel WO | Close WO / Cancel WO | Final |
| Report | Work Order Report | Report WO, Report Material Required, Report Material Issued | Final (B-09) |

## Modul 4 — Flight Operations Interfacing

| Kelompok | Butir REQ | Sekarang ada di | Status |
|---|---|---|---|
| Booking | Flight log entry | 1.1 Flight Log (AFML) | Final |
| Booking | Defect entry | 2.1 Defect (dari baris discrepancy AFML) | Final |
| Booking | Deferred entry | 2.2 DMI | Final |
| Booking | Oil & hydraulic consumption entry | Tab Oil & Fuel di AFML; menu 4.2 dan 4.3 hanya daftar | Final (FL-02) |
| Booking | Fuel consumption entry | Tab Oil & Fuel di AFML; menu 4.1 Fuel Uplift | Final (FL-01, FL-05) |
| Booking | Install & remove component transaction — *"ketika part sudah diinstall di pesawat maka operation life berjalan"* | 3.1 Removal/Installation, 3.2 Robbed, 3.6 Swap; jam komponen bertambah saat closing AFML | Final (CT-01); alokasi jam Usulan (FQ-02) |
| Form | Flight log form | Halaman AFML per tipe pesawat (Master Field 86 field) | Final |
| Form | DMI form | DMI Log RAA-TLM-007, rekap RAA-TLM-006 | Final (K6) |
| Tools | Component install & remove | 3.1 / 3.2 / 3.6 | Final |
| Tools | Reliability (ATA & component) | 5.1 tab Component | Final (rumus), Menunggu (RL-01–RL-09) |
| Tools | Repetitive (ATA & component) | 5.1 tab Repetitive | Final (aturan dasar) |
| Report | Flight hour report | 1.4 Flight Hour Report | Final |
| Report | Oil & hydraulic consumption report | 4.2 Oil Consumption, 4.3 Hydraulic Fluid Consumption | Final (FL-01) |
| Report | Fuel consumption report | 4.1 Fuel Uplift | Final (FL-05) |
| Report | Defect/Deferred Report | 2.7 Defect & Deferred Report | Final |
| Report | Component installed report | 3.3 Component Installed Report | Final |
| Scope | PIREQ | 2.8 Rekap PIREP/MAREP | Final |
| Scope | RFQ | Diganti **RQ** (Sub-modul 6); RFQ dipegang Procurement | Final (9 Okt) |

## Pengguna, jabatan, dan struktur organisasi

| Sheet | Isi |
|---|---|
| Copy of user (11) | engineer, ppc, engineering, inspector, store keeper, procurement, gse, mechanic, admin, finance, management |
| Copy of jabatan (4) | staff, chief, manager, director |
| ORG STRUCTURE | Kolom Chief of Workshop, Procurement, Finance, GSE, Management; baris Engineer, Mechanic; catatan "3 pm" |

Pemetaan ke 25 role sistem ada di [[SSG Role & Matriks RBAC]]; struktur organisasi acuan (CMM) ada di [[Organisasi & Aktor]].
