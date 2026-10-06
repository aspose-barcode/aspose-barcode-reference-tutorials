---
category: general
date: 2026-09-07
description: Buat kode batang PDF417 dalam C# dan pelajari cara mengatur dimensi kode
  batang untuk kontrol yang tepat. Ikuti panduan langkah demi langkah ini untuk membuat
  gambar PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: id
lastmod: 2026-09-07
og_description: Buat kode batang PDF417 di C# dan pelajari cara mengatur dimensi kode
  batang. Tutorial ini menampilkan contoh lengkap yang dapat dijalankan.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: Buat kode batang PDF417 di C# – panduan lengkap dengan dimensi
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: Cara menghasilkan barcode PDF417 di C# dengan dimensi khusus
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode PDF417 di C# dengan dimensi khusus

Jika Anda perlu **menghasilkan barcode PDF417** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara melakukannya. Anda akan melihat contoh lengkap yang dapat dijalankan yang membuat gambar PNG sambil memungkinkan Anda mengontrol dimensi barcode.

Menghasilkan barcode PDF417 adalah kebutuhan umum untuk sistem inventaris, boarding pass, dan dokumen aman. Dalam tutorial ini Anda juga akan belajar **cara mengatur dimensi barcode** sehingga outputnya sesuai dengan kebutuhan tata letak Anda.

## Prasyarat

- .NET 6.0 SDK atau yang lebih baru terinstal  
- Visual Studio 2022 (atau IDE kompatibel C# apa pun)  
- Paket NuGet **Aspose.BarCode for .NET** (atau perpustakaan kompatibel lain yang mendukung PDF417)  

Anda dapat menambahkan paket dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Buat generator barcode PDF417

Langkah pertama adalah menginstansiasi `BarcodeGenerator` dengan tipe `EncodeTypes.Pdf417` dan teks yang ingin Anda enkode. Objek generator menyimpan semua pengaturan untuk barcode.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**Mengapa ini penting:** Enum `EncodeTypes.Pdf417` memberi tahu perpustakaan untuk menggunakan simbol PDF417, yang mendukung muatan data besar dan koreksi kesalahan. String teks dapat berisi karakter Unicode, sehingga Anda dapat mengenkode simbol internasional tanpa pekerjaan tambahan.

## Langkah 2: Cara mengatur dimensi barcode

Mengontrol ukuran setiap modul (kotak hitam/putih terkecil) menentukan resolusi gambar secara keseluruhan. Properti `XDimension.Pixels` mengatur lebar piksel satu modul.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Mengapa ini penting:** `XDimension` yang lebih besar menghasilkan gambar dengan resolusi lebih tinggi, yang berguna untuk pencetakan atau pemindaian dari jarak jauh. Sebaliknya, nilai yang lebih kecil mengurangi ukuran file untuk penggunaan web.

## Langkah 3: Tentukan tata letak PDF417 (kolom dan baris)

PDF417 memungkinkan Anda memengaruhi bentuk matriks dengan menentukan jumlah kolom dan baris. Hal ini dapat memengaruhi keterbacaan dan ukuran fisik barcode.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**Mengapa ini penting:** Menyesuaikan kolom dan baris memungkinkan Anda menempatkan barcode dalam ruang tertentu atau memenuhi persyaratan rasio aspek pemindai. Perpustakaan secara otomatis menambahkan padding jika data tidak mengisi matriks sepenuhnya.

## Langkah 4: Simpan barcode sebagai gambar PNG

Akhirnya, tulis barcode yang dihasilkan ke sebuah file. PNG mempertahankan kualitas lossless, menjadikannya ideal untuk pemrosesan lebih lanjut.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

Saat Anda menjalankan program, `Pdf417Layout.png` muncul di folder output proyek. Gambar tersebut terlihat seperti ini:

![Gambar barcode PDF417 yang dihasilkan dengan dimensi khusus](og_image_placeholder.png)

*Gambar alt: Gambar barcode PDF417 yang dihasilkan dengan dimensi khusus*  

**Mengapa ini penting:** Menyimpan sebagai PNG memastikan bahwa dimensi modul tepat yang Anda atur tetap dipertahankan, yang penting untuk aplikasi pemindaian selanjutnya.

## Contoh lengkap dalam satu blok

Berikut adalah program lengkap yang dapat Anda salin, tempel, dan jalankan tanpa modifikasi (kecuali jalur output jika diinginkan).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### Output yang diharapkan

- **Berkas:** `Pdf417Layout.png` (PNG, lossless)  
- **Dimensi:** Ditentukan oleh `XDimension` (2 px) × (kolom × baris) matriks  
- **Konten:** Barcode PDF417 yang dapat dipindai yang mengenkode string Unicode `Åspóse.Barcóde©`

## Pertanyaan umum dan kasus tepi

### Bagaimana jika saya membutuhkan gambar yang lebih besar untuk pencetakan?

Tingkatkan `XDimension.Pixels` menjadi 4 atau 5. Nilai yang lebih besar menghasilkan barcode dengan resolusi lebih tinggi tetapi juga meningkatkan ukuran file.

### Bisakah saya mengenkode lebih banyak data daripada string contoh?

Ya. PDF417 dapat menampung hingga 1.850 karakter. Cukup ganti argumen teks dalam konstruktor `BarcodeGenerator`. Jika data melebihi kapasitas matriks, perpustakaan secara otomatis menambahkan baris tambahan.

### Bagaimana cara kerja koreksi kesalahan?

PDF417 menyertakan koreksi kesalahan bawaan. Anda dapat menyesuaikan levelnya melalui:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

Level yang lebih tinggi meningkatkan ketahanan dengan biaya barcode yang lebih besar.

### Bagaimana jika barcode terlihat buram di layar?

Pastikan DPI gambar output cocok dengan lingkungan tampilan. Anda dapat mengatur DPI saat menyimpan:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## Tips profesional

- **Tips pro:** Selalu uji barcode yang dihasilkan dengan pemindai sebenarnya yang akan Anda gunakan. Berbagai perangkat memiliki toleransi yang berbeda untuk ukuran modul dan zona tenang.  
- **Waspadai:** Nilai `XDimension` yang sangat kecil (< 1 px) dapat terrender sebagai garis tak terlihat pada layar ber‑DPI tinggi.  
- **Tips untuk aplikasi web:** Sajikan PNG dengan `Cache-Control: public, max-age=86400` untuk mengurangi beban pembuatan berulang.

## Kesimpulan

Anda sekarang tahu cara **menghasilkan barcode PDF417** di C# dan secara tepat **mengatur dimensi barcode** untuk memenuhi setiap kebutuhan. Contoh lengkap yang dapat dijalankan menunjukkan cara membuat gambar PNG dengan tata letak kolom/baris khusus dan ukuran modul, siap untuk pencetakan atau distribusi digital.

### Langkah selanjutnya

- Jelajahi **cara menghasilkan barcode PDF417** dengan format gambar berbeda (JPEG, BMP).  
- Pelajari **cara mengatur dimensi barcode** secara dinamis berdasarkan input pengguna atau DPI perangkat.  
- Integrasikan pembuatan barcode ke dalam API ASP.NET Core untuk menyajikan barcode sesuai permintaan.

Silakan bereksperimen dengan pengaturan PDF417 lainnya seperti koreksi kesalahan, margin, dan warna. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Mengatur Tingkat Kesalahan pada Barcode PDF417 – Panduan Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Cara Menyimpan Barcode di C# – Menghasilkan Barcode PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Menghasilkan Barcode PDF417 di C# – Panduan Lengkap](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}