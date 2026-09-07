---
category: general
date: 2026-09-07
description: Buat barcode planet PNG dalam C# dengan cepat. Pelajari cara menghasilkan
  gambar barcode planet menggunakan Aspose.BarCode dengan bar terisi dan kosong.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: id
lastmod: 2026-09-07
og_description: Buat barcode planet PNG di C# dengan cepat. Ikuti panduan ini untuk
  mempelajari cara menghasilkan gambar barcode planet dengan batang yang terisi dan
  kosong menggunakan Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: Buat barcode planet PNG di C# – tutorial pemrograman lengkap
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara membuat barcode planet PNG dengan C# – panduan langkah demi langkah
url: /id/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat planet barcode PNG dengan C# – panduan langkah demi langkah

Jika Anda perlu **membuat file planet barcode PNG** dalam C#, panduan ini menunjukkan langkah‑langkah tepatnya. Baik Anda sedang membangun integrasi layanan pos atau dasbor logistik, Anda akan belajar **cara menghasilkan gambar planet barcode** dengan batang yang terisi dan kosong menggunakan pustaka Aspose.BarCode.

Dalam tutorial ini Anda akan:

* Menyiapkan folder output untuk gambar Anda.  
* Mengonfigurasi `BarcodeGenerator` untuk simbol Planet.  
* Menghasilkan PNG dengan gaya batang‑terisi default.  
* Menghasilkan PNG dengan batang kosong untuk kontras visual.  

Tidak ada layanan eksternal yang diperlukan—semua berjalan secara lokal pada .NET 6 atau yang lebih baru.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

| Persyaratan | Mengapa penting |
|-------------|-----------------|
| .NET 6 SDK (atau lebih baru) | Menyediakan runtime untuk aplikasi konsol C#. |
| Visual Studio 2022 atau VS Code | IDE apa pun yang dapat mengompilasi proyek C#. |
| Aspose.BarCode untuk .NET (paket NuGet `Aspose.BarCode`) | Menyediakan kelas `BarcodeGenerator` yang digunakan untuk merender Planet barcode. |
| Izin menulis ke folder di disk | File PNG akan disimpan ke lokasi ini. |

Instal paket NuGet dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Buat proyek konsol baru

Buka terminal dan jalankan:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

Ini membuat aplikasi konsol C# minimal dengan nama **PlanetBarcodeDemo**.

## Langkah 2: Tentukan direktori output

Potongan kode pertama menentukan di mana file PNG yang dihasilkan akan disimpan. Menggunakan path absolut atau relatif keduanya dapat; pastikan folder tersebut ada atau biarkan program membuatnya.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*Mengapa langkah ini?* Memisahkan output dari kode sumber membuat proyek Anda rapi dan menghindari penimpaan tidak sengaja.

## Langkah 3: Hasilkan Planet barcode dengan batang terisi

Planet barcode terdiri dari lingkaran konsentris (terisi secara default). Kami mengonfigurasi dimensi X (lebar piksel setiap batang) lalu menyimpan gambar sebagai PNG.

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**Penjelasan**

* `EncodeTypes.Planet` memberi tahu Aspose untuk menggunakan simbol Planet, yang umum untuk layanan pos.  
* `XDimension.Pixels = 4` menghasilkan ukuran yang jelas dan dapat dicetak tanpa skala manual.  
* Metode `Save` menulis file PNG; Anda juga dapat memilih JPEG atau BMP dengan mengubah `BarCodeImageFormat`.

## Langkah 4: Hasilkan Planet barcode dengan batang kosong

Kadang‑kadang visual dengan batang kosong (transparan) diperlukan—misalnya, ketika barcode ditempatkan di atas latar belakang berwarna. Menetapkan `FilledBars` ke `false` menghasilkan gaya ini.

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**Penjelasan**

* `FilledBars = false` menonaktifkan lingkaran padat, menyisakan hanya kontur.  
* Semua pengaturan lain (dimensi X, string data) tetap identik, memastikan kedua gambar mewakili data yang sama.

## Langkah 5: Jalankan program dan verifikasi output

Kompilasi dan eksekusi:

```bash
dotnet run
```

Anda akan melihat pesan konsol yang mengonfirmasi file yang disimpan, dan folder `Barcodes` akan berisi:

* `PostalPlanetFilledBars.png` – Planet barcode klasik dengan batang terisi.  
* `PostalPlanetEmptyBars.png` – Data yang sama ditampilkan dengan batang kosong.

Buka PNG di penampil gambar apa pun. Kedua gambar mengkode string numerik **123456** dan dapat dipindai oleh pembaca barcode pos standar.

## Pertanyaan umum dan penanganan kasus tepi

### Bagaimana jika saya membutuhkan format data yang berbeda?

Planet barcode menerima string numerik hingga 12 digit. Jika Anda memberikan nilai non‑numerik, Aspose akan melempar `ArgumentException`. Validasi input sebelum membuat generator:

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### Bagaimana cara mengubah ukuran gambar tanpa mengubah ketebalan batang?

Gunakan properti `Resolution` atau skala bitmap yang dihasilkan setelah disimpan:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### Bisakah saya menghasilkan format gambar lain?

Ya. Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg`, `Bmp`, atau `Gif`. API mendukung semua format raster umum.

### Bagaimana dengan kustomisasi warna?

Setel `BarColor` dan `BackColor` pada parameter `Barcode`:

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

Opsi ini bekerja untuk versi batang terisi maupun batang kosong.

## Tips profesional untuk penggunaan produksi

* **Cache generator** ketika Anda perlu merender banyak barcode dengan pengaturan yang sama—menginisialisasi objek berulang kali menambah beban.  
* **Dispose** objek `BarcodeGenerator` jika Anda membuat banyak dalam loop (mereka mengimplementasikan `IDisposable`).  
* **Validasi folder output** di awal untuk menghindari pengecualian runtime pada direktori yang dilindungi penulisan.  

## Kesimpulan

Anda kini tahu cara **membuat file planet barcode PNG** dalam C# dan memahami **cara menghasilkan gambar planet barcode** dengan gaya batang terisi dan kosong. Contoh lengkap yang dapat dijalankan menunjukkan cara menyiapkan direktori output, mengonfigurasi `BarcodeGenerator`, dan menyimpan hasilnya sebagai file PNG.

Selanjutnya, Anda dapat mengeksplorasi:

* Menambahkan **teks yang dapat dibaca manusia** di bawah barcode (`planetFilled.Parameters.Caption.Visible = true`).  
* Mengintegrasikan PNG yang dihasilkan ke dalam **faktur PDF** menggunakan Aspose.PDF.  
* Beralih ke simbol postal lainnya seperti **IMB** atau **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`).  

Silakan bereksperimen dengan ketebalan batang, warna, dan resolusi gambar untuk menyesuaikan kebutuhan aplikasi spesifik Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Buat Gambar Planet Barcode di C# – Cara Menghasilkan Barcode Pos](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Buat Planet Barcode di C# – Panduan Lengkap Langkah demi Langkah](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Hasilkan Barcode PNG dengan Aspose.BarCode untuk .NET: Baris Terisi Satu Dimensi](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}