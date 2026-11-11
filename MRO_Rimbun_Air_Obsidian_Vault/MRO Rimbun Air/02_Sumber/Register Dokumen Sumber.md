---
tipe: sumber
modul: umum
diperbarui: 2026-11-11
tags: [mro]
aliases: [Daftar Dokumen, Register Sumber]
---
# Register Dokumen Sumber

## A. Dokumen klien (acuan `[DOK]`)

| Kode | Dokumen | Nomor & versi | Dipakai untuk | Lokasi |
|---|---|---|---|---|
| CMM | Company Maintenance Manual | RAA-MNT-01.01 Issue 02 Rev 00, 29 Des 2025 (152 hal, 11 bab) | Struktur organisasi (2.2), tugas jabatan (2.3), STE (3.6), robbing (3.11) | Project; salinan uncontrolled ber-watermark |
| MP-733 | Maintenance Program B737-300F | RAA-MNT-01.03 Issued 03 Rev 00 | Task, interval, RII bab 2.2 | Project |
| MP-738 | Maintenance Program B737-800SF | RAA-MNT-01.04 Issue 01 Rev 01 | Task, interval | Drive |
| MP-AT7 | Maintenance Program ATR 72 | RAA-MNT-01.05 Issued 02 Rev 00 | Task, interval, RII bab 2.5 | Project |
| MP-DHC | Maintenance Program DHC6-300/-400 | RAA/I/MP/MA Issue 01 Rev 01, Agu 2022 | Task, interval, RII bab 2.10 | Project |
| MSPM | Maintenance Support Procedure Manual | RAA-MNT-02.01 Issue 00 Rev 00, 31 Mar 2026 | Tugas jabatan (2.2), Company Authorization & OTA (bab 3), store, tool, procurement (bab 5) | Project |
| MTPM | Maintenance Training Procedure Manual | RAA-MNT-02.02 Issue 00 Rev 00, 31 Mar 2026 | Kategori personel, level NDT, Training Matrix | Project |
| WBSPM | Wheel & Brake Shop Procedure Manual | RAA-MNT-02.03 Issue 00 Rev 00, 29 Des 2025 | Workshop Engineer/Mechanic, alur shop | Project |
| NDTPM | Non Destructive Testing Procedure Manual | RAA-MNT-02.04 Issue 00 Rev 00, 29 Des 2025 | Sertifikasi, suspensi, pencabutan NDT; retensi 10 tahun | Project |
| ROSTER | Maintenance Personnel Roster | RAA-MNT-03.02 Issue 00 Rev 02, 6 Jul 2026 | 37 personel berwenang, nomor otorisasi, rating, scope | Project |
| REQ | Rimbun Air Requirements | xlsx proyek; versi Google diperbarui 15 Okt 2026 | Services, scope, REQ details, user, jabatan ([[Requirements Awal REQ]]) | Project |
| UCD | Use Case Diagram MRO Systems | Lucid "Copy of RIMBUN AIR" hal. 1 | Aktor resmi per modul | Lucid |
| Form | RAA-TLM-007 DMI Log; RAA-TLM-006 Maintenance Control DMI/MEL Summary | R0, Des 2025 | Menu 2.2, 2.4, 2.7 Modul 4 (K6) | Lampiran 6 Nov |
| Form | RAA-TLM-001 AOG Declaration; RAA-TLM-002 Serviceable Declaration | — | Menu 2.5 Modul 4 | Drive |
| Form | RAA/MD-49 task card; RAA/MD-05 STE | — | Header task card M3; dokumen STE M2 | Drive |
| Form | RAA-TCI-011 aplikasi, RAA-TCI-013 asesmen, RAA-TCI-015 Company Authorization Card | — | SSG-04 | MSPM bab 3 |
| Form | RAA-TMT-002 Unserviceable Tag | — | Tool rusak (MSPM 5.3.5) | MSPM |
| Laporan | Reliability Report Boeing Fleet Q2 2026 | — | Rumus rate, MTBUR, alert level, format export Modul 4 | Lampiran review |
| Referensi | A/C Actual Flight Closing; papan tulis hitungan AFML | — | Aturan closing dan TSN/CSN per sektor | Lampiran review |
| Folder | Drive "Kebutuhan lanjutan" | per meeting (Forms & Tags, NRC, ARC, …) | Dokumen operasional saat ini | [[Workspace Lucid Figma Drive]] |

## B. Dokumen analisis di Project Claude (bukti historis)

Ekspor dari Project, simpan di `90_Arsip/` dengan nama asli. Kolom **Status** menunjukkan apakah dokumen masih menjadi acuan atau sudah dirangkum ke vault.

| Tanggal | Dokumen (`claude/…`) | Modul | Isi | Status |
|---|---|---|---|---|
| 9 Nov | Decision_Log_Modul2_9Nov | M2 | 77 keputusan final, 56 menunggu | Dirangkum ke [[M2 Decision Register]] dan [[M2 Open Questions]] |
| 8 Nov | Review_Desain_Modul2_Setelah_Revisi_8Nov | M2 | Review 136 frame, alur presentasi, 13 pertanyaan sesi | Dirangkum ke catatan SM M2 dan [[2026-11-09 Review Desain M2 Setelah Revisi]] |
| 6 Nov | Konfirmasi_DMI_Modul4_6Nov | M4 | K6-01–04, pemetaan form DMI | Dirangkum |
| 5 Nov | Konfirmasi_Modul4_5Nov | M4 | K5-01–09 | Dirangkum |
| 4 Nov | Keputusan_Fluid_Consumption_Modul4_4Nov | M4 | FL-01–05, FU-01–02 | Dirangkum |
| 4 Nov | Keputusan_AFML_Modul4_4Nov | M4 | AF-01–11, H-01–03 | Dirangkum |
| 3 Nov | Review_Desain_Modul4_Keseluruhan_3Nov | M4 | 268 frame, mapping revisi, 3 gelombang | Acuan revisi desain |
| 3 Nov | Flow_Detail_Modul4_per_Submodul_Menu_3Nov | M4 | 33 menu, 55 langkah, 11 objek, 22 aliran | Dirangkum, dengan koreksi keputusan 4–6 Nov |
| 3 Nov | Insight_Perhitungan_Flight_Log_AFML_Papan_Tulis | M4 | WB, WQ | Acuan rumus |
| 3 Nov | Insight_Actual_Flight_Closing_AFML_Modul4 | M4 | FQ, FC | Acuan (sebagian diganti AF-02, AF-04) |
| 3 Nov | Insight_Reliability_Report_Boeing_Q2_2026_Modul4 | M4 | Rumus, RL | Acuan rumus |
| 3 Nov | Analisis_Insight_Review_2Nov_Modul4_RQ_Procurement | M4 | RQ, PC, P | Acuan |
| 2 Nov | Flow_Modul4_Terbaru_2Nov | M4 | Flow sebelum 3 Nov | Diganti Flow Detail 3 Nov |
| 2 Nov | Master_Field_AFML_ATR72_B737 | M4 | 86 field AFML | Acuan field |
| 1 Nov | Design_Brief_Modul3_UIUX_v2 | M3 | Brief v2.0 (upd 5 Nov) | **Acuan designer** |
| 1 Nov | Review_Desain_HiFi_Modul3_1Nov | M3 | 142 komentar 34 layar | Acuan revisi desain |
| 30 Okt | Knowledge_Base_Modul3_Acuan_Proses_Desain | M3 | Kondisi akhir M3 | Dirangkum ke catatan M3 |
| 30 Okt | Bahasan_Modul3_dari_Review_Modul2 / dari_Review_Modul4_22_28Okt | M3 | Bahasan lintas | Masuk KB M3 |
| 29 Okt | Flow_Modul3_Terbaru_28Okt | M3 | 16 langkah, K1–K5 | Masuk KB M3 |
| 29 Okt | Design_Brief_Modul2_UIUX_v3 | M2 | Brief v3.0, layar 1.1–27.2 | **Acuan designer** |
| 29 Okt | Review_Desain_Figma_Modul2_29Okt | M2 | Temuan Figma (#nnn) | Historis |
| 29 Okt | Knowledge_Base_Modul2_Acuan_Desain_UIUX | M2 | Kondisi akhir M2, Hard Time | Masuk Decision Log 9 Nov |
| 29 Okt | Bahasan_Modul2_dari_Review_Modul3 / dari_Review_Modul4_22_28Okt | M2 | M2-01–M2-35 | Masuk Decision Log 9 Nov |
| 28–29 Okt | Analisis_Insight_Review_27_28Okt…, Detail_Submodul5_Reliability… | M4 | CT, REL, LM | Acuan |
| 27 Okt | Flow_Pembuatan_Task_Card | M3 | Struktur task card | Masuk KB M3 |
| 24–27 Okt | Analisis_Insight_Review_22Okt / 23Okt / 26Okt, Review_Desain_HiFi_AFML… | M4 | AFR, M4, CML | Acuan |
| 25 Okt | Insight_Modul3_dari_Review_23Okt | M3 | M3-01–10 | Masuk KB M3 |
| 19 Okt | Analisis_Revisi_Review_19Okt_Modul3_TaskCard | M3 | Baseline v4.1 B-01–B-64 | Masuk KB M3 |
| 16 Okt | PRD_System_Setting_Governance_RBAC (rev 52, 5 Nov) | SSG | PRD lengkap | **Acuan**; dirangkum ke catatan SSG |
| 13 Okt | Analisis_Review_Desain_Klien_Modul2 | M2 | R01–R57, C1–C27 | Masuk Decision Log 9 Nov |

## C. Lampiran SSG

`RBAC_System_Setting_Governance_Rimbun_Air.xlsx` (17 sheet) dan `PoC_RBAC_SSG_Rimbun_Air.zip` (`rbac_data.py`, `authz.py`, `run_poc.py`, `schema.sql`, `poc_rbac.db`). Lihat [[SSG Data Integrasi & PoC]].
