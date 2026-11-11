---
tipe: alur
modul: M3
diperbarui: 2026-11-11
sumber:
  - claude/Knowledge_Base_Modul3_Acuan_Proses_Desain.md
tags: [m3, lintas]
aliases: [Integrasi Modul 3, DMI di WO]
---
# M3 Integrasi & DMI

Modul 3 berhubungan dengan Modul 4 **hanya lewat WO**: DMI dan CML masuk sebagai baris task card, TSN/CSN dibaca dari sektor AFML, dan selama pesawat di hangar AFML maupun DMI tidak ditulis. Hasil keluar di dua titik: saat **task card Closed** (last done, compliance) dan saat **WO Closed** (DMI, return consumable).

## DMI, CML, dan AFML

| Topik | Aturan | Status | Acuan |
|---|---|---|---|
| DMI masuk WO | DMI masuk forecast menurut due date; planner membuat WO dari forecast/aksi per DMI atau memilih DMI di form WO; beberapa DMI satu registrasi boleh satu WO | Final | B-63, M4-26 |
| DMI di WO | Satu baris task card bersumber DMI tanpa master: judul dari DMI description, nomor DMI, item MEL, material langsung, work performed sebagai rectification | Usulan | Q-25 |
| Status DMI selama di WO | Tetap Open di M4 dengan label "Dalam WO [nomor]" agar tidak masuk WO lain; WO/baris Cancelled → tautan dilepas, DMI kembali ke forecast | Usulan | Q-28, Q26-06 |
| Penutupan DMI | Manual di menu DMI M4, atau saat WO Close. **Closing task card tidak pernah menutup DMI**. Bila ditutup manual di luar WO, nomor WO tidak bisa dipilih | Final | B-61 |
| DMI yang ikut tertutup | Hanya DMI yang baris task card-nya Closed; baris yang dipindah membawa DMI-nya | Usulan | Q-26 |
| Konfirmasi dan data | Popup Close WO menampilkan daftar DMI, engineer mengonfirmasi. Data per DMI: nomor WO & task card, tanggal closing task card, engineer & nomor stamp, station dari lokasi WO, work performed sebagai deskripsi; halaman AFML kosong. Di M4: "Closed by WO [nomor]" | Final (Closed by WO); Usulan (konfirmasi, data) | B-64, Q-27, Q26-05 |
| Tidak ada DMI dari task card | Status Deferred dan aksi Defer ke DMI dihapus dari task card | Final | B-60, M4-14 |
| Perpanjangan DMI | Lewat DMI Extension M4, bukan STE Defect M2 | Usulan | Q-M2-01 |
| CML | Bila CML open masuk forecast: dipilih di form WO seperti DMI, satu baris task card, ikut ditutup saat WO Close | Menunggu | CML-08, Q26-09, Q-43 |
| Selama di hangar | Hanya WO yang di-update; AFML dan DMI tidak ditulis; TSN/CSN WO menjadi acuan sampai Close | Final | B-62, M4-15 |
| TSN/CSN dari AFML | Per **sektor** (mis. 1001-2), hanya sektor yang sudah di-close TR, dengan tanggal as of | Final | LM-10, CT-11 |
| Koreksi jam AFML | Lewat Correct Flight Log di penerbangan berikutnya. Usulan: WO menyimpan sektor sumber; bila ada koreksi setelah as of, Detail WO menampilkan penanda; task card belum Closed bisa ambil ulang, yang Closed tidak berubah | Final (koreksi); Usulan (penanda) | LM-11, Q-45 |
| Keluar hangar | Item MDDR belum selesai ditulis manual sebagai defect AFML; M3 hanya menyimpan referensi teks | Final | B-62, Q-18 |
| WO dari defect | Jalur WO Unscheduled langsung dari defect tidak dipakai; defect terjadwal lewat DMI | Menunggu | M4-28, Q26-06 |
| Stamp | Dari Employee Master M1, sumber sama dengan release authorization AFML | Final | M3B-18, AFR-16 |

## Data masuk ke Modul 3

| Data | Dari | Masuk ke | Pemicu | Status | Acuan |
|---|---|---|---|---|---|
| Isi task dan Check Pack (salinan) | M2 | Form WO | Ditarik ke WO | Final (sumber); Usulan (salinan) | M2-27, M2-33, Q-M2-07 |
| Part bertanda 100% | M2 | Material Required | Task masuk WO | Final | M2-20 |
| Baris forecast DMI dan HT | M2 | Form WO, Asal Planning | Buat WO | Final | M2-01, M2-09 |
| Task EO dan Non-routine | M1 via Task Library | Form WO | Ditarik | Final (EO); Usulan (non-routine) | M2-25, M2-26, Q-M2-09 |
| DMI open per registrasi | M4 | Form WO | Dipilih | Final | B-63 |
| CML open | M4 | Form WO | Dipilih | Menunggu | Q-43 |
| TSN/CSN per sektor + as of | AFML M4 (dicatat di M1) | Form WO | Ambil dari AFML | Final; default sektor Usulan | B-14, LM-10, Q-37 |
| Stamp & otorisasi | Employee Master M1 / SSG | Close task card, Control Sheet | Close | Final (sumber); Usulan (validasi) | M3B-18, Q-04 |
| Issue material | M5 | Material Required | Issue gudang | Final | B-40 |
| Status kalibrasi tool | M5 | Tool Loan | Peminjaman | Final | M2-20, MSPM 5.3.3 |

## Data keluar dari Modul 3

| Data | Ke | Pemicu | Status | Acuan |
|---|---|---|---|---|
| Book (MR) dan RQ | M5 dan pengadaan (form RQ M4) | Aksi Book / RQ | Usulan | B-38, B-39, Q-06, Q-47 |
| Removal dan Installation | Component Transaction M4 | Ganti komponen | Final (Scheduled dari WO); Usulan (titik masuk) | CT-01, CT-02, Q-35 |
| Konfigurasi dan umur komponen | M1 (lewat M4) | Sync Modul 1 | Final | CT-04, CT-07 |
| Robbed dan swap | M1; Material Required WO penerima | Transaksi | Final (tanpa gudang); Usulan (baris material) | CT-08, Q-40 |
| Last done (tanggal, TSN, CSN) | Forecast M2 | Task card Closed | Menunggu | B-17, M2-28, Q-M2-08 |
| Status compliance AD/EO | M1 | Task card Closed | Final | B-17, M2-28 |
| DMI Closed by WO | M4 | WO Closed, dengan konfirmasi | Final (prinsip); Usulan (data) | B-64, Q-27 |
| Batas return consumable | M5 | WO Closed | Final (aturan); Usulan (event) | LM-06, Q-36 |
| NRC/MDDR untuk STE Defect | M2 Menu 13 | Pengajuan STE | Usulan | M2-24 |
| Defect AFML dari MDDR | M4 (ditulis manual) | Keluar hangar | Final | B-62 |
| Tindakan terakhir Hard Time | M2 Menu 26 | Belum diputuskan | Menunggu | HT-02 |
| Relasi WO–Check Pack | Detail WO tab Check Pack (tautan ke M2) | Check Pack ditarik ke WO | Usulan; M2 tidak menampilkan WO | R57, C25 |
| Format nomor WO, NRC, MR, RQ | dari master format nomor | Simpan pertama | Menunggu | C17, M2-13 |

Gambaran semua modul: [[Integrasi End-to-End]].
