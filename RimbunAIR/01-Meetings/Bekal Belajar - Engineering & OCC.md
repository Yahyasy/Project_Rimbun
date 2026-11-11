---
tanggal: 2026-08-03
tipe: catatan-kerja
tags: [bekal, engineering, occ]
---

# Bekal Belajar — Engineering & OCC

**Audiens:** 🟡 Tim Nodewave — bahan baca sebelum wawancara.

> **Isi note ini:** model mental dua peran yang diwawancarai hari ini. Dibaca sekali sebelum berangkat, tidak perlu dibawa ke ruangan.
> Yang dibawa: [[Lembar Wawancara Chief Engineer]] dan [[Lembar Wawancara Staff OCC]].

**Kalau cuma sempat mengingat tiga kalimat:**

> **Engineering** menentukan *apa* dan *bagaimana*, bukan *kapan*.
> **OCC** memperlakukan data jam terbang sebagai produk sampingan operasi, bukan produk maintenance.
> **Engineer** ≠ **engineering** — yang pertama scope saya, yang kedua modul 01.

> ⚠️ **Sebelum membaca Bagian 1.** *Engineering* (departemen yang membuat AMP & EO) adalah **modul 01, bukan scope Anda**. *Engineer* (orang berlisensi yang mengerjakan di lapangan, sering disebut "mekanik") adalah **pengguna utama modul 02 Anda**. Bagian 1 di bawah membahas yang pertama — dibaca supaya nyambung ngobrol dan bisa memetakan serah terimanya, **bukan** karena itu yang akan Anda bangun. Rinciannya di [[Scope]] → *Engineer bukan engineering*.

---

# Bagian 1 · Engineering

## Inti perannya

**Penerjemah dan pengambil keputusan teknis.** Mereka mengubah aturan dari luar — pabrikan dan regulator — menjadi instruksi kerja yang bisa dieksekusi mekanik.

Cara memisahkannya dari peran lain yang sudah kita kenal:

| Peran | Menentukan |
|---|---|
| **Engineering** | **Apa** yang dikerjakan dan **bagaimana** caranya |
| **Planning** (Pak Rian) | **Kapan** dikerjakan |
| **Inspector** (Pak Heri) | Apakah hasilnya **sudah benar** |

Perbedaan waktunya juga jelas: **Engineering memutuskan sebelum kerja, Inspector memverifikasi setelah kerja.**

## Empat konsep

### 1. Corong MPD → AMP

Pabrikan menerbitkan **MPD** (Maintenance Planning Document) berisi ribuan task untuk tipe pesawat itu **di seluruh dunia**. Tidak semuanya relevan untuk satu operator.

Engineering menyaring: mana yang berlaku untuk armada sendiri, interval mana yang perlu diperketat karena kondisi operasi lokal. Hasilnya **AMP** — dan AMP inilah yang disahkan DKPPU, bukan MPD-nya.

> Contoh nyata yang sudah kita dengar dari Pak Heri: *anti-ice system* dikeluarkan dari program karena Indonesia tidak bersalju.

**Aturan emas:** operator boleh **memperketat** interval dari MPD, tapi **tidak boleh melonggarkan** tanpa kajian teknik dan persetujuan regulator.

### 2. EO adalah jawaban untuk yang tidak ada di buku

Task rutin sudah tercantum di AMP. Tapi kalau muncul sesuatu yang tidak tercakup — kerusakan tak terduga, modifikasi, atau cara alternatif yang perlu diputuskan — Engineering menerbitkan **Engineering Order**.

Jadi EO itu penanda: *ini di luar rutin, dan sudah ada yang bertanggung jawab memutuskan boleh*.

### 3. AD, SB, ASB — tiga tingkat paksaan

| | Dari | Sifat |
|---|---|---|
| **AD** — Airworthiness Directive | Regulator (FAA, EASA, DKPPU) | **Wajib**, ada tenggat waktu |
| **SB** — Service Bulletin | Pabrikan | **Opsional** |
| **ASB** — Alert Service Bulletin | Pabrikan | **Mendesak** — menyangkut keselamatan |

Engineering yang menilai mana yang berlaku untuk pesawat kita, lalu menerjemahkannya jadi pekerjaan. Di Rimbun Air ini disebut **ADSB** — gabungan AD dan Alert SB.

### 4. Effectivity

Satu task belum tentu berlaku untuk semua pesawat, **walaupun tipenya sama**. Tergantung nomor seri dan modifikasi yang sudah terpasang.

Ini sebabnya pertanyaan *"gimana tahu task ini buat pesawat yang mana?"* bukan pertanyaan sepele.

## Yang paling ingin didengar hari ini

**Siapa yang menentukan isi teknis task card.** Pak Rian bilang dia yang merakit dokumennya — tapi belum jelas siapa yang menentukan *isi instruksinya*. Jawaban ini langsung menutup batas peran Engineering vs Planning, dan itu bagian paling gelap sekarang.

---

# Bagian 2 · OCC

## Inti perannya

**Menjaga jadwal penerbangan tetap jalan.** Bukan maintenance sama sekali.

OCC — Operations Control Center — memantau pesawat ada di mana, berangkat dan mendarat jam berapa, siapa krunya, ada keterlambatan atau tidak. Itu pekerjaan operasi harian maskapai.

## Satu hal yang paling penting dipahami

**Bagi OCC, data jam terbang adalah produk sampingan.**

Mereka mencatat waktu pergerakan karena butuh mengatur operasi — **bukan** karena maintenance memerlukannya. Standar ketelitiannya mengikuti kebutuhan mereka sendiri, dan selisih beberapa menit mungkin tidak berarti apa-apa di sisi operasi.

Padahal di sisi maintenance, angka itu menentukan kapan pesawat masuk hanggar.

> 🎧 **Itu sebabnya pertanyaan "apakah OCC tahu datanya dipakai untuk maintenance" jadi penting.** Kalau jawabannya tidak, selisih data itu bukan kelalaian — itu konsekuensi wajar dari data yang dipakai untuk tujuan yang tidak pernah dirancang. Solusinya jadi berbeda sama sekali: bukan "minta mereka lebih teliti", tapi memperbaiki desain alirannya.

## Dua konsep

### 1. Empat stempel waktu

```
Block off  →  Take off  →  Landing  →  Block on
(roda mulai jalan)  (mengudara)  (menyentuh landasan)  (berhenti diganjal)
```

| Selisih | Namanya | Dipakai untuk |
|---|---|---|
| Block off → Block on | **Block time** | Operasi, jam kerja kru |
| Take off → Landing | **Airborne time** | **Perhitungan interval maintenance** |

Bedanya adalah waktu *taxi*. Kelihatan kecil, tapi kalau salah pakai, umur komponen terhitung habis untuk waktu pesawat mengantre di darat.

### 2. Dari mana angkanya bisa datang

Tiga kemungkinan, dan ketiganya punya tingkat ketelitian berbeda:

- **Laporan pilot** lewat radio
- **Laporan ground handling** di bandara
- **Tarikan otomatis** dari sistem pelacakan penerbangan

Mengetahui yang mana yang dipakai langsung menjelaskan kenapa bisa ada selisih dengan tulisan tangan di AFML.

## Cara membawakan soal selisih data

Michelle melaporkan angka OCC sering tidak cocok dengan AFML. **Jangan dibawa sebagai keluhan** — sesi akan berubah defensif dan Anda kehilangan informasi.

Bawakan sebagai rasa ingin tahu:

> *"Saya dengar kadang ada selisih kecil antara angka di sistem dengan yang ditulis di buku pesawat. Saya belum paham kenapa — apakah memang wajar, atau ada penyebab tertentu?"*

Begitu prosesnya terlihat, penyebab selisihnya akan menjelaskan dirinya sendiri.

---

## Pengingat terakhir

**OCC di luar 10 modul kontrak.** Sesi itu untuk memahami hulu data, bukan mengumpulkan requirement. Kalau muncul kebutuhan, catat lalu teruskan ke Rigen — jangan dijanjikan.

Terkait: [[Lembar Wawancara Chief Engineer]] · [[Lembar Wawancara Staff OCC]] · [[Glosarium]]
