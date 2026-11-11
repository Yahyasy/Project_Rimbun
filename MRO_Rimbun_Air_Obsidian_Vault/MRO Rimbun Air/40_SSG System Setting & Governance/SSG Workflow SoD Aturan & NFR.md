---
tipe: register-keputusan
modul: SSG
diperbarui: 2026-11-11
sumber:
  - claude/PRD_System_Setting_Governance_RBAC.md
tags: [ssg]
aliases: [Approval Workflow, SoD, Aturan Bisnis Governance, NFR Keamanan, Keputusan SSG]
---
# SSG Workflow, SoD, Aturan Bisnis & NFR

Catatan ini berfungsi sebagai **Decision Register SSG**: D1–D8 ada di [[SSG Overview]], aturan bisnis BR-01–BR-22 di bawah, dan keputusan baru ditambahkan di bagian akhir.

## Approval workflow awal (15 di PRD + WF-SWAP yang perlu ditambahkan)

| Kode | Dokumen | Langkah (aktor → scope) | Status | Sumber |
|---|---|---|---|---|
| WF-MP | Revisi Maintenance Program | STF-PPC ajukan → CHF-PPC (APR-MP) | Final | Klien R09 |
| WF-TECHDOC | Registrasi AD/SB/SL | STF-ENGR ajukan → CHF-PPC (APR-TECHDOC), reject wajib alasan | Final | EC-DB |
| WF-EO | Engineering Order | CHF-PPC assessment → CHF-INS verifikasi → CHF-PPC approve | Final | EC-BRIEF 5.4 |
| WF-STE | Short Term Escalation | ENG-LINE / STF-PPC ajukan → CHF-INS (APR-STE) | Final | M2-BRIEF 13; CMM 3.6 |
| WF-WO | Work Order | STF-PPC ajukan → CHF-PPC approve (APR-WO); *rilis lewat Issue di M3* | Konfirmasi | M3 |
| WF-MEL | DMI Extension (dulu Perpanjangan MEL) | ENG-LINE / CHF-LM ajukan → CHF-INS (APR-MEL-1) → DIR-OPS (APR-MEL-2) | Final | M4 |
| WF-ROB | Robbed part | ENG-LINE / CHF-LM ajukan → DIR-MNT (APR-ROBBING) | Final | CMM 3.11.1 #9 |
| WF-SWAP | Swap (proses baru K5-04) | Usulan: mengikuti WF-ROB | **Perlu ditambahkan** | M4 CT-08 |
| WF-RQ | Request Part | ENG-LINE / STF-PPC ajukan → chief unit pengaju (APR-RQ) → *direktur teknik (M4 P-02)* | Final (langkah 1); langkah 2 perlu diselaraskan | M4 RQ-17, RQ-18 |
| WF-AVL | Approved Vendor List | STF-PROC ajukan → CHF-INS (APR-VENDOR) | Final | MSPM 5.5.1 #4 |
| WF-PAY | Payment PO | STF-PROC ajukan → DIR-MNT → MGMT (APR-PAYMENT) | Konfirmasi urutan | MSPM 5.5.2 |
| WF-SCRAP | Scrap Report | STORE ajukan → INSP-TE (APR-SCRAP) | Konfirmasi | MSPM 5.7.2 vs ML-BRIEF |
| WF-MANUAL | Revisi company manual | CHF-INS / MSTC / CHF-WBS siapkan → DIR-MNT (APR-MANUAL) | Final | MSPM 1.5; WBSPM 1.5 |
| WF-AUTH | Company Authorization | Chief dept ajukan → MSTC review → CHF-INS asesmen & terbit (GOV-AUTH) | Final | MSPM 3.4.1 |
| WF-OTA | One Time Authorization | CHF-LM ajukan → CHF-INS terbit (GOV-OTA) | Final | MSPM 3.5 |
| WF-GOV | Perubahan role, workflow, SoD, keamanan | SYS-ADM siapkan → DIR-MNT (APR-GOV-CHANGE) | Usulan | BR-20 |

Semua workflow memakai SOD-01 dan SOD-06. Approver tiap langkah dapat diubah di SSG-06 tanpa mengubah kode modul.

> [!warning] Selaraskan dengan Modul 4
> WF-RQ di PRD hanya satu langkah (chief unit pengaju), sedangkan Modul 4 menetapkan dua langkah berurutan (chief unit pembuat → direktur teknik, P-02 terbuka). Swap belum punya workflow. Lihat LX-04 di [[Isu Harmonisasi Lintas Modul]].

## Aturan Segregation of Duties

| Kode | Aturan | Dapat dinonaktifkan |
|---|---|---|
| SOD-01 | Pengaju ≠ penyetuju | Ya |
| SOD-02 | Pelaksana task ≠ penanda tangan RII | **Tidak** (dokumen) |
| SOD-03 | Tanpa self-grant kewenangan | Ya |
| SOD-04 | Admin tanpa kewenangan GOV; tidak memberi role ke akunnya sendiri | Ya |
| SOD-05 | Delegasi hanya untuk scope APR | Ya |
| SOD-06 | Langkah approval berurutan | **Tidak** (dokumen) |
| SOD-07 | Pembuat PO ≠ penyetuju payment | **Tidak** (dokumen) |
| SOD-08 | Pengubah toggle ≠ pemilik toggle (usulan) | Ya |

## Aturan bisnis

| ID | Aturan | Sumber | Status | Bukti PoC |
|---|---|---|---|---|
| BR-01 | Akun hanya dari employee aktif; employee Inactive tidak bisa login | [KLIEN] M3-QA 7 | Final | S01–S03 |
| BR-02 | Satu user banyak role; hak = gabungan | [DOK] Roster | Konfirmasi K35c | S30–S31 |
| BR-03 | Aksi A & X wajib lolos RBAC dan kewenangan | [DOK] MSPM 3.1 #1 | Final | S15 |
| BR-04 | Kewenangan sah bila lisensi berlaku, scope cocok tipe/PN/metode NDT, berlaku untuk keluarga pesawat, belum lewat | [KLIEN] M3-QA 1; [DOK] MSPM 3.2 | Final | S12–S14, S16–S17, S21–S29, S32–S33 |
| BR-05 | Toggle Fungsi Approval berlaku universal per orang | [KLIEN] M3-QA 4 | Final | S42–S43 |
| BR-06 | Hanya CHF-INS menerbitkan/membekukan/mencabut/memulihkan; toggle diubah CHF-INS atau Inspector | [DOK] MSPM 3.4; [TERKONFIRMASI] 5 Nov | Final | S34–S35, S40–S41, S67 |
| BR-07 | Masa berlaku maks 1 tahun; pengingat H-30 ke chief departemen | [DOK] MSPM 3.4.4 | Final | S33, S39 |
| BR-08 | NDT: kartu 1 tahun; beku bila tes mata lewat / 12 bulan tidak praktik; cabut 24 bulan; Trainee tidak accept/reject | [DOK] NDTPM | Final | S28–S29 |
| BR-09 | OTA 1 hari (unscheduled, tanpa tipe serupa) atau 7 hari (tipe serupa); kandidat ≥ 5 tahun; usul CHF-LM, terbit CHF-INS | [DOK] MSPM 3.5 | Final | S44–S49 |
| BR-10 | Mechanic tanpa aksi X; pekerjaan di-countersign pemegang AMEL | [DOK] MSPM 2.2.4 | Final | S11, S15 |
| BR-11 | Status training hanya peringatan saat transaksi | [RANCANGAN] EC-DB | Final | — |
| BR-12 | SOD-01 s.d. SOD-08 | Bagian SoD | Usulan & Final | S04, S18, S38, S50, S52–S53, S62–S63, S66, S68 |
| BR-13 | Semua keputusan akses & perubahan role/kewenangan dicatat dengan alasan; toggle hanya status terakhir; retensi mengikuti dokumen terpanjang (NDT 10 tahun) | [DOK] NDTPM 2.2; [TERKONFIRMASI] 5 Nov | Usulan (K36) | 54 baris audit log; S67 |
| BR-14 | Setiap tanda tangan sah menyimpan snapshot | KO-2d | Usulan | 13 snapshot |
| BR-15 | Company manual read-only untuk semua; disiapkan CI/MSTC, disetujui DoM | [DOK] MSPM 1.5–1.6 | Final | Matriks PB-01 |
| BR-16 | Menu tanpa izin disembunyikan; tombol approval nonaktif dengan keterangan aktor yang ditunggu | [RANCANGAN] M2-BRIEF | Final | — |
| BR-17 | Delegasi hanya APR, berbatas waktu, "atas nama" | [DOK] CMM 2.3.2, 2.3.3 | Usulan | S59–S62, S66 |
| BR-18 | Cakupan data per station (base kerja Employee Master) dan status dokumen | [TERKONFIRMASI] 5 Nov | Final | S07–S10, S69 |
| BR-19 | Approval berurutan; reject wajib alasan | [RANCANGAN] M4 | Final | S53–S55 |
| BR-20 | Perubahan role, workflow, SoD, keamanan: maker-checker (SYS-ADM → DIR-MNT) | Usulan | Usulan | — |
| BR-21 | Nomor dokumen dibuat saat simpan pertama, tidak berubah; format terpakai hanya dinonaktifkan | [RANCANGAN] R36 | Usulan (C17) | — |
| BR-22 | "Chief unit pembuat" diturunkan dari garis atasan role pengaju | [RANCANGAN] M4 | Final | S56–S57 |

## Kebutuhan non-fungsional keamanan

| ID | Kebutuhan | Nilai usulan | Dasar |
|---|---|---|---|
| NFR-01 | Password | Min 10 karakter, huruf + angka, beda dari 3 terakhir | [USULAN] |
| NFR-02 | Penguncian akun | 5 kali gagal; dibuka SYS-ADM atau otomatis 15 menit | [USULAN] |
| NFR-03 | Batas sesi | 30 menit tidak aktif; lebih pendek di perangkat bersama hanggar | [USULAN]; K40 |
| NFR-04 | Verifikasi ulang tanda tangan | PIN 6 digit atau password ulang pada aksi X & A | [KONFIRMASI] K38 |
| NFR-05 | Kecepatan `checkAuthority` | < 300 ms p95 | [USULAN] |
| NFR-06 | Audit log | Append-only, tidak bisa diubah/dihapus; retensi ≥ 10 tahun | [DOK] NDTPM 2.2; MTPM 2.7 |
| NFR-07 | Cakupan log | Semua keputusan akses & tanda tangan, termasuk penolakan + alasan per cek | [KONFIRMASI] K37 |
| NFR-08 | Waktu kejadian | Tanggal kejadian terpisah dari input; tanda tangan pakai waktu server | [RANCANGAN] EC-BRIEF |
| NFR-09 | Kredensial | HTTPS; password & PIN di-hash; gambar tanda tangan/stempel hanya untuk layanan tanda tangan | [USULAN] |
| NFR-10 | Efek perubahan kewenangan | Pembekuan, pencabutan, toggle OFF, perubahan base berlaku pada cek berikutnya tanpa menunggu cache | [DOK] MSPM 3.4.5 |
| NFR-11 | Ekspor audit | Audit trail & daftar personel berwenang ke Excel dan PDF | [KONFIRMASI] K26, K37 |
| NFR-12 | Tanda tangan offline | Tidak diizinkan; aksi X wajib online | [USULAN]; K40 |
| NFR-13 | Privasi data personel | Nomor lisensi, tanda tangan, stempel hanya untuk MSTC, CHF-INS, pemilik | [USULAN] |

## Keputusan baru (setelah 11 Nov)

| Kode | Tgl | Sesi | Keputusan → dampak | Acuan |
|---|---|---|---|---|
| | | | | |
