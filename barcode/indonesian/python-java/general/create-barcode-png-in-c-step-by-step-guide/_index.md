---
category: general
date: 2026-08-03
description: Buat PNG barcode dalam C# dan pelajari cara mengubah rasio aspek untuk
  gambar DataBar. Ikuti contoh lengkap ini dengan kode dan tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: id
lastmod: 2026-08-03
og_description: Buat barcode PNG dengan C# dan pelajari cara mengubah rasio aspek
  untuk barcode DataBar. Panduan ini menyediakan kode siap‑jalankan dan tips praktis.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: Buat barcode PNG di C# – contoh lengkap dengan kontrol rasio aspek
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: Buat barcode PNG di C# – panduan langkah demi langkah
url: /id/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat barcode PNG di C# – panduan langkah demi langkah

Jika Anda perlu **membuat barcode PNG** di C#, tutorial ini menunjukkan secara tepat caranya. Anda akan menghasilkan barcode DataBar omnidirectional bertumpuk, menyimpannya sebagai file PNG, dan mempelajari **cara mengubah rasio aspek** untuk menyesuaikan dengan berbagai lingkungan pemindaian.

Panduan ini mencakup semua yang Anda perlukan: paket yang diperlukan, program lengkap yang dapat dijalankan, dan penjelasan mengapa setiap pengaturan penting. Pada akhir tutorial Anda akan memiliki dua file PNG—satu dengan rasio aspek 15 dan satu lagi dengan 30—siap untuk pengujian atau penggunaan produksi.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- .NET 6.0 SDK atau yang lebih baru terpasang
- Visual Studio 2022 (atau IDE C# apa pun)
- Referensi NuGet ke **Aspose.BarCode** (perpustakaan yang menyediakan `BarcodeGenerator`)
- Izin menulis ke direktori tempat file PNG akan disimpan

Anda dapat menambahkan paket Aspose.BarCode dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Siapkan proyek dan impor namespace

Buat aplikasi konsol baru dan impor namespace yang diperlukan untuk pembuatan barcode serta I/O file.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Mengapa ini penting:** Mengimpor `Aspose.BarCode.Generation` memberi Anda akses ke `BarcodeGenerator`. Menjaga kode di dalam `Main` membuat contoh ini mandiri dan mudah dijalankan.

## Langkah 2: Buat generator barcode untuk DataBar omnidirectional bertumpuk

Instansiasi `BarcodeGenerator` dengan tipe `EncodeTypes.DatabarStackedOmniDirectional` dan string data contoh GS1‑128.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Mengapa ini penting:** Tipe enkode yang dipilih menghasilkan DataBar berkapasitas tinggi yang dapat dibaca oleh sebagian besar pemindai modern. String data mengikuti format GS1 Application Identifier (01), yang umum untuk pengidentifikasi produk.

## Langkah 3: Tentukan dimensi X (lebar modul) dalam piksel

Atur lebar modul untuk mengendalikan ukuran keseluruhan barcode tanpa memengaruhi keterbacaannya.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Mengapa ini penting:** Dimensi X sebesar 2 piksel menghasilkan barcode yang tidak terlalu kecil bagi pemindai maupun tidak terlalu besar untuk ruang label tipikal.

## Langkah 4: Simpan PNG pertama dengan rasio aspek 15

Sesuaikan rasio aspek DataBar, lalu simpan gambar sebagai file PNG.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Mengapa ini penting:** Rasio aspek mengontrol hubungan tinggi‑dengan‑lebar dari DataBar bertumpuk. Rasio 15 adalah nilai default umum yang menyeimbangkan keterbacaan dan tinggi label.

## Langkah 5: Ubah rasio aspek menjadi 30 dan simpan PNG kedua

Modifikasi instance generator yang sama untuk menggunakan rasio aspek yang lebih besar, lalu simpan gambar kedua.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Mengapa ini penting:** Meningkatkan rasio aspek memperpanjang barcode secara vertikal, yang dapat meningkatkan keandalan pemindaian pada perangkat beresolusi rendah atau ketika label dicetak pada media sempit.

## Output yang diharapkan

Menjalankan program akan membuat dua file PNG:

| File                               | Rasio Aspek | Dimensi perkiraan (piksel) |
|------------------------------------|-------------|----------------------------|
| `DatabarAspectRatio15.png`         | 15          | 200 × 300 (lebar × tinggi) |
| `DatabarAspectRatio30.png`         | 30          | 200 × 600 (lebar × tinggi) |

Kedua gambar berisi barcode DataBar yang jelas dan dapat dipindai, yang mengenkode identifier GS1 `(01)12345678901231`.

## Pertanyaan umum dan kasus tepi

### Bagaimana cara mengubah properti visual lainnya?

Anda dapat menyesuaikan warna latar depan, warna latar belakang, atau menambahkan teks yang dapat dibaca manusia melalui objek `generator.Parameters.Barcode`. Contohnya:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### Bagaimana jika saya membutuhkan format gambar yang berbeda?

Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif` sesuai kebutuhan. PNG tetap pilihan terbaik untuk gambar barcode tanpa kehilangan kualitas.

### Apakah rasio aspek memengaruhi kecepatan pemindaian?

Rasio aspek yang lebih tinggi meningkatkan tinggi barcode, yang dapat memperbaiki keandalan pemindaian pada perangkat yang kesulitan dengan simbol bertumpuk pendek. Namun, barcode yang sangat tinggi mungkin tidak muat pada label kecil, jadi lakukan pengujian dengan perangkat target Anda.

### Bisakah saya menghasilkan beberapa barcode dalam sebuah loop?

Ya. Buat instance `BarcodeGenerator` baru untuk setiap string data atau gunakan kembali instance yang sama sambil memperbarui `CodeText` dan `DataBar.AspectRatio`. Pendekatan ini mengurangi beban alokasi objek.

## Tips profesional

- **Gunakan kembali generator**: Mengubah hanya `CodeText` atau `AspectRatio` menghindari pembuatan ulang objek, yang mempercepat pemrosesan batch.
- **Validasi output**: Gunakan pemindai genggam atau aplikasi seluler untuk memastikan PNG yang dihasilkan dapat dibaca dengan benar sebelum diterapkan ke produksi.
- **Penamaan file**: Sertakan rasio aspek dalam nama file (seperti yang ditunjukkan) untuk melacak variasi selama pengujian.

## Kesimpulan

Anda kini tahu cara **membuat barcode PNG** di C# dan secara tepat **mengubah rasio aspek** untuk simbol DataBar omnidirectional bertumpuk. Contoh lengkap menunjukkan inisialisasi, pengaturan dimensi X, manipulasi rasio aspek, dan penyimpanan gambar—semua dalam satu program yang dapat dijalankan.

Dari sini Anda dapat menjelajahi tipe barcode tambahan, bereksperimen dengan warna, atau mengintegrasikan generator ke dalam sistem pelaporan atau inventaris yang lebih besar. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Buat Barcode PNG – Rasio Aspek DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cara Menyesuaikan Barcode - Rasio Aspek Codablock F dengan Aspose.BarCode untuk .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}