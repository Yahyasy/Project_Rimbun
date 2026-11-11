---
tipe: meta
modul: umum
diperbarui: 2026-11-11
tags: [mro, meta]
aliases: [Panduan Vault, README]
---
# Cara Pakai Vault

Vault ini adalah **sumber kebenaran tunggal** untuk empat lingkup yang dipegang Yahya di proyek MRO Rimbun Air: Modul 2, Modul 3, Modul 4, dan System Setting & Governance (RBAC). Semua gathering dimulai dari sini, dan semua hasil review klien kembali ke sini sebelum diturunkan ke Design Brief, ERD, Figma, atau PRD.

## 1. Struktur folder

```
MRO Rimbun Air/
├── 00 Home.md                  ← pintu masuk (MOC utama)
├── 00 Peta Vault.canvas        ← peta visual catatan utama
├── 00_Meta/                    ← cara pakai, alur kerja, kamus kode, changelog
├── 01_Konteks/                 ← proyek, peta modul & PM, REQ awal, armada, aktor, kontak
├── 02_Sumber/                  ← register dokumen klien & analisis, tautan Lucid/Figma/Drive
├── 10_M2 Maintenance Programming & Planning/
├── 20_M3 Production & Execution/
├── 30_M4 Flight Operations Interfacing/
├── 40_SSG System Setting & Governance/
├── 50_Lintas Modul/            ← kepemilikan data, integrasi end-to-end, isu harmonisasi
├── 60_Sesi & Review/           ← log sesi + satu catatan per sesi klien
├── 70_Glosarium/
├── 80_Template/                ← template sesi, menu, isu, baris register
└── 90_Arsip/                   ← ekspor dokumen analisis lama & versi yang sudah diganti
```

Setiap folder modul memakai pola yang sama, sehingga cara mencari sesuatu selalu sama:

| Catatan | Isi | Pertanyaan yang dijawab |
|---|---|---|
| `Mx Overview` | MOC modul: tujuan, lingkup, sub-modul, aktor, status, langkah berikutnya | "Modul ini apa dan sampai mana?" |
| `Mx SMn …` / catatan topik | **Kondisi akhir** per sub-modul dan menu: fungsi, aturan, status desain | "Apa yang harus dibangun?" |
| `Mx Alur & Status` / `Status Objek & Integrasi` | Diagram alur, status objek, aliran data | "Bagaimana user dan data bergerak?" |
| `Mx Decision Register` | Keputusan beserta tanggal, sesi, dan kode acuan | "Kapan dan atas dasar apa ini diputuskan?" |
| `Mx Open Questions` | Semua yang belum final, dengan usulan sementara | "Apa yang masih harus ditanyakan?" |

## 2. Hierarki kebenaran

Bila dua sumber berbeda, pakai urutan ini:

| Urutan | Sumber | Label bukti |
|---|---|---|
| 1 | Dokumen klien yang disetujui (MP per tipe, CMM, MSPM, MTPM, WBSPM, NDTPM, Roster) | `[DOK]` |
| 2 | Jawaban atau keputusan klien (tertulis atau di sesi review). **Tanggal terbaru menang.** | `[KLIEN]` |
| 3 | Konfirmasi PM / keputusan internal lintas PM | `[TERKONFIRMASI]`, `[RANCANGAN]` |
| 4 | Usulan tim yang dipakai sementara di desain | `[USULAN]` |

Dokumen analisis lama di `90_Arsip` dan di Project Claude adalah **bukti historis**, bukan acuan. Bila isinya berbeda dengan vault, vault yang berlaku selama catatan vault menyebut kode acuan yang lebih baru.

## 3. Aturan menulis

1. **Kondisi akhir, bukan riwayat.** Catatan sub-modul menulis apa yang berlaku sekarang. Riwayat ada di Decision Register dan [[Changelog Vault]].
2. **Setiap aturan punya label dan kode.** Format: `Aturan … — **Final** (R23, 8 Nov)`. Label: Final, Usulan, Menunggu (lihat [[Kamus Kode & Label]]).
3. **Usulan dan Menunggu selalu punya baris di Open Questions.** Kalau tidak ada barisnya, belum ada yang akan menanyakannya.
4. **Jangan menomori ulang kode lama.** Kode baru memakai pola di [[Kamus Kode & Label#Kode baru setelah 11 Nov 2026]].
5. **Tautkan, jangan salin.** Rujuk `[[M4 SM1 AFML & Flight Log#1.2 Closing AFML]]` alih-alih menyalin aturan ke catatan lain.
6. **Baris register tidak dihapus.** Keputusan yang berubah ditandai `Diganti oleh <kode>`; pertanyaan yang terjawab ditandai `Terjawab <tanggal>`.
7. **Kode lintas modul diberi awalan modul** karena huruf yang sama dipakai berbeda: `M2:K5`, `M3:K1`, `M4:P-02`, `SSG:P03`.

## 4. Properties (frontmatter)

| Properti | Nilai | Contoh |
|---|---|---|
| `tipe` | moc, modul, submodul, alur, data, register-keputusan, register-pertanyaan, konteks, sumber, sesi, lintas, glosarium, template, meta | `submodul` |
| `modul` | M2, M3, M4, SSG, lintas, umum | `M4` |
| `diperbarui` | tanggal terakhir isi catatan berubah | `2026-11-11` |
| `sumber` | dokumen atau sesi yang menjadi dasar | `claude/Keputusan_AFML_Modul4_4Nov.md` |
| `status` (catatan sesi) | dijadwalkan, berlangsung, triase, selesai | `triase` |
| `aliases` | nama lain agar mudah dicari | `[AFML, Flight Log]` |

Tag dipakai hemat: `#m2 #m3 #m4 #ssg #lintas`, ditambah `#perlu-update` untuk catatan yang tertinggal dari keputusan terbaru.

## 5. Plugin yang disarankan

- **Core (sudah ada di Obsidian):** Properties, Templates (folder `80_Template`, sudah diatur di `.obsidian/templates.json`), Backlinks, Outline, Canvas, Graph view. Diagram Mermaid tampil langsung tanpa plugin.
- **Opsional:** Dataview (daftar sesi dan catatan `#perlu-update` otomatis), Advanced Tables (mengedit tabel register), Obsidian Git (riwayat versi vault).

## 6. Bekerja bersama Claude

- Saat meminta analisis, lampirkan catatan modul yang relevan (Overview, sub-modul, Open Questions) agar konteksnya sama dengan vault.
- Minta keluaran dalam bentuk **baris register** (kolom sama dengan register modul) dan daftar **catatan yang terdampak**; itu yang langsung dimasukkan ke vault.
- Dokumen analisis panjang dari Claude disimpan di `90_Arsip`; yang masuk ke catatan modul hanya kondisi akhirnya.
