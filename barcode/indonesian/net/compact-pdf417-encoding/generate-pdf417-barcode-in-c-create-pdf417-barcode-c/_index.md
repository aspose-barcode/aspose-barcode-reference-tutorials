---
category: general
date: 2026-07-24
description: Hasilkan kode batang PDF417 dalam C# menggunakan Aspose.BarCode. Pelajari
  cara membuat kode batang PDF417 C# dengan mode kompak dalam hitungan menit.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: id
lastmod: 2026-07-24
og_description: Hasilkan barcode PDF417 di C# dengan cepat menggunakan Aspose.BarCode.
  Tutorial ini menunjukkan cara membuat barcode PDF417 C# dalam mode kompak, mencakup
  pengaturan, kode, dan verifikasi.
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: Buat Kode Bar PDF417 di C# – Panduan Cepat
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Hasilkan Kode Barcode PDF417 di C# – Buat Kode Barcode PDF417 C#
url: /id/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan Barcode PDF417 di C# – Panduan Pemrograman Lengkap

Pernah bertanya-tanya bagaimana cara **menghasilkan barcode PDF417** dalam aplikasi C# tanpa harus mencari‑cari di forum yang tak berujung? Anda bukan satu‑satunya. Baik Anda sedang membangun sistem tiket, kartu identitas yang aman, atau hanya membutuhkan cara cepat untuk menyematkan data dalam format yang dapat dicetak, menguasai format PDF417 dapat menghemat Anda berjam‑jam percobaan‑dan‑kesalahan.

Dalam panduan ini kami akan membahas **contoh lengkap yang siap dijalankan** yang menunjukkan secara tepat cara **membuat barcode PDF417 dengan C#** menggunakan pustaka populer Aspose.BarCode. Kami akan membahas semua hal mulai dari menginstal paket NuGet hingga menyesuaikan mode kompak, sehingga Anda dapat menyalin‑tempel kode dan melihat hasilnya secara langsung.

## Apa yang Akan Anda Pelajari

- Cara menyiapkan pustaka Aspose.BarCode dalam proyek .NET.  
- Pernyataan C# yang tepat untuk **menghasilkan barcode PDF417** dengan teks khusus, ukuran modul, dan jumlah kolom.  
- Mengapa mengaktifkan opsi *Compact* (Truncate) penting untuk data yang padat.  
- Cara menyimpan barcode sebagai PNG dan memverifikasi hasilnya.  

Tidak diperlukan pengalaman barcode sebelumnya; cukup pemahaman dasar tentang C# dan Visual Studio (atau IDE apa pun yang Anda sukai). Pada akhir panduan Anda akan memiliki metode yang dapat digunakan kembali dan dapat dimasukkan ke dalam proyek apa pun yang membutuhkan gambar PDF417.

## Prasyarat

| Persyaratan | Mengapa penting |
|-------------|-----------------|
| .NET 6.0 atau lebih baru (atau .NET Framework 4.7+) | Aspose.BarCode mendukung keduanya; runtime yang lebih baru memberikan kinerja yang lebih baik. |
| Visual Studio 2022 (atau VS Code dengan ekstensi C#) | Menyediakan IntelliSense dan debugging yang mudah. |
| Koneksi internet (untuk pemulihan NuGet pertama) | Pustaka diunduh dari NuGet.org. |
| Pengetahuan dasar C# | Diperlukan untuk memahami struktur kelas dan pemanggilan metode. |

Jika Anda sudah memiliki semua itu, bagus—mari kita mulai.

## Instal Paket NuGet Aspose.BarCode

Buka folder proyek Anda di terminal dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Atau, di dalam Visual Studio, klik kanan **Dependencies → Manage NuGet Packages**, cari *Aspose.BarCode*, dan klik **Install**. Baris tunggal ini akan menambahkan semua tipe yang akan kami gunakan, termasuk `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat`.

> **Tips pro:** Setelah instalasi, bersihkan dan bangun kembali solusi untuk memastikan assembly direferensikan dengan benar.

## Menghasilkan Barcode PDF417 – Penyiapan dan Dependensi

Hal pertama yang harus dilakukan: kita memerlukan blok `using` yang memasukkan namespace yang relevan ke dalam ruang lingkup.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Namespace ini memberi kami akses ke kelas generator dan enumerasi tipe barcode. Tidak ada yang rumit—hanya tiga baris, dan kami siap mulai membuat barcode.

## Membuat Barcode PDF417 C# – Implementasi Langkah‑per‑Langkah

Berikut adalah **program konsol mandiri** yang membuat barcode PDF417 kompak dari string `"Åspóse.Barcóde©"` dan menyimpannya sebagai `CompactPdf417.png`. Silakan ganti teks dengan apa pun yang Anda butuhkan; generator akan menangani karakter Unicode secara otomatis.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Mengapa Setiap Langkah Penting

1. **Definisi data** – PDF417 dapat menyimpan hingga ~1850 karakter, tetapi kami membuatnya singkat untuk demo. Dukungan Unicode berarti karakter aksen tidak akan menyebabkan masalah.  
2. **Konstruksi generator** – Nilai enum `EncodeTypes.Pdf417` memberi tahu Aspose simbol apa yang akan digunakan; menggantinya dengan `EncodeTypes.QR` akan menghasilkan kode QR sebagai gantinya.  
3. **X‑dimension** – Ini mengontrol lebar setiap modul (kotak kecil yang membentuk barcode). Nilai `2` piksel menghasilkan gambar yang tajam dan tetap dapat dibaca saat dicetak pada 300 dpi.  
4. **Opsi PDF417** – `Columns` memengaruhi rasio aspek barcode; lebih sedikit kolom membuat gambar lebih tinggi, yang dapat berguna untuk struk. `Truncate` (juga disebut *mode Kompak*) menghapus padding pola start/stop, mengurangi ukuran file tanpa mengorbankan integritas data.  
5. **Path output** – Menggunakan `Environment.CurrentDirectory` memastikan gambar berada di samping executable, memudahkan pencarian selama pengembangan.  
6. **Penyimpanan** – `BarCodeImageFormat.Png` memberikan kualitas lossless, sempurna untuk pemrosesan lebih lanjut atau penyematan dalam PDF.

Jalankan program (`dotnet run` atau tekan **F5** di Visual Studio). Setelah beberapa detik Anda akan melihat pesan konsol yang mengonfirmasi lokasi file, dan PNG akan muncul di folder proyek Anda.

![Contoh barcode PDF417](generated-pdf417.png)

*Teks alt gambar: contoh barcode pdf417 – gambar PNG dari barcode PDF417 kompak yang dibuat dengan C#.*

## Mengonfigurasi Mode Kompak – Opsi generator barcode pdf417 c#

Jika Anda membutuhkan barcode yang lebih besar (mungkin untuk pemindaian dari jarak jauh), sesuaikan properti `Columns` dan `Rows`. Berikut cuplikan singkat yang menunjukkan konfigurasi alternatif:

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **Pertanyaan umum:** *Apakah menonaktifkan Truncate akan merusak pemindai yang ada?*  
> Biasanya tidak. Sebagian besar pemindai modern memahami PDF417 ukuran penuh maupun kompak. Namun, jika Anda menargetkan perangkat keras lama, biarkan `Truncate` tetap `false`.

## Simpan dan Verifikasi – cara menghasilkan Output barcode pdf417

Setelah disimpan, Anda dapat membuka PNG dengan penampil gambar apa pun. Untuk memeriksa kembali bahwa barcode mengkodekan data yang dimaksud, gunakan `BarCodeReader` milik Aspose:



## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑per‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Pustaka barcode java – Menambahkan barcode ke PDF menggunakan Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}