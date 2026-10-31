# AISZ GAME SPACE

Project Android native berbasis Kotlin + Jetpack Compose.

## Fitur yang tersedia
- Dashboard dark navy dengan panel rounded dan navigasi Home / Games / Tools / Settings.
- Game launcher: menampilkan aplikasi yang memiliki launcher activity, pencarian, favorit lokal, dan tombol buka aplikasi.
- Battery temperature: membaca temperatur baterai dari broadcast Android (data aktual saat tersedia).
- FPS: ditandai N/A karena aplikasi biasa tidak memperoleh FPS game lain secara umum tanpa API/OEM khusus.
- Touch Tester: koordinat sentuhan dan multi-touch dasar.
- Floating edge panel: overlay resmi Android menggunakan `SYSTEM_ALERT_WINDOW`, dapat dibuka/tutup dan dipindahkan secara vertikal.
- Pengaturan animasi dan floating panel.

## Build APK
1. Buka folder project ini di Android Studio versi yang mendukung AGP 8.7.3.
2. Gunakan JDK 17.
3. Tunggu Gradle Sync.
4. Pilih Build > Build APK(s).
5. APK debug berada di `app/build/outputs/apk/debug/app-debug.apk`.

## Catatan perangkat / izin
- Minimum Android 7.0 (API 24).
- Floating panel meminta izin "Display over other apps". Pengguna harus mengaktifkannya sendiri di Settings Android.
- Beberapa versi HyperOS dapat membatasi overlay atau background service. Jika panel tidak muncul, izinkan "Display pop-up windows" / "Display over other apps" untuk AISZ GAME SPACE dan nonaktifkan pembatasan autostart bila diperlukan.
- Game launcher hanya menampilkan aplikasi yang menyediakan launcher activity dan terlihat oleh Android package visibility.
- FPS untuk game lain ditampilkan N/A jika tidak ada sumber resmi yang dapat diakses.
- Temperatur baterai berasal dari `ACTION_BATTERY_CHANGED`; nilai bisa tidak tersedia pada perangkat tertentu.
- Screenshot lintas aplikasi tidak dibuat sebagai tombol palsu. Android membatasi tangkapan layar layar lain melalui MediaProjection dan persetujuan pengguna.
- Kecerahan sistem dan volume memakai kontrol sistem resmi; aplikasi menyediakan shortcut pengaturan, bukan mengubah pengaturan sensitif secara diam-diam.

## Struktur
- `MainActivity.kt`: UI utama, dashboard, games, tools, settings, touch tester.
- `FloatingPanelService.kt`: edge overlay.
- `GameRepository.kt`: launcher apps.
- `Theme.kt`: palet visual AISZ.
