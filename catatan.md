# DART PACKAGES
## 01 Apa itu Dart Packages?
- Ekosistem Dart menggunakan packages untuk melakukan manajemen software yang bisa disharing, seperti library atau tool
- Saat kita membuat project di Dart, sebenarnya secara tidak langsung kita membuat packages
- Packages bisa dalam bentuk aplikasi atau library (yang digunakan pada aplikasi)
### Keuntungan Menggunakan Packages
- Dengan menggunakan packages, kita akan mengikuti cara management kode Dart
- Dengan packages juga kita bisa melakukan dependency management secara otomatis tanpa harus download libary yang kita butuhkan secara manual

## 02 Membuat Dart Library
- Menggunakan perintah ```dart create --help``` atau ```dart create --h``` untuk menampilkan perintah yang dapat ditambahkan pada saat membuat project
- Untuk membuat dart library, gunakan perintah ```dart create --template=package-simple belajar_dart_package_library```

## 03 Struktur Directory Packages
- Salah satu keuntungan menggunakan packages adalah, struktur directory yang standard untuk project di Dart
- Secara minimal, saat kita membuat dart packages, hanya butuh file pubspec.yaml dan folder lib
- pubspec.yaml digunakan untuk konfigurasi dart packages-nya, sedangkan folder lib untuk menyimpan kode program dart kita
- Namun saat ktia membuat project menggunakan perintah ```dart create```, struktur direktorinya lebih kompleks

### Directory scr
- Salah satu best practice di dart packages adalah, tidak mengekspos kode dart kecuali memang dibutuhkan
- Dan salah satu best packtice yang dilakukan di dart packages, biasanya kode program dart akan ditempatkan di folder src di dalam folder lib
- Semua kode program dart di dalam sec, secara default tidak bisa diekspos ke luar
- Ketika kita butuh mengekspos keluar (artinya bisa diakses oleh project lain), maka biasanya dilakukan secara eksplisit di kode dart di dalam folder lib

## 04 Pubspec
- Saat kita membuat dart packages, hal yang paling utama adalah file pubspec.yaml
- Pubspec.yaml merupakan konfigurasi dari dart packages
- Di dalam pubspec, kita perlu tentukan nama dart packages yang kita buat, termasuk dependency yang kita butuhkan di dart package tersebut

## 05 Membuat Library
- Saat membuat kode dart di dart pakcages, disarankan lakukan di dalam folder src
- Dan ketika melakukan import kode dart dari library, jangan import dari folder src, hal ini karena kode src biasanya digunakan sebagai internal library, dan tidak dijamin akan backward compatible ketika terjadi update library

### Export Libary
- Setelah membuat kode dart di dalam folder src, kita bisa membuat kode dart di lib yang digunakan untuk mengekspos bagian mana yang ingin kita ekspos
- Kita bisa menggunakan kata kunci export jika ingin mengekspos semua kode di dalam file dart, atau gunakan export show jika hanya beberapa saja
- Jangan lupa untuk menambahkan kata kunci library dan diikuti dengan nama library yang kita buat, walaupun tidak wajib, tapi direkomendasikan menggunakannya, karena secara default jika kita tidak menambahkan library, secara otomatis nama library nya adalah string kosong

```dart
    library nama_packages;

    export 'src/nama_file.dart' show namaFungsi, Class;
    export 'src/nama_file_lain.dart';
```

### Import Library
- Setelah membuat library, jika ingin menggunakannya, kita bisa mencobanya di folder example
- Kita bisa melakukan import dengan pola :
```package:nama_library/file.dart```

## 06 Publish Package ke Github
- Setelah membuat library menggunakan dart packages, kita bisa menyimpannya di Git Server, contohnya Github
- Dart Packages terintegrasi dengan baik dengan Git, sehingga kita bisa menambahkan library yang sudah kita buat ke aplikasi melalui Git