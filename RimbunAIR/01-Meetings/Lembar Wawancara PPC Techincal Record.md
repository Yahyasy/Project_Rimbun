---
tanggal: 2026-07-31
tipe: meeting
tags: [panduan, wawancara, ppc, technical-record]
status: lembar bawa — belum dilaksanakan
---

# Lembar Wawancara — PPC Technical Record

**Audiens:** 🟡 Tim Nodewave — lembar kerja, bukan untuk dibagikan ke narasumber.

**Offline · Kantor Rimbun Air Meruya · 10:00–11:00 · narasumber belum diketahui**

> **Fokus sesi: bagaimana mereka bekerja sehari-hari.** Dokumennya sendiri sudah diminta lewat folder Drive, jadi tidak perlu dibolak-balik di sini.

---

## Bekal: apa yang biasanya dikerjakan fungsi Technical Record

> ⚠️ **Ini hipotesis dari standar industri, bukan fakta Rimbun Air.** Gunanya supaya Anda tidak masuk kosong — bisa bertanya *"di sini begini juga?"* alih-alih *"bagaimana caranya?"*
> Kalau ternyata berbeda, **itu temuan** — catat perbedaannya, jangan dipaksakan cocok.

Di operator penerbangan, fungsi technical record adalah **penjaga rekam kelaikudaraan pesawat**. Bukan yang mengerjakan maintenance, dan bukan yang menjadwalkan — tapi yang memastikan **buktinya lengkap, benar, dan bisa ditemukan saat diaudit**.

### Yang biasanya mereka pegang

| Rekam | Isinya |
|---|---|
| Journey log / tech log | Catatan tiap penerbangan: jam, cycle, defect. **Kandidat kuat sumber jam terbang kita** |
| Status AD & SB | Mana yang sudah dikerjakan, mana belum, kapan jatuh tempo berikutnya |
| Status LLP | Komponen berumur terbatas dan sisa umurnya |
| Riwayat komponen | Jejak satu komponen sejak baru, termasuk saat pindah antar pesawat |
| Sertifikat pesawat | Airworthiness, registrasi, radio — beserta masa berlakunya |
| Arsip work order selesai | Bukti pekerjaan yang sudah ditutup |

### Ritme kerja hariannya

Biasanya siklus terima → periksa → catat → arsipkan:

1. Menerima dokumen dari lapangan dan dari planning
2. Memeriksa kelengkapannya sebelum diarsipkan
3. Memasukkan angka ke rekam yang relevan
4. Mengejar dokumen yang belum masuk
5. Menyiapkan laporan status saat diminta atau saat audit

### Keluhan yang lazim di fungsi ini

Kalau salah satu muncul, kejar — biasanya itu masalah nyata:

- Dokumen datang terlambat atau tidak lengkap dari lapangan
- Mengejar-ngejar orang supaya menyerahkan dokumen
- Sulit mencari saat auditor minta record lama
- Entri ganda — angka yang sama diketik di beberapa tempat
- Tidak tahu apa yang belum masuk karena tidak ada daftar induk

### Yang paling ingin kita dengar

| Kalau dia menyebut… | Artinya |
|---|---|
| Menerima tech log dari lapangan | **TB1 kemungkinan tertutup** |
| Punya lemari, ruangan, atau rak arsip | **TB3/TB4 tertutup** |
| Punya register atau daftar induk | Ada mekanisme kontrol kelengkapan |
| Mengetik ulang angka dari dokumen lain | Titik rawan salah ketik, kandidat otomasi |

### Yang mungkin **bukan** urusan mereka

Penjadwalan maintenance, penerbitan work order, dan keputusan teknis — itu planning dan engineering. Kalau dia mengarahkan ke orang lain, catat namanya.

---

## Konsep dasar — pahami ini dulu

Empat konsep yang mendasari hampir semua pertanyaan di lembar ini. Kalau paham keempatnya, Anda tidak akan bingung sendiri saat bertanya.

### 1. "Record" itu apa

Bukan sekadar dokumen. **Record** adalah **bukti riwayat** sebuah pesawat: pekerjaan apa yang pernah dilakukan, kapan, oleh siapa, dan komponen apa yang terpasang.

Gunanya satu: **membuktikan pesawat itu laik terbang.** Kalau regulator datang dan bertanya *"kapan terakhir komponen ini diperiksa?"*, jawabannya harus ada di record — dan harus bisa ditunjukkan.

Jadi kalau nanti dia menyebut "record", yang dia maksud bukan file biasa, tapi **arsip resmi yang punya kekuatan hukum**.

### 2. Kenapa jam terbang jadi pusat segalanya

Tiap pekerjaan maintenance punya jadwal berbasis pemakaian, bukan tanggal. Contoh: *"periksa roda tiap 500 jam terbang."*

Artinya sistem harus selalu tahu: **pesawat ini sudah terbang berapa jam?** Dari situ baru bisa dihitung kapan pekerjaan berikutnya jatuh tempo.

Masalahnya, angka itu lahir di lapangan — setelah pesawat mendarat, ada yang mencatatnya di suatu dokumen. Lalu angka itu harus **sampai** ke orang yang menyusun jadwal.

**Kita belum tahu jalur perpindahan itu.** Siapa yang mencatat pertama, di dokumen apa, dan bagaimana sampai ke Pak Rian. Itu sebabnya pertanyaan soal jam terbang jadi prioritas utama hari ini.

Kalau angkanya telat atau salah, akibatnya nyata: pekerjaan dijadwalkan terlalu cepat (boros) atau terlalu lambat (pesawat terbang dalam kondisi tidak sah).

### 3. Kenapa "berapa lama disimpan" penting

Regulasi mengatur **berapa lama tiap jenis record wajib disimpan** — ada yang setahun, ada yang seumur pesawat, ada yang sampai digantikan versi baru.

Kalau sistem menghapus terlalu cepat, itu pelanggaran. Kalau menyimpan semua selamanya, penyimpanan membengkak tanpa perlu.

Jadi kita perlu tahu aturan mereka sekarang — supaya sistem mengikuti, bukan mengarang sendiri.

### 4. Kenapa nomor revisi manual penting

Manual dari pabrikan **diperbarui berkala** — Boeing tiap 3–4 bulan, ATR dua kali setahun.

Sekarang PPC membuat task card dengan **menyalin instruksi** dari manual itu. Kalau salinan tidak mencantumkan versi asalnya, tidak ada yang tahu apakah instruksi itu masih berlaku setelah manualnya direvisi.

Itu risiko kepatuhan, bukan sekadar kerapian. Karena itu kita perlu tahu: **apakah task card mencantumkan nomor revisi sumbernya?**

---

## Kamus lapangan — istilah yang kemungkinan keluar besok

Disusun dari yang paling mungkin muncul. **Kolom kanan adalah penyelamat** kalau dia pakai istilah yang tidak Anda kenali — tanya balik pakai bahasa itu.

Semua istilah di bawah ada penjelasan lengkapnya di [[Glosarium]].

### Dokumen & rekam

| Kalau dia sebut | Artinya | Tanya balik kalau bingung |
|---|---|---|
| Tech log · journey log · ATL · AFML | Buku catatan penerbangan yang dibawa di pesawat | *"Buku yang dibawa di pesawat tiap terbang itu ya?"* |
| Task card · job card | Kartu instruksi kerja per pekerjaan | *"Ini yang dipegang mekanik pas ngerjain?"* |
| WO · work order | Perintah kerja | — |
| Non-routine · NRC | Temuan di luar perintah kerja | *"Kalau nemu kerusakan lain yang nggak ada di WO?"* |
| CRS · release · DGCA Form 21-18 | Sertifikat pesawat atau komponen boleh dipakai lagi | *"Dokumen yang nyatain boleh terbang lagi?"* |
| DMI · deferred | Perbaikan yang ditunda secara legal | *"Yang rusaknya ditunda perbaikannya?"* |

### Status & pemantauan

| Kalau dia sebut                | Artinya                                             | Tanya balik kalau bingung                         |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------- |
| LD/ND · last done next due     | Tracker jatuh tempo — **jantung modul Anda**        | *"Yang buat lihat kapan jatuh tempo berikutnya?"* |
| ADSB                           | AD + **Alert** Service Bulletin, bukan avionik      | *"Maksudnya AD sama alert SB, ya?"*               |
| HT · hard time                 | Komponen dengan batas umur pasti                    | *"Yang wajib diganti pas kena limit?"*            |
| LLP                            | Life limited part — hard-stop, wajib dibuang        | *"Part yang ada batas umurnya?"*                  |
| Check-pack · A-check · C-check | Paket pekerjaan per tingkat                         | —                                                 |
| TSN / TSO · CSN / CSO          | Jam & cycle komponen sejak baru atau sejak overhaul | *"Ini hitungan umur komponennya?"*                |
| Back-to-birth                  | Riwayat komponen sejak diproduksi                   | *"Riwayat lengkap dari komponen baru?"*           |

### Satuan & angka — catat selalu dengan satuannya

| Istilah | Artinya |
|---|---|
| FH · flight hour · jam terbang | Jam saat pesawat mengudara |
| FC · cycle | Satu kali lepas landas + mendarat |
| Remaining · sisa | Jarak ke jatuh tempo berikutnya |
| Interval · repeat | Jarak antar pengerjaan |

### Regulasi & audit

| Kalau dia sebut               | Artinya                                        |
| ----------------------------- | ---------------------------------------------- |
| CASR                          | Regulasi keselamatan penerbangan Indonesia     |
| DKPPU · Dephub · otoritas     | Regulator                                      |
| Ram check · ramp inspection   | Inspeksi mendadak regulator di bandara         |
| Surveillance · audit internal | Pemeriksaan berkala, internal maupun dari luar |
| Retention · retensi           | Berapa lama record wajib disimpan              |
| Superseded                    | Digantikan versi baru                          |

### Istilah lokal Rimbun Air yang sudah kita dengar

| Istilah                  | Artinya                                                  |
| ------------------------ | -------------------------------------------------------- |
| ==Nurunin / turunin WO== | Menerbitkan work order ke lapangan                       |
| Stamp                    | Cap pribadi engineer, mengikat seperti tanda tangan      |
| Validity tag             | Stiker di alat ukur — tanggal kalibrasi & jatuh temponya |
| Serviceable tag          | Label komponen layak pasang. Di sini **warnanya hijau**  |
| MSS                      | Sistem lama, aslinya untuk gudang bukan maintenance      |
| Technical publication    | Fungsi yang menjaga manual pabrikan tetap versi terbaru  |

---

## Kalimat penyelamat kalau bingung

Jangan pura-pura paham. Tiga kalimat ini aman dipakai berapa kali pun:

> *"Maaf Pak, itu singkatan dari apa ya?"*
> *"Saya awam soal ini — boleh dijelaskan sedikit?"*
> *"Jadi kalau saya tangkap maksudnya X, betul?"*

Yang ketiga paling berguna. Selain memastikan, jawabannya ikut terekam sebagai penjelasan yang bersih.

**Bertanya tidak membuat Anda terlihat tidak siap.** Yang berbahaya justru mengangguk lalu salah catat — sudah empat kali terjadi minggu ini.

---

## Satu penyesuaian dari tiga sesi sebelumnya

Tiga sesi, 100+ pertanyaan, dan kita masih belum tahu dari mana angka jam terbang masuk. Sebabnya bukan kurang pertanyaan — tapi karena kita bertanya **"apa pekerjaan Bapak?"**, dan itu selalu menghasilkan deskripsi peran yang rapi tapi umum.

Penyesuaiannya sederhana: **tanyakan hari kerja yang spesifik, bukan pekerjaan secara umum.**

> Bukan: *"Bagaimana proses kerjanya?"*
> Tapi: *"Kemarin Bapak ngerjain apa saja? Coba dari pagi."*

Orang menjawab pertanyaan abstrak dengan versi ideal. Pertanyaan tentang **kemarin** dijawab dengan yang benar-benar terjadi — termasuk hal yang tertunda, yang bolak-balik, dan yang tidak akan pernah masuk deskripsi jabatan.

Itu satu-satunya perubahan. Sisanya wawancara biasa.

---

## 0 · Kenalan (5 menit)

1. Nama dan jabatan resminya? *(minta disebut untuk rekaman sekalian)*
2. Di bawah Chief yang mana — Maintenance, PPC Engineering, atau Inspector?
3. Di fungsi ini ada berapa orang?

---

## 1 · Hari kerja kemarin (15 menit) ⭐

4. ⭐ **Kemarin Bapak/Ibu ngerjain apa saja? Coba dari pagi sampai pulang.**
   → **Diam. Jangan potong.** Catat yang mau dikejar, tanya di jeda.
5. Itu hari yang biasa, atau kebetulan lagi ramai/sepi?
6. Dari semua itu, mana yang paling makan waktu?
7. Ada yang kemarin tertunda karena menunggu orang atau dokumen lain?

> 🎧 **Dengar:** yang dicari bukan daftar tugas, tapi **urutan dan hambatan**. Kalau dia menyebut menunggu sesuatu, itu titik serah-terima — kejar.

---

## 2 · Satu pekerjaan terakhir (15 menit) ⭐

*Ditelusuri lisan saja. Tidak perlu membuka dokumennya.*

8. ⭐ Coba ambil satu pekerjaan yang **baru selesai kemarin atau minggu ini**. Dari awal masuk ke Bapak/Ibu sampai tuntas, apa saja yang terjadi?
9. ⭐ Dokumen apa yang pertama sampai ke sini? Dari siapa?
10. ⭐ Setelah dari sini, pindah ke siapa?
11. Ada bagian yang biasanya paling lama?
12. Pernah ada yang balik lagi ke sini karena ada yang kurang?

> 🎧 **Dengar:** ini menggantikan telusur dokumen fisik. Yang dicari sama — **urutan dan perpindahan tangan**, cuma diceritakan bukan dilihat.

---

## 3 · Dua yang harus dikejar ⭐⭐

Kalau cerita di atas belum memunculkannya, tanyakan langsung.

13. ⭐⭐ **Angka jam terbang pesawat sampai ke sini lewat apa? Siapa yang membawanya, dan seberapa sering?**

   💬 *Kalau dia balik nanya "maksudnya gimana?":* "Begini Pak — jadwal maintenance kan dihitung dari jam terbang pesawat. Nah saya belum tahu angka jam itu perjalanannya bagaimana: setelah pesawat mendarat, siapa yang catat pertama, di dokumen apa, lalu sampai ke Bapak lewat mana. Itu yang saya mau petakan."

14. ⭐⭐ **Kalau semua sudah beres, dokumennya berakhir di mana? Berapa lama disimpan?**

   💬 *Kalau dia balik nanya:* "Saya ingin tahu ujung perjalanan dokumennya, Pak. Nanti sistemnya harus tahu kapan sebuah pekerjaan dianggap benar-benar tutup, dan dokumennya disimpan berapa lama — supaya tidak terhapus sebelum waktunya."


Dua ini yang paling menentukan. Sisanya bonus.

---

## 4 · Peta dokumen — untuk membaca folder Drive nanti ⭐

*Bukan melihat dokumennya, tapi memahami susunannya. Ini yang bikin folder Drive nanti bisa dibaca.*

15. ⭐ Kalau nanti saya buka folder yang dikumpulkan, **dokumen apa saja yang akan saya temukan?**
16. ⭐ Dari sekian dokumen itu, **mana yang paling sering Bapak/Ibu pegang** sehari-hari?
17. ⭐ Kalau diurutkan sesuai alurnya, **mana duluan mana belakangan?**
18. Ada dokumen yang cuma muncul sesekali? Dalam kondisi apa?
19. Mana yang paling ribet diisi?

> 🎧 **Kenapa ini penting.** Folder Drive akan berisi tumpukan tanpa urutan. Jawaban di sini yang membuatnya bisa dibaca — tanpa perlu satu jam membolak-balik kertas hari ini.

---

## 5 · Titipan dari dua sesi lain

*Pertanyaan pinjaman dari lembar PPC Sesi 2 dan Inspector Sesi 2. Kalau tercover di sini, kedua sesi itu bisa jadi jauh lebih pendek.*

> ⚠️ **Tandai jawabannya sebagai tangan kedua.** Mereka bisa memastikan *dokumen apa yang sampai ke meja mereka* — itu fakta. Tapi soal *bagaimana Pak Rian memutuskan sesuatu*, jawabannya dugaan. Jangan langsung dianggap tertutup.

### Wilayah mereka sendiri — jawabannya justru paling kuat di sini

20. ⭐ **Berapa lama tiap jenis record disimpan?** Ada aturan tertulisnya, atau kebiasaan?

   💬 *Kalau dia balik nanya:* "Nanti sistemnya perlu tahu kapan boleh dan tidak boleh menghapus, Pak. Kalau kecepetan dihapus bisa kena temuan audit. Jadi saya mau ikut aturan yang sudah Bapak pakai."

21. ⭐ **Kalau DKPPU minta record tiga tahun lalu, berapa lama menemukannya?** Pernah kesulitan?

   💬 *Kalau dia balik nanya:* "Saya mau tahu seberapa repot mencarinya sekarang, Pak — supaya kelihatan seberapa besar bantuan yang bisa diberikan sistem nanti."

22. Tim yang mengumpulkan arsip dokumen — **itu tim ini, atau ada tim lain lagi?**

*(Pak Heri menyebut "ada tim sendiri yang khusus mengumpulkan arsip" tapi tidak ingat namanya. Kalau jawabannya "kami", satu titik buta tertutup.)*

### Bisa mereka jawab karena mereka yang mengarsipkan

23. ⭐ Di task card yang masuk ke sini, **ada tercantum nomor revisi manual sumbernya?**

   💬 *Kalau dia balik nanya:* "Maksud saya begini Pak — manual dari pabrikan kan diperbarui berkala. Saya mau tahu, di task card-nya ada keterangan diambil dari manual versi mana? Supaya kalau manualnya berubah, ketahuan task card mana yang perlu diperbarui."

24. Kira-kira **berapa work order** yang masuk ke sini per bulan?
25. Nomor WO formatnya seperti apa? Ada awalan per tipe pesawat atau per tahun?
26. Pernah ada dokumen yang **tertahan lama** di sini karena menunggu kelengkapan? Yang paling sering kurang apa?

   💬 *Kalau dia balik nanya:* "Saya lagi cari tahu di titik mana proses biasanya tersendat, Pak. Bukan mencari siapa yang salah — supaya sistemnya nanti bisa bantu mengingatkan sebelum tersendat."


*(Pertanyaan 26 bisa membuka alur penolakan dari sisi lain — tanpa menyebut kata "ditolak".)*

### Konfirmasi cepat

27. Model pesawat yang ditangani apa saja? Yang disebut *"eng"* itu **Boeing 737NG**, betul?
28. Twin Otter ikut ditangani juga?
29. **ADSB** — maksudnya AD dan Alert Service Bulletin, ya?

### Kalau mereka memegang record defect

30. Catatan **penundaan perbaikan (DMI)** ada di sini juga? Bentuknya seperti apa?

   💬 *Kalau dia balik nanya:* "Yang saya maksud kerusakan yang belum bisa diperbaiki hari itu tapi pesawatnya masih boleh terbang, Pak — biasanya ada batas waktunya. Catatannya disimpan di sini juga?"

31. Bagaimana tahu ada penundaan yang mendekati batas waktu?

*(Blok defect belum tersentuh di sesi mana pun. Kalau ternyata mereka pegang, ini bonus besar.)*

---

## 6 · Kalau masih sempat

32. Laporan status **AD dan Alert SB** — bentuknya seperti apa, siapa yang menyusun?
33. Catatan **status LLP** dan komponen berumur terbatas
34. **Riwayat satu komponen** — kalau pindah pesawat, jamnya bagaimana ikut?
35. Register atau daftar induk — bagaimana tahu ada record yang belum masuk?

---

## 7 · Penutup (5 menit)

24. Apa yang paling bikin frustrasi dari pekerjaan ini?
25. ⭐ Kalau nanti ada sistem, apa yang justru **jangan** diotomatiskan?
26. Siapa lagi yang sebaiknya saya temui?

---

## Sebelum pulang

- [ ] Pastikan folder Drive-nya jalan — sudah diisi belum, siapa yang mengisi
- [ ] ⭐ Minta **satu contoh** dokumen yang paling sering dipakai, kalau belum ada di Drive
- [ ] Foto tempat penyimpanan ars wip — cukup satu foto, tidak perlu isinya
- [ ] Nama & jabatan resmi semua orang yang disebut

---

## MoM sudah disiapkan

Kerangkanya ada di [[2026-07-31 PPC Technical Record]], sudah pra-isi dengan konteks yang kita tahu — termasuk tiga hal yang perlu dicek apakah cocok dengan cerita dia.

**Bagian 1–3 diisi dalam 30 menit setelah keluar**, selagi ingat. Sisanya menyusul setelah dengar rekaman.

## Cara mencatat

**Centang, jangan tulis.** Yang ditulis hanya **angka + satuan · singkatan · nama · waktu**. Sisanya biarkan rekaman.

Tiap topik selesai, **ulang balik lisan**: *"Jadi kalau saya tangkap, urutannya X lalu Y — betul?"*

Setelah keluar ruangan, **debrief suara 5 menit**.

Selengkapnya: [[Instruksi Wawancara]]

**Setup rekaman:** HP dekat narasumber · minta sebut nama & jabatan di awal · hindari dekat AC.

---

## Kalau tinggal 20 menit

Blok **1** (hari kerja kemarin) → blok **3** (dua pertanyaan wajib) → blok **4** (peta dokumen) → **20–22** dari blok titipan.

Blok 4 jangan dilewati — itu yang menentukan folder Drive nanti berguna atau cuma jadi tumpukan. Pertanyaan 20–22 murni wilayah mereka, jadi cepat dijawab dan langsung menutup satu titik buta.

Terkait: [[BPMN & Activity Flow - DRAFT]] · [[Proses Manual Maintenance - DRAFT]] · [[Instruksi Wawancara]]
