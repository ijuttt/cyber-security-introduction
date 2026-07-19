# BAB 1 — CYBERSECURITY INTRO

> Modul pengantar keamanan siber dari nol (zero to hero series)

---

## Tujuan Pembelajaran

Setelah menyelesaikan Bab 1 ini, peserta diharapkan mampu:

1. Menjelaskan definisi cybersecurity dan membedakannya dari information security serta IT security.
2. Memahami dan menerapkan konsep CIA Triad sebagai fondasi seluruh disiplin keamanan siber.
3. Mengenali kategori-kategori ancaman siber yang paling umum beserta karakteristiknya.
4. Menggunakan terminologi dasar (asset, vulnerability, threat, risk, exploit, attack vector) secara tepat dan konsisten.
5. Mengklasifikasikan security control berdasarkan fungsi dan jenisnya.
6. Menjelaskan mengapa cybersecurity menjadi kebutuhan mendesak di era digital, termasuk peran AI dalam lanskap ancaman maupun pertahanan.
7. Memahami risiko kebocoran data baik dari sisi individu maupun organisasi, serta kerangka regulasi yang mengaturnya.
8. Mengidentifikasi peran-peran profesi di industri cybersecurity beserta profil pelaku ancaman.
9. Memetakan attack surface dan lingkungan penerapan keamanan siber di berbagai sektor.
10. Menjelaskan kapan dan bagaimana security seharusnya diterapkan dalam siklus hidup pengembangan sistem.

---

## Daftar Isi

- **1.1 What** — Definisi, CIA Triad, Ancaman, Terminologi, Security Controls
- **1.2 Why** — Digitalisasi, AI, Data Privacy, Dampak Ekonomi
- **1.3 Who** — Pelaku Cybersecurity & Pelaku Ancaman
- **1.4 Where** — Attack Surface & Lingkungan Penerapan
- **1.5 When** — Kapan Security Diterapkan

---

# 1.1 What

Sebelum masuk ke teknis, kita perlu menjawab pertanyaan paling mendasar: **apa itu cybersecurity, sebenarnya?** Banyak orang baru mengasosiasikan cybersecurity dengan "hacker pakai hoodie mengetik cepat di depan layar hitam-hijau" — citra yang jauh dari realita. Section ini akan membangun fondasi konseptual yang akan terus dipakai di seluruh bab-bab berikutnya.

## 1.1.1. Penjelasan Umum

### Definisi Keamanan Siber

Secara formal, **cybersecurity (keamanan siber)** dapat didefinisikan sebagai *praktik melindungi sistem, jaringan, perangkat, aplikasi, dan data dari serangan digital, akses tidak sah, kerusakan, atau gangguan operasional*. Definisi ini sejalan dengan definisi yang dipakai NIST (National Institute of Standards and Technology), yang menyebut cybersecurity sebagai upaya pencegahan kerusakan terhadap, perlindungan atas, dan pemulihan komputer, sistem komunikasi elektronik, dan informasi yang terkandung di dalamnya, guna memastikan **ketersediaan, integritas, autentikasi, kerahasiaan, dan non-repudiasi**.

Definisi sederhananya begini: cybersecurity adalah **usaha berkelanjutan** untuk memastikan bahwa sistem digital melakukan apa yang seharusnya dilakukan — tidak lebih, tidak kurang — dan hanya oleh pihak yang berhak.

Dua kata kunci di sini penting untuk digarisbawahi:

- **"Usaha berkelanjutan"** — bukan proyek sekali jadi, bukan produk yang dibeli lalu selesai. Ini akan dibahas lebih dalam di section 1.5.
- **"Pihak yang berhak"** — cybersecurity pada akhirnya adalah soal *kontrol akses* dalam arti yang sangat luas: siapa boleh melakukan apa, terhadap apa, kapan, dan bagaimana caranya kita tahu itu benar-benar mereka.

### Ruang Lingkup Cybersecurity

Cybersecurity bukan satu bidang tunggal, melainkan payung besar yang menaungi beberapa domain yang saling terhubung:

| Domain | Fokus Perlindungan | Contoh Kontrol |
|---|---|---|
| **Network Security** | Infrastruktur jaringan — lalu lintas data antar perangkat | Firewall, IDS/IPS, segmentasi VLAN, VPN |
| **Application Security** | Aplikasi & website sejak fase development hingga produksi | Secure coding, SAST/DAST, WAF (Web Application Firewall) |
| **Endpoint Security** | Perangkat individual — laptop, smartphone, server | Antivirus/EDR, patch management, disk encryption |
| **Cloud Security** | Infrastruktur, platform, dan layanan berbasis cloud | IAM cloud, encryption at rest/in transit, shared responsibility model |
| **Human Layer / People Security** | Manusia sebagai pengguna sekaligus target | Security awareness training, phishing simulation |

Kelima domain ini **tidak berdiri sendiri-sendiri**. Sebuah organisasi bisa punya firewall generasi terbaru (network security kuat), tapi tetap jebol karena satu karyawan mengklik link phishing (human layer lemah). Inilah kenapa cybersecurity harus dipandang sebagai *sistem yang terintegrasi*, bukan kumpulan tools yang dipasang terpisah-pisah. Prinsip **defense in depth** — melapisi banyak kontrol di banyak domain sekaligus — akan berulang kali muncul di bab-bab selanjutnya.

> 💡 **Catatan:** Beberapa referensi juga memasukkan **OT/ICS Security** (Operational Technology / Industrial Control Systems) sebagai domain tersendiri, mengingat karakteristik sistem industri (pabrik, pembangkit listrik, jaringan air) berbeda signifikan dari IT konvensional. Domain ini akan disinggung lebih lanjut di bagian 1.4.

### Perbedaan Cybersecurity vs Information Security vs IT Security

Tiga istilah ini sering dipakai bergantian secara keliru. Padahal cakupannya berbeda, dan memahami perbedaannya penting supaya kita tidak salah menempatkan tanggung jawab dalam sebuah organisasi.

| Aspek | **IT Security** | **Information Security (InfoSec)** | **Cybersecurity** |
|---|---|---|---|
| **Cakupan** | Infrastruktur TI secara keseluruhan (hardware, software, jaringan) | Semua bentuk informasi — digital **maupun** fisik/verbal | Subset InfoSec yang spesifik menghadapi ancaman melalui **ruang siber** |
| **Fokus utama** | Operasional & ketersediaan sistem TI | Kerahasiaan, integritas, ketersediaan informasi (CIA Triad) | Perlindungan dari serangan digital lewat internet/jaringan |
| **Contoh cakupan** | Server, jaringan, perangkat keras | Dokumen kertas di brankas, percakapan rahasia, database digital | Malware, phishing, hacking, ransomware |

Cara termudah membayangkannya: **Information Security** adalah lingkaran terbesar (melindungi *informasi* dalam bentuk apa pun ia berada — termasuk dokumen fisik yang dikunci di lemari arsip). **IT Security** adalah lingkaran yang berfokus pada *infrastruktur teknologinya* — memastikan server, jaringan, dan sistem tetap jalan dan aman secara operasional. **Cybersecurity** adalah irisan yang paling sering kita bahas sehari-hari: melindungi aset digital **secara spesifik dari ancaman yang datang melalui dunia maya**.

Dalam praktiknya di lapangan, terutama di Indonesia, batas ketiga istilah ini sering kabur dan dipakai saling menggantikan — dan itu wajar. Yang penting dipahami adalah *konsepnya*, bukan sekadar hafal definisinya.

---

## 1.1.2. CIA Triad

Kalau cybersecurity punya "hukum dasar" seperti hukum Newton di fisika, **CIA Triad** adalah salah satunya. Hampir semua keputusan keamanan — mulai dari memilih algoritma enkripsi sampai menyusun kebijakan backup — pada akhirnya bisa ditelusuri balik ke tiga prinsip ini.

CIA di sini **tidak ada hubungannya** dengan Central Intelligence Agency — melainkan singkatan dari:

| Elemen | Definisi | Tujuan | Contoh Kontrol Teknis | Contoh Jika Gagal |
|---|---|---|---|---|
| **Confidentiality** (Kerahasiaan) | Informasi hanya bisa diakses oleh pihak yang berwenang | Mencegah akses/pengungkapan tidak sah | Enkripsi (at rest & in transit), access control (RBAC), least privilege | Data pelanggan bocor dan dijual di forum peretas |
| **Integrity** (Integritas) | Informasi akurat, lengkap, dan tidak diubah tanpa otorisasi | Menjamin data dapat dipercaya | Hashing (SHA-256, dll), checksum, version control (Git), digital signature | Saldo rekening diubah diam-diam oleh pihak tak berwenang |
| **Availability** (Ketersediaan) | Informasi & sistem dapat diakses saat dibutuhkan oleh pihak berwenang | Menjamin layanan tetap berjalan | Redundancy, load balancing, backup rutin, proteksi DDoS | Website e-commerce down saat flash sale karena serangan DDoS |

### Confidentiality (Kerahasiaan)

Prinsip ini menjawab pertanyaan: *"Siapa saja yang boleh melihat informasi ini?"* Pelanggarannya disebut **data breach** atau **unauthorized disclosure**. Dua mekanisme teknis utama untuk menjaga confidentiality:

- **Enkripsi** — mengubah data menjadi bentuk yang tidak terbaca tanpa kunci yang tepat. Ada dua jenis besar: *symmetric encryption* (satu kunci untuk enkripsi & dekripsi, cepat tapi masalah distribusi kunci) dan *asymmetric encryption* (sepasang kunci publik-privat, lebih aman untuk pertukaran kunci). Detail teknisnya akan dibahas mendalam di bab kriptografi.
- **Access control** — memastikan hanya identitas yang diverifikasi dan diberi izin yang bisa mengakses resource tertentu. Prinsip **least privilege** (memberi akses seminimal mungkin sesuai kebutuhan kerja) adalah standar emas di sini.

### Integrity (Integritas)

Prinsip ini menjawab: *"Apakah data ini masih persis seperti aslinya, atau sudah diutak-atik?"* Pelanggaran integritas bisa lebih berbahaya daripada pelanggaran confidentiality dalam kasus tertentu — bayangkan hasil lab rumah sakit diubah diam-diam, atau source code aplikasi disisipi backdoor tanpa sepengetahuan tim developer.

- **Hashing** — fungsi satu arah yang mengubah data menjadi "sidik jari" unik berukuran tetap (misalnya SHA-256). Perubahan sekecil apa pun pada data asli akan menghasilkan hash yang benar-benar berbeda, sehingga hashing dipakai untuk memverifikasi apakah file/data telah diubah.
- **Checksum** — mirip hashing namun umumnya lebih sederhana, sering dipakai untuk mendeteksi kerusakan data saat transfer file.
- **Version control** — seperti Git, mencatat setiap perubahan pada kode sehingga histori dan siapa-mengubah-apa selalu bisa ditelusuri (audit trail).

### Availability (Ketersediaan)

Prinsip ini menjawab: *"Apakah sistem/data bisa diakses saat dibutuhkan?"* Sistem paling aman di dunia tetap gagal memenuhi tujuannya kalau pengguna sah tidak bisa mengaksesnya saat dibutuhkan.

- **Redundancy** — menghindari *single point of failure* dengan menyediakan komponen cadangan (server backup, jalur internet ganda, data center di lokasi berbeda).
- **Backup** — salinan data yang bisa dipulihkan jika data asli hilang/rusak/dienkripsi ransomware. Praktik umum adalah aturan **3-2-1**: 3 salinan data, di 2 media berbeda, dengan 1 salinan disimpan offsite.
- **Proteksi DDoS** — mekanisme untuk menyerap atau memfilter traffic berlebihan yang sengaja dikirim untuk melumpuhkan layanan (dibahas lebih detail di 1.1.3).

> ⚠️ **Penting:** Ketiga elemen CIA Triad sering kali **saling tarik-menarik (trade-off)**. Menambah lapisan enkripsi dan autentikasi (memperkuat confidentiality) bisa memperlambat akses sistem (mengorbankan availability). Setiap organisasi harus menentukan prioritas berdasarkan konteks — bank akan mengutamakan confidentiality & integrity untuk data transaksi, sementara layanan darurat (rumah sakit, 911) mungkin harus mengutamakan availability di atas segalanya.

### Extended Triad: Authentication dan Non-repudiation

Beberapa kerangka kerja modern memperluas CIA Triad dengan dua konsep tambahan yang semakin krusial di era digital:

- **Authentication (Autentikasi)** — proses **memverifikasi identitas**: memastikan seseorang/sesuatu benar-benar seperti yang mereka klaim. Ini berbeda dari *authorization* (apa yang boleh mereka lakukan setelah terverifikasi). Contoh implementasi: password, biometrik, Multi-Factor Authentication (MFA).
- **Non-repudiation (Nirsangkal)** — jaminan bahwa seseorang **tidak bisa menyangkal** telah melakukan suatu tindakan (mengirim pesan, menyetujui transaksi, mengakses sistem). Diwujudkan lewat digital signature dan audit log yang tidak bisa dimanipulasi.

Beberapa akademisi bahkan menyebut kerangka yang lebih lengkap sebagai **Parkerian Hexad** (menambahkan *possession/control, authenticity,* dan *utility*), namun untuk kebutuhan dasar, CIA Triad + Authentication + Non-repudiation sudah cukup menjadi fondasi kokoh untuk seluruh materi selanjutnya.

---

## 1.1.3. Threats Intro

Bagian ini adalah "kamus visual" ancaman siber yang paling sering ditemui. Di bab-bab berikutnya, masing-masing akan dibedah jauh lebih dalam — tujuan di sini adalah membangun **peta mental** supaya ketika istilah-istilah ini muncul nanti, sudah tidak asing lagi.

### Malware

**Malware** (*malicious software*) adalah istilah payung untuk segala jenis perangkat lunak yang dirancang untuk merusak, mencuri, atau mengganggu sistem tanpa izin pemiliknya.

| Jenis | Cara Kerja | Ciri Khas | Contoh Dampak |
|---|---|---|---|
| **Virus** | Menempel pada file/program sah, aktif & menyebar saat file dijalankan | Butuh *aksi manusia* (menjalankan file) untuk menyebar | Merusak/menghapus file, memperlambat sistem |
| **Worm** | Menyebar sendiri lewat jaringan **tanpa** perlu interaksi pengguna | Self-replicating, mengeksploitasi celah jaringan | Membanjiri bandwidth, melumpuhkan jaringan besar |
| **Trojan** | Menyamar sebagai program/file yang tampak sah/berguna | Tidak menyebar sendiri, mengandalkan tipuan | Membuka backdoor, mencuri data |
| **Ransomware** | Mengenkripsi file korban, meminta tebusan untuk kunci dekripsi | Sering disertai *double extortion* (ancam sebar data jika tak bayar) | Operasional lumpuh total, kerugian finansial besar |
| **Spyware** | Diam-diam memantau aktivitas & mencuri informasi pengguna | Berjalan tersembunyi di background | Pencurian kredensial, keylogging, pelacakan aktivitas |

> 💡 Sekilas info: **ransomware kini beroperasi seperti bisnis SaaS** lewat model *Ransomware-as-a-Service* — dibahas lebih detail di 1.3.2.

### Phishing & Social Engineering

**Social engineering** adalah teknik manipulasi psikologis untuk membuat korban secara sukarela membocorkan informasi sensitif atau melakukan tindakan yang merugikan dirinya sendiri. **Phishing** adalah bentuk social engineering yang paling umum, biasanya lewat email atau pesan palsu yang menyamar sebagai entitas terpercaya.

Variasi phishing yang perlu dikenali:

- **Spear phishing** — phishing yang ditargetkan secara spesifik ke individu/organisasi tertentu (personalisasi tinggi, jauh lebih meyakinkan).
- **Whaling** — spear phishing yang menyasar target level tinggi (C-level executive, direksi).
- **Smishing** — phishing lewat SMS.
- **Vishing** — phishing lewat panggilan suara/telepon.

Social engineering bekerja karena mengeksploitasi kecenderungan psikologis manusia — bukan celah teknis. Prinsip yang paling sering dimanfaatkan pelaku: **urgency** (rasa terburu-buru menghalangi berpikir kritis), **authority** (menyamar sebagai atasan/pihak berwenang), **fear** (ancaman konsekuensi buruk), dan **curiosity** (memancing rasa penasaran). Karena mengeksploitasi manusia, bukan mesin, social engineering sering disebut sebagai celah yang **paling sulit ditambal** — tidak ada "patch" untuk sifat manusiawi.

### DDoS Attack

**Distributed Denial of Service (DDoS)** adalah serangan yang membanjiri target (server, jaringan, aplikasi) dengan traffic dalam jumlah masif dari banyak sumber secara bersamaan, sehingga layanan tidak bisa melayani pengguna sah — melanggar prinsip **availability**. Kata "distributed" membedakannya dari DoS biasa (dari satu sumber): DDoS memanfaatkan **botnet** — jaringan ribuan hingga jutaan perangkat yang telah terinfeksi malware dan dikendalikan penyerang tanpa sepengetahuan pemiliknya.

### Man-in-the-Middle (MITM)

Serangan di mana pelaku **menyisipkan diri secara diam-diam** di antara dua pihak yang berkomunikasi, sehingga bisa menyadap atau bahkan mengubah data yang mengalir di antara mereka tanpa disadari kedua belah pihak. Vektor umum: jaringan WiFi publik tak terenkripsi, ARP spoofing, rogue access point (WiFi palsu yang meniru nama jaringan sah), dan SSL stripping (memaksa koneksi turun dari HTTPS ke HTTP).

### SQL Injection / Web-based Attack

**SQL Injection (SQLi)** terjadi ketika penyerang menyisipkan perintah SQL berbahaya ke dalam input aplikasi (misalnya kolom login) yang tidak divalidasi dengan benar, sehingga bisa memanipulasi query database — membaca, mengubah, bahkan menghapus seluruh isi database. Ini hanyalah satu contoh dari kategori besar **web-based attack** yang akan dibahas mendalam lewat kerangka **OWASP Top 10** di bab tersendiri — termasuk XSS (Cross-Site Scripting) dan CSRF (Cross-Site Request Forgery).

### Insider Threat

Ancaman yang berasal dari **dalam organisasi** — karyawan, mantan karyawan, kontraktor, atau mitra yang punya akses sah namun menyalahgunakannya. Terbagi dua:

- **Malicious insider** — sengaja merugikan organisasi (mencuri data untuk dijual, sabotase karena dendam).
- **Negligent insider** — tidak berniat jahat, tapi lalai (mengklik phishing, salah konfigurasi, kehilangan laptop kerja).

Insider threat sering luput dari radar karena kontrol keamanan tradisional (firewall, IDS) dirancang untuk menghadang ancaman dari **luar**.

### Zero-day Exploit

**Zero-day** adalah kerentanan (vulnerability) yang **belum diketahui oleh vendor/pembuat sistem**, sehingga belum ada patch resminya — istilah "zero-day" merujuk pada "nol hari" waktu yang dimiliki vendor untuk memperbaikinya sebelum dieksploitasi. Ini berbahaya karena sistem yang sepenuhnya *up-to-date* pun bisa tetap rentan.

### Advanced Persistent Threat (APT)

**APT** adalah serangan yang **canggih, senyap, dan berlangsung lama** (bisa berbulan-bulan hingga bertahun-tahun) — biasanya dilakukan oleh kelompok dengan sumber daya besar (sering dikaitkan dengan nation-state actor, dibahas di 1.3.2) yang menyasar target spesifik dengan tujuan spesifik: spionase, sabotase, atau pencurian data bernilai tinggi. Karakteristik utamanya: penyerang berusaha **bertahan selama mungkin tanpa terdeteksi** (persistence), bergerak perlahan dari satu sistem ke sistem lain (*lateral movement*), sebelum akhirnya mengeksfiltrasi data. Pola serangan seperti ini biasanya dipetakan menggunakan kerangka **Cyber Kill Chain** atau **MITRE ATT&CK** — akan dibahas tuntas di bab threat intelligence.

---

## 1.1.4. Terminologi Dasar

Enam istilah berikut adalah **"bahasa umum"** yang akan terus dipakai di *setiap* bab selanjutnya — mulai dari risk assessment, penetration testing, sampai incident response. Menguasai relasi antar-istilah ini di awal akan menghemat banyak kebingungan nantinya.

| Istilah | Definisi | Analogi Rumah |
|---|---|---|
| **Asset** | Segala sesuatu yang bernilai dan perlu dilindungi (data, sistem, reputasi, orang) | Barang berharga di dalam rumah (perhiasan, laptop, dokumen penting) |
| **Vulnerability** | Kelemahan/celah yang berpotensi dieksploitasi | Pintu yang kuncinya rusak |
| **Threat** | Potensi bahaya yang bisa memanfaatkan vulnerability | Adanya pencuri yang berkeliaran di sekitar area rumah |
| **Risk** | Kemungkinan (likelihood) suatu threat benar-benar mengeksploitasi vulnerability, dikalikan dampaknya (impact) | Peluang rumah benar-benar dibobol, dan seberapa besar kerugiannya jika terjadi |
| **Exploit** | Alat/teknik/kode spesifik yang dipakai untuk benar-benar memanfaatkan vulnerability | Alat congkel yang dipakai maling untuk membuka kunci rusak |
| **Attack Vector** | Jalur/cara yang dipakai pelaku untuk mendapatkan akses | Jendela belakang yang tidak terkunci, jalur masuk yang dipakai maling |

### Relasi Antar-Istilah

Rangkaian logikanya bisa disusun seperti ini:

> Sebuah **asset** memiliki **vulnerability**. Sebuah **threat** (dalam wujud threat actor/pelaku) memanfaatkan vulnerability tersebut lewat **attack vector** tertentu, menggunakan **exploit** sebagai alatnya — dan kombinasi semua faktor ini menghasilkan **risk** bagi asset tersebut.

Dalam rumus sederhana yang sering dipakai dalam risk management:

```
Risk ≈ Threat × Vulnerability × Impact
```

Artinya: **tidak ada risk tanpa vulnerability** (kalau tidak ada celah, threat sehebat apa pun tidak bisa berbuat banyak), dan **tidak ada risk tanpa threat** (kalau tidak ada pelaku yang berniat/berpotensi menyerang, vulnerability tetaplah cuma celah teoretis). Ketiganya harus hadir bersamaan agar risk benar-benar nyata.

### Kenapa Ini Jadi "Bahasa Umum"?

Karena **setiap** aktivitas cybersecurity — mulai dari vulnerability assessment, penetration testing, threat modeling, sampai menyusun laporan kepatuhan regulasi — pada dasarnya adalah upaya untuk **mengidentifikasi, mengukur, dan mengelola** keenam elemen ini. Tanpa kosakata yang presisi dan konsisten, komunikasi antar-tim (teknis maupun non-teknis, termasuk saat melapor ke manajemen atau regulator) akan berantakan. Inilah alasan mengapa terminologi ini ditempatkan di bab paling awal — semua bab berikutnya akan mengasumsikan istilah-istilah ini sudah dikuasai.

---

## 1.1.5. Security Controls

**Security control** adalah langkah/mekanisme konkret yang diterapkan untuk mengurangi risiko. Security control bisa diklasifikasikan dari dua sudut pandang yang saling melengkapi: **berdasarkan fungsi** (kapan dalam siklus serangan ia bekerja) dan **berdasarkan jenis** (bentuk implementasinya).

### Berdasarkan Fungsi

- **Preventive** — mencegah insiden **sebelum** terjadi. Contoh: firewall, training keamanan, kebijakan password kuat.
- **Detective** — mengidentifikasi insiden **saat/setelah** terjadi. Contoh: IDS (Intrusion Detection System), SIEM, log monitoring, CCTV.
- **Corrective** — memperbaiki dampak **setelah** insiden terdeteksi. Contoh: patching, restore dari backup, prosedur incident response.

> 💡 Beberapa kerangka kerja (seperti CISSP) menambahkan kategori lain seperti *Deterrent* (menakut-nakuti agar tidak dicoba, misalnya papan peringatan CCTV), *Recovery* (memulihkan kondisi normal pasca-insiden besar), dan *Compensating* (kontrol alternatif saat kontrol ideal tidak bisa diterapkan). Untuk level dasar, tiga kategori Preventive–Detective–Corrective sudah cukup sebagai kerangka berpikir utama.

### Berdasarkan Jenis

- **Administrative (Manajerial)** — kebijakan, prosedur, pelatihan, dan proses tata kelola. Contoh: SOP keamanan, kebijakan penggunaan perangkat, security awareness training.
- **Technical (Logical)** — implementasi lewat teknologi/sistem. Contoh: firewall, enkripsi, sistem access control, antivirus.
- **Physical** — perlindungan terhadap akses fisik. Contoh: kunci pintu, CCTV, security guard, biometric door lock, server room dengan akses terbatas.

### Matriks Fungsi × Jenis

Menggabungkan kedua sudut pandang di atas menghasilkan matriks 3×3 yang sangat umum dipakai untuk memetakan kontrol keamanan secara menyeluruh:

| | **Administrative** | **Technical** | **Physical** |
|---|---|---|---|
| **Preventive** | Kebijakan & SOP keamanan, security awareness training | Firewall, enkripsi, MFA | Kunci pintu, pagar, badge access |
| **Detective** | Audit rutin, security assessment terjadwal | IDS/IPS, SIEM, log monitoring | CCTV, sensor gerak, security guard patroli |
| **Corrective** | Revisi kebijakan pasca-insiden, prosedur incident response | Patching, restore backup, isolasi sistem terinfeksi | Perbaikan/penggantian kunci setelah pembobolan |

Memahami matriks ini penting karena **organisasi yang matang tidak boleh bergantung pada satu jenis kontrol saja**. Firewall (technical-preventive) yang kuat tidak banyak membantu kalau tidak dibarengi kebijakan yang jelas (administrative) dan pengawasan fisik ruang server (physical) yang memadai. Prinsip **defense in depth** yang disinggung di 1.1.1 pada dasarnya adalah tentang mengisi sebanyak mungkin sel dalam matriks ini.

---

# 1.2 Why

Setelah memahami **apa itu** cybersecurity, pertanyaan berikutnya yang wajib dijawab: **kenapa ini penting sekarang?** Bukankah keamanan sistem sudah menjadi perhatian sejak komputer pertama kali ada? Betul — tapi skala, kecepatan, dan taruhannya berubah drastis dalam dekade terakhir. Section ini akan membedah alasan cybersecurity bertransformasi dari "urusan tim IT" menjadi "urusan setiap orang, di setiap level."

## 1.2.1. Kenapa Cyber?

### 1.2.1.1. Perkembangan Digitalisasi

**Transformasi digital** telah merambah hampir seluruh sektor kehidupan:

- **Finansial** — dari teller bank fisik ke mobile banking, e-wallet, dan QRIS antarnegara. Uang kini bergerak sebagai baris data, bukan lembaran kertas.
- **Kesehatan** — rekam medis elektronik (RME), telemedicine, resep digital. Data kesehatan yang dulu tersimpan di lemari arsip kini ada di server.
- **Pemerintahan** — e-government, layanan publik digital, identitas digital kependudukan.

Di balik transformasi ini, ada ledakan jumlah **perangkat yang saling terkoneksi (IoT — Internet of Things)**. Jumlah perangkat IoT aktif di seluruh dunia diperkirakan mencapai kisaran **21–22 miliar** pada 2026, dan diproyeksikan terus tumbuh melampaui 40 miliar dalam beberapa tahun mendatang seiring adopsi smart home, wearable device, kendaraan terkoneksi, hingga sensor industri (IIoT). Setiap perangkat baru yang terhubung ke internet — mulai dari CCTV rumah sampai mesin pabrik — pada dasarnya adalah **titik masuk baru** yang berpotensi dieksploitasi jika tidak diamankan dengan benar. Ini yang disebut perluasan **attack surface**, konsep yang akan dibahas tuntas di 1.4.1.

Ketergantungan bisnis pada data dan sistem digital pun menjadi mutlak. Perusahaan modern — dari UMKM sampai korporasi multinasional — nyaris tidak bisa beroperasi tanpa sistem digital: mulai dari pencatatan transaksi, komunikasi internal, hingga rantai pasok (*supply chain*). Ketergantungan inilah yang membuat gangguan pada sistem digital berdampak langsung ke kelangsungan bisnis, bukan sekadar "masalah teknis."

Sebagai gambaran skala ancaman yang terus meningkat: laporan **FBI Internet Crime Complaint Center (IC3)** mencatat lebih dari **1 juta aduan** sepanjang 2025 — pertama kalinya angka tahunan menembus level tersebut — dengan total kerugian yang dilaporkan di Amerika Serikat saja mencapai **US$20,88 miliar**, naik 26% dari tahun sebelumnya. Di Indonesia, Badan Siber dan Sandi Negara (BSSN) mencatat **3,64 miliar percobaan serangan siber** sepanjang 2025. Angka-angka ini menggambarkan tren yang konsisten: **frekuensi dan skala serangan siber terus meningkat setiap tahun**, seiring makin luasnya permukaan yang bisa diserang.

### 1.2.1.2. Munculnya AI dalam Lanskap Ancaman & Pertahanan

Tidak ada perkembangan yang mengubah lanskap cybersecurity secepat kemunculan **AI generatif** dalam beberapa tahun terakhir. AI kini menjadi pedang bermata dua: memperkuat penyerang sekaligus memperkuat bek pertahanan.

**AI sebagai alat ancaman (AI-powered threats):**

- **Deepfake** — teknologi sintesis audio/video yang kini bisa meniru wajah dan suara seseorang secara meyakinkan hanya dari beberapa detik sampel suara. Kasus nyata yang jadi rujukan industri: perusahaan teknik Arup mengalami kerugian **US$25,6 juta** setelah pelaku menggunakan video call dan kloning suara untuk menyamar sebagai CFO perusahaan tersebut, meyakinkan karyawan melakukan 15 kali transfer dana. Riset industri mencatat upaya penipuan berbasis deepfake melonjak lebih dari **2.000%** dalam tiga tahun terakhir, dan deepfake kini berkontribusi pada sekitar **40% dari seluruh kasus penipuan biometrik**. Yang membuat ini makin mengkhawatirkan: tingkat akurasi manusia dalam mendeteksi video deepfake berkualitas tinggi hanya sekitar **24%** — lebih rendah dari sekadar menebak acak.
- **Phishing hasil generate AI** — email phishing yang dulu mudah dikenali dari tata bahasa buruk kini bisa dibuat oleh Large Language Model (LLM) dengan bahasa yang natural, personal, dan disesuaikan konteks target secara otomatis dan masif — menghilangkan "ciri-ciri klasik" yang selama ini diajarkan dalam security awareness training konvensional.
- **Automated attack tools** — AI mempermudah proses reconnaissance (pengintaian target) dan bahkan pembuatan kode berbahaya (malicious code) hanya dari perintah bahasa natural, sehingga menurunkan **barrier to entry** bagi pelaku dengan kemampuan teknis rendah sekalipun.

**AI sebagai alat pertahanan (AI as defense):**

Di sisi berlawanan, AI juga menjadi senjata utama tim defense:

- **Anomaly detection** — sistem berbasis machine learning yang mempelajari pola "normal" dalam jaringan/sistem, lalu menandai penyimpangan yang berpotensi jadi indikasi serangan — jauh lebih cepat dan skalabel dibanding analisis manual.
- **Otomasi SOC (Security Operations Center)** — AI membantu tim SOC melakukan triase ribuan alert per hari, memprioritaskan mana yang benar-benar butuh perhatian manusia (mengurangi *alert fatigue*).

Dampaknya terukur: menurut **IBM Cost of a Data Breach Report 2025**, organisasi yang menerapkan AI keamanan secara ekstensif berhasil menghemat rata-rata **US$1,9 juta** per insiden breach dan mendeteksi insiden **80 hari lebih cepat** dibanding organisasi yang tidak menggunakannya. Namun laporan yang sama juga memberi peringatan: **63% organisasi yang mengalami breach belum memiliki tata kelola (governance) AI yang memadai**, dan **20% organisasi** mengalami insiden yang terkait *shadow AI* — penggunaan tools AI oleh karyawan tanpa sepengetahuan/pengawasan tim IT — yang menambah kerugian rata-rata hingga **US$670.000** per insiden. Ini menegaskan satu hal penting: **AI bukan solusi ajaib**. Tanpa tata kelola yang tepat, AI yang seharusnya jadi alat pertahanan justru bisa menjadi celah baru.

---

## 1.2.2. Data Privacy

### Kenapa Data Itu Berharga?

Frasa **"data adalah minyak baru"** sering dipakai untuk menggambarkan betapa berharganya data di era digital — data menggerakkan targeted advertising, melatih model AI, dan menjadi dasar pengambilan keputusan bisnis bernilai miliaran dolar. Namun analogi ini punya batasnya: berbeda dari minyak, data **tidak habis dipakai** dan **bisa disalin tanpa batas** — sekali bocor, ia bisa disebar, dijual berkali-kali, dan disalahgunakan bertahun-tahun kemudian. Inilah yang membuat kebocoran data jauh lebih sulit "dibersihkan" dibanding tumpahan minyak.

### Jenis Data Sensitif

- **PII (Personally Identifiable Information)** — data yang bisa mengidentifikasi seseorang secara langsung/tidak langsung: nama, NIK, alamat, nomor telepon, data biometrik.
- **Data finansial** — nomor kartu, rekening bank, riwayat transaksi.
- **Data kesehatan** — riwayat penyakit, hasil lab, rekam medis (termasuk kategori data yang paling ketat diatur di hampir semua regulasi privasi dunia).
- **Kredensial** — password, token akses, API key.

### 1.2.2.1. Personal → Risk

Ketika data pribadi seseorang bocor, risikonya nyata dan langsung dirasakan individu tersebut:

- **Pencurian identitas (identity theft)** — pelaku menggunakan data curian untuk berpura-pura menjadi korban, misalnya mengajukan pinjaman online atau membuka rekening atas nama korban.
- **Penipuan finansial** — transaksi tidak sah menggunakan data kartu/rekening yang bocor.
- **Pemerasan (extortion/doxing)** — mengancam menyebarkan informasi pribadi/sensitif kecuali korban membayar, atau menyebarkan data pribadi (alamat, kontak) secara publik dengan niat jahat (doxing).
- **Kerugian psikologis & reputasi** — stres, kecemasan berkepanjangan, hingga dampak sosial/profesional yang nyata bagi korban.

### 1.2.2.2. Organizational → Risk

Bagi organisasi, kebocoran data memicu rentetan kerugian yang saling berkaitan:

- **Kerugian finansial** — denda regulasi (akan dibahas di bagian regulasi di bawah), biaya investigasi forensik, kehilangan bisnis akibat pelanggan berpindah ke kompetitor.
- **Reputasi rusak & hilangnya kepercayaan pelanggan** — kepercayaan yang dibangun bertahun-tahun bisa runtuh dalam hitungan hari setelah insiden terekspos publik.
- **Kebocoran rahasia dagang/kekayaan intelektual** — riset, formula, source code, atau strategi bisnis yang bocor ke kompetitor atau publik.
- **Gangguan operasional (downtime)** — sistem yang harus dimatikan sementara untuk investigasi/pemulihan berarti proses bisnis terhenti. Menurut **IBM Cost of a Data Breach Report 2025**, **86% organisasi** yang mengalami breach melaporkan gangguan operasional nyata — mulai dari penundaan penjualan, layanan terganggu, hingga produksi terhenti.

---

## Risk — Apa yang Terjadi Jika Data Bocor?

Untuk memahami risiko ini secara konkret, mari lihat empat studi kasus nyata — dua dari Indonesia, dua dari skala global.

### Studi Kasus: Tokopedia (Indonesia, 2020)

Pada Maret–April 2020, Tokopedia — salah satu platform e-commerce terbesar Indonesia — mengalami kebocoran data yang memengaruhi sekitar **91 juta akun pengguna**. Data yang bocor mencakup nama, email, tanggal lahir, alamat, dan password dalam bentuk *hash* (SHA2-384). Data tersebut kemudian ditemukan diperjualbelikan di forum peretas dengan harga sekitar **US$5.000**. Meski password tersimpan dalam bentuk hash (bukan plain text — praktik yang tepat sesuai prinsip integrity/confidentiality yang dibahas di 1.1.2), skala data yang bocor tetap menimbulkan risiko besar terkait *credential stuffing* (percobaan login otomatis menggunakan kombinasi email-password bocor ke platform lain) bagi puluhan juta pengguna.

### Studi Kasus: BPJS Kesehatan (Indonesia, 2021)

Pada Mei 2021, mencuat dugaan kebocoran data yang jauh lebih besar: sekitar **279 juta data** — melebihi jumlah penduduk Indonesia saat itu, karena termasuk data individu yang telah meninggal — diduga berasal dari BPJS Kesehatan dan dijual di sebuah forum peretas oleh akun bernama "Kotz". Data yang bocor mencakup NIK, KTP, nama, alamat, nomor telepon, gaji, hingga riwayat kesehatan — kombinasi data yang sangat sensitif karena menggabungkan identitas kependudukan **dan** data kesehatan sekaligus. Kasus ini melibatkan investigasi bersama Kementerian Komunikasi dan Informatika (kini Komdigi), BSSN, dan BPJS Kesehatan, dan menjadi salah satu pendorong utama percepatan pengesahan UU PDP.

### Studi Kasus: Equifax (Global, 2017)

Equifax, salah satu biro kredit terbesar Amerika Serikat, mengalami breach antara Mei–Juli 2017 yang mengekspos data sekitar **147 juta konsumen** — termasuk nama, tanggal lahir, alamat, dan nomor Social Security (identitas nasional AS). Penyebab akar masalahnya cukup mengena sebagai pelajaran: sebuah **vulnerability pada framework Apache Struts yang sudah ada patch-nya**, namun belum sempat diterapkan Equifax. Kasus ini menjadi salah satu bukti paling nyata betapa mahalnya menunda patch management — total penyelesaian hukum (settlement) yang harus dibayar Equifax mencapai **hingga US$700 juta**.

### Studi Kasus: Facebook–Cambridge Analytica (Global, 2018)

Berbeda dari tiga kasus di atas yang murni soal *pembobolan* sistem, kasus ini menyoroti risiko **penyalahgunaan data yang dikumpulkan secara "sah"**. Sejak 2014, sebuah aplikasi kuis kepribadian di Facebook mengumpulkan data hingga **87 juta pengguna** (termasuk data teman-teman pengguna aplikasi tersebut, tanpa sepengetahuan mereka) lewat Facebook Graph API. Data ini kemudian dipakai firma konsultan politik Cambridge Analytica untuk menyusun profil psikologis pemilih guna kepentingan kampanye politik. Setelah terungkap lewat investigasi jurnalistik pada 2018, Facebook didenda **US$5 miliar** oleh FTC (Federal Trade Commission) pada 2019 — rekor denda privasi terbesar pada masanya — disertai kewajiban pengawasan tata kelola privasi selama 20 tahun.

> 📌 **Pelajaran dari keempat kasus:** Risiko kebocoran data tidak selalu berasal dari serangan yang canggih (*sophisticated*). Equifax bocor karena patch yang tertunda. Cambridge Analytica bahkan tidak melibatkan "hacking" dalam arti teknis — melainkan penyalahgunaan API dan kelemahan kebijakan izin akses data pihak ketiga. Ini menegaskan bahwa cybersecurity bukan hanya soal teknologi canggih, tapi juga soal **kedisiplinan dasar**: patch tepat waktu, kebijakan akses data yang ketat, dan pengawasan pihak ketiga.

### Jual-Beli Data di Dark Web

Seperti terlihat di keempat studi kasus di atas, data curian pada akhirnya sering berujung diperjualbelikan di forum-forum peretas bawah tanah. Secara umum, ada ekosistem pasar gelap tempat data hasil breach — kredensial, data kartu, data identitas — diperdagangkan, dengan harga yang bervariasi tergantung jenis data, kesegaran (seberapa baru datanya, karena data lama nilainya menurun setelah korban mengganti password/kartu), dan volume. Fenomena inilah yang membuat dampak sebuah kebocoran data **tidak pernah benar-benar selesai** begitu insiden awal ditangani — data yang sudah tersebar tetap berpotensi disalahgunakan bertahun-tahun kemudian oleh pembeli yang berbeda-beda.

### Regulasi Terkait Data Privacy

Untuk merespons risiko-risiko di atas, berbagai negara menyusun kerangka regulasi perlindungan data. Tiga yang paling relevan untuk dipahami:

**UU PDP (Indonesia)** — Undang-Undang Nomor 27 Tahun 2022 tentang Pelindungan Data Pribadi, disahkan 17 Oktober 2022 dan resmi berlaku penuh (termasuk sanksinya) setelah masa transisi dua tahun, per **17 Oktober 2024**. UU PDP mewajibkan setiap pengendali/pemroses data yang menangani data pribadi warga Indonesia untuk memiliki dasar pemrosesan yang sah, memberikan notifikasi privasi yang transparan, menghormati hak-hak subjek data, melaporkan kebocoran data dalam **72 jam**, serta menerapkan Data Protection Impact Assessment untuk pemrosesan berisiko tinggi. Sanksi administratif bisa mencapai **2% dari pendapatan tahunan**. 

> 💡 **Update terkini (relevan untuk konteks kepatuhan/compliance):** Meski UU PDP sudah berlaku penuh, lembaga pengawas independen yang diamanatkan undang-undang ini (Lembaga/Badan Pelindungan Data Pribadi) **hingga pertengahan 2026 masih dalam proses pembentukan** — Peraturan Presiden dan Peraturan Pemerintah pelaksananya belum seluruhnya terbit. Untuk sementara, fungsi pengawasan implementasi dijalankan oleh Kementerian Komunikasi dan Digital (Komdigi) berkoordinasi dengan BSSN. Ini adalah contoh nyata bagaimana **regulasi yang sudah berlaku secara hukum tidak otomatis berarti infrastruktur penegakannya sudah lengkap** — poin yang penting dipahami khususnya bagi yang bekerja di bidang compliance.

**GDPR (General Data Protection Regulation, Uni Eropa)** — salah satu kerangka regulasi privasi paling berpengaruh di dunia dan sering menjadi rujukan/model bagi regulasi negara lain (termasuk UU PDP). Berlaku sejak 2018, GDPR mengatur hak-hak subjek data secara luas dan bisa menjatuhkan denda hingga **4% dari pendapatan global tahunan** atau €20 juta (mana yang lebih besar), serta berlaku ekstrateritorial — memengaruhi perusahaan mana pun di dunia yang memproses data warga Uni Eropa.

**HIPAA (Health Insurance Portability and Accountability Act, Amerika Serikat)** — regulasi yang secara spesifik mengatur perlindungan data kesehatan (*Protected Health Information*) di AS. Relevan dipelajari karena menjadi salah satu standar rujukan global untuk pengamanan data kesehatan, sektor yang — seperti akan terlihat di bagian ekonomi berikutnya — konsisten menjadi sektor dengan biaya breach termahal.

---

## 1.2.3. Dampak Ekonomi Global dari Cybercrime

Untuk memahami skala persoalan ini secara utuh, angka-angka berikut layak direnungkan.

### Estimasi Kerugian Global

Menurut proyeksi **Cybersecurity Ventures** — salah satu sumber estimasi yang paling sering dikutip di industri — total kerugian global akibat cybercrime diperkirakan menembus **US$10,5 triliun pada 2025**, dengan berbagai model proyeksi terbaru memperkirakan angka tahun 2026 berada di kisaran **US$10,8–11,9 triliun**, dan diproyeksikan terus naik menuju sekitar **US$15,6 triliun pada 2029**. Sebagai perbandingan skala: jika cybercrime dianggap sebagai sebuah "negara", ekonominya akan menjadi yang terbesar ketiga di dunia — hanya kalah dari Amerika Serikat dan Tiongkok. Perlu dicatat bahwa angka-angka semacam ini merupakan **estimasi/proyeksi**, bukan angka yang diaudit secara presisi — karena banyak insiden cybercrime yang tidak pernah dilaporkan sama sekali (*dark figure of crime*) — namun tren kenaikannya konsisten dilaporkan oleh berbagai lembaga riset independen.

### IBM Cost of a Data Breach Report

Laporan tahunan **IBM Cost of a Data Breach Report** (bekerja sama dengan Ponemon Institute) adalah salah satu rujukan paling otoritatif untuk memahami biaya konkret sebuah kebocoran data bagi organisasi. Temuan kunci dari edisi 2025 (data terbaru yang tersedia):

| Metrik | Angka |
|---|---|
| Rata-rata biaya breach global | **US$4,44 juta** (turun 9% dari rekor tertinggi US$4,88 juta di 2024 — penurunan pertama dalam 5 tahun) |
| Rata-rata biaya breach di AS (tertinggi di dunia) | **US$10,22 juta** |
| Sektor kesehatan (termahal, 14 tahun berturut-turut) | **US$7,42 juta** per insiden |
| Sektor finansial | **US$5,56 juta** per insiden |
| Rata-rata waktu identifikasi + containment | **241 hari** (titik terendah dalam 9 tahun) |
| Selisih biaya breach >200 hari vs <200 hari untuk terdeteksi | breach yang butuh >200 hari lebih mahal ~US$1 juta+ |
| Proporsi breach yang melibatkan unsur manusia (phishing, credential curian, human error) | **sekitar 60%** |

Pola yang konsisten muncul dari laporan ini: **kecepatan deteksi dan respons berbanding lurus dengan besarnya kerugian**. Ini menjadi alasan mendasar mengapa *continuous monitoring* (dibahas di 1.5) menjadi begitu krusial — bukan sekadar rekomendasi "best practice", tapi berdampak langsung pada nilai kerugian riil dalam hitungan juta dolar.

### Cyber Insurance sebagai Respons Industri

Melihat besarnya potensi kerugian, industri asuransi merespons dengan mengembangkan **cyber insurance** — polis yang secara spesifik menanggung kerugian akibat insiden siber (biaya forensik, notifikasi korban, denda regulasi, hingga business interruption). Pasar cyber insurance global diperkirakan mencapai sekitar **US$22,5 miliar pada 2026**, dengan premi naik rata-rata **11%** sepanjang 2025 seiring meningkatnya klaim.

Namun, cyber insurance bukan solusi tanpa catatan. Data industri menunjukkan **42% perusahaan yang memiliki polis cyber insurance mengaku cakupannya hanya menanggung sebagian kecil dari kerugian aktual**, dan sekitar **21% klaim ditolak** karena perusahaan tidak memenuhi persyaratan keamanan minimum yang disyaratkan polis (misalnya tidak menerapkan MFA). Ini menegaskan satu prinsip penting: **cyber insurance melengkapi, bukan menggantikan, kontrol keamanan yang solid** — perusahaan tetap wajib menerapkan security control dasar (lihat kembali 1.1.5) agar polis mereka benar-benar bisa dicairkan saat dibutuhkan.

---

# 1.3 Who

Setelah memahami **apa** dan **kenapa**, sekarang kita berkenalan dengan **siapa saja** yang terlibat di dunia cybersecurity — baik yang berjuang melindungi, maupun yang menjadi ancaman.

## 1.3.1. Pelaku Cybersecurity (Offensive & Defensive)

Industri cybersecurity umumnya terbagi ke dalam tiga kelompok besar berdasarkan peran mereka.

### Defensive (Blue Team)

Tim yang bertugas **membangun dan menjaga pertahanan**:

- **Security Analyst** — memantau, menganalisis, dan merespons ancaman sehari-hari; garda depan operasional keamanan.
- **SOC Analyst** — bekerja di Security Operations Center, memantau alert dari berbagai sistem (SIEM, IDS) secara real-time, biasanya berjenjang dari Tier 1 (triase awal) hingga Tier 3 (analisis mendalam).
- **Incident Responder** — turun tangan khusus saat insiden benar-benar terjadi: mengisolasi ancaman, melakukan investigasi forensik, memulihkan sistem.
- **CISO (Chief Information Security Officer)** — pemimpin strategis yang bertanggung jawab atas keseluruhan postur keamanan organisasi, menjembatani tim teknis dengan manajemen/direksi.

### Offensive (Red Team)

Tim yang bertugas **berpikir dan bertindak seperti penyerang** — secara sah dan terotorisasi — untuk menemukan celah sebelum pelaku sungguhan menemukannya:

- **Pentester (Penetration Tester)** — secara sistematis mencoba membobol sistem dalam ruang lingkup dan izin yang disepakati, lalu melaporkan temuan beserta rekomendasi perbaikan.
- **Ethical Hacker** — istilah yang sering dipakai bergantian dengan pentester; menekankan aspek etika dan legalitas dari aktivitas hacking yang dilakukan.
- **Bug Hunter** — mencari kerentanan pada program **bug bounty** yang diselenggarakan perusahaan (mendapat imbalan finansial untuk setiap temuan valid yang dilaporkan secara bertanggung jawab).

### Netral/Support

Peran yang menjembatani sisi teknis dan tata kelola:

- **Security Researcher** — meneliti kerentanan baru, teknik serangan baru, atau menganalisis malware secara mendalam, sering mempublikasikan temuannya untuk kepentingan komunitas.
- **Auditor** — memeriksa apakah kontrol keamanan organisasi telah diterapkan dan berjalan sesuai standar/kebijakan yang berlaku.
- **Compliance Officer** — memastikan organisasi memenuhi kewajiban regulasi (seperti UU PDP, ISO 27001, atau standar sektoral lainnya) dan menerjemahkan bahasa hukum/regulasi menjadi kontrol teknis yang bisa diimplementasikan.

> 💡 **Purple Team** — konsep yang makin populer, bukan tim terpisah melainkan **kolaborasi aktif** antara Red Team dan Blue Team, di mana temuan serangan simulasi langsung dipakai untuk memperkuat deteksi dan respons secara real-time — mempercepat siklus belajar kedua belah pihak.

---

## 1.3.2. Pelaku Ancaman (Threat Actors)

Memahami **siapa** di balik sebuah serangan membantu memprediksi motif, target, dan tingkat kecanggihan yang mungkin dihadapi.

| Threat Actor | Motif | Tingkat Skill | Karakteristik |
|---|---|---|---|
| **Script Kiddie** | Eksistensi, iseng, mencari sensasi | Rendah — mengandalkan tools/script yang dibuat orang lain | Sering menyerang target acak, minim perencanaan |
| **Hacktivist** | Ideologi/politik | Bervariasi | Menyasar organisasi yang dianggap bertentangan dengan nilai yang mereka perjuangkan; sering lewat DDoS atau defacement website |
| **Cybercriminal** | Finansial | Menengah–tinggi | Motif paling umum di balik mayoritas serangan (ransomware, fraud, pencurian data untuk dijual) |
| **Nation-state Actor** | Politik, spionase, sabotase strategis | Sangat tinggi, sumber daya besar | Sering di balik APT (lihat 1.1.3), menyasar infrastruktur kritis atau data intelijen |
| **Insider Threat** | Bervariasi (dendam, finansial, atau tidak sengaja) | Bervariasi | Sudah memiliki akses sah — lihat kembali penjelasan di 1.1.3 |
| **Organized Cybercrime Group** | Finansial, terstruktur | Tinggi, terorganisasi seperti korporasi | Memiliki pembagian peran jelas: developer, operator, pencuci uang, dll |
| **RaaS & MaaS** | Finansial (model bisnis) | Bervariasi (operator tinggi, afiliasi bisa rendah) | Lihat penjelasan detail di bawah |

### Ransomware-as-a-Service (RaaS) & Malware-as-a-Service (MaaS)

Salah satu pergeseran paling signifikan dalam lanskap ancaman modern adalah **industrialisasi cybercrime**. **RaaS** dan **MaaS** adalah model bisnis di mana pengembang malware/ransomware **menyewakan** produk mereka kepada "afiliasi" — mirip persis dengan model Software-as-a-Service yang legal.

Cara kerjanya:

1. **Operator/developer** membangun dan memelihara malware/ransomware, lengkap dengan dashboard, portal negosiasi tebusan, bahkan layanan "customer support" untuk korban yang ingin membayar.
2. **Afiliasi** — yang bisa jadi tidak punya kemampuan teknis membuat malware sendiri — menyewa akses ke platform tersebut untuk benar-benar melancarkan serangan.
3. Hasil tebusan dibagi antara operator dan afiliasi, umumnya dengan afiliasi menerima **70–80%** dari nilai tebusan (beberapa kelompok bahkan menawarkan split hingga 90/10 untuk menarik lebih banyak afiliasi di tengah persaingan antar-kelompok RaaS).

Model ini secara drastis **menurunkan barrier to entry** untuk melakukan serangan ransomware skala besar — seseorang dengan kemampuan teknis minim kini bisa "menyewa" kemampuan menyerang tingkat tinggi, sama seperti menyewa infrastruktur cloud tanpa perlu membangun data center sendiri. Inilah salah satu alasan utama mengapa volume serangan ransomware terus meningkat meski kemampuan defense juga terus membaik — ekosistemnya sudah menjadi industri tersendiri dengan pembagian kerja (*division of labor*) yang matang, lengkap dengan pasar gelap tempat "akses awal" ke jaringan korban (*Initial Access Broker*) diperjualbelikan sebagai layanan terpisah.

---

# 1.4 Where

Bagian ini memetakan **di mana** cybersecurity perlu diterapkan — baik dari sisi teknis (permukaan yang bisa diserang) maupun dari sisi konteks penerapannya di berbagai jenis organisasi/lingkungan.

## 1.4.1. Attack Surface

**Attack surface** adalah keseluruhan titik potensial yang bisa dimanfaatkan pelaku untuk mendapatkan akses tidak sah ke suatu sistem. Semakin luas attack surface, semakin banyak celah yang harus diamankan tim defense — sementara pelaku hanya butuh **satu** celah yang luput untuk berhasil.

- **Jaringan (network layer)** — router, switch, firewall, protokol komunikasi. Kesalahan konfigurasi jaringan bisa membuka jalan ke seluruh sistem di baliknya.
- **Aplikasi & website** — web app, API, aplikasi mobile. Semakin kompleks aplikasi, semakin besar kemungkinan ada celah logika atau kesalahan implementasi (lihat kembali SQL Injection, XSS di 1.1.3).
- **Endpoint** — laptop, smartphone, perangkat IoT individual. Setiap endpoint yang terhubung ke jaringan organisasi adalah pintu masuk potensial, apalagi di era **BYOD (Bring Your Own Device)** dan kerja remote.
- **Cloud infrastructure** — kesalahan konfigurasi (*misconfiguration*) adalah penyebab breach cloud yang paling umum, bukan celah pada infrastruktur penyedia cloud itu sendiri. Ini berkaitan erat dengan konsep **shared responsibility model**: penyedia cloud bertanggung jawab mengamankan *infrastruktur* (keamanan "of the cloud"), sementara pengguna tetap bertanggung jawab mengamankan *konfigurasi dan data mereka sendiri* (keamanan "in the cloud") — pembagian tanggung jawab ini akan dibahas mendalam di bab cloud security.
- **Manusia (human layer)** — seperti dibahas di 1.1.3, manusia adalah target sekaligus celah yang paling sulit "ditambal" lewat social engineering.

## 1.4.2. Lingkungan Penerapan

Kebutuhan dan prioritas cybersecurity berbeda-beda tergantung konteks organisasinya:

- **Perusahaan/korporat** — umumnya memiliki sumber daya paling besar untuk investasi keamanan, namun juga jadi target bernilai tinggi karena data dan aset finansialnya.
- **Infrastruktur kritis** — listrik, air, transportasi, perbankan. Sektor ini unik karena sering melibatkan **OT/ICS (Operational Technology/Industrial Control Systems)** — sistem yang mengontrol proses fisik nyata, bukan sekadar data. Gangguan di sini bisa berdampak langsung ke keselamatan publik, bukan hanya kerugian finansial — itulah mengapa infrastruktur kritis menjadi target favorit nation-state actor (lihat 1.3.2).
- **Pemerintahan** — menyimpan data kependudukan dalam skala masif serta menjalankan layanan publik esensial, menjadikannya target spionase maupun hacktivism.
- **Individu** — dengan makin banyaknya layanan digital pribadi (perbankan, media sosial, dompet digital), individu kini juga menjadi target langsung, bukan hanya "korban tidak langsung" dari breach korporat.
- **Pendidikan** — institusi pendidikan menyimpan data siswa/mahasiswa dalam jumlah besar, namun sering memiliki anggaran keamanan yang jauh lebih terbatas dibanding sektor lain — menjadikannya target yang relatif "empuk".
- **UMKM (Usaha Mikro, Kecil, Menengah)** — sering luput dari perhatian karena dianggap "terlalu kecil untuk diserang", padahal justru sebaliknya: UMKM umumnya punya kontrol keamanan minim namun tetap menyimpan data pelanggan dan transaksi finansial, menjadikannya target yang menarik secara *risk-to-reward* bagi pelaku. Studi industri mencatat bahwa serangan siber terhadap bisnis kecil bisa menimbulkan kerugian rata-rata puluhan ribu dolar per insiden — jumlah yang cukup untuk membuat sebagian UMKM tidak sanggup bertahan dan tutup dalam hitungan bulan setelah insiden.

---

# 1.5 When

Section terakhir Bab 1 ini menjawab pertanyaan yang sering diremehkan: **kapan** sebenarnya keamanan harus mulai dipikirkan?

## 1.5.2. Kapan Security Harus Diterapkan

### Security by Design vs Security sebagai "Tempelan"

Ada dua filosofi yang bertolak belakang dalam menerapkan keamanan:

- **Security sebagai "tempelan" (bolt-on/afterthought)** — sistem dibangun dulu sampai selesai, baru kemudian "ditempeli" kontrol keamanan di akhir — biasanya tepat sebelum rilis, atau lebih buruk lagi, setelah insiden pertama terjadi.
- **Security by Design** — keamanan dipertimbangkan **sejak fase perencanaan dan desain**, menjadi bagian melekat dari arsitektur sistem, bukan lapisan tambahan yang ditempelkan belakangan.

Alasan Security by Design jauh lebih disarankan bukan cuma soal keamanan yang lebih kuat, tapi juga soal **ekonomi**. Prinsip yang sering dikutip dari riset **IBM Systems Sciences Institute** menyebut kerentanan yang ditemukan pada fase desain jauh lebih murah untuk diperbaiki dibanding jika ditemukan setelah sistem sudah berjalan di production — beberapa penelitian lanjutan bahkan mencatat selisih puluhan hingga ratusan kali lipat, tergantung kompleksitas sistem dan metodologi pengukurannya. Yang paling penting dipahami bukan angka pastinya (karena tiap studi punya metodologi dan hasil berbeda), melainkan **arah tren yang konsisten**: semakin lambat sebuah celah keamanan ditemukan dalam siklus hidup sistem, semakin mahal dan rumit biaya perbaikannya — karena sudah melibatkan perubahan kode, pengujian ulang, deployment ulang, penanganan insiden, hingga komunikasi ke pelanggan jika sudah terlanjur dieksploitasi.

### Shift-Left Security dalam SDLC

Konsep **shift-left security** adalah penerapan konkret dari filosofi Security by Design. Istilah "shift-left" merujuk pada diagram siklus hidup pengembangan software (**SDLC — Software Development Life Cycle**), yang biasanya digambar dari kiri ke kanan: *Planning → Design → Development → Testing → Deployment → Maintenance*. Secara tradisional, security check (seperti penetration testing) baru masuk di fase **Testing** — jauh di sisi kanan, mendekati rilis. "Shift-left" berarti menggeser aktivitas keamanan **lebih ke kiri**, sedekat mungkin ke fase awal:

- **Planning/Design** — threat modeling: mengidentifikasi potensi ancaman terhadap arsitektur *sebelum* satu baris kode pun ditulis.
- **Development** — secure coding practices, code review dengan perhatian khusus pada keamanan.
- **Testing** — SAST (Static Application Security Testing) memindai source code, DAST (Dynamic Application Security Testing) menguji aplikasi saat berjalan, keduanya diotomatisasi langsung dalam pipeline CI/CD alih-alih jadi tahap manual terpisah di akhir.

Hasilnya: kerentanan ditemukan dan diperbaiki jauh lebih dini, lebih murah, dan tidak menghambat kecepatan rilis — alih-alih security jadi "penghalang" di ujung proses, ia menjadi bagian yang menyatu dengan alur kerja developer sehari-hari.

### Continuous Monitoring, Bukan Usaha Satu Kali

Ini adalah pesan penutup yang paling penting dari keseluruhan Bab 1: **cybersecurity bukanlah proyek yang punya garis finis**. Sistem yang hari ini dinyatakan "aman" bisa jadi rentan besok — bukan karena sistemnya berubah, tapi karena:

- Kerentanan baru (**CVE — Common Vulnerabilities and Exposures**) terus-menerus ditemukan pada software/library yang dipakai, termasuk yang sudah lama digunakan tanpa masalah.
- Teknik serangan terus berevolusi (lihat kembali bagaimana AI mengubah lanskap ancaman di 1.2.1.2).
- Konfigurasi sistem berubah seiring waktu (penambahan fitur, integrasi baru, perubahan tim) yang berpotensi membuka celah baru tanpa disadari.

Karena itu, **continuous monitoring** — pemantauan berkelanjutan lewat SIEM, vulnerability scanning rutin, penetration testing berkala, dan audit terjadwal — bukan sekadar "nice to have", melainkan kebutuhan mendasar. Kombinasi Security by Design + Shift-Left + Continuous Monitoring inilah yang membentuk siklus keamanan yang benar-benar berkelanjutan: **aman sejak dirancang, tetap diawasi sepanjang beroperasi.**

---

# Rangkuman Bab 1

Mari kita satukan kembali lima pertanyaan besar yang sudah dijawab di bab ini:

- **What** — Cybersecurity adalah praktik melindungi sistem, jaringan, dan data dari serangan digital, dibangun di atas fondasi **CIA Triad** (Confidentiality, Integrity, Availability), dengan bahasa umum berupa terminologi **Asset–Vulnerability–Threat–Risk–Exploit–Attack Vector**, dan diwujudkan lewat **security control** yang preventif, detektif, maupun korektif.
- **Why** — Digitalisasi masif dan kemunculan AI memperluas sekaligus mempercepat lanskap ancaman, sementara data pribadi maupun organisasi menyimpan risiko nyata yang terbukti lewat berbagai studi kasus kebocoran data — dengan kerugian ekonomi global yang terus meningkat setiap tahun.
- **Who** — Ada dua sisi yang saling berhadapan: praktisi cybersecurity (Blue Team, Red Team, dan peran pendukung) di satu sisi, dan beragam threat actor dengan motif berbeda-beda — dari script kiddie iseng hingga nation-state actor bersumber daya besar — di sisi lain.
- **Where** — Attack surface terus meluas mencakup jaringan, aplikasi, endpoint, cloud, hingga manusia itu sendiri, diterapkan di berbagai lingkungan mulai dari korporat besar hingga UMKM yang sering terlewat dari perhatian.
- **When** — Keamanan paling efektif dan paling murah ketika diterapkan **sejak awal** (Security by Design, shift-left dalam SDLC) dan dijaga lewat **pengawasan berkelanjutan** — bukan proyek sekali jadi.

Kelima pertanyaan ini akan menjadi kerangka berpikir yang terus dipakai di bab-bab selanjutnya. Setiap kali mempelajari topik baru — baik itu kriptografi, network security, maupun incident response — akan sangat membantu untuk kembali bertanya: *apa yang dilindungi, kenapa penting, siapa yang terlibat, di mana celahnya, dan kapan kontrolnya harus diterapkan?*

---

# Pertanyaan Refleksi

Gunakan pertanyaan berikut untuk menguji pemahaman sebelum melanjutkan ke Bab 2:

1. Jelaskan dengan kata-katamu sendiri perbedaan antara IT Security, Information Security, dan Cybersecurity. Berikan satu contoh skenario yang termasuk InfoSec namun **bukan** Cybersecurity.
2. Sebuah aplikasi mobile banking mengalami downtime 6 jam karena serangan DDoS. Elemen CIA Triad mana yang paling terdampak? Jelaskan alasannya.
3. Susun sebuah skenario risiko (boleh fiktif) yang menyebutkan secara eksplisit keenam istilah dasar: asset, vulnerability, threat, risk, exploit, dan attack vector.
4. Bandingkan kasus kebocoran data Equifax dan Facebook–Cambridge Analytica. Mana yang murni "hacking" secara teknis, dan mana yang lebih merupakan persoalan kebijakan/tata kelola data? Apa implikasinya terhadap pendekatan pencegahan yang berbeda?
5. Mengapa UMKM sering dianggap "aman" dari serangan siber padahal faktanya justru rentan? Kaitkan jawabanmu dengan konsep attack surface dan security control.
6. Jelaskan bagaimana model bisnis Ransomware-as-a-Service (RaaS) mengubah profil pelaku ancaman yang perlu diwaspadai organisasi.
7. Apa perbedaan mendasar antara pendekatan "security sebagai tempelan" dan "Security by Design"? Mengapa organisasi tetap sering memilih pendekatan pertama meski secara ekonomi lebih mahal dalam jangka panjang?
8. Diskusikan: mengapa keberadaan UU PDP sejak 2022 belum tentu berarti perlindungan data pribadi di Indonesia sudah berjalan optimal secara penuh?

---

# Referensi

Materi pada bab ini disusun dengan merujuk pada sumber-sumber berikut:

- IBM Security, *Cost of a Data Breach Report 2025* — ibm.com/reports/data-breach
- Cybersecurity Ventures — proyeksi kerugian global cybercrime
- FBI Internet Crime Complaint Center (IC3), *2025 Annual Report*
- Badan Siber dan Sandi Negara (BSSN) — statistik serangan siber Indonesia
- Undang-Undang Nomor 27 Tahun 2022 tentang Pelindungan Data Pribadi (UU PDP)
- General Data Protection Regulation (GDPR), Uni Eropa
- Health Insurance Portability and Accountability Act (HIPAA), Amerika Serikat
- Federal Trade Commission (FTC) & Consumer Financial Protection Bureau (CFPB) — dokumen settlement kasus Equifax dan Facebook–Cambridge Analytica
- Pemberitaan seputar kasus kebocoran data Tokopedia (2020) dan BPJS Kesehatan (2021) — termasuk liputan Jakarta Post, CyberScoop, ANTARA News, dan Kominfo
- Laporan tren industri terkait AI-powered threats, deepfake fraud, dan Ransomware-as-a-Service dari berbagai firma riset keamanan siber (2025–2026)

> 📎 Catatan: Beberapa angka statistik pada bab ini (kerugian ekonomi global, biaya breach, jumlah perangkat IoT) bersifat **estimasi/proyeksi** yang terus diperbarui setiap tahun oleh masing-masing lembaga sumber. Untuk kebutuhan akademis/formal, disarankan selalu memverifikasi ke laporan edisi terbaru langsung dari sumber aslinya.

---

*— Akhir Bab 1 —*
