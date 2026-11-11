---
tipe: register-pertanyaan
modul: M2
diperbarui: 2026-11-11
sumber:
  - claude/Decision_Log_Modul2_9Nov.md
  - claude/Review_Desain_Modul2_Setelah_Revisi_8Nov.md
tags: [m2]
aliases: [Pertanyaan Terbuka M2, Konfirmasi Modul 2]
---
# M2 Open Questions

56 butir menunggu per 9 Nov: **41 untuk Rimbun Air, 4 untuk PM Modul 1, 11 internal Modul 2/3/4**. Usulan sementara dipakai di desain dengan label *Belum final*. Setelah dijawab: isi kolom Jawaban, ubah Status menjadi `Terjawab <tgl>`, lalu tambahkan keputusannya ke [[M2 Decision Register]].

Kolom **Sesi 9 Nov** = nomor pertanyaan persetujuan yang dibawa ke [[2026-11-09 Review Desain M2 Setelah Revisi]]; `lama` = pertanyaan lama yang masih terbuka dan dibawa bila waktu cukup.

## Untuk Rimbun Air (41)

| No | Menu | Pertanyaan | Usulan sementara | Sesi 9 Nov | Status | Jawaban |
|---|---|---|---|---|---|---|
| 78 | MP | MP Number sama dengan Kode AMP dan diinput manual? | Sama nilainya, input sekali manual | | Menunggu | |
| 79 | MP | Satu pesawat hanya satu MP? Relasi disimpan di mana? | Ya; di M2, Tab Pesawat detail MP | 7 | Menunggu | |
| 80 | MP | Tambah/lepas pesawat dari MP Active tanpa revisi? | Boleh lewat Tab Pesawat; perubahan tercatat | 6 | Menunggu | |
| 81 | MP | MP aktif sejak disetujui atau sejak Effective Date? | Active saat disetujui; Effective Date informasi dokumen (bila tidak, perlu status "terjadwal") | 4 | Menunggu | |
| 82 | MP | MP boleh diajukan tanpa task? | Submit diblokir bila task kosong | 5 | Menunggu | |
| 83 | MP | Perlu field No. Persetujuan DGCA? | Ya, opsional di Revision Information | 8 | Menunggu | |
| 84 | MP | CASR 121/135 tetap di Aircraft Type, badge PART 121 di header MP dihapus? | Ya untuk keduanya | | Menunggu | |
| 85 | MP | Persetujuan DoM di luar sistem perlu dicatat? | Tidak; cukup Chief PPC | | Menunggu | |
| 86 | Task Library | FEC Category di form task ikut dihapus? | Tetap opsional (5–9) tanpa toggle | lama | Menunggu | |
| 87 | Task Library | Daftar pilihan Task Type? | Kode MPD: LUB, SVC, OPC, FNC, VCK, GVI, DET, SDI, RST, DIS, OHC; Metode Inspeksi digabung | lama | Menunggu | |
| 88 | Task Library | Sumber master Skill Group, Zone, Access Panel? | Skill Group menggantikan Work Group; Zone & Access Panel per tipe lewat impor | lama | Menunggu | |
| 89 | Task Library | Untuk apa field tanggal di Interval/Threshold? | Batas tanggal tetap untuk task sekali jalan | | Menunggu | |
| 90 | Task Library | Titik nol threshold dihitung dari mana? | FH/FC sejak baru; kalender dari tanggal pembuatan pesawat/komponen | | Menunggu | |
| 91 | Task Library | Due task effectivity komponen dari umur komponen per SN? | Ya | | Menunggu | |
| 92 | Task Library | Semua task wajib milik MP? | Task MP wajib; EO merujuk MP; non-routine tanpa MP | | Menunggu | |
| 93 | Task Library | Task card pesawat cukup index + lampiran pabrikan, work description menggantikan Checklist? | Ya | | Menunggu | |
| 94 | Task Library | PDF wajib, dan di setiap baris work description? | Minimal satu per task asal MP; lainnya opsional | 1 | Menunggu | |
| 95 | Task Library | Saat Copy Task, PDF ikut tersalin? | Tidak; diunggah ulang (nama file terkait nomor baru) | 2 | Menunggu | |
| 96 | Import | Simpan baris valid saja? | Ya; baris error dilewati dan bisa diunduh | 3 | Menunggu | |
| 97 | Task Library | Arti "RII harus mencakup 2 engineer"? | Dua personel berbeda (pelaksana dan inspector RII) saat closing | lama | Menunggu | |
| 98 | Lintas | Nama resmi tiga konsep ad-hoc? | "Ad-hoc Task Card" (di WO); "Non-routine Task" (master M1) | | Menunggu | |
| 99 | Hard Time | Bentuk menu Hard Time dan letak HT Report? | Master per PN + tipe, beberapa baris per PN; HT Report di Report Center M2 | | Menunggu | |
| 100 | Hard Time | Pemicu reset HT setelah overhaul/test? | Closing WO dengan referensi ARC/Form 1 | lama | Menunggu | |
| 101 | Hard Time | Shelf life komponen di gudang ikut dihitung? | Tidak di fase ini | | Menunggu | |
| 102 | Forecast | Jatuh tempo LLP dan OC/CM dari M1 tampil di forecast? | Ya, grup read-only bila M1 menyediakan | | Menunggu | |
| 103 | Forecast | CML open masuk forecast? | Ya, grup CML; tanpa batas waktu di bawah | | Menunggu | |
| 104 | Forecast | Daily dan Weekly check di-forecast? | Tidak, tercatat di AFML | | Menunggu | |
| 105 | Forecast | Last done diperbarui saat task card Closed atau WO Closed? | Task card Closed, pakai tanggal/TSN/CSN task card | | Menunggu | |
| 106 | Forecast | Saat WO Close, DMI tertutup otomatis? | Sistem menawarkan, engineer mengonfirmasi | | Menunggu | |
| 107 | Forecast | Removal untuk defect di bawah WO DMI: Scheduled atau Unscheduled? | Unscheduled; Scheduled hanya WO dari planning | | Menunggu | |
| 108 | Due List | Overdue di luar periode tetap tampil? | Ya, teratas | | Menunggu | |
| 109 | STE | Approval STE lewat tombol sistem? Siapa menentukan perlu DAAO? | Ya; Chief Inspector lewat toggle | 10 | Menunggu | |
| 110 | STE | Subjek per jenis STE dan pengaju jenis Task Card? | Check Pack, NRC/MDDR, task card; pengaju PPC Staff | | Menunggu | |
| 111 | STE | STE jenis Defect mencakup DMI? | Tidak; DMI lewat DMI Extension M4 | lama | Menunggu | |
| 112 | STE | PDF wajib sebelum STE disetujui? | Ya | | Menunggu | |
| 113 | STE | Siapa mengisi HIRA dan menutup STE; apakah memakai sistem? | HIRA: Chief Inspector + Safety Manager; penutupan: Chief Maintenance atau Chief Inspector | 11 | Menunggu | |
| 114 | STE | "STE hanya sekali": per siklus jatuh tempo atau selama umur pesawat? | Belum ada usulan | lama | Menunggu | |
| 115 | Check Pack | Threshold/interval Check Pack manual atau dari task? | Manual | 12 | Menunggu | |
| 116 | Check Pack | Effectivity satu atau beberapa pesawat? | Beberapa pesawat dari satu MP | | Menunggu | |
| 117 | Out of Phase | Deteksi otomatis Out of Phase? | Task yang tidak masuk Check Pack mana pun | 9 | Menunggu | |
| 118 | Lain-lain | Kanal notifikasi, format ekspor, rumus rata-rata utilisasi untuk Estimated Due | Belum ada usulan | lama | Menunggu | |

## Untuk PM Modul 1 (4)

| No | Menu | Pertanyaan | Usulan sementara | Sesi 9 Nov | Status | Jawaban |
|---|---|---|---|---|---|---|
| 119 | Format nomor | Master format penomoran per modul atau global; dokumen apa saja? | Global lintas modul; sementara di M2 (lihat SSG-10) | 13 | Menunggu | |
| 120 | Task Library | Task EO disimpan di tabel task M2 dengan asal EO, dibuat dari layar EO M1? | Ya, satu tempat simpan, read-only di Task Library | | Menunggu | |
| 121 | Forecast, HT | Tanggal pembuatan pesawat dan TSN/CSN per SN tersedia? | Dibutuhkan, dibaca per sektor | | Menunggu | |
| 122 | Task Library | Effectivity komponen tertaut ke ID komponen, termasuk sub-major assembly? | Ya; M2 simpan ID komponen, SN dibaca dari M1 | | Menunggu | |

## Internal Modul 2, 3, 4 (11) — bisa diputuskan Yahya

| No | Menu | Pertanyaan | Usulan | Status | Keputusan |
|---|---|---|---|---|---|
| 123 | Forecast | Satu filter Grup Maintenance menggantikan filter terpisah? | Ya | Menunggu | |
| 124 | Check Pack | Detail Check Pack menampilkan WO yang memakainya? | Tidak | Menunggu | |
| 125 | Task card di WO | Task Card Detail di WO dikelola M2 atau M3? | M3; M2 hanya master | Menunggu | |
| 126 | NRC | Masih perlu menu NRC di M2? | Dihapus; STE Defect memilih NRC dari M3 | Menunggu | |
| 127 | Tarik task card | Penarikan task dan Check Pack ke WO tetap di M2? | Pindah ke form WO M3 | Menunggu | |
| 128 | Task Library | Non-routine task dari M1 tampil read-only di Task Library? | Ya | Menunggu | |
| 129 | Task card di WO | Task card di WO salinan isi master? | Ya; revisi sesudahnya tidak mengubah WO berjalan; simpan referensi revisi MP asal | Menunggu | |
| 130 | Check Pack, Forecast | Hapus/batal/pindah task card di WO mengubah master Check Pack dan last done? | Tidak | Menunggu | |
| 131 | MP | Revisi MP dari hasil reliability M4 otomatis? | Tidak; dasar revisi di Catatan Revisi | Menunggu | |
| 132 | Notifikasi Due | Ambang 10% dihitung dari batas mana? | Batas berlaku: threshold sebelum pelaksanaan pertama, interval sesudahnya | Menunggu | |
| 133 | Lintas | Brief M4 masih merujuk tab Komponen task card M2 | Hapus rujukan dari brief M4 | Menunggu | |

> [!tip] Butir 123–133 bisa langsung diputuskan
> Modul 2, 3, dan 4 dipegang PM yang sama. Putuskan sekaligus, catat sebagai `M2-KP-YYMMDD-nn` di register, dan selaraskan dengan [[M3 Open Questions#Internal Modul 2 dan 3]].

## Pertanyaan baru (setelah 11 Nov)

| Kode | Untuk | Menu | Pertanyaan | Usulan sementara | Status | Jawaban |
|---|---|---|---|---|---|---|
| | | | | | | |
