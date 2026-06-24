# WS-05: Variabel & Metrik

> **Bab 5 — Metric, Measurement & Data**

---

## Ringkasan Materi

### Measurement Alignment Model

Setiap pengukuran yang valid harus bisa ditelusuri melalui rantai ini tanpa lompatan logis:

```
Problem → Concept → Variable → Metric → Data → Result
```

### Operationalization = Keputusan Desain

Menerjemahkan konsep abstrak menjadi variabel terukur bukan proses mekanis. "Code quality" yang diukur via SonarQube code smells membawa asumsi implisit. Setiap operasionalisasi harus didokumentasikan dan dijustifikasi.

### Empat Tipe Data (NOIR)

| Tipe | Ciri | Contoh | Operasi Valid |
|------|------|--------|---------------|
| **Nominal** | Kategori, tanpa urutan | Jenis algoritma (RF, SVM, CNN) | Modus, chi-square |
| **Ordinal** | Urutan, interval tidak sama | Skala Likert (1-5) | Median, Spearman |
| **Interval** | Jarak bermakna, tanpa nol absolut | Suhu Celsius | Mean, Pearson, t-test |
| **Ratio** | Jarak bermakna + nol absolut | Waktu eksekusi (ms) | Semua operasi |

Tipe data menentukan uji statistik yang valid. Kebanyakan metrik performa TI = ratio; persepsi pengguna = ordinal.

### Kriteria Pemilihan Metrik

- **Representative** — Mewakili konsep yang diteliti
- **Sensitive** — Cukup peka menangkap perbedaan bermakna (hindari ceiling effect)
- **Feasible** — Bisa dikumpulkan dalam batasan waktu dan biaya

### Pre-registration

Metrik harus ditentukan **sebelum** eksperimen. Memilih metrik setelah melihat data = **p-hacking**. Metrik tambahan yang ditemukan kemudian dilaporkan sebagai *exploratory*, bukan *confirmatory*.

### Primary vs Secondary Metric

- **Primary Metric** — Langsung terikat ke hipotesis, menentukan kesimpulan
- **Secondary Metric** — Pendukung, dilaporkan di samping primary; statusnya suplementer

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Pemilihan metrik | Berdasarkan kebiasaan/tool yang ada | Berdasarkan construct validity |
| Anomali | Dihapus untuk laporan bersih | Diinvestigasi — bisa jadi temuan |
| Kapan dipilih | Setelah sistem jadi (monitoring) | Sebelum eksperimen (by design) |

### Istilah Penting

- **Operationalization** — Transformasi konsep abstrak menjadi variabel terukur
- **Construct Validity** — Sejauh mana pengukuran benar-benar mengukur konsep yang dimaksud
- **Measurement Scale** — Klasifikasi data (NOIR) yang menentukan analisis valid
- **Multi-metric Evaluation** — Menggunakan beberapa metrik untuk menangkap konsep kompleks

---

## Template A.5 — Definisi Variabel, Metrik & Justifikasi

```
VARIABLE & METRIC DEFINITION

Research Question: ____________________

| Variabel | Tipe | Konsep | Metrik | Skala | Satuan | Cara Mengukur | Justifikasi |
|----------|------|--------|--------|-------|--------|---------------|-------------|
|          | IV   |        |        |       |        |               |             |
|          | DV   |        |        |       |        |               |             |
|          | CV   |        |        |       |        |               |             |

Alignment Check:
  RQ → Concept → Variable → Metric → Data → Result
  [ ] Setiap langkah terdokumentasi
  [ ] Tidak ada "lompatan logis"
  [ ] Metrik mengukur apa yang dimaksud (construct validity)
```

---

## Latihan 1 — Operationalization Chain

Gunakan RQ dari WS-04. Definisikan variabel dan metriknya.

**RQ:** "Bagaimana efektivitas kerangka kerja tata kelola keamanan siber berbasis standar ISO 27001 dibandingkan dengan praktik mandiri dalam memitigasi risiko kebocoran data pada sistem pelayanan publik di pemerintah daerah?"__________________________________________________

| Variabel | Tipe | Konsep Abstrak | Metrik Konkret | Skala (NOIR) | Satuan |
|----------|------|---------------|----------------|-------------|--------|
| Metode Tata Kelola | IV | Strategi keamanan |Kategorikal (ISO 27001 vs Mandiri) | Nomnal | — |
|Kejadia Kebocoran | DV |Tingkat keamanan Data |Jumlah insiden kebocoran terverifikasi |Rasio |Jumlah(unit) |
|Kapasitas SDM | CV |Kompetensi Teknis|Skor hasil audit/kuesioner mandiri |Ordinal |Skala Likert |

**Apakah ada lompatan logis dalam rantai?** [ ] Ya / [x  ] Tidak
> Jika ya, di mana? ____________________________________

---

## Latihan 2 — Evaluasi Metrik

Evaluasi metrik DV yang dipilih di Latihan 1 menggunakan 3 kriteria.

| Kriteria | Skor (1-5) | Justifikasi |
|----------|-----------|-------------|
| Representative | 5 |Jumlah insiden kebocoran data adalah indikator langsung dari kegagalan sistem keamanan. |
| Sensitive | 4|Metrik ini mampu mendeteksi perubahan kecil jika pelaporan insiden dilakukan secara real-time. |
| Feasible | 3|Tergantung pada transparansi instansi pemerintah dalam melaporkan insiden (seringkali tertutup). |

**Apakah perlu secondary metric?** [x ] Ya / [ ] Tidak
> Jika ya, apa dan mengapa? Indeks Kematangan SPBE (domain keamanan). Metrik ini penting untuk memvalidasi apakah rendahnya insiden disebabkan oleh ISO 27001 atau karena sistem yang memang belum terintegrasi (sehingga tidak ada data untuk dicuri)._____________________________

**Contoh kasus ceiling effect untuk metrik ini:**
> ___Jika instansi memiliki infrastruktur yang sangat tertutup (air-gapped) atau tidak memiliki exposure akses publik sama sekali, insiden mungkin mencapai angka nol secara alami, sehingga efektivitas ISO 27001 menjadi tidak terlihat perbedaannya dengan praktik mandiri.________________________________________________

---

## Latihan 3 — Data Quality Check

Bayangkan data yang akan dikumpulkan dari eksperimen. Evaluasi 4 dimensi kualitas data.

| Dimensi | Pertanyaan | Jawaban | Strategi Mitigasi |
|---------|-----------|---------|------------------|
| Completeness | *Apakah semua data point terkumpul?* |Belum tentu, ada risiko instansi tidak melaporkan insiden. |Menggunakan laporan pihak ketiga atau data agregat dari BSSN. |
| Consistency | *Apakah ada kontradiksi internal?* |Mungkin ada perbedaan definisi "insiden" antar instansi. |Membuat kriteria baku "insiden" di awal kuesioner audit. |
| Validity | *Apakah benar-benar mengukur yang dimaksud?* |Insiden bisa terjadi bukan karena tata kelola, tapi human error. |Menambahkan variabel kontrol (kualifikasi SDM). |
| Representativeness | *Apakah sampel mewakili populasi target?* |Seringkali hanya instansi "sukses" yang mau ikut riset. |Melakukan random sampling pada daerah dengan berbagai tingkat maturitas SPBE. |

---

## Refleksi

> Mengapa memilih metrik setelah melihat data dianggap p-hacking? Apa bedanya dengan eksplorasi data yang sah?

**Jawaban:**
> Memilih metrik setelah melihat data dianggap p-hacking karena peneliti cenderung mencari metrik yang menghasilkan nilai signifikansi statistik ($p < 0.05$) daripada menguji kebenaran hipotesis secara objektif. Ini adalah bentuk manipulasi hasil (cherry-picking).Bedanya dengan eksplorasi data yang sah: Eksplorasi data yang sah dilakukan untuk memahami distribusi, korelasi, dan karakteristik data sebelum melakukan inferensi statistik (untuk merumuskan hipotesis baru), bukan untuk mengubah metrik demi memaksa hasil yang diinginkan (signifikansi). Eksplorasi yang sah bersifat terbuka dan jujur mengenai keterbatasan data, sedangkan p-hacking bersifat manipulatif untuk mencapai klaim kebaruan yang tidak valid.___________________________________________________
> ___________________________________________________
