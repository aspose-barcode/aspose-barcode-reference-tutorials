---
category: general
date: 2026-08-22
description: Buat kode batang FCC 11 dalam C# menggunakan Aspose.BarCode. Pelajari
  kode langkah demi langkah, atur dimensi, dan hasilkan gambar PNG untuk Australia Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: id
lastmod: 2026-08-22
og_description: Buat kode batang FCC 11 di C# dengan Aspose.BarCode. Ikuti tutorial
  singkat ini untuk menghasilkan kode batang PNG untuk Australia Post, termasuk varian
  FCC 59 dan FCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Buat kode batang FCC 11 di C# – panduan lengkap Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Cara membuat kode batang FCC 11 di C# dengan Aspose.BarCode
url: /id/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode FCC 11 di C# dengan Aspose.BarCode

Jika Anda perlu **membuat barcode FCC 11** dalam aplikasi .NET, panduan ini menunjukkan kode tepat yang diperlukan. Anda akan melihat cara mengonfigurasi dimensi barcode, memilih tabel enkoding yang tepat, dan menyimpan hasilnya sebagai file PNG.

Membuat barcode Australia Post adalah kebutuhan umum untuk logistik, sistem pengiriman surat, dan pelacakan inventaris. Tutorial ini mencakup format FCC 11 dan juga mendemonstrasikan cara menghasilkan barcode FCC 59 dan FCC 62 dengan tabel enkoding yang berbeda, sehingga Anda dapat menggunakan pola yang sama untuk layanan pos lainnya.

## Apa yang Anda perlukan

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Visual Studio 2022 (atau IDE kompatibel C# apa saja)  
* Lisensi yang valid untuk **Aspose.BarCode for .NET** – edisi komunitas dapat digunakan untuk evaluasi  
* Izin menulis ke folder tempat file PNG akan disimpan  

Prasyarat ini menjamin kode dapat dikompilasi dan dijalankan tanpa konfigurasi tambahan.

## Langkah 1: Instal paket NuGet Aspose.BarCode

Buka terminal di folder proyek dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Perintah ini menambahkan versi stabil terbaru dari pustaka ke file proyek Anda. Paket tersebut berisi kelas `BarcodeGenerator` yang digunakan sepanjang tutorial ini.

## Langkah 2: Tentukan folder output

Buat folder tempat gambar yang dihasilkan akan disimpan. Jalurnya dapat berupa absolut atau relatif terhadap executable.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` memastikan folder ada, sehingga mencegah error runtime saat metode `Save` menulis file.

## Langkah 3: Hasilkan barcode FCC 11

Format FCC 11 adalah enkoding default untuk barcode pos Australia Post. Kode berikut membuat barcode yang mengenkripsi string numerik `1101234567`.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Mengapa ini berhasil:**  
* `EncodeTypes.AustraliaPost` memberi tahu pustaka untuk menerapkan aturan enkoding Australia Post.  
* String data `1101234567` mengikuti spesifikasi FCC 11: dua digit pertama (`11`) mengidentifikasi format, diikuti oleh referensi pelanggan 7‑digit.  
* `XDimension` dan `BarHeight` mengontrol ukuran barcode yang dicetak, yang penting untuk keterbacaan pemindai.  

Setelah menjalankan program, Anda akan menemukan `PostalAustraliaPostFCC11.png` di folder `Barcodes`. Gambar tersebut terlihat seperti ini:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## Langkah 4: Buat barcode Australia Post tambahan (opsional)

Meskipun tujuan utama adalah **membuat barcode FCC 11**, Anda sering memerlukan barcode FCC 59 atau FCC 62 untuk kelas surat yang berbeda. Kode di bawah ini menggunakan kembali instance `BarcodeGenerator` yang sama, hanya mengubah string data dan tabel enkoding opsional.

### 4.1 FCC 59 dengan enkoding N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 dengan enkoding N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 dengan enkoding C‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 dengan enkoding Lain

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

Keempat gambar disimpan berdampingan dalam folder yang sama, memudahkan perbandingan perbedaan visual.

## Langkah 5: Pahami tabel enkoding

Australia Post mendefinisikan tiga tabel enkoding:

* **N‑Table** – menafsirkan informasi pelanggan numerik. Gunakan ketika payload hanya berisi digit.  
* **C‑Table** – mendukung karakter alfanumerik, berguna untuk nomor referensi yang mencakup huruf.  
* **Other** – fallback untuk format data khusus atau yang diperluas.

Memilih tabel yang tepat memastikan pemindai barcode mendekode informasi persis seperti yang diharapkan. Jika Anda mengabaikan properti `AustralianPostEncodingTable`, pustaka secara default menggunakan N‑Table, yang dapat memotong karakter non‑numerik.

## Tips, kasus tepi, dan jebakan umum

| Situation | Recommended approach |
|-----------|----------------------|
| Data string length is shorter than required | Pad the numeric portion with leading zeros to meet the FCC specification. |
| Barcode appears blurry when printed | Increase `XDimension` to 5 or 6 pixels and verify the printer’s DPI settings. |
| Scanner returns “invalid format” | Verify that the correct encoding table (N‑Table, C‑Table, Other) matches the data payload. |
| Running on Linux without a GUI | Ensure the `System.Drawing.Common` package is referenced, or use the `Save` method with `BarCodeImageFormat.Png` which does not require a display context. |
| Need a different image format | Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff` as required. |

Tips praktis ini berasal dari penerapan solusi barcode pos di dunia nyata.

## Contoh lengkap yang dapat dijalankan

Berikut adalah program mandiri yang dapat Anda salin ke proyek konsol baru (`dotnet new console`) dan jalankan tanpa modifikasi.



## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to generate barcode java – Australia Post Barcode with Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [How to create barcode quiet zone .NET for Code 16K using Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}