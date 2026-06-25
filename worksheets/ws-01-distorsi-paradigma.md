# WS-01: Distorsi & Paradigma

> **Bab 1 — Research Mindset in IT**

---

## Ringkasan Materi

### Research Trust Model

Pengetahuan ilmiah tidak muncul langsung dari kenyataan. Ia melewati **6 tahap transformasi** yang masing-masing rawan distorsi:

```
Reality → Data → Processing → Analysis → Inference → Knowledge
```

Etika mencegah distorsi yang disengaja (fabrikasi, cherry-picking). Validitas mendeteksi distorsi yang tidak disengaja (confounding variable, sampling bias).

### Tiga Jenis Validitas

| Jenis | Pertanyaan | Contoh Ancaman |
|-------|-----------|----------------|
| **Internal Validity** | Apakah hubungan kausal benar ada? | Confounding variable |
| **External Validity** | Apakah bisa digeneralisasi? | Dataset terlalu homogen |
| **Construct Validity** | Apakah mengukur hal yang benar? | Metrik tidak sesuai klaim |

### Paradigma Riset

Mata kuliah ini menggunakan pendekatan **Positivist** (fenomena TI bisa diukur objektif melalui eksperimen terkontrol) diperkuat **Design Science Research** (DSR). Penting untuk membedakan keduanya:

| Paradigma | Cara Kerja | Contoh di TI |
|-----------|-----------|---------------|
| **Positivis** | Uji hipotesis dengan eksperimen terkontrol | Apakah CNN lebih akurat dari RF pada dataset X? |
| **Design Science Research** | Bangun artefak (sistem/model/framework) untuk menguji proposisi | Dapatkah arsitektur hybrid CNN+LSTM membuktikan peningkatan recall ≥5%? |
| **Interpretivis** | Pahami makna melalui konteks & kualitatif | Bagaimana peneliti manafsirkan anomali data sensor IoT? |

Dalam DSR, artefak **bukan tujuan akhir** — ia adalah instrumen untuk menghasilkan pengetahuan. Pertanyaan riset tetap harus difalsifikasi.

### Mode Berpikir Peneliti

**Curious** (mempertanyakan fenomena) → **Critical** (mengevaluasi klaim berdasarkan bukti) → **Systematic** (merancang investigasi terstruktur dan reproducible).

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan | Membuat sistem yang bekerja | Menghasilkan pengetahuan yang valid |
| Pertanyaan khas | "Bagaimana membuatnya jalan?" | "Apakah klaim ini benar?" |
| Ukuran sukses | Sistem berfungsi, client puas | Hipotesis terjawab, temuan tervalidasi |
| Kegagalan | Harus dihindari | Harus dilaporkan (negative result = kontribusi) |

### Istilah Penting

- **Research Mindset** — Pola pikir yang menuntut bukti dan mempertanyakan asumsi
- **Research Ethics** — Prinsip perilaku: kejujuran, objektivitas, keterbukaan, akuntabilitas
- **HARKing** — Hypothesizing After Results are Known — merumuskan hipotesis setelah melihat data
- **Falsifiability** — Hipotesis harus bisa dibuktikan salah

---

## Template A.1 — Research Mindset Self-Assessment

```
Nama Peneliti    : ____________________
Tanggal          : ____________________

1. Ketika membaca klaim "metode X 95% akurat":
   - Pertanyaan pertama saya: ____________________
   - Data yang dibutuhkan untuk verifikasi: ____________________

2. Posisi paradigma:
   - Pendekatan: [ ] Positivis  [ ] Interpretivis  [ ] Design Science  [ ] Mixed
   - Alasan: ____________________

3. Identifikasi distorsi:
   - Asumsi tersembunyi: ____________________
   - Sumber bias potensial: ____________________
   - Langkah mitigasi: ____________________

4. Komitmen etika:
   - Data yang tidak akan dimanipulasi: ____________________
   - Batasan yang diakui sejak awal: ____________________
```

---

## Latihan 1 — Identifikasi Distorsi

Pilih satu paper riset di bidang TI yang mengklaim "metode X meningkatkan performa." Telusuri setiap tahap Research Trust Model.

> **Panduan pencarian paper:** Gunakan [IEEE Xplore](https://ieeexplore.ieee.org), [ACM Digital Library](https://dl.acm.org), atau Google Scholar. Pilih paper **tahun 2020 ke atas**, di topik yang Anda minati: deteksi anomali, klasifikasi citra, NLP, keamanan siber, IoT, dsb.
>
> **Contoh domain TI:** "Deteksi anomali lalu-lintas jaringan menggunakan CNN — akurasi meningkat 94% vs baseline SVM 87%." Distorsi potensial: apakah dataset normal/anomali seimbang? Apakah hanya diuji pada satu vendor traffic?

**Paper yang dipilih:**
> Judul: _Keamanan Siber dalam Transformasi Digital Pelayanan Publik di Indonesia
> Penulis (Tahun): _Muhammad Alfi Fadhlurrahman, Ni Putu Yundari, Ahnaf Tsaqif Firdaus (2023)_____________________________________
> Sumber/Link DOI: https://scholarhub.ui.ac.id/jkskn/vol6/iss2/5_____________________________________

| Tahap | Apa yang Dilakukan | Potensi Distorsi |
|-------|-------------------|-----------------|
| Reality → Data | Mengumpulkan data serangan siber dari laporan BSSN dan kasus publik.   | Data serangan yang tercatat mungkin hanya puncak gunung es; banyak serangan tidak terdeteksi atau tidak dilaporkan.   |
| Data → Processing |Mengolah data dari berbagai sektor (Kesehatan, Keuangan, Pemerintahan).   | Pengelompokan sektor yang luas dapat mengaburkan perbedaan spesifik tingkat kerentanan teknis di tiap lembaga|
| Processing → Analysis |Menganalisis peran stakeholder (Pemerintah Pusat, Daerah, ASN).   | Analisis bisa bias jika hanya fokus pada perspektif kebijakan formal, mengabaikan realita teknis di lapangan.|
| Analysis → Inference |Menyimpulkan perlunya tiga pilar (teknologi, manusia, tata kelola).   |Inferensi mungkin terlalu menggeneralisasi solusi yang sama untuk semua instansi yang memiliki infrastruktur berbeda. |
| Inference → Knowledge |Merekomendasikan strategi mitigasi untuk ketahanan nasional |Rekomendasi kebijakan mungkin sulit dieksekusi jika kesenjangan anggaran antar daerah tidak dipertimbangkan.   |

**Distorsi paling besar di tahap:** ___________________ Realita → Data.  _____

**Dua distorsi spesifik yang teridentifikasi:**
1. ___________________________________________________ Reporting Bias: Data yang digunakan sangat bergantung pada laporan resmi (BSSN), yang mungkin tidak mencakup serangan pada sektor swasta atau sistem kecil yang tidak memiliki kapasitas pelaporan.  
2. ___________________________________________________Selection Bias: Fokus pada kasus-kasus besar (misal: kebocoran BPJS, peretasan situs DPR) menciptakan persepsi bahwa ancaman hanya terjadi pada level makro, padahal kerentanan pada sistem daerah sering terabaikan.  

---

## Latihan 2 — Analisis Kasus Etika

Skenario: Seorang peneliti menemukan bahwa jika 3 data point outlier dihapus, hasil eksperimennya menjadi signifikan. Dengan outlier, hasilnya tidak signifikan.

| Perspektif | Analisis |
|------------|---------|
| Kejujuran ilmiah | Peneliti harus melaporkan data apa adanya. Menghapus data hanya untuk mendapatkan hasil yang signifikan adalah bentuk manipulasi yang menyesatkan pembaca.  |
| Transparansi | jika outlier dihapus, peneliti wajib memberikan alasan teknis yang valid (misalnya kesalahan sensor) dan menyajikan hasil dengan dan tanpa data tersebut.  |
| Peer review | Reviewer harus dapat mengevaluasi apakah penghapusan tersebut didasarkan pada metodologi yang benar atau hanya upaya "mencari signifikansi" (p-hacking).  |

**Keputusan akhir dan justifikasi:**
> ___________________________________Jangan menghapus data tanpa justifikasi metodologis yang transparan. Laporkan hasil analisis dengan menyertakan data outlier tersebut. Jika hasil tetap tidak signifikan, kejujuran ini lebih bernilai bagi sains daripada hasil signifikan yang didapat dari manipulasi data. Peneliti harus menekankan pada keterbatasan sistem yang diteliti daripada memaksakan klaim keberhasilan.  ________________

---

## Latihan 3 — Posisi Paradigma

**Topik riset:** Analisis Risiko Keamanan Siber dalam Transformasi Digital Pelayanan Publik.________________________________________

> **Skala 1–5:** 1 = tidak sesuai sama sekali dengan topik ini, 5 = sangat sesuai dan dominan digunakan pada riset bertopik serupa.

| Kriteria | Positivis | Interpretivis | Design Science |
|----------|-----------|---------------|----------------|
| Jenis data | Metrik serangan, data sekunder | Analisis peran/kebijakan| Kerangka mitigasi |
| Fokus | Pengukuran resiko | Log Kebijakan |Strategi Perubahan |
| Hasil |Pola ancaman |Perspektif Stakeholder |Rekomendasi tata Pola |

**Paradigma yang dipilih:**Design Scienece _____________________________
**Alasan:** ______________________________Penelitian ini bertujuan untuk menghasilkan rekomendasi kebijakan dan kerangka strategi mitigasi (artefak) untuk memperkuat ketahanan nasional di era digital, bukan sekadar menjelaskan fenomena.  ______________

---

## Refleksi

> Sebelum membaca materi ini, apakah pernah mempertanyakan klaim "95% akurat"? Setelah memahami rantai distorsi, pertanyaan apa yang sekarang akan diajukan saat membaca paper?

**Jawaban:**
> Sebelum membaca: Mungkin pernah menganggap angka "370,02 juta serangan siber" adalah kebenaran mutlak tanpa mempertanyakan bagaimana data tersebut dikumpulkan dan diklasifikasikan.
> Pertanyaan setelah memahami rantai distorsi:"Apakah angka statistik serangan ini mencakup semua jenis ancaman, atau hanya jenis tertentu yang terdeteksi oleh sensor BSSN?"  "Bagaimana kualitas data yang digunakan sebagai dasar kebijakan, mengingat hanya 2,89% instansi yang memiliki implementasi SPBE dengan predikat sangat baik?"  ___________________________________________________
> ___________________________________________________
