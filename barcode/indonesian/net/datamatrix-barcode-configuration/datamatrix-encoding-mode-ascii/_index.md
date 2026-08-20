---
date: 2026-06-09
description: Pelajari cara membuat kode batang DataMatrix dalam mode ASCII menggunakan
  Aspose.BarCode untuk .NET. Panduan ini menunjukkan cara menghasilkan kode batang
  C# dengan cepat.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: Mode Pengkodean DataMatrix (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Buat kode batang DataMatrix dalam mode ASCII dengan Aspose.BarCode untuk .NET
url: /id/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-container >}}
{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat kode batang DataMatrix dalam mode ASCII dengan Aspose.BarCode untuk .NET

## Pendahuluan

Siap untuk **membuat kode batang DataMatrix** gambar yang menggunakan enkoding ASCII yang efisien? Dalam tutorial ini Anda akan belajar cara menghasilkan kode batang DataMatrix dalam mode ASCII menggunakan Aspose.BarCode untuk .NET. Kami akan membimbing Anda melalui setiap langkah—dari menyiapkan proyek hingga menyimpan gambar akhir—sehingga Anda dapat menambahkan pembuatan kode batang ke aplikasi C# Anda dalam hitungan menit.

## Jawaban Cepat
- **Perpustakaan apa yang terbaik untuk DataMatrix di .NET?** Aspose.BarCode for .NET  
- **Berapa baris kode yang dibutuhkan?** About 5‑7 lines for a basic ASCII barcode  
- **Apakah saya memerlukan lisensi?** A free trial works for development; a license is required for production  
- **Platform yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Bisakah saya mengubah ukuran atau warna?** Yes, Aspose.BarCode exposes properties for dimensions and foreground/background colors  

## Apa itu kode batang DataMatrix?
DataMatrix adalah kode batang dua dimensi yang menyimpan teks dan data biner dalam pola persegi yang kompak.  
Sebuah kode batang DataMatrix mengenkode informasi dalam kisi modul hitam dan putih, memungkinkan hingga 2.335 karakter alfanumerik dalam satu simbol. Kode ini banyak digunakan dalam manufaktur, logistik, dan perawatan kesehatan karena dapat dicetak pada ukuran sangat kecil sambil tetap mudah dipindai.

## Cara membuat kode batang DataMatrix dalam mode ASCII?
Muat namespace Aspose.BarCode, buat instance `BarcodeGenerator`, atur `EncodeMode` ke **EncodeMode.ASCII**, berikan string data Anda, dan panggil `Save` untuk menulis file gambar. Pendekatan ini menghasilkan kode batang DataMatrix yang sepenuhnya sesuai dengan enkoding hanya ASCII dalam beberapa baris kode C#.

## Mengapa menggunakan enkoding ASCII untuk DataMatrix?
Mode ASCII adalah enkoding default dan paling efisien untuk data teks biasa, menghasilkan ukuran simbol terkecil untuk string alfanumerik. Ia mendukung semua 128 karakter ASCII, memproses data lebih cepat daripada mode ekstended, dan menjamin kompatibilitas maksimum dengan pemindai lama yang mengharapkan simbol ASCII standar.

## Prasyarat

1. **Lingkungan Pengembangan** – Visual Studio, Rider, atau IDE kompatibel C# apa pun.  
2. **Aspose.BarCode untuk .NET** – Unduh paket terbaru dari [here](https://releases.aspose.com/barcode/net/).  
   - Dokumentasi: [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
   - Bantuan komunitas: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **Pengetahuan dasar C#** – Familiaritas dengan struktur proyek .NET akan membantu Anda mengikuti langkah-langkah dengan cepat.  
4. **Produk Aspose lainnya** dapat ditemukan [here](https://releases.aspose.com/).

## Impor Namespace

Untuk memulai, tambahkan direktif `using` yang diperlukan di bagian atas file C# Anda:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Namespace ini memberi Anda akses ke kelas `BarcodeGenerator` dan tipe terkait gambar yang diperlukan untuk menyimpan output.

## Langkah 1: Buat Direktori

Pilih folder tempat gambar kode batang yang dihasilkan akan disimpan. Ganti `"Your Directory Path"` dengan jalur absolut atau relatif yang ada di mesin Anda.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

Kode ini memastikan direktori ada sebelum mencoba menulis file apa pun, mencegah kesalahan runtime.

## Langkah 2: Enkoding Data dalam Mode ASCII

Kelas `BarcodeGenerator` membuat dan mengonfigurasi gambar kode batang. Enumerasi `DataMatrixEncodeMode` memilih algoritma enkoding untuk simbol DataMatrix.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

Setelah menjalankan kode, Anda akan menemukan `datamatrix_ascii.png` di folder yang Anda tentukan. Gambar tersebut berisi kode batang DataMatrix yang mengenkode string `"1234567890"` menggunakan mode ASCII yang kompak.

## Masalah umum dan solusi

- **Kesalahan akses file** – Pastikan aplikasi memiliki izin menulis ke folder target. Menjalankan Visual Studio sebagai Administrator dapat menyelesaikan masalah izin di Windows.  
- **Ukuran simbol tidak tepat** – Jika kode batang terlihat terlalu besar atau terlalu kecil, sesuaikan `generator.Parameters.Image.Width` dan `Height` atau biarkan Aspose menghitung ukuran optimal secara otomatis dengan menghilangkan properti tersebut.  
- **Karakter tidak didukung** – Mode ASCII hanya menerima karakter dalam rentang 0‑127. Untuk data Unicode, beralih ke `DataMatrixEncodeMode.Base256` atau mode lain yang sesuai.

## Pertanyaan yang Sering Diajukan

**Q: Apakah saya dapat menggunakan ini dalam aplikasi komersial?**  
A: Ya, lisensi Aspose yang valid diperlukan untuk penggunaan produksi; versi percobaan gratis tersedia untuk evaluasi.

**Q: Apakah perpustakaan ini bekerja dengan .NET Core?**  
A: Tentu – Aspose.BarCode sepenuhnya mendukung .NET Core 3.1+, .NET 5, .NET 6, dan versi selanjutnya.

**Q: Berapa banyak karakter yang dapat saya enkode dalam mode ASCII?**  
A: Hingga 2.335 karakter alfanumerik dapat muat dalam satu simbol DataMatrix saat menggunakan enkoding ASCII.

**Q: Bisakah saya mengubah warna latar depan atau latar belakang kode batang?**  
A: Ya, sesuaikan `generator.Parameters.Image.ForeColor` dan `BackColor` ke nilai `System.Drawing.Color` apa pun.

**Q: Di mana saya dapat menemukan contoh yang lebih lanjutan?**  
A: Dokumentasi resmi berisi puluhan contoh yang mencakup ukuran khusus, warna, dan tingkat koreksi kesalahan.

## FAQ

### Q1: Bisakah saya menggunakan Aspose.BarCode untuk .NET dengan bahasa pemrograman lain selain C#?

A1: Aspose.BarCode mendukung beberapa bahasa pemrograman, tetapi tutorial ini berfokus pada C#.

### Q2: Apa saja mode enkoding yang tersedia dalam kode batang DataMatrix?

A2: Kode batang DataMatrix mendukung berbagai mode enkoding, termasuk ASCII, C40, Text, dan Base256. Setiap mode cocok untuk jenis data yang berbeda.

### Q3: Bisakah saya menyesuaikan tampilan kode batang yang dihasilkan, seperti ukuran dan warnanya?

A3: Ya, Aspose.BarCode menyediakan beragam parameter untuk menyesuaikan tampilan kode batang, termasuk ukuran, warna, dan lainnya.

### Q4: Apakah ada versi percobaan gratis Aspose.BarCode untuk .NET yang tersedia?

A4: Ya, Anda dapat menjelajahi Aspose.BarCode untuk .NET dengan versi percobaan gratis dari [here](https://releases.aspose.com/).

### Q5: Di mana saya dapat membeli lisensi untuk Aspose.BarCode untuk .NET?

A5: Anda dapat membeli lisensi dari situs web Aspose [here](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Tutorial Terkait

- [Enkoding DataMatrix dalam Byte dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Baca kode batang DataMatrix C# – Hasilkan Mode DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Cara Menghasilkan Kode Batang DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/pf/main-wrap-class >}}