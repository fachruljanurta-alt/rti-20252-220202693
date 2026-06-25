# WS-15: Scientific Writing

> **Bab 15 — Penulisan Ilmiah**

---

## Ringkasan Materi

### Scientific Argument Flow

```
Problem → Gap → RQ → Method → Result → Analysis → Conclusion → Contribution
```

Paper ilmiah adalah **satu argumen utuh** dari masalah ke kontribusi. Setiap node harus terhubung logis ke node sebelum dan sesudahnya.

### Struktur IMRAD

| Section | Peran | Pertanyaan Kunci |
|---------|-------|-----------------|
| **Introduction** | Motivasi + frame | Why is this needed? |
| **Method** | Deskripsi (reproducible) | How was it done? |
| **Results** | Laporan objektif | What was found? |
| **Discussion** | Interpretasi + refleksi | What does it mean? |
| **Conclusion** | Ringkasan + kontribusi | So what? |

### Logical Flow — "Red Thread"

Setiap paragraf menjawab satu pertanyaan dan memicu pertanyaan berikutnya. Alur logis ini harus terasa di tiga level:
1. **Antar-kalimat** dalam paragraf
2. **Antar-paragraf** dalam section
3. **Antar-section** dalam paper

### Internal Consistency

Setiap elemen yang dijanjikan di Introduction harus hadir di Discussion/Conclusion.

**Consistency Matrix:**
```
           Intro  Method  Result  Discuss  Conclude
RQ1          ✓      ✓       ✓       ✓        ✓
RQ2          ✓      ✓       ✓       ✗ ←      ✓
Metrik-X     ✗      ✗       ✓ ←     ✗        ✗
```
**Masalah:** RQ2 dibahas di semua bagian kecuali Discussion. Metrik-X muncul di Result tapi tidak diperkenalkan di Method.

### Writing Quality Triad

| Kualitas | Deskripsi | Contoh Buruk → Baik |
|----------|----------|---------------------|
| **Clarity** | Dipahami sekali baca | "Performa meningkat" → "Accuracy meningkat dari 85.3% ke 89.7%" |
| **Precision** | Istilah eksak, tanpa ambiguitas | "signifikan" → "signifikan secara statistik (p=0.003, d=1.2)" |
| **Conciseness** | Setiap kata menambah informasi | Hapus kalimat redundan, filler words |

### Urutan Penulisan yang Disarankan

1. **Method & Results** — paling stabil, tulis pertama
2. **Discussion** — interpretasi berdasarkan hasil
3. **Introduction** — frame sesuai temuan aktual
4. **Abstract & Conclusion** — terakhir

### Target Jumlah Kata

| Section | Target |
|---------|--------|
| Introduction | 500–700 |
| Related Work | 700–1000 |
| Method | 800–1200 |
| Results | 500–800 |
| Discussion | 600–900 |
| Conclusion | 200–400 |

### Jebakan Kognitif

1. "Lebih panjang = lebih lengkap" → conciseness lebih berharga
2. "Introduction harus ditulis pertama" → justru ditulis terakhir
3. "Jargon teknis = lebih ilmiah" → clarity lebih penting
4. "Discussion = ringkasan Results" → Discussion = interpretasi + konteks

---

## Template A.15 — Paper Structure Checklist

```
PAPER STRUCTURE CHECKLIST

Title   : ____________________
Target  : [ ] Jurnal  [ ] Konferensi  [ ] Laporan

Section Check:
  [ ] Abstract — masalah, metode, hasil utama, kontribusi (max 250 kata)
  [ ] Introduction — konteks → gap → RQ → kontribusi → struktur paper
  [ ] Related Work — concept-centric, gap positioning
  [ ] Method — reproducible: desain, variabel, metrik, setup, prosedur
  [ ] Results — tabel + grafik + observasi (tanpa interpretasi)
  [ ] Discussion — interpretasi, perbandingan, implikasi, limitation
  [ ] Conclusion — jawaban RQ, kontribusi, future work

Consistency Matrix:
  [ ] RQ di Introduction = RQ di Method = RQ di Conclusion
  [ ] Variabel di Method = variabel di Results
  [ ] Klaim di Discussion didukung data di Results
  [ ] Limitasi di Discussion di-address di Conclusion/Future Work

Writing Quality:
  [ ] Clarity — mudah dipahami tanpa re-read
  [ ] Precision — tidak ada istilah ambigu
  [ ] Conciseness — tidak ada kalimat redundan
```

---

## Latihan 1 — Paper Outline

Buat outline paper untuk riset Anda menggunakan struktur IMRAD.

| Section | Konten Utama (2-3 kalimat) | Target Kata |
|---------|---------------------------|------------|
| Abstract | Transformasi digital SPBE di Indonesia menghadapi tantangan kerentanan data yang tinggi. Studi ini mengevaluasi efektivitas penerapan ISO 27001 dibandingkan praktik mandiri dalam memitigasi insiden kebocoran. Hasil menunjukkan penurunan insiden signifikan dengan pendekatan tata kelola terstandar. | 250 |
| Introduction | Latar belakang: Lonjakan serangan siber pada sistem pemerintah. Gap: Kurangnya model mitigasi terintegrasi di tingkat daerah. RQ: Seberapa efektif ISO 27001 dibandingkan praktik mandiri? | 600 |
| Related Work | Tinjauan kebijakan SPBE, literatur tentang keamanan siber sektor publik, dan kerangka kerja tata kelola TI global/nasional.| 800|
| Method |Eksperimen komparatif pada pemerintah daerah, mencakup variabel SOP, pelatihan SDM, dan audit teknis sebagai intervensi. | 1000 |
| Results |Perbandingan statistik frekuensi insiden kebocoran data sebelum dan sesudah intervensi pada kedua kelompok | 600 |
| Discussion |Analisis mengapa SDM menjadi faktor krusial dan bagaimana hambatan birokrasi mempengaruhi implementasi standar keamanan. | 700 |
| Conclusion |Kesimpulan bahwa tata kelola terstandar adalah prasyarat wajib untuk ketahanan digital nasional. | 300 |

---

## Latihan 2 — Consistency Matrix

Buat consistency matrix untuk memverifikasi internal consistency paper Anda.

|  | Intro | Method | Result | Discussion | Conclusion |
|--|-------|--------|--------|-----------|-----------|
| RQ1 |✓ |✓ |✓ |✓ | ✓|
| Metrik utama |✓ |✓ |✓ |✓ |✓ |
| Variabel IV |✓ |✓ |✓ |- |✓ |
| Variabel DV | ✓| ✓| ✓| ✓| ✓|
| Klaim/kontribusi |✓ |X |✓ |✓ |✓ |

**Isi setiap sel:** ✓ (ada & konsisten), ✗ (missing), ~ (ada tapi inkonsisten)

**Inkonsistensi yang ditemukan:**
> Variabel IV pada bagian metode kurang mengeksplorasi kendala birokrasi yang muncul di bagian diskusi.___________________________________________________

**Tindakan perbaikan:**
> ______Menambahkan variabel kontrol atau penjelasan kualitatif di bagian metode tentang hambatan adopsi SOP di pemerintah daerah._____________________________________________

---

## Latihan 3 — Writing Quality Check

Ambil satu paragraf dari tulisan Anda (atau tulis paragraf baru) dan evaluasi kualitasnya.

**Paragraf asli:**
> "Keamanan siber di daerah sangat penting karena banyak peretasan terjadi. Implementasi ISO 27001 akan membuat sistem lebih aman dan hasilnya akan lebih bagus dari praktik yang sudah ada sekarang di instansi tersebut."

| Kriteria | Evaluasi | Perbaikan |
|----------|---------|-----------|
| Clarity | AMBIGU | Gunakan "tingkat insiden menurun".|
| Precision | "Sangat penting" terlalu subjektif.| Ganti dengan data kerugian atau risiko.|
| Conciseness |Terlalu banyak kata pengisi. |perbaikan kalmat |

**Paragraf setelah perbaikan:**
> "Penerapan standar ISO 27001 pada sistem pelayanan publik daerah terbukti signifikan menurunkan insiden kebocoran data dibandingkan dengan praktik manajemen keamanan mandiri. Pendekatan terstandar ini memberikan kerangka kerja mitigasi risiko yang lebih terukur dalam menghadapi eskalasi ancaman siber nasional."

---

## Refleksi

> Apa perbedaan antara menulis "tentang" riset dan menulis sebagai "argumen" riset? Bagaimana urutan penulisan (Method → Discussion → Introduction) mengubah kualitas tulisan?

> Menulis "tentang" vs "sebagai argumen":
Menulis "tentang" riset hanyalah melaporkan apa yang dilakukan (deskriptif), sedangkan menulis "sebagai argumen" adalah membangun narasi persuasif yang memposisikan riset Anda sebagai solusi yang diperlukan untuk menutup celah pengetahuan.

Ubah urutan penulisan:
Urutan Method → Discussion → Introduction sangat disarankan karena:

1.Method & Results memberikan fakta keras sebagai pondasi argumen.

2.Discussion memetakan hasil tersebut ke arah signifikansi yang lebih luas.

3.Introduction ditulis terakhir agar penulis tahu persis "janji" apa yang akan diberikan kepada pembaca berdasarkan hasil riset yang sudah solid, sehingga menghindari mismatch antara klaim di depan dengan hasil di belakang.___________________________________________________
> ___________________________________________________
