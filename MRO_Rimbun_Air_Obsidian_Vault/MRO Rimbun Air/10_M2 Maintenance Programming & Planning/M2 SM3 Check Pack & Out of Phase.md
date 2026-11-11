---
tipe: submodul
modul: M2
diperbarui: 2026-11-11
sumber:
  - claude/Decision_Log_Modul2_9Nov.md
  - claude/Review_Desain_Modul2_Setelah_Revisi_8Nov.md
tags: [m2]
aliases: [Check Pack, Work Package, Out of Phase]
---
# M2 SM3 Check Pack & Out of Phase

Check Pack adalah **wadah bebas** berisi task, tanpa status dan tanpa check type. Urusan WO keluar dari Modul 2: Check Pack ditarik ke WO di form WO Modul 3.

## Check Pack List, Detail, Form

Layar 21.1 List, 22.1 Detail (tab Task List dan Tasks in Other Pack), 23.1 Form Buat/Ubah.

| Aturan | Status |
|---|---|
| WO yang terkait Check Pack dihapus dari list dan header detail | Final (69) |
| Nomor Check Pack dari master format nomor, terbentuk saat simpan | Final (70) |
| Threshold/interval tampil di list; di form threshold opsional, interval wajib | Final (71); diisi manual Menunggu (115) |
| Double pack baru terjadi setelah Check Pack dibuat; form hanya menampilkan keterangan netral "Juga terdaftar di" | Final (72) |
| Task di pack lain **bukan konflik**: kolom Keterangan dengan badge netral, menampung beberapa nomor Check Pack | Final (73, 76) |
| Sumber task: MP, EO, dan ad-hoc (Non-routine) dengan badge dan filter Sumber | Final (74); definisi sumber ad-hoc Menunggu (98) |
| Kolom WCF terdekat diganti threshold/interval; filter dan urutan berdasarkan nilai interval | Final (75) |
| Effectivity pesawat pada Check Pack; task yang ditawarkan tersaring effectivity | Final (77); satu atau beberapa pesawat Menunggu (116) |
| Mode ubah mengunci task yang sudah ada; popup ringkasan | Final (desain) |
| Ada bagian task dari Rekomendasi WCF | Final (desain) |
| Detail Check Pack tidak menampilkan WO yang memakainya | Usulan (124) |

**Perbaikan desain 8 Nov:** daftar task tampil sebelum effectivity dipilih; filter ATA memakai ikon kalender; nomor read-only bertanda wajib; sumber task yang sama berbeda antar frame; empty state masih menyebut "untuk Work Order".

## Out of Phase Task List

Layar 24.1. Kolom ATA 4 digit, interval terkecil, sumber klasifikasi **Otomatis/Manual**, WCF Due; popup Revert to Automatic; aksi Tarik ke Work Order.

| Aturan | Status |
|---|---|
| Out of Phase Task tidak berubah dari rancangan; bisa ditandai manual dan dikembalikan ke otomatis | Final |
| Definisi deteksi otomatis | Menunggu (117). Desain mengaitkan ke Check Type Master ("interval < check master"), padahal Check Type hanya referensi; usulan: task yang tidak masuk Check Pack mana pun |
| Filter tipe pesawat | Belum ada |

## Sidebar page Check Pack

Masih versi lama (memuat "Approved Maintenance…", submodul Task Card, dan Work Order Check Pack) dengan gaya ikon berbeda. **Harus disamakan** dengan sidebar page Maintenance Program sebelum presentasi.
