# **Laporan Riset MRO: Desain Arsitektur Modul Maintenance Program & Planning**

## **Ringkasan**

Laporan komprehensif ini menyajikan cetak biru arsitektur dan logika bisnis untuk merancang sistem *Maintenance, Repair, and Overhaul* (MRO) khusus bagi operator kargo perintis di bawah yurisdiksi Direktorat Jenderal Perhubungan Udara (DKPPU) Indonesia. Perancangan modul *Maintenance Program & Planning* menuntut keakuratan matematis absolut dalam menghitung *Next Due* berdasarkan prinsip *Whichever Comes First* lintas parameter, karena kegagalan kalkulasi akan berdampak langsung pada pelanggaran status kelaikudaraan (*airworthiness*). Operasional pesawat turboprop dengan utilisasi tinggi sangat bergantung pada metode *Phase Check* untuk mendistribusikan beban kerja secara merata dan meminimalkan kerugian finansial akibat *downtime*1. Laporan ini membedah secara tegas batas antara kewajiban regulasi CASR, praktik industri penerbangan umum, dan pilihan desain sistem untuk menggantikan proses manual tanpa mengorbankan kepatuhan terhadap standar keselamatan. Sistem yang dirancang harus bertindak sebagai penjaga gerbang yang secara otomatis menolak anomali data dan mencegah eskalasi interval yang tidak sah4.

## **A. Aritmetika Interval dan Due Date**

Bagian ini merupakan fondasi paling kritis dalam modul *Maintenance Planning*. Kesalahan desain algoritma di area ini akan menyebabkan pesawat berstatus *unairworthy* (tidak laik terbang), yang dapat berujung pada pencabutan *Air Operator Certificate* (AOC) oleh regulator atau insiden fatal.

### **1\. Jenis-Jenis Interval Maintenance dan Penggunaannya**

Setiap komponen pesawat mengalami degradasi melalui mekanisme fisik dan kimiawi yang berbeda. Oleh karena itu, **\[Kewajiban Regulasi\]** dan dokumen *Maintenance Planning Document* (MPD) dari pabrikan menetapkan interval pemeliharaan dalam berbagai dimensi2. Sistem database harus dirancang untuk mengakomodasi nilai multi-dimensi untuk setiap *task*.

| Jenis Interval | Singkatan | Mekanisme Degradasi | Contoh Penggunaan | Implikasi Desain Sistem |
| :---- | :---- | :---- | :---- | :---- |
| **Flight Hours** | FH | Keausan mekanis akibat gesekan dan operasi berkesinambungan selama pesawat berada di udara. | Inspeksi filter oli mesin, pemeriksaan generator listrik. | Sistem harus membaca *Aircraft Total Time* (AFTF) yang dihitung dari *take-off* hingga *landing*. |
| **Flight Cycles** | FC | Tekanan struktural dan siklus presurisasi kabin (mengembang dan menyusutnya badan pesawat). | Inspeksi *Landing Gear*, inspeksi struktur sayap, dan *fuselage*. | Sistem mendefinisikan 1 FC sebagai satu siklus lengkap *take-off* dan *landing*. |
| **Calendar Time** | Mo/Yr/Dy | Korosi, kelembapan lingkungan, penuaan bahan kimiawi, dan degradasi karet/*seal*. | Inspeksi korosi struktural, kedaluwarsa baterai darurat, penggantian selang hidrolik. | Waktu berjalan mutlak terlepas dari pesawat terbang atau diparkir di hanggar (*Aircraft on Ground* / AOG). |
| **Engine Hours/Cycles** | EH / EC | Sama dengan FH/FC, namun spesifik untuk modul mesin yang dapat dilepas pasang. | Inspeksi bilah turbin (*turbine blades*), keausan kompresor. | **\[Praktik Industri\]** Sistem tidak boleh mengikat umur mesin dengan umur *airframe* (badan pesawat) karena mesin bisa dipindah ke pesawat lain. |

### **2\. Perhitungan Next Due dari Last Done**

Perhitungan *Next Due* (ND) memerlukan pemahaman fundamental tentang perbedaan antara jam terbang pesawat secara keseluruhan dan jam terbang komponen individual. **\[Praktik Industri Umum\]** mengandalkan dua parameter waktu utama: *Airframe Total Time* (AFTF) untuk *task* yang melekat pada badan pesawat, dan *Time Since New* (TSN) atau *Time Since Overhaul* (TSO) untuk komponen *rotable* yang dapat dicabut-pasang8.  
**Skenario Konkret (Berbasis Flight Hours):** Asumsikan Rimbun Air mengoperasikan pesawat ATR 72\.

* **Task:** Penggantian *Starter Generator* (Interval: 1.500 FH).  
* **Status Pesawat Saat Ini (Current AFTF):** 5.200 FH.  
* **Rekam Jejak (Last Done):** Komponen terakhir kali diganti saat pesawat berada pada 4.000 FH.

**Algoritma Sistem:**

> 1. Next Due \= Last Done \+ Interval  
> 2. Next Due \= 4.000 FH \+ 1.500 FH \= 5.500 FH.  
> 3. Remaining (Sisa Waktu) \= Next Due \- Current AFTF  
> 4. Remaining \= 5.500 FH \- 5.200 FH \= 300 FH.

**\[Pilihan Desain\]** Sistem harus menampilkan Remaining \= 300 FH kepada perencana (*Planner*), bukan sekadar angka mentah. Jika komponen tersebut adalah komponen bekas yang dipasang dari pesawat lain, maka perhitungan *Next Due* harus menggunakan nilai *Time Since New* (TSN) dari komponen tersebut, bukan AFTF pesawat saat ini. Kesalahan desain yang paling sering terjadi adalah menyamaratakan umur komponen dengan umur pesawat.

### **3\. Logika "Whichever Comes First" (WCF)**

Mayoritas *task* pemeliharaan kritis memiliki lebih dari satu parameter yang berjalan bersamaan. Aturan **\[Kewajiban Regulasi\]** menetapkan bahwa *task* harus dieksekusi pada parameter apa pun yang tercapai lebih dahulu (*Whichever Comes First*).  
**Skenario Angka Konkret WCF:** Sebuah *task* inspeksi struktur sayap memiliki interval: **1.500 FH ATAU 1.500 FC ATAU 12 Bulan (WCF)**. Asumsi *Average Daily Utilization* (ADU) atau rata-rata terbang harian pesawat di Papua adalah: **5 FH/hari** dan **6 FC/hari**.

* **Pekerjaan Terakhir (Last Done):** 1 Januari 2026\.  
  * Posisi AFTF saat itu: 10.000 FH.  
  * Posisi siklus saat itu: 12.000 FC.  
* **Kondisi Hari Ini (1 Mei 2026):**  
  * Current AFTF: 10.600 FH.  
  * Current FC: 12.720 FC.

**Algoritma Proyeksi WCF Sistem:** Sistem harus mengkalkulasi *Estimated Due Date* (EDD) untuk ketiga parameter dan membandingkannya:

> 1. **Parameter FH:**  
   * Limit \= ![][image1] FH.  
   * Sisa (Remaining) \= ![][image2] FH.  
   * Proyeksi Hari \= ![][image3].  
   * EDD FH \= 1 Mei 2026 \+ 180 hari \= **28 Oktober 2026**.  
> 2. **Parameter FC:**  
   * Limit \= ![][image4] FC.  
   * Sisa (Remaining) \= ![][image5] FC.  
   * Proyeksi Hari \= ![][image6].  
   * EDD FC \= 1 Mei 2026 \+ 130 hari \= **8 September 2026**.  
> 3. **Parameter Kalender:**  
   * Limit Kalender \= 1 Januari 2026 \+ 12 Bulan \= **1 Januari 2027**.

**Resolusi Sistem:** Sistem membandingkan (28 Okt 2026, 8 Sep 2026, 1 Jan 2027). Parameter FC menghasilkan tanggal paling awal, sehingga *task* ini dikendalikan oleh FC. Sistem **\[Pilihan Desain\]** harus menyorot tanggal **8 September 2026** dengan warna merah sebagai *Absolute Due Date*.

### **4\. Tolerance / Variance (Toleransi)**

Toleransi adalah jendela waktu ekstra yang diizinkan untuk melewati batas interval asli tanpa melanggar regulasi.

* **Siapa yang menetapkan?** Pabrikan (OEM) mengusulkannya dalam dokumen desain, dan **\[Kewajiban Regulasi\]** mengharuskan operator (Rimbun Air) untuk mengesahkannya bersama DKPPU dalam dokumen *Approved Maintenance Program* (AMP)4.  
* **Besaran Standar:** Biasanya 10% dari batas interval (misal: untuk interval 500 FH, toleransinya adalah 50 FH), atau nilai absolut seperti maksimal 1 bulan.

**Pertanyaan Kritis: Jika task dikerjakan di dalam jendela toleransi, dari mana Next Due dihitung?** Ini adalah area di mana sistem Anda harus sangat ketat untuk mencegah fenomena "interval creep" (penggelembungan interval yang membahayakan keselamatan).

* **Praktik A (Standar Industri & EASA/FAA):** Jika *task* dieksekusi memanfaatkan toleransi (terlambat dari due date asli), maka *Next Due* **HARUS** dihitung dari *Due Date Asli*, BUKAN dari tanggal aktual pengerjaan10.  
  * *Contoh:* Interval 500 FH. Due Date di 500 FH. Mekanik mengerjakannya pada 540 FH (memakai toleransi 40 FH).  
  * *Kalkulasi Praktik A:* Next Due \= 500 (Due Asli) \+ 500 (Interval) \= **1.000 FH**.  
* **Praktik B (Reset dari Aktual):** Jika dihitung dari aktual, Next Due \= 540 \+ 500 \= **1.040 FH**.

**\[Pilihan Desain & Praktik Industri Umum\]**: Sistem yang Anda bangun **WAJIB menerapkan Praktik A secara otomatis**. Jika Anda mengizinkan Praktik B terjadi secara otomatis, operator dapat mengakumulasi keterlambatan (misal siklus berikutnya menjadi 1.040 \+ 540 \= 1.580 FH, dst), yang secara efektif mengubah interval dasar tanpa persetujuan regulator. **Peringatan Eksplisit:** Meskipun CASR selaras dengan FAA (Amerika Serikat), Anda harus memastikan bahwa logika sistem Anda mematuhi panduan EASA AMC M.A.302 atau panduan DKPPU terkait *permitted variation*4. Jika mekanik mengerjakan *lebih awal* (misal di 450 FH), maka sistem umumnya me-reset perhitungan dari 450 \+ 500 \= 950 FH (operator "rugi" 50 FH, demi menjamin batas keselamatan tidak pernah terlampaui).

### **5\. Interval Escalation (Eskalasi)**

Eskalasi adalah perpanjangan interval pemeliharaan secara permanen (misalnya, dari 500 FH menjadi 600 FH) untuk seluruh armada operator.

* **\[Kewajiban Regulasi\]**: Menurut CASR 121.367 dan 135.367, setiap deviasi atau perubahan dari program pemeliharaan dasar **wajib mendapatkan persetujuan tertulis dari DKPPU**4.  
* **Prosedur:** Operator harus mengumpulkan data dari *Reliability Program* selama berbulan-bulan yang membuktikan bahwa pada batas 500 FH, tidak ada kerusakan atau cacat yang signifikan. Setelah data diserahkan, DKPPU akan menerbitkan revisi AMP9.  
* **\[Pilihan Desain Sistem\]**: Sistem harus memiliki fitur penguncian (*lock*) pada tabel *Master Task*. Hanya pengguna dengan peran (role) spesifik seperti *Engineering Manager* yang diizinkan untuk mengedit interval dasar, dan sistem harus mencatat jejak audit (*audit trail*) yang merekam nomor surat persetujuan DKPPU sebagai justifikasi perubahan. Penting dicatat, *task* tertentu seperti *Airworthiness Directives* (AD) dan *Life Limited Parts* (LLP) **tidak boleh dieskalasi sama sekali**11.

### **6\. Forecasting (Prakiraan Jatuh Tempo)**

Sistem meramalkan kapan sebuah *task* akan jatuh tempo di kalender masa depan dengan mengandalkan parameter Utilisasi Harian Rata-rata (*Average Daily Utilization* / ADU).  
**Rumus dan Algoritma Sistem:**

> 1. **Hitung ADU Dinamis:** ADU \= (Total FH 90 hari terakhir) / 90\. (Sistem harus mengeksekusi hitungan ini setiap malam secara *batch process*).  
> 2. **Rumus Target Date:**  
>    ![][image7]

**Contoh:**

* Sisa waktu (*Remaining*) \= 400 FH.  
* Total terbang dalam 90 hari terakhir \= 450 FH.  
* ADU \= 450 / 90 \= 5 FH per hari.  
* Est. Due Date \= Hari Ini \+ (400 / 5\) \= Hari Ini \+ 80 hari.

### **7\. Realitas Melencengnya Forecast di Dunia Nyata**

Meskipun sistem memproyeksikan tanggal dengan rumus presisi, *planner* sering menemukan tanggal tersebut bergeser di dunia nyata. Hal ini wajar dalam **\[Praktik Industri Umum\]**, dan sistem harus mampu beradaptasi secara dinamis setiap kali *Flight Log* baru dimasukkan. Penyebab utama melesetnya forecast meliputi:

> 1. **Aircraft on Ground (AOG):** Pesawat mengalami kerusakan mesin tak terduga dan tertahan di hanggar selama 2 minggu. Selama periode ini, ADU anjlok mendekati 0\. Dampaknya, *task* berbasis FH dan FC akan terdorong mundur ke masa depan, namun *task* berbasis kalender (misal: jatuh tempo bulan depan) akan tetap tidak berubah, sehingga jarak antar-*task* menjadi tidak sinkron.  
> 2. **Perubahan Rute Mendadak:** Rimbun Air mendapatkan kontrak pengiriman logistik Pemilu ke pedalaman Papua yang menyebabkan utilisasi harian melonjak dari 4 FH menjadi 8 FH. *Task* akan jatuh tempo jauh lebih cepat dari kalender yang diprediksi sistem.  
> 3. **Faktor Lingkungan/Cuaca:** Penutupan bandara akibat cuaca buruk di Papua membuat pesawat diam, berdampak sama seperti skenario AOG.

## **B. Struktur Program Maintenance**

Pemahaman tentang hierarki dokumen teknis mutlak diperlukan agar sistem Anda tidak melanggar batas legalitas.

### **8\. Rantai Dokumen: MRB → MPD → AMP/CAMP**

Ini adalah hierarki **\[Kewajiban Regulasi\]** yang membimbing lahirnya setiap *task* dalam sistem Anda2.

> 1. **Maintenance Review Board (MRB) Report:** Sebuah komite awal yang terdiri dari pabrikan pesawat (misal: ATR), regulator negara pembuat (misal: EASA di Eropa), dan perwakilan operator. Mereka menentukan standar keselamatan minimum saat pesawat pertama kali disertifikasi.  
> 2. **Maintenance Planning Document (MPD):** Berdasarkan laporan MRB, pabrikan menerbitkan MPD. Ini adalah "Buku Suci" yang berisi puluhan ribu *task* mentah.  
> 3. **Approved Maintenance Program (AMP) / Continuous Airworthiness Maintenance Program (CAMP):** Dokumen milik Rimbun Air. Maskapai menyalin *task* dari MPD, lalu menyesuaikannya dengan kondisi operasi lokal (misal: lingkungan berdebu di Papua) dan regulasi lokal DKPPU. **AMP harus disahkan oleh DKPPU**4.

**Aturan Emas:** Operator (Rimbun Air) **Boleh** membuat interval lebih ketat dari MPD (misal: MPD mewajibkan 500 FH, Rimbun menjadikannya 400 FH karena paparan debu *unpaved runway*14). Namun, operator **Tidak Boleh** melonggarkan interval tanpa kajian teknik yang kompleks dan persetujuan DKPPU4.

### **9\. Anatomi Sebuah Task Card**

*Task Card* (atau *Job Card*) adalah instruksi kerja fisik yang akan dicetak oleh sistem Anda untuk dieksekusi oleh mekanik di hanggar1.  
**\[Pilihan Desain\]** Sistem harus memiliki tabel dengan atribut minimum sebagai berikut:

| Field / Kolom | Penjelasan & Fungsi dalam Sistem |
| :---- | :---- |
| **Task Number** | Identitas unik (misal: 32-10-00-101). Sistem harus memblokir duplikasi. |
| **Task Description** | Penjelasan ringkas, e.g., "Inspect Main Landing Gear Tire". |
| **Effectivity** | Menentukan pesawat mana yang terdampak. (Tidak semua *task* ATR 72 berlaku untuk semua MSN/nomor seri pesawat). Sistem memfilter *task* berdasarkan registrasi. |
| **Interval** | Nilai frekuensi pengulangan (e.g., 500 FH, 12 Month). |
| **Skill Code / Trade** | Kualifikasi lisensi mekanik (misal: A untuk Airframe, M untuk Mekanik, E untuk Elektrikal/Avionic). |
| **Man-Hours (MHR)** | Estimasi beban kerja (misal: 2 Jam x 2 Mekanik \= 4 MHR). Digunakan sistem untuk kalkulasi kapasitas hanggar. |
| **Parts / Tools Required** | Tautan relasional ke tabel Inventory/Gudang. Sistem harus memverifikasi apakah suku cadang tersedia sebelum mencetak *Task Card*. |
| **Sign-Off / RII** | Kolom validasi penyelesaian. RII (*Required Inspection Item*) adalah kewajiban regulasi di mana *task* kritis harus diperiksa ulang oleh inspektur independen yang tidak melakukan pekerjaan tersebut1. |

### **10\. Sistem Penomoran Task dan ATA Chapter**

Dunia penerbangan menggunakan standar klasifikasi global bernama **ATA iSpec 2200** (dahulu ATA 100). Penomoran ini menggunakan format 6 digit: XX-YY-ZZ8.

* **XX (Chapter):** Mengindikasikan sistem utama (Misal: 28 \= *Fuel*, 32 \= *Landing Gear*, 72 \= *Engine*).  
* **YY (Section):** Mengindikasikan sub-sistem (Misal: 32-10 \= *Main Landing Gear*).  
* **ZZ (Subject):** Mengindikasikan komponen spesifik.**\[Pilihan Desain\]**: Sistem Anda wajib memiliki tabel master ATA Chapter sehingga *planner* dapat melakukan *filter* pencarian *task* berdasarkan sistem pesawat (misalnya memfilter semua *task* kelistrikan di ATA 24).

### **11\. Hard Time vs On-Condition vs Condition Monitoring (Dalam Penjadwalan)**

Perbedaan ketiga filosofi ini sangat memengaruhi **perilaku algoritma penjadwalan** dalam sistem Anda17:

* **Hard Time (HT):** Komponen memiliki batas umur mutlak dan harus dicabut, dibuang, atau di-*overhaul* saat batas itu tercapai, terlepas dari apakah kondisinya masih bagus.  
  * *Implikasi Sistem:* Sistem harus melacak parameter TSN (Time Since New) dan otomatis memblokir pesawat terbang jika batas HT tercapai tanpa ada perpanjangan sah.  
* **On-Condition (OC):** Komponen dijadwalkan untuk "diinspeksi" secara periodik. Jika ditemukan keausan di atas standar, komponen diganti. Jika masih bagus, komponen dibiarkan beroperasi sampai jadwal inspeksi berikutnya.  
  * *Implikasi Sistem:* Sistem hanya menjadwalkan tiket *task inspeksi*, bukan tiket *pencopotan komponen*. Penggantian hanya terpicu jika mekanik mencatat temuan (*defect*) di dalam *Task Card*.  
* **Condition Monitoring (CM):** Tidak ada interval pemeliharaan atau pembongkaran yang dijadwalkan secara keras. Sebagai gantinya, kesehatan komponen diukur terus menerus melalui sensor dan data. Contoh klasiknya adalah **ECTM (Engine Condition Trend Monitoring)** pada mesin Pratt & Whitney PW127 yang digunakan armada ATR Rimbun Air19.  
  * *Implikasi Sistem:* Untuk mesin PW127, parameter seperti suhu turbin (ITT), kecepatan putaran (NH, NL), dan aliran bahan bakar (WF) dicatat dan dianalisis20. Sistem MRO Anda tidak perlu menjadwalkan "waktu inspeksi", melainkan harus memiliki fitur API atau modul unggah data CSV untuk menerima laporan ECTM harian. Jika grafik tren menyilang garis batas aman (deviasi), sistem baru secara reaktif men-*trigger* sebuah peringatan (*alert*) perbaikan.

### **12\. Life Limited Parts (LLP) dan Airworthiness Limitations**

Ini adalah batasan paling suci dalam dunia penerbangan **\[Kewajiban Regulasi\]**. Bagian dari desain pesawat dikategorikan sebagai *Airworthiness Limitations Section* (ALS) atau *Airworthiness Limitations Items* (AWL), termasuk *Certification Maintenance Requirements* (CMR) dan bagian *Life Limited Parts* (LLP) seperti cakram turbin mesin atau pilar utama *landing gear*12.

* **Karakteristik:** Berbeda dengan *task* biasa, LLP adalah titik henti mutlak (*hard-stop*).  
* **Implikasi Sistem yang Wajib Ada:** Sistem harus menolak memberikan toleransi (*variance*) apa pun untuk *task* berlabel AWL, CMR, atau LLP. Tidak ada eskalasi. Jika suatu disk turbin memiliki batas 15.000 FC dan pesawat telah mencapai 15.000 FC, sistem harus menolak pembuatan *Certificate of Release to Service* (CRS) dan mengkategorikan pesawat sebagai AOG seketika12.

## **C. Work Package / Check-Pack**

Tidak efisien dan merugikan maskapai jika pesawat harus ditarik ke hanggar setiap kali ada satu *task* yang jatuh tempo. Di sinilah *Work Package* atau *Check-pack* berperan.

### **13\. Membundel Task (Check-Pack)**

**\[Praktik Industri Umum\]** *Maintenance Planner* menggunakan sistem MRO untuk mengidentifikasi seluruh *task* (ratusan baris) yang akan jatuh tempo dalam, misalnya, rentang 30 hari ke depan. Semua *task* ini dibundel ke dalam satu tiket kerja besar (*Work Package*). Hal ini bertujuan agar saat mekanik membuka panel lantai kabin, mereka bisa menyelesaikan 10 inspeksi sekaligus, tanpa harus membongkar panel yang sama minggu depan2.

### **14\. Letter Check vs. Phase Check (Equalized Maintenance)**

Ada dua strategi utama dalam membundel *task*, dan pemahaman ini krusial untuk fitur *Work Package Management* di sistem Anda.

| Karakteristik | Letter Check (Block Concept) | Phase Check (Equalized Maintenance) |
| :---- | :---- | :---- |
| **Deskripsi** | Bundel statis skala raksasa. Dinamai A-Check (ringan), C-Check (berat), D-Check (overhaul). | Semua *task* dari A, C, D Check dipecah, didistribusikan, dan diratakan menjadi lusinan paket kecil (misal Phase 1 hingga Phase 75\)1. |
| **Downtime Pesawat** | C-Check menuntut pesawat menginap di hanggar 2–4 minggu berturut-turut. | Setiap Phase Check dirancang untuk bisa diselesaikan dalam 1–2 malam, lalu pesawat terbang normal besoknya2. |
| **Kesesuaian** | Jet komersial besar yang memiliki pesawat cadangan untuk menggantikan rute saat pesawat dihanggarkan. | Maskapai kargo turboprop regional (seperti Rimbun Air) dengan armada minim dan kebutuhan *cash flow* operasional harian yang sangat tinggi2. |
| **Implikasi Sistem** | Sistem cukup melacak siklus statis blok A1, A2, C1, dst. | Sistem dituntut mahir menangani interval fraksional. Sistem harus memampukan *planner* melakukan *drag-and-drop* *task individual* ke berbagai kalender harian untuk pemerataan beban kerja mekanik (*man-hour smoothing*). |

Mengapa Rimbun Air kemungkinan menggunakan *Phase Check*? Turboprop perintis yang tidak terbang kargo selama 3 minggu untuk C-Check akan mengalami kerugian finansial masif. Memecah C-Check menjadi inspeksi-inspeksi malam hari mempertahankan utilisasi. Sistem Anda **jangan** meng-*hardcode* istilah "C-Check" sebagai satu-satunya *template*. Rancanglah arsitektur yang berpusat pada *Task* (*Task-oriented*), di mana *Check-Pack* sekadar menjadi "keranjang belanja" fleksibel bagi *task-task* tersebut1.

### **15\. Task Gagal Dikerjakan dalam Check-Pack**

Jika pesawat sudah telanjur di hanggar dan ternyata satu *task* dalam *check-pack* tidak bisa diselesaikan (contoh: *spare part* rusak dalam pengiriman ke Papua), apa yang terjadi? Sistem Anda harus menyediakan jalur keluar legal **\[Kewajiban Regulasi\]**:

> 1. **Penggunaan MEL (Minimum Equipment List):** Jika komponen yang rusak terdaftar dalam MEL, perbaikannya dapat ditunda secara legal. MEL akan memberikan batas waktu (Kategori A \= waktu spesifik, B \= 3 hari kalender, C \= 10 hari kalender, D \= 120 hari kalender)5. *Sistem harus membuat task baru (Deferred Defect) dengan hitung mundur sesuai kategori MEL tersebut.*  
> 2. **Short-term Escalation:** Mengajukan penundaan jangka pendek berdasar proses internal *Quality Control* yang disetujui DKPPU.  
> 3. **AOG:** Jika komponen kritis (tidak ada di MEL) dan tidak ada toleransi waktu lagi, sistem harus mengunci pesawat (status *Grounded*), mencegah penandatanganan rilis pesawat (*CRS/Release to Service*).

## **D. Kepatuhan AD & SB (Airworthiness Directives & Service Bulletins)**

Manajemen modifikasi adalah fungsi krusial yang selalu diperiksa secara saksama dalam audit DKPPU.

### **16\. Perbedaan Tipe AD (Kewajiban Mutlak)**

*Airworthiness Directives* (AD) dikeluarkan oleh negara pembuat pesawat (misal: EASA untuk ATR) dan diadopsi atau diterbitkan secara independen oleh DKPPU di Indonesia25. AD diterbitkan saat ditemukan kondisi yang tidak aman (*unsafe condition*) pada desain awal. Kepatuhannya **wajib secara hukum** (CASR Part 39).  
Dalam merancang sistem, ada 3 jenis perilaku AD yang harus dikodekan:

> 1. **One-Time AD:** Inspeksi atau penggantian komponen yang hanya dilakukan sekali. Setelah dikerjakan, statusnya di sistem berubah menjadi *Closed* secara permanen.  
> 2. **Recurring AD (Repetitive):** Inspeksi terus-menerus (misalnya: tiap 500 FC periksa retak pada panel). Di sistem, ini beroperasi layaknya *task* AMP biasa dengan hitungan *Next Due*.  
> 3. **Terminating Action:** Bagian resolusi dari AD. Contoh: "Lakukan inspeksi tiap 500 FC (Recurring), SAMPAI panel tersebut diganti dengan material titanium yang baru (Terminating Action)." Sistem Anda harus memiliki fungsi "Pembatalan Relasional": *Jika Task B (Terminating) diselesaikan, hentikan penjadwalan Task A (Recurring)*10.

### **17\. Pelacakan dan Pembuktian Audit AD**

Saat Inspektur DKPPU datang, mereka mengaudit *AD Status Report*.**\[Pilihan Desain & Praktik Industri\]**: Sistem MRO harus menjamin bahwa rekaman eksekusi AD (tanggal pelaksanaan, AFTF saat eksekusi, nomor registrasi mekanik) **bersifat *immutable* (tidak bisa diubah atau dihapus)** setelah ditandatangani secara digital/fisik (*sign-off*). Bukti audit ini biasanya berupa referensi silang ke nomor *Task Card* historis.

### **18\. Service Bulletins (SB) dan Penerapannya**

Berbeda dengan AD, *Service Bulletin* (SB) adalah dokumen perbaikan atau peningkatan (*upgrade*) opsional dari pabrikan (misalnya: modifikasi kursi kargo yang lebih tahan lama). **\[Kewajiban Regulasi\]**: SB **TIDAK WAJIB** dikerjakan, KECUALI jika isi SB tersebut diperintahkan langsung oleh sebuah AD24. Jika Rimbun Air memilih untuk menerapkan SB, departemen *Engineering* akan menerbitkan *Engineering Order* (EO). Sistem MRO Anda harus memiliki fitur untuk menginjeksi *task* SB/EO ini ke dalam *Master Task List* pesawat spesifik agar bisa dijadwalkan layaknya *task* AMP reguler.

### **19\. Laporan Status AD/SB yang Diminta Regulator**

Sistem harus memfasilitasi pembuatan PDF "AD/SB Status Report" dengan kolom standar **\[Praktik Industri Umum\]** sebagai berikut:

* **AD/SB Number:** Nomor unik direktif.  
* **Subject/Description:** Penjelasan singkat permasalahan.  
* **Applicability:** Apakah berlaku untuk pesawat Rimbun Air, atau berlaku berdasarkan Nomor Seri tertentu (MSN).  
* **Method of Compliance (MoC):** Cara spesifik maskapai mematuhinya (misal: "Inspeksi Visual sesuai paragraf 3.A").  
* **Last Done (Date/FH/FC):** Kapan terakhir dilakukan.  
* **Next Due (Date/FH/FC):** Kapan jadwal berikutnya (jika *recurring*).  
* **Status:** "Open", "Closed", atau "Repetitive".

## **E. Implikasi ke Sistem — Persyaratan Desain Database & Aturan Validasi**

Untuk menghindari kesalahan desain perangkat lunak yang berulang di industri MRO, terapkan arsitektur data berikut.

### **20\. Pemodelan Entitas (ERD)**

Diagram Mermaid ini mendemonstrasikan fondasi yang benar. Jangan pernah menggabungkan pelacakan umur pesawat (*Airframe*) dengan komponen yang bisa dicabut (*Rotable Component*) dalam satu baris tabel.

Cuplikan kode  
erDiagram  
    AIRCRAFT ||--o{ COMPONENT\_INSTALLED : has\_installed  
    AIRCRAFT ||--o{ TECH\_LOG : generates\_daily\_utilization  
      
    MASTER\_TASK ||--o{ TASK\_INTERVAL : defines\_limits  
    MASTER\_TASK }o--|| AIRCRAFT\_MODEL : applies\_to\_fleet  
      
    %% AMP Tracking Table (The LD/ND Tracker)  
    AMP\_TRACKER }o--|| MASTER\_TASK : inherits\_rules  
    AMP\_TRACKER }o--|| AIRCRAFT : tracked\_against  
    AMP\_TRACKER }o--|| COMPONENT\_INSTALLED : optionally\_tracked\_against  
      
    WORK\_PACKAGE ||--o{ TASK\_EXECUTION : bundles  
    TASK\_EXECUTION }o--|| AMP\_TRACKER : schedules  
    TASK\_EXECUTION ||--|| EXECUTION\_RECORD : yields\_historical\_data  
      
    AMP\_TRACKER {  
        string track\_id PK  
        string aircraft\_id FK  
        string component\_id FK "Null if airframe task"  
        string task\_number  
        decimal last\_done\_fh  
        date last\_done\_date  
        decimal next\_due\_fh  
        date est\_due\_date "Calculated dynamically via ADU"  
    }

### **21\. Struktur Kolom Laporan LD/ND (Tracker Utama)**

Laporan "LD/ND" (*Last Done / Next Due*) adalah nyawa harian seorang *Maintenance Planner*. Sistem harus mengekspor tabel ini17:

| ATA | Task No | Deskripsi | Interval (WCF) | App | Last Done | Current (FH/FC/Date) | Next Due | Remaining | Est. Due Date | Status |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| 32 | 32-10-01 | MLG Visual Insp. | 500 FH / 6 Mo | PK-RMB | 1.200 FH 1-Jan-26 | 1.600 FH 1-Mei-26 | 1.700 FH 1-Jul-26 | 100 FH 2 Mo | **21-Mei-26** | **DUE** |

*(Catatan Sistem: Est. Due Date mengkalkulasi limit FH dan kalender, lalu menampilkan tanggal terdekat. Status "DUE" menyala kuning jika jarak hari \< 30 hari).*

### **22\. Aturan Validasi (Blocker/Sistem Menolak)**

Rancanglah *logic* penolakan yang keras (bukan sekadar *warning*) pada situasi berikut **\[Pilihan Desain yang didorong Kewajiban Regulasi\]**:

> 1. **Validasi Tanggal Futuristik:** Sistem MENOLAK keras input Last Done Date atau tanggal *Tech Log* penerbangan yang berada di masa depan dari tanggal jam server saat ini.  
> 2. **Validasi Hukum Fisika (Waktu Mundur):** Sistem MENOLAK input Current FH/FC pada catatan penerbangan harian jika nilainya lebih kecil dari angka kumulatif hari sebelumnya. (Pesawat tidak bisa terbang mundur).  
> 3. **Toleransi Ilegal:** Sistem MENOLAK pemberian input toleransi persentase perpanjangan apa pun pada *task* dengan penanda status "LLP", "CMR", atau "AWL"12.  
> 4. **Penandatanganan Ilegal:** Sistem MENOLAK penerbitan CRS (*Certificate of Release to Service*) dari *Check-Pack* jika ada *task* individu di dalamnya yang belum direkam identitas mekanik pelaksananya (lisensi dan stampel digital) serta tindakan yang dilakukan (*Action Taken*)4.

### **23\. Kesalahan Desain Umum Modul Planning MRO**

Belajar dari peranti lunak MRO pasaran yang sering gagal diterapkan pada operator perintis:

> 1. **Meng-hardcode Interval Nama *Check*:** Banyak pengembang non-aviasi mengikat program secara kaku ke struktur "A-Check", "C-Check". Saat ini regulasi, dan MPD ATR modern, sepenuhnya berpusat pada fleksibilitas *Task* individu7. Bangunlah struktur berbasis *Task*, di mana *Check-Pack* hanyalah kanvas kosong yang bisa diisi *Task* ber-interval apa saja secara dinamis.  
> 2. **Mengabaikan Out-of-Phase (OOP):** Banyak *task* memiliki interval eksentrik yang tidak cocok dijatuhkan bersamaan dengan Phase Check reguler (contoh: kalibrasi baterai tiap 3 bulan)17. Sistem harus bisa melacak *task OOP* ini secara independen tanpa memaksanya menunggu jadwal *Phase Check*.  
> 3. **Hanya Mengandalkan Integrasi Manual:** Tracker spreadsheet sangat riskan karena pengguna tunggal harus memindahkan angka *Flight Hours* harian dari kertas kapten pilot ke komputer. Solusi Anda harus mengotomasi ini dengan merelasikan tabel modul *TechLog* secara langsung ke kalkulasi Current FH/FC di modul *Planning*.

## **Yang Perlu Diverifikasi**

*(Tugas Anda sebagai PM adalah memverifikasi data berikut ke sumber primer/tim Rimbun Air)*

> 1. **Nilai Persentase Toleransi AMP Rimbun Air:** Verifikasi ke bagian *Quality Assurance* Rimbun Air: apakah dokumen AMP mereka mengizinkan toleransi 10%, 5%, atau batasan mutlak (e.g., maksimum 50 FH)?7.  
> 2. **Buku MPD ATR Terkini:** Mintalah *Maintenance Planning Document* (MPD) revisi terakhir dari pabrikan ATR untuk mencocokkan format asli interval dasar. Jangan mengandalkan angka 500/1500/10000 FH dari hasil pengamatan singkat.  
> 3. **Logika "Whichever Comes Last" (L):** Meskipun mayoritas *task* menuntut "Whichever Comes First" (WCF), cari tahu apakah ada *task* struktural di AMP Rimbun yang menuntut *Whichever Comes Last* (L)13. Jika ada, algoritma sistem untuk *task* spesifik ini harus memilih *Estimated Due Date* (EDD) yang paling jauh, bukan paling dekat.  
> 4. **Sistem "DGCA":** Konfirmasi bahwa semua referensi standar kepatuhan tim *engineering* merujuk pada regulasi Direktorat Jenderal Perhubungan Udara (DKPPU \- Indonesia). Sering terjadi kebingungan di mana personel merujuk dokumen "DGCA" hasil pencarian internet yang ternyata merupakan milik Directorate General of Civil Aviation India. Untuk Indonesia, pastikan rujukannya berlabel "CASR" (Civil Aviation Safety Regulations)25.

## **Implikasi Utama untuk Sistem yang Anda Bangun**

> 1. **Dashboard Visual Responsif (Traffic Light System):** Kalkulasi Remaining FH/FC/Date sebaiknya diubah menjadi kode warna pada *user interface* (UI) perencana (*planner*).  
   * **Hijau:** Aman (Remaining \> 150 FH atau \> 45 hari).  
   * **Kuning:** Peringatan / Masuk jendela perencanaan (Remaining 50–150 FH atau 15–45 hari).  
   * **Merah:** Kritis / Melewati batas toleransi (Remaining \< 50 FH atau \< 14 hari).  
> 2. **Otomatisasi Hitungan Harian (Batch Processing):** Sistem wajib memiliki *script/cron job* yang berjalan setiap pukul 00:00 (tengah malam) untuk merekonstruksi perhitungan ADU (*Average Daily Utilization*) dan meramalkan ulang *Estimated Due Date* (EDD) seluruh *task*.  
> 3. **Kemampuan Pembuatan Berkas Elektronik Terproteksi:** Fitur pelaporan (Report ADSB, Check-pack Report) bukan sekadar layar antarmuka, tetapi harus bisa diekspor dalam format PDF yang diberi penanda waktu (*timestamp*) statis. Dokumen statis ini akan diarsipkan oleh maskapai dan diperiksa secara acak oleh inspektur DKPPU saat melakukan audit perpanjangan sertifikat operasi27.

#### **Karya yang dikutip**

> 1. Company Maintenance Manual Overview | PDF | Aerospace | Aviation \- Scribd, [https://www.scribd.com/document/442742634/CMM-Issued-6-Rev-5-08-Nov-2019-pdf](https://www.scribd.com/document/442742634/CMM-Issued-6-Rev-5-08-Nov-2019-pdf)  
> 2. Fundamentals of Aircraft Maintenance Programs | PDF | Reliability Engineering \- Scribd, [https://www.scribd.com/document/369857217/Aircraft-Maintenance-Programs](https://www.scribd.com/document/369857217/Aircraft-Maintenance-Programs)  
> 3. 30421002-OJT.pdf \- Repository Poltekbang Surabaya, [https://repo.poltekbangsby.ac.id/2442/1/30421002-OJT.pdf](https://repo.poltekbangsby.ac.id/2442/1/30421002-OJT.pdf)  
> 4. CASR 121 Amdt. 12 Overview | PDF | Government \- Scribd, [https://www.scribd.com/document/566437837/CASR-121-Amdt-12-Certif-Req-and-Supplemental-Air-Carrier-109](https://www.scribd.com/document/566437837/CASR-121-Amdt-12-Certif-Req-and-Supplemental-Air-Carrier-109)  
> 5. Indonesian Civil Aviation Legislation | PDF | Landing Gear | Aircraft \- Scribd, [https://www.scribd.com/presentation/938864309/01-aviation-Legislation-CASR-43-119-121-135](https://www.scribd.com/presentation/938864309/01-aviation-Legislation-CASR-43-119-121-135)  
> 6. Aircraft \- Aviation Maintenance Program Overview \- Scribd, [https://www.scribd.com/document/687274038/CAR-MOE-TPM-notes](https://www.scribd.com/document/687274038/CAR-MOE-TPM-notes)  
> 7. ATR 72-212A Maintenance Manual | PDF | Aviation | Transport \- Scribd, [https://www.scribd.com/document/706080865/119-Vol25-ATR72-212A600-MP-Version1-50-1Nov2017](https://www.scribd.com/document/706080865/119-Vol25-ATR72-212A600-MP-Version1-50-1Nov2017)  
> 8. Aircraft Commerce, [https://www.aircraft-commerce.com/wp-content/uploads/aircraft-commerce-docs/Maintenance/2014/95\_MTCE.pdf](https://www.aircraft-commerce.com/wp-content/uploads/aircraft-commerce-docs/Maintenance/2014/95_MTCE.pdf)  
> 9. t Penerbangan Sipil Bagian 121 (Civil Aviation Safety, [https://www.ukm.my/aaip/wp-content/uploads/2019/02/Peraturan-Direktorat-Jenderal-Nomor-KP-128-Tahun-2016.pdf](https://www.ukm.my/aaip/wp-content/uploads/2019/02/Peraturan-Direktorat-Jenderal-Nomor-KP-128-Tahun-2016.pdf)  
> 10. When does the calendar interval for the next aircraft or component maintenance task start?, [https://www.easa.europa.eu/en/faq/19102](https://www.easa.europa.eu/en/faq/19102)  
> 11. Pemahaman CASR 121 dan Human Factor | PDF \- Scribd, [https://id.scribd.com/document/585007376/Rangkuman-Ujian-Regulasi-Update-1](https://id.scribd.com/document/585007376/Rangkuman-Ujian-Regulasi-Update-1)  
> 12. CMR and Airworthiness Limitations Explained | PDF | Business \- Scribd, [https://www.scribd.com/document/387915173/Certification-Maintenance-Requirements-and-Airworthiness-Limitations-Terminology-Explained-pdf](https://www.scribd.com/document/387915173/Certification-Maintenance-Requirements-and-Airworthiness-Limitations-Terminology-Explained-pdf)  
> 13. Panduan Item Inspeksi Wajib RII | PDF \- Scribd, [https://id.scribd.com/document/715193272/Module-RII-Recurrent](https://id.scribd.com/document/715193272/Module-RII-Recurrent)  
> 14. The Design of Aircraft Landing Gear \[1 & 2\] 2016938903, 9780768099423, 9780768099430, 9780768083453 \- DOKUMEN.PUB, [https://dokumen.pub/the-design-of-aircraft-landing-gear-1-amp-2-2016938903-9780768099423-9780768099430-9780768083453.html](https://dokumen.pub/the-design-of-aircraft-landing-gear-1-amp-2-2016938903-9780768099423-9780768099430-9780768083453.html)  
> 15. Aviation crossroads \- AviTrader, [https://avitrader.com/wp-content/uploads/archive/weekly/AviTrader\_Weekly\_Headline\_News\_2015-12-07.pdf](https://avitrader.com/wp-content/uploads/archive/weekly/AviTrader_Weekly_Headline_News_2015-12-07.pdf)  
> 16. AeroTrac Premium Aircraft Planning Highres | PDF | Business Process \- Scribd, [https://www.scribd.com/document/342198416/AeroTrac-Premium-Aircraft-Planning-Highres](https://www.scribd.com/document/342198416/AeroTrac-Premium-Aircraft-Planning-Highres)  
> 17. What are OOPs, SRT, SSI's, CMR when it comes to performing a Last Done Next Due (LDND) review? \- ialta.aero, [https://ialta.aero/last-done-next-due-ldnd-review](https://ialta.aero/last-done-next-due-ldnd-review)  
> 18. Aircraft Planning and Maintenance \- Tracware, [https://tracware.com/wp-content/uploads/2023/03/Tracware-Aircraft-Maintenance-Brochure.pdf](https://tracware.com/wp-content/uploads/2023/03/Tracware-Aircraft-Maintenance-Brochure.pdf)  
> 19. ECTM Overview and Data Management | PDF | Intelligence Analysis | Email \- Scribd, [https://www.scribd.com/document/211905132/CAMP-Engine-Condition-Trend-Monitoring-pdf](https://www.scribd.com/document/211905132/CAMP-Engine-Condition-Trend-Monitoring-pdf)  
> 20. (PDF) Engine Condition Trend Monitoring (ECTM) Analysis in Aircraft Engines: Pratt & Whitney Engines for Preventive Maintenance \- ResearchGate, [https://www.researchgate.net/publication/363290884\_Engine\_Condition\_Trend\_Monitoring\_ECTM\_Analysis\_in\_Aircraft\_Engines\_Pratt\_Whitney\_Engines\_for\_Preventive\_Maintenance](https://www.researchgate.net/publication/363290884_Engine_Condition_Trend_Monitoring_ECTM_Analysis_in_Aircraft_Engines_Pratt_Whitney_Engines_for_Preventive_Maintenance)  
> 21. Maintaining PW100 engine family values while being cost-effective, [https://www.aviationbusinessnews.com/mro/pw100-engine-maintenance/](https://www.aviationbusinessnews.com/mro/pw100-engine-maintenance/)  
> 22. StandardAero Partners With Firefly in Multi-Year Agreement for PW127M Engine Maintenance on ATR 72-500 Fleet, [https://standardaero.com/standardaero-partners-with-firefly-in-multi-year-agreement-for-pw127m-engine-maintenance-on-atr-72-500-fleet/](https://standardaero.com/standardaero-partners-with-firefly-in-multi-year-agreement-for-pw127m-engine-maintenance-on-atr-72-500-fleet/)  
> 23. EASA vs FAA: Airworthiness Limitations Explained | PDF | Transport | Aviation \- Scribd, [https://www.scribd.com/document/818261903/Airworthiness-Limitations-EASA-vs-FAA-LinkedIn](https://www.scribd.com/document/818261903/Airworthiness-Limitations-EASA-vs-FAA-LinkedIn)  
> 24. Sect 3 Maintenance Operation Procedures \- Academia.edu, [https://www.academia.edu/33047765/Sect\_3\_Maintenance\_Operation\_Procedures](https://www.academia.edu/33047765/Sect_3_Maintenance_Operation_Procedures)  
> 25. Indonesia CASR Part 39 Airworthiness Directives | PDF | Safety | Regulatory Compliance, [https://www.scribd.com/document/358336054/CASR-Part-39-Amdt-2-Airworthiness-Directives](https://www.scribd.com/document/358336054/CASR-Part-39-Amdt-2-Airworthiness-Directives)  
> 26. CASR Part 39: Airworthiness Directives Summary | PDF \- Scribd, [https://www.scribd.com/document/874606793/Summary-CASR-Part-39-English](https://www.scribd.com/document/874606793/Summary-CASR-Part-39-English)  
> 27. PERATURAN DIREKTUR JENDERAL PERHUBUNGAN UDARA NOMOR, [https://jdih.dephub.go.id/api/media?data=Clm7Ce3Gu7gH5OQLbudL1f4fVE0pE5xKR8Rl6Vkdfhgr4UoonTdDbjF8mz6RhNJA7Z8QfpGi6JLP648gwAKLkGXJ4ua5fcbmpho8n1hIR8fZO59iue5Stgt6IIAu13zGJFi96SqEYfcYHJ5LDENrR8FSkMBFJl6dXSBOfJLhvQcPp15nKMIKZbnwcnN4dGz0HGzw2z5LmweYWCXt79IeouOkCZok](https://jdih.dephub.go.id/api/media?data=Clm7Ce3Gu7gH5OQLbudL1f4fVE0pE5xKR8Rl6Vkdfhgr4UoonTdDbjF8mz6RhNJA7Z8QfpGi6JLP648gwAKLkGXJ4ua5fcbmpho8n1hIR8fZO59iue5Stgt6IIAu13zGJFi96SqEYfcYHJ5LDENrR8FSkMBFJl6dXSBOfJLhvQcPp15nKMIKZbnwcnN4dGz0HGzw2z5LmweYWCXt79IeouOkCZok)  
> 28. Inspector Training System Overview | PDF | Professional Certification \- Scribd, [https://www.scribd.com/document/357568448/Si-8900-1-3-Inspector-Training-System](https://www.scribd.com/document/357568448/Si-8900-1-3-Inspector-Training-System)

[image1]: <data:image/png;base64,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>

[image2]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAMYAAAAYCAYAAAChr4ICAAAFkklEQVR4Xu2aaah1UxjHH1OmEurN7KrXlCFjhqT7EhKS8YPX9El8UMb4IBSZ50IJvafMIhRfhMJXEUmmuEhkjtcHs+d/n/W/+7nPXWufs8/pnnM+rF893b3+a+291/6f/ey91tpXpFKpVCqVSqVSqVSWl2s0/o5iYFOxNkfGihZ+0zhPY2eNQzVWa/y0qIWxo8a7Gv9p3K+x5eLqBVD3j8Zc2p4k62r8EMXAY2LX9L7G+qGuHzMa34ntf4OY/x545v1o88x7Ow08IdaftzROC3VkVuNzjb80LpOyf6N4nGVvsQPi5sVfRA7WrU1/uyQG92XgR9xoUYumH+SCVF7hNLT5ReMsp6Hdt648Ln4U6x8SvOTZuRr/aqx0Gtq+4sptXC+WFIS/EaFn3o/oGZgWzzzo54Fpe0ONtzXuaarngX9/uDITaR2njepxka00ThE7GW/cHFeJnfxNsTZdEwPJgMDF77O4ep6e2JODrKfxgcYzTuvJUmPQrtTn5eQKsevAzVs6/2eytA4/dNRynCPW7qBUxpsg/j49Mc+8H9EzMC2eESREPD/uQa/hTQz/7nTaTmL+Xei0UTwemGh8jmETo41LxNqcHPSzk05K/YOGG2kStCVGrr8PJ20m6JHcvhdrHODKbZ7RD3obmZRnGOaUblxoHEm8kMpbNNXz0D+S82lQjwcmd5LIciQGxuhow1crmU06KfUP2kdRHBOlxNhLTMfQ03Nt0h8Iugfeos2fqYybf+OmeoE2z+gHvY1MyrNjpf13xDyC27k29A+M4nEnSp3xDJsYv2pcqvFqKu8e6hF7Og1gGAEdw4Bt03auf9D6LRosF6XEwAID9O+DjiEY9NeC7lkj1gaT5UeT9kgqY+gL6EfJM/rRzzM/xIrgXEi8LtEPvBEwJ4h94lAe1w5K/aZ/YBSPO1HqjIeJcVSsaAHjXg+fiITn9ckCYDT07TR2S9u5/pX0cVBKjPPF9DjJvTzpnwTdg3lD7pq8Rj9KnrFd7jiAOrwtgRWwmUJgNWwHje3FknQbja1tt74cLEv7dHPSOD8q9Zv+gVE87kSpMx4mxjGxoiM4xtVpG5NylPFq9HgDOWHM9Q/a71F0PCc2LBk0ulBKjFVielzKvTLpLwXdw9UXrEJ5eP24IelHyTP6QW8j/TxbbvBpYK3G6RpfaRwv1qeLUn3pt6Z/YFXaHsbjTpQ64xkmMbAcF8ExMDwAHAfv31TPc3jSSal/0Oai6NhX44wO0YVSYnD8iyGkBw8D6L2ge+4Wa/Ne0Hn9h7hyybO5VG6bY8xFccw8pPGlxhGpjD5xMaH0W9M/MIrHnSh1xsPEwCRqEJ4Ua48nnAfaTWmbqwhxhQVr774/pf5Bi2vg46KUGCDXX9wMuWv17CfW5sOg83grXTkeh57Rj7iKQwbxDEOS1zvGsOCafD8/TeW4KkX/yLAedyJ3kggT47hYkcDHJIw/yXUat7kywJIjjrF5Km+g8bPGgwstjMc1vnFltMn1DxrWvSdB18T4OqN9ofFx0HL7Rq3NM/oBb+NxwCQ9O1Hs/JukMibeSIR3Flo0c6UznYZ28O8pp0VPQM7jzuBkt2q8KM1J1kjzNCco4xXPFQWYj/2Odm12SXW3OA1A40e9e1MZ+3ow3IK+WSq/kcr+TYM2WJl5OZWRWGiHZB03mPjdIc1/Ajwt9jEKOtlV7DV/YyrvIdaWZVCaO82KrRrxeFh6xLH8x1F65v2IngF65r2dhGcEE3XOnzDBxz2Vm+/AP1wP7lGASXb0aRCPpxqsTz+rcZI0b4oct4s9BWdiheMwsdULfKBqazctYIL5vNiTsiunij20TogVDu9HCbQZxNtxgaXgnsZd0r5kjA+C94n1vfR/YGAUjyuVSqVSqVQqlUqlUqlUKpVKpTJ9/A9CyBCz8Jgx8gAAAABJRU5ErkJggg==>

[image3]: <data:image/png;base64,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>

[image4]: <data:image/png;base64,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>

[image5]: <data:image/png;base64,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>

[image6]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAASQAAAAYCAYAAABTNoCOAAAJ0UlEQVR4Xu2bCYwmRRWAH6AIovHgEjxmZUFu0MihERyB4LUYFAFRjgASxIsjKJ7gruACq0gwikaOXYNyqECQDcgaYAAlXAZQQpCgjoJyiyDeB9SXqrf9/jdV3TPOP//M7NaXvMxfr6q7q6urX733qkekUqlUKpVKpVKpVCqVgbB6kEOD7B/kFUb/ZvO7BMes55XTxHZBPh7ktU6/kyvPNF7oFZWBsqZXzFZeE+SpICcFOSbIkUE+FuSjSSwfCvK/IP8JcneQNXqrl3N5kGeC3BhknqvzfCvI0xLbq9AfdP9w+hxrS6x7TGK/Nw/yTon9XCfVdUHbHO8P8k9p7qWNR4I8KU1f/y3xPv4icbxU/z09wLBakEUS6y+S2P9dgpwS5Jog5wX5zvLWM4vfSvvz6TfMV67FmM0kWEiu90rDHhLn80NBvhRk697q5ZwZ5L9BRoO8tLdqDEMS59kgx//BIDd7ZT/5hPS+9FYeNu2Ok95V+rkS26xidIAObwWw2kzYE5rqIjrRDvMVEq+RG/C/S9Qf5CsS+rC6ONsrAr8OstiUeQg/MuUSf5TyNennA06nBhV5jquDIYl1M9UgwU1Svud+80mJ13q9r5gm6AsLGn9LBml+kH1NWReuvYwOA/XnIAcYHW0wYF3o/BkEU36tsySu/hcHOT/Id5P8IchbTbtcJ66WXg9oIxnbDi8Dw9CFGiTCrhx4G5a1pHtwvint9YCR9WHd82TscZQxUl20GSRg9VODDXhEtP+90XmorwYpsmqQ73vlNPJhieEq918ySI8G+ZspL5PY/l6jW5J0doEnChnPuHa9B/3kM9JrXPsOg+Vh1faD6wcLTk4CvGSELXc21csZz2B1GSTCRbwyRVel440uR9e1Wa08/wpyl9O9W8aXJ+kySNTtln4T8lLGsLeBFzuTDdLPpP2eVwbaDNIvpHd8cAAo/9XockblwKQrRQBK7tgVilxORW96V6dTyN9QXmp0Cno8pTZKBumW9BdjQE5I0f682OhydD2oG7xC4jGflxhCsRq8ure6lZxBIi/3/PT7vUG2TL+/JrEtxq4NDFfJIK0vccwWSuM5HBXkG0E+pY0cLwlymURD+HWj51yEROSuzpG4OfBtie3buE6aex6SeAzjl4MF7BKJBp+cpYe85RlB3iFx/L8c5C2pjmfBWNLnmRKyKdx/ySB5dO7aFIjqLMNJ9yun99hj95QY6aij4GEBv03is5/r6raR6AF9ReIiuK3EeYRXCoz/giAXpPKUQ6KQzvqOAvkgvXEsO39tzoNJiO4HRqeg78ojqUFih4kXY/cgV0hjkCy8wLQlVJgMnw7yIqcbknhu8kofSDqMcM5I51CDREJyTpAdUlkNkkXHM1c3Xuj/zhJDQc5F6K0wMdHZEHEf6b0XXnydzJzrWInnIhn/WWnydG9LbXKMSGyDEdsw6ch9cA6bmKXNn6QZ8ytl7LhisGnHS8hY0gftH2PJwkaZfndBonkiMhnoU5dBwjNmPrMBc7jRM2Y6Fyw6d9gUaUOPtSkF8p32fLyrPA+r89fUBUjPhcHkN/OBOUp/fpd0A+F2ab/Y/UHuk+ZGbF4Hq4nuQqNT0JOrakMNEqs8VprzMYA5g8RLRdulvmIC7Cj5e2U3BL0PPckB4Hp3oQaJFeaLEncRKeeMjp8Qk8FPQAUdRsCWGT8LOnZZFRYVey5yam1cK7E9xkw5JOnsQoRH5MMP2rwso2O8dSdtY1MH1I/HIA0V5FVBXhnk5Uk2kLF9mCj06ade6cDLZ/Gg7T1Gv2nS2TEHjGRO78m1wav3OnZv2eFT8IRos5/RAWkcPdYuZvAFGXveKYMLjXplgpVMwyNCDk1k6os7P5V/mMoW9IQCbXSFbB7atiWClZJnxku6yCulmRwYFEuXsVZyIRvhS84gsXlA2418RQY8hzYYd39duEYaPS8dv1lYWOlUeLa3pjbgDVIXIzL2PvAu0Z1odAo7SouD/EZiG8bcgm6J01moH49BGiT06UavLEDYSXs+KQEML2U/5rpo2lxTjtyx6nXlOEKid6oeE/lZCwZp1OkUoorSefuKvog5r4MY0ncCHclf1WsOKbc1jv5gr3T8PwaJ3buubzV8vxX0msuxYHSps1uyQD9K57LkDBJhRs4gafjxLl+R4ate4SgZEXJPqh9Ov98X5D1O3pDaQOlcJUYkth8yOlZddNYgsSlCKID+x9IkbTczbQAd4V8J6mezQXqjxPZ2jH0Z1JsadXpP7lhdfDzqSJAnPDf9xkBZMEg2/LMMzCAtkXgh7xkAk4okaA7tHG4wv32oA+jX9UqHGqQP+ooCxOu0H3F6j//uB9aTmKsqwXm9GzsZD6kN2j4t8TOGEoSRPmzxlIyIGgDA/eY3H4+2UTpXCUIV2mv+CEiAorOhIOVTTVl1vj/oznQ6C/VdBokFk2T7RGQy0KdcTpOFhLqrjI7FCR2CkQYtW/gmCR1J/jZyxzLHre7oVLZhJe86Oj5dsGCQ+OQgBxsl/lpTgt6Uj/FhF4nJTQ8vkbqdoDdoUUPThbbz7mMb2uc5Tq/wVTTJeA/GpQ08P/+xJG5zl+sMEzVI/IsI7X1y19KV1ISSEfGTkPK1pqwQPiokxnPnKqGr7pDRqYekOQvyF/6c+tnDFhJzOsNJj47cWwnquwzSoKFPOW9e5wMfPSps2KCz4/GEK8P5Sae7XCX8ucB7SNoGQ6WQr0X3Een1iB6X3hyXhfyuv9aUoB32oYrC9vhPTHkTie3Vwivo5qXfe0t80d7eVI+Bicv29x0Sj2V35jQZv6c0LPE4PDg8AMAI/Vx6P1GwsAK0oSGqrty629EGLvDp0owjDxudTSKW4GXUkFDvm7wCIWWbobKoQSJs4EVnV4XdHHJIFr03DBAeDTsrami53nnS/MsOz6Vre508HAaT9jdL3D1aKM2/lPCiMQ5AmW+WMCZbSVzkWNCWBblU4ndm+ikE+Y3F0vvpAufRXaBfSrMLOp3QJ4wnfeJZ8Y6w5a7vBZ9MjEqc06Djj5BMV9g4ILpgLEBTB7x3JdaRuFmk5+NDYGAMdZFgHhKO42WzW0b+8AUS81j0id1MjBEGk9QBuSW9F7w7+8kH98q7Qz1e25SOP0ajK3FKWEanuJFDXJ2FfBITbFjK/+/WbzAaeDW4+se5Ogsvw+u8sgATiwf6OV8xheBlYlwWBNne1bVhPSTuj2fZ9iEnhojFh29PBgleNQsF11d4sVZ05kqcnwjRQIk3SdygyEUq/YCFim+VdAcT2GmsTBNsJ6+IsACoQapUKrOE8fxf3WzkcqkGqVKZVZCr6QpLZxts2WsOQaVSqcwCJru1W6lUKpVKpVKpVCqVSqWysvEsX5fpIvfNffEAAAAASUVORK5CYII=>

[image7]: <data:image/png;base64,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>