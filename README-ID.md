# AnimeToon ID — Prototype Android

Aplikasi demo Android berbahasa Indonesia untuk katalog anime dan webtoon. Gratis, tanpa langganan dan tanpa iklan.

## Fitur yang sudah ada
- Beranda dengan katalog contoh anime dan webtoon
- Pencarian dan filter kategori
- Halaman detail judul
- Favorit disimpan di perangkat
- UI mobile dark theme
- Berjalan offline karena antarmuka disimpan di dalam aplikasi

## Batasan penting
Ini adalah **prototype yang bisa dibangun menjadi APK**, bukan layanan streaming lengkap. Judul di katalog hanya data contoh; tidak ada video episode atau gambar halaman komik berhak cipta yang disertakan. Server, login, sinkronisasi cloud, panel admin, dan pemutar streaming belum dibuat. Jangan mengunggah konten berhak cipta tanpa izin tertulis atau dasar lisensi yang sah.

## Cara membangun APK di komputer
1. Pasang Android Studio versi stabil dan Android SDK Platform 35.
2. Ekstrak ZIP ini.
3. Android Studio → **Open** → pilih folder `AnimeToonID-Android`.
4. Tunggu Gradle Sync selesai. Izinkan Android Studio mengunduh Gradle dan Android Gradle Plugin jika diminta.
5. Untuk menguji, sambungkan HP Android dengan USB debugging aktif atau jalankan emulator, lalu tekan **Run**.
6. Untuk APK debug: **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
7. APK debug biasanya dibuat di `app/build/outputs/apk/debug/app-debug.apk`. Bagikan file itu untuk pengujian; penerima mungkin perlu mengizinkan pemasangan dari sumber tersebut.
8. Untuk rilis publik, buat signed release APK melalui **Build → Generate Signed Bundle / APK** dan uji sebelum dibagikan.

## Persyaratan build
- Android Studio
- JDK 17 (umumnya disertakan dengan Android Studio)
- Android SDK Platform 35
- Koneksi internet saat Gradle pertama kali mengunduh dependensi build

## Menambahkan konten yang sah
Edit `app/src/main/assets/index.html`, pada array `titles`. Untuk rilis, tambahkan data sumber resmi, informasi lisensi, dan halaman pemutar/pembaca yang sesuai izin. Pastikan hak distribusi mencakup wilayah dan cara penggunaan yang direncanakan.


## Build APK dari HP saja (GitHub Actions)
Workflow build otomatis tersedia di `.github/workflows/android-apk.yml`.

1. Di browser HP, buat repository baru di GitHub.
2. Ekstrak ZIP proyek di aplikasi File HP.
3. Unggah semua isi folder proyek ke repository dengan struktur folder yang sama, termasuk folder `.github/workflows`. Pastikan opsi untuk menampilkan file/folder tersembunyi aktif jika diperlukan.
4. Buka tab **Actions** di repository dan aktifkan Actions bila diminta.
5. Pilih workflow **Build AnimeToon ID APK**, lalu tekan **Run workflow** (atau lakukan push ke branch `main`).
6. Tunggu build selesai dengan status hijau.
7. Buka hasil run workflow, cari bagian **Artifacts**, lalu unduh `AnimeToon-ID-debug-APK`. Ekstrak jika hasil unduhan berupa ZIP; di dalamnya ada `app-debug.apk`.

Catatan: GitHub dapat mengubah tampilan menu pada browser HP. APK debug ditujukan untuk pengujian. Untuk distribusi publik yang lebih luas, buat rilis bertanda tangan dengan kunci yang kamu simpan dengan aman.
