---
category: general
date: 2026-08-06
description: Cara mengatur barcode menggunakan Aspose.BarCode di C#. Pelajari cara
  mengubah karakter makro dan membuat gambar barcode C# dengan kode langkah demi langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- how to change macro
- barcode generator c#
- create barcode image c#
language: id
lastmod: 2026-08-06
og_description: Cara mengatur barcode dengan Aspose.BarCode di C#. Panduan ini menunjukkan
  cara mengubah karakter makro dan membuat gambar barcode C# dengan cepat.
og_image_alt: Screenshot of a MicroPDF417 barcode generated with C# code
og_title: Cara mengatur barcode di C# – Tutorial Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: How to set barcode using Aspose.BarCode in C#. Learn how to change
    macro characters and create barcode image C# with step‑by‑step code.
  headline: How to set barcode in C# – complete Aspose.BarCode guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara mengatur barcode di C# – panduan lengkap Aspose.BarCode
url: /id/net/one-dimensional-barcode-types/how-to-set-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengatur barcode di C# – panduan lengkap Aspose.BarCode

Jika Anda perlu **cara mengatur barcode** dalam aplikasi .NET, tutorial ini menunjukkan langkah‑langkah tepat menggunakan Aspose.BarCode. Anda akan melihat cara mengubah karakter makro, menyesuaikan parameter visual, dan **membuat file gambar barcode C#** yang dapat disimpan langsung ke disk.

Panduan ini mencakup semua hal mulai dari menginstal pustaka hingga menghasilkan dua barcode MicroPDF417 dengan nilai makro yang berbeda. Tidak diperlukan dokumentasi eksternal—Anda dapat menyalin kode, menjalankannya, dan memverifikasi output PNG secara langsung.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 atau lebih baru (contoh menggunakan proyek konsol)
* Visual Studio 2022 atau IDE C# apa pun
* Lisensi Aspose.BarCode yang aktif (evaluasi gratis dapat digunakan untuk pengujian)
* Pengetahuan dasar tentang sintaks C#

Anda juga memerlukan paket NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Cara mengatur parameter barcode – langkah 1: buat generator

Tindakan pertama adalah menginstansiasi `BarcodeGenerator` dengan simbol dan data yang diinginkan. Menggunakan `EncodeTypes.MicroPdf417` memberi tahu Aspose.BarCode untuk menghasilkan varian PDF417 yang kompak.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Step 1: Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417, // symbology
                "12345ABC");             // data to encode
```

**Mengapa ini penting:** `BarcodeGenerator` adalah objek pusat; semua pengaturan selanjutnya memodifikasi properti `Parameters`‑nya. Memilih `EncodeTypes` yang tepat memastikan barcode mengikuti spesifikasi MicroPDF417.

## Cara mengubah karakter makro – langkah 2: sesuaikan parameter visual

Karakter makro adalah kode kontrol opsional yang memungkinkan Anda menggabungkan beberapa simbol PDF417. Contoh ini beralih antara `Macro05` dan `Macro06`. Anda juga mengatur lebar modul (`XDimension`) dan jumlah kolom untuk mengontrol ukuran barcode.

```csharp
            // Step 2: Adjust visual parameters – set the X‑dimension (module width) and number of columns
            generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width in pixels
            generator.Parameters.Barcode.Pdf417.Columns = 4;           // number of data columns

            // Encode the first macro character (Macro05) and save the image
            generator.Parameters.Barcode.Pdf417.MacroCharacters = MacroCharacter.Macro05;
            generator.Save("MicroPdf417_Macro05.png", BarCodeImageFormat.Png);
```

**Mengapa Anda mengubah makro:** Karakter makro memberi tahu pemindai bahwa barcode ini merupakan bagian dari kumpulan data yang lebih besar. Mengubahnya menunjukkan bagaimana data yang sama dapat dihubungkan ke identifier makro yang berbeda.

## Cara mengatur barcode – langkah 3: hasilkan barcode kedua dengan makro yang berbeda

Sekarang kita menggunakan kembali instance `generator` yang sama, hanya mengganti nilai makro. Ini menghindari pembuatan ulang objek dan menunjukkan bahwa **cara mengatur barcode** dapat dilakukan pada saat runtime.

```csharp
            // Step 3: Switch to the second macro character (Macro06) and save the new image
            generator.Parameters.Barcode.Pdf417.MacroCharacters = MacroCharacter.Macro06;
            generator.Save("MicroPdf417_Macro06.png", BarCodeImageFormat.Png);
        }
    }
}
```

### Output yang diharapkan

Menjalankan program akan membuat dua file PNG di folder proyek:

* `MicroPdf417_Macro05.png` – barcode dengan Macro05
* `MicroPdf417_Macro06.png` – barcode dengan Macro06

Kedua gambar menampilkan simbol MicroPDF417 yang kompak yang mengenkode `12345ABC`. Anda dapat membuka file PNG dengan penampil gambar apa pun untuk memverifikasi kualitas visual.

## Praktik terbaik generator barcode C#

* **Gunakan kembali generator:** Mengubah `Parameters` pada instance yang ada lebih efisien daripada membuat generator baru untuk setiap barcode.
* **Atur X‑dimension lebih awal:** Lebar modul memengaruhi ukuran gambar keseluruhan; sesuaikan sebelum menyimpan.
* **Validasi penggunaan makro:** Tidak semua pemindai mendukung karakter makro. Uji dengan perangkat keras target Anda jika berencana menggunakannya dalam produksi.
* **Bebaskan sumber daya:** `BarcodeGenerator` mengimplementasikan `IDisposable`. Pada layanan yang berjalan lama, bungkus dalam blok `using` atau panggil `Dispose()` setelah selesai.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "12345ABC"))
{
    // configure parameters...
}
```

## Membuat gambar barcode C# – tips pemecahan masalah

| Gejala                               | Penyebab kemungkinan                     | Perbaikan |
|--------------------------------------|------------------------------------------|-----------|
| File PNG kosong                      | `XDimension` diatur ke 0 atau nilai sangat tinggi | Gunakan lebar piksel yang wajar (1‑5) |
| Barcode tidak dapat dibaca pemindai | Karakter makro salah untuk pemindai      | Verifikasi dokumentasi pemindai; gunakan `MacroNone` jika tidak diperlukan |
| Exception `ArgumentOutOfRangeException` | Jumlah kolom di luar rentang yang diizinkan (1‑30) | Pertahankan `Columns` antara 1 dan 30 |

## Kesimpulan

Anda sekarang mengetahui **cara mengatur properti barcode**, **cara mengubah karakter makro**, dan cara **membuat file gambar barcode C#** menggunakan Aspose.BarCode. Contoh lengkap yang dapat dijalankan menunjukkan alur kerja penuh mulai dari pembuatan generator hingga ekspor gambar.

Selanjutnya, jelajahi simbol lain (`EncodeTypes.QR`, `EncodeTypes.Code128`) atau sematkan barcode langsung ke PDF dengan Aspose.PDF. Kedua topik berada dalam ekosistem **barcode generator c#** yang lebih luas dan dapat ditambahkan ke proyek ini dengan perubahan kode minimal.

Selamat coding, dan silakan bereksperimen dengan nilai makro, dimensi, dan format output yang berbeda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membuat zona tenang barcode untuk Code 16K menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Cara membuat teks kode dotcode yang diperluas dengan Aspose.BarCode untuk .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Cara Mengatur Border untuk Kustomisasi Barcode ITF-14](/barcode/english/net/itf-14-barcode-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}