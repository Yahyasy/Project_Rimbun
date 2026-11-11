---
tipe: submodul
modul: SSG
diperbarui: 2026-11-11
sumber:
  - claude/PRD_System_Setting_Governance_RBAC.md
  - RBAC_System_Setting_Governance_Rimbun_Air.xlsx
tags: [ssg]
aliases: [Role Catalog, Matriks RBAC, Hak Akses]
---
# SSG Role & Matriks RBAC

Sistem memakai **25 role**: 12 sudah ada di daftar role Employee Master, 13 baru untuk fungsi yang muncul di UCD, REQ, dan manual. Role disusun dari **fungsi** (11 user group REQ) × **jenjang** (staff, chief, manager, director), lalu dipetakan ke posisi CMM. Matriks lengkap: **104 menu di 12 modul, 301 permission, 1.180 pasangan role–permission** (workbook, sheet Matriks RBAC).

## Katalog role

| Kode | Role | Fungsi | Jenjang | Cakupan data | Status | Dasar |
|---|---|---|---|---|---|---|
| DIR-MNT | Director of Maintenance | management | director | Semua | Final | CMM 2.3.3 |
| CHF-INS | Chief Inspector | inspector | chief | Semua | Final | CMM 2.3.4; MSPM 3.4 |
| CHF-LM | Chief Line Maintenance | engineer | chief | Unit | Final | CMM 2.2.2; MSPM 3.5 |
| CHF-PPC | Chief PPC & Engineering | ppc | chief | Unit | Final | CMM 2.2.2; klien R09 |
| CHF-WBS | Chief Wheel & Brake Shop | engineer | chief | Unit | Final | CMM 2.2.2; WBSPM 2.1 |
| MSTC | Maintenance Standard, Training & Compliance | inspector | staff | Semua | Usulan | MSPM 2.2.1 |
| INSP-AC | Aircraft (Maintenance) Inspector | inspector | staff | Semua | Final | MSPM 2.2.2; UCD |
| INSP-RCV | Receiving Inspector | inspector | staff | Station | Usulan | UCD; Roster 2.1 |
| INSP-TE | Tool & Equipment Inspector | inspector | staff | Station | Usulan | Roster 2.2; MSPM 5.7.2 |
| ENG-LINE | Line Engineer | engineer | staff | Station | Final | MSPM 2.2.3; Roster 2.3 |
| MECH-LINE | Line Mechanic | mechanic | staff | Station | Final | MSPM 2.2.4; Roster 2.4 |
| STF-PPC | PPC Staff | ppc | staff | Unit | Final | MSPM 2.2.5; UCD |
| STF-ENGR | Engineering Staff | engineering | staff | Unit | Konfirmasi | UCD; REQ |
| TECH-REC | Technical Record | ppc | staff | Semua | Final | MSPM 2.2.6 |
| STORE | Store / Storeman | store keeper | staff | Station | Usulan | MSPM 2.2.7; UCD |
| ENG-WS | Workshop Engineer | engineer | staff | Unit | Final | WBSPM 2.2; Roster 2.8 |
| MECH-WS | Workshop Mechanic | mechanic | staff | Unit | Final | WBSPM 2.3; Roster 2.9 |
| STF-PROC | Procurement Staff | procurement | staff | Unit | Usulan | UCD; MSPM 5.5 |
| STF-FIN | Finance Staff | finance | staff | Unit | Usulan | UCD; MSPM 5.5.2 |
| STF-GSE | GSE Staff | gse | staff | Unit | Usulan | UCD; REQ |
| MGMT | Management (Managing Director, Board) | management | director | Semua | Usulan | UCD; MSPM 5.5.2 |
| DIR-OPS | Director of Operations | management | director | Semua | Usulan | M4 approval MEL/DMI Extension |
| QS-VIEW | Quality & Safety Viewer | management | director | Semua, baca | Usulan | MSPM/MTPM 1.6 |
| SYS-ADM | System Administrator | admin | staff | Pengaturan saja | Usulan | REQ user admin; K6 |
| AUDITOR | Auditor berbatas waktu | management | staff | Semua, baca | Konfirmasi | MSPM 5.1 #9; K37 |

**Prinsip**
- Satu user boleh banyak role; hak akses = gabungan semua role (BR-02; K35c menunggu konfirmasi resmi).
- Spesialis (NDT, Borescope, RII, EGR, W&B, Compass Swing) **bukan role** — mereka scope kewenangan.
- Jenjang manager belum dipakai karena Directorate of Maintenance tidak punya posisi manager.
- Safety Manager, Chief Maintenance, dan Pilot/FDC belum dibuat sampai Q02 dan Q14 terjawab.
- Garis atasan role dipakai untuk aturan "chief unit pembuat" (approval RQ) dan pengajuan Company Authorization oleh chief departemen.

## Delapan aksi standar

Permission ditulis `<kode menu>.<aksi>`, mis. `M2-03.A` = menyetujui Maintenance Program.

| Kode | Aksi | Dicek kewenangan? | Contoh |
|---|---|---|---|
| V | View | Tidak | Melihat Forecast Dashboard |
| C | Create/Edit | Tidak | Mengisi Flight Log |
| D | Delete/Cancel/Void | Tidak | Membatalkan WO New |
| S | Submit | Tidak | Mengajukan STE |
| A | Approve/Reject | Ya — approval authority (APR/GOV) | Chief PPC menyetujui MP |
| X | Sign/Certify | Ya — Company Authorization (CERT) | Engineer release PF, Inspector sign RII |
| P | Print/Export | Tidak | Cetak RTS, ekspor laporan |
| K | Configure | Tidak | Mengatur format penomoran |

## Cakupan data

| Cakupan | Arti | Dipakai untuk |
|---|---|---|
| Semua | Seluruh data modul | Director, Chief Inspector, MSTC, Technical Record, viewer |
| Unit | Data unit/departemen sendiri | Chief LM, Chief PPC, Chief WBS, staf kantor |
| Station | Station sesuai **base kerja di Employee Master**; penugasan di luar base dilakukan dengan memperbarui data employee (tidak ada penugasan sementara di sistem) | Line Engineer/Mechanic, Store, Receiving & Tool Inspector |
| Status dokumen | Baris tertentu menurut status | Engineer/Mechanic hanya WO berjalan; Technical Record hanya WO Closed |
| Milik sendiri | Draft dan profil sendiri | Profil Saya, draft pengajuan |

## Ringkasan matriks per modul

| Modul | Menu | Input (C/S) | Approve (A) | Sign (X) | Role yang melihat |
|---|---|---|---|---|---|
| SSG | 15 | SYS-ADM, MSTC, chief departemen, CHF-LM (OTA); semua role untuk Profil Saya | DIR-MNT, CHF-INS (GOV), approver lain lewat inbox | — | 25 |
| M01 EC | 11 | STF-ENGR, CHF-PPC, CHF-LM, MSTC, SYS-ADM | CHF-PPC, CHF-INS | — | 21 |
| **M02 MPP** | 12 | STF-PPC, STF-ENGR, CHF-PPC, ENG-LINE, INSP-AC, CHF-LM | CHF-PPC, CHF-INS | — | 15 |
| **M03 P&E** | 10 | STF-PPC, ENG-LINE, MECH-LINE, TECH-REC, CHF-PPC | CHF-PPC, STORE | ENG-LINE, INSP-AC | 14 |
| **M04 FOI** | 21 | ENG-LINE, MECH-LINE, INSP-AC, TECH-REC, STF-PPC, STF-ENGR, CHF-LM, CHF-PPC | CHF-INS, DIR-OPS, DIR-MNT, CHF-LM, CHF-PPC, CHF-WBS | ENG-LINE | 18 |
| M05 Material & Logistics | 9 | STORE | INSP-TE | INSP-RCV | 10 |
| M06 Procurement | 7 | STF-PROC | CHF-INS, STF-PROC, DIR-MNT, MGMT | — | 7 |
| M07 Document Record | 3 | MSTC, CHF-INS, CHF-WBS, CHF-PPC, STF-ENGR, TECH-REC, INSP-AC | DIR-MNT | — | 25 |
| M08 Costing | 4 | STF-FIN, STF-PROC | — | — | 4 |
| M09 Workshop & Hangar | 6 | STF-PPC, ENG-WS, MECH-WS, CHF-WBS | CHF-WBS | ENG-WS | 7 |
| M10 GSE | 5 | STF-GSE, STF-PROC, STORE | belum diketahui | — | 6 |
| M11 Managerial Reports | 1 | — | — | — | 10 |

Baris M01, M05–M11 adalah baseline **[USULAN]** dan perlu divalidasi PM pemilik modul. Baris M02–M04 perlu disesuaikan dengan menu terbaru (mis. M3 tanpa CRS/OTA; M4 3.6 Swap, Fluid 4.1–4.3).

## Aturan tampilan (semua modul)

- Menu dan tombol yang tidak ada di role user **tidak ditampilkan**.
- Tombol keputusan approval tetap tampil tetapi **nonaktif** bagi yang bukan approver, dengan keterangan langkah dan role yang ditunggu.
- Tombol tanda tangan (X) tampil bila role mengizinkan; `checkAuthority` dijalankan saat diklik dan alasan penolakan ditampilkan.
