# Quality Gate Dokumentasi dan Pemulihan

Isi dengan `PASS`, `FAIL`, `UNKNOWN`, dan bukti/tautan. `UNKNOWN` tidak boleh diam-diam dianggap PASS.

| Pemeriksaan | Status | Bukti |
|---|---|---|
| Repo, branch, commit teridentifikasi | UNKNOWN | |
| README sesuai implementasi | UNKNOWN | |
| Semua command instalasi telah dicoba | UNKNOWN | |
| API, UI, atau aplikasi memiliki smoke test | UNKNOWN | |
| Dataset provenance asli, versi dan lisensi tercatat | UNKNOWN | |
| Dataset tersedia lokal dan di backup kedua | UNKNOWN | |
| Data cleaning, duplicate/leakage dan split terdokumentasi | UNKNOWN | |
| Checkpoint ditemukan atau URL hosting terverifikasi | UNKNOWN | |
| Checkpoint SHA-256 dan class mapping/preprocessing benar | UNKNOWN | |
| Inference dari checkpoint pulih terbukti bekerja | UNKNOWN | |
| Validasi, held-out test dan external evaluation terpisah | UNKNOWN | |
| Batasan risiko dan domain shift tertulis | UNKNOWN | |
| Secret / data privat tidak bocor | UNKNOWN | |
| Tautan internal dan visual valid | UNKNOWN | |
| Git diff ditinjau sebelum publikasi | UNKNOWN | |

## Rilis
- **Documentation ready** hanya jika klaim penting berbukti dan tidak ada FAIL kritis.
- **Recoverable** hanya jika checkpoint/dataset sesuai kebutuhan bisa dipulihkan pada lingkungan uji.
- **Reproducible** membutuhkan pengujian eksplisit, bukan hanya notebook tersedia.
