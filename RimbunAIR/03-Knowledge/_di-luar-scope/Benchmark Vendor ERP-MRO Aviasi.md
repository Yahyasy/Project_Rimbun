---
tanggal: 2026-07-27
tipe: knowledge
tags: [vendor, benchmark, mro-software]
---

# Benchmark Vendor ERP-MRO Aviasi

Sumber: [[Sumber Riset A - Proses Bisnis ERP MRO Kargo Perintis]] · [[ERP_MRO Kargo Perintis Indonesia]]

## Ringkasan

### Kelas enterprise (dinilai overkill untuk operator perintis)

- **AMOS** (Swiss-AS) — standar industri, offline-first kuat (AMOSmobile/STORES, AMOSeTL), tapi kompleks & mahal.
- **TRAX** — enterprise, fleet besar; mode offline butuh modifikasi ekstensif untuk kondisi pelosok.
- **IFS Cloud/Maintenix** — skalabel, berat.

### Kelas kecil-menengah (paling relevan)

| Solusi | Vendor | Catatan |
|---|---|---|
| **ENVISION** | Rusada | Terbukti di operator turboprop kecil: Air Chathams (ATR 72), Manta Air (ATR72-600 + Twin Otter, live 8 modul dalam 4 bulan), Texel Air (kargo) |
| **AIRPACK** | ADSoftware (kini Vellox) | 50+ klien kecil; training ~5 hari; harga kompetitif; modul AIRTIME/AIRSTOCK/dll |
| **Ramco Aviation** | Ramco | MRO+ERP+HR/payroll terpadu, cloud-native, mobile offline (Anywhere Apps / Fly Anywhere EFB) |
| **Veryon** (Tracking+/Traxxall) | Veryon | User-friendly, compliance & records, regional/GA/heli |

Pelengkap: Ultramain (ELB), CAMP/Flightdocs (tracking), Comply365/Web Manuals (manual authoring), AVIATAR (predictive, klaim −30% unscheduled removal).

### Pelajaran kegagalan implementasi

- Penyebab utama gagal: rush rollout, **dirty data**, scope accounting ≠ operasional, tidak ada internal owner, dokumentasi tidak lengkap.
- Big Bang & phased rollout standar sering tidak cocok untuk aviation MRO — perlu feedback berkelanjutan + adaptasi regulasi.
- **Southwest Des 2022**: legacy crew-scheduling → 16.700+ pembatalan, denda DOT US$140 juta, rugi >US$1 miliar. Legacy tak di-upgrade = risiko eksistensial.
- Mitigasi wajib: **dual-run paralel** (sistem baru vs paper/legacy minimal 1 siklus check), baseline data terverifikasi sebelum go-live, internal owner dari maintenance+CAMO.

## Caveat

- **Diskrepansi antar riset**: Riset A menyebut ENVISION milik **Rusada**; Riset B menyebut "ENVISION dari Veryon". Yang benar: ENVISION adalah produk **Rusada** — Veryon adalah vendor terpisah (Tracking+/Traxxall). Riset B keliru di titik ini.
- Detail harga/fitur berasal dari materi pemasaran & direktori pihak ketiga — validasi via RFP/demo.
- IGOM/AHM/DGR & ATA Spec 2000 berbayar; edisi presisi harus dibeli dari IATA/ATA.

## Kenapa relevan buat project ini

Kalau project ini **build sendiri**, tabel ini adalah benchmark fitur kompetitor + daftar pelajaran kegagalan yang harus dihindari. Kalau ada opsi **buy/hybrid**, ini shortlist-nya. Lihat [[Decision - Build vs Buy Sistem ERP-MRO]].
