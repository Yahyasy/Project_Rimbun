# **Analisis Kebutuhan Sistem PPC Rimbun Air**

[https://gemini.google.com/app/e62e03b9020612ae](https://gemini.google.com/app/e62e03b9020612ae)

*User prompt: Tolong ekstrak dan analisa hasil in depth interview dengan staff PPC untuk project rimbun ini*

## **Response: date: 2026-07-29 type: knowledge tags: \[mro, ppc, rimbun-air, requirements, idi-analysis\]**

Halo\! Saya mengerti bahwa merancang sistem aviasi dari nol tanpa latar belakang di bidang ini adalah tantangan yang cukup besar, terutama dengan banyaknya istilah teknis dan regulasi ketat yang menyertainya. Namun, Anda sudah mengambil langkah yang tepat dengan melakukan riset dan wawancara mendalam (IDI) dengan tim di lapangan.

Berikut adalah ekstraksi dan analisis dari transkrip wawancara dengan staf PPC (Production Planning and Control) Rimbun Air. Analisis ini saya susun untuk membantu Anda memetakan kebutuhan sistem dari kacamata *user* di lapangan.

### **1\. Peran dan Tantangan Utama PPC Rimbun Air**

Dari wawancara, terlihat jelas bahwa fungsi utama staf PPC di Rimbun Air adalah **koordinasi dan pemantauan (monitoring)**.

> * Mereka bertanggung jawab memastikan dokumen dan jadwal *maintenance* tidak *expired*.  
> * Ada kendala operasional eksternal, seperti alat yang harus dikalibrasi tetapi tertunda karena vendor meminta pembayaran di muka.  
> * Mereka bekerja sangat bergantung pada dokumen panduan fisik, seperti *Maintenance Program* (MP), yang berfungsi sebagai "riwayat" atau panduan utama perawatan pesawat.

### **2\. Alur Kerja (Siklus Hidup Work Order) Saat Ini**

Saat ini, proses pembuatan hingga penutupan Work Order (WO) dilakukan secara manual dan memakan banyak waktu. Berikut adalah alur kerjanya:

> 1. **Referensi Dokumen:** PPC mengambil data dari *Maintenance Program* yang diturunkan dari pabrikan (seperti ATR) atau regulasi lokal (DGCA).  
> 2. **Pembuatan WO (Pain Point Utama):** Staf harus melakukan *copy-paste* instruksi dari dokumen pabrikan (PDF/Word) ke dalam *template* *task card* atau WO standar milik perusahaan. Proses ini diakui sangat memakan waktu.  
> 3. **Distribusi ke Lapangan:** WO yang sudah dicetak diserahkan secara fisik kepada *Engineer*.  
> 4. **Eksekusi & Sign-off:** *Engineer* melakukan pekerjaan sesuai WO (misalnya *A-Check*, *C-Check*, atau *Daily Check*) dan memberikan tanda tangan basah (serta cap/stempel) pada dokumen fisik tersebut.  
> 5. **Verifikasi Internal:** Dokumen fisik dikembalikan ke PPC untuk direviu.  
> 6. **Persetujuan Akhir (QC/Inspector):** Dokumen kemudian diserahkan kepada Inspektor (misalnya Pak Heri) untuk diverifikasi dan ditandatangani.

### **3\. Masalah pada Sistem *Existing* (MSS)**

Rimbun Air saat ini menggunakan sistem bernama "MSS" yang dibangun secara internal oleh "Mas Bobi".

> * Sistem ini pada awalnya dirancang khusus untuk kebutuhan *Store/Inventory*, bukan untuk *Maintenance Planning*.  
> * Sistem tersebut dirasa memiliki banyak *bug* atau ketidakcocokan ketika dipaksakan untuk mengakomodasi alur kerja *maintenance* yang kompleks.  
> * Penyimpanan dokumen manual (seperti *Aircraft Maintenance Manual* / AMM dan *Illustrated Parts Catalog* / IPC) saat ini masih mengandalkan Google Drive, yang diunduh secara manual oleh staf.

### **4\. Kebutuhan Sistem Utama (Fitur yang Diharapkan User)**

| Modul/Fitur | Kondisi Saat Ini (Manual) | Ekspektasi Sistem Baru (*Requirement*) |
| :---- | :---- | :---- |
| **LD/ND (Last Done Next Due) Dashboard** | Dilakukan manual atau terbatas, tidak ada visibilitas instan. | Sistem bisa menampilkan *remaining hours/cycles* (misal: sisa 100 jam) secara otomatis agar PPC bisa segera merencanakan *maintenance* (menurunkan WO). |
| **Work Order & Task Card Generator** | *Copy-paste* manual dari dokumen pabrikan ke MS Word/Excel. | Sistem memiliki *template* bawaan atau *master data* sehingga WO bisa langsung di-*generate* (di-deploy) ke *Engineer* tanpa perlu *copy-paste* berulang. |
| **Manajemen Dokumen (Manuals)** | Diunduh dari Google Drive atau portal pabrikan secara terpisah. | Sistem idealnya memiliki repositori terpusat (*library*) untuk AMM, IPC, dan *Maintenance Program* yang mudah diakses. |
| **Tracking Tool & Kalibrasi** | Dilakukan secara terpisah, sering terhambat isu koordinasi vendor. | Sistem memberikan peringatan (*alert*) sebelum alat ukur atau lisensi mendekati tanggal kedaluwarsa. |

### **5\. Rekomendasi Desain Berdasarkan Praktik Industri**

Mengingat Anda sedang membangun modul *Maintenance Program & Planning* serta *Production & Execution*:

> * **Hierarki Data yang Harus Anda Bangun:** Pastikan sistem Anda membedakan antara *Maintenance Program* (sebagai kamus tugas master), *Work Package/Check-pack* (kumpulan tugas untuk satu jadwal masuk hanggar), dan *Work Order/Task Card* (dokumen kerja aktual yang dieksekusi).  
> * **Transisi Digital:** Jangan langsung menghapus tanda tangan basah jika regulasi (DKPPU) atau kesiapan tim belum memadai. Bangun sistem yang bisa mencetak WO secara otomatis dengan QR code/Barcode, lalu biarkan *Engineer* menandatangani fisiknya, yang kemudian di-scan kembali ke dalam sistem untuk ditutup (*closed*).

Dari analisis di atas, tantangan terbesar staf PPC saat ini adalah waktu yang terbuang untuk administrasi manual (*copy-paste* dokumen) dan kurangnya *dashboard* peringatan jatuh tempo (LD/ND).

Untuk memastikan modul *LD/ND Dashboard* ini nanti benar-benar bisa dipakai oleh mereka, metrik utama apa (misalnya *Flight Hours*, *Flight Cycles*, atau Kalender) yang ingin Anda prioritaskan untuk dihitung pertama kali di dalam sistem?

---

*User prompt: Apakah ada proses bisnis yang masih belum clear dan harus saya tanyakan lagi?*

Response: Sebagai panduan untuk menyusun struktur dokumen *requirements* dan memetakan *user flow* yang solid di Figma atau Taiga nanti, memang ada beberapa area abu-abu dari wawancara tersebut yang berpotensi menjadi *edge cases* saat sistem dikembangkan.

Dari ekstraksi data sebelumnya, alur kerja utamanya (*happy path*) sudah cukup terlihat. Namun, ada beberapa proses bisnis kritikal yang belum *clear* dan sangat perlu Anda tanyakan kembali kepada tim PPC atau *stakeholder* terkait:

### **1\. Sumber Data *Utilization* (Flight Hours & Cycles)**

Sistem diharapkan bisa memberikan peringatan atau menampilkan dasbor *Last Done Next Due* (LD/ND). Namun, dasbor ini butuh data aktual pesawat yang terus berjalan.

> * **Yang harus ditanyakan:** Siapa yang bertanggung jawab memasukkan data *utilization* harian (jam terbang dan jumlah pendaratan) ke dalam sistem? Apakah data ini diambil dari *Technical Logbook* yang diisi pilot? Seberapa sering data ini di-*update* (setiap selesai terbang, harian, atau mingguan)?

### **2\. Penanganan *Non-Routine Task* (*Defect/Finding*)**

Wawancara lebih banyak membahas tentang menurunkan instruksi perawatan rutin (*Maintenance Program*) menjadi Work Order (WO). Namun, di lapangan, hal tak terduga sering terjadi.

> * **Yang harus ditanyakan:** Bagaimana alur kerjanya jika saat melakukan *A-Check* (perawatan rutin), *engineer* menemukan kerusakan lain yang tidak ada di *Task Card*? Bagaimana proses pembuatan *Non-Routine Task Card* atau *Defect Report*\-nya? Siapa yang berhak menyetujui penambahan pekerjaan ini?

### **3\. Ketersediaan Material dan Suku Cadang (*Store/Inventory*)**

Sistem lama (MSS) awalnya dibuat untuk *Store*. Di sisi lain, sebuah WO *maintenance* hampir selalu membutuhkan *parts* atau *consumables* (seperti pelumas, *O-ring*, dll).

> * **Yang harus ditanyakan:** Sebelum PPC merilis WO ke *engineer* di lapangan, bagaimana cara PPC memastikan bahwa material atau *spare part* yang dibutuhkan tersedia di gudang? Apakah sistem PPC baru ini harus terintegrasi langsung dengan sistem MSS yang lama, atau akan ada modul *Inventory* baru?

### **4\. Alur Penolakan (*Rejection / Rework Flow*)**

Kita tahu bahwa dokumen WO fisik akan diserahkan ke Inspector/QC untuk ditandatangani di akhir proses.

> * **Yang harus ditanyakan:** Bagaimana *user flow* di sistem jika Inspector menolak hasil kerja *engineer* karena tidak sesuai standar? Apakah WO tersebut statusnya dikembalikan (*bounce back*)? Bagaimana cara melacak perbaikan (*rework*) dari penolakan tersebut?

### **5\. Strategi Migrasi Data Historis**

Pesawat memiliki ribuan dokumen riwayat perawatan.

> * **Yang harus ditanyakan:** Saat sistem ini *live*, bagaimana cara memindahkan data status komponen (*component historis*) yang saat ini masih berupa kertas atau tersimpan manual ke dalam sistem baru? Apakah tim PPC yang akan melakukan *data entry* secara bertahap, atau butuh fitur *bulk import* khusus?

Memetakan *edge cases* seperti ini di awal akan sangat meminimalisir perubahan struktur *database* atau rombakan *journey* saat *development* sudah berjalan di Jira.

Dari kelima poin *blank spot* di atas, area mana yang menurut Anda paling berisiko menghambat operasional jika tidak segera didefinisikan alurnya?

---

*User prompt: Besok saya akan wawancara inspektor, dimana yang saya tau inspektor ini nanti akan menerima dokumen dari PPC ini untuk di cek kembali*

Response: Langkah yang sangat tepat. Mewawancarai Inspektor adalah tahapan krusial untuk memetakan *user journey* secara menyeluruh (*end-to-end*). Dalam dunia aviasi, Inspektor atau *Quality Control* (QC) bertindak sebagai "gawang terakhir"; mereka yang menentukan apakah pekerjaan sudah sesuai standar dan pesawat aman untuk dirilis kembali (*Release to Service*).

Untuk menyusun *Product Requirement Document* (PRD) yang komprehensif nantinya, Anda perlu menggali bagaimana Inspektor berinteraksi dengan *output* yang dihasilkan oleh tim PPC dan *Engineer*.

Berikut adalah panduan pertanyaan *In-Depth Interview* (IDI) yang bisa Anda gunakan besok, terbagi dalam beberapa fokus area pengumpulan data:

### **1\. Membedah Alur Verifikasi (Current Journey)**

Fokus di sini adalah memahami interaksi fisik dan komunikasi yang terjadi saat ini.

> * "Bagaimana persisnya proses serah terima dokumen *Work Order* (WO) atau *Task Card* dari tim PPC/Engineer ke meja Bapak/Ibu saat ini?"  
> * "Saat mereviu dokumen tersebut, apa saja **komponen spesifik** yang wajib Bapak/Ibu periksa? (Misalnya: referensi *manual* pabrikan, kesesuaian *part number*, validitas stempel *engineer*, atau catatan temuan/defect)."  
> * "Berapa lama rata-rata waktu yang dihabiskan untuk memverifikasi satu paket dokumen pemeliharaan (satu *Work Package*)?"

### **2\. Menggali *Edge Cases* dan Alur Penolakan (*Rejection*)**

Sebuah sistem yang baik harus bisa menangani skenario ketika segala sesuatunya tidak berjalan mulus.

> * "Pernahkah Bapak/Ibu menolak atau mengembalikan dokumen WO dari *Engineer* atau PPC? Biasanya apa penyebab utamanya (misal: tulisan *engineer* tidak terbaca, referensi salah, atau prosedur terlewat)?"  
> * "Jika ada penolakan, bagaimana **alur pengembalian dan perbaikannya (*rework*)** saat ini? Apakah Bapak/Ibu mencoret langsung di kertas tersebut atau ada form laporan (*rejection note*) terpisah?"  
> * "Bagaimana Bapak/Ibu melacak dokumen yang sedang dikembalikan agar tidak hilang atau terlupa?"

### **3\. Aspek Regulasi dan Kepatuhan (*Compliance*)**

Karena ini melibatkan regulasi penerbangan (DKPPU/DGCA), keabsahan data sangat krusial.

> * "Terkait peralihan ke sistem digital, sejauh yang Bapak/Ibu ketahui, apakah otoritas penerbangan sudah mengizinkan penggunaan **Tanda Tangan Elektronik (*E-Signature*)** untuk *sign-off* dokumen di Rimbun Air, ataukah kita masih wajib mencetak WO untuk dibubuhi cap dan tanda tangan basah?"  
> * "Saat *engineer* menggunakan alat ukur khusus (misalnya *torque wrench*), bagaimana cara Bapak/Ibu memverifikasi bahwa alat tersebut status kalibrasinya masih valid saat pekerjaan dilakukan?"

### **4\. Ekspektasi Sistem dan *Acceptance Criteria***

Pertanyaan ini untuk memvalidasi fitur apa yang sebenarnya paling berdampak (*high impact*) bagi mereka.

> * "Apa *pain point* (kendala) terbesar yang paling membuat frustrasi atau menyita waktu Bapak/Ibu saat memverifikasi dokumen saat ini?"  
> * "Jika nanti Bapak/Ibu memiliki *dashboard* sendiri di sistem yang baru, **3 informasi utama** apa yang ingin langsung Bapak/Ibu lihat di layar utama saat pertama kali *login*?"

Dengan menanyakan hal-hal di atas, Anda akan mendapatkan batasan yang jelas mengenai apa yang boleh dan tidak boleh dilakukan oleh sistem berdasarkan kacamata *Quality Control*.

Setelah mendapatkan data *requirements* dari tim PPC hari ini dan tim Inspektor besok, apakah Anda berencana untuk langsung menuangkan alur tersebut ke dalam bentuk *flowchart/user journey map* visual terlebih dahulu, atau langsung menyusun struktur *database* dan tiket pekerjaannya?

---

*User prompt: Apa yang perlu saya pelajari sebelum bertemu staff inspector besok*

Response: Sebagai persiapan untuk wawancara mendalam (IDI) dengan staf Inspektor besok, Anda perlu membekali diri dengan pemahaman dasar mengenai domain aviasi dan menyusun strategi riset UX. Inspektor memiliki *mental model* yang sangat berbeda dengan staf PPC; jika PPC fokus pada kecepatan dan jadwal, Inspektor sangat berorientasi pada kepatuhan (*compliance*) dan kualitas.

Berikut adalah hal-hal krusial yang perlu Anda pelajari dan persiapkan sebelum bertemu mereka:

### **1\. Pahami Kosakata dan Konsep Dasar Inspeksi Aviasi**

Sangat penting untuk berbicara dengan "bahasa" mereka agar wawancara berjalan lancar dan Anda bisa langsung menggali *pain points* tanpa harus banyak bertanya soal definisi. Pelajari istilah-istilah berikut:

> * **Airworthiness (Kelaikudaraan):** Kondisi di mana pesawat memenuhi standar keselamatan dan layak untuk terbang. Ini adalah tujuan utama seorang Inspektor.  
> * **CRS (Certificate of Release to Service):** Dokumen legal atau pernyataan bahwa *maintenance* telah selesai dilakukan sesuai standar dan pesawat diizinkan kembali beroperasi. Inspektor adalah pihak yang mengeluarkan atau menandatangani CRS ini.  
> * **Quality Control (QC) vs Quality Assurance (QA):** Di MRO (Maintenance, Repair, and Overhaul), Inspektor biasanya berada di ranah QC, yaitu mengecek hasil kerja fisik (pesawat dan dokumen WO) secara langsung.  
> * **Stamp/Cap Inspektor:** Setiap Inspektor memiliki stempel unik bernomor yang sifatnya sangat rahasia dan mengikat secara hukum. Mereka menggunakannya untuk melakukan *sign-off* pada *Task Card*.

### **2\. Susun Draft *User Journey* Awal (Asumsi)**

Berdasarkan wawancara dengan PPC sebelumnya, Anda sudah memiliki potongan gambar mengenai alur kerja.

> * Gambarkan *user journey* kasar di atas kertas atau buat *lo-fi wireframe* aliran dokumen dari PPC \-\> Engineer \-\> Inspektor.  
> * Gunakan draft ini saat wawancara besok sebagai alat validasi. Anda bisa menunjukkan draft tersebut dan bertanya, *"Pak/Bu, pemahaman saya alurnya seperti ini. Di titik mana biasanya dokumen tertahan lama, atau di mana Bapak/Ibu harus melakukan pengecekan ulang?"* Memvisualisasikan alur akan sangat membantu memancing *feedback* yang detail.

### **3\. Siapkan Kerangka Penggalian *Acceptance Criteria***

Sistem yang akan dibangun nantinya harus dipecah menjadi tiket-tiket pengembangan. Saat mewawancarai Inspektor, arahkan pertanyaan agar jawabannya bisa langsung Anda terjemahkan menjadi struktur *Product Requirement Document* (PRD) dan *Acceptance Criteria* yang solid.

> * **Validasi Input:** Pelajari cara menanyakan batasan data. Misalnya, *"Agar dokumen ini bisa di-approve, field apa saja yang mutlak tidak boleh kosong?"*  
> * **Alur Error/Penolakan:** Gali bagaimana *flow* ketika Inspektor menemukan kesalahan (tulisan *engineer* salah, *part* tidak sesuai). Ini krusial untuk mendefinisikan *edge cases* dalam PRD Anda.  
> * **Hak Akses (*Role-Based Access Control*):** Pelajari cara memetakan otorisasi. Tanyakan apa yang boleh dilihat oleh Inspektor tetapi tidak boleh diedit, dan apa yang eksklusif hanya bisa dieksekusi oleh akun Inspektor.

### **4\. Pelajari Konsep Tanda Tangan Elektronik (*E-Signature*) dalam Aviasi**

Karena transisi dari manual (kertas) ke digital adalah isu utama, pelajari sedikit tentang regulasi *E-Signature* di Indonesia (khususnya standar DKPPU jika memungkinkan).

> * Persiapkan pertanyaan mengenai seberapa siap tim Inspektor jika stempel fisik mereka digantikan dengan PIN atau otentikasi biometrik di dalam sistem, serta bagaimana mekanisme *tracking history* (audit trail) yang mereka harapkan agar tetap merasa aman secara legal.

Dengan memahami keempat poin di atas, Anda tidak hanya datang sebagai *interviewer*, tetapi sebagai *product problem-solver* yang siap memetakan kebutuhan mereka ke dalam struktur sistem yang logis.

Mengingat kompleksitas alur validasi dokumen ini, metode apa yang biasanya Anda rasa paling efektif untuk mendokumentasikan hasil *interview* agar tidak ada *requirement* teknis yang terlewat saat *sprint planning* nanti?

---

