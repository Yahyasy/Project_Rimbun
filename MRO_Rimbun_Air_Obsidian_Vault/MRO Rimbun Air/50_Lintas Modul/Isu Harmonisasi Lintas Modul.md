---
tipe: lintas
modul: lintas
diperbarui: 2026-11-11
tags: [lintas, perlu-update]
aliases: [Isu Lintas Modul, LX, Konflik Antar Modul]
---
# Isu Harmonisasi Lintas Modul

Isu yang muncul karena dua dokumen atau dua modul mengatur hal yang sama secara berbeda. Setiap isu punya **pemilik keputusan** dan **catatan yang harus diubah** setelah diputuskan. Kode `LX-nn` tidak dipakai ulang.

| Kode | Isu | Posisi A | Posisi B | Pemilik keputusan | Catatan terdampak | Status |
|---|---|---|---|---|---|---|
| LX-01 | Batas DMI di forecast | M2 no 54 (23 Okt): DMI hanya due date, tanpa FH/FC | M4 K6-04 (6 Nov): Limit Type tanggal, FH, atau FC | Yahya (M2 & M4) | [[M2 SM2 Planning & Forecast]], [[M2 Decision Register]], [[M4 SM2 Defect & Deferred]] | Terbuka — usulan: forecast membaca Limit Type, sisa FH/FC dihitung ulang saat closing AFML |
| LX-02 | Pengaturan yang tersebar per modul | M2: Format Nomor (27), Pengaturan Role STE (13.3), Notifikasi Due (14); M3: WO Number Setup; M4: 8.1 Approval Inbox, 8.2 Notifikasi, 8.3 Penomoran, 8.4 Riwayat Cetak | SSG D7: dipusatkan di SSG-06, 07, 10, 11, 12 | Yahya (semua modul) + PM M1 untuk C17 | Semua Overview modul, [[SSG Sitemap & Menu]] | Terbuka — putuskan sebelum desain Gelombang 3 M4 |
| LX-03 | Lokasi OTA | Review klien 19 Okt (B-03): OTA Record pindah ke Modul 1 (EC) | PRD SSG: OTA Record ke SSG-05 karena OTA adalah kewenangan | Yahya + PM M1 (Fadly) | [[SSG Model Governance & Kewenangan#One Time Authorization (OTA)]], [[M3 Decision Register]] | Terbuka — usulan: data OTA di SSG, layar boleh di M1 bila klien tetap meminta |
| LX-04 | Workflow RQ dan Swap | PRD WF-RQ: satu langkah (chief unit pengaju); belum ada WF-SWAP | M4: dua langkah (chief unit pembuat → direktur teknik, P-02); Swap proses tersendiri (K5-04); RQ dari WO approve Chief PPC & Engineering (M3 Q-47) | Yahya; klien untuk P-02 dan CT-08 | [[SSG Workflow SoD Aturan & NFR]], [[M4 SM6 RQ]], [[M4 SM3 Component Transaction]] | Terbuka |
| LX-05 | Nama tiga konsep ad-hoc | M2 no 98 | M3 Q-19 (sama) | Rimbun Air | Glosarium, M2/M3 | Terbuka — usulan "Ad-hoc Task Card" (WO) dan "Non-routine Task" (M1) |
| LX-06 | Pemicu last done | M2 no 105 | M3 Q-M2-08 (sama) | Rimbun Air | [[M2 Alur & Status]], [[M3 Task Card di WO]] | Terbuka — usulan task card Closed |
| LX-07 | Matriks RBAC M2–M4 tertinggal | PRD (16 Okt, rev 5 Nov) memakai menu sebelum review 19 Okt–6 Nov | Menu terbaru: M3 tanpa CRS/OTA; M4 3.6 Swap, Fluid 4.1–4.3, tab Reliability baru; M2 Hard Time | Yahya | Workbook `rbac_data.py`, [[SSG Role & Matriks RBAC]] | Terbuka — perbarui `rbac_data.py`, jalankan ulang PoC |
| LX-08 | Sumber stamp & otorisasi | M3/M4: stamp & otorisasi dari Employee Master M1 | SSG: `employee_authorization` dikelola dari SSG-04, layanan `checkAuthority` (P01) | PM M1 (Fadly) | [[M3 Task Card di WO]], [[M4 SM1 AFML & Flight Log]], [[SSG Data Integrasi & PoC]] | Terbuka — tunggu P01 |
| LX-09 | Pemilik master tipe pesawat | M2 no 19: tipe diinput di M2 (dikonfirmasi 8 Nov) | SSG P02 / M2 KO-1: pemilik master, kolom family, varian | PM M1 + Yahya | [[Armada & Tipe Pesawat]] | Sebagian — input di M2 final; struktur varian terbuka |
| LX-10 | Pemegang layar Pending Install/RTS, return consumable | M3 K1 & Q-34 bergantung pada layar ini | M5 belum menetapkan (Q28-12) | PM M5 (Fadly) | [[M3 Material Tool & Part]] | Terbuka |
| LX-11 | Event WO Closed ke M4 dan M5 | M3: DMI Closed by WO + return consumable ditutup | Bentuk event belum disepakati (Q-27, Q-36) | Yahya + PM M5 | [[M3 Integrasi & DMI]] | Terbuka |
| LX-12 | Pembagian PM | REQ: GAMMA service 1; PRD P06: Gamma M7, M9, M11 | Catatan Okt: Fadly M1, M5, M7, M9 | Manajemen proyek | [[Peta Modul & PM]] | Konfirmasi |

## Cara menutup isu

1. Putuskan (sesi internal PM atau ke klien) dan catat sebagai keputusan di register modul pemilik.
2. Ubah semua catatan di kolom *Catatan terdampak*; hapus tag `#perlu-update` bila sudah sinkron.
3. Ubah Status menjadi `Selesai <tgl> → <kode keputusan>`.
