# WS-12: Result Presentation & Visualization

> **Bab 12 — Penyajian Hasil & Visualisasi**

---

## Ringkasan Materi

### Data → Insight Model

```
Validated Data → Structured Presentation → Visualization → Pattern Recognition → Insight
```

Penyajian **mendahului** analisis. Tabel dan grafik membantu peneliti "melihat" data sebelum menghitung. Langsung ke uji statistik tanpa visualisasi berisiko kesimpulan yang secara teknis benar tapi kontekstual salah (Anscombe's Quartet, 1973).

### Tabel = Presisi, Grafik = Pola

Keduanya **saling melengkapi**:
- Tabel: angka presisi, self-contained (dipahami tanpa teks), sortable
- Grafik: pola visual, tren, perbandingan cepat

### Jenis Grafik Berdasarkan Tujuan

| Tujuan | Jenis Grafik |
|--------|-------------|
| Perbandingan antar-skenario | Bar chart (grouped/stacked) |
| Distribusi per-skenario | Box plot / violin plot |
| Tren temporal | Line chart |
| Korelasi dua variabel | Scatter plot |
| Proporsi (total = 100%) | Pie chart (hati-hati!) |

### Contoh Tabel Hasil yang Baik

| Model | Accuracy (%) | F1-Score (%) | Training Time (min) |
|-------|-------------|-------------|---------------------|
| BERT | 88.4 ± 1.2 | 87.1 ± 1.4 | 45.2 ± 3.1 |
| LSTM | 86.1 ± 1.8 | 84.5 ± 2.0 | 12.8 ± 1.2 |
| SVM | 82.3 ± 0.9 | 80.7 ± 1.1 | 0.3 ± 0.1 |

*N=10 per model. Mean ± std. Diurutkan berdasarkan Accuracy.*

### Visualization Bias — Yang Harus Dihindari

| Bias | Deskripsi | Dampak |
|------|----------|--------|
| Truncated axis | Y tidak dari 0 | Memperbesar perbedaan kecil |
| Inconsistent scale | Dua grafik skala beda | Perbandingan menyesatkan |
| Cherry-picked data | Hanya tampilkan yang "menang" | Selektif, tidak jujur |
| 3D effects | Efek 3D tanpa dimensi data ke-3 | Distorsi tanpa informasi |
| Missing error bar | Tidak ada variabilitas | Menyembunyikan ketidakpastian |

### Engineering vs Research Presentation

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Tujuan grafik | Dashboard monitoring | Mendukung argumen ilmiah |
| Informasi wajib | KPI, threshold | Mean, std, CI, N, p-value |
| Bias handling | Less critical | Wajib dihindari (peer-review) |

---

## Template A.12 — Result Presentation Plan

```
RESULT PRESENTATION PLAN

Research Question : ____________________
Metrik Utama      : ____________________

Tabel Hasil:
| Skenario | Metrik 1 (mean ± std) | Metrik 2 (mean ± std) | n |
|----------|----------------------|----------------------|---|
|          |                      |                      |   |

Visualisasi yang Direncanakan:
| # | Jenis Grafik | Pesan Utama | Metrik |
|---|-------------|-------------|--------|
| 1 |             |             |        |
| 2 |             |             |        |

Bias Check:
  [ ] Y-axis mulai dari 0 (atau dijustifikasi)
  [ ] Error bar/CI ditampilkan
  [ ] Semua data disertakan (tidak cherry-picked)
  [ ] Tidak menggunakan 3D tanpa alasan
```

---

## Latihan 1 — Tabel Hasil

Buat tabel hasil eksperimen Anda (boleh dengan data simulasi jika belum punya data riil).

| Skenario | Metrik 1 (mean ± std) | Metrik 2 (mean ± std) | n |
|----------|----------------------|----------------------|---|
| ISO 27001 | 3.2 ± 0.8 | 3.8 ± 0.3 | *10* |
|Praktik Mandiri |8.6 ± 1.5 |2.1 ± 0.5 |9 |
| | | | |

**Checklist tabel:**
- [ x] Self-contained (judul jelas, satuan ada, N tercantum)
- [x ] Mean ± std (bukan single number)
- [x ] Diurutkan berdasarkan metrik utama
- [x ] Format konsisten di semua baris

---

## Latihan 2 — Rencana Visualisasi

Rencanakan 2-3 grafik untuk menyajikan data dari Latihan 1. Setiap grafik = satu pesan.

| # | Jenis Grafik | Pesan | Data yang Digunakan |
|---|-------------|-------|---------------------|
| 1 | *Bar chart + error bar* | ISO 27001 menurunkan jumlah insiden secara signifikan. | Mean insiden ± std |
| 2 | *Box plot* | ISO 27001 memberikan konsistensi performa (varians rendah). | Seluruh data insiden (n=19) |
| 3 | *Scatter plot* | Korelasi antara maturitas SPBE dan rendahnya insiden. | Skor SPBE vs Jumlah Insiden |

---

## Latihan 3 — Bias Detection

Evaluasi visualisasi berikut untuk bias (skenario dari contoh):

**Skenario:** Metode A = 91.2%, Metode B = 90.8%. Bar chart dengan Y-axis mulai dari 90%.

| Pertanyaan | Jawaban |
|-----------|---------|
| Apakah Y-axis menyesatkan? | Ya — Memulai axis dari 90% melebih-lebihkan selisih performa visual secara drastis. |
| Apakah error bar ditampilkan? | Tidak (asumsi skenario).|
| Apakah semua kondisi ditampilkan? |Ya |
| Apa solusinya? | Memulai Y-axis dari 0 atau menggunakan broken-axis dengan keterangan jelas.|

**Evaluasi grafik Anda sendiri dari Latihan 2:**
- [x ] Semua bias check lulus
- [ ] Ada yang perlu diperbaiki: ____

---

## Refleksi

> Mengapa tabel dan grafik keduanya diperlukan — tidak cukup salah satu saja? Pernahkah Anda membuat grafik yang (tanpa sengaja) menyesatkan?
>
> Mengapa tabel dan grafik keduanya diperlukan?
Tabel diperlukan untuk presisi; pembaca yang ingin melakukan kalkulasi ulang atau melihat nilai eksak sangat bergantung pada tabel. Grafik diperlukan untuk interpretasi cepat; mata manusia lebih cepat menangkap tren, pola, dan anomali (seperti outlier B4 pada riset kita) melalui visualisasi dibandingkan deretan angka. Kombinasi keduanya adalah bentuk integritas riset: tabel memberikan bukti data, grafik memberikan pemahaman naratif.

Pernahkah membuat grafik yang (tanpa sengaja) menyesatkan?
Pernah, saat membuat grafik pie chart dengan terlalu banyak kategori yang mirip, sehingga perbedaan kecil terlihat besar atau sulit dibaca. Grafik tersebut menyesatkan karena tidak memberikan informasi yang akurat mengenai proporsi sebenarnya, yang kemudian saya perbaiki menjadi bar chart agar setiap batang memiliki titik awal dan akhir yang jelas untuk dibandingkan.

> ___________________________________________________
> ___________________________________________________
