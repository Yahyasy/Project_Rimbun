---
tipe: register-keputusan
modul: M4
diperbarui: 2026-11-11
sumber:
  - claude/Keputusan_AFML_Modul4_4Nov.md
  - claude/Keputusan_Fluid_Consumption_Modul4_4Nov.md
  - claude/Konfirmasi_Modul4_5Nov.md
  - claude/Konfirmasi_DMI_Modul4_6Nov.md
  - claude/Flow_Detail_Modul4_per_Submodul_Menu_3Nov.md
tags: [m4]
aliases: [Keputusan M4, Decision Log Modul 4]
---
# M4 Decision Register

Urutan berlaku: keputusan **lebih baru menggantikan** yang lama. K5 (5 Nov) dan K6 (6 Nov) > AF dan FL (4 Nov) > Flow Detail (3 Nov) > insight review 22 Okt–2 Nov.

## 1. Keputusan lintas modul

| Tgl | Keputusan | Asal |
|---|---|---|
| 8 Okt | M4 penulis tunggal transaksi pasang-lepas komponen (M3 menautkan, M1 read-only); M4 pemegang siklus hidup DMI (forecast M2 hanya membaca); penomoran dokumen M4 mengikuti format form klien | Keputusan internal lintas modul |
| 9 Okt | RQ tetap di M4; Procurement memegang RFQ | Diskusi dengan PM Procurement |
| Okt | LLP & OC/CM di M1; HT master di M2, M1 menarik HT dari M2 | Usulan klien |
| — | ATA hanya 4 digit chapter-section | Klien |
| 30 Okt | Leg type per PN & SN dikirim ke M6; core exchange & RO part U/S dipicu Procurement/Material Logistics tanpa RQ | Konfirmasi PM |

## 2. Keputusan AFML (4 Nov)

| Kode | Keputusan | Menggantikan |
|---|---|---|
| AF-01 | Close berurutan per registrasi; halaman tertahan bila halaman sebelumnya (registrasi sama) belum Closed; registrasi lain tidak tertahan | Usulan di review 3 Nov |
| AF-02 | Closing satu per satu; **tidak ada Closing Harian** | FC3; Flow Detail A8 |
| AF-03 | Halaman Void tidak masuk daftar closing dan dilewati; brought forward dari halaman non-void sebelumnya | FC4 |
| AF-04 | Pembaruan ke M1, M5, M6 ada di Component Transaction (status M6 + Resend); AFML hanya sync jam & cycle pesawat ke M1, tanpa panel Sync per tujuan | FC5, FC6; Flow Detail A9 |
| AF-05 | AFML hanya membaca PN oli yang di-issue M5; pemakaian oli tidak dikirim balik ke M5 | AFR-05 (bagian oli) |
| AF-06 | Waktu penggantian komponen dari Event Date & Time Component Transaction; tidak ada field jam di tabel Component Change AFML; peringatan bila di tengah sektor | FQ-02 sebagian; Flow Detail A5 |
| AF-07 | Engine Parameter disertakan, seluruh field Master Field per tipe | AFR-08, AFR-24, Q28-08 |
| AF-08 | Flight Hour Report tampil jam:menit dan desimal; ekspor memuat keduanya | WQ-01 sebagian |
| AF-09 | Status setelah submit **Waiting TR**; setelahnya engineer tidak bisa mengubah; TR hanya Tab Flight Data | Q26-11, B-01, AFR-02, HDR-08 |
| AF-10 | DHC-6 tanpa contoh fisik; form mengikuti Master Field; tanpa frame khusus | Butir terbuka Master Field DHC-6 |
| AF-11 | AFML hanya mencatat discrepancy & rectification; jalur penyelesaian & isian DMI di Sub-modul 2 | Struktur AFML 4 Nov pagi |

## 3. Keputusan Fluid Consumption (4 Nov)

| Kode | Keputusan | Menggantikan |
|---|---|---|
| FL-01 | Tiga menu: 4.1 Fuel Uplift, 4.2 Oil Consumption, 4.3 Hydraulic Fluid Consumption | 4.1–4.5 lama; penamaan B-05 |
| FL-02 | Semua fluid diinput di AFML Tab Oil & Fuel; menu hanya daftar & hitungan; hanya halaman Closed | Flow Detail D1, D4; REL-21; AF-03 |
| FL-03 | Oil Consumption hanya di 4.2; tab Oil di 5.1 dihapus; tab 5.1: Utilization, Component, Non-Serialized, Defect & PIREP, Repetitive | REL-17, REL-21; Flow Detail D6, E6 |
| FL-04 | QT/FH per engine = oli ditambahkan ÷ FH sejak top-up sebelumnya, termasuk sektor top-up; hanya oli engine | REL-18, REL-19; WB-07, WB-08 |
| FL-05 | Fuel Uplift tanpa hitungan per baris; total uplift & burn per registrasi per periode; liter vs KG/LBS; remaining tidak divalidasi | AFR-14, AFR-15, AFR-23 |

## 4. Konfirmasi Modul 4 (5 Nov)

| Kode | Keputusan |
|---|---|
| K5-01 | Halaman Void boleh diubah lewat Correct Flight Log; nilai lama, baru, selisih tercatat sebagai koreksi |
| K5-02 | Wheel assy: outer sebagai induk "Wheel Assy / Outer", punya PN & SN |
| K5-03 | Entri dari AFML bernama **Discrepancy** di Defect & Deferred sampai jalur dipilih; "Deferred" hanya untuk yang masuk DMI |
| K5-04 | **Swap** proses tersendiri (bukan bagian Robbed), hanya antar pesawat; form pola sama dengan Robbed & Record Removal/Installation; menu baru 3.6 |
| K5-05 | Hydraulic QT/FH basis **FH**, sama dengan oli; basis cycle tidak dipakai |
| K5-06 | Status RQ tetap; pemenuhan sebagai keterangan di bawah badge (lihat [[M4 SM6 RQ]]) |
| K5-07 | Master UOM & UOM conversion di Modul 1; RQ hanya membaca UOM dari PN Master |
| K5-08 | Koreksi tidak mengubah AFML Closed; selisih dibawa ke halaman berikutnya (Corrected Hours/Cycle); status Pending → Applied |
| K5-09 | Oli & hydraulic di-issue ke WO, bukan ke registrasi; PN di Tab Oil & Fuel dari issue ke WO pesawat itu; satuan read-only |

## 5. Konfirmasi DMI (6 Nov)

| Kode | Keputusan |
|---|---|
| K6-01 | Nomor DMI dari master penomoran seperti desain (mis. `045/RAA/DMI/10/26`) |
| K6-02 | Intermediate Action RAA-TLM-007 belum dikelola sistem; tercetak kosong |
| K6-03 | Monitor Request wajib; DMI Open/Extended dengan Monitor Request Yes tampil di 2.4; yang No tetap di DMI List |
| K6-04 | Limit Type DMI: tanggal, flight hours, atau flight cycles (menjawab FQ-05) |

## 6. Keputusan dasar per keluarga kode (ringkas)

Keputusan rinci ada di dokumen insight; yang paling sering dirujuk:

| Kode | Keputusan |
|---|---|
| AFR-01, AFR-04 | Closing berurutan; TR hanya mengubah Flight Data |
| AFR-06, AFR-20 | Field AFML per tipe pesawat; sektor per leg (ATR 1, B737 ≤ 6) |
| LM-10, LM-11 | TSN/CSN per sektor dari halaman Closed; koreksi lewat penerbangan berikutnya |
| M4-24, M4-25 | Nomor defect halaman + item + urut 7 digit; tidak ada defect Open |
| M4-12, M4-13 | DMI Extension sekali per DMI, approval CI → DirOps |
| M4-17–M4-23 | AOG & Serviceable berpasangan, dari defect, cetak dengan status dokumen |
| M4-19 | Fleet Status terpisah dari status pesawat M1 |
| M4-26 | DMI open masuk forecast M2; bisa dibuat WO; Closed by WO |
| CT-01–CT-11 | Removal/Installation terpisah; Scheduled bila WO; reason tanpa grup; parent-child; Pending RTS/Install; robbed DoM; consumable tanpa CT |
| REL-02–REL-21 | Reliability per fleet tanpa arsip; rate, MTBUR, alert level 2,5 SD populasi 12 bulan; repetitive 3 bulan ATA 4 digit |
| RQ-01–RQ-23, P-01, P-03 | Struktur RQ; Open = menunggu approval; Approved → RFQ; RO tanpa RQ |
| CML-01–CML-07 | CML menu sendiri; halaman buku CML; cabin location master; closing tanpa approval |

## 7. Keputusan baru (setelah 11 Nov)

| Kode | Tgl | Sesi | Menu | Keputusan → dampak | Acuan |
|---|---|---|---|---|---|
| | | | | | |
