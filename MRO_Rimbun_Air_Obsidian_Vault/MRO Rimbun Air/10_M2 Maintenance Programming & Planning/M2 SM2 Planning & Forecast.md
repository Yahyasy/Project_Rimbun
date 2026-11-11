---
tipe: submodul
modul: M2
diperbarui: 2026-11-11
sumber:
  - claude/Decision_Log_Modul2_9Nov.md
  - claude/Review_Desain_Modul2_Setelah_Revisi_8Nov.md
tags: [m2, perlu-update]
aliases: [Forecast, STE, Planning & Forecasting, Maintenance Planning & Forecast]
---
# M2 SM2 Planning & Forecast

Forecast membaca DMI dari Modul 4, dihitung ulang setiap AFML di-close, dan bisa langsung dibuat menjadi WO. STE tidak dihitung sistem: sistem mencatat STE per kejadian beserta dokumen fisiknya.

## Konsep hitung

| Konsep | Aturan | Status |
|---|---|---|
| Batas yang berlaku | Threshold sebelum pelaksanaan pertama, interval sesudahnya | Final (29) |
| WCF | *Whichever Comes First* — due terdekat dari FH, FC, atau kalender | Final |
| Data umur | TSN dan CSN diperbarui **per sektor**; semua data "as of" tanggal closing AFML terakhir | Final (56) |
| Hitung ulang | Setiap AFML di-close Technical Record: jam terbang, umur komponen, LLP, HT, DMI ikut berubah. Salah input dikoreksi pada penerbangan berikutnya, bukan diedit | Final (55) |
| Last done | Diperbarui otomatis setelah closing di WO Modul 3; status AD/EO di Modul 1. Tidak diinput manual | Final (58); pemicu task card vs WO Menunggu (105) |
| Status baku | **Safe, Approaching, Due, Overdue** | Final (desain) |
| Grup forecast | MP Task, AD/SB & EO, HT, DMI, CML | Final kecuali CML (Menunggu 103); LLP & OC/CM read-only Menunggu (102); Daily/Weekly check tidak di-forecast (Menunggu 104) |

## Forecast Dashboard

Layar 10.1.

| Aturan | Status |
|---|---|
| Kolom Interval/Threshold sebelum Remaining, dengan penanda batas berlaku (mis. "Threshold · 20.000 FC") | Final (51) |
| Filter menambah grup AD/SB dan HT; usulan menjadi satu filter **Grup Maintenance** multi-select + rentang WCF Due | Final (52); satu filter Usulan (123) |
| DMI masuk berdasarkan due date (tanpa FH/FC); sisa hari; perpanjangan lewat DMI Extension Modul 4 menghasilkan due date baru | Final (53, 54) — `#perlu-update`: Modul 4 K6-04 (6 Nov) menetapkan Limit Type DMI tanggal/FH/FC, lihat LX-01 di [[Isu Harmonisasi Lintas Modul]] |
| **Buat WO** dari forecast atau aksi per DMI; beberapa DMI satu registrasi boleh satu WO; DMI ikut tertutup saat WO Close | Final (53); cara tutup Menunggu (106) |
| Buat WO **hanya untuk baris DMI dan HT**; membuka form WO Modul 3 terisi, bertanda asal planning; item yang sudah ber-WO tidak bisa dipilih | Final (53, 57; desain) |
| Removal Scheduled = transaksi dari WO hasil planning (WO wajib diisi); tanpa WO = Unscheduled | Final (57); WO DMI Menunggu (107) |
| Kolom: Group, TSN/CSN, Interval/Threshold (T/I), WCF Due, Remaining Due (satuan batasnya), Flags (Notified, STE active, nomor WO) | Final (desain) |

**Perbaikan desain 8 Nov:** subtitle masih "AMP", tanggal as of belum ada di header, filter masih terpisah, rentang WCF Due belum ada, tombol Rekomendasi Prioritas dan Buat WO di header belum ada, Create WO masih muncul di baris MP Task, checkbox baris ber-WO masih aktif, data contoh tidak konsisten.

## Due List dan Detail Due

Layar 11.1 Due List, 11.2 Detail Due (tab Nilai Due, Remaining Due).

| Aturan | Status |
|---|---|
| Filter periode forecast (tanggal mulai–akhir) di atas tabel; berlaku juga untuk ekspor | Final (59) |
| Overdue paling atas, lalu jatuh tempo terdekat | Final (60); Overdue di luar periode tetap tampil Menunggu (108) |
| Tombol **Tambah STE** di bawah section WCF Calculation & Remaining; tombol Submit STE di header dihapus | Final (61) |
| Submit STE memperbarui daftar STE dan kolom Active STE di forecast | Final (62) |
| Detail Due menampilkan Last Done dari closing task card (tanggal + TSN/CSN), WO terakhir, batas berlaku, waktu hitung; Estimated Due, WCF Due, Remaining Due; due asli dan due setelah STE berdampingan | Final (desain) |
| Baris DMI/CML: due read-only dari Modul 4, tanpa Add STE. Baris HT: Buat WO dan Lihat Hard Time | Usulan; belum didesain |

**Perbaikan desain 8 Nov:** **Due List belum direvisi sama sekali**; Detail Due versi lama (tombol Submit STE) harus dihapus.

## WCF Priority

Layar 12.1. Beberapa task dipilih lalu **Create Check Pack from Selection**. Perbaikan: urutkan berdasarkan WCF Due, tampilkan nomor Check Pack (bukan hanya Available/In Pack), hapus status "Due Soon".

## STE (Short Term Escalation)

Layar 13.1 List, 13.2 Form Pengajuan, 13.3 Pengaturan Role, 13.4 Detail & Approval (tab Approval, HIRA, DAAO & Closure, Dokumen STE).

| Aturan | Status |
|---|---|
| Nomor STE dari master format nomor | Final (63) |
| STE **tidak dihitung** sistem; dicatat per kejadian. Banner dan blok toleransi dihapus. Validasi task dilarang STE dan STE ganda tetap ada | Final (64) |
| Jenis STE: **Check Pack, Defect, Task Card**; field subjek muncul kondisional di bawah jenis | Final (65); subjek per jenis Menunggu (110) |
| Lampiran **PDF** dokumen STE fisik; due setelah ekstensi diisi manual dari dokumen fisik | Final (66); wajib sebelum approve Menunggu (112) |
| HIRA tidak wajib; bila kosong "HIRA tidak dilampirkan" | Final (67) |
| Stempel dan tanda tangan tidak di-upload; tab Form & Signatures menjadi tab Dokumen STE | Final (68) |
| Approval STE lewat tombol di sistem; Chief Inspector menentukan perlu DAAO lewat toggle; tombol aktif mengikuti toggle | Menunggu (109) |
| STE Defect tidak mencakup DMI (DMI lewat DMI Extension Modul 4); subjek Defect memilih NRC/MDDR dari Modul 3 | Menunggu (111, 126) |
| Pengisi HIRA dan penutup STE | Menunggu (113) |
| Arti "STE hanya sekali" | Menunggu (114) |
| Pengaturan Role STE (13.3) | Usulan pindah ke SSG-06 ([[SSG Sitemap & Menu]]) |

**Perbaikan desain 8 Nov:** field subjek per jenis belum ada, Regulatory Basis masih tampil, satuan ekstensi masih date picker (harus FH/FC/Hari), upload masih PNG (harus PDF), subtitle "Short Term Extension" (harus Escalation), baris Defect dobel di Pengaturan Role, Approve dan Forward to DAAO aktif bersamaan.

## Notifikasi Due

Layar 14.1. Ambang tetap **10% dari batas yang berlaku**; daftar role penerima dengan toggle aktif. Kanal notifikasi Menunggu (118). Usulan pindah ke SSG-11.

## Report Center

Layar 15.1–15.4 dengan pola **parameter → Show → pratinjau → Export**.

| Laporan | Isi | Perbaikan |
|---|---|---|
| LDND | ATA 4 digit, batas berlaku | Tambah WO terakhir, Remaining Due, STE aktif; status pakai 4 status baku |
| SB/AD | Jenis, nomor dokumen, status compliance, task terkait, next due, sisa | Tambah tombol Show dan kolom Last Done |
| HT | Posisi/"In store", P/N, S/N, tindakan, batas, TSN/CSN, sisa, due, as of | Sesuai |
| Check-pack | Tanpa WO; threshold/interval, effectivity, jumlah task, total man-hours, "Also in Other Pack" | Sesuai |

Format ekspor (PDF/Excel) Menunggu (118).
