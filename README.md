## 1. Cybersecurity Intro

### 1.1. What
- 1.1.1. Penjelasan Umum
  - Definisi keamanan siber
  - Ruang lingkup: network, aplikasi, endpoint, cloud, manusia
  - Perbedaan cybersecurity vs information security vs IT security
- 1.1.2. CIA Triad
  - Confidentiality (kerahasiaan) — enkripsi, access control
  - Integrity (integritas) — hashing, checksum, version control
  - Availability (ketersediaan) — redundancy, backup, DDoS protection
  - (Opsional tambahan) Extended triad: Authentication, Non-repudiation
- 1.1.3. Threats Intro
  - Malware (virus, worm, trojan, ransomware, spyware)
  - Phishing & Social Engineering
  - DDoS Attack
  - Man-in-the-Middle (MITM)
  - SQL Injection / Web-based attack
  - Insider Threat
  - Zero-day exploit
  - Advanced Persistent Threat (APT)
- 1.1.4. Terminologi Dasar
  - Asset, Vulnerability, Threat, Risk, Exploit, Attack Vector — relasi antar istilah
  - Kenapa ini jadi "bahasa umum" yang dipakai di semua bab lain
- 1.1.5. Security Controls
  - Berdasarkan fungsi: Preventive, Detective, Corrective
  - Berdasarkan jenis: Administrative, Technical, Physical

### 1.2. Why
- 1.2.1. Kenapa Cyber?
  - 1.2.1.1. Perkembangan Digitalisasi
    - Transformasi digital di berbagai sektor (finansial, kesehatan, pemerintahan)
    - Peningkatan jumlah perangkat terkoneksi (IoT)
    - Ketergantungan bisnis pada data & sistem digital
    - Statistik pertumbuhan serangan siber dari tahun ke tahun
  - 1.2.1.2. Munculnya AI dalam Lanskap Ancaman & Pertahanan
    - AI-powered threats: deepfake, phishing hasil generate AI, automated attack tools
    - AI sebagai alat defense: anomaly detection, otomasi SOC
- 1.2.2. Data Privacy
  - Kenapa data itu berharga (data sebagai "minyak baru")
  - Jenis data sensitif: PII, data finansial, data kesehatan, kredensial
  - 1.2.2.1. Personal → Risk
    - Pencurian identitas (identity theft)
    - Penipuan finansial
    - Pemerasan (extortion/doxing)
    - Kerugian psikologis & reputasi
  - 1.2.2.2. Organizational → Risk
    - Kerugian finansial (denda regulasi, kehilangan bisnis)
    - Reputasi rusak & hilangnya kepercayaan pelanggan
    - Kebocoran rahasia dagang/kekayaan intelektual
    - Gangguan operasional (downtime)
  - **# Risk (Apa yang terjadi jika data bocor)**
    - Contoh kasus kebocoran data (bisa isi studi kasus lokal: Tokopedia, BPJS, dll — atau global: Facebook-Cambridge Analytica, Equifax)
    - Jual-beli data di dark web
    - Regulasi terkait: UU PDP (Indonesia), GDPR (Eropa), HIPAA
- 1.2.3. *(bisa tambahan)* Dampak Ekonomi Global dari Cybercrime
  - Estimasi kerugian global akibat cybercrime per tahun
  - Referensi laporan tahunan (mis. IBM Cost of a Data Breach Report)
  - Cyber insurance sebagai respons industri

### 1.3. Who
- 1.3.1. Pelaku Cybersecurity (Offensive & Defensive)
  - **Defensive (Blue Team)**: Security Analyst, SOC Analyst, Incident Responder, CISO
  - **Offensive (Red Team)**: Pentester, Ethical Hacker, Bug Hunter
  - **Netral/Support**: Security Researcher, Auditor, Compliance Officer
- 1.3.2. Pelaku Ancaman (Threat Actors)
  - Script Kiddie
  - Hacktivist
  - Cybercriminal (motif finansial)
  - Nation-state Actor (motif politik/spionase)
  - Insider Threat (karyawan/orang dalam)
  - Organized Cybercrime Group
  - Raas & Maas (Ransomware/Malware-as-a-service)

### 1.4. Where
- 1.4.1. Attack Surface
  - Jaringan (network layer)
  - Aplikasi & website
  - Endpoint (laptop, smartphone, IoT device)
  - Cloud infrastructure
  - Manusia (human layer — social engineering)
- 1.4.2. Lingkungan Penerapan
  - Perusahaan/korporat
  - Infrastruktur kritis (listrik, air, transportasi, perbankan)
  - Pemerintahan
  - Individu
  - Pendidikan
  - UMKM

### 1.5. When
- 1.5.2. Kapan Security Harus Diterapkan
  - Security by Design vs security sebagai "tempelan" belakangan
  - Shift-left security dalam SDLC
  - Continuous monitoring, bukan usaha satu kali

## 2. Offensive & Defensive

### 2.0. Skillset Pillars (Fondasi Sebelum Masuk ke Offensive/Defensive)

Sebelum bahas offensive vs defensive, penting paham dulu **3 pilar skillset dasar** di cybersecurity. Ibarat segitiga — makin banyak sisi yang dikuasai, makin luas jalur karier yang terbuka.

#### 2.0.1. Tiga Pilar Utama
- **A. Operating System (OS)**
  - Linux fundamentals (permission, file system, process, service)
  - Windows internals (registry, Active Directory, PowerShell)
  - Command line proficiency (bash, PowerShell, cmd)
  - System hardening & privilege management
  - Log & file system forensics dasar

- **B. Network**
  - TCP/IP model & OSI layer
  - Protokol umum (HTTP/S, DNS, FTP, SMB, SSH)
  - Routing & switching dasar
  - Firewall, VPN, proxy
  - Packet analysis (Wireshark, tcpdump)

- **C. Programming/Scripting**
  - Bahasa scripting (Python, Bash) untuk otomasi
  - Bahasa low-level (C/C++) untuk paham memory & exploit
  - Web dev dasar (HTML, JS, SQL) untuk paham web vuln
  - Membaca & modifikasi source code (bukan cuma nulis dari nol)

#### 2.0.2. Kombinasi Skillset → Jalur Karier
- **OS + Network** (tanpa Programming kuat) → System/Network Administrator, SOC Analyst, Network Security Engineer
- **Network + Programming** (tanpa OS mendalam) → Web App Pentester, Network Automation/Security Engineer, API Security
- **OS + Programming** (tanpa Network mendalam) → Malware Analyst, Reverse Engineer, Exploit Developer
- **OS + Network + Programming** (ketiganya) → Red Teamer, Full-stack Pentester, Security Researcher, CTF Player

*(Diagram segitiga akan ditampilkan terpisah di bawah)*

### 2.1. Offensive Security
- 2.1.1. Penetration Testing
  - Web App Pentest
  - Network Pentest
  - Mobile App Pentest
  - Wireless Pentest
  - Social Engineering Pentest
  - 2.1.1. Jenis Pentest
    - Black Box
    - Grey Box
    - White Box
- 2.1.2. Red Teaming
  - Simulasi serangan end-to-end (mirip attacker asli)
  - Fokus: evasion, persistence, lateral movement
- 2.1.3. Vulnerability Assessment
  - Scanning otomatis (Nessus, OpenVAS)
  - Manual verification (menghindari false positive)
  - CVSS Scoring untuk menilai severity
- 2.1.4. Bug Bounty
  - Platform: HackerOne, Bugcrowd; Skill fokus: web/app vulnerability hunting
  - Responsible/Coordinated Disclosure
- 2.1.5. Tools
  - Burpsuite
  - Wireshark
  - ZAP
  - FFUF
  - Censys
  - Curl
  - dll.

### 2.2. Defensive Security
- 2.2.1. SOC (Security Operations Center) & Monitoring
  - Tier 1/2/3 Analyst, Alert triage, log correlation
- 2.2.2. Blue Teaming
  - Threat hunting
  - Detection engineering
  - Deception (Honeypot, Honeytoken)
- 2.2.3. Hardening & Patch Management
  - Baseline configuration (CIS Benchmark)
  - Vulnerability remediation
  - Zero Architecture
- 2.2.4. Incident Response
  - Preparation → Identification → Containment → Eradication → Recovery → Lesson Learned (siklus NIST)
  - Digital Forensic

### 2.3. Purple Teaming
- Kolaborasi red & blue team
- Tujuan: validasi deteksi, feedback loop untuk perbaikan defense

## 3. How Attackers Think

### 3.1. Framework Analisis Serangan
(Jelasin kayakk, kan kalau Software Development/Web Development ada standarization kayak ISO dll. nah kalo di siber ada ginian)
- 3.1.1. Cyber Kill Chain (Lockheed Martin)
  - Reconnaissance → Weaponization → Delivery → Exploitation → Installation → Command & Control → Actions on Objectives
- 3.1.2. MITRE ATT&CK Framework
  - Tactics & Techniques (lebih granular dari Kill Chain)
  - Digunakan untuk threat intelligence & detection mapping
- 3.1.3. OWASP
  - Web (OWASP Top 10)
  - Mobile (OWASP MASVS)
  - AI/LLM (OWASP Top 10 for LLM Applications) — makin relevan belakangan ini
- 3.1.4. NIST SP 800-30
  - Ditambah NIST Cybersecurity Framework (CSF) sebagai pelengkap yang lebih luas — sekarang 6 fungsi sejak CSF 2.0: Govern, Identify, Protect, Detect, Respond, Recover
- 3.1.5. CVE & CWE
  - Hubungan dengan CVSS (severity scoring)
  - NVD (National Vulnerability Database) sebagai database referensi

### 3.2. Mindset Penyerang
- 3.2.1. Mencari Weakest Link
  - Bukan selalu nyerang sistem tercanggih, tapi titik terlemah (manusia, konfigurasi salah, patch telat)
- 3.2.2. Cost-Benefit Analysis dari Sisi Attacker
  - Effort vs value target
  - Kenapa target "kecil" pun bisa jadi sasaran (supply chain attack)
- 3.2.3. Persistence & Stealth
  - Attacker sering tidak buru-buru — prioritas: tidak ketahuan

### 3.3. Studi Kasus
- 3.3.1. Contoh serangan nyata (walkthrough singkat, misal ransomware attack chain)
- 3.3.2. Analisis: skillset apa yang dipakai attacker di tiap tahap (kaitkan lagi ke 3 pilar skillset) & Analisis CIA Triad

## 4. Demo (Hands-on Lab — Blackbox Simulation)

### 4.1. Sesi Offensive (Attacker Side)

#### 4.1.1. Reconnaissance
- Port scanning ke target (`nmap -sV -p- <target-ip>`)
- Identifikasi service & versi yang berjalan (fingerprinting)
- Temukan database port yang exposed (misal port 3306/5432/27017 terbuka tanpa autentikasi/filtering)
- Enumerasi endpoint aplikasi web (manual browsing / directory brute-force)

#### 4.1.2. Exploitation — Database Exposed
- Coba koneksi langsung ke database dari luar (`mysql -h <target-ip> -u root`)
- Demonstrasi: kalau credential default/lemah, langsung bisa masuk tanpa lewat aplikasi sama sekali
- Tunjukkan risiko: data bisa diakses/diekstrak langsung dari luar tanpa exploit rumit — cukup karena kesalahan konfigurasi (network exposure)

#### 4.1.3. Exploitation — BOLA di Aplikasi
- Login sebagai user A, ambil token/session
- Coba akses endpoint dengan mengganti `id` milik user lain (misal `id=1` → `id=2`)
- Tunjukkan aplikasi tidak melakukan object-level authorization check → data user lain bisa diakses (data leakage)
- Screenshot/log request-response sebagai bukti (evidence)

#### 4.1.4. Menghitung CVSS Score
- Breakdown metric CVSS v3.1/v4.0 untuk kedua temuan:
  - **Attack Vector (AV)** — Network
  - **Attack Complexity (AC)** — Low/High
  - **Privileges Required (PR)** — None/Low
  - **User Interaction (UI)** — None
  - **Scope (S)** — Unchanged/Changed
  - **Confidentiality/Integrity/Availability Impact (C/I/A)**
- Hitung skor akhir & tentukan severity (Low/Medium/High/Critical) pakai kalkulator resmi FIRST.org
- Bandingkan skor temuan 1 (DB exposed) vs temuan 2 (BOLA) — diskusikan kenapa bisa beda severity

#### 4.1.5. Membuat Laporan (Reporting)
- Struktur laporan pentest sederhana:
  - Executive Summary
  - Scope & Methodology
  - Findings (per temuan): deskripsi, bukti, CVSS score, affected endpoint/asset
  - Impact & Risk Rating
  - Rekomendasi remediasi
- Latihan: peserta bikin 1 halaman laporan dari temuan yang baru saja didapat

### 4.2. Sesi Defensive (Defender Side)

#### 4.2.1. Remediasi — Database Exposed
- Konfigurasi firewall (`ufw`/`iptables`/security group cloud) agar port database hanya bisa diakses dari internal network/application server, bukan dari luar
- Best practice tambahan:
  - Bind database ke `localhost`/internal IP saja, bukan `0.0.0.0`
  - Ganti/hapus credential default
  - Terapkan network segmentation (DB di subnet terpisah dari public-facing app)

#### 4.2.2. Remediasi — BOLA
- Tambahkan middleware/authorization check di endpoint yang rentan:
  - Validasi bahwa `id` yang diminta memang milik user yang sedang login (ownership check)
  - Terapkan prinsip least privilege di level object, bukan cuma level endpoint
- Contoh pola perbaikan (pseudocode):
  ```
  if requested_resource.owner_id != current_user.id:
      return 403 Forbidden
  ```
- Tambahkan logging untuk percobaan akses tidak sah (buat deteksi ke depannya)

#### 4.2.3. Verifikasi Perbaikan
- Ulangi langkah exploitation di 4.1.2 dan 4.1.3 — pastikan sekarang gagal (403/connection refused)
- Bandingkan before-after: tunjukkan hasil scan/request sebelum vs sesudah patch

#### 4.2.4. Update Laporan
- Tambahkan status **"Remediated"** di laporan pentest
- Diskusi: kenapa retest itu penting sebelum laporan ditutup

### 4.3. Wrap-up & Diskusi
- 4.3.1. Rekap siklus lengkap: Recon → Exploit → Assess (CVSS) → Report → Remediate → Verify — mirror dari siklus offensive-defensive di Bab 2
- 4.3.2. Kaitkan lagi ke pilar skillset (Bab 2.0):
  - Recon & exploit DB butuh **Network**
  - Exploit BOLA & bikin middleware butuh **Programming**
  - Firewall & permission butuh **OS**
- 4.3.3. Q&A / Diskusi terbuka
