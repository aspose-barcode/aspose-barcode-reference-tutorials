---
category: general
date: 2026-07-27
description: Buat gambar barcode omnidireksional menggunakan Aspose.BarCode. Pelajari
  cara menghasilkan barcode dengan Aspose, mengatur rasio aspek, dan menyimpan file
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: id
lastmod: 2026-07-27
og_description: Buat gambar barcode omnidirectional menggunakan Aspose. Ikuti panduan
  ini untuk menghasilkan barcode dengan Aspose, sesuaikan rasio aspek, dan ekspor
  PNG.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Buat Gambar Barcode Omnidirectional dengan Aspose – Langkah demi Langkah
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Buat Gambar Barcode Omnidireksional dengan Aspose – Panduan Lengkap
url: /id/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Gambar Barcode Omnidirectional dengan Aspose – Panduan Lengkap

Pernahkah Anda perlu **membuat gambar barcode omnidirectional** tetapi tidak yakin pustaka mana yang harus dipilih? Anda tidak sendirian. Dalam banyak proyek logistik dan ritel, format DataBar Stacked Omnidirectional adalah rahasia untuk pengkodean yang kompak dan ber‑densitas tinggi.  

Kabar baiknya? Dengan **Aspose.BarCode** Anda dapat menghasilkan barcode tersebut dalam beberapa baris kode, menyesuaikan rasio aspeknya, dan langsung menyimpan PNG ke disk. Di bawah ini Anda akan melihat secara tepat cara **generate barcode with Aspose**, mengapa setiap pengaturan penting, dan hal‑hal yang perlu diwaspadai saat mengubah rasio aspek.

---

## Apa yang Dibahas dalam Tutorial Ini

Kami akan melangkah melalui seluruh siklus hidup:

1. Menyiapkan folder output.  
2. Membuat instance generator DataBar Stacked Omnidirectional.  
3. Mengonfigurasi dimensi piksel dan rasio aspek.  
4. Menyimpan barcode sebagai file PNG.  
5. Memperluas contoh untuk format lain dan kasus tepi.  

Pada akhir tutorial Anda akan memiliki aplikasi konsol C# siap‑jalankan yang menghasilkan dua gambar barcode yang berbeda. Tanpa alat eksternal, hanya kode Aspose murni.

**Prasyarat**

- .NET 6.0 SDK atau yang lebih baru (kode ini juga berfungsi pada .NET Framework 4.7.2).  
- Paket NuGet Aspose.BarCode untuk .NET (`Install-Package Aspose.BarCode`).  
- Sebuah folder di disk tempat gambar dapat ditulis.  

Jika Anda sudah memiliki semuanya, mari kita mulai.

---

## Langkah 1: Siapkan Folder Output

Hal pertama—beritahu program di mana menyimpan file PNG. Menuliskan path secara hard‑code cocok untuk demo, tetapi di produksi Anda biasanya membacanya dari konfigurasi.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*Mengapa ini penting:* `Directory.CreateDirectory` bersifat idempotent; tidak akan melempar pengecualian jika folder sudah ada, sehingga Anda tidak perlu blok try‑catch.

---

## Langkah 2: Buat Generator DataBar Stacked Omnidirectional

Sekarang kami memulai generator dengan tipe enkode spesifik dan data contoh. String `"(01)12345678901231"` mengikuti sintaks GS1 Application Identifier untuk GTIN 14‑digit.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*Penjelasan:* `EncodeTypes.DatabarStackedOmniDirectional` memberi tahu Aspose untuk menggunakan varian omnidirectional, yang dapat dibaca dari arah mana pun—sempurna untuk label kecil yang mungkin diputar.

---

## Langkah 3: Atur Parameter Barcode Umum

Sebelum merender apa pun, kami mendefinisikan ukuran elemen terkecil (X‑Dimension). Nilai **2 piksel** menghasilkan gambar tajam tanpa membuat ukuran file membengkak.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Tip:* Jika Anda memerlukan resolusi lebih tinggi untuk pencetakan, naikkan nilai ini menjadi 3 atau 4. Ingat bahwa X‑Dimension yang lebih besar meningkatkan lebar dan tinggi secara proporsional.

---

## Langkah 4: Hasilkan dan Simpan dengan Aspect Ratio 15

Keluarga DataBar memungkinkan Anda menyesuaikan **rasio aspek**, yang mengontrol hubungan tinggi‑ke‑lebar. Rasio aspek **15** adalah nilai default umum untuk barcode omnidirectional.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*Apa yang akan Anda lihat:* Barcode yang relatif tinggi namun tetap muat dengan nyaman pada label 2 × 1 cm. Format PNG mempertahankan kualitas lossless, ideal untuk pemrosesan atau pencetakan lebih lanjut.

---

## Langkah 5: Ubah Aspect Ratio menjadi 30 dan Simpan Lagi

Ingin barcode yang lebih pendek? Cukup ubah properti `AspectRatio` dan panggil `Save` lagi. Tidak perlu membuat generator baru.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*Mengapa menggunakan kembali generator yang sama?* Objek Aspose ringan; mengubah properti dan menyimpan ulang lebih cepat daripada membuat instance baru, dan memastikan pengaturan enkoding yang sama (misalnya X‑Dimension) tetap konsisten.

---

## Contoh Lengkap yang Berfungsi

Menggabungkan semuanya, berikut program lengkap yang dapat Anda salin‑tempel ke proyek konsol baru.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**Output yang Diharapkan**

Menjalankan program membuat sub‑folder `Barcodes` yang berisi:

- `DatabarAspectRatio15.png` – lebih tinggi, tampilan klasik.  
- `DatabarAspectRatio30.png` – lebih datar, lebih cocok untuk label lebar.  

Kedua gambar menampilkan data GTIN yang sama; hanya proporsi visualnya yang berbeda.

---

## Memperluas Contoh (Kasus Tepi & Variasi)

### 1. Format Gambar Berbeda

Aspose mendukung BMP, JPEG, TIFF, dan SVG selain PNG. Ganti nilai enum:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG berbasis vektor, artinya Anda dapat memperbesarnya tanpa kehilangan ketajaman—berguna untuk aplikasi web responsif.

### 2. Menyesuaikan Warna

Anda mungkin memerlukan barcode putih di latar belakang gelap. Atur `ForeColor` dan `BackColor`:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. Menangani Aspect Ratio yang Tidak Valid

Aspose memvalidasi rentang (biasanya 5‑50). Jika Anda memberikan nilai di luar rentang, `ArgumentException` akan dilempar. Bungkus pemanggilan `Save` dalam try‑catch untuk memberikan pesan yang ramah:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. Generasi Batch

Ketika Anda memiliki daftar GTIN, lakukan loop, perbarui `CodeText`, dan simpan tiap file dengan nama unik. Objek generator dapat dipakai ulang, menjaga penggunaan memori tetap rendah.

---

## Kesalahan Umum & Pro Tips

- **Jangan pernah lupa mengatur `XDimension`** sebelum menyimpan; nilai default (0,33 mm) dapat menghasilkan gambar buram pada tampilan beresolusi rendah.  
- **Rasio aspek adalah tinggi‑ke‑lebar**, bukan sebaliknya. Angka yang lebih besar membuat barcode *lebih pendek* secara vertikal.  
- **Path file:** Gunakan `Path.Combine` untuk menghindari masalah pemisah yang spesifik platform—terutama jika kode Anda berjalan di container Linux.  
- **Lisensi:** Aspose.BarCode bersifat komersial. Dalam mode percobaan, watermark muncul pada gambar. Daftarkan lisensi lebih awal untuk menghindari kejutan di produksi.  

---

## Kesimpulan

Anda kini tahu cara **membuat gambar barcode omnidirectional** menggunakan Aspose, menyesuaikan rasio aspek, dan mengekspor file PNG—semua dalam kurang dari 30 baris C#. Tutorial ini menunjukkan proses langkah‑demi‑langkah, menjelaskan mengapa setiap pengaturan penting, serta mencakup ekstensi seperti format berbeda, warna, dan pemrosesan batch.

Siap untuk tantangan berikutnya? Cobalah menghasilkan QR code, menyematkan barcode ke dalam PDF, atau mengintegrasikan output ke API ASP.NET Core. Prinsip **generate barcode with Aspose** yang sama berlaku untuk semua tipe barcode, sehingga Anda dapat menggunakan kembali apa yang dipelajari hari ini.

Ada pertanyaan atau ingin berbagi modifikasi Anda? Tinggalkan komentar di bawah—selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut membahas topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cara Membuat Barcode Aspose Java - Menyesuaikan Kualitas Gambar](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [Cara Menghasilkan Gambar Barcode di Java dengan Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}