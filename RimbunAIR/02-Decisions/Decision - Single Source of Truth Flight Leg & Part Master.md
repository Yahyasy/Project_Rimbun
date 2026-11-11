---
tanggal: 2026-07-27
tipe: decision
status: open — paling siap diputuskan
---

# Decision: Single Source of Truth Flight Leg & Part Master

Terkait meeting: [[2026-07-27 Kickoff Nodewave x Rimbun Air]]

> 🔴 **Open, dan ini yang paling siap diputuskan** dari enam decision — tidak terbengkalai oleh konflik scope mana pun. Modul 04 "Flight Ops Interface" jelas ada di kontrak, jadi pertanyaan siapa sumber otoritatif flight leg tetap relevan apa pun hasil rekonsiliasi. Butuh input: butir A2 (process owner ops & materials) dan D4 (inventori awal) di [[Checklist Data dari Rimbun Air]].

## Masalah / konteks

Dua data ini adalah tulang punggung integrasi seluruh sistem:

- **Flight leg (jam & cycle)** mengalir dari ops ke maintenance — mismatch = interval LLP/AD terlewat, pesawat berpotensi ilegal terbang atau di-ground [[Glosarium#D|DGCA]].
- **Part master** — nomor part sama dientri berbeda = stok pecah, rekonsiliasi gagal.

Perlu diputuskan siapa/modul apa yang menjadi sumber otoritatif, siapa yang boleh entri/koreksi, dan bagaimana governance-nya (terutama saat entri terjadi offline di lapangan).

Referensi: [[Interval, Due Date & Forecasting Maintenance]], [[Tech Log, Defect & Reliability Analysis]]

## Opsi yang dipertimbangkan

1. **Flight leg**: sumber tunggal = ATL/eTLB yang di-sign PIC (fakta operasional), modul lain read-only + rekonsiliasi otomatis vs data dispatch; koreksi hanya via entri koreksi ber-audit-trail.
2. **Flight leg**: sumber = modul flight ops (dispatch), [[Glosarium#E|eTLB]] memverifikasi — lebih cepat tersedia, tapi bukan fakta aktual.
3. **Part master**: tim/role tunggal sebagai data steward + validasi duplikat otomatis (normalisasi PN, interchangeability check) saat entri; lapangan tidak boleh membuat PN baru, hanya request.
4. **Part master**: entri terdesentralisasi + dedup berkala — lebih luwes, terbukti jadi failure point klasik.

## Keputusan final


## Alasan


## Siapa yang setuju / stakeholder terkait

