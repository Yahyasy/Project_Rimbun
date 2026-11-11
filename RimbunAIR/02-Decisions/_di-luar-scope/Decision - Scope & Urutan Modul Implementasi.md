---
tanggal: 2026-07-27
tipe: decision
status: tertutup de facto — alasan belum ditulis
---

# Decision: Scope & Urutan Modul Implementasi

Terkait meeting: [[2026-07-27 Kickoff Nodewave x Rimbun Air]]

> ⚠️ **Sudah ditetapkan kontrak.** Kickoff menetapkan **10 modul MRO**, agile per sub-modul dengan sign-off berjenjang, **go-live bulan 12**. Ini **berbeda** dari ketiga opsi di bawah — khususnya soal dual-run paralel dan urutan verifikasi baseline data. Yang perlu ditulis: trade-off apa yang diterima dengan tidak mengikuti rekomendasi riset. Lihat K4 & K5 di [[Rekonsiliasi Scope - Riset vs Kontrak]].

## Masalah / konteks

ERP ini mencakup dua rantai (kargo + MRO) dengan ±12 modul potensial. Big Bang terbukti berisiko tinggi di aviation MRO. Riset merekomendasikan urutan bertahap dan dual-run paralel dengan paper. Perlu diputuskan modul mana yang jadi MVP, urutan rilis, dan benchmark keluar tiap tahap.

Referensi: [[Interval, Due Date & Forecasting Maintenance]], [[Benchmark Vendor ERP-MRO Aviasi]]

## Opsi yang dipertimbangkan

1. **Mengikuti rekomendasi riset (MRO-first)**: Tahap 0 (bulan 0–3) pemetaan AS-IS + pembersihan baseline data (100% part serialized punya release cert & jam terverifikasi) → Tahap 1 technical records + materials + line maintenance → dual-run ≥1 siklus check → Tahap 2 cargo/POD → Tahap 3 reliability & prediktif. Benchmark go-live: rekonsiliasi stok >98%, nol duplikasi part master, mismatch jam ops↔maintenance = 0.
2. **Cargo-first**: mulai dari booking→AWB→W&B→POD + pelaporan subsidi (nilai bisnis/cash flow paling cepat terasa, risiko regulasi lebih rendah daripada maintenance records) → MRO menyusul.
3. **Dua jalur paralel tipis**: flight leg + AWB sebagai tulang punggung dulu (single source of truth), lalu lebar ke dua arah.

## Keputusan final


## Alasan


## Siapa yang setuju / stakeholder terkait

