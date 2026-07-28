---
category: general
date: 2026-07-27
description: Tutorial barcode dengan karakter khusus menunjukkan cara menghasilkan
  barcode PDF417 dengan Aspose. Pelajari pembuatan langkah demi langkah dan penanganan
  data Unicode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode with special characters
- how to generate pdf417
- create barcode with aspose
- Aspose PDF417 macro
- Unicode barcode generation
language: id
lastmod: 2026-07-27
og_description: Tutorial barcode dengan karakter khusus menjelaskan cara menghasilkan
  barcode PDF417 menggunakan Aspose, mencakup penanganan Unicode dan metadata makro.
og_image_alt: Screenshot of a PDF417 barcode containing special characters generated
  with Aspose
og_title: Barcode dengan Karakter Khusus – Hasilkan PDF417 dengan Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Barcode with special characters tutorial shows how to generate PDF417
    barcodes with Aspose. Learn step‑by‑step creation and handling of Unicode data.
  headline: Barcode with Special Characters – Complete Guide to Generating PDF417
    Using Aspose
  type: TechArticle
- description: Barcode with special characters tutorial shows how to generate PDF417
    barcodes with Aspose. Learn step‑by‑step creation and handling of Unicode data.
  name: Barcode with Special Characters – Complete Guide to Generating PDF417 Using
    Aspose
  steps:
  - name: Expected Output
    text: If you open the PNG, you’ll see a rectangular barcode with a series of black
      and white bars. Scanning it with a PDF417‑compatible scanner (or a mobile app
      like “Barcode Scanner”) will return the exact text `"Åspóse.Barcóde©"` along
      with the macro metadata we set. In other words, the barcode faithful
  - name: What if my text contains emojis or non‑BMP characters?
    text: Aspose.BarCode supports full UTF‑16, so emojis work as long as the target
      scanner can decode them. Just pass the string directly; the library handles
      the encoding internally.
  - name: Do I need to set a specific character set?
    text: No. Unlike older barcode SDKs that required `CodePage` settings, Aspose
      automatically detects Unicode. However, if you target a legacy device that only
      understands ASCII, you’ll need to strip or replace special characters before
      generation.
  - name: How does this differ from a regular PDF417 barcode?
    text: The `MacroPdf417` variant adds extra fields (file ID, segment count, etc.)
      that help split large payloads across multiple barcodes. If you don’t need those,
      you can switch `EncodeTypes.Pdf417` and drop the macro‑specific properties.
  - name: Can I generate the barcode as a vector (SVG) instead of PNG?
    text: 'Absolutely. Change the `BarCodeImageFormat` to `Svg`:'
  type: HowTo
tags:
- barcode
- Aspose
- PDF417
- .NET
title: Barcode dengan Karakter Khusus – Panduan Lengkap Membuat PDF417 Menggunakan
  Aspose
url: /id/net/compact-pdf417-encoding/barcode-with-special-characters-complete-guide-to-generating/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode dengan Karakter Khusus – Panduan Lengkap untuk Menghasilkan PDF417 Menggunakan Aspose

Pernah bertanya-tanya bagaimana cara membuat **barcode dengan karakter khusus** yang mencakup aksen, simbol, atau bahkan tanda hak cipta? Anda tidak sendirian. Banyak pengembang menemui kesulitan ketika data mereka berisi karakter seperti “Å”, “é”, atau “©”, dan contoh standar jarang menunjukkan cara menanganinya. Dalam tutorial ini kami akan membahas contoh konkret yang tidak hanya menyelesaikan masalah tersebut tetapi juga mendemonstrasikan **cara menghasilkan PDF417** barcode menggunakan pustaka Aspose.BarCode.

Kami akan memulai dengan menyiapkan aplikasi console .NET sederhana, lalu menyelami kode yang menghasilkan barcode PDF417 yang berisi string `"Åspóse.Barcóde©"`. Sepanjang proses Anda akan melihat mengapa setiap pengaturan penting, cara mengonfigurasi metadata macro‑PDF417, dan hal-hal yang perlu diwaspadai saat menangani Unicode. Pada akhir tutorial Anda akan siap **membuat barcode dengan Aspose** dalam proyek apa pun, baik untuk inventaris, tiket, atau pelacakan dokumen aman.

## Prasyarat

- .NET 6.0 SDK atau yang lebih baru (kode ini juga berfungsi dengan .NET Framework 4.7+)
- Visual Studio 2022 (atau IDE apa pun yang Anda sukai)
- Lisensi Aspose.BarCode untuk .NET yang valid (Anda dapat memulai dengan percobaan gratis)
- Familiaritas dasar dengan sintaks C#

Jika ada yang terdengar tidak familiar, jangan panik—cukup instal .NET SDK dan dapatkan paket NuGet `Aspose.BarCode` dan Anda siap melanjutkan.

## Langkah 1: Instal Aspose.BarCode dan Siapkan Proyek

Untuk menghasilkan **barcode dengan karakter khusus**, hal pertama yang Anda perlukan adalah pustaka Aspose.BarCode. Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Ini akan mengunduh versi terbaru (per Juli 2026, versi 23.12) yang mendukung penanganan Unicode penuh secara langsung. Setelah paket dipulihkan, buat file C# baru bernama `Program.cs` dan tambahkan direktif `using` biasa:

```csharp
using System;
using Aspose.BarCode.Generation;
```

Mengapa `using Aspose.BarCode.Generation`? Direktif ini memberi kita akses ke kelas `BarcodeGenerator`, inti dari **cara menghasilkan PDF417** barcode dengan Aspose.

## Langkah 2: Inisialisasi Barcode Generator dengan Teks Unicode

Sekarang tiba bagian yang benar‑benar membuat **barcode dengan karakter khusus**. Perhatikan string yang kami berikan ke konstruktor berisi “Å”, “ó”, dan “©”. Aspose secara otomatis mendeteksi rentang Unicode, sehingga Anda tidak memerlukan langkah encoding tambahan—cukup berikan string .NET biasa:

```csharp
// Step 2: Create a barcode generator for Macro PDF417 with Unicode text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

`EncodeTypes.MacroPdf417` memberi tahu Aspose bahwa kami menginginkan barcode PDF417 yang dapat membawa informasi macro (berguna untuk membagi payload besar). Generator kini menyimpan **barcode dengan karakter khusus** yang siap untuk penyesuaian lebih lanjut.

## Langkah 3: Sesuaikan Penampilan dan Metadata Macro

Barcode sederhana berfungsi, tetapi kebanyakan skenario dunia nyata memerlukan kontrol atas ukuran, jumlah kolom, dan bidang macro. Di bawah ini kami menyesuaikan dimensi X, jumlah kolom, dan kemudian mengatur beberapa properti macro‑PDF417. Setiap baris diberi komentar sehingga Anda dapat melihat *mengapa* itu penting.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel size of a module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns (affects width)

    // Define macro PDF417 metadata (file ID, segment info, etc.)
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Tip cepat: jika barcode yang dihasilkan terlalu lebar, turunkan nilai `Columns` atau tingkatkan `XDimension`. Kedua parameter memengaruhi ukuran gambar akhir, yang penting saat menyematkan barcode dalam PDF atau label cetak.

## Langkah 4: Simpan Barcode sebagai Gambar

Akhirnya, kami menyimpan barcode ke file PNG. Metode `Save` secara otomatis merender **barcode dengan karakter khusus** ke format raster yang dapat Anda tampilkan di situs web, sematkan dalam laporan, atau kirim ke printer.

```csharp
    // Save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Ganti `YOUR_DIRECTORY` dengan jalur absolut atau relatif yang ada di mesin Anda. Setelah program selesai, Anda akan melihat `ExtPDF417Meta.png` yang berisi barcode PDF417 tajam yang mengkodekan string Unicode.

### Output yang Diharapkan

Jika Anda membuka PNG, Anda akan melihat barcode berbentuk persegi panjang dengan serangkaian bar hitam dan putih. Memindainya dengan pemindai yang kompatibel dengan PDF417 (atau aplikasi seluler seperti “Barcode Scanner”) akan mengembalikan teks tepat `"Åspóse.Barcóde©"` beserta metadata macro yang kami atur. Dengan kata lain, barcode dengan setia mempertahankan karakter khusus—tanpa kehilangan data.

## Pertanyaan Umum & Kasus Tepi

### Bagaimana jika teks saya mengandung emoji atau karakter non‑BMP?

Aspose.BarCode mendukung UTF‑16 penuh, sehingga emoji berfungsi selama pemindai target dapat mendekodenya. Cukup berikan string secara langsung; pustaka menangani encoding secara internal.

### Apakah saya perlu mengatur set karakter tertentu?

Tidak. Berbeda dengan SDK barcode lama yang memerlukan pengaturan `CodePage`, Aspose secara otomatis mendeteksi Unicode. Namun, jika Anda menargetkan perangkat lama yang hanya memahami ASCII, Anda harus menghapus atau mengganti karakter khusus sebelum menghasilkan barcode.

### Bagaimana ini berbeda dari barcode PDF417 biasa?

Varian `MacroPdf417` menambahkan bidang ekstra (ID file, jumlah segmen, dll.) yang membantu membagi payload besar ke beberapa barcode. Jika Anda tidak memerlukannya, Anda dapat beralih ke `EncodeTypes.Pdf417` dan menghapus properti khusus macro.

### Bisakah saya menghasilkan barcode sebagai vektor (SVG) alih-alih PNG?

Tentu saja. Ubah `BarCodeImageFormat` menjadi `Svg`:

```csharp
barcodeGenerator.Save("ExtPDF417Meta.svg", BarCodeImageFormat.Svg);
```

Output vektor dapat diskalakan tanpa kehilangan kualitas—berguna untuk pencetakan resolusi tinggi.

## Contoh Lengkap yang Berfungsi

Berikut adalah program lengkap yang siap dijalankan. Salin‑tempel ke `Program.cs`, sesuaikan jalur output, dan tekan **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeSpecialCharsDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel size of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns

                // Step 3: Define macro PDF417 metadata (file ID, segment info, etc.)
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode as a PNG image
                barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Barcode with special characters generated successfully!");
        }
    }
}
```

Menjalankan program ini akan mencetak baris konfirmasi dan menempatkan `ExtPDF417Meta.png` di folder executable. Buka file tersebut, pindai, dan verifikasi bahwa karakter khusus tetap utuh setelah proses round‑trip.

## Tips Pro untuk Penggunaan Produksi

- **Cache generator** jika Anda membuat banyak barcode dalam loop; menggunakan kembali instance `BarcodeGenerator` yang sama mengurangi beban memori.
- **Set `Resolution`** (`barcodeGenerator.Parameters.ImageResolution`) ketika Anda memerlukan DPI lebih tinggi untuk aset siap cetak.
- **Validate input**: hapus karakter kontrol yang dapat merusak bidang macro. Regex sederhana seperti `^[\u0020-\u007E\u00A0-\u00FF]+$` berfungsi untuk kebanyakan kasus penggunaan Latin‑1.
- **Thread safety**: setiap thread harus memiliki `BarcodeGenerator` masing‑masing. Kelas ini tidak thread‑safe.

## Kesimpulan

Anda kini memiliki resep lengkap, end‑to‑end untuk membuat **barcode dengan karakter khusus** menggunakan Aspose, dan Anda juga telah melihat **cara menghasilkan PDF417** barcode yang membawa metadata macro. Contoh ini mencakup semua hal mulai dari menginstal paket NuGet hingga menyimpan PNG akhir, serta menyoroti jebakan umum seperti penanganan Unicode dan pengaturan ukuran gambar.

Siap untuk langkah selanjutnya? Coba ganti format gambar ke SVG, bereksperimen dengan payload yang lebih besar

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Mengenali Barcode PDF417 dengan Karakter Cina dalam Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)
- [Mengenali Barcode PDF417 dengan Karakter Turki dalam Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}