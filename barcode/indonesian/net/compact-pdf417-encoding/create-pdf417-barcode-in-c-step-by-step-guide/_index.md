---
category: general
date: 2026-10-04
description: Buat kode batang PDF417 di C# dengan cepat. Pelajari cara menghasilkan
  kode batang PDF417 dan cara menyimpan gambar kode batang sebagai PNG dengan Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- barcode for mobile scanning
- aspose barcode png generation
lastmod: 2026-10-04
og_description: Buat kode batang PDF417 di C# dengan Aspose.Barcode. Tutorial ini
  menunjukkan cara menghasilkan kode batang PDF417 yang kompak, mengonfigurasi tampilannya,
  dan menyimpannya sebagai gambar PNG untuk pemindaian seluler atau pencetakan label.
og_image_alt: 'Developer guide: Create PDF417 barcode in C# and save as PNG using
  Aspose.Barcode'
og_title: Buat kode batang PDF417 di C# – panduan lengkap langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
- Aspose.Barcode
title: Buat kode batang PDF417 di C# – panduan langkah demi langkah
url: /id/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat kode batang PDF417 di C# – panduan langkah demi langkah

Jika Anda perlu **membuat kode batang PDF417** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara menghasilkan kode batang PDF417 dan cara menyimpan gambar kode batang sebagai file PNG. Anda akan mendapatkan gambar kompak yang bekerja dengan baik untuk pemindaian seluler, sistem tiket, atau printer label.

## Jawaban Cepat
- **Perpustakaan mana yang menangani pembuatan PDF417?** Aspose.Barcode for .NET.  
- **Format apa yang disimpan contoh?** PNG, menggunakan `BarCodeImageFormat.Png`.  
- **Berapa baris kode yang diperlukan?** Sekitar 10 baris setelah penyiapan proyek.  
- **Bisakah saya menyesuaikan ukuran dan pemotongan?** Ya – properti `Columns`, `Rows`, dan `Truncate`.  
- **Apakah kode kompatibel dengan .NET‑6?** Sepenuhnya, dan juga bekerja dengan .NET Framework 4.7+.

## Apa yang Anda butuhkan untuk membuat kode batang PDF417 di C#?
Untuk memulai, Anda memerlukan SDK .NET terbaru, IDE seperti Visual Studio 2022, dan paket NuGet **Aspose.Barcode for .NET**. Alat‑alat ini memungkinkan contoh dikompilasi dan dijalankan tanpa konfigurasi tambahan.

- .NET 6.0 SDK atau yang lebih baru (juga bekerja dengan .NET Framework 4.7+)
- Visual Studio 2022 atau editor yang kompatibel dengan C#
- Akses internet untuk mengunduh paket NuGet Aspose.Barcode

## Bagaimana cara menyiapkan proyek .NET untuk pembuatan kode batang PDF417?
Buat proyek konsol baru, tambahkan paket Aspose.Barcode, dan buka `Program.cs` yang dihasilkan. Ini menyiapkan ruang kerja bersih tempat Anda dapat menginstansiasi generator kode batang dan menulis file output.

```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

## Bagaimana cara menghasilkan kode batang PDF417 dengan Aspose.Barcode?
`BarcodeGenerator` adalah kelas Aspose.Barcode yang membuat gambar kode batang dari data dan simbolologi yang diberikan. Anda menentukan simbolologi PDF417, menyediakan teks untuk dienkode, dan secara opsional menyesuaikan ukuran atau pengaturan koreksi kesalahan.

```bash
   dotnet add package Aspose.Barcode
   ```

### Mengapa ini penting
* **EncodeTypes.Pdf417** memberi tahu perpustakaan untuk menggunakan standar PDF417, yang mendukung muatan data besar dan koreksi kesalahan.
* Menyediakan karakter Unicode membuktikan generator menangani input non‑ASCII tanpa konfigurasi tambahan.

## Bagaimana cara mengonfigurasi tampilan kode batang PDF417?
Anda dapat mengontrol ukuran modul, jumlah kolom, dan apakah kode batang menggunakan mode kompak (dipotong). Pengaturan ini secara langsung memengaruhi keterbacaan pada layar kecil dan ukuran file keseluruhan gambar PNG.

`generator.Parameters.Barcode.XDimension` mengatur lebar satu modul, sementara `Columns` dan `Rows` menentukan dimensi matriks. Menetapkan `Truncate` ke `true` menghapus zona tenang untuk gambar yang lebih kompak.

```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

### Tips praktis
Jika Anda memerlukan kode batang yang lebih tinggi untuk ruang horizontal terbatas, tingkatkan `Columns`. Menetapkan `Truncate` ke `true` mengurangi tinggi keseluruhan dengan menghapus zona tenang, yang ideal untuk layar seluler.

## Bagaimana cara menyimpan gambar kode batang sebagai PNG?
`Save` adalah metode dari `BarcodeGenerator` yang menulis gambar yang dihasilkan ke sebuah file. Berikan jalur file dan `BarCodeImageFormat.Png` untuk membuat gambar PNG dalam satu langkah.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Hasil yang diharapkan
Menjalankan program membuat `CompactPdf417.png` di folder proyek. Membuka file tersebut menampilkan kode batang PDF417 kompak yang mengenkripsi string *Åspóse.Barcóde©*. Gambar dapat disematkan dalam HTML, laporan PDF, atau dicetak pada label.

## Bagaimana cara memverifikasi file kode batang yang dihasilkan?
Setelah program selesai, Anda dapat memverifikasi keberadaan file dengan perintah cepat. Pemeriksaan sederhana ini mengonfirmasi bahwa langkah pembuatan dan penyimpanan selesai tanpa error.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

Jika file muncul, proses **membuat kode batang PDF417** berhasil.

## Apa variasi umum dan kasus tepi saat menghasilkan kode batang PDF417?
Berbagai skenario mungkin memerlukan penyesuaian pada pengaturan generator. Di bawah ini tabel referensi cepat yang menunjukkan cara menangani variasi tipikal.

| Situation | Adjustment |
|-----------|------------|
| **String data lebih panjang** | Tingkatkan `Columns` atau atur `Rows` untuk menampung lebih banyak codeword. |
| **Format gambar berbeda** | Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif`. |
| **Resolusi lebih tinggi** | Atur `generator.Parameters.ImageResolution` sebelum `Save`. |
| **Warna latar belakang** | Gunakan `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;`. |
| **Penanganan pengecualian** | Bungkus `generator.Save` dalam blok `try/catch` untuk menangkap error I/O. |

## Apa langkah selanjutnya setelah membuat kode batang?
Sekarang Anda dapat menghasilkan dan menyimpan kode batang PDF417, Anda mungkin ingin menjelajahi kemampuan terkait seperti menghasilkan kode QR, menyematkan kode batang dalam dokumen PDF, atau menyesuaikan warna untuk keselarasan merek. Semua ini menggunakan API `BarcodeGenerator` yang sama, sehingga Anda dapat memperluas contoh dengan usaha minimal.

## Panduan terkait
- [Cara Membuat Kode Batang – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara Menghasilkan Kode Batang DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Cara menghasilkan kode batang Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menggunakan kode ini dalam aplikasi web?**  
A: Ya. Kelas `BarcodeGenerator` yang sama bekerja di proyek ASP.NET, MVC, atau Blazor; pastikan server memiliki izin menulis untuk folder output.

**Q: Apakah Aspose.Barcode mendukung simbolologi 2‑D lainnya?**  
A: Tentu saja. Lebih dari 30 jenis kode batang 2‑D didukung, termasuk QR, DataMatrix, dan Aztec.

**Q: Seberapa besar kode batang yang dapat saya buat?**  
A: PDF417 dapat mengenkripsi hingga 1.850 karakter dalam satu simbol; Anda juga dapat membagi data ke beberapa baris dengan menyesuaikan `Rows` dan `Columns`.

**Q: Apakah lisensi diperlukan untuk penggunaan produksi?**  
A: Ya. Versi percobaan gratis tersedia untuk evaluasi, tetapi lisensi komersial diperlukan untuk penerapan.

**Q: Versi .NET apa yang kompatibel?**  
A: Aspose.Barcode mendukung .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6/7.

---

**Terakhir Diperbarui:** 2026-10-04  
**Diuji Dengan:** Aspose.Barcode 24.11 untuk .NET  
**Penulis:** Aspose  

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```
```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```
```bash
dotnet run && ls -l CompactPdf417.png
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}