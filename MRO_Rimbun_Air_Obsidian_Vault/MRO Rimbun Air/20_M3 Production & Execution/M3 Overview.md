---
tipe: moc
modul: M3
diperbarui: 2026-11-11
sumber:
  - claude/Knowledge_Base_Modul3_Acuan_Proses_Desain.md
  - claude/Design_Brief_Modul3_UIUX_v2.md
  - claude/Review_Desain_HiFi_Modul3_1Nov.md
tags: [m3]
aliases: [Modul 3, Production & Execution, P&E, Work Order Management]
---
# M3 Production & Execution — Overview

> [!abstract] Posisi 11 Nov 2026
> Modul 3 kini **satu sub-modul: Work Order Management** (review klien 19 Okt). Acuan kondisi akhir: Knowledge Base 30 Okt → Design Brief UI/UX v2.0 (1 Nov, diperbarui 5 Nov). Review hi-fi 1 Nov: **142 komentar** di 34 layar (29 wajib diperbaiki, 64 sesuaikan, 18 tambahkan, 6 hapus/pindah, 25 sudah sesuai). Ada **60 butir terbuka** (15 prioritas tinggi untuk Rimbun Air).

## Tujuan

Semua pekerjaan hangar dicatat **per task card di dalam WO**, dari WO dibuat sampai Close WO. Penggantian komponen dicatat di Modul 4 dan pergerakan barang di Modul 5, keduanya dipicu dari WO.

## Lingkup

| Masuk ke M3 | Keluar dari M3 |
|---|---|
| Detail task card di WO, penarikan Check Pack & task ke WO, NRC, relasi WO–Check Pack (dari Modul 2) | OTA Record → Modul 1 (EC) |
| Ad-hoc Task Card + MDDR | CRS (Menu 12–14) → Workshop; pesawat memakai **RTS** |
| Material Required per task card, Book/RQ | Task Card Aktif & Panel Eksekusi lintas WO (dihapus) |
| Cetak WO, task card, Control Sheet, RTS | Form Material Request (diganti Book → MR) |
| | Component Transaction (Scheduled) → Modul 4 |

## Menu (sidebar final)

| Menu | Isi | Catatan |
|---|---|---|
| Work Order List | Filter status, tab Perlu Tindakan, indikator MDDR open & Pending Install, cetak/ekspor | [[M3 Work Order]] |
| Form WO (buat/ubah) | Registrasi, Asal WO, TSN/CSN dari sektor AFML, pemilih Check Pack/task/DMI | [[M3 Work Order#Buat WO]] |
| Detail WO | Header & aksi per status, Task Card Execution List, tab Check Pack, Temuan, Riwayat Status | [[M3 Task Card di WO]] |
| Material Request List | Lintas WO, hanya lihat | [[M3 Material Tool & Part]] |
| Report | Report WO, Material Required, Material Issued | |
| Work Order Number Setup | Bisa pindah ke master format nomor global (C17) | [[Isu Harmonisasi Lintas Modul]] |

Nomor menu Design Brief v2: Menu 1–10 di WO Management; Menu 11 pindah ke EC; Menu 12–14 (CRS) pindah ke Workshop.

## Lima keputusan yang paling mengubah desain

1. **Close WO menjadi batas material**: Pending Install WO harus nol; return consumable ditutup saat WO Closed (K1, LM-06).
2. **Penggantian komponen dicatat di Modul 4**: Removal dan Installation dua transaksi terpisah, otomatis Scheduled karena WO terisi (CT-01, CT-02).
3. **Temuan punya dua jalur**: NRC untuk temuan yang diselesaikan di WO; Ad-hoc task card dengan MDDR untuk yang tidak bisa. Task card tidak bisa di-defer ke DMI (B-30, B-54–B-60).
4. **DMI dikerjakan sebagai baris task card** dan ditutup saat WO Close (B-63, B-64).
5. **RII butuh dua orang dan dua stamp**: pelaksana dan inspector RII berbeda (K4, MP B737 bab 2.2).

## Catatan modul

- [[M3 Work Order]] — status, aturan per tahap, cetak
- [[M3 Task Card di WO]] — jenis, struktur, status, closing, RII
- [[M3 Temuan NRC Ad-hoc MDDR]]
- [[M3 Material Tool & Part]] — Material Required, Pending Install/RTS, tool, robbed/swap
- [[M3 Integrasi & DMI]] — DMI, CML, AFML, data masuk/keluar
- [[M3 Decision Register]] · [[M3 Open Questions]]

## Aktor

PPC Staff, Chief PPC & Engineering, Engineer (di-sign-in), Mechanic, Inspector RII, Chief Inspector, Storeman (M5), Director of Maintenance, Technical Record (M4). Rincian peran: [[Organisasi & Aktor#Aktor per modul Yahya]].

## Langkah berikutnya

1. Tindak lanjuti 29 komentar *wajib diperbaiki* review hi-fi 1 Nov, terutama: Asal WO dan pemilih DMI di Form WO, tombol aksi per status, popup Close WO (Pending Install, DMI, tool), hapus CRS/OTA/Task Card Active/Form MR dari sidebar.
2. Bawa 15 pertanyaan prioritas tinggi ke Rimbun Air ([[M3 Open Questions]]).
3. Putuskan 5 butir internal M2–M3 bersama butir 123–133 [[M2 Open Questions]].
4. Pindahkan frame Task Card dari page Figma Modul 2 ke page Production & Execution.
