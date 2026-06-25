# WS-08: Proposal Integration (UTS)

> **Bab 8 — Proposal & Checkpoint**

---

## Ringkasan Materi

### Proposal = Satu Argumen Utuh

Proposal riset bukan kumpulan bab yang independen. Ia adalah **satu argumen** yang mengalir dari masalah ke rencana solusi. Jika satu koneksi putus, seluruh proposal kehilangan koherensi.

### Integration Map — 6 Koneksi Kritis

```
Problem (Bab 2) → Gap (Bab 3) → RQ & H (Bab 4) → Metrik (Bab 5) → Sistem (Bab 6) → Eksperimen (Bab 7)
```

| Koneksi | Pertanyaan Verifikasi |
|---------|----------------------|
| Problem → Gap | Apakah gap muncul dari analisis literatur terhadap masalah? |
| Gap → RQ | Apakah RQ langsung menjawab gap yang teridentifikasi? |
| RQ → Metrik | Apakah setiap variabel di RQ punya metrik terdefinisi? |
| Metrik → Sistem | Apakah setiap metrik bisa diukur oleh komponen sistem? |
| Sistem → Eksperimen | Apakah desain eksperimen menggunakan sistem sebagai instrumen? |

### Koherensi Vertikal + Horizontal

- **Vertikal** — Alur logis atas-ke-bawah (problem → experiment). Setiap section menjawab pertanyaan yang diangkat section sebelumnya dan memunculkan pertanyaan baru.
- **Horizontal** — Konsistensi terminologi (nama variabel di RQ = di hipotesis = di metrik = di desain)

**Operasionalisasi Red Thread** (benang merah):
```
Bab 2 (Problem) → | memperkenalkan masalah X + evidensi |
                          ↓ menimbulkan pertanyaan: "apa akar gap-nya?"
Bab 3 (Gap)     → | menjawab pertanyaan tadi + membuka "lalu apa yang perlu diteliti?" |
                          ↓
Bab 4 (RQ/H)    → | menjawab gap dengan pertanyaan spesifik + prediksi terukur |
                          ↓
Bab 5-7 (Method)→ | menjawab RQ melalui desain eksperimen yang tepat |
```
Jika ada lompatan (section B tidak menjawab pertanyaan section A), red thread putus.

### Jebakan Kognitif

| Jebakan | Deskripsi |
|---------|----------|
| "Selling" Introduction | Menulis promosi, bukan menyajikan data dan gap |
| Copy-paste Methodology | Menyalin deskripsi tekstbook tanpa menyesuaikan ke RQ |
| Optimistic Timeline | Meremehkan waktu implementasi; selalu tambah buffer 30-50% |
| No Possibility of Failure | Mengimplikasikan hasil pasti sukses — proposal jujur mengakui H₀ mungkin tidak ditolak |

### Struktur Proposal

1. **Pendahuluan** — Latar belakang + problem statement (Bab 1-2)
2. **Tinjauan Pustaka** — Literature review + gap + baseline (Bab 3)
3. **RQ / Kontribusi / Hipotesis** — (Bab 4)
4. **Metodologi** — Metrik + sistem + desain eksperimen (Bab 5-7)
5. **Timeline & Output**

### Istilah Penting

- **Integration Map** — Diagram 6 koneksi kritis antar komponen proposal
- **Vertical Coherence** — Alur logis atas-ke-bawah
- **Horizontal Coherence** — Konsistensi terminologi di semua bagian
- **Checkpoint** — Titik self-assessment sebelum transisi dari desain ke eksekusi

---

## Template A.8 — Integration Checklist

```
PROPOSAL INTEGRATION CHECKLIST

Koneksi Vertikal (Flow Atas-Bawah):
  [ ] Problem → Gap: masalah terdokumentasi di literatur
  [ ] Gap → RQ: pertanyaan menjawab gap spesifik
  [ ] RQ → Hypothesis: hipotesis memprediksi jawaban
  [ ] Hypothesis → Metric: metrik mengukur variabel dalam hipotesis
  [ ] Metric → System: komponen sistem menghasilkan/mengukur metrik
  [ ] System → Experiment: desain eksperimen menggunakan sistem

Koneksi Horizontal (Konsistensi):
  [ ] Istilah sama di semua bagian
  [ ] Variabel di RQ = variabel di hipotesis = metrik di desain
  [ ] Scope tidak berubah dari masalah ke eksperimen

Cognitive Trap Checklist:
  [ ] Tidak ada paragraf "promosi" di pendahuluan (hanya data & gap)
  [ ] Metodologi disesuaikan ke RQ, bukan copy-paste textbook
  [ ] Timeline sudah ditambah buffer 30-50% dari estimasi awal
  [ ] Proposal mengakui kemungkinan H0 tidak ditolak (honest uncertainty)
  [ ] Tidak ada klaim "pasti berhasil" atau "meningkatkan signifikan"

Rubrik Self-Assessment:
| Kriteria     | 1 (Lemah)                                        | 2 (Cukup)                                     | 3 (Baik)                                           | Skor |
|------------- |--------------------------------------------------|-----------------------------------------------|----------------------------------------------------|------|
| Koherensi    | >2 koneksi vertikal terputus                     | 1-2 koneksi lemah, argumen masih bisa diikuti | Semua 6 koneksi terhubung, red thread jelas        |      |
| Specificity  | Variabel/metrik masih abstrak, tidak ada angka   | Sebagian metrik terdefinisi numerik           | Semua metrik + threshold + unit pengukuran jelas   |      |
| Feasibility  | Timeline >6 bulan tanpa memperhitungkan sumber   | Timeline 3-6 bulan dengan asumsi tertentu     | Timeline 1-3 bulan realistis dengan rencana detail |      |
| Rigor        | Baseline tidak jelas atau straw man              | 1-2 baseline dengan justifikasi partial       | 2+ baseline SOTA + justifikasi pemilihan lengkap   |      |
```

---

## Latihan 1 — Kompilasi Proposal Mini

Kumpulkan hasil dari WS-02 sampai WS-07 menjadi satu ringkasan proposal.

| Komponen | Sumber | Isi (1-2 kalimat) |
|----------|--------|-------------------|
| Problem Statement | WS-02 | Integrasi sistem pelayanan publik (SPBE) berjalan masif, namun tingkat implementasi yang "Sangat Baik" rendah (2,89%) dan rentan serangan siber (370 juta+ kasus). |
| Gap | WS-03 | Tidak ada model mitigasi risiko yang seragam dan terintegrasi untuk interoperabilitas data antar-instansi daerah yang memiliki disparitas kapasitas digital. |
| RQ | WS-04 | Bagaimana efektivitas kerangka kerja tata kelola berbasis ISO 27001 dibandingkan praktik mandiri dalam memitigasi kebocoran data di pemerintah daerah? |
| Hipotesis | WS-04 | H₁: Penerapan ISO 27001 secara signifikan menurunkan frekuensi insiden kebocoran data (≥30%) dibandingkan praktik mandiri. |
| Variabel & Metrik | WS-05 | IV = Metode tata kelola (ISO vs Mandiri); DV = Jumlah insiden kebocoran data; Metrik = Frekuensi insiden per kuartal. |
| Sistem | WS-06 |Modul kebijakan tata kelola (ISO 27001) yang diintegrasikan ke dalam SOP audit keamanan data instansi pemerintah daerah. |
| Desain Eksperimen | WS-07 |Studi komparatif antara dua kelompok instansi daerah (kelompok kontrol: praktik mandiri; kelompok perlakuan: penerapan ISO 27001). |

---

## Latihan 2 — Integration Checklist

Verifikasi 6 koneksi kritis. Isi dengan merujuk tabel di Latihan 1.

| Koneksi | Status | Bukti |
|---------|--------|-------|
| Problem → Gap |  ✅    |Literasi menunjukkan riset saat ini masih sektoral dan belum ada model mitigasi SPBE yang terintegrasi. |
| Gap → RQ |  ✅  | RQ fokus pada pengujian efektivitas kerangka kerja untuk menutup gap disparitas tata kelola.|
| RQ → Hypothesis |  ✅  |H₁ secara spesifik memprediksi dampak ISO 27001 terhadap insiden data sesuai RQ. |
| Hypothesis → Metric |  ✅   | Metrik "frekuensi insiden" langsung digunakan untuk menguji H₁.|
| Metric → System |  ✅   | Sistem memonitor insiden sebagai output dari implementasi tata kelola.|
| System → Experiment |✅ |Eksperimen membandingkan penerapan sistem di dua kondisi (ISO vs Mandiri). |

**Koneksi mana yang paling lemah?**Metric → System. _______________________
**Bagaimana cara memperkuatnya?**
> _Melakukan validasi data dengan triangulasi laporan BSSN agar metrik frekuensi insiden benar-benar merefleksikan performa sistem keamanan di lapangan.__________________________________________________

**Konsistensi horizontal — apakah istilah dan scope konsisten?** [x ] Ya / [ ] Tidak
> Jika tidak, di bagian mana terjadi inkonsistensi? _________

---

## Latihan 3 — Rubrik Self-Assessment

Evaluasi proposal mini menggunakan rubrik.

| Kriteria | Skor (1-3) | Justifikasi |
|----------|-----------|-------------|
| Koherensi | 3 |Alur dari masalah nasional hingga desain eksperimen bersifat logis dan linier. |
| Specificity | 3 |Metrik (insiden) dan metode (ISO 27001) sudah terdefinisi secara operasional. |
| Feasibility | 2| Bergantung pada kerja sama instansi pemerintah daerah yang seringkali sulit diakses.|
| Rigor |3 |Desain eksperimen komparatif memberikan dasar inferensi yang kuat. |

**Skor total:** 11_____ / 12

**Apakah proposal siap untuk fase eksekusi?** [ ] Ya / [ x] Belum
> Jika belum, apa yang perlu diperbaiki? _Perlu membangun jaringan atau surat izin riset kepada pihak terkait agar akses data insiden di tingkat daerah dapat terjamin kualitasnya._________________

---

## Refleksi

> Dari seluruh proses WS-01 sampai WS-08, bagian mana yang paling mudah dan paling sulit? Mengapa? Apa yang akan dilakukan berbeda jika mengulang dari awal?

**Bagian termudah:** _Problem Formation (karena masalah keamanan siber di Indonesia sangat nyata dan datanya melimpah).___________________________________
**Bagian tersulit:** Threat Analysis & Fairness (karena mengontrol variabel di lingkungan pemerintahan yang heterogen sangatlah menantang secara teknis dan politis).____________________________________
**Yang akan dilakukan berbeda:** Jika mengulang, saya akan lebih awal menentukan akses data sebagai variabel penentu (feasibility constraint) sebelum merumuskan desain eksperimen, agar proposal tidak sekadar ideal di atas kertas namun mustahil di lapangan.
> ___________________________________________________
> ___________________________________________________
