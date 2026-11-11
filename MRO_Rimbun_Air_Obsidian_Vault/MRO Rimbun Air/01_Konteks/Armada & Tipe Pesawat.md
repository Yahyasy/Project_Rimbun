---
tipe: konteks
modul: umum
diperbarui: 2026-11-11
sumber:
  - Maintenance Program B737-300F, B737-800SF, ATR 72, DHC6-300/400
  - claude/Master_Field_AFML_ATR72_B737.md
  - claude/PRD_System_Setting_Governance_RBAC.md
tags: [mro]
aliases: [Armada, Fleet, Tipe Pesawat]
---
# Armada & Tipe Pesawat

## Tipe pesawat dan Maintenance Program

| Tipe | Dokumen MP | Nomor & versi | Catatan |
|---|---|---|---|
| Boeing 737-300F | Maintenance Program B737-300F | RAA-MNT-01.03, Issued 03 Rev 00 | RII di bab 2.2 |
| Boeing 737-800SF | Maintenance Program B737-800SF | RAA-MNT-01.04, Issue 01 Rev 01 | |
| ATR 72-212A | Maintenance Program ATR 72 | RAA-MNT-01.05, Issued 02 Rev 00 | RII di bab 2.5; Roster menulis rating "ATR72-600" (varian, G07) |
| DHC-6 300/400 | Maintenance Program DHC6-300/-400 Series | RAA/I/MP/MA, Issue 01 Rev 01 (Agu 2022) | RII di bab 2.10; work area Check Type khusus DHC-6 |

Registrasi nyata yang muncul di review: **PK-OTK**, **PK-OTD**. Desain masih sering memakai data salah (B737-800/A320neo/B77F, PK-RAA s.d. PK-RAD); data contoh wajib diganti armada di atas sebelum dipresentasikan.

> [!important] Aturan ATA
> Di Rimbun Air ATA hanya dipakai **4 digit chapter-section** (mis. `25-45`), bukan 2 atau 6 digit. Berlaku di Task Library, forecast, report, defect, dan reliability (M2 no 37, dikonfirmasi 8 Nov).

## Perbedaan per tipe yang memengaruhi sistem

| Area | B737 | ATR 72 | DHC-6 |
|---|---|---|---|
| Sektor per halaman AFML | Sampai 6 | 1 | Mengikuti Master Field (tanpa contoh fisik, AF-10) |
| Fuel di AFML | Uplift liter; fuel burn; sisa fuel akhir setelah semua sektor | Uplift liter; fuel used Eng 1 dan Eng 2 | Usulan: 37 field umum (DHC-a) |
| Satuan remaining/total/burn | KG atau LBS sesuai tipe | KG atau LBS sesuai tipe | — |
| Oli di AFML | Eng 1, Eng 2, IDG 1, IDG 2, APU | Eng 1, Eng 2, Others | — |
| Hydraulic | Satu nilai HYD FLD added | Sistem Blue dan Green | — |
| Engine parameter | ENG-03 (termasuk UTC, Mach, SAT, TAT, gross weight, duct pressure, 2 bacaan/halaman) | ENG-01, ENG-02 | Usulan: daftar ATR (turboprop) |
| Scope kewenangan khusus | TC (Boeing saja) | WI (ATR 72 saja) | EMMA (DHC-6 saja) |

## Master tipe pesawat

- Tipe pesawat **diinput di Modul 2** lewat Aircraft Type Profile (M2 no 19, dikonfirmasi 8 Nov).
- Perlu kolom *family* dan relasi varian ke tipe induk (contoh ATR72-600 → ATR 72-212A); pemilik master dibahas dengan PM Modul 1 (SSG P02, M2 KO-1).
- Pesawat (registrasi, MSN, delivery & manufacture date, status) adalah data Modul 1; relasi pesawat ke MP disimpan lewat Tab Aircraft di detail MP (usulan M2 no 79).
