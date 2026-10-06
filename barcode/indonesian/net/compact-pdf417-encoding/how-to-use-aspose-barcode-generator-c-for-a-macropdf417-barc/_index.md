---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C# memungkinkan Anda menambahkan data makro
  dan menghasilkan kode batang PDF417 dengan mudah. Pelajari langkah demi langkah
  cara menambahkan metadata makro dan membuat gambar PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: id
lastmod: 2026-10-05
og_description: Aspose Barcode Generator C# menunjukkan cara menambahkan metadata
  makro dan menghasilkan kode batang PDF417 dalam beberapa baris kode.
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Aspose Barcode Generator C# – tambahkan makro & hasilkan barcode PDF417
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: Cara menggunakan Aspose Barcode Generator C# untuk barcode MacroPdf417
url: /id/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menggunakan Aspose Barcode Generator C# untuk barcode MacroPdf417

Jika Anda perlu membuat barcode MacroPdf417 dalam C#, **Aspose Barcode Generator C#** menyediakan API yang ringkas yang menangani baik gambar barcode maupun metadata macro yang diperlukan. Tutorial ini menunjukkan secara tepat cara menambahkan informasi macro dan menghasilkan gambar barcode PDF417 dalam beberapa langkah saja.

Anda akan belajar cara mengonfigurasi parameter visual, menyematkan field macro seperti file ID dan timestamp, serta menyimpan hasilnya sebagai PNG. Tidak diperlukan alat eksternal—hanya pustaka Aspose.BarCode dan lingkungan pengembangan .NET.

## Prasyarat

* .NET 6.0 atau yang lebih baru terinstal  
* Visual Studio 2022 (atau IDE C# apa pun)  
* Salinan berlisensi atau evaluasi dari **Aspose.BarCode untuk .NET**  

Kode ini bekerja di Windows, Linux, dan macOS karena pustaka ini bersifat platform‑agnostik.

## Langkah 1: Instal paket NuGet Aspose.BarCode

Buka proyek Anda di Visual Studio, lalu jalankan perintah berikut di **Package Manager Console**:

```powershell
Install-Package Aspose.BarCode
```

Ini menambahkan assembly `Aspose.BarCode` dan dependensinya ke proyek Anda.

## Langkah 2: Buat instance barcode generator

Baris pertama membuat objek `BarcodeGenerator` untuk simbol **MacroPdf417** dan menyediakan teks yang ingin Anda enkode.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*Mengapa ini penting*: Nilai `EncodeTypes.MacroPdf417` memberi tahu pustaka untuk mengharapkan field terkait macro, yang akan Anda atur pada langkah berikutnya.

## Langkah 3: Tentukan tampilan visual

Anda dapat mengontrol ukuran setiap modul (kotak hitam atau putih terkecil) dan jumlah kolom dalam matriks PDF417. Menyesuaikan `XDimension` memengaruhi resolusi gambar secara keseluruhan.

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

Meningkatkan `Columns` mengurangi tinggi barcode, sementara `XDimension` yang lebih besar membuat gambar lebih jelas pada layar ber‑DPI tinggi.

## Langkah 4: Tambahkan metadata macro (cara menambahkan macro)

MacroPdf417 memerlukan beberapa field tambahan yang menggambarkan file sumber dan segmentasinya. Properti berikut langsung memetakan spesifikasi macro PDF417:

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*Mengapa field ini*:
* `MacroPdf417FileID` mengikat semua segmen bersama, memastikan pemindai dapat menyusun kembali dokumen asli.  
* `MacroPdf417SegmentID` dan `MacroPdf417SegmentsCount` memberi tahu decoder urutan dan total jumlah bagian.  
* `MacroPdf417FileSize` dan `MacroPdf417Checksum` menyediakan pemeriksaan integritas, yang berguna untuk transfer data besar.

## Langkah 5: Simpan gambar barcode (cara menghasilkan pdf417)

Akhirnya, tulis barcode ke disk. Metode `Save` menerima jalur file dan format gambar. PNG mempertahankan tepi barcode yang tajam tanpa artefak kompresi.

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Saat program dijalankan, Anda akan menemukan **ExtPDF417Meta.png** di folder output. Membuka gambar menampilkan barcode MacroPdf417 yang bersih, siap untuk dicetak atau disematkan dalam PDF.

### Output yang Diharapkan

| Nama file          | Format | Dimensi (perkiraan) |
|--------------------|--------|----------------------|
| ExtPDF417Meta.png  | PNG    | 300 × 150 px (varies with `XDimension`) |

Memindai gambar dengan pembaca yang kompatibel dengan PDF417 (mis., ZXing, Aspose.BarCode untuk .NET) mengembalikan teks asli **“Åspóse.Barcóde©”** beserta semua field macro.

## Kesalahan umum dan cara menghindarinya

| Masalah | Mengapa terjadi | Solusi |
|---------|----------------|--------|
| **Incorrect `EncodeTypes`** | Menggunakan `EncodeTypes.Pdf417` alih-alih `EncodeTypes.MacroPdf417` menonaktifkan field macro. | Selalu buat instance generator dengan `EncodeTypes.MacroPdf417`. |
| **Missing macro fields** | Beberapa pemindai mengabaikan barcode jika field macro yang diperlukan tidak disertakan. | Isi setidaknya `FileID`, `SegmentID`, `SegmentsCount`, dan `Terminator`. |
| **Too small `XDimension`** | Nilai di bawah 1 piksel dapat menghasilkan barcode yang tidak dapat dibaca pada tampilan beresolusi rendah. | Pertahankan `XDimension` ≥ 2 piksel untuk kebanyakan skenario layar dan cetak. |
| **File path errors** | Memberikan jalur relatif yang tidak ada akan memunculkan pengecualian. | Gunakan `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` atau jalur absolut. |

## Kode sumber lengkap

Berikut adalah contoh lengkap yang dapat dijalankan yang dapat Anda salin ke proyek konsol baru.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

Jalankan program (`dotnet run`). Setelah eksekusi, konsol mencetak pesan sukses dan file PNG muncul di folder output proyek.

## Langkah Selanjutnya

* **Encode data lebih besar** – Tingkatkan `Columns` atau sesuaikan `Rows` (melalui `Pdf417.Rows`) untuk menampung lebih banyak karakter.  
* **Sematkan dalam PDF** – Gunakan Aspose.PDF untuk menempatkan PNG yang dihasilkan ke dalam dokumen.  
* **Verifikasi pemindaian** – Manfaatkan `Aspose.BarCode.Reader` untuk mendekode barcode dan mengonfirmasi field macro secara programatik.  

Mengeksplorasi topik ini memperdalam pemahaman Anda tentang **cara menghasilkan barcode PDF417** dengan informasi macro yang kaya dan mempersiapkan Anda untuk kasus penggunaan dunia nyata seperti pemrosesan dokumen batch atau pertukaran data yang aman.

---

*Selamat coding! Jika Anda menemukan panduan ini berguna, pertimbangkan untuk membagikannya dengan rekan tim atau memberi bintang pada repositori Aspose.BarCode di GitHub.*

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to generate PDF417 barcode in C# with Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Aspose barcode example: generate Macro PDF417 in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}