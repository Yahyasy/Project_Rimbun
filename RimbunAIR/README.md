# Vault RimbunAIR — Panduan

Vault kerja **Eza (Product Manager)** untuk project MRO Rimbun Air × Nodewave.
Difokuskan ke **3 modul yang saya pegang**: Maintenance Program & Planning · Production & Execution · Flight Operations Interfacing.

## Mulai dari mana

**Selalu [[Overview]] dulu.** Di situ ada status, daftar risiko, dan peta ke semua note lain. Kalau cuma punya dua menit, itu saja cukup.

## Satu note satu tugas

Tiap note punya baris **"Isi note ini"** di bagian atas. Kalau ragu buka yang mana, ini ringkasannya:

| Note | Tugasnya |
|---|---|
| [[Overview]] | Dashboard. Status, risiko, dan peta ke note lain |
| [[Scope]] | Apa yang harus dibangun. 3 modul, 16 requirement, batas dengan modul orang lain |
| [[Proses Manual Maintenance - DRAFT]] | Cara kerja Rimbun Air sekarang, plus **daftar TB** — pertanyaan proses yang belum terjawab |
| [[Checklist Data dari Rimbun Air]] | **Dokumen dan data** yang harus diminta ke klien |
| [[Glosarium]] | Kamus istilah |
| [[Rekonsiliasi Scope - Riset vs Kontrak]] | Latar belakang risiko scope. Arsip alasan, bukan tracker |
| [[Riwayat Koreksi]] | Hal yang sempat salah dicatat lalu diperbaiki. Note lain hanya menulis keadaan sekarang |
| 3 note domain di `03-Knowledge` | Teori standar industri per modul. Bukan praktik Rimbun Air |
| `01-Meetings` | Rekaman percakapan + bahan wawancara. Yang dibawa ke ruangan namanya diawali `_Lembar`. Metode wawancaranya di [[Instruksi Wawancara]] |

## Penanda audiens

Tiap note punya baris **Audiens** di bawah judul. Tiga tingkat:

| | Arti |
|---|---|
| 🟢 | Boleh ditunjukkan ke Rimbun Air |
| 🟡 | Untuk tim Nodewave |
| 🔴 | Internal — berisi penilaian risiko klien atau konflik kontrak, **jangan dibagikan** |

Cek penandanya sebelum membagikan apa pun keluar.

## Dua daftar bernomor, jangan tertukar

Ini yang paling sering bikin bingung, jadi sengaja dipisah tegas:

- **TB1–TB6** — pertanyaan **proses** yang belum terjawab. Rumahnya di [[Proses Manual Maintenance - DRAFT]], karena butuh konteks alurnya.
- **A–E, G** — **dokumen dan data** yang harus diminta ke klien. Rumahnya di [[Checklist Data dari Rimbun Air]].

Kalau sesuatu adalah *pertanyaan*, itu TB. Kalau sesuatu adalah *barang yang diminta*, itu checklist. Tidak ada yang muncul di dua tempat.

Daftar **risiko** hanya ada satu, di [[Overview]]. Note lain boleh menjelaskan latarnya, tapi tidak menyimpan daftar tandingan.

Begitu juga **action item**: versi gabungan yang masih terbuka ada di bagian *Tindakan berikutnya* di [[Overview]]. Tiap MoM tetap menyimpan versi aslinya lengkap dengan konteks — tapi kalau mau tahu apa yang harus dikerjakan, cukup buka Overview.

## Struktur folder

| Folder | Isi |
|---|---|
| `00-Inbox` | File kerja sementara, termasuk hasil export CSV |
| `01-Meetings` | MoM + panduan wawancara, format `YYYY-MM-DD Judul.md` |
| `02-Decisions` | Decision log yang masih hidup |
| `03-Knowledge` | Riset domain untuk 3 modul saya |
| `04-Daily` | Daily note — 3 baris: dikerjain apa, blocker, next step |
| `99-Templates` | Template, jangan diedit |

Tiga subfolder sengaja disingkirkan dari pandangan sehari-hari:

| Subfolder | Isi | Kapan dibuka |
|---|---|---|
| `03-Knowledge/_di-luar-scope` | Kargo, sparepart, benchmark vendor. Plus note konteks Papua yang **premisnya salah** — jangan dipakai | Kalau scope melebar |
| `02-Decisions/_di-luar-scope` | Decision project-level yang sudah tertutup | Kalau ditanya "kenapa dulu diputuskan begitu" |
| `03-Knowledge/_sumber-mentah` | Hasil riset mentah, sudah disuling | Kalau perlu verifikasi |

## Konvensi

- **Wawancara** → copy `99-Templates/mom-wawancara.md` ke `01-Meetings/YYYY-MM-DD Fungsi.md`. Siapkan **sebelum** sesi, isi bagian 1–3 dalam 30 menit setelah keluar
- **Meeting biasa** → copy `99-Templates/meeting.md` ke `01-Meetings/YYYY-MM-DD Judul.md`
- **Keputusan** → copy `99-Templates/decision.md` ke `02-Decisions/Decision - Judul.md`, isi `status:` di frontmatter
- **Riset baru** → copy `99-Templates/knowledge.md` ke `03-Knowledge/`
- **Daily** → copy `99-Templates/daily.md` ke `04-Daily/YYYY-MM-DD.md`
- **Link** pakai `[[Nama File]]` tanpa path — supaya tidak rusak saat file dipindah folder

## Disiplin yang sudah terbukti berguna

1. **Tandai asumsi.** Tulis `(asumsi)` untuk apa pun yang belum dikonfirmasi narasumber, dan kumpulkan di satu bagian "perlu dikonfirmasi".
2. **Jangan telan riset mentah.** Sudah sembilan kali kita menangkap catatan yang keliru — daftarnya di [[Riwayat Koreksi]]. Semuanya tertangkap karena ada pembanding, bukan karena dibaca ulang lebih teliti.
3. **Pisahkan regulasi, praktik industri, dan pilihan desain.** Ketiganya gampang tertukar, dan akibatnya mahal saat jadi requirement.
4. **Selisih antara praktik lapangan dan standar industri adalah daftar kerja** — entah sistem yang menyesuaikan, atau kebiasaan yang harus berubah. Putuskan sadar-sadar, jangan dibiarkan ketahuan saat UAT.

## Setup git

Belum di-init. Kalau mau:

```bash
cd ~/Projects/Obsidian/RimbunAIR
git init
cat > .gitignore << 'GIT'
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.obsidian/plugins/*/data.json
.DS_Store
GIT
git add .
git commit -m "Initial vault structure"
```

Repo-nya **private** — isinya catatan kerja klien.
