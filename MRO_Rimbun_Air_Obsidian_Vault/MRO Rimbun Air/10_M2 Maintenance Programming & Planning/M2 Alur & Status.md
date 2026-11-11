---
tipe: alur
modul: M2
diperbarui: 2026-11-11
sumber:
  - claude/Review_Desain_Modul2_Setelah_Revisi_8Nov.md
  - claude/Decision_Log_Modul2_9Nov.md
tags: [m2]
aliases: [Alur Modul 2, User Flow M2]
---
# M2 Alur & Status

## Perjalanan data (alur presentasi)

Urutan ini dipakai untuk presentasi ke klien dan untuk menguji kelengkapan desain: satu tipe pesawat, satu MP, satu registrasi, satu task dari awal sampai akhir.

```mermaid
flowchart LR
  T["Aircraft Type"] --> D["MP Draft<br/>(PPC Staff)"]
  D --> A["Tab Aircraft:<br/>daftar registrasi"]
  A --> K["Task Library:<br/>isi task / Import"]
  K --> S["Submit"]
  S --> AP{"Chief PPC"}
  AP -->|Approve| ACT["MP Active<br/>versi lama Archived"]
  AP -->|Reject + catatan| D
  ACT --> F["Forecast Dashboard<br/>(MP Task, AD/SB&EO, HT, DMI, CML)"]
  F --> STE["STE per kejadian"]
  F --> CP["Check Pack<br/>(WCF Priority)"]
  F --> WO["Buat WO<br/>(baris DMI/HT)"]
  CP --> WO3["Form WO Modul 3"]
  WO --> WO3
  WO3 --> CL["Close task card<br/>(Modul 3)"]
  CL -->|last done: tanggal, TSN, CSN| F
  AFML["Closing AFML<br/>(Modul 4)"] -->|hitung ulang jam, umur, DMI| F
```

| No | Langkah | Layar | Pesan kunci |
|---|---|---|---|
| 1 | Siapkan tipe pesawat | Aircraft Type list/form/detail | Identitas tipe saja; FEC dan STE Basis dihapus |
| 2 | Buat MP Draft | Daftar MP, Create MP | MP Number sama untuk semua revisi, terkunci setelah simpan |
| 3 | Daftarkan pesawat pemakai MP | Tab Aircraft, popup Add Aircraft | Hanya registrasi bertipe sama; MP Start Date = awal forecast |
| 4 | Isi task | Task Library, Add Task, Pratinjau, Import | Lima bagian; threshold lalu interval; effectivity pesawat atau komponen |
| 5 | Task dari modul lain | Detail task asal EO | EO dan Non-routine dari Modul 1, read-only; Copy membuat task MP |
| 6 | Ajukan dan setujui MP | Submit, tab Internal Approval | Hanya Chief PPC; approve → Active, versi lama Archived, forecast dihitung ulang |
| 7 | Revisi MP | Copy MP, Riwayat Revisi | Task dan interval tersalin; riwayat tidak bisa dihapus |
| 8 | Data pendukung | Check Type, Hard Time, Format Nomor | Check Type hanya referensi; HT batas per PN, sisa per SN |
| 9 | Pantau jatuh tempo | Forecast, Detail Due | Dihitung ulang setiap closing AFML |
| 10 | Perpanjang jatuh tempo | Add STE, Detail STE | Tanpa hitungan toleransi; dokumen fisik dilampirkan |
| 11 | Bentuk paket kerja | WCF Priority, Check Pack | Wadah bebas; effectivity menyaring task |
| 12 | Buat WO langsung | Forecast baris HT/DMI → Create WO | Form WO Modul 3 terisi, bertanda asal planning |
| 13 | Task di luar paket | Out of Phase | Otomatis/Manual, bisa dikembalikan |
| 14 | Notifikasi dan laporan | Notifikasi Due, Report Center | Ambang 10%; parameter → tampilkan → ekspor |

## Status Maintenance Program

```mermaid
stateDiagram-v2
  [*] --> Draft: Create MP / Copy MP
  Draft --> WaitingApproval: Submit (PPC Staff)
  WaitingApproval --> Draft: Reject + catatan (Chief PPC)
  WaitingApproval --> Active: Approve (Chief PPC)
  Active --> Archived: versi baru dengan MP Number sama di-approve
  Archived --> [*]
```

- Hanya satu MP Active per tipe pesawat; versi Archived menampilkan banner dengan tautan ke versi aktif.
- Draft bisa diubah; Active tidak bisa diedit (revisi lewat Copy MP).

## Status forecast per baris

```mermaid
stateDiagram-v2
  direction LR
  Safe --> Approaching: masuk ambang notifikasi (10% batas berlaku)
  Approaching --> Due: mencapai batas
  Due --> Overdue: melewati batas
  Approaching --> Safe: last done baru / STE disetujui
  Due --> Safe: last done baru
  Overdue --> Safe: last done baru
```

Nama status baku: Safe, Approaching, Due, Overdue. Label lain di desain (OK, Due Soon) harus diganti.

## Siklus last done

1. Task masuk WO (Modul 3) sebagai salinan master dengan referensi revisi MP asal (usulan 129).
2. Task card di-close di WO dengan tanggal, TSN, CSN (Modul 3).
3. Last done task MP diperbarui otomatis (58); status AD/EO diperbarui di Modul 1.
4. Forecast menghitung due berikutnya dari batas yang berlaku (interval setelah pelaksanaan pertama).

Task card yang dihapus, dibatalkan, atau dipindah di WO **tidak** mengubah Check Pack maupun last done (usulan 130).
