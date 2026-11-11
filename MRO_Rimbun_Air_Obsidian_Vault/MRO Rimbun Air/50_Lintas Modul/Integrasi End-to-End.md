---
tipe: lintas
modul: lintas
diperbarui: 2026-11-11
tags: [lintas]
aliases: [Alur Data End-to-End, Integrasi Lintas Modul]
---
# Integrasi End-to-End

Empat cerita data yang menghubungkan Modul 2, 3, 4 dan modul lain. Dipakai untuk menguji kelengkapan desain dan menyiapkan cek silang klien (Mas Bobi) atas sambungan antarmodul. Tabel aliran rinci ada di [[M3 Integrasi & DMI]] dan [[M4 Status Objek & Integrasi]].

## 1. Dari Maintenance Program sampai last done

```mermaid
sequenceDiagram
  participant M1 as M1 EC
  participant M2 as M2 Planning
  participant M3 as M3 WO
  participant M4 as M4 AFML
  M2->>M2: MP Active (Chief PPC) + Task Library
  M1-->>M2: TSN/CSN per SN, task EO/Non-routine
  M4-->>M2: Closing AFML → hitung ulang forecast (as of)
  M2->>M3: Check Pack / task / baris HT-DMI → Form WO (Asal Planning)
  M3->>M3: WO New → Approved → Issued → WIP
  M3->>M2: Task card Closed → last done (tanggal, TSN, CSN)
  M3->>M1: Compliance AD/EO
  M2->>M2: Due berikutnya dari interval
```

## 2. Dari defect sampai DMI ditutup

```mermaid
sequenceDiagram
  participant AF as M4 AFML
  participant DD as M4 Defect & Deferred
  participant M2 as M2 Forecast
  participant M3 as M3 WO
  participant M6 as M6 Procurement
  AF->>DD: Discrepancy (Submit → Waiting TR)
  DD->>DD: Jalur Deferred → DMI Open (Limit Type tgl/FH/FC)
  DD->>M6: RQ (bila part kurang) → RFQ → order
  M6-->>DD: tanggal order & kedatangan (untuk DMI Extension)
  DD-->>M2: DMI open masuk forecast
  M2->>M3: Buat WO dari baris DMI
  M3->>M3: Baris task card bersumber DMI, Closed
  M3->>DD: WO Close + konfirmasi → DMI "Closed by WO"
```

## 3. Dari component change sampai konfigurasi

```mermaid
sequenceDiagram
  participant AF as M4 AFML / M3 task card
  participant CT as M4 Component Transaction
  participant M5 as M5 Gudang
  participant M1 as M1 Konfigurasi
  participant M6 as M6 Procurement
  M5->>CT: Issue ke WO → Pending Install
  AF->>CT: Record Removal (Scheduled bila ada WO, Event Date/Time)
  CT->>M5: Pending RTS (S/U/S)
  AF->>CT: Record Installation (PN divalidasi)
  CT->>M1: Konfigurasi & umur part (Sync M1, Resend)
  CT->>M6: Leg type per PN & SN
  M5->>M6: Part U/S → RO langsung (tanpa RQ)
  AF->>M1: Closing AFML → jam & cycle pesawat (+ komponen, usulan)
```

## 4. Dari tanda tangan sampai audit

```mermaid
sequenceDiagram
  participant MOD as M2/M3/M4 layar
  participant SSG as SSG
  participant M1 as M1 Employee
  MOD->>SSG: checkAccess (tampil tombol)
  MOD->>SSG: checkAuthority (aksi X) / approve (aksi A)
  SSG->>M1: status, lisensi, toggle, base
  SSG-->>MOD: izin + signature snapshot / tolak + alasan
  SSG->>SSG: audit log (append-only)
```

## Titik integrasi yang belum final

| Titik | Kode | Register |
|---|---|---|
| Pemicu last done (task card vs WO Closed) | M2 no 105, Q-M2-08 | [[M2 Open Questions]], [[M3 Open Questions]] |
| DMI tertutup otomatis atau konfirmasi | Q26-05, Q-27, M2 no 106 | [[M4 Open Questions]] |
| Jam komponen saat closing AFML | FQ-02, FQ-03 | [[M4 Open Questions]] |
| Hitung ulang forecast langsung setelah closing | FQ-04 | [[M4 Open Questions]] |
| Limit Type DMI di forecast | LX-01 | [[Isu Harmonisasi Lintas Modul]] |
| CML masuk forecast dan WO | CML-08, Q26-09, Q-43, M2 no 103 | M2, M3, M4 |
| Event WO Closed ke M5 | Q-36, LX-11 | [[M3 Open Questions]] |
| Pengaturan terpusat di SSG | LX-02 | [[Isu Harmonisasi Lintas Modul]] |
