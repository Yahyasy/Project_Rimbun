---
tipe: submodul
modul: M4
diperbarui: 2026-11-11
sumber:
  - claude/Flow_Detail_Modul4_per_Submodul_Menu_3Nov.md
  - claude/Review_Desain_Modul4_Keseluruhan_3Nov.md
tags: [m4, lintas]
aliases: [CML, Cabin Maintenance Log, Approval Inbox M4]
---
# M4 SM7 CML & Lintas

## 7.1 CML (Cabin Maintenance Log)

| Langkah | Aturan | Status | Acuan |
|---|---|---|---|
| G1 Catat item | Langsung atau dari **Transfer to CML** (membawa defect asal & halaman AFML); item langsung berlabel "recorded directly". Isian: **No. halaman buku CML** (bukan AFML page), flight number, deskripsi wajib, cabin location dari **master berkelompok**, reported by dari Employee Master; report time & station tidak wajib; due date opsional | Final; pelapor (cabin crew/pilot/maintenance kabin) Menunggu | CML-01–CML-04, CML-06, CML-07 |
| G2 Jadwalkan perbaikan | CML open bisa masuk forecast M2; pengerjaan lewat WO belum dirancang | Menunggu | CML-08, Q-43 M3, M2 no 103 |
| G3 Closing | Oleh engineer kabin dengan **otorisasi aktif**, tanpa approval; overdue ditandai | Final; syarat penutup Q26-08 | CML-05 |

Status CML: **Open → Closed**. Label "[Candidate]" dihapus karena CML sudah menjadi menu.

## 8.x Lintas

| Menu | Isi | Status |
|---|---|---|
| 8.1 Approval Inbox | Satu kotak masuk untuk: DMI Extension (Chief Inspector → Director of Operation), RQ (chief unit pembuat → direktur teknik; Approve/Revision/Reject, catatan wajib untuk Revision & Reject), **Robbed** dan **Swap** sebagai dua jenis pengajuan (Director of Maintenance) | Belum didesain |
| 8.2 Pengaturan Notifikasi | Ambang jatuh tempo DMI (default 10% sebelum batas) dan penerima; usulan: pengingat halaman Waiting TR > 1 hari, notifikasi Alert Status 2 & 3; kanal in-app, email, WhatsApp | Belum didesain (usulan) |
| 8.3 Template Form & Penomoran | Format nomor defect (halaman + item + urut 7 digit tanpa reset tahunan), DMI, AOG & Serviceable per jenis form, DMI Extension, RQ; nomor dibentuk saat simpan pertama, read-only | Belum didesain |
| 8.4 Riwayat Dokumen Cetak | Draft, Printed, Signed Uploaded untuk declaration, DMI Log, DMI Extension, Robbed Part Form, RQ; scan bertanda tangan diunggah | Belum didesain |

> [!question] 8.1–8.4 dibangun di M4 atau di SSG?
> PRD SSG mengusulkan Menu 8.1–8.4 **diganti** layanan pusat: SSG-07 Approval Inbox, SSG-11 Aturan Notifikasi, SSG-10 Master Format Penomoran, SSG-12 Audit Trail & Log (termasuk log cetak). Karena keduanya dipegang Yahya, putuskan sebelum Gelombang 3 desain. Lihat LX-02 di [[Isu Harmonisasi Lintas Modul]].

## Butir terbuka

Q26-07 (pelapor CML), Q26-08 (syarat penutup), Q26-09 & CML-08 (CML masuk forecast), CT-08 (approval & cetak Swap), daftar jabatan dan matriks role untuk approver.
