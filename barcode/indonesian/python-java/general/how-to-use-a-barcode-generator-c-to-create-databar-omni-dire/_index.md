---
category: general
date: 2026-08-22
description: Tutorial generator barcode C# menunjukkan cara menghasilkan file PNG
  barcode, membuat barcode DataBar, dan menyesuaikan tinggi barcode dalam beberapa
  langkah saja.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: id
lastmod: 2026-08-22
og_description: Panduan generator barcode C# membawa Anda melalui cara menghasilkan
  barcode PNG, membuat barcode DataBar, dan menyesuaikan tinggi barcode secara efisien.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: generator barcode C# – buat barcode DataBar dan sesuaikan tinggi
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara menggunakan generator barcode C# untuk membuat barcode DataBar Omni‑directional
url: /id/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menggunakan generator barcode C# untuk membuat barcode DataBar Omni‑directional

Jika Anda membutuhkan **barcode generator C#** yang dapat menghasilkan gambar PNG berkualitas tinggi, panduan ini akan membantu Anda. Anda akan belajar cara **generate barcode PNG**, membuat barcode DataBar Omni‑directional, dan menyesuaikan tinggi barcode tanpa meninggalkan IDE Anda.

Men‑generate barcode secara programatik menghilangkan langkah manual menggunakan editor grafis. Pada akhir tutorial ini Anda akan memiliki dua file PNG—satu dengan tinggi bar 30 pixel dan satu lagi dengan tinggi bar 60 pixel—siap untuk dimasukkan ke faktur, label, atau sistem inventaris.

**Prerequisites**

- .NET 6.0 atau lebih baru (kode juga bekerja dengan .NET Framework 4.7+)
- Referensi ke paket NuGet `Aspose.BarCode` (atau perpustakaan lain yang menyediakan API serupa)
- Familiaritas dasar dengan C# dan Visual Studio atau IDE pilihan Anda

---

## Langkah 1: Siapkan proyek barcode generator C# 

Membuat instance **barcode generator C#** adalah hal pertama yang Anda lakukan. Konstruktor mengambil dua argumen: tipe barcode (`EncodeTypes.DatabarOmniDirectional`) dan payload data. Pada contoh ini payload mengikuti format Identifier Aplikasi GS1 untuk GTIN 14‑digit.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Mengapa ini penting:** Enum `EncodeTypes.DatabarOmniDirectional` memberi tahu perpustakaan untuk merender DataBar yang dapat dibaca dari arah mana pun, yang ideal untuk label ritel kecil.

---

## Langkah 2: Tentukan dimensi modul (X‑dimension)

X‑dimension mengontrol lebar satu modul barcode. Menetapkannya ke 2 pixel menghasilkan gambar yang tajam dan dapat dibaca sambil menjaga ukuran file tetap kecil.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tip:** Jika Anda membutuhkan barcode yang lebih rapat karena ruang terbatas, turunkan nilai menjadi 1 pixel, tetapi uji keterbacaan dengan pemindai.

---

## Langkah 3: Hasilkan PNG pertama dengan tinggi bar 30 pixel

Tinggi bar menentukan seberapa tinggi bar muncul. Tinggi 30 pixel adalah default umum untuk label standar.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

File `DatabarBarHeight30Pixels.png` kini berisi **generate barcode PNG** yang dapat langsung digunakan di halaman web atau dicetak sesuai permintaan.

---

## Langkah 4: Sesuaikan tinggi barcode menjadi 60 pixel dan simpan PNG kedua

Mengubah tinggi bar semudah menetapkan nilai baru ke properti yang sama. Ini menunjukkan kemampuan **adjust barcode height** dari generator.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Sekarang Anda memiliki `DatabarBarHeight60Pixels.png`, yang ideal untuk kemasan lebih besar dimana barcode harus dipindai dari jarak jauh.

**Expected output**

- `DatabarBarHeight30Pixels.png` – barcode DataBar Omni‑directional yang kompak, tinggi 30 px.
- `DatabarBarHeight60Pixels.png` – barcode yang sama, tinggi dua kali lipat untuk visibilitas lebih baik.

Kedua gambar adalah file PNG, mempertahankan kualitas lossless dan mendukung transparansi bila diperlukan.

---

## Cara menghasilkan file PNG barcode dalam format berbeda

Meskipun tutorial ini berfokus pada PNG, metode `Save` menerima format lain seperti `Jpeg`, `Bmp`, dan `Svg`. Untuk **how to generate barcode** file dalam format lain, cukup ganti `BarCodeImageFormat.Png` dengan nilai enum yang diinginkan:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Memilih SVG berguna ketika Anda membutuhkan gambar vektor yang dapat diskalakan tanpa pikselasi.

---

## Kesalahan umum saat Anda **create DataBar barcode** gambar

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| Barcode tampak buram | X‑dimension terlalu rendah untuk resolusi target | Tingkatkan `XDimension.Pixels` menjadi 3 atau 4 |
| Pemindai tidak dapat membaca kode | Tinggi bar terlalu pendek untuk optik pemindai | Gunakan minimal 30 pixel atau ikuti spesifikasi pemindai |
| String data ditolak | Format GS1 tidak tepat | Pastikan string dimulai dengan Identifier Aplikasi yang tepat, misalnya `(01)` untuk GTIN‑14 |

Mengatasi poin-poin ini lebih awal menghemat waktu saat mengintegrasikan barcode ke dalam alur produksi.

---

## Tips lanjutan: Menggunakan kembali generator yang sama untuk banyak barcode

Jika Anda perlu **generate barcode PNG** file untuk sekumpulan produk, gunakan kembali instance `BarcodeGenerator` yang sama dan hanya perbarui properti `CodeText`:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

Pola ini meminimalkan overhead pembuatan objek dan membuat kode Anda lebih ringkas.

---

## Kesimpulan

Anda kini memiliki alur kerja **barcode generator C#** lengkap yang **creates DataBar barcodes**, **generates barcode PNG** files, dan memungkinkan Anda **adjust barcode height** dengan satu perubahan properti. Contoh ini mencakup semua mulai dari penyiapan proyek hingga penanganan kasus tepi, sehingga Anda dapat mengintegrasikan pembuatan barcode ke dalam aplikasi .NET apa pun dengan percaya diri.

**Langkah selanjutnya**

- Jelajahi simbol barcode lain (`EncodeTypes.QR`, `EncodeTypes.Code128`) untuk memperluas solusi Anda.
- Gabungkan generator dengan ASP.NET Core untuk menyajikan barcode secara langsung melalui endpoint API.
- Bereksperimen dengan opsi warna (`generator.Parameters.Barcode.ForeColor`) untuk keperluan branding.

Selamat coding, dan semoga pemindaian Anda selalu cepat!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat dan membangun pada teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Menghasilkan dan Menyesuaikan Tinggi Barcode untuk One-Dimensional Databar menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Hasilkan Barcode One-Dimensional Databar 2D Menggunakan Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Cara Menghasilkan Barcode DataMatrix Menggunakan Aspose.BarCode untuk .NET – Panduan Langkah‑per‑Langkah](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}