# WS-07: Experimental Design & Validity

> **Bab 7 — Experimental Design & Validity**

---

## Ringkasan Materi

### Correlation ≠ Causality

Kausalitas membutuhkan 3 syarat:
1. **Covariance** — X dan Y bergerak bersama
2. **Temporal precedence** — X berubah sebelum Y
3. **Elimination of alternatives** — Tidak ada faktor lain yang menjelaskan Y

Controlled experiment adalah satu-satunya metode yang bisa membuktikan kausalitas.

### Empat Jenis Validitas

| Jenis | Pertanyaan | Ancaman Umum |
|-------|-----------|-------------|
| **Internal** | Apakah hubungan IV→DV nyata? | Confounding variable, selection bias |
| **External** | Apakah bisa digeneralisasi? | Dataset terlalu spesifik |
| **Construct** | Apakah mengukur konsep yang benar? | Metrik tidak sesuai |
| **Conclusion** | Apakah kesimpulan statistik valid? | Sample size kecil, uji salah |

Internal dan external validity sering berkonflik: semakin terkontrol (internal kuat) → semakin artificial (external lemah).

### Tiga Tipe Eksperimen dalam Riset TI

| Tipe | Deskripsi | Kapan Digunakan |
|------|----------|----------------|
| **Comparison Study** | Metode A vs B pada kondisi identik | Membandingkan pendekatan berbeda |
| **Ablation Study** | Full system → lepas komponen satu per satu | Mengukur kontribusi tiap komponen |
| **Parameter Study** | Variasikan satu parameter, amati dampak | Uji sensitifitas/robustness |

### Fairness dalam Perbandingan

Perbandingan yang adil = **kondisi identik** untuk semua metode: dataset sama, preprocessing sama, tuning effort sebanding, environment sama, metrik sama.

Contoh tidak adil: Transformer (30 fitur tambahan + Bayesian optimization) vs RF (default params) → hasilnya misleading.

### Threats to Validity = Diidentifikasi Sebelum Eksperimen

Ancaman validitas harus diidentifikasi **sebelum** eksperimen dan mitigasinya dirancang sebagai bagian dari desain — bukan ditulis sebagai boilerplate setelah selesai.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan testing | Memastikan sistem memenuhi requirement | Membuktikan hubungan kausal antar variabel |
| Baseline | Versi sebelumnya (last release) | Metode tervalidasi dari literatur |
| Kegagalan | Bug → fix → release | H₀ tidak ditolak → tetap kontribusi ilmiah |
| Sukses | 100% test pass | Evidence valid — mendukung atau menolak hipotesis |

### Istilah Penting

- **Causality** — Hubungan sebab-akibat (covariance + temporal + elimination)
- **Controlled Experiment** — Ubah satu variabel, kontrol sisanya, amati efek
- **Fairness** — Semua metode diuji pada kondisi yang benar-benar identik
- **Threats to Validity** — Faktor yang bisa melemahkan kesimpulan jika tidak dimitigasi
- **Conclusion Validity** — Validitas statistik: power, sample size, uji yang tepat

---

## Template A.7 — Desain Eksperimen Lengkap

```
EXPERIMENT DESIGN

Research Question : ____________________
Hypothesis        : ____________________
Tipe Eksperimen   : [ ] Comparison  [ ] Ablation  [ ] Parameter

Kondisi Eksperimen:
| Kondisi | Deskripsi | IV Value | CV Settings |
|---------|-----------|----------|-------------|
| Control |           |          |             |
| Treatment |         |          |             |

Fairness Checklist:
  [ ] Dataset identik untuk semua kondisi
  [ ] Preprocessing setara
  [ ] Tuning effort setara
  [ ] Environment identik
  [ ] Metrik evaluasi sama

Threat Analysis:
| Threat Type | Ancaman Spesifik | Mitigasi |
|-------------|-----------------|----------|
| Internal    |                 |          |
| External    |                 |          |
| Construct   |                 |          |
| Conclusion  |                 |          |

Statistical Plan:
  Uji statistik   : ____________________
  Justifikasi      : ____________________
  Alpha            : ____________________
  Effect size min  : ____________________
```

---

## Latihan 1 — Desain Eksperimen

Susun desain eksperimen berdasarkan RQ, variabel, dan sistem dari WS-04 sampai WS-06.

**RQ:**"Bagaimana efektivitas kerangka kerja tata kelola keamanan siber berbasis standar ISO 27001 dibandingkan dengan praktik mandiri dalam memitigasi risiko kebocoran data pada sistem pelayanan publik di pemerintah daerah?" __________________________________________________
**Tipe eksperimen:** [x ] Comparison / [ ] Ablation / [ ] Parameter

| Kondisi | Deskripsi | IV Value | CV Settings |
|---------|-----------|----------|-------------|
| Control | Praktik keamanan siber mandiri (tanpa standar baku) | Praktik Mandiri | Infrastruktur daerah (tipe A), SDM tingkat menengah |
| Treatment |Penerapan standar ISO 27001 (SOP, Audit, Monitoring) |ISO 27001 | Infrastruktur daerah (tipe A), SDM tingkat menengah|

---

## Latihan 2 — Fairness Checklist

Evaluasi apakah desain eksperimen di Latihan 1 sudah fair.

| Kriteria | Status | Detail |
|----------|--------|--------|
| Dataset identik |  ✅  | Data insiden diambil dari periode waktu (2022-2023) yang sama.|
| Preprocessing setara |✅ | Kategorisasi "jenis insiden" diseragamkan untuk kedua kondisi.|
| Tuning effort setara | ✅|Keduanya diuji pada organisasi pemerintah dengan skala infrastruktur serupa. |
| Environment identik |✅ | Lingkungan birokrasi dan skala pelayanan publik setara.|
| Metrik evaluasi sama |✅ |Menggunakan frekuensi insiden dan skor kematangan keamanan siber. |

**Ada yang tidak fair?** [ ] Ya / [x ] Tidak
> Jika ya, bagaimana cara memperbaikinya? ________________

---

## Latihan 3 — Threat Analysis

Identifikasi ancaman validitas untuk desain eksperimen ini.

| Threat Type | Ancaman Spesifik | Mitigasi |
|-------------|-----------------|----------|
| Internal | Variasi kualitas SDM antar instansi daerah. | Gunakan variabel kontrol (usia/tingkat pendidikan/pelatihan IT ASN). |
| External |Perbedaan jenis ancaman siber yang diterima tiap daerah. | Gunakan data agregat BSSN yang dikategorikan berdasarkan jenis serangan.|
| Construct |"Insiden" mungkin tidak dilaporkan di daerah yang kurang sistematis. |Validasi data dengan audit pihak ketiga (BSSN) sebagai pembanding. |
| Conclusion |Jumlah sampel instansi yang terbatas untuk generalisasi nasional. |Memperbanyak jumlah sampel instansi (minimal 20-30 daerah). |

**Ancaman mana yang paling sulit dimitigasi?**Construct Ability _____________
**Mengapa?**
> Karena di Indonesia, terdapat budaya reluctance to report (keengganan melaporkan) atas kegagalan sistem keamanan di tingkat instansi pemerintah karena takut sanksi atau citra buruk. Hal ini membuat data yang tersedia tidak selalu mencerminkan realitas.___________________________________________________

---

## Refleksi

> Sebuah paper melaporkan "metode kami mengalahkan semua baseline." Apa 3 pertanyaan pertama yang harus diajukan untuk mengevaluasi klaim ini?

**Jawaban:**
1. _"Apakah kondisi eksperimen (tuning, dataset, hardware) benar-benar setara bagi metode Anda dan baseline?" (Untuk memastikan tidak ada keunggulan buatan).__________________________________________________
2."Apakah baseline yang digunakan sudah merupakan SOTA (State of the Art) terbaru, atau hanya baseline usang yang mudah dikalahkan?" (Untuk memastikan validitas perbandingan). ___________________________________________________
3. "Apakah signifikansi statistik diuji dengan benar, atau hanya kebetulan pada satu titik evaluasi saja?" (Untuk memastikan hasil bukan karena keberuntungan/kebetulan data).___________________________________________________
