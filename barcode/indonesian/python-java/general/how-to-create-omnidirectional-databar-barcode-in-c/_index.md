---
category: general
date: 2026-09-29
description: Pelajari cara membuat kode batang Databar omnidirectional di C# dengan
  Aspose.BarCode. Sesuaikan dimensi X, atur rasio aspek, dan simpan gambar PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: id
lastmod: 2026-09-29
og_description: Buat kode batang Databar omnidirectional di C# menggunakan Aspose.BarCode.
  Pelajari cara mengatur dimensi X, menyesuaikan rasio aspek, dan mengekspor file
  PNG.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Buat kode batang Databar omnidireksional di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Cara membuat kode batang Databar omnidireksional di C#
url: /id/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode Databar omnidirectional di C#

Jika Anda perlu **membuat barcode Databar omnidirectional** dalam aplikasi .NET, panduan ini menunjukkan langkah‑langkah tepatnya. Anda akan melihat cara menginisialisasi barcode DataBar stacked omnidirectional, mengonfigurasi X‑dimension‑nya, mengubah rasio aspek, dan menghasilkan gambar PNG dengan Aspose.BarCode.

Membuat **DataBar stacked omnidirectional barcode** umum ketika Anda harus mengkodekan pengidentifikasi produk untuk pemindai ritel. Dalam tutorial ini Anda akan belajar **mengatur rasio aspek barcode**, mengontrol ukuran modul, dan mengekspor hasilnya tanpa meninggalkan IDE.

## Prasyarat

- .NET 6.0 atau yang lebih baru terpasang
- Visual Studio 2022 (atau IDE kompatibel C# apa pun)
- Paket NuGet **Aspose.BarCode for .NET** (versi 23.12 atau lebih baru)

Anda dapat menambahkan paket tersebut melalui NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Inisialisasi barcode Databar omnidirectional

Langkah pertama adalah membuat instance `BarcodeGenerator` yang menargetkan simbol **DataBar stacked omnidirectional**. Konstruktor menerima tipe enkode dan string data.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Mengapa ini penting:** Nilai `EncodeTypes.DatabarStackedOmniDirectional` memberi tahu Aspose.BarCode untuk merender format Databar omnidirectional tertentu, yang diperlukan untuk pemindaian dalam kedua arah.

## Langkah 2: Tentukan X‑dimension (ukuran modul)

X‑dimension mengontrol lebar satu modul barcode dalam piksel. Nilai `2` piksel bekerja dengan baik untuk render di layar dan sebagian besar printer.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Mengapa ini penting:** X‑dimension yang konsisten memastikan barcode memenuhi spesifikasi ukuran minimum untuk pemindai ritel sekaligus menjaga ukuran file gambar tetap terkendali.

## Langkah 3: Atur rasio aspek pertama dan simpan gambar

**Rasio aspek** menentukan hubungan tinggi‑ke‑lebar DataBar. Rasio aspek `15` menghasilkan barcode yang kompak dan tinggi, ideal untuk ruang label yang sempit.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Mengapa ini penting:** Menyesuaikan rasio aspek memungkinkan Anda menempatkan barcode ke dalam tata letak label yang berbeda tanpa mengorbankan keterbacaan. PNG yang disimpan dapat diperiksa di penampil gambar apa pun.

## Langkah 4: Ubah rasio aspek dan hasilkan gambar kedua

Kadang‑kadang barcode yang lebih lebar diperlukan—misalnya, ketika label memiliki lebih banyak ruang horizontal. Mengubah rasio menjadi `30` menghasilkan tampilan yang lebih datar.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Mengapa ini penting:** Dengan mengekspos properti **set barcode aspect ratio**, Anda dapat menghasilkan berbagai variasi barcode dari satu basis kode, menyederhanakan alur kerja pembuatan label otomatis.

## Output yang Diharapkan

Menjalankan program menghasilkan dua file PNG di folder output aplikasi:

| Nama File                | Rasio Aspek | Deskripsi Visual |
|--------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png` | 15           | Barcode tinggi dan sempit yang cocok untuk label sempit |
| `DatabarAspectRatio30.png` | 30           | Barcode lebih lebar yang mengisi lebih banyak ruang horizontal |

Anda dapat menyematkan gambar ini dalam laporan, mencetaknya pada kemasan produk, atau mengirimnya ke layanan web untuk pemrosesan lebih lanjut.

![Contoh pembuatan barcode Databar omnidirectional](databar-example.png "Contoh pembuatan barcode Databar omnidirectional")

*Tangkap layar menunjukkan dua file PNG yang dihasilkan berdampingan.*

## Pertanyaan umum dan kasus tepi

### Bagaimana jika saya membutuhkan X‑dimension yang berbeda?

Anda dapat menetapkan nilai integer apa pun ke `XDimension.Pixels`. Nilai di bawah `1` diabaikan, dan nilai di atas `10` dapat menghasilkan modul yang terlalu besar dan melampaui margin printer. Uji output visual setelah setiap perubahan.

### Bagaimana cara saya mengenkode data AI lain (mis., UPC, EAN)?

Ganti string data dalam konstruktor `BarcodeGenerator` dengan Application Identifier (AI) yang sesuai. Untuk kode UPC‑A, gunakan `"012345678905"` tanpa awalan AI.

### Bisakah saya mengekspor ke format selain PNG?

Ya. Metode `Save` menerima `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff`, dan `BarCodeImageFormat.Bmp`. Pilih format yang sesuai dengan alur kerja downstream Anda.

## Tips pro: gunakan kembali generator untuk pemrosesan batch

Jika Anda perlu menghasilkan puluhan barcode dengan rasio aspek yang bervariasi, pertahankan instance `BarcodeGenerator` tetap hidup dan hanya ubah `DataBar.AspectRatio` sebelum setiap `Save`. Ini menghindari beban overhead dari membuat ulang generator untuk setiap gambar.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Kesimpulan

Anda sekarang tahu cara **membuat barcode Databar omnidirectional** di C# menggunakan Aspose.BarCode. Dengan menginisialisasi `BarcodeGenerator`, mengatur X‑dimension, menyesuaikan **set barcode aspect ratio**, dan menyimpan file PNG, Anda dapat menghasilkan gambar barcode yang memenuhi berbagai kebutuhan label.  

Selanjutnya, jelajahi topik terkait seperti **generate barcode image** untuk kode QR, validasi **DataBar stacked omnidirectional barcode**, atau mengintegrasikan PNG yang dihasilkan ke dalam faktur PDF dengan Aspose.PDF. Bereksperimenlah dengan rasio aspek dan ukuran modul yang berbeda untuk menemukan konfigurasi optimal bagi perangkat keras pencetakan Anda.

---

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara menggunakan generator barcode C# untuk membuat barcode DataBar Omni‑directional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [databar stacked omnidirectional barcode di C# – Panduan Lengkap](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Cara menghasilkan barcode di C# – membuat gambar barcode c# dengan DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}