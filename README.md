# Manga Text Selector (Android / XML + Kotlin)

Starter project untuk memilih blok teks manga memakai OCR on-device. UI dibangun dengan XML; alur aplikasi ditulis dengan Kotlin.

## Fitur yang sudah ada
- Memilih satu gambar menggunakan Android Photo Picker.
- Menjalankan OCR ML Kit untuk model Latin dan Jepang di perangkat.
- Menampilkan kotak hijau pada blok teks yang terdeteksi.
- Menyentuh kotak/teks untuk memilih blok.
- Mengganti bentuk bingkai seleksi ke persegi, oval, atau lingkaran.
- Menyalin hasil OCR dari blok yang dipilih.

## Cara membuka
1. Ekstrak ZIP ini.
2. Buka folder `MangaTextSelector` dari Android Studio.
3. Gunakan JDK 17 dan izinkan Gradle melakukan Sync.
4. Jalankan pada emulator/perangkat Android API 23 atau lebih baru.

## Struktur penting
- `app/src/main/res/layout/activity_main.xml` — UI XML.
- `app/src/main/java/com/example/mangaselector/MainActivity.kt` — pemilih gambar, OCR, penggabungan hasil, salin teks.
- `app/src/main/java/com/example/mangaselector/SelectionOverlayView.kt` — gambar kotak OCR, hit-test sentuhan, bentuk seleksi.
- `app/src/main/AndroidManifest.xml` — konfigurasi aplikasi.
- `app/build.gradle.kts` — dependensi AndroidX dan ML Kit.

## Batasan prototipe
OCR menghasilkan perkiraan bounding box blok teks, bukan jaminan batas glyph yang sempurna. Font dekoratif, teks vertikal, balon yang bertumpuk, efek suara, resolusi rendah, dan kontras buruk dapat menurunkan akurasi. Bingkai oval/lingkaran mengubah bentuk visual seleksi, jadi sebagian area kosong di sekitar teks bisa tercakup. Prototipe ini belum menghapus teks dari gambar, belum menyunting/mengetik ulang teks pada balon, belum mengekspor hasil gambar, dan belum menjadi ekstensi yang tertanam di aplikasi lain. Fitur-fitur itu memerlukan modul terpisah.

Untuk kualitas editor produksi, langkah lanjutan yang disarankan ialah menambahkan pegangan resize manual, deteksi kontur balon (computer vision), alat inpainting untuk menghapus teks asli, dan ekspor gambar berlapis.
