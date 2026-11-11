---
tipe: moc
modul: M2
diperbarui: 2026-11-11
sumber:
  - claude/Decision_Log_Modul2_9Nov.md
  - claude/Review_Desain_Modul2_Setelah_Revisi_8Nov.md
  - claude/Design_Brief_Modul2_UIUX_v3.md
tags: [m2]
aliases: [Modul 2, MPP, Maintenance Programming & Planning, Maintenance Program & Planning]
---
# M2 Maintenance Programming & Planning — Overview

> [!abstract] Posisi 11 Nov 2026
> **77 keputusan final, 56 menunggu** (Decision Log 9 Nov). Review desain 8 Nov atas 46 layar: 18 sesuai, 26 sebagian, 2 belum. Sesi review desain hasil revisi dengan klien dijadwalkan 9 Nov — **jawaban 13 pertanyaan persetujuan belum dicatat** di [[2026-11-09 Review Desain M2 Setelah Revisi]].

## Tujuan

Modul 2 adalah **modul perencanaan**: menyimpan Maintenance Program (MP) per tipe pesawat beserta task master, menghitung jatuh tempo, mencatat Short Term Escalation (STE), dan menyusun Check Pack. Modul 2 **tidak mengeksekusi** pekerjaan; eksekusi berjalan di Work Order [[M3 Overview|Modul 3]].

## Lingkup setelah review

| Masuk M2 | Keluar dari M2 |
|---|---|
| Aircraft Type Profile (tipe pesawat diinput di M2) | AD/SB Compliance dan EO → Modul 1 |
| Maintenance Program, revisi, approval Chief PPC | Handoff Check Pack ke WO → Modul 3 |
| Task Library sebagai **satu-satunya master task card** | Submodul Task Card, eksekusi, NRC, cetak task card → Modul 3 |
| **Hard Time** (batas per PN, sisa umur per SN) — HT report pindah dari Modul 1 | Pencatatan lepas-pasang komponen → Modul 4 |
| Forecast (MP Task, AD/SB & EO, HT, DMI, CML usulan), STE, Check Pack, Out of Phase | Submisi DGCA (di luar sistem) |
| Master format nomor dokumen (sementara; usulan dipusatkan di SSG) | Approval oleh Director of Maintenance (tidak tampil di sistem) |

## Sub-modul dan menu

| Sub-modul | Menu (nomor layar Design Brief v3.0) | Catatan |
|---|---|---|
| [[M2 SM1 Maintenance Program]] | Aircraft Type (1.1–1.3), Maintenance Program (3.1, 4.1, 4.2), Check Type (2.1–2.3), Task Library & Task (5.1, 6.1–6.3), Import (7.1–7.2), Hard Time (26.1–26.3), Format Nomor Dokumen (27.1–27.2) | Urutan sidebar: Aircraft Type, MP, Check Type, Task Library, Hard Time, Format Nomor |
| [[M2 SM2 Planning & Forecast]] | Forecast Dashboard (10.1), Due List (11.1), Detail Due (11.2), WCF Priority (12.1), STE (13.1–13.4), Notifikasi Due (14.1), Report Center (15.1–15.4) | |
| [[M2 SM3 Check Pack & Out of Phase]] | Check Pack List (21.1), Detail (22.1), Form (23.1), Out of Phase Task List (24.1) | |

Pendukung: [[M2 Alur & Status]] · [[M2 Data & Entitas]] · [[M2 Decision Register]] · [[M2 Open Questions]]

## Aktor

| Aktor | Peran |
|---|---|
| PPC Staff | Membuat dan mengajukan MP, mengisi task, membuat Check Pack, mengajukan STE |
| Chief PPC & Engineering | Satu-satunya approver MP (M2 no 23) |
| Engineering Staff | Task Library, Hard Time |
| Line Engineer | Mengajukan STE (WF-STE) |
| Chief Inspector | Memutuskan STE; menentukan perlu DAAO (usulan no 109) |
| Role penerima notifikasi | Diatur di Notifikasi Due (usulan pindah ke SSG-11) |

Matriks akses lengkap: [[SSG Role & Matriks RBAC#Ringkasan matriks per modul]].

## Hubungan dengan modul lain

- **Membaca:** pesawat, PN, TSN/CSN per SN, task EO & Non-routine dari [[Peta Modul & PM|Modul 1]]; DMI dan jam terbang (setiap closing AFML) dari Modul 4; last done dari closing task card Modul 3.
- **Menyediakan:** Hard Time (TBO) ke Modul 1 dan Component Transaction Modul 4; task, Check Pack, dan baris forecast DMI/HT untuk Buat WO di Modul 3.
- Rincian: [[Integrasi End-to-End]], [[Kepemilikan Data & Batas Modul]].

## Langkah berikutnya

1. Catat jawaban sesi 9 Nov → [[M2 Open Questions]] → [[M2 Decision Register]].
2. Selesaikan sisa desain: Due List, filter Grup Maintenance dan tanggal as of di Forecast, field subjek STE, label "AMP" yang tersisa, sidebar Check Pack, data contoh armada nyata ([[M2 SM2 Planning & Forecast]]).
3. Update ERD v7, Sitemap Menu/Screen v2 dari vault, lalu tetapkan v2 sebagai acuan resmi.
4. Putuskan internal bersama Modul 3/4 butir 123–133 (bisa langsung karena PM sama).
