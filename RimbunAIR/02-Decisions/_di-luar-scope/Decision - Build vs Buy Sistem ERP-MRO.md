---
tanggal: 2026-07-27
tipe: decision
status: tertutup de facto — alasan belum ditulis
---

# Decision: Build vs Buy Sistem ERP-MRO

Terkait meeting: [[2026-07-27 Kickoff Nodewave x Rimbun Air]]

> ⚠️ **Sudah ditetapkan kontrak.** Kickoff 27 Jul 2026 menetapkan **build custom oleh Nodewave**. Yang tersisa bukan memilih, tapi **menuliskan alasan dan trade-off** yang diterima — supaya bisa dijawab kalau ditanya lagi setahun lagi. Lihat K5 di [[Rekonsiliasi Scope - Riset vs Kontrak]].

## Masalah / konteks

Riset merekomendasikan **membeli** platform modular kelas kecil-menengah (ENVISION, AIRPACK, Ramco, Veryon), tetapi arah project saat ini adalah **develop sendiri** ERP untuk Rimbun Air. Ini keputusan paling hulu yang menentukan segalanya: scope development, timeline, dan risiko kepatuhan regulasi. Perlu diputuskan eksplisit dan didokumentasikan alasannya, karena akan ditanya lagi ("kenapa dulu tidak beli jadi?").

Referensi: [[Benchmark Vendor ERP-MRO Aviasi]]

## Opsi yang dipertimbangkan

1. **Build penuh (custom)** — kontrol penuh, fit dengan konteks perintis (offline-first, subsidi, self-handling); minus: beban kepatuhan CASR/audit DKPPU ditanggung sendiri, waktu lama, risiko reinventing modul MRO yang sangat kompleks (AD/SB, LLP, back-to-birth).
2. **Buy (vendor kecil-menengah)** — cepat live (Manta Air: 8 modul dalam 4 bulan), compliance sudah teruji; minus: biaya lisensi, fit terbatas untuk kebutuhan lokal (subsidi DJPU, bahasa, PSrE Indonesia).
3. **Hybrid** — buy untuk core MRO/technical records (area paling berat regulasinya), build untuk cargo/subsidi/POD/integrasi lokal; minus: kompleksitas integrasi dua sistem.

Kriteria evaluasi wajib dari riset (berlaku juga sebagai acuan fitur bila build): (a) mobile offline-first; (b) e-signature + audit trail imutabel; (c) modul CAMO/reliability; (d) Cargo-IMP/e-AWB + roadmap ONE Record; (e) referensi operator turboprop kecil.

## Keputusan final


## Alasan


## Siapa yang setuju / stakeholder terkait

