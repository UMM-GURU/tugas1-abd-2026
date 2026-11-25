# Tugas 1: Eksplorasi dan Analisis Dataset Besar Indonesia (`stocks.csv`)

Repository ini berisi pengerjaan **Tugas 1 — Analisis Big Data 2026** menggunakan dataset saham Indonesia (`stocks.csv`, ~136,3 MB, > 2 juta baris) dengan pendekatan *lazy evaluation* **Polars**, analitik SQL **DuckDB**, serta visualisasi interaktif **Plotly**.

## Ringkasan Dataset & Alur Kerja

- **Dataset mentah:** `data/raw/stocks.csv` (~136,3 MB, 2.061.655 baris, 7 kolom: `datetime`, `symbol`, `open`, `high`, `low`, `close`, `volume`). Detail sumber dan instruksi dataset dicatat pada `data/README.md` (file data besar tidak di-commit ke Git).
- **Milestone 1 (`notebooks/01_data_profiling.ipynb`):** Profil awal skema, jumlah baris, deteksi *null*, serta ringkasan statistik menggunakan Polars LazyFrame dan DuckDB `SUMMARIZE`.
- **Milestone 2 (`notebooks/02_data_cleaning.ipynb`):** Deteksi dan penanganan *missing values*, validasi harga/OHLC, deduplikasi berdasarkan kunci `["symbol", "datetime"]`, verifikasi kualitas data, lalu penyimpanan hasil ke `data/processed/dataset_bersih.parquet`.
- **Milestone 3 & Final (`notebooks/03_eda_and_insight.ipynb`):** Analisis deret waktu (`datetime`) dan eksplorasi emiten menggunakan `data/processed/dataset_bersih.parquet`, dilengkapi 6 visualisasi interaktif Plotly serta minimal 5 insight utama.

## Struktur Repository

```text
.
├── .github/workflows/lint_check.yml
├── data/
│   ├── README.md
│   └── processed/            
├── notebooks/
│   ├── 01_data_profiling.ipynb
│   ├── 02_data_cleaning.ipynb
│   └── 03_eda_and_insight.ipynb
├── output/figures/
├── src/
├── Dockerfile
├── requirements.txt
└── README.md