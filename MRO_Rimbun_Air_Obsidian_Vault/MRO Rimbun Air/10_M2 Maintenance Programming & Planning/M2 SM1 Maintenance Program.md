---
tipe: submodul
modul: M2
diperbarui: 2026-11-11
sumber:
  - claude/Decision_Log_Modul2_9Nov.md
  - claude/Review_Desain_Modul2_Setelah_Revisi_8Nov.md
tags: [m2]
aliases: [Submodul Maintenance Program, AMP, Task Library]
---
# M2 SM1 Maintenance Program

Kondisi akhir per menu. Angka dalam kurung merujuk nomor baris [[M2 Decision Register]] (keputusan) atau [[M2 Open Questions]] (usulan). Status desain mengikuti review 8 Nov.

## Navigasi

Sidebar: **Aircraft Type → Maintenance Program → Check Type → Task Library → Hard Time → Format Nomor Dokumen** (14). Label "AMP Dashboard" diganti "Maintenance Program" di semua label, judul, breadcrumb, tombol, toast (15). Desain 8 Nov: urutan masih berbeda antar frame dan label "AMP" masih tersisa.

## Aircraft Type

Layar 1.1 List, 1.2 Form, 1.3 Detail.

| Aturan | Status |
|---|---|
| Tipe pesawat diinput di Modul 2 lewat Aircraft Type Profile | Final (19; konfirmasi PM 8 Nov) |
| Isi: Type Code, Type Name, Manufacturer, CASR 121/135, Kode AMP (teks, opsional) | Final (18) |
| FEC dan Basis STE dihapus dari tipe | Final (16, 17) |
| Tipe tidak bisa dihapus selama masih punya MP; tombol hapus nonaktif dengan tooltip | Final (rancangan awal) |
| Tipe pesawat tidak punya status | Final — desain masih menampilkan popup "set to active status" |
| Hubungan Kode AMP dengan MP Number | Menunggu (78) |
| CASR tetap di Aircraft Type; badge PART 121 di header MP dihapus | Menunggu (84) |

## Maintenance Program

Layar 3.1 Daftar MP, 4.1 Form & Detail MP (Info Revisi, Tab Aircraft, Approval Internal), 4.2 Riwayat Revisi.

| Aturan | Status |
|---|---|
| **MP Number** adalah identitas utama, kolom pertama setelah nomor, sama untuk semua revisi; terkunci setelah simpan pertama bersama tipe dan No. Revisi | Final (20, 21) |
| Rantai versi = MP Number yang sama, diurutkan Issue dan Revisi; field Supersedes tidak dipakai | Final (21) |
| Kategori operasional dihapus | Final (22) |
| Satu MP Active per tipe pesawat; revisi dibuat lewat **Copy MP** (task dan interval ikut tersalin ke Draft baru) | Final (rancangan awal) |
| Approval: PPC Staff mengajukan, **Chief PPC** menyetujui/menolak (reject wajib catatan). Director of Maintenance tidak tampil | Final (23) |
| Approve → MP langsung **Active**, versi lama **Archived**, forecast dihitung ulang | Final (desain 8 Nov sesuai) |
| Submisi DGCA di luar sistem; tab DGCA-PAI dihapus | Final (24) |
| Aircraft effectivity mengacu ke MP yang menempel di pesawat (Tab Aircraft: registrasi, MSN, MP Start Date) | Final (25); tempat relasi Menunggu (79) |
| MP Start Date menjadi awal forecast; daftar Tab Aircraft menjadi pilihan effectivity task dan Check Pack | Final (desain) |
| Menu aksi: Detail, Ubah (Draft saja), Copy MP (Active saja) | Usulan (review 8 Nov) |
| MP aktif sejak disetujui atau sejak Effective Date | Menunggu (81) |
| Submit diblokir bila task masih 0 | Menunggu (82) |
| Tambah/lepas pesawat dari MP Active tanpa revisi | Menunggu (80) |
| No. Persetujuan DGCA (opsional) | Menunggu (83) |

## Check Type

Layar 2.1 List, 2.2 Form, 2.3 Detail.

| Aturan | Status |
|---|---|
| Check Type hanya **data referensi**, tidak terhubung ke task maupun Check Pack | Final (27) |
| Check code, check name, sequence number dihapus dari form task | Final (26) |
| Tipe pesawat wajib dipilih dulu; nama dan kode wajib; interval dasar dan Work Area Count (khusus DHC-6) opsional | Final (desain) |
| Kartu ringkasan "Active AMP Revision" dan satuan "CH" dihapus | Usulan (review 8 Nov) |

## Task Library dan Form Task

Layar 5.1 Task Library, 6.1 Task Detail, 6.2 Form Tambah/Ubah/Copy, 6.3 Pratinjau Dokumen.

**Isi task (lima bagian di form):**

| Bagian | Field dan aturan | Status |
|---|---|---|
| Identitas & Parameter Tugas | ATA dropdown 4 digit chapter-section dengan pencarian (37); Task Type pilihan (40; daftar Menunggu 87); Zone multi (bertumpuk) dan Access Panel multi (dipisah koma), keduanya dropdown master (34; sumber master Menunggu 88); Skill Group kode + deskripsi (36); Jumlah Personel dan Man-hours per task card, mis. 0.50 = 30 menit, tanpa total (35); referensi task maksimal 3 baris (33) | Final |
| Pengaturan Interval/Threshold | Baris berulang dengan jenis batas **Threshold** atau **Interval**; threshold dihitung lebih dulu, interval berlaku setelah threshold tercapai (28, 29). Basis FH, FC, kalender (angka + satuan hari/bulan/tahun dengan aritmetika kalender) dan field tanggal (30, 31) | Final; arti field tanggal Menunggu (89); titik nol threshold Menunggu (90) |
| Task Card Number & PDF | Nomor task card, deskripsi (dipindah ke sini, 32), work description per baris dengan lampiran PDF | Final (32); PDF wajib per baris Menunggu (94) |
| Material & Tool | Task Part: PN dari PN Master + qty + replacement code **100%** (wajib diganti setiap dikerjakan) atau **OC** (38). Tool beserta qty; istilah "tool", status kalibrasi di Modul 5; tanpa SN/transaksi (43). Part 100% otomatis masuk Material Required WO | Final |
| Effectivity | Pilih **salah satu**: pesawat (dari Tab Aircraft MP) atau komponen (PN lalu SN multi) (41) | Final; due komponen dari umur per SN Menunggu (91); modal Add Component belum didesain |

**Aturan lain**

| Aturan | Status |
|---|---|
| Setiap task tergabung di MP (39); task MP wajib milik MP, task EO merujuk MP, non-routine tanpa MP | Final (39); rincian Menunggu (92) |
| Checklist pindah ke Task Library sebagai daftar work description (42) | Final; bentuk Menunggu (93) |
| Task asal **EO** dan **Non-routine** dibuat di Modul 1, tampil read-only (badge asal, banner "managed in Module 1"), tanpa Edit dan Mark as Out of Phase; Copy membuat task MP baru yang bisa diedit | Final (2, 10); tampil read-only Usulan (128) |
| Add New Task nonaktif bila MP bukan Draft; Edit nonaktif di MP Active; Mark as Out of Phase nonaktif di MP Active | Final (desain) |
| Copy Task mengosongkan nomor task card; PDF tidak ikut tersalin | Usulan (95) |
| STE Prohibited tampil dengan alasan; terkunci otomatis untuk AD/CDCCL | Usulan (desain) |
| Arti "RII harus mencakup 2 engineer" | Menunggu (97) |
| FEC Category di task | Menunggu (86) |

**Perbaikan desain 8 Nov:** ATA masih 2 digit di Task Library/Task Detail; kolom Nomor Dokumen, MP, Lampiran dan tombol Import di header belum ada; penanda read-only dan empty state hasil filter belum ada; Personel dan Deskripsi belum bertanda wajib.

## Import Task

Layar 7.1 Upload, 7.2 Preview & Validasi.

| Aturan | Status |
|---|---|
| Import membaca Excel dan mencocokkan dengan PDF yang disertakan; template mengikuti field baru (multi-sheet, kunci nomor task card) | Final (44); bentuk template Usulan |
| Validasi per sel: format/master tidak cocok, data ganda, wajib kosong | Final (45) |
| Simpan baris valid saja, baris error bisa diunduh | Menunggu (96) — desain sudah begini, brief belum |
| Preview: filter Valid/Error, edit inline, buka baris, penanda sel error | Belum didesain |

## Hard Time

Layar 26.1 List, 26.2 Form, 26.3 Detail & sisa umur per SN.

| Aturan | Status |
|---|---|
| Menu Hard Time di MP sebagai acuan **TBO** bagi Modul 1 dan Component Transaction Modul 4; HT report keluar dari Modul 1. Task MP ber-effectivity komponen menjadi hard time komponen | Final (46) |
| Expendable serialized berumur terbatas (mis. baterai) ikut Hard Time | Final (47) |
| LLP dan OC/CM dihitung di Modul 1; M2 hanya memegang batas HT dan sisa umur HT, membaca TSN/CSN per SN dari Modul 1 | Final (48) |
| Komponen yang di-scrap (dicatat di Modul 5) berhenti dihitung; scrap bukan tindakan HT | Final (49) |
| PN terkunci setelah simpan; baris HT: tindakan, acuan hitung, batas FH/FC/kalender, batas pertama, task MP terkait, referensi | Final (desain) |
| Sisa umur per SN dengan posisi atau "In store", tanggal as of = closing AFML terakhir; Record Last Action (tanggal, TSN, CSN, referensi ARC/Form 1/WO); label "Needs last action" | Final (desain) |
| Bentuk menu: master per PN dan tipe pesawat, boleh beberapa baris per PN; HT Report di Report Center | Menunggu (99) |
| Pemicu reset HT setelah overhaul/test | Menunggu (100, HT-02) |
| Shelf life komponen di gudang | Menunggu (101) |

Perbaikan desain: satuan kalender masih "Years" (harus pilih hari/bulan/tahun), popup simpan salah teks, tabel keluar frame, contoh A320neo.

## Format Nomor Dokumen

Layar 27.1 List, 27.2 Form.

| Aturan | Status |
|---|---|
| Master format nomor untuk dokumen bernomor otomatis; dikonfigurasi admin, tidak ditanam di kode (50) | Final |
| Isi: prefix, format tahun dan bulan, panjang nomor urut, pemisah, reset, pratinjau langsung; format berlaku untuk dokumen berikutnya | Final (desain) |
| Saat ini mencakup Check Pack dan STE | Final |
| Berlaku per modul atau global; lokasi master | Menunggu (119, C17) — usulan SSG-10, lihat [[Isu Harmonisasi Lintas Modul]] |

Frame lama "Order Number Format" (order pengadaan) harus dihapus dari page.
