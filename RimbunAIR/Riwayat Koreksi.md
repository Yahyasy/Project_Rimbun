---
tanggal: 2026-07-30
tipe: knowledge
tags: [koreksi, disiplin, riwayat]
audiens: internal
---

# Riwayat Koreksi

**Audiens:** 🔴 Internal saja — Catatan kesalahan kita sendiri. Untuk tim Nodewave.

> **Isi note ini:** catatan hal-hal yang sempat salah dicatat lalu diperbaiki, beserta cara ketahuannya.
> Note lain di vault ini menuliskan **keadaan saat ini saja** — tanpa penjelasan "dulu salah begini". Semua riwayatnya dikumpulkan di sini.

Tujuannya dua: menjaga jejak supaya keputusan bisa ditelusuri, dan **mengingatkan seberapa sering kita keliru** — dua belas koreksi dalam delapan hari, semuanya tertangkap karena kebetulan ada pembanding.

---

## Daftar koreksi

| # | Yang sempat dicatat | Yang benar | Ketahuan dari |
|---|---|---|---|
| 1 | Release certificate = "[[Glosarium#D\|DGCA]] Form 1" | **[[Glosarium#D\|DGCA Form 21-18]]** | Riset pembanding. Form 1 milik DGCA India |
| 2 | AC e-records Des 2023 berlaku di Indonesia | Milik **DGCA India**, bukan Indonesia | Riset pembanding |
| 3 | ENVISION produk Veryon | Produk **Rusada** | Selisih antar dua sumber riset |
| 4 | Inspector bernama "Agus" | **Pak Heri** | Wawancara langsung |
| 5 | Rimbun Air operator perintis turboprop Papua | **Operator kargo jet**, jaringan nasional termasuk Papua | Klarifikasi + riset publik |
| 6 | "EDSB" → dibaca ADS-B avionik | **ADSB = [[Glosarium#A\|AD]] + Alert Service Bulletin** | Dokumen Scope + konfirmasi |
| 7 | Engineer yang memperbarui [[Glosarium#L\|LD/ND]] | **PPC (Pak Rian)** sendiri | Transkrip verbatim |
| 8 | "Ke store, cocokan" = alur dokumen WO | Soal **receiving material** | Transkrip verbatim |
| 9 | "CSR" sebagai sumber dokumen | **[[Glosarium#C\|CASR]]** (Civil Aviation Safety Regulation) | Klarifikasi |
| 10 | **"Erod"** = staf Engineering penerbit EO | **Bukan nama siapa pun** — salah dengar dari catatan tangan. Penyusun EO masih belum diketahui | Konfirmasi Eza, 3 Agu |
| 11 | **"Chief LM"** = penyetuju WO tanpa nama | **Pak Joko**, *Chief Line Maintenance Engineer* | Wawancara langsung, 3 Agu |
| 12 | Harbour Energy **menawarkan sistem mereka sendiri** ke Rimbun | Tidak. Harbour hanya **mempertanyakan kehandalan**; justru Rimbun yang ingin punya sistem sendiri — karena itulah Nodewave disewa | Koreksi Eza, 3 Agu |

---

## Tiga yang paling berdampak

### Papua — dan apa yang sebenarnya salah

Premis "operator kargo perintis Papua" masuk sejak riset pertama, lalu ikut ditulis ke dalam **ketiga prompt deep research**. Jadi sebagian isi note domain sempat berdiri di atas asumsi yang keliru.

Yang keliru **bukan** "ada operasi di Papua" — Rimbun Air memang melayani Jayapura dan Wamena, dan sejarahnya bermula dari charter Twin Otter di sana. Yang keliru adalah framing bahwa **seluruh operasinya** perintis turboprop di landasan terpencil.

Kenyataannya operator kargo dengan armada jet: 4× Boeing 737-300F, 1× Boeing 737-800SF, 1× DHC-6 Twin Otter, 1× ATR 72-600. Jaringannya nasional.

**Yang terdampak:** argumen offline-first kehilangan fondasinya (K2 turun jadi 🟢), klaim "jeda log 3–7 hari" perlu dicek ulang, dan bagian mesin PT6A hanya relevan untuk armada turboprop.

**Yang tidak terdampak:** seluruh aritmetika interval, aturan CASR, siklus work order, [[Glosarium#R|RII]], kalibrasi, dan [[Glosarium#C|CRS]]. Semuanya berlaku untuk operator mana pun.

### TB3 — dua kali salah sebelum benar

Awalnya diduga PPC yang memperbarui LD/ND. Lalu catatan tulisan tangan sesi inspector membuatnya berubah jadi "engineer". Lalu transkrip verbatim menunjukkan "engineer" itu jawaban untuk pertanyaan lain — dan yang benar memang **PPC**, sesuai dugaan awal.

Pelajarannya: catatan cepat saat wawancara gampang menempelkan jawaban ke pertanyaan yang salah. Verbatim menyelesaikan ini; kalau tidak ada, kesalahan itu akan terbawa ke PRD.

### MSS — separuh benar, dan separuh itu penting

Pak Rian bilang MSS *"basic dari awalnya bukan untuk maintenance"* dan PPC sudah sepenuhnya spreadsheet. Dari situ kita simpulkan MSS adalah project gagal yang tidak dipakai.

Mba Michelle membantahnya: *"Sistem yang dibuat Mas Bobby ini sudah cukup provide."* MSS **dipakai setiap hari** untuk AFML — create, discrepancy, rectification, component replacement, export laporan DKPPU.

Keduanya benar. MSS memang tidak cocok untuk planning, tapi berfungsi baik untuk technical record. Kesalahan kita adalah **menggeneralisasi dari satu pengguna ke seluruh sistem**.

Dampaknya besar untuk K4: ternyata ada database berisi data AFML yang mungkin bisa dimigrasikan, bukan diketik ulang.

### ADSB — hampir jadi fitur yang salah

Sempat dibaca sebagai ADS-B, sistem surveillance avionik. Kalau tidak tertangkap, bisa muncul requirement untuk melacak perangkat avionik — padahal maksudnya **kepatuhan AD dan Alert Service Bulletin**, hal yang sama sekali berbeda.

Dan koreksi keduanya juga penting: bukan Service Bulletin biasa, tapi **Alert** [[Glosarium#S|SB]] — kategori mendesak yang perlakuannya jauh lebih ketat.

---

### "Erod" — nama yang tidak pernah ada

Berasal dari satu coretan tangan sesi 29 Jul: *"Pak Rian hanya deploy aja, EO engineer Erod."* Kata terakhir dibaca sebagai nama orang, dan sejak itu **"Erod (Engineering)" muncul di tujuh note** — daftar stakeholder, tabel peran, diagram swimlane, bahkan agenda wawancara yang menargetkan dia.

Delapan hari berjalan tanpa ada yang mempertanyakannya, karena begitu sebuah nama masuk daftar stakeholder ia terlihat seperti fakta yang sudah diverifikasi.

**Pelajarannya berbeda dari koreksi lain:** yang salah bukan isinya, tapi **kepercayaan diri formatnya**. Nama di dalam tabel terbaca lebih pasti daripada nama di dalam kalimat. Coretan tangan yang belum diverifikasi sebaiknya tidak langsung naik ke tabel — beri penanda dugaan dulu.

**Yang masih terbuka:** siapa sebenarnya yang menyusun EO di Rimbun. Belum ada jawabannya dari sesi mana pun.

## Pola yang terlihat

Dua belas koreksi, dan semuanya tertangkap dari salah satu dari tiga hal:

1. **Sumber pembanding** — dua riset yang saling berselisih, atau transkrip yang membantah catatan
2. **Konfirmasi langsung** ke orang yang tahu
3. **Riset publik** untuk fakta yang bisa diverifikasi dari luar

Tidak ada satu pun yang tertangkap karena "dibaca ulang dengan teliti". **Ketelitian tidak menemukan kesalahan jenis ini — pembanding yang menemukan.**

Konsekuensinya untuk cara kerja:

- Jangan pernah menyimpulkan dari satu sumber tanpa penanda asumsi
- Transkrip verbatim jauh lebih berharga daripada ringkasan, meski lebih repot dibaca
- Ringkasan AI atas transkrip yang buruk akan meneruskan kesalahannya dengan nada meyakinkan
- Deep research bisa **mengarang detail spesifik** yang tidak pernah diberikan — registrasi pesawat dan nama pangkalan pernah muncul begitu saja

## Yang masih berupa dugaan

Belum salah, tapi belum terkonfirmasi. Kalau nanti keliru, tempatnya di tabel atas.

| Dugaan | Dasarnya | Cara memastikan |
|---|---|---|
| *"eng"* = Boeing 737**NG** | "NG" terdengar seperti "eng", dan armada memang punya 737-800 | Satu kalimat ke Pak Rian |
| ~~Technical Record = tim arsip~~ | ✅ Terkonfirmasi 31 Jul — Michelle yang scan & simpan ke Google Drive | — |
| Interval 10.000 FH per model | Dikonfirmasi dua kali, tapi angkanya tidak lazim untuk check rutin | Cocokkan ke [[Glosarium#M\|MPD]] |
| *"Free flight check"* sebenarnya **pre-flight check** | Tercatat dari catatan tangan sesi PPC. Pak Joko menyebut *pre-flight check* dengan jelas berikut aktivitasnya. *Free flight* bukan istilah maintenance | Satu kalimat ke Pak Rian |
| **A-Check 730 FH** vs **interval per model 500 / 1500 / 10000 FH** | Dua set angka yang tidak nyambung. Kalau A-Check 730 FH, 500 FH untuk 737 Classic itu check apa? | [[Glosarium#M\|MPD]] per tipe — butir G2 di [[Checklist Data dari Rimbun Air]] |
| Semua nomor pasal CASR | Riset bersumber sekunder, bukan JDIH | Cek ke JDIH Kemenhub |

Terkait: [[Overview]] · [[Proses Manual Maintenance - DRAFT]]
