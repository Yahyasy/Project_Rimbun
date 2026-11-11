---
tipe: meta
modul: umum
diperbarui: 2026-11-11
tags: [mro, meta]
aliases: [Kamus Kode, Kode Keputusan, Label Status]
---
# Kamus Kode & Label

## Label status

| Label | Arti | Dipakai di desain |
|---|---|---|
| **Final** | Keputusan klien atau dokumen klien sudah jelas | Ya, tanpa penanda |
| **Usulan** | Rancangan tim, belum disetujui klien | Ya, dengan label *Belum final* |
| **Menunggu** | Belum bisa didesain final sampai pertanyaannya dijawab | Ya bila perlu, dengan label *Belum final* |
| **Ditahan** | Dibahas tetapi sengaja ditunda; desain tetap seperti sekarang | Tidak berubah |
| **Terjawab \<tgl>** | Status baris di Open Questions setelah ada jawaban | — |
| **Diganti oleh \<kode>** | Keputusan lama yang sudah tidak berlaku | — |

## Label bukti

`[DOK]` aturan tertulis di manual klien · `[KLIEN]` jawaban atau keputusan klien · `[RANCANGAN]` dokumen kerja tim Nodewave · `[USULAN]` keputusan desain yang perlu disetujui · `[KONFIRMASI]` menunggu jawaban · `[TERKONFIRMASI]` konfirmasi sudah diterima (dengan tanggal).

## Kode per modul

> [!warning] Huruf yang sama dipakai berbeda di tiap modul
> `K`, `P`, `Q`, dan `C` muncul di lebih dari satu modul dengan arti berbeda. Saat mengutip lintas modul, tulis awalannya: `M2:K5`, `M3:K1`, `M4:P-02`, `SSG:P03`.

### Modul 2

| Kode | Arti | Sumber |
|---|---|---|
| No 1–77 | Baris keputusan final di Decision Log 9 Nov | [[M2 Decision Register]] |
| No 78–133 | Baris usulan menunggu konfirmasi di Decision Log 9 Nov | [[M2 Open Questions]] |
| R01–R57 | Input klien pada review desain Modul 2, 13 Okt | Analisis_Review_Desain_Klien_Modul2 |
| C1–C27 | Klarifikasi Modul 2 | idem |
| K1–K40, KO-x | Daftar Konfirmasi Modul 2 (30 Sep) | Daftar Konfirmasi M2 |
| M2-01–M2-16 | Bahasan Modul 2 dari review Modul 4 (22–28 Okt) | Bahasan_Modul2_dari_Review_Modul4 |
| M2-17–M2-35 | Bahasan Modul 2 dari review Modul 3 (19–27 Okt) | Bahasan_Modul2_dari_Review_Modul3 |
| Q-M2-01–09 | Pertanyaan lintas Modul 2 | idem |
| HT-xx | Pertanyaan Hard Time | Design Brief M2 v3 |
| #nnn | Nomor komentar Figma (review 29 Okt) | Review_Desain_Figma_Modul2_29Okt |
| Sesi no 1–13 | Pertanyaan persetujuan untuk sesi klien 9 Nov | Review_Desain_Modul2_Setelah_Revisi_8Nov |
| Layar 1.1–27.2 | Nomor layar Design Brief M2 v3.0 | Design_Brief_Modul2_UIUX_v3 |

### Modul 3

| Kode | Arti | Sumber |
|---|---|---|
| B-01–B-64 | Baseline keputusan Modul 3 v4.1 | Analisis_Revisi_Review_19Okt_Modul3_TaskCard |
| Q-01–Q-47 | Pertanyaan Modul 3 | Baseline + Flow 28 Okt + bahasan lintas |
| M3-01–M3-10 | Temuan Modul 3 dari review Modul 4 (23 Okt) | Insight_Modul3_dari_Review_23Okt |
| M3B-01–M3B-22 | Bahasan Modul 3 dari review Modul 4 (22–28 Okt) | Bahasan_Modul3_dari_Review_Modul4 |
| K1–K5 | Konfirmasi PM 29 Okt (**bukan** K Modul 2) | Flow_Modul3_Terbaru_28Okt |
| AS-, R-, MAT- | Kode lama sebelum baseline v4.1 | arsip |
| Menu 1–10 | Nomor menu Design Brief M3 v2.0 (Menu 11 pindah ke EC, 12–14 ke Workshop) | Design_Brief_Modul3_UIUX_v2 |

### Modul 4

| Kode | Arti | Sumber |
|---|---|---|
| A1–H4 | 55 langkah alur per sub-modul (A AFML … H Lintas) | Flow_Detail_Modul4 3 Nov |
| AFR-01–29 | Review AFML 22 Okt | Analisis_Insight_Review_22Okt |
| M4-01–M4-32 | Review Defect & Deferred 23 dan 26 Okt | Analisis_Insight_Review_23Okt / 26Okt |
| CML-01–08 | Review CML 26 Okt | idem 26 Okt |
| CT-01–11, LM-01–11, REL-01–21 | Review Component Transaction & Reliability 27–28 Okt (LM = lintas modul) | Analisis_Insight_Review_27_28Okt |
| Q26-xx, Q27-xx, Q28-xx | Pertanyaan per tanggal review | idem |
| RQ-01–23, PC-01–12, P-01–08 | Review RQ & Procurement 2 Nov (**P-xx bukan P SSG**) | Analisis_Insight_Review_2Nov |
| FQ-01–08, FC3–FC6 | Insight Actual Flight Closing AFML | Insight_Actual_Flight_Closing |
| WB-01–09, WQ-01–06 | Hitungan AFML dari papan tulis klien | Insight_Perhitungan_Flight_Log |
| RL-01–09 | Insight Reliability Report Boeing Fleet Q2 2026 | Insight_Reliability_Report |
| HDR-, ENG-, OIL-, HYD-, FUL- | Field di Master Field AFML (86 field) | Master_Field_AFML_ATR72_B737 |
| AF-01–11, H-01–03 | Keputusan & butir ditahan AFML 4 Nov | Keputusan_AFML_Modul4_4Nov |
| FL-01–05, FU-01–02 | Keputusan & usulan Fluid Consumption 4 Nov | Keputusan_Fluid_Consumption_Modul4_4Nov |
| K5-01–09 | Konfirmasi Modul 4, 5 Nov | Konfirmasi_Modul4_5Nov |
| K6-01–04 | Konfirmasi DMI, 6 Nov | Konfirmasi_DMI_Modul4_6Nov |
| DHC-a, DHC-b | Butir terbuka DHC-6 | Keputusan_AFML_Modul4_4Nov |

### System Setting & Governance (SSG)

| Kode | Arti |
|---|---|
| D1–D8 | Keputusan desain utama PRD |
| SSG-01–SSG-15 | Menu SSG |
| BR-01–BR-22 | Aturan bisnis governance |
| SOD-01–SOD-08 | Aturan Segregation of Duties |
| WF-xxx | Approval workflow (WF-MP, WF-STE, WF-RQ, …) |
| NFR-01–NFR-13 | Kebutuhan non-fungsional keamanan |
| G01–G17 | Konflik & gap antar dokumen |
| Q01–Q17 / P01–P08 | Klarifikasi ke Rimbun Air / ke PM lain (**bukan** P-xx Modul 4) |
| S01–S69 | Skenario PoC |
| DIR-MNT, CHF-INS, … | Kode role (25 role) |
| AC-, SP-, WS-, GM-, APR-, GOV- | Kode scope kewenangan (46 scope) |

## Kode baru setelah 11 Nov 2026

| Jenis | Pola | Contoh |
|---|---|---|
| Keputusan | `{MOD}-KP-YYMMDD-nn` | `M4-KP-261112-01` |
| Pertanyaan | `{MOD}-Q-YYMMDD-nn` | `M2-Q-261112-03` |
| Isu lintas modul | `LX-nn` | `LX-07` |
| Temuan saat sesi (sementara) | `TEMUAN-n` di catatan sesi | diganti kode resmi saat triase |

`{MOD}` = `M2`, `M3`, `M4`, atau `SSG`. Tanggal = tanggal sesi tempat keputusan atau pertanyaan muncul, sehingga kode tidak pernah bentrok antar sesi.
