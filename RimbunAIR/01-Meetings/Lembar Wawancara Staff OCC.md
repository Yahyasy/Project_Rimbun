---
tanggal: 2026-08-03
tipe: meeting
tags: [panduan, wawancara, occ]
status: lembar bawa — belum dilaksanakan
---

# Lembar Wawancara — Staff OCC

**Audiens:** 🟡 Tim Nodewave — lembar kerja, bukan untuk dibagikan ke narasumber.

> ⚠️ **Tujuan sesi ini berbeda dari sesi lain.**
> OCC ada di **departemen Operasional** — di luar 10 modul kontrak, apalagi di luar 3 modul saya. Jadi ini **bukan** sesi mengumpulkan requirement.
>
> Yang dicari: **memahami hulu data.** Angka jam terbang yang dipakai seluruh perhitungan maintenance ternyata berasal dari sistem mereka. Kita perlu tahu dari mana angka itu, seberapa bisa dipercaya, dan kenapa sering tidak cocok.
>
> **Jangan menjanjikan fitur apa pun.** Kalau mereka menyebut kebutuhan, catat dan teruskan ke Rigen — jangan diiyakan.

> 📖 **Baca dulu sebelum berangkat:** [[Bekal Belajar - Engineering & OCC]] — model mental kedua peran, lengkap dengan konsep dasarnya.

---

## 🎯 Yang dicari hari ini: **urutan**, bukan penjelasan

**Satu sesi = satu lane.** Untuk OCC, lane-nya cukup digambar sebagai *pool eksternal* — yang perlu jelas hanya **apa yang keluar dari mereka dan lewat apa**. Pertanyaan di bawah cuma checklist cakupan. Yang benar-benar menghasilkan diagram adalah satu kalimat ini:

> ⭐⭐ *"Coba satu penerbangan kemarin, Pak — dari pesawat mau berangkat sampai datanya masuk. Ceritakan dari awal."*
> lalu dorong terus: ***"terus apa?"*** — sampai angkanya keluar dari tangan mereka.

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

## Bekal: apa yang kita sudah tahu

Dari wawancara Technical Record (31 Jul):

- OCC punya **sistem sendiri**, terpisah dari MSS
- Data yang mereka pasok masuk otomatis ke AFML: **flight time · block time · total cycle · fuel burn · remaining · uplift · nama captain, FO, engineer**
- Engineer di lapangan tinggal *create* AFML, angkanya sudah muncul sendiri
- Lokasi mereka di **Cengkareng**, technical record di Meruya
- **Pak Andi** disebut sebagai orang yang paling paham bagian movement

### Masalah yang dilaporkan dari hilir

Michelle menemukan **angka OCC sering tidak cocok dengan AFML tulisan tangan**:

> *"Fuel burn di AFML aktualnya 420, tapi di sistem jadi 450. Kadang block off, take off, landing ada kelebihan berapa menit, atau malah beda jam — take off jam 18:54 tapi block off jam 7:50."*

Dia memperbaikinya manual tiap hari, karena engineer tidak punya akses edit.

> ⚠️ **Cara membawakan ini penting.** Jangan datang seolah melaporkan kesalahan mereka. Yang kita cari adalah **bagaimana datanya dikumpulkan** — selisihnya akan menjelaskan dirinya sendiri begitu prosesnya terlihat.

---

## Kamus singkat

| Kalau dia sebut | Artinya |
|---|---|
| Movement | Data pergerakan pesawat — berangkat, mendarat, waktunya |
| Block off / block on | Saat roda mulai jalan dan berhenti diganjal |
| Take off / landing | Saat mengudara dan menyentuh landasan |
| Fuel uplift · fuel burn | Bahan bakar yang diisi dan yang terpakai |
| Cycle | Satu kali lepas landas + mendarat |
| AFML | Buku catatan penerbangan yang dibawa di pesawat |

**Kalimat penyelamat:** *"Maaf, itu maksudnya apa ya?"* · *"Jadi kalau saya tangkap maksudnya X, betul?"*

---

## 0 · Kenalan (5 menit)

1. Nama dan jabatan resminya? *(minta disebut untuk rekaman)*
2. OCC ini di bawah departemen apa? Ada berapa orang?
3. Apakah bekerja bergiliran atau jam kantor biasa?

## 1 · Hari kerja kemarin (10 menit) ⭐

4. ⭐ **Kemarin ngerjain apa saja? Coba dari pagi.**
   → **Diam, jangan potong.**
5. Mana yang paling makan waktu?

## 2 · Dari mana datanya ⭐⭐ — inti sesi

6. ⭐⭐ **Data pergerakan pesawat — jam berangkat, mendarat, dan sebagainya — masuk ke sistem lewat apa?**

   💬 *Kalau dia balik nanya:* "Saya lagi memetakan perjalanan data jam terbang, Pak. Ternyata angka yang dipakai untuk menghitung jadwal maintenance itu berasal dari sistem OCC. Saya mau paham dari mana asalnya sebelum masuk ke situ."

7. ⭐⭐ **Diketik manual, atau ditarik otomatis dari suatu tempat?** Kalau ditarik, dari mana?
8. ⭐ Siapa yang melaporkan — pilot, ground handling, atau menara?
9. ⭐ Berapa lama setelah pesawat mendarat sampai datanya masuk?
10. Kalau pesawat mendarat tengah malam atau di luar jam kerja, bagaimana?
11. Ada tahap pengecekan sebelum data dianggap final?

## 3 · Isi datanya

12. ⭐ Data apa saja yang OCC catat untuk satu penerbangan?
13. Yang mana yang diketik orang, yang mana yang muncul sendiri?
14. Fuel — angkanya dari mana? Dari pilot atau dari pengisian?
15. Nama crew — captain, FO, engineer — itu dari jadwal atau diinput per penerbangan?

## 4 · Selisih angka ⭐

*Bawakan sebagai rasa ingin tahu, bukan keluhan.*

16. ⭐ **Pernah ada kondisi angka di sistem berbeda dengan catatan di pesawat?** Biasanya karena apa?

   💬 *Cara membuka:* "Saya dengar kadang ada selisih kecil antara angka di sistem dengan yang ditulis di buku pesawat. Saya belum paham kenapa — apakah memang wajar, atau ada penyebab tertentu?"

17. Kalau ada yang salah, siapa yang bisa memperbaiki?
18. Ada yang pernah minta perbaikan ke sini? Alurnya bagaimana?
19. Apakah OCC tahu kalau datanya dipakai untuk menghitung jadwal maintenance?

> 🎧 **Dengar baik-baik jawaban 19.** Kalau ternyata mereka **tidak tahu** datanya dipakai untuk maintenance, itu temuan penting — artinya tidak ada insentif akurasi di sisi hulu, dan itu masalah desain, bukan masalah orang.

## 5 · Sistem mereka

20. ⭐ Sistemnya namanya apa? Dibuat siapa?
21. Datanya bisa diekspor?
22. Sistem lain ada yang menarik data dari sini selain AFML?

## 6 · Penutup (5 menit)

23. Apa yang paling bikin frustrasi dari pekerjaan ini?
24. Siapa lagi yang sebaiknya saya temui soal data ini?

---

## Yang diminta

- [ ] ⭐ **Tangkapan layar** tampilan data movement satu penerbangan
- [ ] Nama sistem dan siapa yang memeliharanya
- [ ] Nama & jabatan orang yang disebut

## MoM sudah disiapkan

Kerangkanya di [[2026-08-03 Staff OCC - Pak Pipit]], sudah pra-isi dengan yang perlu dicek. **Bagian 1–3 diisi dalam 30 menit setelah keluar.**

## Cara mencatat

Centang, jangan tulis. Yang ditulis hanya **angka + satuan · singkatan · nama · waktu**. Tiap topik selesai, **ulang balik lisan**. Keluar ruangan, **debrief suara 5 menit**. Selengkapnya: [[Instruksi Wawancara]]

## Kalau tinggal 15 menit

Pertanyaan **6, 7, 9, 16, 19** saja.

Lima itu menjawab: dari mana datanya, seberapa cepat, kenapa bisa selisih, dan apakah mereka sadar datanya dipakai maintenance.
