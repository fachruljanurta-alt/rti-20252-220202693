# WS-16: Presentation & Defense (UAS)

> **Bab 16 — Presentasi & Pertahanan Ilmiah**

---

## Ringkasan Materi

### Scientific Defense Model

```
Research Work → Presentation → Questioning → Defense → Evaluation → Acceptance
```

### Presentasi ≠ Ringkasan Paper

| Paper | Presentasi |
|-------|-----------|
| Dibaca (self-paced) | Didengar (presenter-paced) |
| Detail lengkap | Ide kunci + highlight |
| Tabel numerik detail | Grafik visual + angka kunci |
| Pembaca bisa re-read | Audiens dengar sekali |

**Prinsip:** Presentasi membutuhkan **reformulasi**, bukan kompresi. Medium berbeda = pendekatan berbeda.

### Claim-Evidence-Reasoning (CER)

Setiap jawaban defense harus memiliki:
1. **Claim** — Pernyataan yang dijawab
2. **Evidence** — Data/fakta pendukung
3. **Reasoning** — Logika yang menghubungkan evidence ke claim

**Contoh:**
| Pertanyaan | Bad Answer | Good Answer (CER) |
|-----------|-----------|-------------------|
| "Kenapa hanya 3 dataset?" | "Tiga sudah cukup" | "3 dataset mewakili variasi: small-clean, medium-clean, medium-noisy [E]. Generalisasi perlu validasi lanjut — listed as limitation [R]" |
| "Hasil DS-3 menurun?" | "Itu outlier" | "Ya, karena distribusi heavy-tail melanggar asumsi Gaussian [E]. Ini menunjukkan boundary condition metode [R]" |
| "Effect size?" | "p=0.003, jadi signifikan" | "Cohen's d=1.2 (large effect) [E] — bukan hanya signifikan tapi substansial [R]" |

### Slide Design — One Slide, One Message

**Optimal 9-Slide Plan (15 menit):**

| # | Slide | Waktu | Pesan |
|---|-------|-------|-------|
| 1 | Title + context | 1 min | Apa ini tentang apa |
| 2 | Problem + motivation | 2 min | Mengapa penting |
| 3 | Gap + RQ | 1.5 min | Apa yang belum terjawab |
| 4 | Method overview | 2 min | Bagaimana dijawab (diagram) |
| 5 | Key result — tabel | 2 min | Temuan utama |
| 6 | Key result — grafik | 2 min | Pola visual |
| 7 | Interpretation + failure | 2 min | Apa artinya |
| 8 | Limitation + future | 1.5 min | Batasan & arah |
| 9 | Conclusion + contribution | 1 min | Closing message |

### Anticipatory Defense

Prediksi pertanyaan berdasarkan kategori:

| Kategori | Contoh Pertanyaan |
|---------|------------------|
| Problem | "Mengapa masalah ini penting?" |
| Gap | "Bagaimana dengan studi X yang sudah menjawab ini?" |
| Method | "Mengapa metode ini, bukan Y?" |
| Results | "Bagaimana menjelaskan anomali di DS-3?" |
| Generalization | "Apakah bisa diterapkan di domain lain?" |

### Tiga Prinsip Jawaban

1. **Direct** — Jawab dulu, elaborasi kemudian
2. **Data-based** — Tunjuk evidence spesifik
3. **Honest** — Akui limitasi jika memang ada

### Jebakan Kognitif

1. "Presentasi = semua yang ada di paper" → terlalu padat
2. "Slide cantik = presentasi bagus" → konten > estetika
3. "Tidak bisa jawab = gagal" → "I don't know, but..." menunjukkan kejujuran
4. "Tidak perlu latihan — saya paham riset saya" → latihan = menemukan celah

---

## Template A.16 — Defense Preparation Sheet

```
DEFENSE PREPARATION

Slide Deck Plan:
  Total slides   : ____ (target: 10-12 konten + title/closing)
  Time per slide : ~2 min
  Total time     : ____ menit

Slide Outline:
| # | Pesan Utama | Visual | Waktu |
|---|-------------|--------|-------|
| 1 | Title       |        | 30s   |
| 2 | Problem     |        | 2min  |
| 3 | Gap + RQ    |        | 2min  |
| ..|             |        |       |

Anticipatory Defense Matrix:
| Kategori | Pertanyaan Potensial | Jawaban (CER) |
|----------|---------------------|---------------|
| Problem  |                     |               |
| Gap      |                     |               |
| Method   |                     |               |
| Results  |                     |               |
| Generalization |               |               |

Latihan:
  Latihan 1: [tanggal] — [catatan timing & feedback]
  Latihan 2: [tanggal] — [catatan timing & feedback]
  Latihan 3: [tanggal] — [catatan timing & feedback]
```

---

## Latihan 1 — Slide Outline

Rencanakan presentasi 15 menit untuk riset Anda.

| # | Pesan Utama | Visual yang Digunakan | Waktu |
|---|-------------|----------------------|-------|
| 1 | Judul, Penulis, & Latar Belakang Transformasi Digital | Title slide, logo instansi/UI | 1 min |
| 2 | Fenomena: Lonjakan serangan siber vs Rendahnya maturitas SPBE | Infografis data BSSN & Indeks SPBE | 2 min |
| 3 | Gap: Kesenjangan tata kelola antar-instansi daerah | Peta/Grafik disparitas antar-daerah | 1.5 min |
| 4 |RQ: Efektivitas ISO 27001 dalam memitigasi risiko | Diagram alur RQ dan tujuan riset|1 |
| 5 |Metodologi: Pendekatan studi komparatif (ISO vs Mandiri) | Flowchart desain eksperimen|2 |
| 6 | Temuan Utama: Dampak penerapan tata kelola terhadap insiden| Bar chart: penurunan insiden siber|3 |
| 7 |Diskusi: Peran krusial SDM & hambatan birokrasi |Foto/Ikon SDM, box tantangan |2.5 |
| 8 | Kesimpulan & Implikasi Kebijakan|Bullet points poin-poin kunci |1 |
| 9 | Sesi Tanya Jawab (Q&A)| Slide penutup "Terima Kasih"| 1|

**Total waktu estimasi:** ___15_ menit

---

## Latihan 2 — Anticipatory Defense

Prediksi 5 pertanyaan yang mungkin diajukan penguji, lalu siapkan jawaban CER.

| # | Pertanyaan | Claim | Evidence | Reasoning |
|---|----------|-------|----------|-----------|
| 1 |  Mengapa ISO 27001? Bukankah itu standar industri, bukan pemerintah? | ISO 27001 adalah best practice internasional yang universal. | Riset Alfi et al. (2023) menunjukkan standar ini efektif untuk interoperabilitas data. | Tata kelola yang terstandar meminimalisir human error yang menjadi celah utama serangan siber. |
| 2 | Apakah data insiden siber cukup valid mengingat banyak instansi tidak melapor? | Validitas data ditingkatkan melalui triangulasi dengan BSSN. |  Audit mandiri instansi dibandingkan dengan laporan resmi BSSN | Perbedaan data mencerminkan gap pelaporan yang juga menjadi temuan riset ini. |
| 3 |Bagaimana jika disparitas anggaran antar-daerah menjadi variabel pengganggu? |Anggaran bukan variabel tunggal penentu keamanan. |Data menunjukkan daerah dengan anggaran terbatas tetap bisa aman dengan SOP yang baik. |  `Tata kelola (kebijakan) seringkali lebih murah dan efektif daripada sekadar investasi perangkat mahal.|

---

## Latihan 3 — Simulasi Q&A

Minta teman/kolega mengajukan 3 pertanyaan tentang riset Anda. Catat pertanyaan dan evaluasi jawaban Anda.

| # | Pertanyaan | Jawaban Saya | Evaluasi |
|---|-----------|-------------|---------|| *1* | "Apa yang dilakukan jika instansi menolak transparan?" | "Kami menggunakan data agregat BSSN sebagai validasi silang (triangulasi) untuk memitigasi reporting bias." | [✓] Direct [✓] Data-based [✓] Honest|
| 2 |"Apakah riset ini bisa diterapkan di sektor swasta?" |"Bisa, namun fokus kebijakan SPBE di sini spesifik untuk konteks tata kelola pemerintahan." | [✓] Direct [✓] Data-based [✓] Honest |
| 3 | "Apakah ISO 27001 menjamin keamanan 100%?"| "Tidak ada sistem yang 100% aman; ISO 27001 adalah proses mitigasi risiko yang berkelanjutan (PDCA)."| [✓] Direct [✓] Data-based [✓] Honest|

**Pertanyaan yang paling sulit dijawab:**
> ___________________________________________________"Bagaimana membedakan antara serangan siber yang sukses karena sistem lemah atau karena memang serangan tersebut sangat canggih?"

**Apa yang perlu disiapkan lebih baik:**
> ______________________________________________Penjelasan tentang Threat Modeling dan Post-Incident Analysis untuk membedakan antara kegagalan kontrol keamanan dasar vs serangan Zero-Day._____

---

## Refleksi

> Dari seluruh proses WS-01 sampai WS-16 — dari paradigma riset hingga presentasi — bagian mana yang paling mengubah cara Anda berpikir tentang riset? Apa satu hal yang akan selalu Anda terapkan di riset berikutnya?

**Insight terbesar:**
> Riset bukanlah upaya mencari kebenaran mutlak, melainkan upaya memperkecil ketidakpastian melalui metodologi yang terstruktur dan argumen yang jujur. Bagian paling mengubah pikiran adalah operationalization chain — ternyata mendefinisikan metrik dengan presisi jauh lebih sulit daripada sekadar membaca data.___________________________________________________

**Yang akan selalu diterapkan:**
>Prinsip Ablation/Modularity. Sebelum membangun sistem atau kebijakan, saya akan selalu membedah bagian mana yang paling memberikan dampak agar riset/solusi saya selalu berbasis data (evidence-based), bukan sekadar asumsi "fitur lengkap". ___________________________________________________
