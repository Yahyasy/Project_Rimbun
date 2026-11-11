---
tanggal: 2026-07-30
tipe: catatan-kerja
tags: [metode, wawancara]
---

# Cara Wawancara Sendirian

**Audiens:** 🟡 Tim Nodewave — metode kerja, bukan isi project.

> **Isi note ini:** cara menangani wawancara offline sendirian tanpa kehilangan fokus. Baca sekali, lalu cukup lihat bagian *Sebelum masuk ruangan* tiap sesi.

Masalahnya bukan kecepatan menulis. Masalahnya **mencatat isi sambil mewawancarai itu dua pekerjaan yang saling merebut perhatian** — dan yang kalah selalu yang lebih penting: mendengarkan.

---

## Sebelum sesi: riset perannya dulu

Jangan masuk kosong. Sebelum tiap wawancara, siapkan **hipotesis tentang apa yang biasanya dikerjakan fungsi itu** — dari standar industri, bukan tebakan.

Tanpa itu, pertanyaannya jadi *"bagaimana proses kerjanya?"* — terbuka, dan dijawab dengan deskripsi peran yang rapi tapi umum. Dengan hipotesis, pertanyaannya jadi *"di sini begini juga?"* — dan itu jauh lebih cepat sampai ke detail.

Manfaat keduanya: kalau jawabannya **berbeda** dari hipotesis, Anda langsung sadar itu temuan. Tanpa pembanding, penyimpangan lewat begitu saja.

Tulis hipotesisnya **di lembar wawancara itu sendiri**, jangan bikin note terpisah. Isinya cukup empat hal:

1. Apa yang biasanya dipegang fungsi ini
2. Ritme kerja hariannya
3. Keluhan yang lazim muncul
4. Yang **bukan** urusan mereka — supaya tidak salah alamat bertanya

> ⚠️ Selalu tandai bahwa itu **hipotesis, bukan fakta**. Bahayanya kalau lupa: Anda mendengar apa yang Anda harapkan, bukan apa yang dia katakan.

Contohnya ada di [[Lembar Wawancara PPC Techincal Record]], bagian *Bekal*.

---

## Kalau tujuannya BPMN: gali alur, bukan topik

**Satu sesi = satu lane.** Anda tidak sedang memahami sebuah departemen. Anda sedang mengisi satu baris swimlane, dari kiri ke kanan.

Pertanyaan topikal *("bagaimana AD ditangani?")* menghasilkan penjelasan yang rapi tapi tidak berurut — dan tidak bisa digambar. Yang bisa digambar cuma **urutan kejadian**.

### Enam slot yang harus terisi

Tiap aktivitas di diagram butuh enam hal ini. Kalau salah satu kosong, di diagram jadi kotak putus-putus.

| # | Slot | Bunyi pertanyaannya |
|---|---|---|
| 1 | **Pemicu** | *"Bapak tahu harus mulai kerja ini dari apa? Ada yang ngasih tahu, atau lihat sendiri?"* |
| 2 | **Urutan aktivitas** | *"Terus apa? … terus?"* — kata kerja + objek |
| 3 | **Masuk & keluar** | *"Waktu mulai, Bapak pegang apa? Selesainya jadi apa?"* |
| 4 | **Percabangan** | *"Pernah nggak yang nggak lewat jalur itu? Bedanya di mana?"* |
| 5 | **Serah terima** | *"Habis itu ke siapa? Lewat apa — WA, kertas, sistem?"* |
| 6 | **Kalau gagal** | *"Kalau ternyata salah atau nggak lengkap, gimana?"* |

**Slot 6 yang paling sering terlewat**, dan itu sebabnya blok B6 *(alur penolakan)* masih gelap sampai sekarang. Orang secara alami menceritakan jalur mulus. Jalur gagal harus diminta.

### Empat cara memancingnya

**1 · Telusuri satu kejadian nyata, bukan kebiasaan.**

Jangan: *"Biasanya alurnya bagaimana?"* → jawabannya deskripsi peran.
Tapi: *"Yang terakhir Bapak tangani kapan? Coba ceritakan dari awal."* → jawabannya urutan.

Ingatan manusia menyimpan kejadian, bukan prosedur. Satu kejadian konkret memunculkan urutan, percabangan, dan serah terima sekaligus — tanpa perlu ditanya satu-satu.

**2 · Rantai "terus apa?"**

Terus dorong sampai pekerjaan itu **keluar dari tangannya**. Lalu balik arah: *"Sebelum sampai ke Bapak, dari siapa?"* Maju sampai batas lane, mundur sampai batas lane. Selesai satu lane.

**3 · Cari batasnya untuk menemukan percabangan.**

Gateway di BPMN muncul dari pertanyaan *"kapan ini tidak berlaku?"*. Kalau semua jawaban terdengar seragam, kemungkinan besar Anda belum menemukan cabangnya — bukan cabangnya tidak ada.

**4 · Tanyakan penungguan.**

*"Setelah dikirim, Bapak nunggu berapa lama?"* Jeda menunggu tidak pernah disebut spontan, padahal di diagram itu bisa jadi bottleneck paling mahal — dan sering jadi alasan terkuat kenapa sistem ini dibangun.

### Verifikasi dengan menggambar, bukan bertanya

Di akhir sesi, gambar alurnya di kertas **di depan dia**, lalu sodorkan pulpennya:

> *"Ini yang saya tangkap, Pak. Ada yang kebalik atau kelewat?"*

Orang jauh lebih cermat mengoreksi gambar yang salah daripada menjawab pertanyaan terbuka. Fotonya jadi bahan mentah paling berharga untuk Gama.

---

## Prinsipnya

**Rekaman menyimpan isi. Anda menyimpan arah.**

Kalau sudah merekam, semua fakta sudah aman. Yang tidak terekam dan hilang kalau Anda menunduk menulis:

- Momen narasumber ragu atau berubah nada — itu penanda ada sesuatu
- Kesempatan bertanya *"tadi maksudnya gimana?"* tepat saat masih nyambung
- Kontak mata, yang menentukan seberapa terbuka orang bercerita

---

## Yang boleh ditulis — hanya empat

Selebihnya jangan. Serius.

| Tulis | Kenapa |
|---|---|
| **Angka + satuan** | ASR sering salah dengar angka, dan ini yang paling mahal kalau keliru |
| **Singkatan** | Tulis, lalu **langsung tanya kepanjangannya** di detik itu |
| **Nama orang & jabatan** | ASR hampir selalu salah dengar nama |
| **Waktu** *(mis. 14:23)* | Penanda untuk mencari balik di rekaman |

Semua yang lain — alur, penjelasan, cerita — **biarkan rekaman yang menangkap**.

Kalau ada yang ingin dikejar tapi sedang tidak pas dipotong, cukup tulis **satu kata** di margin. Nanti kembali ke situ.

---

## Empat teknik yang menggantikan mencatat

### 1. Ulang balik dengan kata-kata sendiri

Tiap selesai satu topik, rangkum lisan:

> *"Jadi kalau saya tangkap, alurnya dari A ke B lalu ke C. Betul begitu, Pak?"*

Tiga manfaat sekaligus: Anda memverifikasi pemahaman, narasumber dapat kesempatan mengoreksi, dan **rangkuman bersih itu ikut terekam** — jauh lebih rapi daripada catatan tangan Anda.

### 2. Centang, jangan tulis

Lembar wawancara dipakai sebagai **checklist**, bukan buku catatan. Centang yang sudah terjawab, lingkari yang perlu dikejar. Itu saja.

### 3. Foto, jangan deskripsikan

Kalau narasumber menunjukkan dokumen, **jangan mendeskripsikannya di catatan**. Foto. Satu foto mengalahkan satu paragraf, dan tidak memutus percakapan.

### 4. Debrief suara, 5 menit setelah keluar

Di mobil atau lobi, rekam suara sendiri:

> *"Barusan saya belajar apa. Apa yang bikin saya kaget. Apa yang beda dari dugaan. Apa yang harus dikejar."*

Ini yang paling sering terlewat, dan paling sulit dipulihkan. Fakta ada di rekaman, tapi **kesan dan sintesis Anda cuma ada di kepala** — dan hilang dalam dua jam.

---

## Yang paling menyelesaikan masalah: bawa orang kedua

Semua di atas menambal. Ini menyelesaikan.

**Satu bicara, satu mencatat.** Ini praktik standar riset pengguna, dan alasannya persis masalah yang Anda rasakan.

Kandidatnya sudah ada di tim:

| Siapa | Kenapa cocok |
|---|---|
| **Wisnu** | Sesama Product Manager, paham konteksnya |
| **Gama** | BPMN Consultant — dia yang akan menggambar alurnya. Mendengar langsung jauh lebih baik daripada membaca MoM |

Pembagiannya: Anda pegang percakapan dan kontak mata sepenuhnya. Dia mencatat, dan **hanya dia yang boleh menyela** untuk menanyakan hal yang terlewat, di jeda.

Kalau Gama ikut, ada bonus: dia bisa langsung memvalidasi diagram di tempat.

---

## Perbaiki kualitas rekaman

Transkrip kita sejauh ini banyak yang rusak, dan itu bikin Anda merasa harus mencatat. Perbaiki di sumbernya:

- **Taruh HP dekat narasumber**, bukan di tengah meja. Suara Anda tidak penting, suara dia yang penting.
- **Minta menyebut nama dan jabatan di awal**, untuk rekaman. Ini sekaligus menjawab pertanyaan pertama Anda.
- **Hindari ruangan berisik AC.** Kalau bisa pilih tempat, pilih yang sepi.
- **Rekam dua alat** kalau bisa — HP dan laptop. Satu rusak, satu selamat.
- **Setelah sesi, langsung namai filenya** dengan tanggal dan narasumber.

---

## Sebelum masuk ruangan

Empat baris ini saja yang perlu diingat:

1. Sudah baca hipotesis peran di lembar? Kalau belum, baca dulu
2. **Hari ini saya mengisi satu lane** — yang saya cari urutan, bukan penjelasan
3. Rekaman menyimpan isi — saya menyimpan arah
4. Yang saya tulis cuma: **angka, singkatan, nama, waktu**
5. Tiap topik selesai, **ulang balik lisan**
6. Sebelum pamit, **gambar alurnya di depan dia** dan minta dikoreksi
7. Keluar ruangan, **langsung debrief suara 5 menit**
8. Dalam 30 menit, isi bagian 1–3 MoM dari template `mom-wawancara`

Terkait: [[Lembar Wawancara PPC Techincal Record]] · [[Riwayat Koreksi]]
