---
tipe: moc
modul: umum
diperbarui: 2026-11-11
tags: [mro]
aliases: [Home, Beranda, Dashboard]
---
# MRO Rimbun Air — Home

> [!info] Sumber kebenaran tunggal
> Vault ini memegang konteks dan keputusan untuk empat lingkup Yahya di proyek sistem MRO Rimbun Air (Nodewave): **Modul 2**, **Modul 3**, **Modul 4**, dan **System Setting & Governance (RBAC)**. Posisi pengetahuan: **11 November 2026**.

## Mulai dari sini

- [[Cara Pakai Vault]] — struktur, hierarki kebenaran, aturan menulis
- [[Alur Kerja Gathering & Update]] — langkah sebelum, saat, dan sesudah sesi klien
- [[Kamus Kode & Label]] — arti R01, B-xx, AF-xx, K5-xx, BR-xx, dan label status
- [[Glosarium]]

## Modul

| Modul | MOC | Keputusan | Pertanyaan terbuka | Posisi terakhir |
|---|---|---|---|---|
| M2 Maintenance Programming & Planning | [[M2 Overview]] | [[M2 Decision Register]] | [[M2 Open Questions]] | 77 final, 56 menunggu (9 Nov); desain 46 layar: 18 sesuai, 26 sebagian, 2 belum; **jawaban sesi 9 Nov belum dicatat** |
| M3 Production & Execution | [[M3 Overview]] | [[M3 Decision Register]] | [[M3 Open Questions]] | 1 sub-modul WO Management; Design Brief v2; review hi-fi 142 komentar; 60 butir terbuka |
| M4 Flight Operations Interfacing | [[M4 Overview]] | [[M4 Decision Register]] | [[M4 Open Questions]] | 33 menu (+3.6 Swap); keputusan 4–6 Nov masuk Brief v2; revisi desain 3 gelombang |
| SSG System Setting & Governance | [[SSG Overview]] | [[SSG Workflow SoD Aturan & NFR]] | [[SSG Gap & Klarifikasi]] | PRD rev 52 draft review PM; PoC 69/69 lulus |

## Konteks

[[Ringkasan Proyek]] · [[Peta Modul & PM]] · [[Requirements Awal REQ]] · [[Armada & Tipe Pesawat]] · [[Organisasi & Aktor]] · [[Stakeholder & Kontak]] · [[Register Dokumen Sumber]] · [[Workspace Lucid Figma Drive]]

## Lintas modul

[[Kepemilikan Data & Batas Modul]] · [[Integrasi End-to-End]] · [[Isu Harmonisasi Lintas Modul]]

## Sesi

- [[Log Sesi & Review]]
- Perlu ditriase: [[2026-11-09 Review Desain M2 Setelah Revisi]]

## Prioritas terbuka per 11 Nov

1. **M2** — catat jawaban 13 pertanyaan sesi 9 Nov, lalu putuskan butir internal 123–133.
2. **Lintas** — LX-01 (Limit Type DMI di forecast), LX-02 (pengaturan dipusatkan di SSG), LX-03 (lokasi OTA), LX-04 (workflow RQ & Swap).
3. **M4** — butir Reliability RL-01–RL-09, approver RQ (P-02), approval & cetak Swap (CT-08), jalur WO Unscheduled (M4-28).
4. **M3** — 15 pertanyaan prioritas Tinggi ke Rimbun Air; 29 komentar *wajib diperbaiki* di hi-fi.
5. **SSG** — Q01, Q02, Q04–Q06 ke klien dan P01–P03 ke PM lain; perbarui `rbac_data.py` dengan menu terbaru (LX-07).

## Catatan yang perlu diperbarui

Catatan bertag `#perlu-update` belum sinkron dengan keputusan terbaru. Dengan plugin Dataview:

```dataview
LIST FROM #perlu-update SORT file.name ASC
```

Tanpa Dataview: klik tag `#perlu-update` di panel Tags.
