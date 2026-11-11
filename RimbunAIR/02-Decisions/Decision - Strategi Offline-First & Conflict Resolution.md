---
tanggal: 2026-07-27
tipe: decision
status: kemungkinan gugur — premis dasarnya salah
---

# Decision: Strategi Offline-First & Conflict Resolution

Terkait meeting: [[2026-07-27 Kickoff Nodewave x Rimbun Air]]

> 🟢 **Kemungkinan besar decision ini gugur.** Premis dasarnya — Rimbun Air operator perintis Papua dengan konektivitas minim — ternyata **salah dengar**. Lokasi kerja yang sebenarnya disebut: Cengkareng, Halim, Bandung. Kalau konfirmasi lokasi membenarkan ini, decision ini tidak perlu diambil sama sekali dan bisa diarsipkan.
>
> Catatan lama: Deck kickoff hanya menjanjikan *"web application with mobile access"* — kata offline/sync tidak muncul sama sekali. Jadi sebelum memilih strategi conflict resolution di bawah, harus dipastikan dulu **apakah offline-first memang masuk scope**, dan itu ditentukan oleh data konektivitas riil per stasiun (butir D3 di [[Checklist Data dari Rimbun Air]]), bukan asumsi. Lihat K2 di [[Rekonsiliasi Scope - Riset vs Kontrak]].

## Masalah / konteks

Bandara perintis nyaris tanpa konektivitas. Untuk **modul saya**, yang terdampak adalah **tech log ([[Glosarium#A|AFML]])** dan **eksekusi work order di luar pangkalan** — keduanya harus tetap bisa mencatat tanpa sinyal.

Dua konsekuensi yang spesifik ke modul saya:
- **[[Glosarium#C|CASR]] 91.25 mewajibkan journey log berada di dalam pesawat.** Kalau tech log dielektronikkan, tablet-nya jadi bagian kelengkapan pesawat secara hukum — tidak boleh mati total tanpa prosedur cadangan.
- **Entri jam terbang tertunda.** Riset menyebut salinan fisik bisa tertahan 3–7 hari di stasiun perintis, dan jam sering didiktekan lewat radio dulu. Perlu status "draft / menunggu rekonsiliasi" supaya perhitungan [[Glosarium#L|LD/ND]] bisa jalan sambil menunggu dokumen asli.

Failure mode paling berbahaya di area saya bukan konflik stok, melainkan **dua sumber angka jam yang berbeda** — lihat [[Tech Log, Defect & Reliability Analysis]].

Referensi: [[Tech Log, Defect & Reliability Analysis]]

## Opsi yang dipertimbangkan

1. **Last-write-wins per field + audit log** — sederhana; minus: bisa menimpa data yang benar tanpa disadari.
2. **Timestamp hierarchy yang memprioritaskan lapangan** (field ops menang atas kantor pusat untuk transaksi fisik) — sesuai realita bahwa kejadian fisik di lapangan adalah fakta; minus: butuh aturan per jenis transaksi.
3. **Merge dengan flag manual** — konflik ditandai dan diselesaikan manusia; paling aman untuk record airworthiness; minus: butuh SDM yang mengawal antrean konflik.
4. Kombinasi per jenis data (mis. opsi 2 untuk inventory movement, opsi 3 untuk record airworthiness).

Perlu diputuskan juga: teknologi sync (CRDT / event-sourcing / queue-based), batas durasi offline yang didukung, dan perilaku reservasi stok saat status remote tidak diketahui.

## Keputusan final


## Alasan


## Siapa yang setuju / stakeholder terkait

