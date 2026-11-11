---
tipe: register-pertanyaan
modul: SSG
diperbarui: 2026-11-11
sumber:
  - claude/PRD_System_Setting_Governance_RBAC.md
tags: [ssg]
aliases: [Open Questions SSG, Gap SSG, Klarifikasi RBAC]
---
# SSG Gap & Klarifikasi

25 pertanyaan (17 ke Rimbun Air, 8 ke PM lain); **3 terjawab 5 Nov** (Q03, P07, P08). Selama belum dijawab, usulan default dipakai di matriks dan PoC. Prioritas Tinggi yang terbuka (Q01, Q02, Q04–Q06, P01–P03) harus terjawab sebelum SSG-02, SSG-03, SSG-04 dikunci.

## Ke Rimbun Air

| Kode | Prioritas | Pertanyaan | Usulan default | Terkait | Status | Jawaban |
|---|---|---|---|---|---|---|
| Q01 | Tinggi | 13 role baru disetujui? Satu orang boleh lebih dari satu role? Perkiraan jumlah user per role? | Ya, multi-role | K35, K35c, K6, G01, G02, BR-02 | Menunggu | |
| Q02 | Tinggi | Safety Manager dan Chief Maintenance memakai sistem? Chief Maintenance = Chief Line Maintenance? | Chief Maintenance = Chief LM; Safety Manager dicatat Chief Inspector | K5, K35; M2 no 113 | Menunggu | |
| Q03 | Tinggi | Siapa mengubah toggle Fungsi Approval? | — | G10, BR-06, S41 | **Terjawab 5 Nov** | Chief Inspector dan Inspector |
| Q04 | Tinggi | Katalog scope: C Check, Brake Assy, RTS Avionic Task; WI untuk B737-800? Koreksi teks "Batik Air" di MSPM 3.2 dan nomor manual NDT | Tambah C Check & Brake Assy; WI hanya ATR72 | G03, G04, G08, G12, S21 | Menunggu | |
| Q05 | Tinggi | Data Roster: FP (RAA-11), PFDI (RAA-34), C Chek (RAA-29), PN 261231.2-1 (WBS-01), ATR72-600 vs 212A | FP = PF; PFDI = PF, DI; PN sama; ATR72-600 varian 212A | G05–G07 | Menunggu | |
| Q06 | Tinggi | Data kartu RAA-TCI-015 (terbit, habis), level NDT, contoh form OTA | Diperlukan sebelum migrasi | G09, G14, G15 | Menunggu | |
| Q07 | Sedang | Approver WO, Shop WO, GSE WO, laporan reliability & alert level, koreksi AFML, material request? | WO: Chief PPC; Shop WO: Chief WBS; koreksi AFML: Chief LM | WF-WO; M4 K5-08 (koreksi tanpa approval) | Menunggu | |
| Q08 | Sedang | Approval payment DT & MD berurutan atau paralel; batas nominal? | Berurutan DT lalu MD | WF-PAY | Menunggu | |
| Q09 | Sedang | Scrap Report ditandatangani Tool & Equipment Inspector atau Receiving Inspector? | Tool & Equipment Inspector (MSPM 5.7.2) | G11 | Menunggu | |
| Q10 | Sedang | PIN / password ulang saat tanda tangan diterima untuk audit DGCA? | PIN 6 digit | K38, NFR-04 | Menunggu | |
| Q11 | Sedang | Masa simpan audit trail dan format ekspor audit? | 10 tahun; Excel & PDF | K26, K36, K37, G13 | Menunggu | |
| Q12 | Sedang | Kanal notifikasi; penerima pengingat kewenangan H-30? | In-app & email; chief departemen & pemegang | K9; M2 no 118 | Menunggu | |
| Q13 | Sedang | Format nomor dokumen per jenis (STE, WO, CRS, EO, RQ, OTA) dan periode reset | Diisi di SSG-10 | C17, R36, BR-21 | Menunggu | |
| Q14 | Sedang | Pilot / Flight Dispatch Control login langsung (Modul 4)? | Tidak pada tahap awal; data diinput Line Engineer | Interview M4 | Menunggu | |
| Q15 | Rendah | Akun Auditor hanya-baca berbatas waktu? | Ya, maks 30 hari | AUDITOR, K37 | Menunggu | |
| Q16 | Rendah | Kebijakan password/sesi/perangkat bersama dari IT; tanda tangan offline di station? | NFR-01–03; tanda tangan wajib online | K40, NFR-12 | Menunggu | |
| Q17 | Rendah | Chief/manager Procurement, Finance, GSE sebagai approver? | Perlu nama posisi | Jenjang manager | Menunggu | |

## Ke PM modul lain

| Kode | Untuk | Prioritas | Pertanyaan | Usulan | Status | Jawaban |
|---|---|---|---|---|---|---|
| P01 | PM M1 (EC) | Tinggi | Enum role diganti FK ke role SSG; `employee_authorization` diperluas; tab Kewenangan Approval dikelola SSG-04? | Ya | Menunggu | |
| P02 | PM M1 & M2 | Tinggi | Pemilik master tipe pesawat, kolom family, relasi varian ATR72-600 | Satu master tipe dengan `family` & `parent_type_id`; tipe diinput di M2 (M2 no 19) | Menunggu | |
| P03 | Semua PM | Tinggi | Validasi baris matriks; pindahkan pengaturan per modul ke SSG | Ya | Menunggu | |
| P04 | PM M5 | Sedang | Penanda tangan scrap dan approver material request | Tool & Equipment Inspector; Store | Menunggu | |
| P05 | PM Wisnu (M6, M8, M10) | Sedang | Approver budget, payment, GSE WO; posisi chief Procurement, Finance, GSE | Perlu data posisi | Menunggu | |
| P06 | PM Gamma / Fadly (M7, M9, M11) | Rendah | Hak akses Document Record dan approver Shop WO | Matriks PB-01 & WS-01 | Menunggu | |
| P07 | PM M1 | Sedang | Penugasan di luar base kerja | — | **Terjawab 5 Nov** | Perbarui base kerja di Employee Master |
| P08 | PM M1 | Sedang | Riwayat perubahan toggle perlu disimpan? | — | **Terjawab 5 Nov** | Tidak perlu; hanya status terakhir |

## Konflik dan gap antar dokumen

| ID | Area | Temuan | Perlakuan sementara | Klarifikasi |
|---|---|---|---|---|
| G01 | Struktur organisasi | ORG STRUCTURE REQ tanpa Wheel & Brake Shop, memisahkan Engineering Staff; CMM/MSPM memuat 4 chief | Pakai CMM/MSPM | Q01 |
| G02 | Daftar role | Enum EC 11 posisi + 3 temuan; 13 fungsi belum punya role | Role dikelola SSG | P01, Q01 |
| G03 | Katalog scope | Roster memakai C Check, Brake Assy yang tidak ada di MSPM 3.2 | Tambah ke katalog | Q04 |
| G04 | Keberlakuan WI | Roster: WI untuk B737-800; MSPM: WI hanya ATR72 | PoC menolak (S21) | Q04 |
| G05 | Penulisan scope | FP, PFDI, C Chek, "A (Phase Check))" | Normalisasi; FP tidak diubah | Q05 |
| G06 | PN workshop | 261231.2-1 vs 2612312-1 | Simpan apa adanya | Q05 |
| G07 | Tipe pesawat | Rating ATR72-600 vs armada ATR72-212A | Relasi varian | Q05, P02 |
| G08 | Teks manual | MSPM 3.2 menyebut "Batik Air policy" | Sampaikan ke MSTC | Q04 |
| G09 | Nomor form | MSPM 3.5 vs 3.4.1 tentang RAA-TCI-015 | Konfirmasi form OTA | Q06 |
| G10 | Toggle | EC-BRIEF: semua Chief; MSPM: hanya CI | **Terjawab** 5 Nov: CI & Inspector | Q03 |
| G11 | Penanda tangan scrap | MSPM 5.7.2 vs ML-BRIEF | Konfirmasi | Q09, P04 |
| G12 | Nomor dokumen NDT | BT-MNT-02.04 vs RAA-MNT-02.02 | Sampaikan ke MSTC | Q04 |
| G13 | Riwayat kewenangan | EC tanpa riwayat; NDTPM 10 tahun, MTPM 2 tahun setelah keluar | Riwayat di `authorization_event`; toggle tanpa riwayat | Q11 |
| G14 | Tanggal kartu | Roster tanpa tanggal terbit/habis | Minta data RAA-TCI-015 | Q06 |
| G15 | Level NDT | Roster tanpa level NDT-01 | Minta sertifikat | Q06 |
| G16 | Tumpang tindih Task Card | M2 Menu 16–20 dan M3 Menu 5 sama-sama eksekusi | **Selesai**: eksekusi di M3 (M2 no 4) | P03 |
| G17 | Nama modul 7 | Publication vs Document Record | Pakai Document Record | P06 |

Lima temuan (G03–G07) menunjukkan Roster ditulis bebas tanpa daftar kode; katalog scope SSG-03 menutup celah ini.
