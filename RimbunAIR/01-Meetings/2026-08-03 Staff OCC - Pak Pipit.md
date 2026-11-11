---
tanggal: 2026-08-03
tipe: meeting
tags: [wawancara, occ, afml]
status: final
---

# Staff OCC — Pak Pipit

**Audiens:** 🔴 Internal saja — berisi penilaian. Jangan dibagikan ke narasumber.

> ⚠️ **OCC di luar 10 modul kontrak.** Sesi ini untuk memahami hulu data, bukan mengumpulkan requirement. Tidak ada fitur yang dijanjikan.

> **Sesi terpendek, hasil paling tajam.** 26 menit, dan menutup ujung paling hulu dari rantai jam terbang — sumber angka yang menopang seluruh modul saya.

---

## Info sesi

| | |
|---|---|
| **Tanggal** | 3 Agustus 2026, sore · ±26 menit |
| **Narasumber** | **Pak Pipit** — Staff OCC, departemen Operasional |
| **Lokasi kerjanya** | **Bandara Cengkareng** — satu lokasi dengan engineer |
| **Tempat** | Daring |
| **Hadir dari kita** | Eza |
| **Rekaman** | Ada · transkrip di `_sumber-mentah/Mentahan Transcript - Staff OCC - Pak Pipit.csv` |
| **Verifikasi** | [[Tanya Jawab - Sesi 3 Agustus]] |

---

## 1 · Kesan langsung

**Tiga hal yang paling nempel:**

1. **Pekerjaannya sempit dan satu arah** — pada dasarnya satu hal: memindahkan data penerbangan ke sistem. *"Selain itu sih nggak ada, semua data itu kembali ke AFML."*
2. **Masalah utamanya bukan angka, tapi nomor.** Block on/off dan take off/landing hampir tidak pernah selisih. Yang sering salah adalah **nomor AFML**-nya.
3. **Dia tidak tahu datanya dipakai untuk maintenance.** Chief-nya cuma bilang sesi ini soal *"pengsinkronan jam terbang"*, dan dia mengira ini tentang jam terbang pilot.

**Yang di luar dugaan:** ada **dua pengirim independen** untuk data yang sama — co-pilot dan engineer lapangan — dan OCC membandingkan keduanya. Pemeriksaan silang itu tidak pernah muncul di sesi mana pun.

**Yang terasa dia ragu:** saat ditanya apakah sinkronisasi ke MSS berjalan otomatis. Dijawab *"iya betul… kalau nggak salah"*.

---

## 2 · Yang dipelajari

### Perannya

Menerima data penerbangan, mengisi kolom *actual* beserta nomor AFML, memastikan cocok antara dua sumber. Bisa juga mencatat keterangan gangguan teknis atau force majeure langsung di sistem.

### Alur kerjanya

1. **Pilot & co-pilot** mengisi AFML di pesawat — bahan bakar dipakai, bahan bakar sisa, actual take off, touchdown
2. **Co-pilot mengirimkan data lengkap** dalam **format baku**
3. Paralel: **engineer lapangan mengirim foto AFML**
4. **OCC membandingkan keduanya** — siapa pun yang datang duluan, dicek silang dengan yang lain
5. OCC mengisi kolom *actual* + **nomor AFML** di sistem OCC
6. **Sinkron otomatis ke MSS** — kuncinya **nomor AFML**
7. Hilir: Mba Michelle merekonsiliasi hard copy vs MSS

> **Grup WhatsApp berfungsi sebagai backup dan jalur konfirmasi**, bukan kanal utama. Kalau ada selisih, pengecekannya lewat WhatsApp.

### Dokumen yang disebut

| Dokumen                   | Dari siapa                   | Ke siapa       | Bentuk                         |
| ------------------------- | ---------------------------- | -------------- | ------------------------------ |
| [[Glosarium#A\|AFML]]     | Pilot & co-pilot, di pesawat | Engineer & OCC | Buku, nomor **ditulis manual** |
| Data penerbangan co-pilot | Co-pilot                     | OCC            | **Format baku**                |
| Foto AFML                 | Engineer lapangan            | OCC            | Foto                           |

### Angka & fakta struktural

- **Satu AFML = satu rute, bukan satu cycle.** CGK–UPG–CGK = **satu AFML, dua cycle**
- **Kru atau engineer ganti → AFML baru**, walau rutenya sama
- Nomor AFML berurut manual — contoh kesalahan: ditulis `01011` padahal seharusnya `01012`
- Template AFML **sama untuk semua rute dan semua tipe pesawat**
- **Tidak ada alat perekam otomatis.** *"Belum ada. Mungkin nanti ke depannya bisa diadakan."*

---

## 3 · Yang berbeda dari pemahaman sebelumnya ⭐

| Yang kita catat sebelumnya | Yang dia bilang | Siapa yang benar |
|---|---|---|
| Data movement masuk otomatis ke AFML | Betul — tapi **kuncinya nomor AFML**, dan gagal total kalau nomornya salah | Dia melengkapi |
| Angka OCC sering selisih dengan AFML tulisan tangan | **Bukan angkanya.** Block on/off & take off/landing *"kecil kemungkinan bedanya"*. Yang sering salah **nomornya** | **Kita salah sasaran** |
| OCC satu-satunya sumber data movement | Ada **dua pengirim** — co-pilot dan engineer — dan OCC membandingkan | Kita tidak tahu |

**Yang terkonfirmasi benar:**

- Seluruh isi berasal dari AFML: *"pengambilan datanya dari AFML semua"*
- Sinkron ke MSS berjalan otomatis
- Rekonsiliasi berlapis memang nyata — OCC mengecek silang, lalu Technical Record mengecek lagi

---

## 4 · Kutipan penting

> *"Penerimaan data komplitnya dari teman-teman co-pilot… Jadi kita ambil dari situ untuk pengisian yang namanya actual, dan ada nomor AFML di situ."*

> *"Kalau semisal teman-teman teknik di lapangan itu duluan mengirim foto AFML, kita responnya teknik."*

> *"Kadang nomornya harusnya 01012, ditulisnya 01011. Nah itu menjadi perbedaan… dan itu nggak masuk di sistemnya teman-teman teknik."*

> *"Dia di teknik itu nggak muncul sama sekali."*

> *"Block on block off, ataupun take off ataupun actual landing, itu kecil sih, kecil kemungkinan bedanya. Kalau nomor AFML yang sering."*

> *"Pokoknya bukan satu cycle. Semisal Cengkareng–Makassar–Cengkareng itu berarti ada dua cycle… tapi satu rute. Selagi krunya belum ganti, engineernya belum ganti."*

> *"Hampir 90% itu kita ngisi manual."*

---

## 5 · Tafsir saya *(bukan yang dia bilang)*

- **(asumsi)** Kegagalan sinkronisasi bersifat **senyap di sisi OCC**. Mereka merasa sudah mengisi semuanya; yang tahu ada yang hilang justru tim teknik, yang lalu meminta koreksi. Artinya **deteksi kesalahan bergantung pada seseorang menyadari ketiadaan data** — bukan pada sistem memberi tahu.
- **(asumsi)** Ini requirement paling konkret yang pernah saya dapat: **validasi nomor AFML pada titik entri** — berurut, tidak boleh duplikat, dicocokkan dengan penerbangan. Satu aturan ini menghapus keluhan utama dua tim sekaligus.
- **(asumsi)** Karena **rekonsiliasi silang co-pilot vs engineer sudah menjadi kebiasaan**, akurasi angka jam terbang di Rimbun kemungkinan lebih baik daripada dugaan saya. Risikonya ada di **kelengkapan**, bukan ketepatan.
- **(asumsi)** *Satu AFML = satu rute, bukan satu cycle* adalah **keputusan model data**, bukan sekadar detail. Kalau skema dirancang per-cycle, rekonsiliasi ke AFML fisik akan patah sejak awal.
- **(asumsi)** OCC tidak tahu datanya menopang perencanaan maintenance. **Tidak ada insentif akurasi di hulu** — dan itu argumen untuk memindahkan validasi ke sistem, bukan ke orang.

---

## 6 · Yang masih gelap

| Yang belum jelas | Kenapa penting | Tanya ke siapa |
|---|---|---|
| Berapa penerbangan per hari yang diproses | Menentukan volume & beban entri | Pak Pipit / Mas Bobby |
| Seberapa sering nomor AFML salah | Menakar besar masalahnya. Sejauh ini hanya *"sering"* | Pak Pipit |
| Jalur utama co-pilot mengirim data — apa persisnya, kalau WhatsApp hanya backup | Menentukan titik integrasi hulu | Pak Pipit |
| Apa yang terjadi pada data yang salah nomor — dibiarkan, dihapus, atau diperbaiki? | Menentukan perlu-tidaknya jejak koreksi | Pak Pipit |
| Bentuk sistem OCC & apakah datanya bisa diekspor | Menentukan integrasi atau entri ulang | Mas Bobby / Pak Andi |

**Yang tidak sempat ditanyakan:** apakah pilot mengisi AFML di lembar yang sama dengan engineer, dan siapa yang memegang buku AFML fisik antar-penerbangan.

---

## 7 · Catatan istilah

*"Oisi" / "OSIS" / "posisi" / "OSC"* di sepanjang transkrip semuanya = **OCC**. Salah dengar yang konsisten, aman diabaikan.

---

## 8 · Action items

- [ ] Minta **contoh AFML terisi, satu rute penuh** — PIC: Eza — Pak Pipit sudah bersedia
- [ ] Jadwalkan **observasi ke Cengkareng** — OCC & engineer satu lokasi, keduanya sudah mempersilakan — PIC: Eza
- [ ] Angkat **validasi nomor AFML** jadi requirement eksplisit modul 03 — PIC: Eza
- [ ] Pastikan model data AFML **per rute, bukan per cycle**, sebelum skema DB disusun — PIC: Eza → Rafi
- [ ] Tanya Mas Bobby: sistem OCC bisa diekspor atau diintegrasikan? — PIC: Eza

**Kontak:** Pak Pipit memberikan nomor WhatsApp dan bersedia dihubungi langsung untuk pertanyaan susulan.

---

## Kenapa sesi ini penting melebihi durasinya

Rantai jam terbang sekarang **lengkap dari ujung ke ujung** — dan yang terlihat adalah **tiga titik rekonsiliasi manual untuk satu angka**:

pilot isi AFML → co-pilot kirim ⟷ engineer kirim foto → **OCC bandingkan (1)** → sinkron ke MSS via nomor AFML → **Michelle rekonsiliasi hard copy vs MSS (2)** → approve → TSN/CSN → **PPC pakai untuk LD/ND (3)**

Tiga orang di tiga departemen memeriksa hal yang sama, karena tidak ada satu pun yang mempercayai sumbernya. **Ini pembenaran terkuat untuk sistem yang saya bangun** — dan sekarang saya punya sumbernya langsung, bukan dugaan.

---

Terkait: [[2026-07-31 PPC Technical Record]] · [[2026-08-03 Chief Line Maintenance - Pak Joko]] · [[Proses Manual Maintenance - DRAFT]] · [[Decision - Single Source of Truth Flight Leg & Part Master]]
