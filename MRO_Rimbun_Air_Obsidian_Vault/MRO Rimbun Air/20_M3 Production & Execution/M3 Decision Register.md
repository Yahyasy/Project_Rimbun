---
tipe: register-keputusan
modul: M3
diperbarui: 2026-11-11
sumber:
  - claude/Knowledge_Base_Modul3_Acuan_Proses_Desain.md
  - claude/Analisis_Revisi_Review_19Okt_Modul3_TaskCard.md
tags: [m3]
aliases: [Keputusan M3, Baseline Modul 3]
---
# M3 Decision Register

Modul 3 tidak punya log bernomor urut seperti Modul 2. Keputusan Final tersebar di tabel aturan catatan topik (kolom **Status = Final** beserta kodenya), sehingga register ini berisi: (1) keputusan struktur, (2) keputusan lintas modul yang mengikat M3, (3) daftar rancangan lama yang tidak berlaku, dan (4) keputusan baru setelah 11 Nov. Teks lengkap B-01–B-64 ada di baseline v4.1 (arsip).

## 1. Keputusan struktur

| Kode | Tgl | Keputusan | Sumber |
|---|---|---|---|
| — | 19 Okt | Modul 3 menjadi **1 sub-modul** Work Order Management | Review klien 19 Okt |
| B-02 | 19 Okt | CRS pindah ke Workshop; pesawat memakai RTS | Review klien |
| B-03 | 19 Okt | OTA Record pindah ke Modul 1 (EC) | Review klien |
| B-04, B-05 | 19 Okt | Eksekusi task card hanya per WO di Detail WO; tidak ada daftar lintas WO | Review klien; M2 no 4 |
| B-06 | 19 Okt | Non-routine Task di-master di M1 (menu Ad-hoc), ditarik ke WO | Review klien |
| B-10–B-13 | 19 Okt | Status WO New → Waiting Approval → Approved → Issued → Work in Progress (otomatis) → Closed; tanpa Rejected | Review klien |
| B-19, B-21 | 19 Okt | Sign-in nama per task card tanpa jam; jam kerja di kertas | Review klien |
| B-22 | 19/23 Okt | Status task card tanpa On Hold dan Deferred | Review klien |
| B-30–B-35 | 19 Okt | NRC adalah anak task card, dikerjakan di WO, tidak di-master | Review klien |
| B-54–B-62 | 19–23 Okt | Temuan yang tidak selesai lewat Ad-hoc + MDDR; ditulis manual sebagai defect AFML saat keluar hangar; tidak ada defer ke DMI dari task card | Review klien |
| B-63, B-64 | 23–26 Okt | DMI dikerjakan sebagai baris task card; DMI "Closed by WO" saat WO Close | Review M4 |
| K1 | 29 Okt | Pending Install WO harus nol sebelum Close WO (Close WO menjadi batas material) | Konfirmasi PM |
| K2 | 29 Okt | Tool dari gudang lewat Tool Loan | Konfirmasi PM |
| K4 | 29 Okt | RII butuh dua orang, dua stamp (pelaksana ≠ inspector) | Konfirmasi PM; MP B737 2.2 |

## 2. Keputusan lintas modul yang mengikat M3

| Kode | Tgl | Keputusan | Asal |
|---|---|---|---|
| — | 8 Okt | Modul 4 penulis tunggal transaksi pasang-lepas komponen; M3 hanya menautkan | Keputusan internal lintas modul |
| CT-01, CT-02 | 27 Okt | Removal & Installation dua transaksi; Scheduled otomatis bila WO terisi | Review M4 |
| CT-06, CT-10 | 27 Okt | Pending Install / Pending RTS; consumable tanpa SN dibebankan langsung ke WO | Review M4 |
| CT-08 | 27 Okt | Robbed antar pesawat tanpa gudang, approval Director of Maintenance | Review M4 |
| LM-10 | 28 Okt | TSN/CSN per sektor AFML yang sudah di-close | Review M4 |
| M2-20 | 19 Okt | Part 100% otomatis masuk Material Required; tool read-only dari Task Library | Review M3 |
| K5-04 | 5 Nov | Swap adalah proses tersendiri, dua arah, hanya antar pesawat | Konfirmasi M4 |
| K5-09 | 5 Nov | Oli/hydraulic di-issue ke WO, bukan ke registrasi | Konfirmasi M4 |
| K5-02 | 5 Nov | Wheel assy: bagian outer sebagai induk, PN & SN sendiri | Konfirmasi M4 |

## 3. Rancangan lama yang tidak berlaku

Dipakai untuk memastikan desain baru tidak mengacu ke rancangan lama.

| No | Rancangan lama | Pengganti | Sumber |
|---|---|---|---|
| 1 | Status WO Draft | New | AS-03, B-10 |
| 2 | Approve sekaligus melepas WO | Approved, lalu Issued saat serah terima | R-09, B-12 |
| 3 | Status WO Rejected | Kembalikan ke New dengan catatan, atau Cancel | B-11 |
| 4 | Sign-in pertama sebagai penugasan; sesi sign-in/out berjam | Sign-in nama per task card tanpa jam | R-05, AS-19, B-19, B-21 |
| 5 | Status task card On Hold dan Deferred | Dihapus | R-03, B-22 |
| 6 | Mekanik menandai selesai, engineer AMEL countersign | Closing oleh personel yang di-sign-in, dengan stamp | R-02, B-24, B-25 |
| 7 | Sign-off final Chief per task card | Dihapus (usulan) | R-04, Q-12 |
| 8 | Checkbox verifikasi dokumen saat Close WO | Close WO cukup tanggal wajib | R-13, AS-11, B-15 |
| 9 | Material Request berstatus lengkap dengan penyetuju terpisah | Baris Open/Issued; Book membentuk MR yang di-approve PPC | R-14, MAT-01, B-37–B-44 |
| 10 | OTA Record di M3 | Modul 1 | AS-23, B-03 |
| 11 | CRS di M3 | Workshop; pesawat RTS | K-02, B-02 |
| 12 | TSN/CSN diisi saat mulai kerja, per halaman AFML | Sejak WO dibuat, per sektor + as of | B-14, LM-10 |
| 13 | Menu Task Card lintas WO dan Panel Eksekusi | Task Card Execution List di Detail WO | B-04, M2-17 |
| 14 | Task Card Detail tab Checklist, Komponen, Material, Sign-off | Header tetap, work description, material & tool, closing | M2-18, M2-19, M2-22, Q-20 |
| 15 | Defer task card ke DMI; DMI tertutup saat task card selesai | Tidak ada DMI dari task card; DMI ditutup saat WO Close atau manual | B-60, B-61, M4-14 |
| 16 | NRC dan MDDR satu form; NRC menerbitkan Sub Task Card | NRC anak task card; MDDR di Ad-hoc | B-30, B-54, M2-24 |
| 17 | Menu Tarik Task Card dan Handoff WO di M2 | Form WO M3 membaca Check Pack & task dari M2 | M2-27, R57, Q-M2-07 |
| 18 | Satu form Record Replacement lepas-pasang | Removal & Installation terpisah | CT-01 |
| 19 | Terjadwal/Tidak Terjadwal dipilih manual | Otomatis Scheduled bila WO terisi | CT-02 |
| 20 | WO Unscheduled langsung dari defect | Defect terjadwal lewat DMI; Asal WO Planning/Manual | M4-28, Q26-06 |
| 21 | Pending Install cukup diperingatkan saat Close WO | Harus nol sebelum Close WO | K1, Q-34 |
| 22 | Tool dipinjam tanpa catatan / lewat request material | Tool Loan | B-45, K2 |
| 23 | Semua pengeluaran gudang di luar WO wajib RQ | B-40 berlaku untuk issue ke WO; line maintenance diatur M5 (usulan) | B-40, Q-41 |
| 24 | Temuan "di-convert" menjadi defect M4 | Ditulis manual sebagai defect AFML (usulan redaksi) | B-60, B-62, Q-42 |

## 4. Keputusan baru (setelah 11 Nov)

| Kode | Tgl | Sesi | Menu | Keputusan → dampak | Acuan |
|---|---|---|---|---|---|
| | | | | | |
