---
tanggal: 2026-07-27
tipe: decision
status: ditunda — di luar scope kontrak
---

# Decision: Standar Cargo Messaging (Cargo-IMP vs ONE Record)

Terkait meeting: [[2026-07-27 Kickoff Nodewave x Rimbun Air]]

> ⏸️ **Ditunda.** Rantai kargo tidak ada di 10 modul yang dikontrakkan, jadi keputusan ini belum perlu diambil sekarang. Simpan sebagai bahan siap-pakai kalau kargo masuk fase berikutnya. Lihat K1 di [[Rekonsiliasi Scope - Riset vs Kontrak]].

## Masalah / konteks

Cargo-IMP (FWB/FHL/FSU) edisi 34 adalah edisi **final** — pengembangan berpindah ke Cargo-XML dan **IATA ONE Record**, yang di-endorse sebagai preferred standard efektif 1 Jan 2026. Sistem baru yang dibangun tahun ini harus memutuskan mendukung format mana, karena mempengaruhi skema data AWB dan integrasi dengan pihak ketiga (agen, GHA, bandara). Catatan: skala interoperabilitas Rimbun Air mungkin kecil (banyak self-handling di rute perintis), jadi bisa jadi kebutuhan EDI eksternal minim — ini perlu divalidasi dulu.

Referensi: [[Proses Bisnis Kargo Perintis End-to-End]]

## Opsi yang dipertimbangkan

1. **ONE Record native** (data model JSON-LD/API) — future-proof, cocok untuk sistem greenfield 2026; minus: ekosistem lokal (agen/bandara perintis) mungkin belum siap.
2. **Cargo-IMP dulu** — kompatibel dengan sistem lama mitra; minus: standar sudah dibekukan, technical debt sejak hari pertama.
3. **Internal model sendiri + adapter** — simpan data AWB dalam model internal yang bisa diekspor ke Cargo-IMP maupun ONE Record sesuai kebutuhan mitra; minus: effort adapter ganda.
4. **Tanpa EDI dulu** — bila validasi menunjukkan tidak ada mitra yang menuntut pertukaran pesan, cukup dokumen cetak/PDF + siapkan model data yang ONE Record-compatible.

## Keputusan final


## Alasan


## Siapa yang setuju / stakeholder terkait

