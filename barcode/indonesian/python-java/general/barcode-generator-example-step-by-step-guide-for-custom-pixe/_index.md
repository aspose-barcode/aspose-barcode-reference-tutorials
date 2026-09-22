---
category: general
date: 2026-08-12
description: Contoh generator barcode yang menunjukkan cara menghasilkan barcode dengan
  ukuran piksel yang tepat. Pelajari cara mengatur lebar modul, tinggi bar, dan membuat
  barcode Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to generate barcode
- barcode pixel size
- generate planet barcode
- barcode height setting
language: id
lastmod: 2026-08-12
og_description: Contoh generator barcode menunjukkan cara menghasilkan barcode dengan
  dimensi piksel yang tepat. Ikuti panduan ini untuk mengontrol lebar modul dan tinggi
  bar untuk kode Planet dan RM4SCC.
og_image_alt: Screenshot of a barcode generator example showing a Planet barcode with
  custom pixel size
og_title: contoh generator barcode – sesuaikan ukuran piksel di C#
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  headline: barcode generator example – step‑by‑step guide for custom pixel sizes
  type: TechArticle
- description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  name: barcode generator example – step‑by‑step guide for custom pixel sizes
  steps:
  - name: Install the Aspose.BarCode package
    text: 'Open a terminal in your project folder and run:'
  - name: Add the necessary `using` directives
    text: '```csharp using Aspose.BarCode.Generation; using Aspose.BarCode.BarCodeImageFormat;
      ```'
  - name: – generate a Planet barcode with automatically calculated height
    text: '```csharp // Step 1: Generate a Planet barcode with automatically calculated
      height BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate a Planet barcode with an explicit 100‑pixel height
    text: '```csharp // Step 2: Generate a Planet barcode with an explicit 100‑pixel
      height BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate an RM4SCC barcode with the same explicit height
    text: '```csharp // Step 3: Generate an RM4SCC barcode with the same explicit
      height BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC,
      "123456");'
  - name: What is **barcode pixel size**?
    text: '*Pixel size* refers to the physical number of screen or printer pixels
      that represent a single module (`XDimension`). A larger pixel size yields a
      bigger barcode, which can be easier for low‑resolution scanners but consumes
      more label real‑estate.'
  - name: How does `BarHeight` affect readability?
    text: The `BarHeight` property controls the vertical length of the bars. Standards
      for most 1‑D barcodes (including Planet and RM4SCC) recommend a minimum height
      of 10 mm when printed at 300 dpi, which translates to roughly 118 pixels. Setting
      a height below that can cause read errors, especially on mobil
  - name: When should you let the library calculate height automatically?
    text: If you’re generating barcodes for on‑screen display only, the automatic
      calculation keeps the aspect ratio consistent and reduces the amount of manual
      tweaking needed. For printed labels that must meet strict ISO specifications,
      you should **explicitly set the bar height**.
  - name: Pro tip on performance
    text: When generating thousands of barcodes in a batch job, reuse a single `BarcodeGenerator`
      instance and only change the `CodeText` and size parameters between saves. This
      avoids repeated allocation of internal rendering objects and can cut execution
      time by up to 30 %.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Contoh generator barcode – panduan langkah demi langkah untuk ukuran piksel
  khusus
url: /id/python-java/general/barcode-generator-example-step-by-step-guide-for-custom-pixe/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# contoh generator barcode – panduan langkah‑demi‑langkah untuk ukuran piksel khusus

Jika Anda membutuhkan **contoh generator barcode** yang memungkinkan Anda mengontrol setiap piksel, panduan ini menunjukkan secara tepat cara melakukannya. Anda akan belajar mengatur lebar modul, menentukan tinggi bar yang tetap, dan menghasilkan barcode Planet serta RM4SCC dengan dimensi yang dapat diprediksi.

Sebagian besar pengembang mengalami kesulitan dengan gambar “cara menghasilkan barcode” yang terlihat sama di setiap layar atau printer. Potongan kode di bawah ini menyelesaikan masalah tersebut dengan mengekspos parameter tingkat piksel dari pustaka Aspose.BarCode untuk .NET, sehingga Anda dapat menghasilkan output yang konsisten tanpa tebak‑tebakan.

## Apa yang akan Anda pelajari

* Cara menginstal paket NuGet yang diperlukan.
* Cara menghasilkan barcode Planet dengan tinggi yang dihitung secara otomatis.
* Cara menghasilkan barcode Planet dengan tinggi 100 piksel yang eksplisit.
* Cara menghasilkan barcode RM4SCC menggunakan tinggi eksplisit yang sama.
* Mengapa **ukuran piksel barcode** penting untuk keandalan pemindaian.
* Tips untuk memecahkan masalah umum saat Anda menghasilkan gambar barcode Planet.

Anda hanya memerlukan .NET 6 atau yang lebih baru, lingkungan pengembangan C# dasar, dan koneksi internet untuk mengunduh paket NuGet.

---

## contoh generator barcode – menyiapkan lingkungan pengembangan

Sebelum menulis kode apa pun, pastikan pustaka Aspose.BarCode tersedia untuk proyek Anda.

### Instal paket Aspose.BarCode

Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Perintah ini menambahkan versi stabil terbaru dari **Aspose.BarCode** ke `csproj` Anda. Setelah proses pemulihan selesai, Anda dapat mulai menggunakan kelas `BarcodeGenerator`.

> **Pro tip:** Target .NET 6 atau .NET 7 untuk mendapatkan manfaat dari peningkatan performa terbaru dan penanganan default UTF‑8.

### Tambahkan direktif `using` yang diperlukan

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;
```

Namespace ini mengekspos kelas `BarcodeGenerator` dan enum `BarCodeImageFormat` yang akan digunakan nanti dalam tutorial.

---

## Cara menghasilkan barcode dengan ukuran piksel khusus

Tiga langkah berikut menggambarkan **contoh generator barcode** secara lengkap. Setiap langkah membangun dari langkah sebelumnya, sehingga Anda dapat menyalin‑tempel seluruh blok ke dalam aplikasi konsol dan menjalankannya tanpa perubahan.

### Langkah 1 – menghasilkan barcode Planet dengan tinggi yang dihitung secara otomatis

```csharp
// Step 1: Generate a Planet barcode with automatically calculated height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set module width (x‑dimension) to 4 pixels
planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG
planetAuto.Save("PlanetAuto.png", BarCodeImageFormat.Png);
```

**Mengapa ini berhasil:**  
*Properti `XDimension` menentukan lebar satu modul barcode (elemen hitam atau putih terkecil). Ketika Anda tidak menyertakan `BarHeight`, pustaka menghitung tinggi yang mempertahankan rasio aspek standar untuk kode Planet.*

**Output yang diharapkan:** File PNG bernama `PlanetAuto.png` yang berisi barcode Planet yang bersih. Tingginya menyesuaikan lebar modul 4 piksel, biasanya sekitar 60 piksel untuk payload enam karakter.

### Langkah 2 – menghasilkan barcode Planet dengan tinggi 100 piksel yang eksplisit

```csharp
// Step 2: Generate a Planet barcode with an explicit 100‑pixel height
BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same module width
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Force the bar height to 100 pixels
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
planetFixed.Save("PlanetHeight100.png", BarCodeImageFormat.Png);
```

**Mengapa Anda mungkin memerlukan ini:**  
Kadang perangkat pemindai mengharapkan tinggi bar minimum untuk deteksi yang dapat diandalkan. Dengan mengatur `BarHeight.Pixels`, Anda menjamin setiap gambar yang dihasilkan memenuhi persyaratan tersebut, terlepas dari panjang data yang dikodekan.

**Output yang diharapkan:** `PlanetHeight100.png` menampilkan data yang sama seperti sebelumnya, tetapi bar memiliki tinggi tepat 100 piksel, memberi Anda kontrol penuh atas ukuran visual.

### Langkah 3 – menghasilkan barcode RM4SCC dengan tinggi eksplisit yang sama

```csharp
// Step 3: Generate an RM4SCC barcode with the same explicit height
BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Use the same module width for consistency
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Apply the 100‑pixel bar height
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
rm4sccFixed.Save("RM4SCCHeight100.png", BarCodeImageFormat.Png);
```

**Mengapa ini penting:**  
`EncodeTypes.RM4SCC` adalah barcode linear bertumpuk yang digunakan dalam logistik. Menyelaraskan tinggi bar-nya dengan barcode Planet menyederhanakan pemrosesan batch ketika kedua simbol muncul pada label yang sama.

**Output yang diharapkan:** `RM4SCCHeight100.png` menampilkan barcode RM4SCC dengan ukuran sempurna, cocok dengan tinggi 100 piksel yang Anda tetapkan untuk kode Planet.

> **Verifikasi hasil:** Buka setiap PNG di penampil gambar dan pastikan bar hitam berukuran tepat 4 piksel lebar dan, jika Anda menentukan, 100 piksel tinggi. Anda juga dapat memasukkan file ke aplikasi pemindai barcode untuk memastikan mereka terdekripsi menjadi “123456”.

---

## Memahami ukuran piksel barcode dan tinggi bar

### Apa itu **ukuran piksel barcode**?

*Ukuran piksel* mengacu pada jumlah fisik piksel layar atau printer yang mewakili satu modul (`XDimension`). Ukuran piksel yang lebih besar menghasilkan barcode yang lebih besar, yang dapat lebih mudah bagi pemindai beresolusi rendah tetapi mengonsumsi lebih banyak ruang pada label.

### Bagaimana `BarHeight` memengaruhi keterbacaan?

Properti `BarHeight` mengontrol panjang vertikal bar. Standar untuk kebanyakan barcode 1‑D (termasuk Planet dan RM4SCC) merekomendasikan tinggi minimum 10 mm saat dicetak pada 300 dpi, yang kira‑kira setara dengan 118 piksel. Menetapkan tinggi di bawah itu dapat menyebabkan kesalahan pembacaan, terutama pada kamera seluler.

### Kapan Anda harus membiarkan pustaka menghitung tinggi secara otomatis?

Jika Anda menghasilkan barcode hanya untuk tampilan di layar, perhitungan otomatis menjaga rasio aspek tetap konsisten dan mengurangi jumlah penyesuaian manual yang diperlukan. Untuk label cetak yang harus memenuhi spesifikasi ISO yang ketat, Anda harus **menetapkan tinggi bar secara eksplisit**.

---

## Kesalahan umum dan praktik terbaik saat Anda menghasilkan barcode Planet

| Kesalahan | Mengapa terjadi | Solusi |
|-----------|----------------|--------|
| Bar muncul terlalu tipis atau terlalu tebal | `XDimension` dibiarkan pada default (1 piksel) pada tampilan resolusi tinggi | Setel `XDimension.Pixels` minimal 3‑4 untuk kejelasan visual |
| Pemindai tidak dapat membaca kode | `BarHeight` terlalu kecil untuk panjang fokus pemindai | Gunakan `BarHeight.Pixels` ≥ 100 untuk kebanyakan pemindai seluler |
| Gambar menjadi buram setelah skala | Menyimpan sebagai JPEG memperkenalkan artefak kompresi | Simpan sebagai PNG (`BarCodeImageFormat.Png`) untuk output tanpa kehilangan |
| Tipe barcode tidak terduga | Nilai enum `EncodeTypes` salah | Periksa kembali bahwa Anda menggunakan `EncodeTypes.Planet` untuk simbol Planet |

### Pro tip tentang kinerja

Saat menghasilkan ribuan barcode dalam pekerjaan batch, gunakan kembali satu instance `BarcodeGenerator` dan hanya ubah `CodeText` serta parameter ukuran di antara penyimpanan. Ini menghindari alokasi berulang objek rendering internal dan dapat mengurangi waktu eksekusi hingga 30 %.

---

## Contoh lengkap yang berfungsi – gabungkan semuanya

Buat proyek konsol baru (`dotnet new console -n BarcodeDemo`) dan ganti isi `Program.cs` dengan yang berikut:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Directory where PNG files will be saved
            string outputDir = Environment.CurrentDirectory;

            // ---------- Planet barcode – automatic height ----------
            var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputDir}/PlanetAuto.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetAuto.png generated.");

            // ---------- Planet barcode – fixed 100‑pixel height ----------
            var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputDir}/PlanetHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetHeight100.png generated.");

            // ---------- RM4SCC barcode – same fixed height ----------
            var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputDir}/RM4SCCHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("RM4SCCHeight100.png generated.");

            Console.WriteLine("All barcodes created successfully.");
        }
    }
}
```

Jalankan program dengan `dotnet run`. Setelah eksekusi Anda akan menemukan tiga file PNG di folder proyek, masing‑masing menggambarkan skenario **contoh generator barcode** yang berbeda.

---

## Langkah selanjutnya dan topik terkait

* **Cara menghasilkan barcode dalam format lain** – jelajahi `EncodeTypes.Code128`, `EncodeTypes.QR`, dan `EncodeTypes.DataMatrix` untuk kebutuhan 2‑D.  
* **Menyematkan barcode dalam PDF** – gabungkan Aspose.BarCode dengan Aspose.PDF untuk menempatkan barcode langsung pada templat faktur.  
* **Ukuran barcode dinamis berdasarkan input pengguna** – hitung  

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara menghasilkan barcode java: Membuat Gambar Barcode yang Tepat](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [Cara Menghasilkan Barcode di Java Membuat dan Menetapkan Ukuran untuk Gambar Utuh](/barcode/english/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [Cara membuat barcode code128 di Java dan mengatur tinggi bar](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}