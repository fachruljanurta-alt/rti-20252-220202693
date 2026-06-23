# WS-03: Literature Mapping & Gap

> **Bab 3 — Literature Review, Research Gap & Baseline**

---

## Ringkasan Materi

### Literature Review = Positioning, Bukan Ringkasan

Literature review bukan merangkum paper satu per satu. Pendekatan yang benar adalah **concept-centric** — organisasi berdasarkan tema, metode, atau variabel. Tujuan: menemukan **pola, kontradiksi, dan gap**.

**Perbandingan pendekatan Author-centric vs Concept-centric:**

| Aspek | Author-centric (Hindari) | Concept-centric (Gunakan) |
|-------|--------------------------|---------------------------|
| Struktur | Per penulis/paper ("Rahman et al. menyatakan...") | Per konsep/metode ("Pendekatan berbasis transformer") |
| Tujuan | Ringkasan isi paper | Perbandingan metode & identifikasi gap |
| Contoh paragraph | "Rahman (2023) pakai CNN. Lee (2022) pakai LSTM. Zhang (2021) pakai RF." | "Tiga pendekatan dominan: CNN digunakan oleh 4 paper untuk representasi fitur visual; LSTM untuk data sekuensial; RF sebagai baseline klasik." |
| Hasil akhir | Daftar paper | Peta pengetahuan + gap yang teridentifikasi |

### Empat Jenis Research Gap

| Jenis Gap | Deskripsi | Contoh |
|-----------|----------|--------|
| **Performance Gap** | Performa belum memadai | Akurasi deteksi hanya 78% pada kasus tertentu |
| **Method Gap** | Pendekatan belum diterapkan | Belum ada yang pakai transformer untuk task ini |
| **Data Gap** | Dataset terbatas/tidak representatif | Semua studi pakai dataset sintetis |
| **Context Gap** | Belum diuji pada konteks berbeda | Belum ada evaluasi di negara berkembang |

Gap terkuat = kombinasi 2+ jenis.

### Systematic Search Strategy

1. **Database utama**: IEEE Xplore, ACM DL, Scopus
   - Akses IEEE/ACM melalui jaringan kampus atau VPN institusi
   - Alternatif bebas biaya: Google Scholar, ResearchGate ([researchgate.net](https://www.researchgate.net)), arXiv ([arxiv.org](https://arxiv.org))
2. **Boolean query** yang terdokumentasi eksplisit
   - Contoh: `("anomaly detection" OR "intrusion detection") AND ("deep learning" OR "neural network") NOT ("medical imaging")`
   - Gunakan tanda kutip untuk frasa eksak; AND/OR/NOT mengontrol scope
3. **Snowballing** — dua arah:
   - **Backward snowballing**: buka daftar referensi di paper kunci → telusuri paper yang dikutip
   - **Forward snowballing**: di Google Scholar, klik "Cited by" di bawah paper kunci → temukan paper yang mengutipnya
   - Ulangi 1–2 tingkat untuk membangun cakupan komprehensif
4. Klaim "belum ada penelitian" harus didukung **bukti pencarian**

### Baseline Selection — 3 Kriteria

| Kriteria | Pertanyaan |
|----------|-----------|
| **Relevan** | Apakah menyelesaikan masalah yang sama? |
| **Representatif** | Apakah mewakili common practice? |
| **State-of-the-Art** | Apakah terbaru/terbaik? |

Membandingkan deep learning 2024 dengan decision tree sederhana tanpa justifikasi = **straw man comparison** (perbandingan tidak jujur).

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan baca literatur | Mencari solusi yang sudah ada | Memahami apa yang belum terjawab |
| Cara membaca paper | Tutorial, how-to | Metode, limitasi, gap |
| Baseline | Framework terpopuler | State-of-the-art yang rigorous |
| Dokumentasi pencarian | Tidak diperlukan | Wajib (reproducible) |

### Istilah Penting

- **Concept-centric** — Organisasi literatur berdasarkan konsep/metode, bukan per penulis
- **Snowballing** — Backward (telusuri referensi) + Forward (cari yang mengutip paper kunci)
- **Research Position** — Pernyataan eksplisit posisi riset terhadap studi sebelumnya
- **Straw man comparison** — Memilih baseline lemah agar metode sendiri terlihat lebih baik

---

## Template A.3 — Literature Mapping & Gap Identification

```
LITERATURE MAPPING

Topik      : ____________________
Database   : ____________________
Query      : ____________________
Tahun      : ____________________
Hasil awal : ____ paper → Screening → ____ paper final

Literature Matrix (concept-centric):

| Study | Tahun | Method | Data | Result | Limitation |
|-------|-------|--------|------|--------|------------|
|       |       |        |      |        |            |

Pola yang ditemukan:
  Metode dominan     : ____________________
  Dataset umum       : ____________________
  Limitasi berulang  : ____________________

GAP IDENTIFICATION

Gap 1: [Jenis: performance / method / data / context]
  Deskripsi    : ____________________
  Bukti        : ____________________
  Signifikansi : ____________________

Gap 2: [Jenis: ____]
  Deskripsi    : ____________________
  Bukti        : ____________________
  Signifikansi : ____________________

Baseline Selection:
| Baseline | Relevansi | Representatif | Source |
|----------|-----------|---------------|--------|
|          |           |               |        |
```

---

## Latihan 1 — Concept-Centric Literature Table

Gunakan topik riset dari WS-02. Cari minimal 5 paper relevan menggunakan database akademik.

> **Panduan pencarian:**
> - Database: IEEE Xplore, ACM DL, Google Scholar, atau ResearchGate
> - Tulis query Boolean yang digunakan: contoh `("object detection" OR "image classification") AND ("edge computing") NOT ("medical")`. Dokumentasikan query secara eksplisit.
> - Akses gratis: buka Google Scholar → cari judul paper → klik [PDF] jika tersedia, atau akses lewat campus VPN

**Topik riset:** Risiko Keamanan Siber pada Sistem Pemerintahan Berbasis Elektronik (SPBE).
**Query pencarian:** ("cyber security" OR "keamanan siber") AND ("digital transformation" OR "transformasi digital") AND ("public service" OR "pelayanan publik") NOT ("medical").
**Database:** Google Scholar & UI Scholars Hub.

| # | Study | Tahun | Method | Dataset | Result | Limitasi |
|---|-------|-------|--------|---------|--------|----------|
| 1 | Alfi dkk | 2023 | Kualitatif | Laporan BSSN,Kasus Publik | Identifikasi 3 pilar |  |
| 2 |Rofii |2018 |Analisis Stratejik |Dokumen Pertahanan |Postur ketahanan siber |Belum mencakup SPBE 4.0 |
| 3 |Sudarmadi & Runturambi |2019 |Deskriptif |Strategi BSSN |Analisis ancaman siber |Fokus pada instansi BSSN |
| 4 |Jayantho dkk. |2020 |Pemodelan Dinamis |Data Big Data |Meminimalisasi spionase |Fokus pada industri 4.0 |
| 5 |Luthfah |2024 |Tinjauan Pustaka |Sektor Jasa Keuangan |Penguatan siber sektor keuangan |Terbatas pada sektor keuangan |

**Pola yang terlihat — Metode dominan:** Kualitatif dan tinjauan pustaka.
**Limitasi yang berulang:** Fokus penelitian masih terkotak-kotak per sektor (keuangan/pertahanan) dan belum ada model mitigasi yang seragam untuk integrasi SPBE lintas instansi.

---

## Latihan 2 — Gap Identification

Berdasarkan tabel di Latihan 1, identifikasi gap.

| Jenis Gap | Ditemukan? | Gap Statement |
||-----------|---------------|
| Performance Gap | [x ] Ya / [ ] Tidak | Hanya 2,89% instansi yang memiliki implementasi SPBE sangat baik. |
| Method Gap | [ ] Ya / [ ] Tidak |- |
| Data Gap | [x ] Ya / [ ] Tidak | Kurangnya data riil mengenai serangan siber pada tingkat pemda|
| Context Gap | [x ] Ya / [ ] Tidak |Belum ada strategi mitigasi siber yang terintegrasi untuk "Satu Data Indonesia". |

**Gap utama yang dipilih:** Kesenjangan Konteks pada integrasi kebijakan "Satu Data Indonesia".
**Mengapa gap ini penting (bukan sekadar "belum ada yang meneliti")?**Karena transformasi digital pelayanan publik memerlukan interoperabilitas data antar instansi, namun belum ada model keamanan yang selaras dengan tantangan geopolitik dan keragaman infrastruktur daerah.
> ___________________________________________________

---

## Latihan 3 — Baseline Selection

Pilih 2 baseline dari literatur yang sudah dibaca.

| # | Baseline | Mengapa Relevan | Mengapa Representatif | Apakah SOTA? | Sumber |
|---|----------|----------------|----------------------|-------------|--------|
| 1 | Model Pertahanan Siber Kemenhan | Fokus pada gangguan pertahanan | Dasar regulasi keamanan negara | Tidak | Widjajanto dkk., 2023 |
| 2 | Kerangka SPBE (Perpres 95/2018)|Dasar tata kelola SPBE |Standar nasional pemerintahan |Tidak |Alfi dkk., 2023 |

**Apakah pemilihan baseline ini bisa dianggap straw man?** [ ] Ya / [x ] Tidak
> Justifikasi: Ini adalah praktik umum (baseline) karena mencerminkan realita kebijakan yang berlaku di Indonesia yang harus dipatuhi oleh seluruh institusi publik.

---

## Refleksi

> Apa perbedaan antara "belum ada yang meneliti ini" (klaim tanpa bukti) dengan research gap yang valid? Bagaimana cara membuktikan bahwa sebuah gap benar-benar ada?

**Jawaban:**
Apa perbedaan antara "belum ada yang meneliti ini" (klaim tanpa bukti) dengan riset gap yang valid?
"Belum ada yang meneliti" hanyalah asumsi subjektif. Riset gap yang valid didasarkan pada evaluasi sistematis terhadap literatur yang ada yang menunjukkan bahwa meskipun suatu topik sudah dibahas, terdapat aspek spesifik (kinerja, metode, atau konteks) yang belum terjawab atau tidak efektif untuk diimplementasikan.  Bagaimana cara membuktikan bahwa sebuah celah benar-benar ada?
Dengan cara pemetaan literatur (Mapping). Kita harus menunjukkan bahwa hasil riset terdahulu memiliki batasan (limitasi) yang konsisten, dan dengan memberikan argumen logis bahwa kondisi saat ini (misalnya: SPBE 4.0) berbeda dengan kondisi saat penelitian terdahulu dilakukan, sehingga penelitian baru diperlukan untuk menutup celah tersebut.  
