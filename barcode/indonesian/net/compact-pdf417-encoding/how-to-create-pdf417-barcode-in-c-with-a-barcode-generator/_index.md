---
category: general
date: 2026-11-17
description: Pelajari cara membuat barcode PDF417 di C# – panduan lengkap tentang
  cara menghasilkan barcode dari string menggunakan generator barcode C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: id
lastmod: 2026-11-17
og_description: Buat kode batang PDF417 di C# dengan cepat. Tutorial ini menunjukkan
  cara menghasilkan kode batang dari string dengan generator kode batang C# dan menyertakan
  kode sumber lengkap.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: Buat kode batang PDF417 di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: Cara membuat barcode PDF417 di C# dengan generator barcode
url: /id/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat PDF417 barcode di C# dengan generator barcode

Jika Anda perlu **create PDF417 barcode** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara melakukannya. Anda akan belajar **how to generate barcode** dari string biasa, mengonfigurasi ukuran simbol, dan menyimpan hasilnya sebagai file PNG—semua menggunakan generator barcode C# yang handal.

Membuat barcode secara programatik menghilangkan langkah manual dan menjamin kualitas yang konsisten. Dalam tutorial ini kami akan membahas semuanya mulai dari penyiapan proyek hingga gambar akhir, sehingga Anda dapat mengintegrasikan pembuatan barcode ke dalam solusi C# apa pun hari ini.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru (kode ini bekerja dengan .NET Core dan .NET Framework)
* Visual Studio 2022 (atau IDE apa pun yang mendukung C#)
* Lisensi atau percobaan gratis **Aspose.BarCode for .NET** – perpustakaan yang digunakan dalam contoh
* Familiaritas dasar dengan sintaks C#

Tidak diperlukan paket tambahan; paket NuGet `Aspose.BarCode` berisi semua kelas yang Anda perlukan.

## Langkah 1 – Menyiapkan generator barcode C#

Hal pertama yang Anda lakukan saat **create PDF417 barcode** adalah menginstansiasi objek `BarcodeGenerator`. Objek ini mewakili **c# barcode generator** yang akan menangani pengkodean, rendering, dan penyimpanan.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*Mengapa ini penting*: Enum `EncodeTypes.Pdf417` memberi tahu perpustakaan untuk menggunakan simbol PDF417, yang merupakan standar yang sama digunakan untuk kartu identitas dan label transportasi. String `"(01)12345678901234"` adalah contoh **generate barcode from string** yang juga menunjukkan cara **create GS1 barcode** data.

## Langkah 2 – Mengonfigurasi dimensi X (lebar modul)

Dimensi X mengontrol lebar bar terkecil (modul). Nilai umum untuk rendering di layar adalah 2 piksel.

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Menetapkan dimensi X secara eksplisit mencegah generator menggunakan nilai default, yang mungkin menghasilkan barcode terlalu kecil untuk beberapa pemindai.

## Langkah 3 – Menentukan jumlah kolom

PDF417 memungkinkan Anda menyesuaikan jumlah kolom, yang memengaruhi bentuk barcode dan kapasitas data. Untuk label kompak, empat kolom bekerja dengan baik.

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

Jika Anda memerlukan barcode yang lebih tinggi, tingkatkan jumlah kolom; perpustakaan akan secara otomatis menghitung baris yang diperlukan.

## Langkah 4 – Menyimpan barcode sebagai gambar

Akhirnya, ekspor barcode ke file PNG. PNG mempertahankan tepi yang tajam dan mendukung transparansi.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

Menjalankan program akan membuat `output/Gs1Pdf417.png`. Buka file tersebut di penampil gambar apa pun—Anda akan melihat **PDF417 barcode** yang bersih yang mengkodekan data GS1 yang Anda berikan.

### Output yang Diharapkan

![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="Barcode PDF417 yang dihasilkan dibuat dengan generator barcode C#"}

*Gambar di atas menunjukkan hasil dari contoh kode lengkap. Barcode dapat dipindai oleh pembaca yang kompatibel dengan PDF417 apa pun.*

## Opsi tambahan dan variasi umum

### Mengubah format gambar

Jika Anda lebih suka JPEG atau BMP, cukup ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg` atau `BarCodeImageFormat.Bmp`. Sisanya kode tetap sama.

### Menyesuaikan tingkat koreksi kesalahan

PDF417 mendukung tingkat koreksi kesalahan 0‑8. Tingkat yang lebih tinggi meningkatkan redundansi tetapi juga memperbesar barcode.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Menghasilkan barcode GS1 lainnya

`BarcodeGenerator` yang sama dapat menghasilkan **create GS1 barcode** untuk simbol lain, seperti `EncodeTypes.Gs1DataMatrix` atau `EncodeTypes.Gs1Qr`. Cukup ganti nilai enum:

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Menangani data kosong atau null

Saat Anda **generate barcode from string**, selalu validasi input:

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

Ini mencegah pengecualian runtime dan memastikan barcode mematuhi aturan format GS1.

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda salin‑tempel ke proyek konsol baru. Program ini mencakup semua direktif `using` yang diperlukan, pembuatan folder, dan penanganan error.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Jalankan program** (`dotnet run`) dan Anda akan menemukan `Gs1Pdf417.png` di dalam folder *output*. Pindai dengan pembaca PDF417 apa pun untuk memverifikasi bahwa GTIN `(01)12345678901234` telah terkodekan dengan benar.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan kode ini pada .NET Framework 4.6?**  
A: Ya. Perpustakaan Aspose.BarCode menargetkan .NET Standard 2.0, yang kompatibel dengan .NET Framework 4.6 dan yang lebih baru.

**Q: Bagaimana jika saya membutuhkan gambar dengan resolusi lebih tinggi?**  
A: Atur properti `Resolution` sebelum menyimpan:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**Q: Apakah barcode masih valid tanpa Identifier Aplikasi GS1?**  
A: Itu akan menjadi barcode PDF417 standar, tetapi tidak akan dikenali sebagai simbol yang mematuhi GS1. Sertakan awalan `(01)` ketika Anda memerlukan kepatuhan **create GS1 barcode**.

## Kesimpulan

Anda sekarang tahu cara **create PDF417 barcode** di C# menggunakan **c# barcode generator** yang kuat. Tutorial ini mencakup:

* Menginstansiasi `BarcodeGenerator` dengan data GS1  
* Mengonfigurasi dimensi X dan jumlah kolom  
* Menyimpan hasil sebagai gambar PNG  
* Memperluas solusi dengan koreksi kesalahan, format berbeda, dan validasi input  

Dengan dasar ini Anda dapat menghasilkan barcode PDF417 atau GS1 apa pun langsung dari string, menyematkannya dalam laporan, atau mengirimnya ke printer. Jelajahi API Aspose.BarCode untuk menambahkan warna, menambahkan margin, atau menggabungkan beberapa barcode menjadi satu gambar.

**Langkah selanjutnya**: coba menghasilkan **create GS1 barcode** untuk DataMatrix, bereksperimen dengan perhitungan kolom dinamis, atau integrasikan generator ke dalam layanan web ASP.NET Core yang mengembalikan gambar barcode sesuai permintaan.

Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara menghasilkan PDF417 barcode di C# – panduan lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [Cara membuat barcode micro pdf417 dan menghasilkan PNG di C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [Cara membuat barcode macro PDF417 di C# menggunakan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}