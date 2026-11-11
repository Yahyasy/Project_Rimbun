---
tipe: moc
modul: SSG
diperbarui: 2026-11-11
sumber:
  - claude/PRD_System_Setting_Governance_RBAC.md
tags: [ssg]
aliases: [RBAC, System Setting & Governance, SSG, PRD RBAC]
---
# SSG System Setting & Governance (RBAC) — Overview

> [!abstract] Posisi 11 Nov 2026
> PRD rev 52 (diperbarui 5 Nov) berstatus **draft untuk direview PM modul lain** sebelum dikonfirmasi ke Rimbun Air. PoC dijalankan ulang 5 Nov: **69 dari 69 skenario lulus**. Tiga klarifikasi sudah terjawab (Q03, P07, P08). Butir prioritas Tinggi yang masih terbuka (Q01, Q02, Q04–Q06, P01–P03) menahan penguncian desain SSG-02, SSG-03, SSG-04.

## Tujuan

Satu tempat yang mengatur tiga hal untuk **seluruh modul** sistem MRO: **siapa boleh masuk**, **menu dan aksi apa yang boleh dipakai**, dan **tanda tangan siapa yang sah**. Dibutuhkan karena Employee Master (M1) menyatakan login dan hak akses di luar cakupannya, sementara Modul 2, 3, dan 4 masing-masing mulai membuat pengaturan role, approval, notifikasi, dan penomoran sendiri.

## Keputusan desain utama

| No | Keputusan | Dasar |
|---|---|---|
| D1 | **Akses dipisah dari kewenangan**: role (RBAC) menentukan menu & aksi; Company Authorization menentukan sah tidaknya tanda tangan. Aksi tanda tangan wajib lolos keduanya | MSPM 3.1 #1; Roster 2.3 |
| D2 | Role = fungsi × jenjang, dipetakan ke posisi CMM; satu user boleh banyak role | REQ user & jabatan; 9 personel multi-kategori di Roster |
| D3 | Spesialis (NDT, Borescope, RII, EGR, W&B, Compass Swing) adalah **scope kewenangan**, bukan role | MTPM 4.1; Roster 2.5–2.7 |
| D4 | Kewenangan terikat tipe pesawat (atau daftar PN untuk workshop), berlaku maks **1 tahun** | Roster 2.3, 2.8; MSPM 3.4.4 |
| D5 | Hanya **Chief Inspector** yang menerbitkan, membekukan, mencabut, memulihkan kewenangan | MSPM 3.4.1, 3.4.5; CMM 2.3.4 |
| D6 | Akun user selalu berasal dari **Employee aktif** | Klien, M3-QA no 7 |
| D7 | Approval workflow, approval inbox, penomoran dokumen, aturan notifikasi **dipusatkan** di SSG | M2 13.4, 14, R36; M3 Menu 10–11; M4 8.1–8.3 |
| D8 | Perubahan role & kewenangan dicatat riwayatnya; **toggle approval hanya status terakhir** | [TERKONFIRMASI] 5 Nov; NDTPM 2.2 |

## Lingkup

| Termasuk | Di luar |
|---|---|
| Akun user (dari Employee), status, reset password, riwayat login | Data induk karyawan, lisensi, tanda tangan & stempel (tetap di Employee Master M1) |
| Role, permission per modul–menu–aksi, cakupan data | Catatan training (Training Master M1); status training hanya peringatan |
| Katalog scope & siklus Company Authorization, OTA | Proses bisnis tiap modul (SSG hanya layanan cek) |
| Toggle Fungsi Approval per personel | Dokumen Roster RAA-MNT-03.02 (klien: bukan scope) |
| Approval workflow, inbox terpusat, delegasi | Integrasi SSO / direktori perusahaan |
| Aturan SoD, master penomoran, aturan notifikasi | |
| Audit trail, kebijakan keamanan | |

## Catatan SSG

- [[SSG Model Governance & Kewenangan]] — 4 lapis cek, `checkAuthority`, siklus Company Authorization, OTA, normalisasi Roster
- [[SSG Role & Matriks RBAC]] — 25 role, 8 aksi, cakupan data, ringkasan matriks per modul
- [[SSG Sitemap & Menu]] — 15 menu dan acceptance criteria
- [[SSG Workflow SoD Aturan & NFR]] — 15 workflow, SOD-01–08, BR-01–22, NFR-01–13
- [[SSG Data Integrasi & PoC]] — ERD 26 entitas, integrasi per modul, PoC 69 skenario
- [[SSG Gap & Klarifikasi]] — G01–G17, Q01–Q17, P01–P08

## Langkah berikutnya

1. Review internal PRD & matriks bersama PM lain; tiap PM memvalidasi baris modulnya dan menjawab P01–P06.
2. Kirim Q01, Q02, Q04–Q17 ke Rimbun Air bersama tabel gap (prioritas Q01, Q02, Q04–Q06).
3. Minta data kartu RAA-TCI-015 dan sertifikat level NDT untuk migrasi register kewenangan.
4. Masukkan jawaban ke `rbac_data.py`, jalankan ulang PoC & workbook, perbarui status di vault.
5. Susun wireframe 15 menu SSG dan spesifikasi API `checkAccess`, `checkAuthority`, `approve`, `signatureSnapshot`.
6. Sepakati urutan pemindahan menu pengaturan dari EC, M2, M3, M4 ke SSG ([[Isu Harmonisasi Lintas Modul]]).
