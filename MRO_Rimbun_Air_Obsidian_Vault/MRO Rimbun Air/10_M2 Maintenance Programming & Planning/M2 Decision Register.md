---
tipe: register-keputusan
modul: M2
diperbarui: 2026-11-11
sumber:
  - claude/Decision_Log_Modul2_9Nov.md
tags: [m2]
aliases: [Decision Log Modul 2, Keputusan M2]
---
# M2 Decision Register

Nomor baris mengikuti Decision Log 9 Nov (1–77) agar tetap cocok dengan artifact. Keputusan baru setelah 11 Nov memakai kode `M2-KP-YYMMDD-nn` di bagian paling bawah. Kolom **Acuan** memakai kode di [[Kamus Kode & Label#Modul 2]].

**Sumber sesi:** 13 Okt review desain M2 (R01–R57) · 19 & 23 Okt review M3 · 22–28 Okt review M4 (termasuk diskusi Hard Time 27–28 Okt) · 8 Nov konfirmasi PM.

## Lingkup dan perpindahan antar modul

| No | Tgl | Menu | Keputusan → dampak | Acuan |
|---|---|---|---|---|
| 1 | 13 Okt | AD/SB | AD/SB Compliance keluar dari M2; dokumen teknis dan EO di M1 → menu & frame AD/SB dihapus | R33 |
| 2 | 13 Okt | EO | EO dibuat di M1, bisa menambah task card sendiri atau merujuk task MP; nomor EO mengikuti MP → task asal EO tetap masuk forecast dan Check Pack | R34, R35, C26 |
| 3 | 13 Okt | Handoff WO | Handoff Check Pack ke WO berjalan di modul WO → menu WO Check Pack keluar dari M2 | R57 |
| 4 | 19 Okt | Submodul Task Card | Task card di M2 hanya master; eksekusi per WO di Detail WO M3, tanpa daftar lintas WO → submodul Task Card bubar, Task Library satu-satunya master | M2-17, B-04, B-05 |
| 5 | 19 Okt | Task Card Detail | Task card di WO hanya header; job description opsional → tab Checklist, Komponen, Material dihapus | M2-18 |
| 6 | 19 Okt | Closing | Sign-off diganti closing (work performed, TSN, CSN, tanggal) terhubung stamp; field temuan & transfer MDDR/DMI/AFML dihapus | M2-22 |
| 7 | 19/23 Okt | Status task card | Open, In Progress, Completed, Closed, Cancelled; tanpa On Hold dan Deferred | M2-23, Q-02 |
| 8 | 19/23 Okt | NRC | NRC anak task card, dibuat & dikerjakan di WO, tidak di-master, berbeda dari MDDR → alur & form NRC keluar dari M2 | M2-24, M3-01 |
| 9 | 19 Okt | Komponen | Tab Komponen dihapus; lepas-pasang dicatat di Component Transaction M4 | M2-19 |
| 10 | 19 Okt | Non-routine | Masalah berulang di-master di M1 (menu Ad-hoc), ditambahkan ke WO saat pesawat terkena → tombol "Buat Task Ad-hoc" tidak dibutuhkan | M2-25, B-06 |
| 11 | 23 Okt | Ad-hoc di WO | Task card ad hoc di WO sekali pakai, tidak masuk master, berbeda dari menu Ad-hoc M1 | M2-11, M3-03 |
| 12 | 19 Okt | Task dari EO | Task EO tidak dibuat ulang; langsung ditambahkan ke WO → fitur "Buat Task dari EO" dihapus | M2-26 |
| 13 | 23 Okt | Cetak | Task card selalu di-generate sistem dan dicetak dari WO → tombol cetak tidak ada di M2 | M2-29, M3-05, M3-07, M3-08 |

## Submodul Maintenance Program

| No | Tgl | Menu | Keputusan → dampak | Acuan |
|---|---|---|---|---|
| 14 | 13 Okt | Navigasi | MP sebelum Check Type; sidebar: Aircraft Type, MP, Check Type, Task Library, Hard Time | R04 |
| 15 | 13 Okt | Nama menu | "AMP Dashboard" → "Maintenance Program" di semua label | R05 |
| 16 | 13 Okt | Aircraft Type | FEC dihapus dari tipe (nasib FEC Category di task menunggu) | R01 |
| 17 | 13 Okt | Aircraft Type | STE tidak ditetapkan per tipe → field Basis STE dihapus | R02 |
| 18 | 13 Okt | Aircraft Type | Source dokumen = Kode AMP (teks) | R03 |
| 19 | 13 Okt; 8 Nov | Aircraft Type | Tipe pesawat diinput di M2 lewat Aircraft Type Profile | R01–R03, PM 8 Nov |
| 20 | 13 Okt | Daftar MP | MP Number paling kiri setelah nomor, identitas utama, bisa diklik | R06 |
| 21 | 13 Okt | Revisi | Supersedes tidak dipakai; rantai versi = MP Number sama, urut Issue & Revisi | R07 |
| 22 | 13 Okt | Revisi | Kategori operasional dihapus | R08 |
| 23 | 13 Okt | Approval MP | DoM tidak tampil; PPC Staff ajukan, Chief PPC setujui/tolak | R09 |
| 24 | 13 Okt | DGCA | Submisi DGCA di luar sistem → tab DGCA-PAI dihapus | R10, K25 |
| 25 | 13 Okt | Pesawat pengguna MP | Effectivity mengacu ke MP yang menempel di pesawat (tempat relasi menunggu) | R27, KO-1 |
| 26 | 13 Okt | Form task | Check code/name/sequence dihapus dari task; tersisa relasi tipe | R11 |
| 27 | <29 Okt | Check Type | Check Type hanya referensi, tidak terhubung ke task maupun Check Pack | C24 |
| 28 | 13 Okt | Interval/Threshold | Section "Pengaturan Interval/Threshold", tiap baris berjenis Threshold atau Interval | R12 |
| 29 | 13 Okt | Interval/Threshold | Threshold dihitung dulu; setelah tercapai interval berlaku | R20 |
| 30 | 13 Okt | Interval/Threshold | Kalender hari/bulan/tahun + field tanggal (arti tanggal menunggu) | R13, R30 |
| 31 | 13 Okt | Interval/Threshold | Flight hour pindah ke section interval | R19 |
| 32 | 13 Okt | Task Card | Deskripsi pindah ke section Task Card Number & PDF | R14 |
| 33 | 13 Okt | Referensi | Task reference code hingga 3 baris | R15 |
| 34 | 13 Okt | Zone, Access Panel | Masuk Identitas & Parameter; zone multi bertumpuk, access panel multi dipisah koma; dropdown master | R16, R21, R22 |
| 35 | 13 Okt | Man-hours | Dipisah: Jumlah Personel dan Man-hours per task card (0.50 = 30 menit), tanpa total | R17, C10 |
| 36 | 13 Okt | Skill Group | Skill group engineer: kode + deskripsi, dropdown master | R18 |
| 37 | 13 Okt; 8 Nov | ATA | Dropdown satu pilihan dari master; **4 digit chapter-section** (mis. 25-45) | R23, PM 8 Nov |
| 38 | 13 Okt | Task Part | Part + qty, replacement code 100% atau OC; 100% wajib diganti setiap dikerjakan; PN dari PN Master | R24, R25 |
| 39 | 13 Okt | Task | Setiap task card punya detail isi dan tergabung di MP | R26 |
| 40 | 13 Okt | Task Type | Task type berupa pilihan (daftar menunggu) | R28 |
| 41 | 13 Okt | Effectivity | Pilih salah satu: pesawat (MP ini) atau komponen (PN lalu SN) | R29 |
| 42 | 19 Okt | Checklist | Checklist pindah ke Task Library | M2-19 |
| 43 | 19 Okt | Material & Tool | Material dan tool di Task Library + qty; istilah "tool"; kalibrasi di M5; tanpa SN/transaksi di task card; part 100% otomatis ke Material Required WO → menu Material, Sparepart & Kalibrasi dihapus | M2-20, R25 |
| 44 | 13 Okt | Import | Import Excel dicocokkan dengan PDF; template mengikuti field baru | R31 |
| 45 | 13 Okt | Import | Error handling per kolom, data ganda, data wajib | R32 |
| 46 | 27 Okt | Hard Time | Menu Hard Time di MP sebagai acuan TBO bagi M1 dan Component Transaction M4; HT report keluar dari M1; task effectivity komponen menjadi HT komponen | M2-05, LM-05 |
| 47 | 28 Okt | Hard Time | Expendable serialized berumur terbatas (baterai) masuk konfigurasi dan HT | M2-06, LM-04 |
| 48 | 27–28 Okt | Umur komponen | LLP dan OC/CM di M1; M2 hanya batas HT dan sisa umur HT; TSN/CSN per SN dibaca dari M1 | M2-05 |
| 49 | 27–28 Okt | Scrap | Komponen scrap tidak dihitung lagi (LLP, HT, dll.); scrap dicatat di M5, bukan tindakan HT | diskusi HT |
| 50 | 13 Okt | Format nomor | Master format nomor untuk dokumen bernomor otomatis, dikonfigurasi admin (lokasi menunggu) | R36, K16 |

## Maintenance Planning & Forecast

| No | Tgl | Menu | Keputusan → dampak | Acuan |
|---|---|---|---|---|
| 51 | 13 Okt | Forecast | Kolom Interval/Threshold sebelum Remaining dengan penanda batas berlaku | R37 |
| 52 | 13 Okt | Forecast | Filter ditambah grup AD/SB dan HT | R38 |
| 53 | 26 Okt | Forecast: DMI | DMI masuk forecast menurut due date; Buat WO dari forecast/aksi per DMI; beberapa DMI satu registrasi satu WO; DMI ikut tertutup saat WO Close | M2-01, M4-26 |
| 54 | 23 Okt | Forecast: DMI | Batas DMI hanya due date (tanpa FH/FC); DMI Extension menghasilkan due date baru. **Perlu diselaraskan:** K6-04 (6 Nov) menetapkan time limit DMI bisa tanggal, FH, atau FC — lihat LX-01 | M2-03, M4-07, M4-08, M4-13 |
| 55 | 28 Okt | Hitung ulang | Saat AFML di-close TR: jam terbang, umur komponen, LLP, HT, DMI berubah; salah input dikoreksi di penerbangan berikutnya | M2-07, LM-11, AFR-03 |
| 56 | 28 Okt | Tanggal data | TSN/CSN per sektor; data umur "as of" closing AFML terakhir | M2-08, LM-10, CT-11 |
| 57 | 27–28 Okt | Forecast → WO | Removal Scheduled = transaksi dari WO hasil planning (WO wajib); tanpa WO = Unscheduled | M2-09, CT-02 |
| 58 | 19 Okt | Last done | Setelah closing di WO, last done diperbarui otomatis; AD/EO di M1; tidak diinput manual | M2-28, B-17 |
| 59 | 13 Okt | Due List | Filter periode (tanggal mulai–akhir) | R39 |
| 60 | 13 Okt | Due List | Overdue paling atas | R40 |
| 61 | 13 Okt | Detail Due | Tambah STE di bawah WCF Calculation & Remaining; Submit STE di header dihapus | R41 |
| 62 | 13 Okt | Detail Due | Submit STE memperbarui dashboard STE dan kolom Active STE | R42 |
| 63 | 13 Okt | Nomor STE | Nomor STE berformat dari master | R43 |
| 64 | 13 Okt | Perhitungan STE | STE tidak dihitung, dicatat per kejadian; validasi task terlarang & STE ganda tetap | R02 |
| 65 | 13 Okt | Jenis STE | Check Pack, Defect, Task Card; field subjek kondisional | R44 |
| 66 | 13 Okt | Dokumen STE | Lampiran PDF dokumen fisik; due setelah ekstensi diisi manual | R45 |
| 67 | 13 Okt | HIRA | Tidak wajib; tab tetap ada | R46 |
| 68 | 13 Okt | Tanda tangan | Stempel & tanda tangan tidak di-upload; tab menjadi Dokumen STE | R47 |

## Check Pack & Out of Phase

| No | Tgl | Menu | Keputusan → dampak | Acuan |
|---|---|---|---|---|
| 69 | 13 Okt | List | WO terkait dihapus dari list dan header detail | R48 |
| 70 | 13 Okt | Nomor | Format nomor Check Pack dari master | R49 |
| 71 | 13 Okt | List | Tambah threshold/interval di list | R50 |
| 72 | 13 Okt | Buat | Double pack baru terjadi setelah dibuat; form hanya keterangan netral | R51 |
| 73 | 13 Okt | Detail | Task di pack lain bukan konflik; kolom Keterangan, badge netral | R52 |
| 74 | 13 Okt | Pilih task | Mencakup task EO, MP, ad-hoc; badge & filter Sumber | R53 |
| 75 | 13 Okt | Pilih task | Kolom WCF terdekat diganti threshold/interval | R54 |
| 76 | 13 Okt | Detail | Task boleh di lebih dari satu pack | R55 |
| 77 | 13 Okt | Effectivity | Effectivity pesawat pada Check Pack; task tersaring | R56 |

## Keputusan lintas modul yang mengikat M2

| Tgl | Keputusan | Acuan |
|---|---|---|
| 8 Okt | DMI dipegang Modul 4; Forecasting M2 hanya membaca | Keputusan internal lintas modul |
| Okt | HT dibuat di M2 sebagai master batas per PN; M1 menarik data HT dari M2; LLP dan OC/CM tetap di M1 | Usulan klien, Okt 2026 |

## Keputusan baru (setelah 11 Nov)

| Kode | Tgl | Sesi | Menu | Keputusan → dampak | Acuan |
|---|---|---|---|---|---|
| | | | | | |
