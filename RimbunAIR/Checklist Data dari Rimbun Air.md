---
tanggal: 2026-07-28
tipe: knowledge
tags: [requirement-gathering, checklist, data]
status: 1 selesai / 6 sebagian dari 31 butir · fokus: tutup titik buta alur PPC
---

# Checklist Data yang Dibutuhkan dari Rimbun Air

**Audiens:** 🔴 Internal saja — Berisi penilaian kelengkapan data klien. Untuk tim Nodewave.

> **Isi note ini:** daftar **dokumen dan data yang harus diminta** ke Rimbun Air.
> Kalau cari *pertanyaan proses yang belum terjawab*, itu ada di [[Proses Manual Maintenance - DRAFT]] (daftar TB).

Sumber: perluasan tabel "Need Information" (6 butir) di [[2026-07-27 Kickoff Nodewave x Rimbun Air]], diperlebar memakai entitas & failure point di `03-Knowledge/`

## Kenapa note ini ada

Saat note ini dibuat, vault ini **nol data spesifik Rimbun Air**. Semua yang ada di `03-Knowledge/` adalah riset industri generik: "armada tipikal perintis", "bandara perintis umumnya", "operator perintis biasanya". Tidak ada satu pun registrasi pesawat, nama stasiun, atau nama orang yang nyata.

Itu wajar — fase Requirement Gathering (bulan 0–3) memang untuk mengisi ini. Note ini adalah wadahnya, dan jadi ukuran seberapa jauh fase itu sudah berjalan.

Tabel di deck kickoff hanya menyebut 6 butir. Kalau hanya 6 butir itu yang diminta, beberapa entitas inti di [[Interval, Due Date & Forecasting Maintenance]] dan [[Eksekusi Work Order, Kewenangan & Kalibrasi]] tidak akan pernah terisi. Daftar di bawah menutup gap itu.

**Cara pakai.** Centang `[x]` begitu diterima, tulis lokasi filenya di kolom catatan. Butir bertanda 🔥 adalah blocker: tanpa itu, modul terkait tidak bisa dirancang sama sekali. Butir bertanda 🟡 sudah tersentuh sebagian tapi belum tuntas.

> 📌 **Jalur pengumpulan dokumen sudah ada.** Koordinator Rimbun Air diminta menyiapkan **folder Drive** berisi dokumen yang biasa dikerjakan tiap tim. Butir dokumen di bawah tidak perlu diminta satu-satu lagi di wawancara — cukup dipastikan masuk ke folder itu.

**Progress terakhir (2026-07-29).** Wawancara PPC ([[2026-07-29 Staff PPC & Engineering]]) menyentuh A2, B1, C1, C4, C5, D2, dan menutup D1: sistem lama **MSS ternyata project gagal** dan tidak dipakai — proses yang berlaku adalah alur manual.

Prioritas sekarang bergeser ke **kelompok F**: menutup enam titik buta di [[Proses Manual Maintenance - DRAFT]] supaya AS-IS-nya benar-benar utuh.

Tiga sample masih ditunggu: **spreadsheet [[Glosarium#L|LD/ND]]** (struktur kolomnya langsung jadi bahan skema DB), **satu paket dokumen lengkap** yang pernah diserahkan ke engineer, dan **Maintenance Program** versi terbaru.

---

## A. Orang & organisasi

*Tanpa ini, tidak ada yang bisa ditanya dan tidak ada yang bisa tanda tangan.*

- [ ] 🔥 **A1 — Project PIC / PM tunggal dari Rimbun Air.** Satu nama, satu nomor. Deck kickoff meminta ini "at kick-off". Ini yang menandatangani sign-off per sub-fitur; tanpa dia, seluruh alur agile Nodewave macet di langkah 4.
- [ ] 🟡🔥 **A2 — Process owner per modul.** *(sebagian: 3 Chief — Maintenance, PPC Engineering, Inspector. Pak Rian = PPC · Pak Heri = Inspektor Maintenance lapangan · Mbak Hilda = manual · **Pak Joko = Chief Line Maintenance Engineer** (maintenance control, penyetuju WO) · Pak Pipit = Staff OCC · Mas Bobi = pembuat MSS & koordinator. **Penerbit EO belum diketahui orangnya**. Nama lengkap & jabatan resmi belum ada)* Minimal: engineering/CAMO, planning, materials, procurement, costing, flight ops. Deck meminta "week 1". Nama + peran + ketersediaan jadwal wawancara.
- [ ] 🟡 **A3 — Struktur organisasi maintenance.** *(sebagian: 3 Chief teridentifikasi, plus Inspektor Quality & Safety terpisah)* Masih perlu: posisi [[Glosarium#C|CAMO]], dan siapa yang berwenang merilis pesawat. Menentukan role & permission matrix.
- [ ] **A4 — Daftar certifying staff + lisensi Part 65.** Nomor lisensi, rating/scope, tanggal expiry. → dibutuhkan entitas `Certifying Staff` untuk validasi sign-off WO; lihat [[Regulasi & Kepatuhan CASR Indonesia]].
- [ ] **A5 — Approval limit riil per jenis dokumen.** Deck memakai contoh IDR 50 Jt / 250 Jt — konfirmasi apakah itu angka Rimbun Air atau ilustrasi. Menentukan konfigurasi approval engine.

## B. Aset & konfigurasi

*Ini isi tabel master pertama yang harus ada sebelum modul apa pun jalan.*

- [ ] 🟡🔥 **B1 — Fleet register.** *(sebagian: **Boeing 737 Classic** 500 FH · **ATR** 1500 FH · satu model lagi 10000 FH yang tipenya belum diketahui. Registrasi PK-xxx dan jumlah unit belum ada)* Registrasi PK-xxx, tipe, MSN, tanggal masuk armada, status (aktif/stored/AOG). Vault saat ini masih menulis "armada tipikal: Caravan, Twin Otter, ATR…" — generik, bukan armada Rimbun Air.
- [ ] 🔥 **B2 — TSN/CSN aktual per pesawat + tanggal cut-off-nya.** *(catatan: untuk pesawat bekas, riwayatnya berasal dari pemilik sebelumnya — kelengkapannya perlu dicek)* Ini baseline yang menentukan seluruh perhitungan interval. Salah di sini = seluruh forecast maintenance salah.
- [ ] **B3 — As-built configuration per pesawat.** Komponen terpasang beserta posisi, PN, SN, [[Glosarium#T|TSN/TSO]], [[Glosarium#C|CSN/CSO]].
- [ ] 🔥 **B4 — Daftar [[Glosarium#L|LLP]] terpasang + sisa umur.** Life-limited parts adalah hard-stop; lihat [[Manajemen Sparepart & Supply Chain]]. Tanpa data ini sistem tidak bisa memblokir apa pun.
- [ ] 🔥 **B5 — Daftar base & stasiun operasi.** *(sebagian: Cengkareng, Halim, Bandung disebut sebagai lokasi kerja. **Premis "operator perintis Papua" ternyata salah dengar**)* Mana pangkalan utama, mana stasiun, mana yang punya gudang. **Ini yang menutup K2** — kalau semua di kota besar, offline-first tidak perlu dibangun.
- [ ] **B6 — Daftar GSE** (kalau modul 10 memang dipakai).

## C. Dokumen & aturan main

*Ini yang diterjemahkan jadi business rules.*

- [ ] 🟡🔥 **C1 — [[Glosarium#A|AMP/CAMP]] yang disetujui [[Glosarium#D|DGCA]].** *(sebagian: dikonfirmasi ada, disebut "Maintenance Program", diupdate setahun sekali — dokumennya belum diterima)* Sumber seluruh task card terjadwal. Deck tidak menyebut ini secara eksplisit — padahal ini dokumen paling menentukan untuk modul Program & Planning.
- [ ] 🔥 **C2 — [[Glosarium#M|MEL]].** Termasuk kategori deferral yang berlaku di armada Rimbun Air. Menentukan logika deferred defect; lihat [[Tech Log, Defect & Reliability Analysis]].
- [ ] **C3 — SOP tertulis per proses.** Deck meminta "week 1". Kalau SOP belum tertulis, itu temuan penting tersendiri: berarti BPMN dibangun dari wawancara murni, dan butuh waktu lebih lama.
- [ ] 🟡 **C4 — Daftar AD/SB terbuka + status compliance-nya.** *(sebagian: dikonfirmasi [[Glosarium#A|AD]] wajib & [[Glosarium#S|SB]] opsional — daftarnya belum diterima)* Harus terbawa ke sistem baru; AD lewat tenggat = systematic lock.
- [ ] 🟡🔥 **C5 — Form & template dokumen yang dipakai sekarang.** *(dinaikkan jadi blocker setelah wawancara PPC: merakit paket dokumen ternyata inti pekerjaan mereka. Sudah diminta satu paket dokumen lengkap yang pernah diserahkan ke engineer — belum diterima)* Work order, store issue, PO/RO, release. Menentukan layout "sign-ready PDF".
- [ ] **C6 — Riwayat audit/temuan [[Glosarium#D|DKPPU]] terakhir.** Temuan lama = daftar hal yang sistem baru wajib perbaiki, dan argumen terkuat untuk prioritas fitur.

## D. Sistem & data eksisting

*Ini menentukan apakah migrasi mungkin atau tidak.*

- [x] ~~**D1 — Akses ke sistem internal**~~ → **MSS: dibangun internal oleh Mas Bobi, aslinya untuk Store/Inventory, tidak cocok dipakai maintenance planning.** Proses yang berlaku alur manual (spreadsheet + kertas). Referensi, bukan blocker.
- [ ] **D1b — Batas integrasi dengan MSS** *(kalau modul material tetap di MSS)*. Karena MSS memang sistem Store, kemungkinan ia tetap dipakai untuk inventory — perlu diperjelas apakah sistem baru harus terintegrasi atau ada modul inventory baru.
- [ ] **D1c — Akses Google Drive tempat AMM/IPC disimpan.** Untuk melihat struktur & volume dokumen teknis yang sekarang diunduh manual.
- [ ] 🟡🔥 **D2 — Sample data riil dalam Excel.** *(sebagian: spreadsheet LD/ND sudah diminta ke PPC, belum diterima)* Master dan transaksi, dengan volume sebenarnya. Deck meminta "week 1". Ini juga bahan untuk menilai seberapa kotor datanya.
- [ ] 🟡 **D3 — Konektivitas per lokasi.** Turun prioritas: dengan basis di Cengkareng/Halim/Bandung, kemungkinan besar tidak jadi masalah. Cukup konfirmasi singkat bersama B5.
- [ ] **D4 — Data komponen terpasang per pesawat.** PN, SN, posisi, TSN/CSN. Yang saya butuh cuma komponen yang terpasang (untuk component transaction & LLP tracking) — stok gudang urusan modul 05.
- [ ] **D5 — Perangkat yang dipakai di lapangan.** Android/iOS, tablet atau HP, versi OS, milik perusahaan atau pribadi. Menentukan target build Flutter.
- [ ] **D6 — Sample arsip record yang harus dipertahankan.** Untuk menguji retention engine terhadap aturan [[Glosarium#C|CASR]].

## G. Verifikasi dari deep research

*Muncul dari tiga riset 29 Jul. Sebagian bisa dijawab tim Rimbun Air, sebagian harus dicek ke dokumen primer.*

- [ ] 🔥 **G1 — Besaran toleransi di AMP Rimbun Air.** 10%, 5%, atau nilai absolut? Menentukan algoritma inti.
  *Catatan 30 Jul: pemahaman awal tim adalah "tidak ada toleransi karena terkait izin terbang". Itu benar untuk LLP/CMR/Airworthiness Limitation, tapi untuk task terjadwal biasa praktik industri umumnya punya toleransi yang disahkan DKPPU di AMP. **Jangan tanya ke PPC — cek langsung ke dokumen AMP atau ke QA.***
- [ ] 🔥 **G2 — [[Glosarium#M|MPD]] per tipe.** Boeing 737 Classic, 737NG, dan ATR 72-600. Angka 500/1500/10000 FH baru dari wawancara, belum dari dokumen pabrikan.
- [ ] **G3 — Apakah ada task "Whichever Comes Last" di AMP?** Kalau ada, algoritmanya kebalikan dari [[Glosarium#W|WCF]].
- [ ] **G4 — Definisi jam di AMP: airborne atau block time?** Riset bilang airborne, tapi yang mengikat definisi di AMP mereka sendiri.
- [ ] **G5 — OpSpec extension deferral B & C.** Kalau DKPPU belum memberi kewenangan itu, tombol extension harus disembunyikan.
- [ ] **G6 — Varian mesin PT6A/PW127 yang dipakai.** Tiap varian punya ambang oli & torque baseline berbeda untuk [[Glosarium#E|ECTM]].
- [ ] **G7 — Template resmi [[Glosarium#D|DGCA Form 21-18]].** Format diatur ketat; modul cetak tidak boleh mengubah margin/font/urutan kotak.
- [ ] **G8 — Verifikasi angka retensi CASR ke JDIH Kemenhub.** Riset baru dan [[Regulasi & Kepatuhan CASR Indonesia]] menyebut angka berbeda — salah satu keliru.

## H. Yang menunggu sesi lanjutan

*Bukan dokumen, tapi jawaban yang cuma bisa didapat dari narasumber. Detail pertanyaannya ada di lembar wawancara masing-masing.*

- [ ] 🔥 **H1 — Sumber angka jam terbang** yang masuk ke LD/ND. Titik buta terbesar yang tersisa. → [[Lembar Wawancara PPC & Engineer - Sesi 2]]
- [ ] 🔥 **H2 — Rumus di spreadsheet LD/ND.** Terjawab sendiri kalau filenya bisa dilihat. → [[Lembar Wawancara PPC & Engineer - Sesi 2]]
- [ ] **H3 — Ambang penerbitan WO.** Angka tetap atau penilaian per kasus. → [[Lembar Wawancara PPC & Engineer - Sesi 2]]
- [ ] **H4 — Nomor revisi di task card.** Ditanyakan ke dua-duanya, karena keduanya menyentuh dokumen yang sama.
- [ ] **H5 — Ada [[Glosarium#R|RII]] atau tidak.** Menentukan satu aturan validasi keras. → [[Lembar Wawancara Inspector - Sesi 2]]
- [ ] **H6 — Alur penolakan dokumen** dan cara melacaknya. → [[Lembar Wawancara Inspector - Sesi 2]]
- [ ] **H7 — Tim arsip dokumen** siapa dan retensinya berapa lama. → [[Lembar Wawancara Inspector - Sesi 2]]
- [ ] **H8 — Defect & penundaan (MEL).** Belum tersentuh sama sekali di sesi mana pun.

## E. Administratif

- [ ] **E1 — Jadwal daily sync + slot progress report dua-mingguan.** Deck meminta ini "at kick-off".
- [ ] **E2 — Akses ke shared project folder + WhatsApp group.**
- [ ] **E3 — Kontrak/SPK final** beserta lampiran scope, supaya ada rujukan otoritatif saat terjadi sengketa scope.

---

## Yang tidak diminta deck kickoff tapi penting

Kalau waktu terbatas dan harus memilih, empat butir ini yang paling sering terlewat dan paling mahal akibatnya:

| Butir | Kenapa sering terlewat | Akibat kalau terlewat |
|---|---|---|
| **C1 — AMP/CAMP** | Dianggap "dokumen compliance", bukan requirement | Modul Planning dibangun tanpa sumber task card yang sah |
| **B4 — Daftar LLP** | Dikira bagian dari inventory biasa | Hard-stop tidak bisa diimplementasikan; risiko regulasi langsung |
| **D3 — Survei konektivitas** | Tidak ada di deck sama sekali | Arsitektur diputuskan berdasar asumsi, bukan fakta |
| **C6 — Temuan audit DKPPU** | Dianggap sensitif/internal | Kehilangan daftar prioritas fitur yang paling kredibel |

## Kenapa relevan buat project ini

Selama checklist ini mayoritas kosong, `03-Knowledge/` hanya berguna sebagai bekal bertanya — belum bisa jadi dasar PRD. Butir 🔥 yang belum terisi adalah blocker nyata, bukan sekadar to-do.

Terkait: [[Rekonsiliasi Scope - Riset vs Kontrak]] · [[Interval, Due Date & Forecasting Maintenance]]
