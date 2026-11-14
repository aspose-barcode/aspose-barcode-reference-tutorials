---
category: general
date: 2026-11-14
description: Pelajari cara membuat barcode PDF417 di C# dengan cepat. Panduan ini
  juga menunjukkan cara menghasilkan PDF417 dan cara menyesuaikan pengaturan PDF417
  untuk kontrol yang tepat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: id
lastmod: 2026-11-14
og_description: Buat kode batang PDF417 di C# dengan petunjuk langkah demi langkah.
  Pelajari cara menghasilkan PDF417 dan cara menyesuaikan parameter PDF417 untuk hasil
  yang tepat.
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: Buat kode batang PDF417 di C# – panduan lengkap dengan tata letak khusus
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: Cara membuat barcode PDF417 dengan tata letak khusus di C#
url: /id/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode PDF417 dengan tata letak khusus di C#

Jika Anda perlu **membuat barcode pdf417** untuk sistem tiket, label inventaris, atau pemindaian aplikasi seluler, tutorial ini menunjukkan proses lengkapnya. Anda akan melihat cara menghasilkan PDF417 dengan cepat dan cara menyesuaikan pengaturan PDF417 seperti kolom dan baris, sehingga barcode sesuai dengan batasan desain Anda.

Membuat barcode tidak memerlukan perpustakaan grafis yang kompleks—hanya Aspose.BarCode untuk .NET (atau API kompatibel apa pun). Pada akhir panduan ini Anda akan memiliki file PNG siap pakai yang dapat Anda sematkan dalam PDF, halaman web, atau mencetak langsung dari aplikasi Anda.

## Prerequisites

- .NET 6.0 atau lebih baru (kode juga berfungsi dengan .NET Framework 4.7+)
- Aspose.BarCode untuk .NET (paket NuGet `Aspose.BarCode`)
- Pemahaman dasar tentang C# dan Visual Studio (atau IDE apa pun)

> **Pro tip:** Jika Anda menggunakan pipeline CI/CD, tambahkan referensi paket NuGet di file proyek Anda sehingga build tetap dapat direproduksi.

## Step 1: Install the barcode library

Buka folder proyek Anda di terminal dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Paket ini menyertakan kelas `BarcodeGenerator` yang digunakan sepanjang tutorial ini. Tidak ada dependensi native tambahan yang diperlukan.

## Step 2: Create a basic PDF417 barcode

Tujuan pertama adalah **membuat barcode pdf417** dengan pengaturan default. Program berikut menyiapkan generator, mengkodekan string contoh, dan menyimpan hasilnya sebagai gambar PNG.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**Why this works:**  
`EncodeTypes.Pdf417` memberi tahu perpustakaan untuk menggunakan simbol PDF417. Konstruktor secara otomatis membuat objek `Barcode` dengan nilai kolom/baris default yang menjamin dapat dipindai untuk kebanyakan kasus penggunaan.

Jalankan program (`dotnet run`). Anda akan menemukan `Pdf417Default.png` di folder proyek. Membuka gambar menampilkan barcode PDF417 standar yang siap dipindai.

![Create PDF417 barcode example](https://example.com/images/pdf417-default.png){:alt="Contoh pembuatan barcode PDF417 yang menunjukkan tata letak default"}

## Langkah 3: Cara menghasilkan PDF417 dengan dimensi khusus

Kadang label berukuran tetap atau komponen UI memerlukan jejak barcode tertentu. Di sinilah **cara menghasilkan pdf417** dengan kolom dan baris khusus menjadi penting.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**Why you might want this:**  
- **Lebar terbatas:** Mengurangi kolom dan menambah baris menghasilkan barcode yang lebih lebar tetapi lebih pendek, sempurna untuk label sempit.  
- **Tinggi terbatas:** Menambah kolom dan mengurangi baris menghasilkan barcode yang lebih tinggi dan lebih sempit, berguna ketika Anda memiliki ruang vertikal.

Baik `Columns` maupun `Rows` hanya menerima nilai dalam rentang yang didokumentasikan (2‑30 untuk kolom, 1‑90 untuk baris). Memberikan nilai di luar rentang akan memunculkan `ArgumentOutOfRangeException`, jadi selalu validasi input pengguna jika Anda menampilkan pengaturan ini di UI.

## Langkah 4: Cara menyesuaikan PDF417 lebih lanjut

Selain kolom dan baris, simbol PDF417 menawarkan banyak parameter opsional:

| Property | Tujuan | Nilai tipikal |
|----------|--------|----------------|
| `ErrorLevel` | Mengontrol kemampuan koreksi kesalahan | 0‑8 (lebih tinggi = lebih kuat) |
| `MacroPdf417` | Mengaktifkan macro PDF417 untuk data multi‑segmen | `true`/`false` |
| `CompactPdf417` | Menghasilkan barcode yang lebih kompak dengan mengorbankan koreksi kesalahan yang berkurang | `true`/`false` |
| `SecurityLevel` | Menambahkan digit pemeriksaan keamanan | 0‑2 |

Berikut contoh singkat yang juga mengatur level kesalahan ke maksimum (8) untuk lingkungan yang berisik:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**Why it matters:**  
Koreksi kesalahan yang lebih tinggi memungkinkan pemindai memulihkan data bahkan jika sebagian barcode rusak. Namun, hal ini juga meningkatkan ukuran barcode, jadi seimbangkan pengaturan ini dengan batasan tata letak Anda.

## Langkah 5: Verifikasi barcode berfungsi

Setelah menghasilkan PNG, uji dengan aplikasi pemindai barcode apa pun (sebagian besar smartphone memiliki pembaca PDF417 gratis). Jika pemindai mengembalikan teks asli (`Custom layout text`), barcode tersebut valid.

Jika Anda mengalami masalah pemindaian:

1. **Periksa dimensi:** Pastikan kolom/baris tetap dalam rentang yang diizinkan.  
2. **Sesuaikan level kesalahan:** Tingkatkan `ErrorLevel` untuk media yang rusak.  
3. **Tinjau kualitas gambar:** Simpan dengan DPI yang lebih tinggi (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) jika Anda berencana mencetak.

## Kode sumber lengkap untuk helper yang dapat digunakan kembali

Berikut adalah kelas kompak yang dapat digunakan kembali yang dapat Anda masukkan ke dalam proyek .NET apa pun. Kelas ini mengenkapsulasi **cara menghasilkan pdf417** dan **cara menyesuaikan pdf417** dalam satu metode.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

Anda dapat memanggil helper ini seperti:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

Metode ini mengabstraksi boiler‑plate yang berulang, memungkinkan Anda fokus pada logika bisnis.

## Kesalahan umum dan cara menghindarinya

- **Nilai di luar rentang:** Selalu validasi `columns` dan `rows` sebelum menetapkannya.  
- **Format gambar tidak tepat:** Beberapa pemindai lama hanya menerima BMP atau JPEG. Gunakan `BarCodeImageFormat.Bmp` jika diperlukan.  
- **DPI rendah untuk cetak:** DPI default adalah 96. Untuk cetakan berkualitas tinggi, secara eksplisit atur DPI yang lebih tinggi (mis., 300) saat memanggil `Save`.  
- **Kurangnya dukungan font:** PDF417 mengkodekan data biner, jadi biasanya Anda tidak perlu menentukan font. Namun, jika Anda menambahkan teks di atas gambar, pastikan font terpasang di mesin target.

## Conclusion

Anda kini tahu cara **membuat barcode pdf417** dari awal hingga akhir, cara **menghasilkan pdf417** dengan pengaturan kolom/baris khusus, dan cara **menyesuaikan pdf417** untuk koreksi kesalahan dan kekompakan. Dengan mengikuti pola helper yang dapat digunakan kembali, Anda dapat menghasilkan barcode sesuai permintaan, menyesuaikannya dengan batasan tata letak apa pun, dan menjamin pemindaian yang andal di lingkungan produksi.

**Next steps**

- Jelajahi simbol lain seperti QR atau Code128 menggunakan kelas `BarcodeGenerator` yang sama.  
- Gabungkan output PNG dengan perpustakaan pembuatan PDF (mis., iText7) untuk menyematkan barcode dalam faktur.  
- Bereksperimen dengan `MacroPdf417` untuk transmisi data multi‑segmen, fitur yang berguna dalam aplikasi logistik dan transportasi.

Selamat coding, semoga barcode Anda selalu dapat dipindai pada percobaan pertama!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara menghasilkan barcode PDF417 di C# – panduan langkah demi langkah](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Cara menghasilkan barcode dan menyesuaikan barcode PDF417 di C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [Cara membuat barcode PDF417 dan mengekspor PNG di C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}