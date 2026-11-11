---
tipe: alur
modul: M4
diperbarui: 2026-11-11
sumber:
  - claude/Flow_Detail_Modul4_per_Submodul_Menu_3Nov.md
  - claude/Keputusan_AFML_Modul4_4Nov.md
  - claude/Konfirmasi_Modul4_5Nov.md
tags: [m4, lintas]
aliases: [Status Objek M4, Integrasi Modul 4]
---
# M4 Status Objek & Integrasi

Tabel ini adalah versi Flow Detail 3 Nov yang **sudah dikoreksi** keputusan 4–6 Nov. Kolom **Koreksi** menandai baris yang berubah.

## Status per objek

| Objek | Status | Pemicu | Catatan | Koreksi |
|---|---|---|---|---|
| Halaman AFML | Draft, **Waiting TR**, Closed, Void | Engineer submit; TR close/void | Closed hanya dikoreksi lewat Correct Flight Log; tidak ada panel Sync per tujuan | AF-09, AF-04 |
| Sektor AFML | TSN/CSN sementara, lalu terkunci | Simpan; halaman Closed | Brought forward dari sektor terakhir halaman non-void sebelumnya | AF-03 |
| Koreksi flight log | Pending, Applied | Dicatat TR; halaman tujuan Closed | Selisih dibawa ke halaman berikutnya | K5-08 (baru) |
| Defect | **Discrepancy** (belum pilih jalur) → Closed (Rectified, Deferred to DMI, Transferred CML, AOG Declared) | Jalur dipilih di 2.1 | Tidak ada Open | K5-03, AF-11 |
| DMI | Open, Extended, Closed | Deferred; Extension Approved; manual atau lewat WO | Limit Type tanggal/FH/FC; Monitor Request wajib | K6-03, K6-04 |
| DMI Extension | Draft, Submitted, Approved, Rejected | Chief LM ajukan; CI lalu DirOps | Sekali per DMI | — |
| Declaration | AOG, Serviceable; dokumen Draft, Printed, Signed Uploaded | Engineer in Charge dari defect | Terpisah dari status pesawat M1 | — |
| Component Transaction | Remove, Install, Robbed, **Swap**; Scheduled/Unscheduled; status kirim M1, M5, M6 + Resend | Engineer mencatat; Scheduled bila WO terisi | Swap proses sendiri | K5-04, AF-04 |
| Part ber-SN di gudang | Pending Install, Pending RTS | Issue gudang; removal | Pending RTS tutup saat diterima; Pending Install berbatas Close WO | — |
| RQ | Draft, Open, Revision, Approved, Rejected; item Open, Order, Closed | Submit; approval berurutan; order & penerimaan di M6 | Keterangan pemenuhan di bawah badge, tanpa status baru | K5-06 |
| CML | Open, Closed | Input / Transfer to CML; closing tanpa approval | Penutup berotorisasi aktif | — |
| PN di Reliability | Normal, Alert 1, Alert 2, Alert 3 | Rate bulanan melewati alert level | — | — |

## Aliran data (22)

| Data | Dari | Ke | Pemicu | Status | Acuan |
|---|---|---|---|---|---|
| Jam & cycle pesawat per sektor | M4 AFML | M1 | Closing halaman | Final | AFR-03, LM-10, AF-04 |
| Jam & cycle komponen terpasang | M4 (closing) | M1 | Closing, per sektor | Usulan | FQ-02, FQ-03, AF-06 |
| Pemicu hitung ulang sisa task & HT | M4 (closing) | M2 | Closing | Final (M2 no 55); mekanisme Usulan | FQ-04 |
| Koreksi jam & cycle | M4 Correct Flight Log | M1, M2 | Halaman tujuan Closed (Applied) | Final (M1); Usulan (M2) | LM-11, K5-08 |
| PN oli & hydraulic yang di-issue **ke WO** | M5 | M4 AFML | Issue ke WO | Final | AFR-12, K5-09 |
| Saldo oli per registrasi | — | — | — | **Tidak dibuat** | AF-05, FU-02 |
| TSN/CSN sektor untuk form WO | M4 AFML | M3 | Ambil dari AFML | Final (sektor); Usulan (WO antar penerbangan) | LM-10, WQ-05 |
| DMI open sebagai sumber forecast | M4 | M2 | DMI Open | Final; Limit Type FH/FC perlu diselaraskan (LX-01) | M4-26, K6-04 |
| DMI ke WO dan Closed by WO | M4 ↔ M3 | Dua arah | DMI dipilih di form WO; WO Close dengan konfirmasi | Final (prinsip); Usulan (konfirmasi) | M4-26, Q26-05 |
| Item MDDR yang belum selesai | M3 | M4 (defect AFML) | Keluar hangar; ditulis manual | Final | M4-15 |
| WO sebagai dasar Scheduled | M3 | M4 Component Transaction | Nomor WO diisi | Final | CT-02 |
| Konfigurasi & umur part | M4 Component Transaction | M1 | Removal, Installation, Robbed, Swap | Final | CT-04, CT-07 |
| Pending RTS dari removal | M4 | M5 | Removal (S/U/S) | Final | CT-06, CT-07 |
| Part di-issue untuk dipasang | M5 | M4 Installation | Issue membuka Pending Install | Final | CT-06, CT-09 |
| Leg type (aircraft / receiving store) | M4 Component Transaction | M6 | Transaksi per PN & SN | Final | Konfirmasi PM 30 Okt |
| Core exchange & RO part U/S | M5, M6 | Vendor | Dipicu Procurement / Material Logistics, tanpa RQ | Final | P-01 |
| Penanda PN (OC/CM, wheel assy, sub-major assy, kategori, oli); QPA per tipe varian | M1 PN Master | M4 | Master | Final; kategori part perlu konfirmasi | LM-01–LM-03, REL-07 |
| UOM | M1 PN Master | M4 RQ (read-only) | Master | Final | K5-07 |
| MTBUR Worldwide per PN | M1 PN Master | M4 Reliability | Master | Usulan | RL-05 |
| Data pesawat untuk report (MSN, delivery, manufacture, tipe varian) | M1 | M4 Reliability | Master | Final | Laporan hal. 6 |
| Hard Time (TBO) | M2 | M4, M1 | Master | Final | LM-04, LM-05 |
| Stamp, otorisasi, qualification | M1 Employee Master (+ SSG checkAuthority) | M4 | Pilih engineer, tanda tangan, penutup | Final | AFR-16, M4-16, M4-18, CML-04 |
| RQ, order, tanggal kedatangan | M4 ↔ M6 | Dua arah | RQ Approved → RFQ; order kembali ke RQ & DMI Extension | Final | RQ-01, RQ-20, P-03 |

Status pesawat di M1 **tidak** menerima data dari declaration M4 (M4-19). CML open sebagai sumber forecast M2 masih Menunggu (CML-08).
