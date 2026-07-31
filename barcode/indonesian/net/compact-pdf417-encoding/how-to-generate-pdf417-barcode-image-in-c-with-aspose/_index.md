---
category: general
date: 2026-07-30
description: Cara menghasilkan gambar barcode PDF417 di C# dengan Aspose. Pelajari
  langkah demi langkah cara membuat barcode dengan Aspose, mengatur metadata MacroPDF417,
  dan menyimpannya sebagai PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode image c#
- create barcode with aspose
- Aspose.BarCode PDF417
- MacroPdf417 metadata
language: id
lastmod: 2026-07-30
og_description: Cara menghasilkan gambar barcode PDF417 di C# dengan Aspose. Ikuti
  panduan lengkap ini untuk membuat barcode dengan Aspose, mengonfigurasi metadata
  MacroPDF417, dan menghasilkan file PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode image created with Aspose
  in C#
og_title: Cara Membuat Gambar Barcode PDF417 di C# dengan Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: How to generate PDF417 barcode image in C# with Aspose. Learn step‑by‑step
    how to create barcode with Aspose, set MacroPDF417 metadata, and save as PNG.
  headline: How to Generate PDF417 Barcode Image in C# with Aspose
  type: TechArticle
tags:
- Aspose
- C#
- Barcode
title: Cara Menghasilkan Gambar Barcode PDF417 di C# dengan Aspose
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Gambar Barcode PDF417 di C# dengan Aspose

Cara membuat gambar barcode PDF417 di C# dengan Aspose sering menjadi tantangan bagi siapa saja yang menangani pengkodean data berkapasitas tinggi. Dalam panduan ini kami akan membahas setiap langkah—menyiapkan generator, menyesuaikan metadata MacroPDF417, dan akhirnya menyimpan file PNG yang tajam.

Jika Anda pernah mencoba **generate barcode image c#** dan berakhir dengan kanvas kosong atau pemindaian yang tidak dapat dibaca, Anda tidak sendirian. Kabar baiknya, Aspose.BarCode membuat seluruh proses hampir tanpa rasa sakit, dan pada akhir artikel ini Anda akan dapat **create barcode with Aspose** untuk alur kerja perusahaan apa pun.

## Apa yang Akan Anda Pelajari

- Menginstal dan mereferensikan pustaka Aspose.BarCode untuk .NET.  
- Menginisialisasi generator PDF417 dengan payload khusus.  
- Menerapkan bidang spesifik MacroPDF417 seperti file ID, segment ID, dan timestamp.  
- Mengekspor hasil ke gambar PNG yang dapat disisipkan dalam laporan atau aplikasi seluler.  
- Tips untuk memecahkan masalah umum (misalnya, lebar modul yang salah, segmen yang hilang).

Tidak diperlukan pengalaman sebelumnya dengan MacroPDF417; pemahaman dasar tentang C# dan Visual Studio sudah cukup.

## Prasyarat

| Persyaratan | Alasan |
|-------------|--------|
| .NET 6.0 atau lebih baru | Versi LTS terkini, sepenuhnya didukung oleh Aspose |
| Visual Studio 2022 (atau IDE apa pun) | Untuk mengkompilasi dan menjalankan contoh |
| Aspose.BarCode untuk .NET (NuGet) | Menyediakan `BarcodeGenerator` dan dukungan PDF417 |

Anda dapat menambahkan pustaka melalui NuGet:

```bash
dotnet add package Aspose.BarCode
```

Setelah fondasi selesai, mari kita selami kode.

## Cara Membuat Gambar Barcode PDF417 di C# – Penyiapan

Hal pertama yang kami lakukan adalah membuat instance `BarcodeGenerator` untuk tipe enkode **MacroPdf417**. Objek ini memuat semua opsi konfigurasi, mulai dari ukuran modul hingga metadata kaya yang diharapkan MacroPDF417.

```csharp
using Aspose.BarCode.Generation;
using System;

// Step 1: Create the barcode generator with the desired payload.
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Payload"))
{
    // The rest of the configuration goes here.
}
```

> **Mengapa ini penting:** `EncodeTypes.MacroPdf417` memberi tahu Aspose untuk menghasilkan barcode PDF417 yang dapat dibagi menjadi beberapa segmen—fitur penting untuk file besar atau pemrosesan batch.

## Mengonfigurasi Penampilan Dasar

Barcode yang dapat dibaca dimulai dengan pengaturan visual yang tepat. `XDimension` mengontrol lebar setiap modul (kotak hitam/putih kecil), sementara `Columns` menentukan berapa banyak kolom yang akan ditempati barcode.

```csharp
// Step 2: Define basic barcode appearance.
generator.Parameters.Barcode.XDimension.Pixels = 2;   // Module width in pixels.
generator.Parameters.Barcode.Pdf417.Columns = 5;    // Number of columns (adjust for size).
```

- **Tip:** Jika barcode terlihat terlalu padat pada printer struk, naikkan `XDimension` menjadi `3` atau `4`.  
- **Jebakan:** Menetapkan `Columns` terlalu rendah dapat menyebabkan barcode melampaui batas gambar, menghasilkan pemindaian yang tidak dapat dibaca.

## Menetapkan Metadata Khusus MacroPDF417

MacroPDF417 memungkinkan Anda menyematkan informasi tingkat file langsung ke dalam barcode. Ini sangat cocok untuk melacak pengiriman dokumen besar atau membagi file menjadi beberapa pemindaian.

```csharp
// Step 3: Set MacroPDF417 specific metadata.
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 CRC
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Apa fungsi masing‑masing bidang:**

| Properti | Deskripsi |
|----------|-----------|
| `MacroPdf417FileID` | Pengidentifikasi unik untuk seluruh file. |
| `MacroPdf417SegmentID` | Indeks segmen saat ini (dimulai dari 0). |
| `MacroPdf417SegmentsCount` | Jumlah total segmen yang file dibagi. |
| `MacroPdf417FileName` | Nama yang dapat dibaca manusia, berguna untuk log audit. |
| `MacroPdf417Checksum` | CRC 16‑bit untuk verifikasi integritas data. |
| `MacroPdf417FileSize` | Ukuran file asli dalam byte, membantu penerima mengalokasikan buffer. |
| `MacroPdf417TimeStamp` | Tanggal/waktu saat file dibuat. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | String opsional untuk mengidentifikasi pengirim/penerima. |
| `MacroPdf417Terminator` | Menandai segmen terakhir; diperlukan untuk dekoding yang tepat. |

> **Mengapa repot?** Tanpa bidang‑bidang ini, pemindai hanya dapat membaca data mentah, bukan konteksnya. Menambahkan metadata berarti sistem penerima dapat menyusun kembali file asli secara otomatis.

## Menyimpan Barcode sebagai PNG

Setelah generator sepenuhnya dikonfigurasi, menyimpan gambar cukup dengan satu baris kode:

```csharp
// Step 4: Save the generated barcode image.
generator.Save("YOUR_DIRECTORY/MacroPdf417Meta.png", BarCodeImageFormat.Png);
```

- **Format file:** PNG bersifat lossless, memastikan setiap modul tetap tajam untuk pemindai.  
- **Alternatif:** Gunakan `BarCodeImageFormat.Jpeg` jika Anda memerlukan ukuran file yang lebih kecil, namun harapkan sedikit penurunan keterbacaan.

### Output yang Diharapkan

Setelah menjalankan potongan kode, Anda akan menemukan `MacroPdf417Meta.png` di folder yang ditentukan. Gambar tersebut seharusnya mirip dengan ilustrasi di bawah ini:

![PDF417 barcode generated with Aspose](path/to/your/image.png){alt="Cara menghasilkan gambar barcode PDF417 di C#"}

Gambar tersebut berisi kisi‑kisi padat kotak hitam dan putih, dengan payload yang terenkode serta metadata MacroPDF417 yang disematkan.

## Contoh Lengkap yang Siap Pakai

Berikut adalah program lengkap yang dapat Anda salin‑tempel. Program ini dapat dikompilasi dengan proyek .NET 6+ apa pun dan hanya memerlukan paket NuGet Aspose.BarCode.



## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}