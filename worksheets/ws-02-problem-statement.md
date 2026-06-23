# WS-02: Problem Statement

> **Bab 2 — Problem Formulation & System Context**

---

## Ringkasan Materi

### Problem Formation Model

Masalah riset melewati 5 tahap transformasi. Melompat langsung dari Reality ke Variable adalah kesalahan paling umum.

```
Reality → Observed Issue (Symptom) → Diagnosed Problem (Root Cause)
→ Researchable Problem (Scoped) → Measurable Variable (Operationalized)
```

### Topic ≠ Problem ≠ Research Problem

| Level | Contoh | Status |
|-------|--------|--------|
| **Topik** | Keamanan IoT | Terlalu luas, tidak bisa diuji |
| **Problem** | MQTT tidak terenkripsi | Spesifik tapi belum riset |
| **Research Problem** | Belum ada studi membandingkan overhead TLS 1.3 vs DTLS pada MQTT di IoT RAM < 64KB | Bisa dirancang eksperimennya |

### Symptom vs Root Cause

Apa yang diamati (gejala) ≠ mengapa terjadi (akar masalah). Gunakan **5 Whys** atau **Fishbone Diagram** untuk menggali.

Contoh: "User meninggalkan checkout" (symptom) → "Waktu loading > 8 detik karena API call sequential" (root cause).

### System Thinking

Setiap masalah riset TI harus terikat pada komponen sistem: **Input → Process → Output → Outcome → Constraints → Stakeholders**.

### Problem Quality Check

Masalah riset yang layak harus memenuhi 5 kriteria:
- **Clarity** — Satu orang membaca akan paham
- **Measurability** — Ada metrik kuantitatif
- **Relevance** — Penting untuk domain
- **Testability** — Bisa gagal (falsifiable)
- **Impact** — Ada kontribusi jika terjawab

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan | Menyelesaikan masalah (*solve*) | Memahami dan membuktikan (*understand & prove*) |
| Masalah | Bug, error, fitur belum ada | Gap dalam pengetahuan |
| Scope | Selesaikan semua yang perlu | Batasi agar bisa dibuktikan |
| Output | Working system | Evidence, paper, replicable findings |

### Istilah Penting

- **Problem Statement** — Formulasi tertulis: konteks sistem + gap + dampak + justifikasi
- **System Context** — Deskripsi lengkap: input, proses, output, outcome, constraints, stakeholders
- **Problem Drift** — Masalah "bermutasi" dari pendahuluan ke metodologi karena statement awal tidak presisi
- **Solution-First Thinking** — Memulai dari solusi tanpa masalah yang jelas — berbahaya dalam riset
- **Operational Definition** — Definisi variabel yang cukup jelas agar peneliti lain bisa mengukur hal yang sama

---

## Template A.2 — Problem Statement Builder

```
PROBLEM STATEMENT BUILDER

Domain & Konteks
  Domain   : ____________________
  Konteks  : ____________________

System Context
  Input       : ____________________
  Process     : ____________________
  Output      : ____________________
  Outcome     : ____________________
  Constraints : ____________________
  Stakeholders: ____________________

Fenomena → Problem
  Fenomena yang diamati             : ____________________
  Gejala (symptom) yang terukur     : ____________________
  Masalah yang didiagnosis          : ____________________
  Masalah riset (researchable)      : ____________________
  Variabel yang terukur             : ____________________

Problem Quality Check
  [ ] Clarity — Apakah satu orang membaca akan paham?
  [ ] Measurability — Apakah ada metrik kuantitatif?
  [ ] Relevance — Apakah penting untuk domain?
  [ ] Testability — Apakah bisa gagal?
  [ ] Impact — Apakah ada kontribusi jika terjawab?

Problem Statement (1 paragraf):
  ____________________
```

---

## Latihan 1 — Dari Topik ke Masalah Riset

Pilih satu topik di bidang TI yang diminati. Transformasikan melalui 5 tahap Problem Formation Model.

**Topik awal:** Risiko Keamanan Siber pada Sistem Pemerintahan Berbasis Elektronik (SPBE).________________________________________

| Tahap | Hasil |
|-------|-------|
| Reality | Transformasi digital sedang dijalankan untuk mengintegrasikan pelayanan publik di Indonesia. |
| Observed Issue (Symptom) | Adanya ratusan juta serangan siber per tahun dan rendahnya implementasi SPBE (hanya 2,89% institusi berpredikat sangat baik). |
| Diagnosed Problem (Root Cause) |Kerentanan sistem akibat integrasi big data yang belum dibarengi dengan arsitektur keamanan dan kesadaran SDM yang memadai. |
| Researchable Problem |Bagaimana merancang strategi mitigasi risiko keamanan siber yang mencakup pilar teknologi, manusia, dan tata kelola untuk melindungi layanan publik digital? |
| Measurable Variable |Indeks kematangan SPBE, frekuensi serangan siber, dan skor Natural Cyber Security Index (NCSI) Indonesia. |

**Apakah terjebak solution-first thinking?** [ ] Ya / [x] Tidak
> Jika ya, kembali ke tahap mana? ________________________

---

## Latihan 2 — System Context Decomposition

Gambarkan konteks sistem dari masalah riset di Latihan 1.

| Komponen | Deskripsi |
|----------|----------|
| Input | Data pribadi masyarakat, riwayat transaksi, dan akses masuk ASN. |
| Process |Pengelolaan data melalui arsitektur SPBE dan integrasi machine learning. |
| Output |Layanan publik digital yang terintegrasi (kesehatan, pendidikan, keuangan). |
| Outcome |Kualitas pelayanan publik yang lebih efisien, transparan, dan inklusif. |
| Constraints |Kesenjangan anggaran antar daerah, perbedaan kapasitas digital, dan belum adanya arus utama regulasi pelindungan data. |
| Stakeholders |Pemerintah pusat, pemerintah daerah, ASN, dan masyarakat.|

**Komponen mana yang paling relevan dengan masalah riset?** __Process (karena di sinilah titik kerentanan integrasi data dan ancaman siber terjadi)._____________

---

## Latihan 3 — Problem Quality Check

Evaluasi problem statement yang sudah dibuat menggunakan 5 kriteria.

| Kriteria | Skor (1-5) | Justifikasi |
|----------|-----------|-------------|
| Clarity | 5 |Masalah sangat spesifik pada sektor pelayanan publik. |
| Measurability |4 |Terdapat data statistik serangan dan indeks evaluasi SPBE |
| Relevance |5 |Sangat relevan dengan tantangan transformasi digital nasional. |
| Testability |4 |Strategi mitigasi dapat divalidasi melalui kerangka tata kelola. |
| Impact | 5|Berdampak pada ketahanan nasional dan pelindungan data pribadi. |

**Skor total:** 23/ 25

**Problem statement versi final (1 paragraf):**
> _Penelitian ini bertujuan untuk menganalisis risiko keamanan siber pada sistem pelayanan publik terintegrasi di Indonesia dengan mengevaluasi tiga pilar pembangunan siber—teknologi, manusia, dan tata kelola—guna merumuskan strategi mitigasi yang efektif untuk memastikan keberlanjutan dan ketahanan sistem pelayanan publik di era transformasi digital__________________________________________________
> ___________________________________________________

---

## Refleksi

> Bandingkan "masalah" yang biasa ditemui saat coding (bug, error) dengan masalah riset. Apa perbedaan fundamental dalam cara mendefinisikan dan mendekati keduanya?

**Jawaban:**
Masalah coding bersifat teknis dan deterministik; ia memiliki kondisi yang jelas antara benar atau salah, sehingga solusinya seringkali sudah tersedia melalui debugging atau perbaikan sintaks. Sebaliknya, masalah riset bersifat sistemik dan kompleks; ia tidak memiliki jawaban tunggal yang mutlak dan memerlukan sintesis dari berbagai aspek—seperti kebijakan, perilaku manusia, dan infrastruktur teknis—untuk memahami dan memitigasi risikonya secara holistik dalam skala nasional.
> 
