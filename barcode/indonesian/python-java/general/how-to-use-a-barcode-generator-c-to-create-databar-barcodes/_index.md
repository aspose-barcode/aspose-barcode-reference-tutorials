---
category: general
date: 2026-09-07
description: Tutorial generator barcode C# yang menunjukkan cara menghasilkan file
  PNG barcode dan membuat barcode DataBar dengan baris serta kolom yang dapat disesuaikan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: id
lastmod: 2026-09-07
og_description: 'tutorial generator barcode C#: pelajari cara menghasilkan file PNG
  barcode dan membuat barcode DataBar dengan baris serta kolom khusus dalam hitungan
  menit'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: generator barcode C# – buat barcode DataBar dan gambar PNG
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: Cara menggunakan generator barcode C# untuk membuat barcode DataBar
url: /id/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menggunakan Barcode Generator C# untuk Membuat Barcode DataBar

Jika Anda memerlukan **barcode generator C#** untuk membuat barcode berkualitas tinggi, panduan ini menunjukkan cara **menghasilkan file PNG barcode** dan **membuat barcode DataBar** dengan baris dan kolom yang dapat disesuaikan. Baik Anda membangun sistem inventaris ritel maupun platform tiket, langkah‑langkah di bawah ini memungkinkan Anda menghasilkan barcode DataBar Expanded Stacked dalam satu contoh yang berdiri sendiri.

Dalam tutorial ini Anda akan belajar:

* Cara menginstansiasi `BarcodeGenerator` untuk simbol DataBar Expanded Stacked.  
* Cara menyesuaikan pengaturan kolom dan baris agar memenuhi spesifikasi ISO / GS1.  
* Cara menyimpan output sebagai gambar PNG yang dapat disematkan di halaman web atau dicetak pada label.  

Tidak diperlukan layanan eksternal—hanya pustaka Aspose.BarCode untuk .NET (atau pustaka kompatibel lain yang mengikuti API yang sama). Kode ini berjalan pada .NET 6+ dan berfungsi di Visual Studio, Rider, atau IDE apa pun yang mendukung C#.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6 SDK atau yang lebih baru terpasang.  
* Referensi ke paket NuGet `Aspose.BarCode` (atau pustaka setara yang menyediakan `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat`).  
* Familiaritas dasar dengan sintaks C# dan struktur proyek.  

Anda dapat menambahkan paket melalui baris perintah:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Inisialisasi barcode generator C# untuk DataBar Expanded Stacked

Langkah pertama adalah membuat instance `BarcodeGenerator` yang menargetkan simbol **DataBar Expanded Stacked**. Objek ini menyimpan semua parameter rendering, termasuk teks yang akan dienkode.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**Mengapa ini penting:** Nilai enum `EncodeTypes.DatabarExpandedStacked` memberi tahu pustaka standar barcode mana yang harus diterapkan. Menggunakan enum yang tepat memastikan gambar yang dihasilkan mematuhi spesifikasi GS1 DataBar.

## Langkah 2: Konfigurasi jumlah kolom (baris default digunakan)

DataBar Expanded Stacked dapat dibagi menjadi beberapa kolom. Menyesuaikan jumlah kolom mengubah kepadatan visual dan dapat membantu menampung string data yang lebih panjang dalam ruang terbatas.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**Tips pro:** Jumlah kolom default adalah 1. Menetapkannya menjadi 4 menghasilkan empat kolom bertumpuk, yang ideal untuk string numerik yang lebih panjang sambil menjaga tinggi barcode tetap dapat dikelola.

## Langkah 3: Hasilkan PNG barcode dengan pengaturan kolom yang diterapkan

Sekarang simpan barcode sebagai gambar PNG. PNG mempertahankan tepi tajam yang dibutuhkan pemindai dan bekerja baik di web maupun media cetak.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

File `DatabarCols4.png` berisi **barcode PNG** yang dapat Anda sematkan langsung di HTML:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## Langkah 4: Buat instance generator terpisah untuk konfigurasi baris

Jika Anda perlu mengontrol jumlah baris alih‑alih kolom, buat instance `BarcodeGenerator` baru. Menggunakan kembali instance yang sama setelah mengubah dimensi dapat menyebabkan artefak tata letak yang tidak terduga, sehingga objek baru adalah pendekatan paling aman.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Langkah 5: Atur jumlah baris (kolom default digunakan)

Baris memengaruhi penumpukan vertikal modul barcode. Menambah baris dapat membuat barcode lebih tinggi, yang mungkin diperlukan untuk ukuran label tertentu.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**Mengapa baris vs. kolom:** Kolom membagi barcode secara horizontal, sementara baris memperpanjangnya secara vertikal. Pilih orientasi yang paling cocok dengan tata letak label Anda.

## Langkah 6: Hasilkan PNG barcode dengan pengaturan baris yang diterapkan

Akhirnya, simpan barcode yang telah disesuaikan barisnya sebagai file PNG.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Sekarang Anda memiliki dua file PNG yang berbeda:

* `DatabarCols4.png` – 4 kolom, 1 baris.  
* `DatabarRows3.png` – 1 kolom, 3 baris.

Kedua gambar siap langsung digunakan dalam aplikasi, laporan, atau label cetak.

## Cara menghasilkan file PNG barcode di C# dengan dimensi khusus

Pola yang ditunjukkan di atas dapat digunakan kembali untuk varian DataBar apa pun atau simbol lain yang didukung pustaka. Berikut template ringkas yang dapat Anda salin‑tempel ke dalam kelas utilitas:

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Panggil metode tersebut seperti ini:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**Kasus tepi yang perlu dipertimbangkan**

* **Panjang data** – DataBar Expanded Stacked dapat mengodekan hingga 74 karakter numerik. Melebihi batas ini akan menimbulkan pengecualian. Validasi panjang input sebelum memanggil generator.  
* **Dimensi tidak valid** – Pustaka membatasi kolom menjadi 1‑4 dan baris menjadi 1‑3 untuk simbol ini. Menyediakan nilai di luar rentang tersebut akan diabaikan atau menyebabkan error.  
* **DPI gambar** – Jika Anda memerlukan resolusi lebih tinggi untuk pencetakan, atur `generator.Parameters.ImageResolution` sebelum menyimpan.

## Output yang diharapkan

Saat Anda membuka `DatabarCols4.png` atau `DatabarRows3.png`, Anda akan melihat barcode DataBar yang jelas dan kontras tinggi. Memindai gambar dengan pemindai kompatibel GS1 mengembalikan teks asli `"Databar Expanded Stacked long"`.

![Contoh barcode DataBar Expanded Stacked yang disimpan sebagai PNG menggunakan barcode generator C#](image.png)

*Alt text: Contoh barcode DataBar Expanded Stacked yang disimpan sebagai PNG menggunakan barcode generator C#*

## Kesimpulan

Tutorial ini menunjukkan bagaimana **barcode generator C#** dapat digunakan untuk **membuat barcode DataBar** dan **menghasilkan file PNG barcode** dengan pengaturan baris dan kolom yang dapat disesuaikan. Dengan mengikuti enam langkah—menginisialisasi generator, mengonfigurasi kolom atau baris, dan menyimpan sebagai PNG—Anda memperoleh gambar siap produksi yang cocok untuk sistem inventaris, tiket, atau skenario apa pun yang memerlukan rendering barcode yang andal.

Selanjutnya, Anda dapat menjelajahi:

* Menambahkan warna atau gambar latar belakang ke PNG (masih kompatibel dengan sebagian besar pemindai).  
* Menggunakan simbol lain seperti QR, Code 128, atau PDF417 melalui API `BarcodeGenerator` yang sama.  
* Menyematkan PNG yang dihasilkan langsung ke tampilan ASP.NET Core MVC atau komponen Blazor.

Silakan bereksperimen dengan string data, dimensi, dan format gambar yang berbeda (misalnya JPEG, BMP). Pola yang sama berlaku, menjadikan **barcode generator C#** alat serbaguna dalam kotak peralatan setiap pengembang .NET. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Generate barcode C# – Create DataBar barcode](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}