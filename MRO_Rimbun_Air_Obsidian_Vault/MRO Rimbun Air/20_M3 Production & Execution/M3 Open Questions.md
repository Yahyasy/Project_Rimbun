---
tipe: register-pertanyaan
modul: M3
diperbarui: 2026-11-11
sumber:
  - claude/Knowledge_Base_Modul3_Acuan_Proses_Desain.md
tags: [m3]
aliases: [Pertanyaan Terbuka M3]
---
# M3 Open Questions

60 butir terbuka per 30 Okt: **49 untuk Rimbun Air (15 prioritas Tinggi), 6 untuk PM lain, 5 internal M2–M3**. Prioritas Tinggi mengubah alur atau struktur data; Sedang mengubah tampilan atau aturan layar. Kolom **Sama dengan** menunjuk butir yang sama di register modul lain agar tidak ditanyakan dua kali.

## Rimbun Air — prioritas Tinggi (15)

| Kode | Pertanyaan | Usulan sementara | Sama dengan | Status | Jawaban |
|---|---|---|---|---|---|
| Q-M2-08 | Last done diperbarui saat task card Closed atau WO Closed? | Task card Closed (tanggal, TSN, CSN task card) | M2 no 105 | Menunggu | |
| Q-13 | Arti "RII mencakup 2 engineer" dan alurnya? | Pelaksana menandai Completed, inspector RII menutup; dua orang, dua stamp | M2 no 97 | Menunggu | |
| Q-20 | Task card pesawat cukup index + lampiran pabrikan; work description menggantikan Checklist? | Ya | M2 no 93 | Menunggu | |
| M3-10 | Asal task card workshop dan approval-nya? | Dibuat di Task Library, melalui approval sebelum dipakai | | Menunggu | |
| Q-04 | Validasi personel penutup? | Dari daftar sign-in; ditolak bila otorisasi/lisensi tidak aktif | SSG `checkAuthority` | Menunggu | |
| Q-08 | TSN/CSN saat close task card dari WO atau diisi ulang? | Default dari WO, bisa diubah | | Menunggu | |
| Q-18 | MDDR masih open saat WO ditutup, boleh Close? | Ad-hoc ditutup "Dilanjutkan ke defect AFML" + referensi manual | | Menunggu | |
| Q-25 | DMI tampil dan dikerjakan bagaimana di WO? | Satu baris task card bersumber DMI | | Menunggu | |
| Q-26 | DMI mana yang ikut ditutup saat WO Close? | Hanya yang baris task card-nya Closed | | Menunggu | |
| Q-27 | DMI ditutup otomatis atau konfirmasi; data apa yang dikirim? | Konfirmasi di popup Close WO | M4 Q26-05; M2 no 106 | Menunggu | |
| Q-34 | Pending Install saat Close WO: blokir atau peringatan? | Close WO aktif bila Pending Install nol, aksi per baris | | Menunggu | |
| Q-40 | Baris material untuk part robbed/swap, posisi kosong donor, persetujuan swap? | Terpenuhi referensi transaksi; donor lewat jalur normal; swap mengikuti robbing | M4 CT-08 | Menunggu | |
| Q-41 | Issue gudang tanpa WO (AFR-18) atau semua wajib WO (B-40)? | B-40 hanya untuk issue ke WO | | Menunggu | |
| Q27-03 | Removal di WO untuk DMI/defect tercatat Scheduled? | Scheduled hanya bila Asal WO Planning | M2 no 107 | Menunggu | |
| HT-02 | Pemicu reset Hard Time setelah overhaul/test? | Closing WO dengan referensi ARC/Form 1 | M2 no 100 | Menunggu | |

## Rimbun Air — prioritas Sedang (34)

| Kode | Pertanyaan | Usulan sementara | Status | Jawaban |
|---|---|---|---|---|
| Q-01 | PPC boleh mengubah WO saat Waiting Approval? | Terkunci; Chief mengembalikan ke New | Menunggu | |
| Q-03 | Status WO mana yang otomatis? | WIP otomatis; Close WO manual | Menunggu | |
| Q-05 | Di status apa task card boleh dihapus? | New, Approved, Issued | Menunggu | |
| Q-11 | Siapa menutup WO? | Produksi (engineer) | Menunggu | |
| Q-15 | Issue per WO atau per task card? | Per WO | Menunggu | |
| Q-32 | Field wajib di Close WO? | Hanya tanggal closing | Menunggu | |
| Q-37 | Ambil dari AFML memakai sektor mana? | Sektor terakhir yang di-close sebelum tanggal WO | Menunggu | |
| Q-46 | List M3 bisa diekspor? | Ya, PDF dan Excel | Menunggu | |
| Q26-06 | Jalur WO Unscheduled dari defect dan kolom In WO masih dipakai? | Tidak; label "Dalam WO" mengisi kolom In WO bila dipertahankan (= M4-28) | Menunggu | |
| Q-07 | Arti "material beres" sebelum In Progress? | Semua baris material Issued | Menunggu | |
| Q-10 | Sign-in mulai Approved atau Issued? | Approved | Menunggu | |
| Q-12 | Sign-off final Chief per task card dihapus? | Dihapus | Menunggu | |
| Q-29 | Lampiran PDF wajib? | Wajib untuk task asal MP (= M2 no 94) | Menunggu | |
| Q-30 | Kolom RTS per work description atau per task card? | Stamp per work description + satu blok closing | Menunggu | |
| Q-31 | Kapan work description di WO boleh diubah? | Selama task card Open | Menunggu | |
| Q-39 | RII untuk Ad-hoc, DMI, NRC? | NRC ikut induk; toggle RII di Ad-hoc dan DMI | Menunggu | |
| Q-09 | Format nomor NRC; arti "NRC tidak masuk master"? | Induk + "-NRC-01"; tidak menjadi task di Task Library | Menunggu | |
| Q-14 | NRC punya status Cancelled? | Ya | Menunggu | |
| Q-16 | Buku MDDR milik MRO, nomor diinput manual? | Ya, unik dalam satu WO | Menunggu | |
| Q-17 | Status MDDR terpisah dari Ad-hoc? | Tidak; hasil MDDR dicatat saat Close | Menunggu | |
| Q-19 | Nama resmi Ad-hoc task card? | "Ad-hoc Task Card" di WO; "Non-routine Task" di M1 (= M2 no 98) | Menunggu | |
| Q-21 | Kapan temuan menjadi NRC dan kapan MDDR? | Sesuai tabel jalur temuan | Menunggu | |
| Q-22 | "Monitor" status MDDR itu yang mana? | Tab Temuan + indikator di WO List | Menunggu | |
| Q-23 | Siapa menambah Ad-hoc, kapan, format nomor? | PPC, Approved s.d. WIP, nomor WO + "-AH-01" | Menunggu | |
| Q-24 | Setiap Ad-hoc wajib punya MDDR? | Tidak; paling banyak satu | Menunggu | |
| Q-33 | Resolution MDDR sama dengan work performed? | Satu isian, masih bisa diubah | Menunggu | |
| Q-M2-01 | STE jenis Defect mencakup DMI? | Tidak; DMI lewat DMI Extension (= M2 no 111) | Menunggu | |
| Q-28 | Status DMI selama di WO? | Open berlabel "Dalam WO" | Menunggu | |
| Q-43 | CML dikerjakan dan ditutup lewat WO bagaimana? | Seperti DMI | Menunggu | |
| Q-45 | TSN/CSN WO disesuaikan setelah koreksi jam AFML? | Tidak otomatis; penanda di Detail WO | Menunggu | |
| Q26-09 | CML open masuk forecast? | Ya, grup sendiri (= M2 no 103) | Menunggu | |
| Q-38 | Tool Loan wajib WO; tool non-gudang? | WO wajib, task card opsional; non-gudang tidak dicatat | Menunggu | |
| Q27-05 | Swap memakai satu form dua arah? Form cetak apa? | Satu form; format Robbed Part Form | **Sebagian terjawab 5 Nov** (K5-04: Swap proses tersendiri, pola form sama; cetak & approval masih CT-08) | |
| Q27-06 | Part dari Pending RTS dipasang di posisi lain pesawat sama lewat Install biasa? | Ya, sumber Pending RTS | Menunggu | |

## PM modul lain (6)

| Kode | Untuk | Pertanyaan | Usulan sementara | Status | Jawaban |
|---|---|---|---|---|---|
| Q-06, Q-47 | PM M4 dan M5 | Book membentuk MR atau RQ? Approver RQ dari WO, sequence nomor, status order kembali ke WO? | MR di-approve PPC; RQ lewat form M4, approve Chief PPC & Engineering; nomor dari master; status order sebagai info | Menunggu | |
| Q-35 | PM M4 (Yahya) | Removal/Installation dibuka dari baris task card atau menu M4? | Keduanya | Menunggu | |
| Q-42 | PM M4 (Yahya) | Ada aksi convert temuan ke defect? | Tidak; ditulis manual di AFML | Menunggu | |
| Q-36 | PM M5 | Bagaimana M5 tahu WO sudah Closed? | Event WO Closed bersamaan dengan event DMI | Menunggu | |
| Q28-12 | PM M5 | Pemegang layar Pending RTS/Install, store unserviceable, return consumable? | Disepakati di sesi PM | Menunggu | |
| C17 | PM M1 | Di mana master format nomor dokumen? | Satu master global lintas modul (= M2 no 119; SSG-10) | Menunggu | |

> [!tip] Q-35 dan Q-42 bisa langsung diputuskan
> Modul 4 dipegang Yahya sendiri; putuskan sekarang dan catat di [[M3 Decision Register]] dan [[M4 Decision Register]].

## Internal Modul 2 dan 3

| Kode | Pertanyaan | Usulan | Sama dengan | Status | Keputusan |
|---|---|---|---|---|---|
| Q-M2-05 | Task Card Detail di WO dikelola M3? | Ya; M2 hanya master | M2 no 125 | Menunggu | |
| Q-M2-06 | Menu NRC dihapus dari M2? | Ya | M2 no 126 | Menunggu | |
| Q-M2-07 | Penarikan Check Pack & task dari form WO M3? | Ya | M2 no 127 | Menunggu | |
| Q-M2-09 | Non-routine task read-only di Task Library? | Ya | M2 no 128 | Menunggu | |
| C25 | Detail Check Pack menampilkan WO yang memakainya? | Tidak | M2 no 124 | Menunggu | |

## Pertanyaan baru (setelah 11 Nov)

| Kode | Untuk | Pertanyaan | Usulan sementara | Status | Jawaban |
|---|---|---|---|---|---|
| | | | | | |
