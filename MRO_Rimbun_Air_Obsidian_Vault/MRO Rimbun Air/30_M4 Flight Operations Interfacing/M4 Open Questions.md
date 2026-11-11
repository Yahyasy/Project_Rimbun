---
tipe: register-pertanyaan
modul: M4
diperbarui: 2026-11-11
sumber:
  - claude/Flow_Detail_Modul4_per_Submodul_Menu_3Nov.md
  - claude/Konfirmasi_Modul4_5Nov.md
  - claude/Keputusan_AFML_Modul4_4Nov.md
tags: [m4]
aliases: [Pertanyaan Terbuka M4]
---
# M4 Open Questions

Daftar 32 kelompok butir terbuka Flow Detail 3 Nov, **sudah dicocokkan** dengan keputusan 4–6 Nov. Butir yang terjawab dipindah ke bagian *Sudah terjawab sejak 3 Nov* agar jejaknya tetap ada.

## Masih terbuka

| Sub-modul | Kode | Butir | Usulan sementara | Untuk | Status |
|---|---|---|---|---|---|
| AFML | AFR-21, WQ-02 | Brought forward dari halaman belum Closed; TSN tampil jam:menit atau desimal | Brought forward dari sektor terakhir non-void; input jam:menit | Rimbun Air | Menunggu |
| AFML | FQ-01, FQ-06, FQ-07 | Jam dikirim saat Closed; perlakuan sync gagal | Dikirim saat Closed; halaman tetap Closed, kirim ulang | Rimbun Air | Menunggu |
| AFML | FQ-02, FQ-03 | Alokasi jam komponen saat penggantian di tengah halaman; jam engine dari flight atau block time; jam APU | Dibagi menurut waktu block off (Event Time AF-06) | Rimbun Air, PM M1 | Sebagian (AF-06) |
| AFML | AFR-27, FC4 | Baris component change wajib punya transaksi sebelum Close | Ya, cek sebelum Close | Rimbun Air | Menunggu |
| AFML | WQ-05, FQ-08 | WO di antara penerbangan memakai TSN/CSN sesudah sektor terakhir; sumber referensi Actual Flight Closing | Ya | Rimbun Air, Yahya | Menunggu |
| AFML | H-02 | Defect dan DMI dari halaman yang kemudian di-void | Tetap berlaku; hanya jam & cycle tidak dihitung | Rimbun Air | Ditahan |
| AFML | K5-08 lanjutan | Periode laporan selisih koreksi; perlu approval koreksi | Tanggal halaman tujuan + keterangan asal; tanpa approval, alasan wajib | Rimbun Air | Menunggu |
| AFML | DHC-a | Field aktif DHC-6 | 37 field umum ATR & B737; engine parameter daftar ATR | Yahya, Rimbun Air | Menunggu |
| AFML | DHC-b | Siapa mengatur Master Field per tipe | Diisi tim dev saat setup; layar Master Field menyusul | Yahya | Menunggu |
| Fluid | WQ-03, WQ-06 | Oli dicatat sesudah mendarat; aturan ATR sama dengan B737 | Dipakai sebagai asumsi | Rimbun Air | Ditahan |
| Fluid | WQ-04 | Batas QT/FH per tipe engine & sistem hydraulic untuk warna | Tanpa warna dulu | Rimbun Air | Ditahan |
| Fluid | Q28-07 | Oli APU | Ikut posisi APU B737 | Rimbun Air | Menunggu |
| Defect | M4-28, Q26-06 | Jalur WO Unscheduled dan kolom In WO | Tidak dipakai; label "Dalam WO" | Rimbun Air | Menunggu |
| Defect | Q26-02, Q26-03 | Satu AOG untuk beberapa defect; kolom AOG di report | — | Rimbun Air | Menunggu |
| Defect | Q26-04 | Nomor urut 7 digit global atau per registrasi | — | Rimbun Air | Menunggu |
| Defect | Q26-05 | DMI tertutup otomatis atau konfirmasi saat WO Close | Konfirmasi di popup Close WO (= M3 Q-27, M2 no 106) | Rimbun Air | Menunggu |
| Defect | M4-11, M4-12, M4-32 | Defect ditulis ulang saat penutupan; STE; nama menu DMI Extension | — | Rimbun Air | Menunggu |
| Defect | Q26-01, Q26-10 | Fleet Status hanya dari declaration; bagian atas Rekap PIREP/MAREP | Ya; — | Rimbun Air | Menunggu |
| Component | Q27-02, Q27-03 | Child yang tidak ikut terlepas; Scheduled untuk WO DMI/defect | Scheduled hanya bila Asal WO Planning | Rimbun Air | Menunggu |
| Component | Q27-06 | Pemasangan dari Pending RTS di posisi lain | Ya, lewat Install biasa | Rimbun Air | Menunggu |
| Component | CT-08 (Swap) | Approval Director of Maintenance dan cetak form untuk Swap | Mengikuti Robbed | Rimbun Air | Menunggu |
| Component | Q27-07, Q27-08 | Component Removal Report dihapus; kolom TSN, CSN, as of | Hapus; kolom sesuai | Rimbun Air | Menunggu |
| Component | Baru 30 Okt | Transaksi yang dikirim ke Procurement, robbed & swap, data shipping core | — | PM M6 (Wisnu) | Menunggu |
| Reliability | RL-01, RL-02 | Basis jam rate keseluruhan dan bulanan | — | Rimbun Air | Menunggu |
| Reliability | RL-03 | Jendela 12 bulan dan nilai alert level; file Excel sumber laporan | 2,5 SD populasi 12 bulan | Rimbun Air | Menunggu |
| Reliability | RL-04, RL-05 | Alert Status di sistem & notifikasi; MTBUR Worldwide | Notifikasi Alert 2 & 3; MTBUR WW di PN Master | Rimbun Air, PM M1 | Menunggu |
| Reliability | RL-06–RL-09 | Top 10 gabung PN pengganti; rate & alert defect; FC di Utilization; laporan ATR & DHC-6 | — | Rimbun Air | Menunggu |
| Reliability | Q28-05, Q28-06, Q28-09 | Minimum kemunculan repetitive; layar Rule Settings; isi Non-Serialized | Rule Settings dihapus; Top 10 issue part | Rimbun Air | Menunggu |
| Lintas M2 | FQ-04 | Sisa task & HT dihitung ulang langsung setelah closing | Ya | PM M2 (Yahya) | Bisa diputuskan |
| RQ | P-02, RQ-18 | Siapa "direktur teknik"; dua langkah untuk semua tipe termasuk AOG | Director of Maintenance; dua langkah semua tipe | Rimbun Air | Menunggu |
| RQ | P-07 | Credit note | — | Rimbun Air, PM M6 | Menunggu |
| RQ | P-08, Q-47 M3 | Penyelarasan RQ dari task card WO | Form RQ M4, approver Chief PPC & Engineering | PM M3 (Yahya) | Bisa diputuskan |
| RQ | Konfirmasi Procurement | RQ Status Report: list acuan, Category, Source, No. item, Required By, keterangan status | — | PM M6 (Wisnu) | Menunggu |
| CML | Q26-07, Q26-08, Q26-09, CML-06, CML-08 | Pelapor; syarat penutup; CML masuk forecast; waktu & stasiun tidak wajib | Otorisasi aktif; masuk forecast sebagai grup | Rimbun Air | Menunggu |
| Lintas | Q28-10, Q28-11, Q28-12 | Penanda PN di M1; Hard Time di M2; layar Pending & return consumable di M5 | — | PM M1, M2, M5 | Sebagian (HT di M2 Final) |
| Lintas | 8.1–8.4 vs SSG | Approval Inbox, notifikasi, penomoran, riwayat cetak dibangun di M4 atau SSG | Dipusatkan di SSG | Yahya | Bisa diputuskan (LX-02) |

## Sudah terjawab sejak 3 Nov

| Kode | Butir | Jawaban | Tgl |
|---|---|---|---|
| Q26-11 | Nama status setelah submit | Waiting TR (AF-09) | 4 Nov |
| AFR-08, AFR-24, Q28-08 | Engine parameter masuk sistem | Disertakan (AF-07) | 4 Nov |
| WQ-01 | Format jam | Flight Hour Report jam:menit + desimal (AF-08); input jam:menit masih usulan | 4 Nov (sebagian) |
| FC3 | Closing Harian | Tidak ada; satu per satu (AF-02) | 4 Nov |
| H-01 | Halaman Void bisa diedit | Lewat Correct Flight Log (K5-01) | 5 Nov |
| H-03, P-05, Q27-01 | Format S/N wheel assy | Outer sebagai induk (K5-02) | 5 Nov |
| Q27-05 | Form Swap | Proses tersendiri, pola form sama (K5-04); approval & cetak masih CT-08 | 5 Nov |
| FU-01 | Basis QT/FH hydraulic | Per FH (K5-05) | 5 Nov |
| P-06, PC-01 | Master UOM | Di Modul 1 (K5-07) | 5 Nov |
| FQ-05 | DMI berbatas jam/cycle | Limit Type tanggal/FH/FC (K6-04) | 6 Nov |
| Q26-12 | Input oli dibatasi PN issue | Ya, dari issue ke WO (K5-09) | 5 Nov |
| AFR-13, Q-09 (22 Okt) | Saldo oli | Tidak dibuat (AF-05, FU-02) | 4 Nov |
| Q26-13 | Fuel Drain Check | Tidak masuk struktur menu baru (FL-01) | 4 Nov |

## Pertanyaan baru (setelah 11 Nov)

| Kode | Untuk | Sub-modul | Pertanyaan | Usulan sementara | Status | Jawaban |
|---|---|---|---|---|---|---|
| | | | | | | |
