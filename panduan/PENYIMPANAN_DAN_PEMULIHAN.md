# Kebijakan Penyimpanan, Model, Dataset, dan Backup

## Pisahkan empat jenis artefak

1. **Kode dan dokumentasi**: GitHub repository per proyek.
2. **Data mentah**: sumber asli/Kaggle bila diizinkan, disk kerja, backup kedua yang berbeda perangkat/lokasi.
3. **Model terlatih**: `models/` bila ukuran kecil dan lisensi memungkinkan; untuk ukuran besar gunakan GitHub Release, Git LFS, Hugging Face atau storage privat.
4. **Bukti penelitian**: notebook, manifest, metrik, kurva, laporan audit dan versi dependency.

## Model boleh diunggah
Tidak ada larangan universal. Hindari file besar dalam sejarah Git biasa. Pilih jalur publik hanya jika lisensi/dataset/private information memungkinkan; untuk yang proprietary, simpan secara privat dengan akses terkendali.

## Aturan keputusan cepat
| Kondisi | Pilihan |
|---|---|
| File kecil, lisensi aman, ingin clone lalu langsung jalan | Commit checkpoint di repo (kalau perlu Git LFS) |
| Berkas besar, ingin versi unduhan resmi | GitHub Releases / Hugging Face Hub |
| Model rahasia / data sensitif | Private storage atau registry yang punya kontrol akses |
| Dataset pihak ketiga tidak boleh redistribusi | Simpan hanya URL sumber resmi + instruksi akses + hash lokal |

## Identitas artefak
Selalu catat nama file, ukuran, SHA-256, version, tanggal, model/dataset source, preprocessing, dan hasil tes baca/load. **Tanpa informasi ini, model ada tetapi mungkin tidak bisa dipakai.**

## Strategi backup
Gunakan minimal satu salinan selain disk kerja, idealnya perangkat atau layanan terpisah. Sinkronisasi otomatis bukan pengganti versioned backup. Uji pemulihan secara berkala.

## Contoh cek hash (PowerShell)

```powershell
Get-FileHash -LiteralPath '.\models\model.pt' -Algorithm SHA256
```

## Recovery order
1. Apakah file masih ada di lokal? 2. Apakah ada backup kedua? 3. Apakah Kaggle output/release menyediakan artefak? 4. Unduh ulang dari sumber resmi bila perlu. 5. Training ulang adalah opsi terakhir.

## Catatan keamanan
Jangan commit API key, kredensial, PII, dataset private atau data yang lisensinya melarang distribusi. Checkpoint `.pkl` / `.joblib` hanya boleh di-load dari sumber tepercaya karena deserialisasi bisa mengeksekusi kode.
