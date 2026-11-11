---
tanggal: 2026-08-03
tipe: meeting
tags: [panduan, wawancara, engineering]
status: lembar bawa — belum dilaksanakan
---

# Lembar Wawancara — Chief Engineer

**Audiens:** 🟡 Tim Nodewave — lembar kerja, bukan untuk dibagikan ke narasumber.

> **Kenapa sesi ini penting.** Lane ini masih kosong di BPMN (blok B2), dan sekaligus jadi tempat menguji satu batas scope yang belum pasti — lihat kotak di bawah.

### ⚠️ Baca ini dulu — *engineer* ≠ *engineering*

Dua hal berbeda yang namanya mirip, dan **hanya satu yang scope Anda**:

| | Yang dikerjakan | Modul |
|---|---|---|
| **Engineering** *(fungsi)* | Membuat AMP, menerbitkan EO, menilai AD/SB berlaku untuk armada mana | **01 Engineering & Configuration — bukan Anda** |
| **Engineer** *(orang)* | Pemegang lisensi yang mengerjakan & menandatangani pekerjaan di lapangan | **02 Production & Execution — Anda** |

Sumber: `Scope.md` → *"Batas antara menerima EO dan membuat EO harus jelas."*

**Artinya untuk sesi ini:** blok 2 dan 3 **bukan lagi inti sesi** — jangan habiskan waktu menggali *bagaimana* Engineering bekerja di dalam. Yang Anda perlukan cuma **titik serah terimanya**: dokumen apa yang keluar dari mereka, ke siapa, dalam bentuk apa, seberapa sering. Itu yang menyambung ke modul Anda. Sisanya catat saja, lalu teruskan ke PM modul 01.

**Yang jadi inti sesi:** blok **5** (pekerjaan engineer di lapangan) dan pertanyaan **17** (siapa menentukan isi task card — ini persis garis batasnya).

> ℹ️ Struktur Rimbun punya **Chief PPC Engineering** dan **Chief Maintenance** *(Pak Heri, 30 Jul)*. Dugaan saya keduanya berbeda orang, **tapi itu belum diverifikasi** — bisa saja di Rimbun keduanya satu peran, atau istilahnya dipakai bergantian. Jangan diasumsikan; tanyakan di blok 0.

> 📖 **Baca dulu sebelum berangkat:** [[Bekal Belajar - Engineering & OCC]] — model mental kedua peran, lengkap dengan konsep dasarnya.

---

## 🎯 Yang dicari hari ini: **urutan**, bukan penjelasan

**Satu sesi = satu lane.** Pertanyaan di bawah cuma checklist cakupan. Yang benar-benar menghasilkan diagram adalah satu kalimat ini:

> ⭐⭐ *"Yang terakhir Bapak tangani kapan? Coba ceritakan dari awal."*
> lalu dorong terus: ***"terus apa?"*** — sampai pekerjaan itu keluar dari tangannya.

Enam slot yang harus terisi per aktivitas. Centang sambil jalan:

| | Slot | Pancingannya |
|---|---|---|
| ☐ | **Pemicu** | *"Tahu harus mulai dari apa?"* |
| ☐ | **Urutan** | *"Terus apa? … terus?"* |
| ☐ | **Masuk & keluar** | *"Mulai pegang apa, selesainya jadi apa?"* |
| ☐ | **Percabangan** | *"Pernah nggak yang nggak lewat jalur itu?"* |
| ☐ | **Serah terima** | *"Ke siapa, lewat apa — WA, kertas, sistem?"* |
| ☐ | **Kalau gagal** | *"Kalau salah atau nggak lengkap, gimana?"* |

⚠️ **Slot terakhir paling sering terlewat.** Orang menceritakan jalur mulus; jalur gagal harus diminta.

**Sebelum pamit:** gambar alurnya di kertas di depan dia, sodorkan pulpennya — *"ada yang kebalik atau kelewat, Pak?"* Foto hasilnya. Itu bahan paling berharga untuk Gama.

Selengkapnya: [[Instruksi Wawancara]]

## Bekal: apa yang biasanya dikerjakan Engineering

> ⚠️ Hipotesis standar industri, **bukan fakta Rimbun Air**. Kalau berbeda, itu temuan.

Engineering adalah **penerjemah**: mengubah aturan dari luar (pabrikan, regulator) menjadi instruksi kerja yang bisa dieksekusi di lapangan.

| Yang biasanya mereka pegang | Isinya |
|---|---|
| **Maintenance Program (AMP)** | Menyaring task dari manual pabrikan mana yang berlaku untuk armada sendiri |
| **Engineering Order (EO)** | Instruksi kerja untuk hal yang tidak rutin — modifikasi, perbaikan khusus |
| **AD & Alert SB** | Menilai mana yang berlaku, menerjemahkan jadi pekerjaan, memantau kepatuhan |
| **Keputusan teknis** | Boleh atau tidak sesuatu dikerjakan dengan cara tertentu |
| **Reliability** | Analisis kerusakan berulang |

### Yang sudah kita dengar dari orang lain

- Penerbit **EO** belum diketahui orangnya *(nama yang sempat tercatat ternyata salah dengar)*
- **ADSB** — AD dari FAA & EASA, SB dari pabrikan — *"engineering biasa ngurusnya"* *(Technical Record, 31 Jul)*
- Manual pabrikan **disaring dulu** mana yang cocok untuk Indonesia. Contoh: anti-ice system dibuang karena tidak ada musim salju *(Inspector, 30 Jul)*
- Maintenance Program direvisi **Boeing 3–4 bulan, ATR 2× setahun** *(PPC)*

Semuanya perlu dikonfirmasi ke sumbernya hari ini.

---

## Kamus singkat

| Kalau dia sebut | Artinya | Tanya balik kalau bingung |
|---|---|---|
| EO · Engineering Order | Instruksi kerja untuk hal non-rutin | *"Ini yang keluar kalau ada pekerjaan khusus?"* |
| AD | Perintah wajib dari regulator | *"Yang wajib dikerjakan dari otoritas?"* |
| ASB · Alert SB | Peringatan mendesak dari pabrikan | *"Yang urgent dari pabrikan?"* |
| MPD | Dokumen jadwal perawatan dari pabrikan | *"Buku jadwal dari pabrik?"* |
| AMP · Maintenance Program | Program perawatan versi Rimbun, disahkan DKPPU | — |
| Effectivity | Task ini berlaku untuk pesawat yang mana | *"Gimana tahu task ini buat pesawat yang mana?"* |
| Major repair | Perbaikan besar yang butuh persetujuan khusus | — |

**Kalimat penyelamat:** *"Maaf Pak, itu singkatan dari apa ya?"* · *"Saya awam soal ini, boleh dijelaskan sedikit?"* · *"Jadi kalau saya tangkap maksudnya X, betul?"*

---

## 0 · Kenalan & peta istilah (7 menit) ⭐⭐

*Jangan buru-buru lewat blok ini. Setengah kebingungan kita selama ini berasal dari satu kata yang dipakai untuk dua hal.*

1. Nama dan jabatan resminya? *(minta disebut untuk rekaman)*
2. ⭐ Kalau boleh saya pastikan — ini **Chief PPC Engineering**, **Chief Maintenance**, atau sebutan lain?
3. ⭐ Di bawah Bapak ada berapa orang? Apa saja perannya, dan mereka biasanya kerja di mana — kantor atau hanggar?

**Peta istilah** *(ini yang mau diuji — jangan sodorkan dugaan kita, biarkan dia yang mendefinisikan)*

3a. ⭐⭐ **Di Rimbun, kalau orang bilang "engineer", yang dimaksud siapa?**
   → Diam. Jangan pancing dengan pilihan.

3b. ⭐⭐ **Kalau "engineering"?** Sama atau beda dengan "engineer"?

3c. ⭐ Kata **"mekanik"** dipakai juga di sini? Bedanya apa dengan engineer?

3d. ⭐ Yang memegang **lisensi** dan boleh tanda tangan — semua orang, atau sebagian?

> 💬 *Kalau dia balik nanya kenapa ditanya:* "Saya lagi menyusun peran-peran di sistem, Pak. Kalau saya salah pakai istilah, nanti hak aksesnya kebalik — yang harusnya boleh tanda tangan jadi tidak boleh."

> **Kalibrasi — catat jawabannya, ini menentukan bobot blok 5:**
>
> 3e. ⭐ *Seberapa dekat Bapak dengan pekerjaan harian di hanggar — tiap hari ke lapangan, atau lebih banyak di kantor?*
>
> | Jawabannya | Artinya untuk blok 5 |
> |---|---|
> | Tiap hari ke lapangan | Jawabannya tangan pertama. Boleh dipakai langsung. |
> | Sesekali / lewat laporan | Tetap tanyakan, tapi tandai di MoM sebagai **tangan kedua** — belum menutup B7. |
> | Tidak pernah | Percepat blok 5 jadi 3 pertanyaan saja, lalu pakai **20p** untuk minta akses ke orangnya. |
>
> Apa pun jawabannya, **blok 5 tetap dijalankan.** Kalau ternyata di Rimbun engineer dan mekanik memang satu orang, dia jelas tahu — dan dugaan soal dua Chief yang terpisah gugur.

## 1 · Hari kerja kemarin (10 menit) ⭐

4. ⭐ **Kemarin Bapak ngerjain apa saja? Coba dari pagi.**
   → **Diam, jangan potong.**
5. Mana yang paling makan waktu?
6. ⭐ *(tunjukkan diagram)* Ini pemahaman saya dari ngobrol dengan tim lain. Bagian Bapak yang mana, dan mana yang keliru?

## 2 · Dari aturan luar jadi pekerjaan — **cukup permukaan** ⏱️ 8 menit

> 🔵 **Ini wilayah modul 01, bukan Anda.** Yang dibutuhkan cuma **titik serah terimanya**. Jangan tergoda menggali dalam — kalau dia bersemangat cerita, catat saja dan lanjut. Hasilnya diteruskan ke PM modul 01, bukan masuk PRD Anda.

7. ⭐ **Kalau ada AD baru terbit, sampai ke Rimbun lewat siapa?** Lalu berhenti di meja siapa?

   💬 *Kalau dia balik nanya:* "Saya lagi memetakan perjalanan sebuah aturan, Pak — dari terbit di regulator sampai jadi pekerjaan yang dikerjakan di lapangan. Saya belum tahu bagian mana yang lewat Bapak."

8. ⭐⭐ **Setelah dinilai berlaku, bentuk keluarannya apa?** Selembar dokumen? Task card? Cuma pemberitahuan ke Pak Rian?
   *→ Ini yang benar-benar penting: bentuk barang yang masuk ke sistem Anda.*
9. ⭐ Yang wajib di-forecast tanggal jatuh temponya — **AD dan Alert SB saja**, atau SB biasa dan SL juga?
   *→ Menguji asumsi di scope: SL informatif, SB biasa opsional, keduanya tidak di-forecast.*
10. Bagaimana menentukan sebuah AD berlaku untuk pesawat kita atau tidak? *(sekilas saja)*
11. Kalau manual/AMP direvisi, siapa yang memberitahu Pak Rian, dan lewat apa?
12. Berapa sering revisi itu datang untuk tiap tipe pesawat?

## 3 · Engineering Order — **cukup permukaan** ⏱️ 5 menit

> 🔵 Sama: pembuatan EO = modul 01. Yang perlu Anda tahu cuma **EO sampai ke modul Anda dalam bentuk apa**.

13. ⭐ Kapan sebuah EO diterbitkan? Apa yang memicunya? *(sekilas)*
14. ⭐⭐ **Setelah EO terbit, diserahkan ke siapa — dan berubah jadi WO oleh siapa?**
15. Nomor EO didaftarkan di mana? Ada daftar statusnya?
16. Kira-kira berapa EO dalam sebulan?

## 4 · Task card ⭐⭐ — garis batasnya persis di sini

17. ⭐⭐ **Siapa yang menentukan isi teknis task card — Engineering atau PPC?**

   💬 *Kalau dia balik nanya:* "Dari ngobrol dengan Pak Rian, dia yang merakit dokumennya. Tapi saya belum jelas siapa yang menentukan *isi* instruksinya — apa yang harus dikerjakan di lapangan."

   *→ Kalau jawabannya **Engineering**, maka isi task card dipasok modul 01 dan modul Anda cuma wadahnya. Kalau **PPC**, isinya masuk scope Anda. Ini menentukan batas PRD — catat jawabannya persis.*

18. ⭐ Di task card ada dicantumkan **nomor revisi manual sumbernya**?
19. Kalau manual sudah direvisi, task card lama diapakan?
20. Bagaimana tahu sebuah task berlaku untuk registrasi pesawat yang mana?

## 5 · Sehari-hari engineer di lapangan ⭐⭐ — **inti sesi** ⏱️ 20 menit

> 🟢 **Ini scope Anda yang sesungguhnya.** Engineer lapangan adalah **pengguna utama modul Production & Execution** — work order, transaksi komponen, validasi lisensi, tool crib, CRS. Sampai hari ini kita belum pernah mendengar pekerjaannya langsung; semua dari cerita Pak Rian, Pak Heri, dan Mba Michelle.
>
> **Jalankan blok ini apa pun jabatannya.** Bobot kepercayaan jawabannya ditentukan pertanyaan **3e**, bukan dilewati.

**Alur satu shift**

20a. ⭐⭐ **Coba ceritakan satu shift engineer dari datang sampai pulang.** → **Diam, jangan potong.**
20b. ⭐ Bagaimana dia tahu hari ini mengerjakan apa — ada yang membagi tugas, atau ambil sendiri?
20c. ⭐ Paket dokumen dari Pak Rian, diterima langsung oleh engineer-nya atau lewat Bapak dulu?
20d. Kalau pekerjaan belum selesai sampai ganti shift, serah terimanya bagaimana?

**Saat mengerjakan** *(ini yang menentukan bentuk antarmuka nanti)*

20e. ⭐⭐ **Sambil kerja, dia pegang apa?** Kertas task card, atau ada HP/tablet juga?
20f. ⭐ Task card dicentang **per langkah sambil jalan**, atau diisi sekaligus di akhir?
20g. Kalau tangannya kotor atau lagi di atas tangga, catatannya bagaimana?

**Lisensi, alat, material** *(tiga requirement modul saya sekaligus)*

20h. ⭐ Semua engineer punya lisensi, atau ada yang belum? Siapa yang boleh **tanda tangan** dan siapa yang hanya boleh mengerjakan?
20i. ⭐ Bagaimana Bapak memastikan orang yang tanda tangan **lisensinya masih berlaku** dan sesuai tipe pesawatnya?
20j. ⭐ Kalau butuh alat khusus, ambilnya bagaimana — ada pencatatan siapa pinjam apa?
20k. Alat yang perlu kalibrasi, bagaimana tahu masih valid?
20l. ⭐ Kalau butuh sparepart di tengah pekerjaan, dia sendiri yang ke store, atau ada yang mengambilkan?

**AFML** *(sumber angka jam terbang — ini pangkal seluruh perencanaan)*

20m. ⭐⭐ **Setelah pesawat mendarat, siapa yang mengisi AFML?** Engineer yang bertugas, atau ada yang khusus?
20n. Angka jam terbang & cycle-nya dia salin dari mana — dari pilot, atau dari instrumen?
20o. Pernah ada yang salah tulis? Kalau ketahuan salah, dikoreksinya bagaimana?

**Terakhir — jauh lebih berharga daripada wawancara**

20p. ⭐⭐ **Boleh saya ikut lihat satu engineer bekerja, sekitar 30 menit?** Tidak perlu wawancara, saya cuma mau lihat dokumennya dipakai seperti apa di lapangan.

💬 *Kalau dia ragu:* "Supaya sistemnya nanti tidak merepotkan mereka, Pak. Saya khawatir kalau saya rancang cuma dari cerita, hasilnya nggak cocok sama kondisi lapangan."

## 6 · Temuan di luar rencana

21. ⭐ Kalau mekanik menemukan kerusakan di luar perintah kerja, alurnya bagaimana?
22. Siapa yang menyetujui pekerjaan tambahan itu?
23. Ada batas kapan sesuatu jadi **major repair** yang butuh persetujuan lebih tinggi?
24. Pernah ada yang sampai harus dilaporkan ke DKPPU?

## 7 · Hubungan antar tim

25. Ke Pak Rian, Bapak menyerahkan apa? Dari dia, menerima apa?
26. Dengan tim inspector, di titik mana bersinggungan?
27. Dengan technical record?
28. Reliability atau analisis kerusakan berulang — itu di Bapak juga?

## 8 · Penutup (5 menit)

29. Apa yang paling bikin frustrasi dari pekerjaan ini?
30. ⭐ Kalau nanti ada sistem, apa yang justru **jangan** diotomatiskan?
31. Kalau punya layar sendiri, 3 informasi apa yang ingin langsung terlihat?
32. Siapa lagi yang sebaiknya saya temui?

---

## Yang diminta

- [ ] ⭐ Contoh **satu EO** yang sudah pernah terbit
- [ ] Contoh **daftar status AD/ASB** yang dipantau
- [ ] Contoh **task card** — untuk lihat apakah ada nomor revisi
- [ ] *(kalau dia dekat dengan lapangan)* Contoh **task card yang sudah terisi & tertanda tangan** — jauh lebih informatif daripada yang kosong
- [ ] *(kalau dia dekat dengan lapangan)* Daftar engineer + jenis lisensi & tipe pesawat yang dicakup
- [ ] Pastikan dokumen ini masuk ke folder Drive

## MoM sudah disiapkan

Kerangkanya di [[2026-08-03 Chief Line Maintenance - Pak Joko]], sudah pra-isi dengan yang perlu dicek. **Bagian 1–3 diisi dalam 30 menit setelah keluar.**

## Cara mencatat

Centang, jangan tulis. Yang ditulis hanya **angka + satuan · singkatan · nama · waktu**. Tiap topik selesai, **ulang balik lisan**. Keluar ruangan, **debrief suara 5 menit**. Selengkapnya: [[Instruksi Wawancara]]

## Kalau tinggal 20 menit

Urutannya tetap sama apa pun jabatannya — yang dipotong adalah blok 2 dan 3, karena itu wilayah modul 01:

**3a–3c** (peta istilah) → **20a** (satu shift engineer) → **20e–20f** (dia pegang apa saat kerja) → **20h–20i** (lisensi & siapa boleh tanda tangan) → **17** (siapa menentukan isi task card) → **20p** (izin ikut lihat).

Menutup **B7** dan sebagian **B4** di [[BPMN & Activity Flow - DRAFT]]. Blok 2–3 boleh ditanyakan lewat email menyusul — bentuknya konfirmasi, bukan eksplorasi.
