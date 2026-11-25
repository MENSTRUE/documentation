# Recovery Runbook — [Nama Proyek]

## Skenario
- Laptop berganti/rusak
- File model terhapus
- Dataset privat tidak tersedia
- Dependency versi lama gagal dipasang

## Inventaris minimum
- Repo + commit SHA:
- Arsip / backup kedua dan lokasi:
- Model checkpoint + checksum:
- Dataset + checksum + lisensi:
- Dependency versi:
- Secrets harus dibuat ulang di tempat aman (jangan salin ke repo):

## Jalur A: Jalankan tanpa melatih ulang
1. Clone repository versi yang diketahui.
2. Dapatkan checkpoint dari URL/backup yang terverifikasi (jangan tautan fiktif).
3. Verifikasi checksum.
4. Instal environment sesuai versi runtime.
5. Jalankan smoke test/inference dan API/GUI bila ada.
6. Catat hasil dan error.

## Jalur B: Training ulang bila model tidak tersedia
1. Periksa izin akses dataset.
2. Cocokkan versi, hash, jumlah file dan split.
3. Jalankan notebook/script dengan seed dan versi dependency tercatat.
4. Bandingkan metrik sesuai toleransi dan batasan nondeterminisme.
5. Arsipkan checkpoint dan update model registry.

## Setelah pulih
Perbarui file inventory, lokasi backup, dan prosedur yang ternyata tidak bekerja.
