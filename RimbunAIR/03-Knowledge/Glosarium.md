---
tanggal: 2026-07-27
tipe: knowledge
tags: [glosarium, referensi]
---

# Glosarium ERP-MRO Kargo Perintis

**Audiens:** 🟢 Boleh ke Rimbun Air — **Boleh dibagikan ke siapa pun.** Kamus istilah, tanpa penilaian.

> **Isi note ini:** kamus istilah. Buka ini duluan tiap ketemu singkatan asing.

Sumber: dirangkum dari knowledge notes project ini. Istilah disusun alfabetis; kategori dalam kurung menandai domain: **[MRO]**, **[Regulasi]**, **[Sistem]**.

> 📌 Difokuskan ke 3 modul saya. Istilah kargo dan inventory sudah dikeluarkan — lihat `_di-luar-scope/` kalau nanti diperlukan.

Cara pakai: cari singkatan/istilah di sini dulu sebelum baca notes detail — tiap entri menaut ke note sumbernya.

## A

- **ADU (Average Daily Utilization)** **[Sistem]** — Rata-rata jam terbang harian, dasar memproyeksikan tanggal jatuh tempo. Lazim dihitung dari 90 hari terakhir. → [[Interval, Due Date & Forecasting Maintenance]]
- **AFML (Aircraft Flight & Maintenance Log)** **[MRO]** — Istilah Rimbun Air untuk tech log/ATL: dokumen hukum per penerbangan berisi waktu, fuel, defect, dan CRS. → [[Tech Log, Defect & Reliability Analysis]]
- **AFTF (Airframe Total Time)** **[Sistem]** — Akumulasi jam badan pesawat; dasar perhitungan task yang melekat di airframe, dibedakan dari TSN komponen. → [[Interval, Due Date & Forecasting Maintenance]]
- **Airborne Time** **[Sistem]** — Take-off sampai touch-down. Inilah yang dipakai untuk perhitungan interval maintenance. → [[Tech Log, Defect & Reliability Analysis]]
- **Alert Level** **[MRO]** — Ambang statistik reliability, lazimnya Mean + (2 × Standard Deviation) dari 12–24 bulan historis. Terlampaui = wajib investigasi. → [[Tech Log, Defect & Reliability Analysis]]
- **AWL (Airworthiness Limitation Item)** **[Regulasi]** — Batasan kelaikudaraan dari sertifikasi tipe; tidak boleh diberi toleransi maupun eskalasi. → [[Interval, Due Date & Forecasting Maintenance]]

- **AC (Advisory Circular)** **[Regulasi]** — Panduan non-mengikat dari otoritas penerbangan (FAA/DGCA) yang menjelaskan cara memenuhi suatu regulasi. FAA AC 120-78B jadi acuan best-practice e-signature karena Indonesia belum punya AC/SI khusus eTLB. → [[Regulasi & Kepatuhan CASR Indonesia]]
- **AD (Airworthiness Directive)** **[MRO]** — Perintah wajib dari otoritas (DGCA/FAA) untuk memperbaiki masalah keselamatan; berbeda dari SB karena sifatnya mandatori dan harus terekam permanen. Sistem harus mengunci rilis penerbangan bila AD lewat tenggat. → [[Tech Log, Defect & Reliability Analysis]]
- **AMEL (Aircraft Maintenance Engineer License)** **[Regulasi]** — Lisensi teknisi pemeliharaan pesawat di bawah CASR Part 65; renewal tiap 2 tahun + recent experience. → [[Regulasi & Kepatuhan CASR Indonesia]]
- **AMO (Approved Maintenance Organization)** **[MRO]** — Bengkel/organisasi pemeliharaan yang disetujui DGCA di bawah CASR Part 145. → [[Tech Log, Defect & Reliability Analysis]]
- **AMP/CAMP (Aircraft/Continuous Airworthiness Maintenance Program)** **[MRO]** — Program pemeliharaan pesawat yang disusun operator berbasis MPD OEM, disetujui DGCA. → [[Tech Log, Defect & Reliability Analysis]]
- **AOC (Air Operator Certificate)** **[Regulasi]** — Izin operasi maskapai; pelanggaran kepatuhan berat berisiko pencabutan AOC. → [[Regulasi & Kepatuhan CASR Indonesia]]
- **AOG (Aircraft on Ground)** **[MRO]** — Kondisi pesawat tidak bisa terbang karena kekurangan sparepart; memicu skema darurat pooling/exchange/loan. → [[Manajemen Sparepart & Supply Chain]]
- **ATA Chapter** **[Sistem]** — Kodifikasi standar internasional (mis. ATA 32 = Roda Pendarat) untuk menstandardisasi pelaporan kerusakan lintas sistem. → [[Interval, Due Date & Forecasting Maintenance]]
- **ATA Spec 2000** **[MRO]** — Standar industri untuk barcode/RFID part serialized dan pertukaran release certificate elektronik (Chapter 16). → [[Manajemen Sparepart & Supply Chain]]
- **ATL (Aircraft Technical Log)** **[MRO]** — Journey log yang wajib dibawa tiap flight (CASR 91.25); versi digitalnya adalah eTLB. → [[Tech Log, Defect & Reliability Analysis]]

## B

- **Back-to-birth** **[MRO]** — Rantai dokumentasi lengkap sebuah komponen sejak diproduksi hingga sekarang, termasuk seluruh sertifikat rilisnya. → [[Eksekusi Work Order, Kewenangan & Kalibrasi]]

- **Buy-back Inspection** **[MRO]** — Inspeksi ulang oleh RII Inspector setelah mekanik memperbaiki pekerjaan yang sebelumnya ditolak. → [[Eksekusi Work Order, Kewenangan & Kalibrasi]]
- **Block Time** **[Sistem]** — Waktu dari chocks-off sampai chocks-on, termasuk taxi. Dipakai untuk jam kerja kru — **bukan** untuk interval maintenance. → [[Tech Log, Defect & Reliability Analysis]]

- **Back-to-birth records** **[MRO]** — Rantai dokumentasi lengkap sebuah part serialized sejak diproduksi (birth record) hingga sekarang, termasuk seluruh release certificate-nya. → [[Manajemen Sparepart & Supply Chain]]

## C

- **CASS (Continuing Analysis & Surveillance System)** **[Regulasi]** — Program pengawasan keandalan independen yang wajib di CASR 121/135; mengevaluasi kecukupan program perawatan sekaligus kinerja pelaksanaannya. → [[Tech Log, Defect & Reliability Analysis]]
- **CDL (Configuration Deviation List)** **[MRO]** — Daftar panel/bagian struktur eksternal yang boleh tidak terpasang, biasanya dengan penalti performa. Pelengkap MEL. → [[Tech Log, Defect & Reliability Analysis]]
- **Company Authorization** **[Regulasi]** — Izin internal dari QA yang membatasi kewenangan mekanik; bisa lebih sempit dari lisensi negaranya. Inilah source of truth sistem, bukan lisensi DKPPU. → [[Eksekusi Work Order, Kewenangan & Kalibrasi]]
- **Check-pack** **[MRO]** — Istilah Rimbun Air untuk work package: bundel task card yang dikerjakan dalam satu periode grounded. → [[Interval, Due Date & Forecasting Maintenance]]

- **CAMO (Continuing Airworthiness Management Organization)** **[MRO]** — Fungsi/organisasi yang mengelola kelaikudaraan berkelanjutan pesawat, termasuk reliability monitoring. → [[Tech Log, Defect & Reliability Analysis]]
- **CAS (Continuing Analysis & Surveillance)** **[Regulasi]** — Kewajiban pemantauan berkelanjutan program maintenance (CASR 121.373/135.373). → [[Tech Log, Defect & Reliability Analysis]]
- **CASR (Civil Aviation Safety Regulation)** **[Regulasi]** — Regulasi keselamatan penerbangan Indonesia, harmonis dengan FAR AS (14 CFR), diterbitkan Kemenhub. → [[Regulasi & Kepatuhan CASR Indonesia]]
- **CMM (Component Maintenance Manual)** **[MRO]** — Manual acuan bengkel untuk membongkar, memeriksa, memperbaiki suatu komponen. → [[Tech Log, Defect & Reliability Analysis]]
- **CMR (Certification Maintenance Requirement)** **[MRO]** — Persyaratan pemeliharaan wajib hasil sertifikasi tipe pesawat; hanya bisa diubah dengan izin otoritas. → [[Tech Log, Defect & Reliability Analysis]]
- **CRS (Certificate of Release to Service)** **[MRO]** — Istilah umum untuk dokumen rilis kelaikan komponen setelah repair/overhaul; di Indonesia berbentuk DGCA Form 21-18. → [[Tech Log, Defect & Reliability Analysis]]
- **CSN/CSO (Cycles Since New/Overhaul)** **[MRO]** — Akumulasi **siklus** sejak baru atau sejak overhaul terakhir; satu cycle = satu take-off + landing. Pasangan TSN untuk interval berbasis cycle, dan dasar perhitungan LLP. → [[Interval, Due Date & Forecasting Maintenance]]

## D

- **Discrepancy** **[MRO]** — Keluhan pilot atas sesuatu yang tidak beres selama penerbangan, ditulis sendiri oleh pilot di **blok hitam** [[Glosarium#A|AFML]]. Wajib ditutup oleh *rectification* atau dialihkan jadi [[Glosarium#D|DMI]] sebelum pesawat terbang lagi. → [[2026-07-31 PPC Technical Record]]
- **DMI (Deferred Maintenance Item)** **[MRO]** — Catatan penundaan perbaikan hasil deferral MEL, dengan hitung mundur sesuai kategori A/B/C/D. → [[Tech Log, Defect & Reliability Analysis]]

- **DGCA (Directorate General of Civil Aviation)** **[Regulasi]** — Regulator penerbangan sipil Indonesia, c.q. DKPPU. → [[Regulasi & Kepatuhan CASR Indonesia]]
- **DGCA Form 21-18** **[Regulasi]** — Authorized Release Certificate/Airworthiness Approval Tag Indonesia; ekuivalen FAA 8130-3, EASA Form 1. Diatur SI 21-09; issuer simpan duplikat ≥2 tahun. → [[Regulasi & Kepatuhan CASR Indonesia]]
- **DKPPU (Direktorat Kelaikudaraan dan Pengoperasian Pesawat Udara)** **[Regulasi]** — Unit DGCA yang mengaudit & menyetujui kepatuhan kelaikudaraan operator. → [[Regulasi & Kepatuhan CASR Indonesia]]

## E

- **ENC (Engine Cycle)** **[MRO]** — Siklus termal mesin. Aborted take-off menambah 1 ENC meski pesawat tidak pernah terbang (0 FC). → [[Tech Log, Defect & Reliability Analysis]]
- **Equalized Maintenance** **[MRO]** — Nama lain phase check: task dari A/C/D check dipecah rata jadi paket-paket kecil supaya downtime pendek. → [[Interval, Due Date & Forecasting Maintenance]]

- **ECTM (Engine Condition Trend Monitoring)** **[MRO]** — Pemantauan prediktif kondisi mesin (khususnya PT6A) via parameter ITT, NH/NL, fuel flow, untuk mendeteksi keausan sebelum gagal. → [[Tech Log, Defect & Reliability Analysis]]
- **eTLB (Electronic Technical Logbook)** **[MRO]** — Versi digital ATL/journey log; belum ada AC/SI Indonesia spesifik yang mengesahkannya. → [[Tech Log, Defect & Reliability Analysis]], [[Decision - E-Signature & Electronic Recordkeeping]]

## F

- **FOD (Foreign Object Debris)** **[MRO]** — Benda asing tertinggal di pesawat (mis. kunci pas) yang bisa merusak turbin atau menyumbat hidrolik. Alasan utama kontrol alat ketat. → [[Eksekusi Work Order, Kewenangan & Kalibrasi]]

## G

- **GIGO (Garbage In, Garbage Out)** **[Sistem]** — Prinsip: data migrasi yang kotor/salah menghasilkan sistem yang tidak reliable; failure point #1 saat go-live. → [[Interval, Due Date & Forecasting Maintenance]]

## H

- **Hard Time (HT) / On-Condition (OC) / Condition Monitoring (CM)** **[MRO]** — Tiga klasifikasi metode pemeliharaan komponen: interval tetap, dipantau kondisinya, atau dipantau tren keandalannya. → [[Tech Log, Defect & Reliability Analysis]]

## I

- **Interval creep** **[Sistem]** — Penggelembungan interval akibat Next Due dihitung dari tanggal aktual (bukan due date asli) saat task dikerjakan dalam toleransi. Efektif mengubah AMP tanpa izin regulator. → [[Interval, Due Date & Forecasting Maintenance]]
- **ITT (Inter-Turbine Temperature)** **[MRO]** — Suhu antar-turbin, salah satu dari tiga parameter inti ECTM bersama Ng dan Wf. → [[Tech Log, Defect & Reliability Analysis]]

## L

- **LGC (Landing Gear Cycle)** **[MRO]** — Siklus roda pendaratan. Touch-and-go menambah LGC tapi belum tentu FC. → [[Tech Log, Defect & Reliability Analysis]]
- **LD/ND (Last Done / Next Due)** **[Sistem]** — Tracker induk yang mencatat kapan tiap task terakhir dikerjakan dan kapan jatuh tempo. Di Rimbun Air masih berupa spreadsheet. → [[Interval, Due Date & Forecasting Maintenance]]

- **LLP (Life-Limited Part)** **[MRO]** — Komponen dengan batas siklus kelelahan metalurgi (mis. turbine disk); wajib dihancurkan setelah limit, apapun kondisi fisiknya — sistem harus hard-stop. → [[Manajemen Sparepart & Supply Chain]]

## M

- **MTBUR (Mean Time Between Unscheduled Removal)** **[MRO]** — Rata-rata usia komponen sebelum dicabut paksa; kebalikan proporsional dari removal rate. → [[Tech Log, Defect & Reliability Analysis]]

- **MEL (Minimum Equipment List)** **[MRO]** — Daftar yang menentukan komponen mana boleh rusak sementara (deferred) dengan kategori A/B/C/D beserta batas waktu perbaikannya. → [[Tech Log, Defect & Reliability Analysis]]
- **MPD (Maintenance Planning Document)** **[MRO]** — Dokumen dari OEM berisi seluruh persyaratan MRB plus scheduled maintenance mandatori; jadi basis penyusunan AMP/CAMP. → [[Tech Log, Defect & Reliability Analysis]]
- **MRB (Maintenance Review Board) Report** **[MRO]** — Basis metodologi MSG-3 yang menjadi sumber MPD. → [[Tech Log, Defect & Reliability Analysis]]
- **MSG-3** **[MRO]** — Metodologi analisis untuk menyusun program pemeliharaan pesawat berbasis MRB. → [[Tech Log, Defect & Reliability Analysis]]

## N

- **Ng (Gas Generator Speed)** **[MRO]** — Putaran kompresor inti mesin, parameter ECTM. → [[Tech Log, Defect & Reliability Analysis]]
- **NRC (Non-Routine Card)** **[MRO]** — Dokumen untuk temuan di luar cakupan pekerjaan yang sedang dilakukan; ditautkan sebagai child record dari task card pemicunya. → [[Eksekusi Work Order, Kewenangan & Kalibrasi]]

## O

- **OOP (Out-of-Phase)** **[Sistem]** — Task dengan interval eksentrik yang tidak cocok ikut jadwal phase check; harus bisa dilacak independen. → [[Interval, Due Date & Forecasting Maintenance]]
- **OpSpecs (Operations Specifications)** **[Regulasi]** — Lampiran sertifikat operator berisi kewenangan spesifik dari otoritas, mis. izin one-time extension deferral atau pemakaian record elektronik. → [[Tech Log, Defect & Reliability Analysis]]

## P

- **Placard INOP** **[MRO]** — Stiker fisik di atas instrumen rusak yang di-defer. Nomor kontrolnya wajib dicatat sebagai bukti tanda fisik terpasang. → [[Tech Log, Defect & Reliability Analysis]]

- **PIREP (Pilot Report)** **[MRO]** — Laporan anomali dari pilot setelah penerbangan, masuk ke ATL/eTLB. → [[Tech Log, Defect & Reliability Analysis]]
- **PSrE (Penyelenggara Sertifikasi Elektronik)** **[Regulasi]** — Penyedia tanda tangan elektronik tersertifikasi terdaftar Komdigi; syarat kekuatan hukum tertinggi menurut PP 71/2019. → [[Regulasi & Kepatuhan CASR Indonesia]], [[Decision - E-Signature & Electronic Recordkeeping]]

## Q

- **Quality Escape** **[MRO]** — Kebocoran mutu, mis. alat kedaluwarsa kalibrasi terlanjur dipakai merilis pekerjaan. Menuntut kemampuan reverse trace di sistem. → [[Eksekusi Work Order, Kewenangan & Kalibrasi]]

## R

- **Ram check / ramp inspection** **[Regulasi]** — Inspeksi mendadak oleh DKPPU di bandara mana pun. Temuannya masuk ke portal milik regulator dan wajib dijawab operator. → [[2026-07-30 Staff Inspector Maintenance]]
- **Rectification** **[MRO]** — Jawaban engineer atas *discrepancy* pilot: apa yang diperiksa, ditemukan, dan dikerjakan. Ditulis di **blok putih** AFML oleh engineer berlisensi. Satu discrepancy = satu rectification. → [[2026-07-31 PPC Technical Record]]
- **Retention** **[Regulasi]** — Berapa lama sebuah record wajib disimpan. Aturannya berbeda per jenis record. → [[Regulasi & Kepatuhan CASR Indonesia]]

- **Recent Experience Requirement** **[Regulasi]** — Syarat agar lisensi tetap aktif: melakukan/mengawasi pemeliharaan minimal 6 bulan dalam 24 bulan terakhir. → [[Eksekusi Work Order, Kewenangan & Kalibrasi]]
- **Repetitive Defect** **[MRO]** — Laporan serupa (ATA chapter & seksi sama) pada tail number sama sebanyak 3 kali dalam 15–30 hari. Gejala root cause meleset. → [[Tech Log, Defect & Reliability Analysis]]
- **RII (Required Inspection Item)** **[Regulasi]** — Pekerjaan kritis yang wajib inspeksi ganda; yang mengerjakan dilarang menginspeksi pekerjaannya sendiri. → [[Eksekusi Work Order, Kewenangan & Kalibrasi]]

- **Release Certificate** **[Regulasi]** — Lihat **DGCA Form 21-18**.
- **Reliability monitoring** **[MRO]** — Pemantauan tren kegagalan komponen/sistem untuk deteksi dini, wajib ada bila program berbasis MSG-3. → [[Tech Log, Defect & Reliability Analysis]]
- **Rotable / Repairable / Consumable / Expendable** **[MRO]** — Empat kelas material dengan perlakuan tracking berbeda: rotable dilacak per serial number seumur hidup, consumable per batch dengan shelf life, expendable dibuang setelah pakai. → [[Manajemen Sparepart & Supply Chain]]

## S

- **Stamp** **[MRO]** — Cap pribadi bernomor milik engineer atau inspektor. Mengikat secara hukum, setara tanda tangan. → [[2026-07-30 Staff Inspector Maintenance]]
- **Superseded** **[Regulasi]** — Status dokumen yang sudah digantikan versi lebih baru. Sering jadi patokan batas retensi. → [[Regulasi & Kepatuhan CASR Indonesia]]

- **Scope of Authority** **[Regulasi]** — Irisan antara lisensi DKPPU dan Company Authorization; inilah batas sebenarnya kewenangan seorang mekanik. → [[Eksekusi Work Order, Kewenangan & Kalibrasi]]
- **SUP (Suspected Unapproved Parts)** **[MRO]** — Komponen yang diduga palsu atau tanpa dokumen sah; sasaran utama receiving inspection. → [[Eksekusi Work Order, Kewenangan & Kalibrasi]]

- **SB (Service Bulletin)** **[MRO]** — Rekomendasi perbaikan dari OEM; tidak wajib kecuali diangkat menjadi AD oleh otoritas. → [[Tech Log, Defect & Reliability Analysis]]
- **SDR (Service Difficulty Report)** **[Regulasi]** — Pelaporan kesulitan servis ke otoritas (CASR 91.423). → [[Regulasi & Kepatuhan CASR Indonesia]]
- **SI (Staff Instruction)** **[Regulasi]** — Panduan teknis internal DGCA untuk pelaksanaan regulasi (mis. SI 21-09 untuk Form 21-18). → [[Regulasi & Kepatuhan CASR Indonesia]]

## T

- **TSN / TSO (Time Since New / Since Overhaul)** **[MRO]** — Akumulasi **jam terbang** sejak baru atau sejak overhaul terakhir. Berlaku dua tingkat: pesawat punya TSN sendiri, tiap komponen juga. Dipakai sebagai satuan Last Done dan Next Due di [[Glosarium#L|LD/ND]] — jadi *remaining* = Next Due − TSN sekarang. → [[Interval, Due Date & Forecasting Maintenance]]

- **Terminating Action** **[MRO]** — Modifikasi yang mengakhiri kewajiban recurring sebuah AD. Sistem butuh pembatalan relasional: selesai task terminating → hentikan penjadwalan task recurring. → [[Interval, Due Date & Forecasting Maintenance]]
- **TSI (Time Since Installation)** **[Sistem]** — Jam sejak komponen dipasang di pesawat saat ini, dibedakan dari TSN yang menghitung sejak baru. → [[Tech Log, Defect & Reliability Analysis]]

- **Task Card** **[MRO]** — Instruksi kerja spesifik dalam Work Order, mengacu ATA chapter dan sumber MPD/MRB. → [[Interval, Due Date & Forecasting Maintenance]]

## U

- **Unserviceable (US) tag** **[MRO]** — Label merah pada komponen yang dilepas dari pesawat, berisi PN/SN/jam/deskripsi kerusakan. → [[Tech Log, Defect & Reliability Analysis]]

## W

- **WCF (Whichever Comes First)** **[Sistem]** — Aturan saat satu task punya beberapa interval sekaligus: yang tercapai duluan yang berlaku. → [[Interval, Due Date & Forecasting Maintenance]]
- **Wf (Fuel Flow)** **[MRO]** — Laju aliran bahan bakar, parameter ECTM. → [[Tech Log, Defect & Reliability Analysis]]

- **WO (Work Order)** **[MRO]** — Dokumen perintah kerja pemeliharaan, berisi Task Card dan rekaman removal/install komponen. → [[Interval, Due Date & Forecasting Maintenance]]
- **WORM (Write Once, Read Many)** **[Sistem]** — Prinsip penyimpanan append-only untuk audit trail yang tidak bisa diubah/dihapus. → [[Regulasi & Kepatuhan CASR Indonesia]]

## Kenapa relevan buat project ini

Istilah-istilah ini akan muncul berulang di nama tabel, field, dan validasi bisnis saat development. Glosarium ini jadi rujukan cepat supaya penamaan skema database dan diskusi dengan stakeholder (CAMO, ops, finance) konsisten dengan istilah industri yang sudah baku.
