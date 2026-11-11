---
tanggal: 2026-08-03
tipe: catatan-kerja
tags: [ekspor, lucid, bpmn, gama]
status: siap kirim
---

# Ekspor ke Lucidchart — untuk Gama

**Audiens:** 🟡 Tim Nodewave.

> **Isi note ini:** versi Mermaid yang sudah disesuaikan supaya bisa diimpor Lucidchart, plus CSV cadangan.
> **Sumbernya tetap** [[BPMN & Activity Flow - DRAFT]] — kalau prosesnya berubah, ubah di sana dulu, baru perbarui note ini.

---

## Filenya sudah dipisah — tinggal buka & salin semua

Supaya tidak perlu menyalin dari dalam markdown, tiap diagram sudah jadi file teks sendiri di folder **`Diagram Mermaid/`**:

- `1 - End to End.txt`
- `2 - Line Check Harian.txt`
- `3 - Defect dan DMI.txt`

Buka salah satu, **Ctrl/Cmd + A** lalu **Ctrl/Cmd + C**. Itu yang ditempel.

---

## Cara paling gampang: minta Gama yang impor

Lucid itu alatnya dia. Kirim tiga file `.txt` di atas plus tautan ke note ini — selesai. Dia yang tahu mau digambar ulang seperti apa dalam BPMN 2.0.

Sisa panduan di bawah ini untuk kalau Anda tetap mau coba sendiri.

---

## Jalur 1 · Impor Mermaid ke Lucidchart

1. Buka **lucid.app**, login
2. Klik **`+ New`** → **Lucidchart** → **Blank document**
3. Di menu atas klik **`Insert`**
4. Cari **`Diagram as Code`** — ikonnya `</>`. Di sebagian versi namanya **`Mermaid`** atau ada di `File → Import`
5. Panel terbuka di sisi kanan → pastikan bahasa yang dipilih **Mermaid**
6. **Tempel** isi file `.txt` tadi
7. Klik **`Insert`**

> ⚠️ **Kalau `Diagram as Code` tidak ada di menu Insert**, fitur ini tidak aktif di paket akun Anda. Jangan dicari-cari — langsung ke Jalur 2.

### Yang sudah saya sesuaikan dari versi asli

Kode di bawah **bukan salinan mentah** dari note sumber. Tiga hal diubah supaya importer tidak tersedak:

| Diubah | Alasan |
|---|---|
| `classDef` & `class` dihapus | Pewarnaan Mermaid tidak terbaca Lucid, dan sering bikin parser gagal |
| `direction TB` di dalam subgraph dihapus | Tidak didukung importer |
| **Subgraph bersarang diratakan** — hanya lane aktor, fase dibuang | Nested subgraph paling sering gagal jadi container |

Konsekuensinya: **penanda blok belum terkonfirmasi hilang** karena itu dibawa oleh pewarnaan. Daftarnya ada di bawah tiap diagram — perlu ditandai ulang manual di Lucid.

---

### Diagram 1 — End-to-end

```
flowchart TD
    subgraph PLT["Pilot dan co-pilot"]
        A1["Isi blok hitam AFML - discrepancy, fuel dipakai dan sisa"]
        A2["Catat engine data saat cruising"]
        A3["Co-pilot kirim data format baku"]
    end
    subgraph ENG1["Engineer lapangan"]
        A4["Isi blok putih AFML - oli, hidrolik, engine parameter"]
        A5["Tulis rectification atas discrepancy pilot"]
        A6["Catat component replacement - PN dan SN on dan off"]
        A7["Create record di MSS"]
        A8["Kirim foto AFML"]
        C2["Terima paket dan tanda tangan checklist serah terima"]
        C3["Kerjakan task"]
        GD{"Ada temuan di luar WO?"}
        C4["Catat di halaman belakang dan lampiran pengeluaran part"]
        C5["Tanda tangan basah dan engineering stamp"]
    end
    subgraph OCC["OCC Cengkareng"]
        A9["Bandingkan data co-pilot vs foto AFML"]
        A10["Isi kolom actual dan nomor AFML"]
        GA{"Nomor AFML cocok?"}
        A11["Koreksi nomor"]
    end
    subgraph SYS["Sistem"]
        A12["Sinkron otomatis ke MSS"]
        A13["Tarik otomatis - flight time, block time, cycle, fuel burn, uplift, nama crew"]
        AX["Data tidak muncul di sisi maintenance"]
    end
    subgraph TR["Technical Record"]
        A14["Rekonsiliasi hard copy vs MSS"]
        A15["Perbaiki ketidaksesuaian"]
        A16["Approve - TSN dan CSN terbit"]
        D7["Scan WO"]
        D8["Simpan ke Google Drive"]
    end
    subgraph PPC["PPC Planning"]
        B1["Update LD/ND - jam, cycle, tanggal"]
        B2["Spreadsheet hitung next due"]
        B3["Pantau remaining"]
        GB{"Mendekati ambang?"}
        B4["Tentukan jenis check"]
        B5["Susun kebutuhan material dan cek ketersediaan"]
        GC{"Material tersedia?"}
        B6["Ajukan permintaan pembelian"]
        B7["Ambil template - matriks tipe pesawat x jenis dokumen"]
        B8["Rakit paket dokumen - salin instruksi dari AMM atau MP"]
        B9["Beri nomor WO berurut merujuk entri LD/ND"]
        B10["Cetak paket hardcopy"]
        D1["Reviu kelengkapan stamp dan tanda tangan RII"]
        GE{"Lengkap?"}
    end
    subgraph CLM["Chief Line Maintenance"]
        C1["Distribusi task ke engineer dan tanyakan kendala material"]
        D2["Cek halaman belakang task card"]
        D3["Sign dan stamp halaman depan"]
    end
    subgraph INS["Inspector"]
        D4["Verifikasi akhir - ttd lengkap dan nilai final terisi"]
        GF{"Satisfied?"}
        D5["Alur penolakan - belum diketahui"]
        D6["Chief Inspector tanda tangan penutup"]
    end

    A1 --> A2
    A2 --> A3
    A3 --> A9
    A4 --> A5
    A5 --> A6
    A6 --> A7
    A7 --> A8
    A8 --> A9
    A9 --> A10
    A10 --> GA
    GA -- ya --> A12
    GA -- tidak --> AX
    AX --> A11
    A11 --> A10
    A12 --> A13
    A13 --> A14
    A14 --> A15
    A15 --> A16
    A16 --> B1
    B1 --> B2
    B2 --> B3
    B3 --> GB
    GB -- belum --> B3
    GB -- ya --> B4
    B4 --> B5
    B5 --> GC
    GC -- tidak --> B6
    GC -- ya --> B7
    B6 --> B7
    B7 --> B8
    B8 --> B9
    B9 --> B10
    B10 --> C1
    C1 --> C2
    C2 --> C3
    C3 --> GD
    GD -- ya --> C4
    GD -- tidak --> C5
    C4 --> C5
    C5 --> D1
    D1 --> GE
    GE -- tidak --> C3
    GE -- ya --> D2
    D2 --> D3
    D3 --> D4
    D4 --> GF
    GF -- tidak --> D5
    GF -- ya --> D6
    D6 --> D7
    D7 --> D8
    D6 --> B1
```

**Tandai ulang di Lucid sebagai belum terkonfirmasi:** `GB` *(B5)* · `C3` *(B7)* · `C4` *(B4)* · `D5` *(B6)* · `AX` *(jalur gagal, sudah pasti tapi perlu menonjol)*

---

### Diagram 2 — Line check harian

```
flowchart TD
    START(["Pesawat dijadwalkan terbang"])
    subgraph ENGB["Engineer duty"]
        L1["Ambil tools dari store - fuel drain, pressure gauge"]
        L2["Pre-flight check"]
        L3["Isi form pre-flight"]
        L4["Kembalikan tools"]
        L5["Transit check saat transit"]
        L6["Daily check - brake wear, tire pressure"]
        L7["Weekly check"]
        L8["Isi AFML dan create record MSS"]
        BG{"Ada defect?"}
    end
    FLY(["Pesawat terbang"])
    DMI["Masuk proses DMI"]
    DONE(["Selesai"])

    START --> L1
    L1 --> L2
    L2 --> L3
    L3 --> L4
    L4 --> FLY
    FLY --> L5
    L5 --> L6
    L6 --> L7
    L7 --> L8
    L8 --> BG
    BG -- ya --> DMI
    BG -- tidak --> DONE
```

**Seluruh diagram ini masih kerangka** — blok B8. Tandai semuanya putus-putus kecuali `L8`.

---

### Diagram 3 — Defect dan DMI

```
flowchart TD
    D0(["Defect ditemukan - discrepancy pilot atau temuan engineer"])
    D1["Rujuk MEL terbitan Rimbun"]
    DG1{"Boleh terbang dengan defect ini?"}
    D2["Pesawat AOG - rektifikasi wajib"]
    D3["Masuk DMI kategori A, B, atau C"]
    D4["Timer berjalan - kategori C sepuluh hari"]
    DG2{"Part tersedia?"}
    D5["Cek status PO ke procurement"]
    DG3{"Datang sebelum jatuh tempo?"}
    D6["Extend - referensi wajib status PO"]
    D7["Pinjam part dari operator lain - catat FH dan FC saat pasang"]
    D8["Rektifikasi dan tulis di AFML"]
    D9(["Pesawat serviceable"])

    D0 --> D1
    D1 --> DG1
    DG1 -- tidak --> D2
    DG1 -- ya --> D3
    D2 --> DG2
    D3 --> D4
    D4 --> DG2
    DG2 -- ya --> D8
    DG2 -- tidak --> D5
    D5 --> DG3
    DG3 -- ya --> D8
    DG3 -- tidak --> D6
    D6 --> D8
    D5 --> D7
    D7 --> D8
    D8 --> D9
```

**Tandai putus-putus:** `D7` — part pinjaman, jalur darurat, belum dipastikan sebagai praktik baku.

---

## Jalur 2 · Impor CSV *(kalau Jalur 1 tidak tersedia)*

File: **`Lucid - Import Diagram.csv`** di folder yang sama.

**Lucidchart → `File` → `Import Data` → `Process Diagram` → unggah CSV**

Isinya tiga halaman sekaligus, dibedakan kolom `Page ID`:

| Page ID | Isi |
|---|---|
| 1 | End-to-end |
| 2 | Line check harian |
| 3 | Defect dan DMI |

### Yang perlu diperhatikan

CSV ini **tidak membawa swimlane**. Kolom `Lane` saya sertakan sebagai keterangan, tapi Lucid mengabaikannya — lane-nya digambar manual setelah shape masuk. Yang dihemat CSV adalah bagian paling melelahkan: mengetik 60-an node dan menyambungkannya satu per satu.

Nama kolom mengikuti format impor standar Lucidchart. **Saya tidak bisa mengetesnya**, jadi kalau importer menolak, kemungkinan besar cuma soal nama kolom yang perlu disesuaikan dengan template yang Lucid tawarkan saat impor.

---

## Jalur 3 · Lewat draw.io *(gratis, paling jarang gagal)*

Kalau dua jalur di atas mentok. Agak memutar, tapi tidak butuh akun berbayar sama sekali.

1. Buka **app.diagrams.net** *(dulu draw.io)* — tidak perlu login
2. Pilih **`Create New Diagram`** → **Blank Diagram** → **`Create`**
3. Di toolbar atas klik tombol **`+`** *(Insert)*
4. Pilih **`Advanced`** → **`Mermaid...`**
5. Hapus contoh yang ada, **tempel** isi file `.txt`
6. Klik **`Insert`** — diagramnya muncul
7. **`File`** → **`Export as`** → **`VSDX`** → simpan
8. Balik ke Lucidchart: **`File`** → **`Import`** → pilih file `.vsdx` tadi

Kalau Anda cuma butuh gambarnya untuk dipresentasikan — **berhenti di langkah 6**. Dari situ bisa langsung `File → Export as → PNG` atau `PDF`, tidak perlu Lucid sama sekali.

---

## Catatan untuk Gama

**Shape library.** Node di CSV memakai library **Flowchart** karena paling aman. Untuk BPMN 2.0 yang sebenarnya, padanannya:

| Di sini | BPMN 2.0 |
|---|---|
| Terminator | Start / End Event |
| Process | Task |
| Decision | Exclusive Gateway |

**Yang tidak ikut terbawa dan harus dibaca dari note sumber:**

- **Enam blok belum terkonfirmasi** — daftarnya di [[BPMN & Activity Flow - DRAFT]] bagian 7
- **Register 80 aktivitas** — bagian 4, termasuk aktivitas paralel yang tidak masuk diagram: kalibrasi, kontrol lisensi, audit, dokumen pesawat
- **16 aturan bisnis** — bagian 8
- **Data object per dokumen** — bagian 6

**Satu hal yang jangan disederhanakan saat digambar ulang:** jalur `GA → AX` di diagram 1. Kalau nomor AFML salah, datanya **hilang**, bukan salah tampil — dan itu perilaku yang paling penting ditangkap sistem baru.

---

Terkait: [[BPMN & Activity Flow - DRAFT]] · [[Proses Manual Maintenance - DRAFT]]
