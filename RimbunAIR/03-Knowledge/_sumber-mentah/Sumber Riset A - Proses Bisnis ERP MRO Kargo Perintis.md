# Riset Mendalam: Proses Bisnis End-to-End Operator Kargo Perintis Indonesia & Sistem ERP/MRO Pendukung

## TL;DR
- Operator kargo perintis (ATR 42/72, Cessna Caravan, Twin Otter, Dash-8) menjalankan **dua rantai proses inti** yang wajib terjahit dalam satu sistem: rantai kargo (booking→AWB→W&B→loading→dispatch/flight following→unloading→POD) mengikuti standar IATA (e-AWB, Cargo-IMP FWB/FHL/FSU, IGOM/AHM), dan rantai continuing airworthiness/MRO (post-flight→defect→work order→removal→repair→release cert **DGCA Form 21-18**→serviceable stock→reinstal) yang diatur CASR Part 43/65/91/121/135/145.
- Untuk operator kecil-menengah, solusi paling realistis adalah platform MRO/CAMO **modular, cloud-capable, dengan mobile offline-first** (Rusada ENVISION, ADSoftware AIRPACK, Ramco, Veryon) — **bukan** suite enterprise berat (AMOS, TRAX, IFS) — karena keterbatasan SDM engineer bersertifikat dan konektivitas di bandara Papua.
- Risiko implementasi terbesar bukan teknologi melainkan **data** (initial load kotor, mismatch flight hours ops↔maintenance, duplikasi part master) dan **kepatuhan** (audit trail imutabel, e-signature tersertifikasi sesuai UU ITE/PP 71/2019, retensi record); mitigasi wajib: dual-run paralel, baseline konfigurasi terverifikasi, dan desain offline-sync dengan conflict resolution.

## Key Findings

1. **Dua rantai, satu tulang punggung data.** Titik integrasi kritis adalah **flight leg** (jam & cycle) yang mengalir dari operasi ke maintenance, dan **AWB/manifest** yang mengalir dari cargo acceptance ke load control. Registrasi pesawat (PK-xxx), part number/serial number, dan ATA chapter adalah kunci penghubung lintas modul.

2. **Regulasi Indonesia meniru FAR AS.** CASR Part 121/135 Subpart L (121.361–121.380 / 135.361–135.443) mengatur maintenance program, CAMP, Continuing Analysis & Surveillance, dan maintenance recording. CASR Part 43 mengatur siapa boleh kerja & sign-off serta isi record; CASR Part 145 mengatur AMO; CASR Part 65 mengatur lisensi AMEL. Retensi record: 1 tahun/sampai superseded (135.439/121.380/91.417), overhaul sampai superseded, dan **90 hari setelah unit ditarik permanen (43.12(c) — spesifik Indonesia)**.

3. **Release certificate Indonesia = DGCA Form 21-18** (Authorized Release Certificate/Airworthiness Approval Tag), ekuivalen FAA 8130-3 / EASA Form 1, diatur Staff Instruction **SI 21-09**; penerbit menyimpan duplikat minimal 2 tahun.

4. **e-Signature & eTLB.** Belum ditemukan AC/SI Indonesia yang spesifik mengesahkan eTLB; desain sistem harus bersandar pada **UU ITE (Pasal 11) + PP 71/2019** tanda tangan elektronik tersertifikasi (PSrE), sambil menjadikan FAA AC 120-78B sebagai pembanding best-practice untuk audit trail & imutabilitas.

5. **Vendor.** AMOS/TRAX/IFS = enterprise, mahal, kompleks; ENVISION, AIRPACK, Ramco, Veryon lebih cocok untuk fleet kecil turboprop. ENVISION khususnya sudah terbukti pada operator turboprop regional kecil: **Air Chathams** (NZ, fleet 15+ termasuk ATR 72 eks Air NZ), **Manta Air** (Maldives, ATR72-600 + DHC-6 Twin Otter, "deployed 8 of ENVISION's modules in just four months"), dan **Texel Air** (kargo Bahrain, Boeing 737 freighter).

6. **Konteks perintis Papua nyata & keras.** Program Jembatan Udara melayani 22 Koordinator Wilayah dengan **46 rute kargo perintis** (plus 266 rute penumpang dan 1 rute subsidi kargo, per KP 206/207 Tahun 2024); kendala utama: SDM berkualifikasi khusus terbatas, cuaca, keamanan (penembakan pesawat), dan infrastruktur bandara minim — menuntut aplikasi offline-first.

## Details

### 1. RANTAI PROSES OPERASIONAL (KARGO)

**Diagram alur:**
```
[Shipper/Agen] → BOOKING (kapasitas, rute, tanggal)
      │  aktor: sales/reservasi cargo; sistem: cargo booking module
      ▼
PENERBITAN AWB (Air Waybill)
      │  dokumen: Master AWB (+ House AWB bila konsolidasi)
      │  standar: IATA e-AWB; pesan Cargo-IMP FWB/16 (data AWB),
      │           FHL/4 (consolidation list), FZB (house waybill data)
      │  aktor: cargo acceptance officer
      ▼
ACCEPTANCE + SECURITY SCREENING + DGR CHECK
      │  cek: dangerous goods (IATA DGR), e-CSD (consignment security declaration)
      │  status EDI: FSU-RCS (received from shipper) → carrier liable
      ▼
PENIMBANGAN & WEIGHT-AND-BALANCE
      │  aktor: load control officer; dokumen: loadsheet
      │  standar: IATA AHM (load control), IGOM Ch.5
      ▼
LOADING / ULD build-up (turboprop kecil umumnya bulk/loose, bukan ULD)
      │  aktor: ramp/ground handling; standar: IGOM Ch.3 & Ch.4; AHM
      ▼
FLIGHT DISPATCH & FLIGHT FOLLOWING
      │  dokumen: dispatch release, loadsheet final, NOTOC (bila DG)
      │  aktor: FOO/dispatcher, PIC; keputusan: go/no-go (cuaca, W&B, MEL)
      ▼
LANDING BANDARA TUJUAN → GROUND HANDLING & UNLOADING
      │  status EDI: FSU-FOH (freight on hand), FSU-DLV (delivered)
      ▼
PROOF OF DELIVERY (POD)
      │  dokumen: delivery receipt/signature; sistem: track & trace
```

**Standar & catatan:**
- **e-AWB / Cargo-IMP**: FWB versi 16+ (data AWB), FHL versi 4 (consolidation list — sering keliru disebut house waybill; house waybill data sebenarnya **FZB**), FSU (status update: RCS/FOH/DLV). Cargo-IMP edisi ke-34 (efektif 1 Jan 2015) adalah edisi final; pengembangan berpindah ke Cargo-XML dan **IATA ONE Record** — yang, per IATA Cargo Services Conference, "endorsed ONE Record as the preferred standard for data sharing among air cargo stakeholders effective 1 January 2026" (per data IATA Des 2025: >70% awareness, hampir 50% readiness, maskapai mewakili 72% volume AWB global on-track).
- **IGOM** (prosedur "how to do") & **AHM** (kebijakan "what to do") saling melengkapi; IGOM juga acuan audit ISAGO.
- Sistem wajib mampu mengarsip pesan EDI untuk durasi tertentu (SOP IATA menyebut 5–7 tahun di beberapa bandara).
- **Konteks perintis**: banyak bandara Papua tidak punya GHA komersial → operator self-handling. Turboprop kecil (Caravan/Twin Otter) memuat bulk/loose, bukan ULD, sehingga **W&B manual per-leg sangat kritikal** karena margin berat sempit dan medan pegunungan menuntut akurasi.

### 2. PROSES MAINTENANCE & MRO

**Diagram alur:**
```
POST-FLIGHT INSPECTION / PIREP & pilot report
      │  dokumen: Aircraft Technical Log (ATL)/journey log
      │          (wajib dibawa tiap flight, CASR 91.25)
      ▼
DEFECT / TEMUAN
      ├── dapat di-defer? → MEL check (Kategori A/B/C/D)
      │        A = interval spesifik dalam MEL
      │        B = 3 hari kalender (tak termasuk hari temuan)
      │        C = 10 hari kalender
      │        D = 120 hari kalender
      │        → placard "INOP", entri log, tracking deferred defect
      └── tidak → WORK ORDER
             ├── LINE MAINTENANCE (di stasiun; kewenangan terbatas)
             └── BASE MAINTENANCE / HEAVY CHECK (di hangar/AMO)
      ▼
REMOVAL KOMPONEN → TAGGING "UNSERVICEABLE" (US)
      ▼
KIRIM KE BENGKEL (internal shop / vendor eksternal / OEM)
      ▼
REPAIR / OVERHAUL
      ▼
PENERBITAN RELEASE CERTIFICATE
      │  Indonesia: DGCA Form 21-18 (Authorized Release Certificate/
      │             Airworthiness Approval Tag)
      │  ekuivalen: FAA 8130-3, EASA Form 1, TCCA Form One
      ▼
RECEIVING INSPECTION → SERVICEABLE STOCK (tag serviceable)
      │  gate: verifikasi S/N vs data plate + validitas release cert;
      │        jika mismatch → quarantine
      ▼
INSTALASI ULANG → UPDATE TECHNICAL RECORDS (TSN/TSO, CSN/CSO, position)
      ▼
RETURN TO SERVICE (maintenance release oleh certifying staff Part 65/145)
```

**Maintenance planning & continuing airworthiness:**
- **MRB/MPD**: MRB Report (basis metodologi MSG-3) → sumber Maintenance Planning Document (MPD) OEM → operator menyusun Aircraft Maintenance Program (AMP)/CAMP yang disetujui DGCA. MPD memuat semua persyaratan MRB plus scheduled maintenance mandatori (CMR & Airworthiness Limitations) yang hanya dapat diubah dengan izin otoritas.
- **Scheduled**: A/B/C/D check (label tidak wajib), time-controlled/hard-time items, Airworthiness Limitations (AL) & Certification Maintenance Requirements (CMR).
- **Unscheduled**: defect rectification, AOG.
- **AD/SB compliance**: AD (Airworthiness Directive) **wajib** dan harus terekam permanen dalam maintenance records; SB (Service Bulletin) dari OEM (dapat mandatori bila diangkat menjadi AD).
- **Reliability monitoring / CAMO**: Continuing Analysis & Surveillance (CASR 121.373/135.373; SI 8900-6.6). Program reliability wajib dikembangkan bila program berbasis MSG-3, ada komponen condition-monitored, tidak ada overhaul time untuk semua komponen signifikan, atau disyaratkan MPD/MRB.
- **Klasifikasi maintenance komponen**: Hard Time (HT), On-Condition (OC), Condition Monitoring (CM).

### 3. MANAJEMEN SPAREPART & SUPPLY CHAIN

- **Klasifikasi material**:
  - *Rotable* — high-value, serialized, repairable berulang, dikembalikan ke stok setelah repair/overhaul (mis. landing gear, avionics box).
  - *Repairable* — dapat diperbaiki tetapi nilai/siklus lebih terbatas.
  - *Consumable* — dipakai habis (grease, filter).
  - *Expendable* — tidak diperbaiki, dibuang setelah dipakai (fasteners, seals).
- **Serialized tracking & back-to-birth**: setiap part serialized diberi identitas unik, barcode/RFID permanen (**ATA Spec 2000**) untuk full lifecycle traceability; birth record + rantai release cert menyusun *back-to-birth records*. FAA & EASA menerima Authorized Release Certificate elektronik yang dipertukarkan di bawah **ATA Spec 2000 Chapter 16**.
- **Life-Limited Parts (LLP)**: hard life (mis. turbine disk); status LLP wajib terekam (135.439(a)(2)(ii)/121.380).
- **Shelf life**: consumable dengan expiry (seals, adhesives, oksigen) butuh manajemen tanggal kedaluwarsa.
- **Pooling/exchange/loan/lease & AOG logistics**: untuk operator kecil, akses part pool/exchange dengan vendor mengurangi capital tie-up; AOG desk mengelola pengiriman darurat. Distribusi ke remote station memerlukan stok konsinyasi minimal; setiap movement antar-stasiun harus terekam agar traceability tidak putus.

### 4. REGULASI & KEPATUHAN INDONESIA

**Struktur regulasi**: CASR (Civil Aviation Safety Regulation) Indonesia diterbitkan sebagai Lampiran Keputusan/Peraturan Menteri Perhubungan; harmonis dengan 14 CFR (FAR) AS dengan penomoran section identik. Regulator: Direktorat Jenderal Perhubungan Udara (DGCA/Ditjen Hubud) c.q. **Direktorat Kelaikudaraan dan Pengoperasian Pesawat Udara (DKPPU)**.

**Daftar kewajiban regulasi (dengan sumber):**

| Regulasi | Isi pokok | Sumber |
|---|---|---|
| CASR Part 121/135 Subpart L | Maintenance program (x.367), CAMP, Continuing Analysis & Surveillance (x.373), company maintenance manual (121.369/135.369), maintenance recording (121.380/135.439) | Kemenhub/DGCA (silabus mengutip section) |
| CASR 135.439 / 121.380 | Retensi: record airworthiness release & status 1 tahun/sampai superseded; overhaul sampai superseded oleh work setara; record status ditransfer bersama pesawat saat dijual | teks FAR harmonis (law.cornell.edu) |
| CASR 135.441 | Transfer maintenance records saat pesawat dijual | teks FAR harmonis |
| CASR Part 43 (Lampiran KM 78/2000) | 43.5 & 43.7 (siapa boleh RTS: AME Part 65, AMO Part 145, AOC Part 121/135, manufacturer); 43.9 (isi record: deskripsi, tanggal, nama, tanda tangan+nomor lisensi+kategori); 43.11 (record inspeksi + pernyataan airworthy); **43.12(c) retensi 90 hari setelah unit ditarik permanen**; Appendix B major repair/alteration via DGCA Form 43-337 | PDF resmi Part 43 Amdt.1 |
| CASR Part 145 | AMO: 145.207/209 manual, 145.211 quality & safety, 145.213 inspection, 145.215 capability list, 145.219 recordkeeping, 145.221 reports of failures, 145.223 DGCA inspections; App B SMS | silabus DGCA mengutip section |
| CASR Part 65 | Lisensi Aircraft Maintenance Engineer (AMEL): basic certificate, license, type/group rating; renewal tiap 2 tahun + recent experience | CASR Part 65 Amdt.1 |
| CASR Part 91 | 91.25 journey log dibawa tiap flight; 91.417 maintenance records; 91.419 transfer; 91.421 rebuilt engine; 91.423 SDR | CASR 91 Amdt.5 (PM 81/2017) |
| CASR Part 21 | Certification procedures / airworthiness (Certificate of Airworthiness per Part 21) | CASR 21 |
| DGCA Form 21-18 + SI 21-09 | Authorized Release Certificate/Airworthiness Approval Tag; issuer simpan duplikat ≥2 tahun; dapat berfungsi sebagai indikasi approval for return to service bagi AMO/AOC dengan CAMP | Form & SI resmi DGCA |
| SI 8900-6.6 / 8900-6.9 | Continuing Analysis & Surveillance; auditing & surveillance AMO | JDIH Kemenhub |
| UU No.1/2009 Penerbangan | Definisi angkutan udara perintis (angkutan udara niaga dalam negeri melayani jaringan/rute perintis) | dephub.go.id |
| UU ITE (Ps.11) + PP 71/2019 (Ps.59–60) | Tanda tangan elektronik tersertifikasi (PSrE), keabsahan & kekuatan hukum; UU 1/2024 perubahan kedua | JDIH Komdigi |

**Data & dokumen yang WAJIB terekam & dapat diaudit DKPPU:**
- Aircraft Technical Log / journey log (per flight, jam & cycle).
- Maintenance records: work order, task card, sign-off certifying staff.
- Traceability part: serial, release cert (Form 21-18), back-to-birth.
- CAMP/AMP status; AD/SB status; LLP status; TSN/TSO/CSN/CSO.
- Deferred defects/MEL log.
- Personnel qualification (Part 65 license & rating scope).

**Implikasi desain sistem:**
- *Audit trail imutabel*: setiap perubahan record tercatat (siapa, kapan, apa perubahan) — tidak dapat dihapus (append-only/WORM).
- *E-signature*: gunakan TTE **tersertifikasi** via PSrE terdaftar Komdigi (kekuatan pembuktian tertinggi sesuai PP 71/2019 Ps.59–60; kombinasi ≥2 faktor autentikasi) untuk sign-off maintenance release; scan/tempel di PDF **tidak** setara secara hukum.
- *Imutabilitas*: penyimpanan append-only untuk record airworthiness.
- *Penerimaan eTLB*: karena belum ada AC/SI Indonesia spesifik, operator perlu proposal & approval formal ke DKPPU (analog jalur OpSpec A025 FAA); FAA AC 120-78B (dan EASA setara) menjadi acuan penyusunan standar sistem (elemen kunci e-signature, akses record untuk otoritas, keamanan sistem).
- *Retensi*: engine sistem harus menahan record sesuai periode (1 tahun/superseded; life-of-aircraft untuk status; 90 hari pasca-withdrawal untuk unit; ≥2 tahun untuk duplikat Form 21-18) dan mendukung transfer record saat pesawat dijual.

### 5. ARSITEKTUR MODUL & DATA

**Modul lazim sistem ERP/MRO penerbangan:**
- Engineering (AD/SB, modifikasi, engineering order, konfigurasi baseline)
- Planning (forecast, work package, task card, slot)
- Materials/Inventory (stock, purchasing, rotable pool, shelf life)
- Line Maintenance (mobile/tablet, defect, MEL)
- Base Maintenance / Heavy Check
- Component / Shop (repair order, workscope, release)
- Technical Records (TSN/TSO, back-to-birth, C of A)
- Reliability (event, alert, rate, CASA)
- Procurement (PO, vendor, RO, exchange)
- Finance (cost, invoicing, WIP)
- HR/Certifying staff qualification (Part 65 license, authorization scope)
- Flight Ops / Cargo (flight leg, AWB, load control)

**Tabel entitas data utama:**

| Entitas | Atribut kunci | Relasi | Sumber sistem |
|---|---|---|---|
| Aircraft | registration (PK-xxx), MSN, type, TSN, CSN | ⟶ Flight Leg, Component (installed), Work Order | Fleet/Engineering |
| Component/Part | part number, serial number, ATA chapter, TSN/TSO, CSN/CSO, position/effectivity, LLP limit, shelf-life | ⟶ Aircraft (position), Release Cert, Work Order | Materials/Technical Records |
| Part Master | part number, description, class (rotable/repairable/consumable/expendable), interchangeability | ⟶ Component, Stock, PO | Materials |
| Work Order | WO number, aircraft reg, type (line/base/shop), status, task cards | ⟶ Task Card, Component removal/install, certifying staff | Planning/Maintenance |
| Task Card | task ref, ATA, interval, MPD/MRB source, sign-off | ⟶ Work Order, AMP | Planning |
| Release Certificate | Form 21-18 no., part S/N, date, approver, RTS statement | ⟶ Component, Work Order | Shop/Records |
| Flight Leg | flight no., date, dep/arr, block hours, cycles, aircraft reg | ⟶ Aircraft (hrs/cyc), AWB/manifest | Flight Ops |
| AWB | AWB no., shipper, consignee, weight, pieces, SHC, DG | ⟶ Flight Leg (manifest), booking | Cargo |
| Deferred Defect/MEL | defect id, MEL cat (A/B/C/D), raised date, due date | ⟶ Aircraft, Work Order | Line Maintenance |
| Certifying Staff | license no. (Part 65), ratings, authorization scope, expiry | ⟶ Work Order sign-off | HR/Quality |

**Integrasi/handoff & failure points umum:**
- **Ops→Maintenance (flight hours/cycles)**: mismatch jam terbang dari flight ops ke maintenance = penyebab umum error hitung interval → LLP/AD berpotensi terlewat. Butuh *single source of truth* flight leg.
- **Cargo→Load control (AWB→loadsheet)**: data berat harus konsisten agar W&B akurat.
- **Initial data migration**: baseline konfigurasi pesawat & status komponen saat go-live adalah titik gagal #1 — dirty data (part number/jam salah) dapat menghentikan pesawat (grounded).
- **Duplikasi part master**: nomor part sama dientri berbeda → stok pecah, rekonsiliasi gagal.
- **Rekonsiliasi stok**: fisik vs sistem, terutama stok remote station.

### 6. BENCHMARK & PRAKTIK INDUSTRI

**Perbandingan vendor:**

| Solusi | Vendor | Segmen | Deployment | Catatan untuk operator perintis |
|---|---|---|---|---|
| AMOS | Swiss-AS | Airline/MRO besar, fleet kompleks | on-prem/cloud | Fungsi dalam & traceability kuat; kompleks & mahal; cenderung *overkill* untuk fleet kecil |
| TRAX (eMRO/eMobility) | TRAX | Fleet besar | device-agnostic, mobile | Enterprise; modul luas; digital engineering (TechDocs) |
| Ramco Aviation | Ramco | Mid-market s/d enterprise, MRO+ERP+HR/payroll | cloud-native, mobile offline-capable | Integrasi ERP luas; mobility-first (task card digital, offline); cocok bila butuh finance+HR terpadu |
| IFS Cloud / Maintenix | IFS | Komersial & militer, asset lifecycle | cloud | Skalabel; berat |
| **ENVISION** | **Rusada** | **Regional/kecil-menengah, mixed fleet turboprop/piston/heli** | web-based, device-agnostic, app "Envision Tasks" (tablet) | **Paling relevan**: terbukti pada Air Chathams (ATR 72), Manta Air (ATR72-600 + Twin Otter, live 8 modul dalam 4 bulan), Texel Air (cargo); Rusada: "It can manage a fleet of one, or a fleet of one thousand" |
| **AIRPACK** | **ADSoftware (kini Vellox)** | **Operator/MRO/CAMO kecil (50+ klien)** | Windows/web, cloud hosting | Sederhana, training ~5 hari, harga kompetitif, dukungan 24/7; modul AIRTIME/AIRSTOCK/AIRUSER/AIRDOC/AIRSTAT/AIRWORK; cocok fleet kecil |
| Veryon (Tracking+/Traxxall) | Veryon | Regional, GA, heli, government | cloud | User-friendly; compliance & records; cocok operator regional |
| Ultramain | Ultramain | Airline/MRO | mobile (ELB/digital logbook) | Digital logbook & work scoping |
| Corridor | Continuum | GA/MRO Amerika | — | Repair station |
| CAMP / Flightdocs | CAMP Systems | Business/GA | cloud | Tracking, forecasting, reliability |
| Comply365 / Web Manuals | — | Manual & document control | cloud | Pelengkap (manual authoring), bukan MRO inti |
| AVIATAR | Lufthansa Technik | Predictive/analytics | cloud | Add-on analytics; LHT klaim mampu memangkas hingga 30% unscheduled removal |

**Pelajaran dari kegagalan/molor implementasi:**
- Metodologi *Big Bang* & *Phased Rollout* standar sering tidak cocok untuk aviation MRO karena tuntutan operasional & regulator; dibutuhkan feedback berkelanjutan dan adaptasi ke standar regulasi.
- Penyebab utama gagal: rush rollout, **dirty data** (part number/jam salah dapat menghentikan pesawat), scope accounting vs operasional dikira sama, tidak ada *internal owner*, dokumentasi tidak lengkap. Estimasi industri: hingga ~80% proyek software gagal bila tim tidak diberi waktu belajar cukup.
- **Southwest Airlines (Des 2022)**: sistem *crew-scheduling* legacy "SkySolver" (dirancang era 1990-an) memicu pembatalan **16.700+ penerbangan**; Southwest didenda **US$140 juta oleh DOT** (denda terbesar dalam sejarah agensi) dan mencatat kerugian **>US$1 miliar**, lalu menegaskan komitmen anggaran modernisasi teknologi **US$1,3 miliar per tahun** untuk 2023. Pelajaran: legacy yang tidak di-upgrade tepat waktu adalah risiko eksistensial.
- Rekomendasi: **dual-run validation** (paralel sistem baru vs paper/legacy sebelum retire), staging jelas, tim lead maintenance+CAMO.

**Tantangan spesifik operasi remote (Papua):**
- Konektivitas terbatas/no-connectivity di bandara perintis → wajib **offline-first**: aplikasi tablet line maintenance & cargo acceptance harus jalan offline dan sinkron saat online, dengan **conflict resolution** (mis. last-write-wins per field + audit log, atau merge dengan flag manual).
- SDM engineer bersertifikat (Part 65) & pilot mountain-rating sangat terbatas di remote area — sistem harus mudah dipakai, memandu prosedur, dan memberi validasi otomatis untuk mencegah error.
- Keamanan (contoh nyata: penembakan Cessna Grand Caravan PK-SNR milik Smart Cakrawala Aviation, rute Tanah Merah–Danawage, 11 Feb 2026; DGCA menegaskan operator yang menghentikan penerbangan atas alasan keamanan tidak dikenai sanksi), cuaca buruk, dan infrastruktur bandara minim (UPBU kelas III); armada Caravan/Pilatus untuk medan pegunungan.
- **Program Jembatan Udara** (perintis kargo) melibatkan multi-operator (Trigana Air, Nasional Global Aviasi, Susi Air, dll). Per KP 206/207 Tahun 2024, terdapat **22 Korwil, 46 rute kargo perintis** (plus 266 rute penumpang & 1 rute subsidi kargo); 46 rute kargo terkonsentrasi pada 7 KPA Korwil: Tarakan, Masamba, Timika, Dekai, Tanah Merah, Oksibil, dan Wamena.

## Recommendations

**Tahap 0 — Fondasi (bulan 0–3):**
- Petakan proses AS-IS kedua rantai; tetapkan *single source of truth*: flight leg (jam/cycle) dan part master.
- Bersihkan & verifikasi baseline konfigurasi pesawat + status komponen (TSN/TSO, LLP, AD/SB) **sebelum** memilih sistem. Benchmark keluar tahap: 100% part serialized punya release cert & jam terverifikasi.

**Tahap 1 — Seleksi vendor (bulan 3–6):**
- Shortlist **ENVISION, AIRPACK, Ramco, Veryon** (hindari AMOS/TRAX/IFS untuk skala perintis).
- Kriteria wajib: (a) mobile **offline-first** line maintenance & cargo; (b) e-signature ready + audit trail imutabel; (c) modul CAMO/reliability; (d) dukungan Cargo-IMP/e-AWB (dan roadmap ONE Record); (e) referensi operator turboprop kecil.
- Threshold ganti keputusan: bila vendor tidak dapat mendemokan offline-sync pada kondisi no-connectivity → coret.

**Tahap 2 — Implementasi bertahap (bulan 6–18):**
- Mulai dari modul **technical records + materials + line maintenance** (bukan Big Bang). Dual-run paralel dengan paper minimal 1 siklus check.
- Ajukan approval formal ke **DKPPU** untuk electronic recordkeeping/eTLB & e-signature; gunakan **PSrE tersertifikasi** untuk sign-off maintenance release.
- Benchmark go-live: rekonsiliasi stok >98%, nol duplikasi part master, mismatch jam ops↔maintenance = 0.

**Tahap 3 — Optimasi (bulan 18+):**
- Aktifkan reliability monitoring & (opsional) predictive analytics.
- Integrasi cargo track & trace + POD digital; siapkan migrasi Cargo-IMP → Cargo-XML/ONE Record.
- Threshold: jika unscheduled removal turun & dispatch reliability naik konsisten, pertimbangkan *interval escalation* berbasis data reliability (dengan approval DGCA).

## Caveats
- Teks retensi record CASR 135.439/121.380/91.417 dikonfirmasi dari FAR AS yang diadopsi harmonis oleh Indonesia; **angka persis pada PDF CASR Indonesia perlu diverifikasi langsung** ke JDIH Kemenhub/hubud.kemenhub.go.id. Retensi 90 hari (43.12(c)) serta Form 21-18/SI 21-09 dikonfirmasi dari teks Indonesia.
- Belum ditemukan AC/SI Indonesia yang eksplisit mengesahkan eTLB/e-signature untuk maintenance records; jalur approval DKPPU bersifat kasuistik. AC e-records Des 2023 yang muncul dalam pencarian adalah milik **DGCA India**, bukan Indonesia — jangan dikutip sebagai regulasi Indonesia.
- Beberapa detail vendor (harga, fitur, ranking) berasal dari materi pemasaran vendor & direktori/komparasi pihak ketiga (G2, Capterra, direktori Aircraft IT), bukan data pangsa pasar terverifikasi independen; validasi via RFP/demo.
- Standar cargo & ground handling (IGOM/AHM/DGR) serta ATA Spec 2000 bersifat berbayar; nomor edisi & bab spesifik perlu dibeli dari IATA/ATA untuk implementasi presisi.
- Contoh Air India (approval eTLB DGCA India Juli 2026) dan Southwest disajikan sebagai *pembanding industri*, bukan preseden regulasi Indonesia.