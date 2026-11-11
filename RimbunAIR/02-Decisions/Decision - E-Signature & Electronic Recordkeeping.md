---
tanggal: 2026-07-27
tipe: decision
status: open — perlu klarifikasi niat desain
---

# Decision: E-Signature & Electronic Recordkeeping (PSrE, eTLB, approval DKPPU)

Terkait meeting: [[2026-07-27 Kickoff Nodewave x Rimbun Air]]

> 🔴 **Ada opsi keempat yang muncul dari kontrak.** Deck kickoff menjanjikan *"sign-ready PDF"* dengan signature block untuk ditandatangani — artinya kemungkinan besar **tanda tangan tetap basah di kertas**, sistem hanya generator dokumen. Kalau itu memang niatnya, tidak masalah secara hukum, tapi konsekuensinya sistem **bukan** system of record legal untuk release dan arsip kertas jalan terus. Perlu dipastikan mana yang dipilih sebelum modul recordkeeping dirancang. Lihat K3 di [[Rekonsiliasi Scope - Riset vs Kontrak]].

## Masalah / konteks

Sign-off maintenance release secara elektronik harus sah secara hukum. Dasar hukum yang ada: UU ITE Ps.11 + PP 71/2019 Ps.59–60 — tanda tangan elektronik **tersertifikasi** via [[Glosarium#P|PSrE]] terdaftar Komdigi punya kekuatan pembuktian tertinggi; scan/tempel tanda tangan di PDF tidak setara. Sementara itu **belum ada AC/SI Indonesia yang spesifik mengesahkan [[Glosarium#E|eTLB]]** — jalur approval ke [[Glosarium#D|DKPPU]] bersifat kasuistik (analog OpSpec A025 FAA), dengan FAA AC 120-78B sebagai acuan best-practice.

Referensi: [[Regulasi & Kepatuhan CASR Indonesia]]

## Opsi yang dipertimbangkan

1. **PSrE tersertifikasi sejak awal** (pilih penyedia: PrivyID, VIDA, Peruri, dll) — kekuatan hukum tertinggi; minus: biaya per-signature/user, integrasi API, dan ketergantungan konektivitas saat signing (bagaimana offline?).
2. **E-signature internal (kriptografis, non-PSrE) dulu + paper backup untuk release** — cepat jalan; minus: kekuatan pembuktian lebih rendah, dual-run kertas lebih lama.
3. **Bertahap**: mulai paper-parallel, ajukan proposal eTLB + e-signature ke DKPPU sedini mungkin, aktifkan PSrE saat approval turun.

Sub-keputusan yang mengikuti: pilihan PSrE, arsitektur append-only/WORM untuk audit trail, mekanisme signing saat offline (mis. pre-authenticated session / sign lokal lalu anchor saat online), dan siapa yang mengawal proposal ke DKPPU.

## Keputusan final


## Alasan


## Siapa yang setuju / stakeholder terkait

