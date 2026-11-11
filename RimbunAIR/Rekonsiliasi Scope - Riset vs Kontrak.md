---
tanggal: 2026-07-28
tipe: knowledge
tags: [scope, risiko, kontrak]
status: 1 terbuka · 1 turun · 1 hampir tutup · 2 selesai
---

# Rekonsiliasi Scope — Riset vs Kontrak

**Audiens:** 🔴 Internal saja — berisi konflik antara riset dan kontrak. Jangan dibagikan ke Rimbun Air.

> **Isi note ini:** catatan lima titik di mana asumsi riset awal tidak cocok dengan komitmen kontrak, beserta bagaimana masing-masing berakhir.
> Untuk daftar risiko yang aktif dipantau, buka [[Overview]]. Note ini penjelasan latarnya.

| # | Konflik | Status |
|---|---|---|
| **K4** | Migrasi data dijadwalkan setelah go-live | 🔴 **Terbuka** — satu-satunya yang masih hidup |
| K2 | Offline-first tidak disebut di proposal | 🟢 Hampir tutup — premisnya runtuh |
| K3 | "Sign-ready PDF" vs e-sign [[Glosarium#P\|PSrE]] | 🟠 Turun — bukan gap |
| K1 | Rantai kargo tidak ada di 10 modul | ✅ Selesai |
| K5 | Dua decision sudah tertutup kontrak | ✅ Selesai |

---

## 🔴 K4 — Migrasi data dijadwalkan setelah go-live

**Kata riset.** Dirty data adalah penyebab utama kegagalan implementasi MRO. Mitigasi wajib: baseline terverifikasi **sebelum** go-live, plus dual-run paralel minimal satu siklus check.

**Kata kontrak.** Go-live bulan 12, lalu *"Warranty & Data Migration (Month 12–18)"* — migrasi **enam bulan setelah** go-live. Scope juga **mengecualikan** migrasi dari Excel, Word, dan kertas.

**Kata lapangan.** MSS tidak dipakai PPC planning, tapi **dipakai penuh untuk AFML** — databasenya berisi flight hours, cycle, discrepancy, dan component replacement, serta bisa diekspor. Yang benar-benar berjalan: [[Glosarium#L|LD/ND]] di spreadsheet, dokumen kerja di kertas.

Konsekuensinya: **hampir seluruh data awal jatuh di sisi yang tidak dimigrasikan.** Bukan sebagian — hampir semuanya. Dan tanpa LD/ND, PPC tidak bisa memproduksi satu dokumen pun di hari pertama.

**Yang perlu diputuskan.** Siapa mengisi data awal, kapan, dan apakah masuk kontrak atau jadi beban Rimbun Air. Dengan PPC hanya satu orang, "diinput manual oleh tim klien" bukan jawaban realistis.

---

## 🟢 K2 — Offline-first

Argumen offline-first seluruhnya bersandar pada premis "bandara perintis nyaris tanpa konektivitas". Premis itu **tidak berlaku** — Rimbun Air operator kargo jet dengan basis di Jakarta dan Bandung, bukan operator turboprop di landasan terpencil.

Kontrak juga tidak pernah menjanjikan offline. Jadi kemungkinan besar ini bukan konflik sama sekali, dan itu menghemat effort besar.

**Sisa langkah:** konfirmasi daftar lokasi operasi, lalu tutup dan arsipkan [[Decision - Strategi Offline-First & Conflict Resolution]].

## 🟠 K3 — E-signature

Riset menuntut e-signature tersertifikasi PSrE; kontrak menjanjikan "sign-ready PDF". Lapangan mengonfirmasi **tanda tangan masih basah di kertas** — jadi pendekatan kontrak sejalan dengan praktik berjalan, bukan gap.

Yang tersisa cuma keputusan arah jangka panjang di [[Decision - E-Signature & Electronic Recordkeeping]].

## ✅ K1 — Rantai kargo

Kontrak mencakup 10 modul MRO; scope saya 3 di antaranya. Kargo tidak ada di mana pun. Note terkait sudah dipindahkan ke `_di-luar-scope/`.

## ✅ K5 — Decision yang tertutup kontrak

Build vs Buy dan Scope & Urutan Modul sudah ditetapkan kickoff. Keduanya diarsipkan ke `02-Decisions/_di-luar-scope/`, digantikan [[Scope]] sebagai acuan kerja harian.

Tiga decision tersisa aktif — semuanya menyentuh modul saya.

Terkait: [[Overview]] · [[Riwayat Koreksi]]
