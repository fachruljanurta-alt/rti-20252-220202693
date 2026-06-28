# WS-13: Data Preprocessing

> **Bab 13 — Preprocessing & Persiapan Data untuk Analisis**

---

## Ringkasan Materi

### Data Refinement Pipeline

```
Raw Data → Cleaning → Transformation → Normalization → Processed Data → Analysis Ready
```

Setiap tahap memiliki tujuan berbeda. **Preprocessing bukan langkah teknis biasa** — setiap keputusan preprocessing adalah keputusan riset yang bisa mengubah kesimpulan.

### Empat Prinsip Preprocessing

| Prinsip | Deskripsi |
|---------|----------|
| **Consistency** | Metode sama untuk data yang sama |
| **Transparency** | Setiap langkah terdokumentasi |
| **Reproducibility** | Orang lain bisa mengulang dengan hasil sama |
| **Minimal Distortion** | Ubah sesedikit mungkin; jika normalisasi tidak perlu, jangan lakukan |

### Cleaning Triad

| Masalah | Strategi | Risiko |
|---------|---------|--------|
| **Missing values** | | |
| — Listwise deletion | Missing < 5%, random | Data loss |
| — Mean/median imputation | Sedikit missing, dist. normal | Mengurangi variabilitas |
| — Model-based imputation | Banyak missing, pola sistematis | Introduces dependency |
| — Flag & separate | Missing karena alasan substantif | Kompleksitas analisis |
| **Duplikat** | Identifikasi → verifikasi → hapus | False positive (data mirip ≠ duplikat) |
| **Error format** | Standardisasi tipe, encoding | Kehilangan informasi saat konversi |

### Normalisasi — Kapan & Metode Mana

| Metode | Formula | Output | Sensitif Outlier? |
|--------|---------|--------|-------------------|
| Min-max | (x-min)/(max-min) | [0, 1] | Ya |
| Z-score | (x-mean)/std | Unbounded | Lebih robust |
| Robust scaling | (x-median)/IQR | Unbounded | Paling robust |

**Kunci:** Parameter normalisasi harus dihitung dari **training set saja** — bukan seluruh data. Pelanggaran = **data leakage**.

### Data Leakage Prevention

Data leakage terjadi ketika informasi dari test set "bocor" ke preprocessing:
- Normalisasi parameter dari seluruh dataset ← **SALAH**
- Cross-validation dilakukan sebelum split ← **SALAH**
- Feature selection menggunakan label test set ← **SALAH**

### Jebakan Kognitif

1. "Preprocessing cuma teknis — tidak perlu detail" → bisa ubah kesimpulan
2. "Lebih banyak preprocessing = lebih bersih = lebih baik" → over-processing distorsi data
3. "Normalisasi selalu diperlukan" → belum tentu, tergantung metode analisis
4. "Imputation sama untuk semua situasi" → strategi harus sesuai konteks

---

## Template A.13 — Preprocessing Documentation Log

```
PREPROCESSING LOG

Dataset           : ____________________
Jumlah data awal  : ____________________

Cleaning:
| Masalah | Jumlah Kasus | Penanganan | Justifikasi |
|---------|-------------|------------|-------------|
| Missing |             |            |             |
| Duplikat|             |            |             |
| Error   |             |            |             |

Transformation:
| Transformasi | Variabel | Detail | Alasan |
|-------------|----------|--------|--------|
|             |          |        |        |

Normalization:
  Metode    : ____________________
  Alasan    : ____________________
  Parameter : (dihitung dari: training set / seluruh data)

Leakage Check:
  [ ] Parameter normalisasi dari training set saja
  [ ] Tidak ada informasi test set dalam preprocessing
  [ ] Cross-validation dilakukan setelah split

Jumlah data akhir : ____________________
Script tersedia   : [ ] Ya → path: ____ | [ ] Belum
```

---

## Latihan 1 — Cleaning Plan

Periksa dataset Anda (atau dataset contoh) dan dokumentasikan masalah yang ditemukan.

| Masalah | Jumlah Kasus | Penanganan | Justifikasi |
|---------|-------------|------------|-------------|
| Missing di kolom "skor_spbe" | 2 dari 20 (10%) | Imputasi Mean | Data bersifat Missing at Random pada instansi kecil. |
|Data bersifat Missing at Random pada instansi kecil. |1 dari 20 (5%) |Deduplikasi |Mencegah pembobotan ganda pada insiden yang sama. |

**Jumlah data sebelum cleaning:** __20__
**Jumlah data setelah cleaning:** ____20
**Persentase data yang hilang/berubah:**0 ____%

---

## Latihan 2 — Normalisasi Decision

Tentukan apakah data Anda perlu normalisasi, dan jika ya, metode apa yang tepat.

| Variabel | Range Asli | Distribusi | Outlier? | Metode Normalisasi | Alasan |
|----------|-----------|-----------|----------|-------------------|--------|
| insiden_count | 0 – 22 | *Right-skewed* | *Ya (22) | *Robust scaling* | Adanya outlier (insiden DDoS ekstrem) perlu penanganan agar tidak mendominasi model. |

**Apakah normalisasi diperlukan?** [x ] Ya / [ ] Tidak
**Justifikasi:**
> ___________________________________Normalisasi diperlukan karena data insiden dan skor SPBE memiliki satuan dan skala yang sangat berbeda. Menggunakan Robust Scaling untuk insiden siber memastikan bahwa model statistik tidak bias akibat nilai ekstrem (outlier), sementara Min-Max Scaling untuk skor SPBE memudahkan interpretasi perbandingan.________________

**Leakage check:**
- [x ] Parameter dihitung dari training set saja
- [ x] Normalisasi diterapkan setelah train-test split

---

## Latihan 3 — Preprocessing Report

Buat ringkasan preprocessing lengkap — dokumentasi yang cukup bagi orang lain untuk mereplikasi.

```
PREPROCESSING SUMMARY

1. Dataset: Laporan Insiden Siber dan Skor SPBE Pemerintah Daerah 2023
2. Data awal: 20 records, 4 features
3. Cleaning:
   - Missing values: 2 kasus, metode: Imputasi Mean
   - Duplikat: 1 kasus, tindakan: Deduplikasi
   - Error: 3 kasus format tanggal, tindakan: Standardisasi ISO 8601
4. Transformation: Encoding kategori "Metode Tata Kelola" menjadi numerik
5. Normalisasi: Robust Scaling (insiden) & Min-Max (SPBE), parameter dari Training Set
6. Data akhir: 20 records, 4 features
7. Leakage check: [x] Lulus / [ ] Ada masalah
```

---

## Refleksi

> Apakah Anda pernah melakukan normalisasi "karena biasa dilakukan" tanpa mempertimbangkan apakah benar-benar diperlukan? Apa risiko over-preprocessing?

> Ya, seringkali normalisasi dianggap sebagai "ritual" wajib sebelum masuk ke pemodelan. Namun, over-preprocessing memiliki risiko nyata, yaitu hilangnya informasi interpretatif. Contohnya, melakukan normalisasi berlebihan pada data yang memiliki makna fisik (seperti jumlah insiden siber) dapat menyulitkan pembaca dalam memahami dampak nyata di lapangan. Selain itu, over-preprocessing dapat menyebabkan overfitting pada data training jika transformasi yang dilakukan terlalu kompleks atau tidak relevan dengan karakteristik populasi asli.x___________________________________________________
> ___________________________________________________
