# Tugas 1: Eksplorasi dan Analisis Dataset Besar Indonesia

Template untuk Tugas 1 mata kuliah Analisis Big Data. Setelah repository GitHub Classroom dibuat, ubah nama repository menjadi `tugas1-[username_github]`.

## Milestone

| Tahap | Target | Bukti yang dikumpulkan |
|---|---|---|
| Milestone 1 | Pertemuan 3 | Dataset >= 500 MB atau > 1 juta baris, `data/README.md`, dan `notebooks/01_data_profiling.ipynb` |
| Milestone 2 | Pertemuan 5 | Cleaning dengan Polars dan profiling DuckDB `SUMMARIZE` |
| Milestone 3 | Pertemuan 8 | Analisis temporal/ruang dan minimal 6 visualisasi interaktif |
| Final | Pertemuan 10 | Minimal 5 insight, Dockerfile, dan dokumentasi akhir |

## Output yang Diharapkan

Pada final submission, repository harus menghasilkan analisis yang dapat dijalankan ulang dari awal dan memuat:

- Dataset Indonesia yang terdokumentasi, berukuran minimal 500 MB atau lebih dari 1 juta baris, beserta instruksi unduhnya.
- Notebook profiling, cleaning, serta EDA yang dapat dieksekusi berurutan.
- Cleaning dan validasi data untuk missing values, duplikasi, outlier, serta aturan kualitas yang relevan dengan dataset.
- Analisis temporal atau spasial, minimal 6 visualisasi interaktif dengan Plotly atau Altair, dan minimal 5 insight analitik yang didukung hasil analisis.
- Environment yang dapat direproduksi melalui `Dockerfile`, `requirements.txt`, dan petunjuk eksekusi di README.
- Riwayat commit bertahap yang menunjukkan proses kerja pada setiap milestone.

## Kaitan dengan Materi Perkuliahan

| Materi | Pertemuan | Penerapan pada Tugas 1 |
|---|:---:|---|
| Polars dan lazy evaluation | 2 | Profiling dan transformasi dataset besar dengan `scan_*`, expressions, dan pipeline efisien. |
| DuckDB dan format data | 3 | Query analitik serta profiling dengan `SUMMARIZE`; gunakan Parquet bila sesuai. |
| Data quality dan cleaning | 4 | Tangani missing values, duplikasi, outlier, dan validasi data. |
| EDA dan visualisasi | 5 | Bangun visualisasi interaktif serta rumuskan insight analitik. |
| Time series | 6 | Terapkan analisis pola waktu atau pola spasial yang relevan dengan dataset. |
| Dask, NLP, dan ML | 7-9 | Opsional sebagai pengembangan jika relevan dengan skala dan pertanyaan analisis. |
| Streamlit dan Docker | 10-11 | Dokumentasikan environment Docker; dashboard Streamlit bersifat opsional untuk Tugas 1. |

## Ringkasan Penilaian

Nilai Tugas 1 berbobot 25% dari nilai akhir. Penilaian lengkap ada di dokumen spesifikasi tugas; ringkasannya sebagai berikut.

| Aspek | Bobot | Indikator utama |
|---|:---:|---|
| Konsistensi commit dan GitHub workflow | 20% | Commit bertahap, pesan deskriptif, struktur repository rapi, dan pemeriksaan otomatis lulus. |
| Data handling dengan Polars dan DuckDB | 25% | Pengolahan data besar efisien, memakai Polars dan DuckDB sesuai peran masing-masing. |
| Cleaning dan data quality | 15% | Profiling, validasi, serta penanganan null dan outlier terdokumentasi. |
| Visualisasi dan insight | 25% | Visualisasi interaktif informatif dan insight analitik yang didukung data. |
| Reproduktivitas dan Docker | 15% | Dockerfile, dependency, dan instruksi eksekusi memungkinkan proyek dijalankan ulang. |

Target kualitas tertinggi adalah analisis yang efisien, terdokumentasi, dapat direproduksi, dan memperlihatkan proses kerja konsisten sepanjang milestone; bukan hanya hasil akhir yang terlihat baik.

## Struktur Repository

```text
.
├── .github/workflows/lint_check.yml
├── data/README.md
├── notebooks/
│   ├── 01_data_profiling.ipynb
│   ├── 02_data_cleaning.ipynb
│   └── 03_eda_and_insights.ipynb
├── output/figures/
├── src/
├── Dockerfile
├── requirements.txt
└── README.md
```

## Menjalankan Project

```bash
docker build -t tugas1-bigdata .
docker run --rm -p 8888:8888 -v "$(pwd)":/home/jovyan/work tugas1-bigdata
```

Buka JupyterLab pada `http://localhost:8888/lab`. Konfigurasi Dockerfile menjalankan JupyterLab tanpa password atau token untuk penggunaan lokal. Jangan gunakan konfigurasi ini pada server atau jaringan publik. Letakkan dataset pada `data/raw/`, lalu sesuaikan `DATA_PATH` di notebook profiling.

## Aturan Teknis

- Gunakan Polars untuk manipulasi data dan DuckDB untuk analitik SQL.
- Dataset harus minimal 500 MB atau lebih dari 1 juta baris.
- Jangan commit file data besar; simpan instruksi unduhan dan sumber data pada `data/README.md`.
- Gunakan commit bertahap dan pesan yang jelas, misalnya `feat: add initial dataset profiling`.

## Integritas Akademik dan Penggunaan AI

- Dilarang menyalin kode, laporan, atau visualisasi mahasiswa lain maupun repository publik tanpa sitasi dan atribusi yang jelas.
- Dilarang menggunakan jasa joki atau menyerahkan pekerjaan yang tidak dapat dijelaskan sendiri.
- AI boleh digunakan untuk belajar, mencari rujukan, menjelaskan konsep, atau debugging. AI tidak menggantikan tanggung jawab mahasiswa atas kebenaran dan kualitas solusi.
- Mahasiswa wajib dapat menjelaskan setiap bagian kode, menjalankan serta memverifikasi ulang hasilnya, dan memastikan penggunaan Polars serta DuckDB sesuai standar kuliah.
- Setiap penggunaan AI harus dicantumkan pada bagian AI Disclosure Statement di bawah.
- Pelanggaran pertama bernilai 0 untuk tugas terkait; pelanggaran berikutnya dapat berakibat nilai E untuk mata kuliah sesuai ketentuan akademik.

## AI Disclosure Statement

Isi bagian ini sebelum pengumpulan akhir.

> Alat AI yang digunakan: [nama alat].
>
> Bagian yang dibantu: [contoh: penjelasan error Polars atau review dokumentasi].
>
> Verifikasi yang dilakukan: [contoh: menjalankan ulang kode, memeriksa dokumentasi resmi, dan memahami setiap cell].
