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

### 1.2. Why
- 1.2.1. Kenapa Cyber?
  - 1.2.1.1. Perkembangan Digitalisasi
    - Transformasi digital di berbagai sektor (finansial, kesehatan, pemerintahan)
    - Peningkatan jumlah perangkat terkoneksi (IoT)
    - Ketergantungan bisnis pada data & sistem digital
    - Statistik pertumbuhan serangan siber dari tahun ke tahun
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
    - Regulasi terkait: UU PDP (Indonesia), GDPR (Eropa)
- 1.2.3. *(bisa tambahan)* Dampak Ekonomi Global dari Cybercrime
  - Estimasi kerugian global akibat cybercrime per tahun

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
  - Individ

---

# 2. Offensive & Defensive

## 2.0. Skillset Pillars (Fondasi Sebelum Masuk ke Offensive/Defensive)

Sebelum bahas offensive vs defensive, penting paham dulu **3 pilar skillset dasar** di cybersecurity. Ibarat segitiga — makin banyak sisi yang dikuasai, makin luas jalur karier yang terbuka.

### 2.0.1. Tiga Pilar Utama
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

### 2.0.2. Kombinasi Skillset → Jalur Karier
- **OS + Network** (tanpa Programming kuat) → System/Network Administrator, SOC Analyst, Network Security Engineer
- **Network + Programming** (tanpa OS mendalam) → Web App Pentester, Network Automation/Security Engineer, API Security
- **OS + Programming** (tanpa Network mendalam) → Malware Analyst, Reverse Engineer, Exploit Developer
- **OS + Network + Programming** (ketiganya) → Red Teamer, Full-stack Pentester, Security Researcher, CTF Player

*(Diagram segitiga akan ditampilkan terpisah di bawah)*

## 2.1. Offensive Security
- 2.1.1. Penetration Testing
  - Web App Pentest
  - Network Pentest
  - Mobile App Pentest
  - Wireless Pentest
- 2.1.2. Red Teaming
  - Simulasi serangan end-to-end (mirip attacker asli)
  - Fokus: evasion, persistence, lateral movement
- 2.1.3. Vulnerability Assessment
  - Scanning otomatis (Nessus, OpenVAS)
  - Manual verification (menghindari false positive)
- 2.1.4. Bug Bounty
  - Platform: HackerOne, Bugcrowd
  - Skill fokus: web/app vulnerability hunting

## 2.2. Defensive Security
- 2.2.1. SOC (Security Operations Center) & Monitoring
  - Tier 1/2/3 Analyst
  - Alert triage, log correlation
- 2.2.2. Blue Teaming
  - Threat hunting
  - Detection engineering
- 2.2.3. Hardening & Patch Management
  - Baseline configuration (CIS Benchmark)
  - Vulnerability remediation
- 2.2.4. Incident Response
  - Preparation → Identification → Containment → Eradication → Recovery → Lesson Learned (siklus NIST)

## 2.3. Purple Teaming
- Kolaborasi red & blue team
- Tujuan: validasi deteksi, feedback loop untuk perbaikan defense

---

# 3. How Attackers Think

## 3.1. Framework Analisis Serangan
(Jelasin kayakk, kan kalau Software Development/Web Development ada standarization kayak ISO dll. nah kalo di siber ada ginian)
- 3.1.1. Cyber Kill Chain (Lockheed Martin)
  - Reconnaissance → Weaponization → Delivery → Exploitation → Installation → Command & Control → Actions on Objectives
- 3.1.2. MITRE ATT&CK Framework
  - Tactics & Techniques (lebih granular dari Kill Chain)
  - Digunakan untuk threat intelligence & detection mapping
- OWASP
  - Web
  - Mobile
- NIST SP 800-30
- CVE & CWE

## 3.2. Mindset Penyerang
- 3.2.1. Mencari Weakest Link
  - Bukan selalu nyerang sistem tercanggih, tapi titik terlemah (manusia, konfigurasi salah, patch telat)
- 3.2.2. Cost-Benefit Analysis dari Sisi Attacker
  - Effort vs value target
  - Kenapa target "kecil" pun bisa jadi sasaran (supply chain attack)
- 3.2.3. Persistence & Stealth
  - Attacker sering tidak buru-buru — prioritas: tidak ketahuan

## 3.3. Studi Kasus
- 3.3.1. Contoh serangan nyata (walkthrough singkat, misal ransomware attack chain)
- 3.3.2. Analisis: skillset apa yang dipakai attacker di tiap tahap (kaitkan lagi ke 3 pilar skillset) & Analisis CIA Triad
