---
category: general
date: 2026-09-29
description: Panduan generator barcode C# menunjukkan cara menghasilkan barcode MicroPdf417,
  mengubah dimensi, mengatur kolom, dan menyesuaikan ukuran barcode hanya dalam beberapa
  baris.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: id
lastmod: 2026-09-29
og_description: Panduan generator barcode C# menunjukkan cara menghasilkan barcode
  MicroPdf417, mengubah dimensi, mengatur kolom, dan menyesuaikan ukuran barcode hanya
  dalam beberapa baris.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: Panduan generator barcode C# – buat dan sesuaikan MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'Panduan generator barcode C#: membuat MicroPdf417'
url: /id/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Panduan generator barcode C#: buat MicroPdf417

Jika Anda membutuhkan **barcode generator C#** untuk proyek .NET Anda, tutorial ini akan memandu Anda membuat barcode MicroPdf417 dari awal. Anda akan belajar **cara menghasilkan barcode**, mengubah dimensi, mengatur kolom, dan **menyesuaikan ukuran barcode** dengan mudah.

MicroPdf417 adalah simbolologi 2‑D yang kompak dan cocok untuk memberi label pada bagian kecil, tiket, atau tag inventaris. Pada akhir panduan ini Anda akan memiliki aplikasi konsol lengkap yang dapat dijalankan yang menghasilkan gambar PNG dari barcode, dan Anda akan memahami bagaimana setiap parameter memengaruhi ukuran akhir.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru (kode juga berfungsi dengan .NET Framework 4.7+)
* IDE yang kompatibel dengan C# (Visual Studio, VS Code, Rider, dll.)
* Paket NuGet **GroupDocs.Barcode** – instal dengan  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

Tidak diperlukan alat eksternal tambahan; pustaka menangani encoding, rendering, dan penyimpanan file.

## Barcode generator C#: menginisialisasi generator

Langkah pertama adalah membuat instance `BarcodeGenerator` dan menentukan simbolologi (`EncodeTypes.MicroPdf417`) bersama dengan data yang ingin Anda enkode.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**Mengapa ini penting:**  
`BarcodeGenerator` adalah titik masuk untuk semua operasi barcode. Konstruktor mengikat **EncodeTypes** yang dipilih (MicroPdf417) ke string data mentah. Pustaka secara otomatis menangani karakter Unicode seperti “Å” dan “©”, sehingga Anda tidak memerlukan logika enkoding tambahan.

## Cara mengubah dimensi barcode

Keterbacaan barcode sangat bergantung pada lebar modul (dimensi X). Mengaturnya ke jumlah piksel yang lebih besar membuat bar menjadi lebih lebar dan gambar lebih mudah dipindai, terutama pada tampilan beresolusi rendah.

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Penjelasan:**  
`XDimension.Pixels` mengontrol lebar satu modul barcode. Defaultnya adalah 1 pixel, yang dapat terlihat tipis pada monitor ber‑DPI tinggi. Meningkatkannya menjadi 2 pixel menggandakan lebar keseluruhan tanpa memengaruhi data yang dienkode.

**Tip:** Jika Anda berencana mencetak barcode pada 300 dpi, nilai 3 atau 4 pixel sering memberikan keseimbangan terbaik antara ukuran dan keandalan pemindaian.

## Cara mengatur kolom untuk kontrol ukuran

MicroPdf417 memungkinkan Anda menentukan jumlah kolom (hingga 4). Lebih sedikit kolom menghasilkan barcode yang lebih tinggi; lebih banyak kolom membuatnya lebih lebar tetapi lebih pendek. Menyesuaikan nilai ini adalah cara utama untuk **menyesuaikan ukuran barcode**.

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Mengapa ini berhasil:**  
Properti `Pdf417.Columns` dibagikan di semua simbolologi berbasis PDF417, termasuk MicroPdf417. Mengaturnya ke nilai maksimum (4) menyebarkan data ke tata letak seluas mungkin, mengurangi tinggi keseluruhan. Jika Anda membutuhkan tinggi yang lebih kompak, turunkan jumlah kolom menjadi 2 atau 3.

**Kasus tepi:** Ketika string data panjang, pustaka dapat secara otomatis menambah baris untuk menampung konten, terlepas dari jumlah kolom. Jaga payload di bawah 50 karakter untuk ukuran yang dapat diprediksi.

## Sesuaikan ukuran barcode untuk output yang berbeda

Selain dimensi X dan kolom, Anda dapat memengaruhi ukuran gambar akhir dengan memilih format gambar dan DPI yang sesuai. PNG bersifat lossless, sempurna untuk tampilan web, sementara BMP atau TIFF mungkin lebih disukai untuk pencetakan berkualitas tinggi.

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Jika Anda membutuhkan DPI yang lebih tinggi, Anda dapat mengaturnya secara eksplisit:

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**Hasil:** File PNG yang disimpan berisi barcode MicroPdf417 yang tajam dan menghormati dimensi yang Anda konfigurasikan. Buka file tersebut di penampil gambar apa pun untuk memverifikasi ukuran visual.

### Output yang diharapkan

Menjalankan program menghasilkan file bernama **MicroPdf417.png** (atau **MicroPdf417_300dpi.png** jika Anda mengatur DPI). Barcode akan terlihat serupa dengan ilustrasi di bawah:

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*Alt text:* *Output generator barcode C# menampilkan PNG MicroPdf417*

Memindai gambar dengan pembaca barcode 2‑D standar mengembalikan string asli `Åspóse.Barcóde©`.

## Kode sumber lengkap untuk salin‑tempel cepat

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

Salin kode ke dalam proyek konsol baru, pulihkan paket NuGet, dan jalankan `dotnet run`. Konsol akan mengonfirmasi lokasi gambar, dan Anda akan melihat barcode yang dihasilkan di folder proyek Anda.

## Pertanyaan umum dan pemecahan masalah

| Pertanyaan | Jawaban |
|------------|---------|
| **Bagaimana jika barcode terlihat buram?** | Tingkatkan `XDimension.Pixels` atau DPI (`Parameters.Image.DpiX/Y`). Keduanya memperbesar modul dan meningkatkan kejelasan visual. |
| **Apakah saya dapat menggunakan format gambar lain?** | Ya. Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Tiff`. PNG tetap pilihan paling aman untuk kualitas lossless. |
| **Data saya mengandung emoji—apakah akan terenkode?** | MicroPdf417 mendukung UTF‑8, sehingga sebagian besar emoji terenkode dengan benar. Jika Anda menemukan kesalahan, pastikan string telah dinormalisasi dengan benar (`System.Text.Encoding.UTF8`). |
| **Bagaimana cara saya menghasilkan simbolologi lain?** | Ubah `EncodeTypes.MicroPdf417` ke nilai lain apa pun dari `EncodeTypes` ( |

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membuat Gambar Barcode di C# – Panduan MicroPdf417](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [Cara menghasilkan barcode PDF417 di C# dengan dimensi khusus](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}