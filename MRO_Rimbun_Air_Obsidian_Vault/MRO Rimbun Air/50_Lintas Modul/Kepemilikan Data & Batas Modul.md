---
tipe: lintas
modul: lintas
diperbarui: 2026-11-11
tags: [lintas]
aliases: [Data Ownership, Batas Modul, Siapa Pegang Apa]
---
# Kepemilikan Data & Batas Modul

Prinsip: **satu data, satu penulis**. Modul lain hanya membaca atau menautkan. Tabel ini menjawab "data X dicatat di modul mana?" dan menjadi rujukan saat ERD dan API disusun.

| Data / proses | Penulis (pemilik) | Pembaca | Dasar |
|---|---|---|---|
| Pesawat, konfigurasi (NHA/NLA), PN Master, UOM & konversi | M1 | Semua | REQ; K5-07 |
| Tipe pesawat (Aircraft Type Profile) | **M2** (input); struktur varian dibahas dengan M1 | M1, M4, SSG | M2 no 19; LX-09 |
| Employee, lisensi, tanda tangan & stempel, base kerja | M1 | SSG, M3, M4 | PRD SSG |
| Akun, role, permission, katalog scope, Company Authorization, toggle | **SSG** (usulan; tunggu P01) | Semua | D1–D8 |
| AD/SB/SL, EO, status compliance | M1 | M2 (forecast), M3 | M2 no 1, 2 |
| Non-routine Task (menu Ad-hoc) | M1 | M2 (read-only), M3 | M2 no 10 |
| LLP, OC/CM (perhitungan umur) | M1 | M2, M4 | M2 no 48 |
| OTA | M1 (klien 19 Okt) vs SSG (PRD) | M3, M4 | LX-03 |
| Maintenance Program, Task Library (satu-satunya master task card), Check Type, Check Pack | **M2** | M3 | M2 no 4 |
| **Hard Time** (batas per PN, sisa umur per SN) | **M2** | M1, M4 | M2 no 46 |
| Forecast, STE, Out of Phase | **M2** | M3 | M2 SM2 |
| Master format nomor dokumen | M2 (sementara) → SSG-10 (usulan) | Semua | C17; LX-02 |
| Work Order, eksekusi task card, NRC, Ad-hoc + MDDR, Material Required, Book/MR | **M3** | M2 (last done), M4 (DMI closed), M5 | M3 Overview |
| Last done task MP | Dihitung M2 dari closing task card M3 | M2 | M2 no 58 |
| Halaman AFML, jam & cycle pesawat per sektor, koreksi flight log | **M4** | M1 (jam), M2 (forecast), M3 (TSN/CSN WO) | AF-04 |
| Defect, DMI (siklus hidup penuh), DMI Extension, AOG/Serviceable, Fleet Status | **M4** | M2 (forecast DMI), M3 (baris DMI di WO) | Keputusan 8 Okt |
| Transaksi pasang-lepas komponen (scheduled & unscheduled), robbed, swap | **M4** (penulis tunggal) | M1 (konfigurasi), M3 (menautkan), M5, M6 | Keputusan 8 Okt; K5-04 |
| Fluid (oli, hydraulic, fuel) | **M4** (input di AFML) | — | FL-02 |
| Reliability & repetitive | **M4** (hitung) | Engineering | M4 SM5 |
| RQ (request part) | **M4** | M3 (RQ dari WO), M6 | Keputusan 9 Okt |
| RFQ, order (PO, RO, EXO, loan, rental, warranty), core return | M6 | M4 (status order per item) | Keputusan 9 Okt |
| Issue, receiving, Pending Install/RTS, Tool Loan, scrap, stok | M5 | M3, M4 | CT-06; M2 no 49 |
| CRS (release dari shop) | M9 Workshop | — | B-02 |
| CML | **M4** | M2 (forecast, menunggu) | CML-08 |

## Batas yang sering tertukar

- **Task card**: master di M2 (Task Library); eksekusi dan cetak di M3. Tidak ada daftar task card lintas WO.
- **Komponen di task card**: tidak ada; lepas-pasang selalu lewat Component Transaction M4 (dibuka dari baris task card).
- **DMI di WO**: DMI tetap milik M4; M3 hanya membuat baris task card bersumber DMI dan mengirim "Closed by WO".
- **Status pesawat**: M1 (diubah manual) ≠ Fleet Status M4 (dari declaration).
- **Hard Time vs LLP**: HT di M2; LLP & OC/CM di M1.
- **Scrap**: dicatat M5; menghentikan hitungan HT/LLP, bukan tindakan HT.
