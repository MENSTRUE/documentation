# documentation — Standar Dokumentasi & Pemulihan Proyek

> **Kode bisa terlupakan. Proyek harus tetap bisa dipahami, dijalankan, dilatih ulang, dan dipulihkan.**

Repositori ini adalah **pusat standar dokumentasi yang dapat digunakan ulang untuk semua proyek**: AI/ML, Android, backend, frontend, data engineering, riset, otomasi, dan aplikasi lainnya. Bahasa utama: **Bahasa Indonesia**. Ini bukan repositori penyimpanan dataset atau checkpoint; masing-masing proyek menyimpan dan menautkan artefaknya dengan cara yang sesuai.

## Mulai di sini

1. Salin [MASTER_PROMPT_DOKUMENTASI.md](prompts/MASTER_PROMPT_DOKUMENTASI.md) lalu tambahkan tautan repository proyek dan file bukti yang tersedia.
2. Gunakan [template dokumentasi proyek](templates/README_PROYEK.md) sebagai kerangka **berbasis bukti**, bukan sekadar mengganti nama.
3. Catat data di [registri dataset](templates/REGISTRI_DATASET.csv) dan checkpoint di [registri model](templates/REGISTRI_MODEL.csv).
4. Ikuti [panduan penyimpanan dan pemulihan](panduan/PENYIMPANAN_DAN_PEMULIHAN.md).
5. Jalankan [checklist rilis dokumentasi](checklists/QUALITY_GATE.md) sebelum commit.

## Prinsip yang tidak boleh dikompromikan

- **Repositori aktual dan artefak eksperimen adalah sumber kebenaran**: jangan mengarang fitur, endpoint, metrik, label, lisensi, atau status deployment.
- **Dokumentasi bukan backup data**. Dataset/model yang hendak dipakai lagi harus tetap tersedia pada penyimpanan yang dapat diakses, berizin, dan memiliki checksum.
- **Checkpoint tidak dilarang masuk GitHub.** Pilih Git reguler, Git LFS, GitHub Releases, atau model registry berdasarkan ukuran, lisensi, dan kebutuhan reproduksi.
- **Data privat tetap privat**. Cantumkan prosedur akses tanpa mengungkap token, dataset terlindungi, informasi pribadi, atau rahasia.
- **Model tanpa konteks berisiko tidak dapat digunakan**. Simpan class mapping, preprocessing, dependency versions, manifest, dan cara inference.
- **Jangan klaim 100% reproducible** jika data privat, versi dependency belum dibekukan, atau checkpoint belum dapat dipulihkan.
- Status **ada / teruji / direncanakan** harus berbeda. Hasil validasi tidak sama dengan held-out test atau uji eksternal.

## Peta berkas

| Berkas | Fungsi |
| --- | --- |
| `prompts/MASTER_PROMPT_DOKUMENTASI.md` | Instruksi universal untuk AI/coding agent |
| `templates/README_PROYEK.md` | Kerangka README yang menyeluruh |
| `templates/MODEL_CARD.md` | Kontrak model dan keterbatasannya |
| `templates/DATASET_CARD.md` | Provenance dan batasan dataset |
| `templates/REGISTRI_DATASET.csv` | Inventaris data yang benar-benar ada |
| `templates/REGISTRI_MODEL.csv` | Inventaris checkpoint, lokasi dan SHA-256 |
| `templates/RECOVERY_RUNBOOK.md` | Instruksi mengembalikan proyek dari nol |
| `panduan/PENYIMPANAN_DAN_PEMULIHAN.md` | Kebijakan Git, dataset, model dan backup |
| `checklists/QUALITY_GATE.md` | Gerbang kualitas sebelum publikasi |
| `AGENTS.md` | Aturan bagi agent yang mengelola standar ini |

## Cara menggunakan untuk sebuah proyek

```text
Proyek A (repo terpisah)
  README.md
  docs/...
  notebooks/...
  models/... atau tautan release yang diverifikasi
  reports/...

Repo documentation (ini)
  Standar, prompt, template, checklist, dan panduan
```

Dokumentasi di repo proyek **harus menyebut nama/path model dan dataset milik proyek itu**, bukan menggunakan contoh generik.

## Aturan perubahan

Perbarui template bila ada pembelajaran lintas proyek. Perbarui dokumentasi aktual di repositori proyek terkait, bukan mengganti seluruh README lama tanpa audit. Simpan perubahan melalui Git diff dan riwayat commit.

## Lisensi

MIT untuk template/panduan asli di sini. **Tidak mencakup dataset, checkpoint, gambar, dokumentasi pihak ketiga, atau proyek lain secara otomatis.** Lihat [LICENSE](LICENSE).
