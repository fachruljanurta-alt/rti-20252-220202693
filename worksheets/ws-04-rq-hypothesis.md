# WS-04: Research Question & Hypothesis

> **Bab 4 — Research Question, Contribution & Hypothesis**

---

## Ringkasan Materi

### RQ Bukan Pertanyaan Biasa

Research Question yang baik secara implisit mengandung cetak biru eksperimen: subjek, baseline, metrik, domain, dataset.

| Kualitas | Contoh |
|----------|--------|
| **Buruk** | "Bagaimana pengaruh deep learning terhadap deteksi malware?" |
| **Baik** | "Apakah CNN menghasilkan F1-Score lebih tinggi dari RF pada CIC-MalMem-2022?" |

Perbedaan: RQ yang baik menyebutkan **metode spesifik**, **metrik terukur**, **baseline**, dan **dataset**.

### Tiga Jenis RQ

| Jenis | Pola | Kebutuhan |
|-------|------|-----------|
| **Comparison** | A vs B → mana lebih baik? | ≥ 2 metode, metrik sama |
| **Improvement** | A' vs A → modifikasi lebih baik? | Pre/post, bukti perbaikan |
| **Exploratory** | Faktor X₁...Xₙ → pengaruh terhadap Y? | Multi-variabel, korelasi/regresi |

### Contribution Statement

Tiga jenis kontribusi: **Improvement** (metode terbukti lebih baik), **Comparison** (perbandingan sistematis yang belum ada), **Novel Approach** (pendekatan baru). Kontribusi harus terhubung langsung dengan gap — kontribusi tanpa gap = klaim tanpa justifikasi.

### Hypothesis H₀ / H₁

- **H₀** (Null) = Tidak ada perbedaan signifikan — asumsi default, harus dibuktikan salah
- **H₁** (Alternative) = Ada perbedaan signifikan — diterima hanya jika H₀ ditolak
- Harus **falsifiable**, mengandung **metrik terukur**, dirumuskan **SEBELUM eksperimen**

### Rantai Operasionalisasi

```
RQ → Variable → Metric → Data → Analysis
```

Jika rantai ini tidak lengkap, RQ belum mature. Bi-directional: RQ yang tidak bisa jadi hipotesis testable harus direvisi mundur.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan pertanyaan | Apa yang harus dibangun? | Apa yang harus dibuktikan? |
| Bentuk jawaban | Sistem yang berfungsi | Bukti empiris terukur |
| Sukses diukur oleh | User satisfaction, uptime | Signifikansi statistik, effect size |
| Jika gagal | Debug dan perbaiki | Laporkan, analisis mengapa |

### Istilah Penting

- **Research Question (RQ)** — Pertanyaan spesifik: variabel terukur + metrik + konteks
- **Contribution Statement** — Apa yang diketahui setelah riset selesai yang sebelumnya belum ada
- **H₀ / H₁** — Null vs Alternative Hypothesis
- **Falsifiability** — Kondisi hipotesis ditolak harus bisa didefinisikan sebelum eksperimen
- **Operationalization** — Proses mewujudkan konsep abstrak menjadi variabel terukur

---

## Template A.4 — RQ-Contribution-Hypothesis

```
RQ-CONTRIBUTION-HYPOTHESIS

Gap Statement  : ____________________

Research Question:
  Tipe         : [ ] Comparison  [ ] Improvement  [ ] Exploratory
  Formulasi    : ____________________
  Variabel IV  : ____________________
  Variabel DV  : ____________________
  Metrik       : ____________________
  Dataset      : ____________________
  Baseline     : ____________________

Quality Check RQ:
  [ ] Variabel spesifik
  [ ] Metrik jelas
  [ ] Baseline ada
  [ ] Konteks disebutkan
  [ ] Memerlukan eksperimen (bukan hanya survei literatur)

Contribution Statement:
  Apa yang baru diketahui : ____________________
  Jenis kontribusi        : [ ] Improvement  [ ] Comparison  [ ] Novel approach
  Gap yang diisi          : ____________________

Hypothesis Pair:
  H₀ : ____________________
  H₁ : ____________________
  Threshold              : ____________________
  Justifikasi threshold  : ____________________
```

---

## Latihan 1 — Dari Gap ke RQ

Gunakan gap yang ditemukan di WS-03. Transformasikan menjadi Research Question.

**Gap dari WS-03:** Belum adanya model mitigasi risiko keamanan siber yang seragam dan terintegrasi untuk mendukung interoperabilitas data antar instansi pada "Satu Data Indonesia" di tingkat Pemerintah Daerah.____________________________________

**RQ versi pertama (tulis bebas):**
> Bagaimana cara membuat sistem keamanan siber yang aman untuk pelayanan publik di daerah agar tidak diretas?___________________________________________________

**Evaluasi RQ:**

| Komponen | Ada? | Isi |
|----------|------|-----|
| Metode spesifik | Tidak |Masih terlalu umum |
| Metrik terukur |Tidak |Tidak ada tolok ukur keberhasilan |
| Baseline |Tidak |Tidak ada pembanding   |
| Dataset/konteks |Ya |Pelayanan publik di daerah |

**Tipe RQ:** [ ] Comparison / [ ] Improvement / [ x] Exploratory

**RQ versi revisi (setelah evaluasi):**
> "Bagaimana efektivitas kerangka kerja tata kelola keamanan siber berbasis standar ISO 27001 dibandingkan dengan praktik mandiri yang saat ini digunakan dalam memitigasi risiko kebocoran data pada sistem pelayanan publik di pemerintah daerah?"___________________________________________________

---

## Latihan 2 — Hypothesis Pair

Rumuskan pasangan hipotesis dari RQ di Latihan 1.

| Komponen | Isi |
|----------|-----|
| H₀ | Tidak ada perbedaan signifikan dalam tingkat insiden keamanan data antara pemerintah daerah yang menerapkan ISO 27001 dengan yang tidak. |
| H₁ |Penerapan kerangka kerja ISO 27001 secara signifikan menurunkan frekuensi insiden kebocoran data dibandingkan dengan praktik mandiri. |
| Metrik |Jumlah insiden kebocoran data (per kuartal) dan Indeks Kematangan SPBE. |
| Threshold |Penurunan sebesar 30% dari tingkat insiden dasar (baseline). |
| Justifikasi threshold |Berdasarkan standar rata-rata peningkatan efisiensi keamanan siber pada organisasi sektor publik yang telah mengadopsi standarisasi tata kelola. |

**Apakah hipotesis ini falsifiable?** [ x] Ya / [ ] Tidak
> Bagaimana cara membuktikannya salah? Jika setelah penerapan ISO 27001, jumlah insiden kebocoran data justru meningkat atau tidak berubah secara statistik signifikan dibandingkan sebelum penerapan.___________________

---

## Latihan 3 — Rantai Operasionalisasi

Lengkapi rantai dari RQ hingga metode analisis.

| Tahap | Isi |
|-------|-----|
| RQ | Efektivitas ISO 27001 dalam memitigasi risiko kebocoran data pada layanan publik. |
| Variable (IV) | Penerapan kerangka kerja ISO 27001 (Ya/Tidak). |
| Variable (DV) |Tingkat insiden keamanan data (Kebocoran data). |
| Metric |Frekuensi insiden per tahun dan skor kematangan keamanan siber (BSSN). |
| Data source |Laporan insiden BSSN dan kuesioner audit mandiri instansi pemerintah. |
| Analysis method |Uji beda statistik (T-Test) atau Analisis komparatif deskriptif. |

**Apakah rantai lengkap?** [x ] Ya / [ ] Tidak
> Jika tidak, tahap mana yang perlu direvisi? ______________

---

## Refleksi

> Ambil satu judul skripsi/paper yang pernah dibaca. Coba ekstrak RQ-nya. Apakah RQ tersebut memenuhi semua komponen (metode, metrik, baseline, konteks)? Jika tidak, apa yang hilang?

**Judul:** "Analisis Risiko Keamanan Siber dalam Transformasi Digital Pelayanan Publik di Indonesia" (Alfi et al., 2023)._____________________________________________
**RQ yang diekstrak:** (Secara implisit) "Bagaimana risiko keamanan siber dalam transformasi digital pelayanan publik dan bagaimana strategi mitigasinya?"__________________________________
**Komponen yang hilang:**RQ pada makalah tersebut bersifat sangat eksploratif (kualitatif). Komponen yang hilang adalah Baseline (apa standar keamanan saat ini yang dibandingkan?) dan Metrik terukur (bagaimana kuantifikasi "keamanan" tersebut?). Karena makalah ini bersifat studi strategi, RQ-nya lebih fokus pada deskripsi masalah daripada pengukuran performa, yang membuat evaluasinya sulit jika hanya menggunakan metrik teknis. _______________________________
