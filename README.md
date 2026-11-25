# Tahu Nggak Sih? Kamu — Aplikasi Android

Aplikasi Android resmi channel YouTube **Tahu Nggak Sih? Kamu**
(https://www.youtube.com/@tahunggaksihkamu).

Berisi kumpulan fakta unik dan inspiratif berbahasa Indonesia, lengkap dengan
pencarian, filter kategori, detail fakta, favorit, tombol bagikan, Fakta Hari
Ini, dan tombol untuk membuka channel YouTube.

## Fitur

- 36 fakta unik & inspiratif berbahasa Indonesia
- Kategori: Sains, Hewan, Sejarah, Inspiratif, Teknologi
- Pencarian fakta
- Filter per kategori + filter Favorit
- Halaman detail fakta
- Simpan favorit (SharedPreferences)
- Bagikan fakta ke aplikasi lain
- Fakta Hari Ini (berganti setiap hari)
- Tombol buka channel YouTube @tahunggaksihkamu

## Teknologi

- Kotlin, Gradle 8.5, Android Gradle Plugin 8.5.2
- compileSdk 34, targetSdk 34, minSdk 24, Java 17
- XML layout + RecyclerView + AndroidX AppCompat / Material
- Tanpa Jetpack Compose dan tanpa dependensi eksternal yang berisiko

## Build

### Di GitHub Actions (otomatis)

Setiap push ke branch `main` menjalankan `.github/workflows/build-apk.yml`:
build debug APK, upload sebagai artifact, dan membuat GitHub Release `v1.0`
dengan APK sebagai asset. APK bisa diunduh publik dari halaman Releases.

### Lokal

```bash
# Butuh JDK 17 dan Android SDK (platform Android 34, build-tools 34.0.0)
# Atur ANDROID_HOME / ANDROID_SDK_ROOT ke lokasi SDK.
# Gradle wrapper membutuhkan gradle-wrapper.jar; hasilkan sekali dengan:
gradle wrapper --gradle-version 8.5
chmod +x gradlew
./gradlew assembleDebug
# APK: app/build/outputs/apk/debug/app-debug.apk
```

Atau langsung dengan Gradle yang sudah terinstal:

```bash
gradle assembleDebug
```

Build tanpa daemon Gradle (mis. di VM yang memblokir TCP loopback) —
lihat `BUILD_MANUAL.md`.

## Struktur

```
app/src/main/java/com/tahunggaksihkamu/app/
  MainActivity.kt      # daftar fakta, cari, filter, Fakta Hari Ini
  FactDetailActivity.kt# detail fakta, favorit, bagikan
  FactAdapter.kt       # RecyclerView adapter
  Fact.kt              # model + kategori
  FactRepository.kt    # 36 fakta + Fakta Hari Ini
```

## Lisensi

Konten fakta untuk channel Tahu Nggak Sih? Kamu.
