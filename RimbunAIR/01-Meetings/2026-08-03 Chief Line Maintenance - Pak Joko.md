---
tanggal: 2026-08-03
tipe: meeting
tags: [wawancara, maintenance-control, chief-lm]
status: final
---

# Chief Line Maintenance — Pak Joko

**Audiens:** 🔴 Internal saja — berisi penilaian. Jangan dibagikan ke narasumber.

> **Sesi dengan cakupan terluas sejauh ini.** Dia menyentuh sembilan hal yang sebelumnya ❌ belum tergali, dan menutup tiga di antaranya sekaligus. Tapi cakupannya juga jauh melampaui scope saya — lihat bagian 5.

---

## Info sesi

| | |
|---|---|
| **Tanggal** | 3 Agustus 2026, siang · ±60 menit |
| **Narasumber** | **Pak Joko** — *Chief Line Maintenance Engineer* |
| **Posisi** | Kemungkinan besar **Chief Maintenance**, satu dari tiga Chief |
| **Tempat** | Daring |
| **Hadir dari kita** | Eza |
| **Rekaman** | Ada · transkrip di `_sumber-mentah/Mentahan Transcript - Chief Engineer - Pak Joko.csv` |
| **Verifikasi** | [[Tanya Jawab - Sesi 3 Agustus]] |

---

## 1 · Kesan langsung

**Tiga hal yang paling nempel:**

1. **Dia orang yang sudah tahu persis apa yang dia butuhkan** — bukan menjawab pertanyaan, tapi mendiktekan spesifikasi. Kata *"dashboard"* muncul belasan kali.
2. **Semua monitoring-nya di Excel buatan sendiri, dan belum selesai.** *"Masih satu-satuan, belum saya combine."*
3. **Dia bekerja sendirian** untuk cakupan kontrol yang sangat besar — pesawat, personel, tools, GSE, dokumen, audit.

**Yang di luar dugaan:** dia membuat template Excel dan dashboard-nya **memakai ChatGPT**, dan menyarankan saya melakukan hal yang sama alih-alih memberikan file aslinya.

**Yang terasa dia ragu:** saat diminta filenya — dijawab *"belum selesai semua"*, lalu dialihkan ke saran memakai ChatGPT. Mungkin memang belum rapi, mungkin juga tidak nyaman membagikannya.

---

## 2 · Yang dipelajari

### Perannya

**Maintenance control, scheduling, monitoring.** Bukan eksekusi, bukan perencanaan interval. Dia **koordinator yang memantau** pekerjaan engineer — bukan atasan struktural mereka.

Cakupan yang dia monitor, disebut sendiri dalam satu tarikan napas:

| Wilayah | Isinya |
|---|---|
| **Status pesawat** | Serviceable / [[Glosarium#A\|AOG]] · open [[Glosarium#D\|DMI]] |
| **Personel** | Validitas lisensi, *type rating authorization*, visa & paspor, training, medical, roster/shift |
| **Tools** | Database tools, kalibrasi, transaksi keluar-masuk, tool pinjaman |
| **GSE** | GPU (ground power unit), genset, emergency equipment |
| **Maintenance control** | Jadwal A-Check & periodical, defect control, engine & APU monitoring |
| **Komponen** | Database part, rotable / consumable / chemical / expendable, shelf life chemical |
| **Dokumen** | Manual pabrikan, record transit/weekly/daily check, dokumen pesawat (CoA, CoR) |
| **Audit** | Temuan internal & eksternal, status open/close, evidence untuk closing |
| **Procurement** *(memantau, bukan menjalankan)* | Status PO untuk part yang menahan DMI |

### Alur kerjanya dalam siklus WO

1. **Planner menurunkan task** — *"dari sisi planner ngeluarin task buat besok Senin"*
2. **Pak Joko mendistribusikan** ke engineer, sekalian menanyakan kendala material
3. Engineer mengerjakan
4. **Planner memeriksa duluan** — kelengkapan stamp, tanda tangan [[Glosarium#R\|RII]]
5. **Pak Joko memeriksa halaman belakang task card**, lalu **sign + stamp di halaman depan**
6. **Inspector** verifikasi akhir
7. WO close → masuk database → LD/ND diperbarui

> Lapisan nomor 5 sebelumnya tidak ada di catatan kita. Sekarang jelas: **Pak Joko wajib di semua WO**, karena dialah penanggung jawabnya.

### Dokumen yang disebut

| Dokumen | Dari siapa | Ke siapa | Bentuk |
|---|---|---|---|
| Task card daily / transit / weekly | Form baku yang sudah ada | Engineer duty | Kertas, ingin online |
| Task card A-Check / C-Check / yearly | Planner | Engineer | Kertas |
| Form pre-flight check | Baku | Engineer | Kertas |
| Lampiran temuan inspeksi | Engineer | Ikut task card | Kertas |
| [[Glosarium#A\|AFML]] | Engineer yang terbang | — | Buku, di-*create* juga di MSS |
| Sertifikat kalibrasi | Vendor third party | Pak Joko | Kertas |
| Certificate of Airworthiness · Certificate of Registration | DKPPU | Rimbun | Kertas, berlaku 1 tahun |
| MEL | Diterbitkan Rimbun | Acuan DMI | Dokumen |

### Angka yang disebut

- **AMEL** berlaku maksimal **3 tahun**
- **Company Authorization** — misal 1 atau 2 tahun, **tidak boleh melebihi masa AMEL**
- **Medical health check** — 2 tahunan, untuk kru ATR yang melayani Harbour Energy
- **DMI kategori C** — batas **10 hari** untuk rektifikasi
- Reminder kalibrasi & lisensi — **1 bulan** sebelum jatuh tempo
- Reminder DMI — **1 hari** sebelum jatuh tempo
- Contoh cruising level untuk engine monitoring — **37.000 kaki**

### Nama yang disebut

**Zainul** — ditanya soal status kalibrasi tools. Kemungkinan kustodian tool crib, **calon pengguna modul saya**.
**Pak Sandi** — inspector, disebut sejajar Pak Heri untuk melengkapi evidence inspeksi DKPPU.
**Mas Sidiq** — material control, yang menanyakan part tak dikenal terpasang di pesawat.
**Pak Andi** — disebut sebagai manajer sistem, lebih paham detail MSS.

---

## 3 · Yang berbeda dari pemahaman sebelumnya ⭐

| Yang kita catat sebelumnya | Yang dia bilang | Siapa yang benar |
|---|---|---|
| **"Erod"** staf Engineering penerbit EO | Nama itu tidak pernah ada | **Kita salah** → [[Riwayat Koreksi]] #10 |
| **"Chief LM"** penyetuju WO, tanpa nama | Dialah orangnya | **Terpecahkan** → #11 |
| Rantai ttd: engineer → PPC → inspector → Chief Inspector | Ada **Pak Joko** antara planner dan inspector | Kita kurang satu lapis |
| Task card semuanya diterbitkan planner | Daily/transit/weekly **form baku**, diisi sendiri oleh engineer | Kita menyamaratakan |
| Harbour Energy menawarkan sistem mereka | Hanya mempertanyakan kehandalan | **Kita salah** → #12 |

**Yang terkonfirmasi benar:**

- MSS memang dipakai untuk mencatat penerbangan, komponen on/off dengan P/N & S/N, dan engine monitoring — sejalan dengan keterangan Mba Michelle
- Angka jam terbang **bukan** dihitung maintenance: *"untuk yang ngitung-ngitung jamnya dari sisi operasional"*
- Tanda tangan basah masih berlaku penuh — dia *sign + stamp* fisik

---

## 4 · Kutipan penting

> *"Untuk dari sisi saya kemungkinan untuk kontrol di pesawatnya, terus scheduling, habis itu untuk maintenance control."*

> *"Kalau yang daily, transit check, weekly check, itu kan udah sehari-hari, emang task-nya baku. Kalau yang kayak A-Check, yearly, terus C-Check, nah itu yang ngontrol dari engineering planner. Kalau yang sehari-hari mah dari kita sendiri, tinggal ngisi-ngisi datanya."*

> *"Kalau datanya udah lengkap, baru saya sign di depannya, di halaman depan."*

> *"Saya masih bikin manual database-nya. Jadi bikin kayak Excel gitu."*

> *"Kalau yang AMEL kan yang ngeluarin dari authority, dari Perhubungan. Kalau yang company authorization tergantung dari sisi quality-nya, dari Chief Inspector. Cuma nggak ngelebihin dari AMEL-nya."*

> *"Misalkan di flight hour sama flight cycle sekian kita minjem. Nanti balikinnya di flight hour berapa, flight cycle berapa — buat acuan untuk pembayaran."*

> *"Kalau jam-jam ini salah masukin, semuanya ke belakang ngacak-ngacak semua."*

---

## 5 · Tafsir saya *(bukan yang dia bilang)*

- **(asumsi)** *"Engineering planner"* yang dia maksud = **Pak Rian**, bukan departemen lain. Dasarnya: Pak Rian berada di bawah Chief **PPC Engineering**, dan Michelle juga menyebut *"planner create"*. Kalau benar, **tidak ada departemen Engineering terpisah yang menerbitkan task card** — dan satu-satunya artefak Engineering yang belum jelas pemiliknya tinggal **EO**.
- **(asumsi)** Ada **dua keluarga pekerjaan** dengan alur berbeda: *line check* harian yang dipicu kalender dan tidak melahirkan WO, dan *scheduled check* yang dipicu ambang LD/ND dan melahirkan work package. Ini pola standar industri, dan cocok dengan semua yang kita dengar.
- **(asumsi)** Sebagian besar daftar keinginannya **bukan modul saya** — personel, training, medical, procurement, GSE, audit, publication. Yang benar-benar milik saya dari sesi ini: **tool crib & kalibrasi**, **validasi lisensi**, **WO & non-routine**, **DMI/deferral**, **component transaction**.
- **(asumsi)** Penolakannya memberi file Excel bukan soal kerahasiaan, melainkan karena **memang belum ada yang layak ditunjukkan**. Kalau benar, itu justru memperkuat kasus sistem — kontrolnya saat ini bergantung pada satu orang dan beberapa file setengah jadi.

---

## 6 · Yang masih gelap

| Yang belum jelas | Kenapa penting | Tanya ke siapa |
|---|---|---|
| **Siapa yang menyusun EO** | Satu-satunya artefak Engineering yang belum ada pemiliknya | Mas Bobby |
| Apakah *"engineering planner"* = Pak Rian | Menentukan ada tidaknya lane Engineering terpisah di BPMN | Pak Rian, sesi 2 |
| **B4** — non-routine bernomor otomatis, atau sekadar lampiran? | Scope saya menyebut *"penomoran otomatis"*; yang dia jelaskan lampiran di balik task card | Pak Rian / observasi |
| WO tetap di-close walau material kurang — praktik baku atau kasus? | Kalau baku, aturan closing di sistem harus mengakomodasi *out of phase* | Pak Rian / Pak Joko |
| Jumlah engineer & **matriks lisensi × tipe pesawat** | Inti requirement HR License Validation | Pak Joko |
| Nama manual yang dipakai tim teknik | Tertangkap *"AMM…PC…RM…DMM"*, dia juga sebut CMM. **Jangan ditebak** | Mas Bobby / Mbak Hilda |
| Isi Excel monitoring-nya | Itu spesifikasi dashboard yang dia inginkan | Mas Bobby |

---

## 7 · Istilah yang sudah dipecahkan

| Istilah di transkrip | Artinya |
|---|---|
| *"Aji"* | **AOG** — Aircraft on Ground |
| *"send"* / *"send and stamp"* | **sign** — tanda tangan |
| *"fing"* / *"pendingan"* | **finding** — temuan |
| *"har komponen"* | **[[Glosarium#H\|Hard Time]] component** |
| *"brick wear"* | **brake wear** |
| *"auto paste"* | **out of phase** — pekerjaan digeser ke luar jadwal check |
| *"AU monitoring"* | **APU monitoring** |
| *"yang di Nine"* | **NG** — Boeing 737-800 |

---

## 8 · Action items

- [ ] Minta **contoh task card terisi + lampiran temuan** — PIC: Eza — via Mas Bobby
- [ ] Minta **Excel monitoring** Pak Joko *(sudah ditolak sekali — coba lewat Mas Bobby)* — PIC: Eza
- [ ] Minta **daftar engineer + AMEL + Company Authorization** — PIC: Eza
- [ ] Minta salinan **MEL Rimbun** — dasar kategori DMI A/B/C — PIC: Eza
- [ ] Cari tahu **siapa penyusun EO** — PIC: Eza
- [ ] Jadwalkan **observasi lapangan ke Cengkareng** — PIC: Eza — via Mas Bobby
- [ ] Teruskan **tolok ukur Harbour Energy** (akurasi jam + jejak audit) ke Rigen sebagai acceptance criteria — PIC: Eza

**Yang bukan modul saya, tapi jangan hilang** — teruskan ke Rigen: kontrol personel & training (06), status PO & procurement (04), GSE & emergency equipment, audit finding control, dokumen pesawat CoA/CoR.

---

## Yang tertutup dari sesi ini

Tiga requirement yang sebelumnya ❌ **belum tergali** sekarang punya isi:

**Defect & Deferred (DMI)** — MEL terbitan Rimbun → DMI kategori A/B/C → kategori C = 10 hari → rektifikasi atau **extend dengan referensi status PO** → reminder H-1 → koordinasi ke procurement.

**Tool Crib & Kalibrasi** — database tools, transaksi keluar-masuk, tool pinjaman, sertifikat dari vendor bersertifikasi nasional, reminder 1 bulan sebelum expiry.

**HR License Validation** — **dua tanggal kedaluwarsa**: AMEL (Perhubungan, maks 3 tahun) dan Company Authorization (Chief Inspector, ≤ AMEL). Assessment ulang 1 bulan sebelum habis.

Plus satu yang benar-benar baru dan **belum ada di scope mana pun**: **part pinjaman antar-operator**, dicatat pada FH/FC saat dipasang dan saat dikembalikan, jadi dasar pembayaran. Sekarang murni catatan manual.

---

Terkait: [[Proses Manual Maintenance - DRAFT]] · [[BPMN & Activity Flow - DRAFT]] · [[Scope]] · [[Riwayat Koreksi]] · [[2026-08-03 Staff OCC - Pak Pipit]]
