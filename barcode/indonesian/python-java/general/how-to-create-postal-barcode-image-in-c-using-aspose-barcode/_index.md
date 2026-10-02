---
category: general
date: 2026-10-02
description: Buat gambar kode batang pos di C# dengan Aspose.BarCode. Pelajari cara
  menghasilkan kode batang Planet dan RM4SCC, sesuaikan batang yang terisi, dan simpan
  file PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- Aspose.BarCode C#
- postal barcode PNG
- barcode XDimension setting
language: id
lastmod: 2026-10-02
og_description: Buat gambar kode batang pos di C# dengan Aspose.BarCode. Tutorial
  ini menunjukkan cara menghasilkan kode batang Planet dan RM4SCC, menyesuaikan isi
  bar, dan mengekspor file PNG.
og_image_alt: Postal barcode image generated with Aspose.BarCode (filled bars)
og_title: Buat gambar kode batang pos di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  headline: How to create postal barcode image in C# using Aspose.BarCode
  type: TechArticle
- description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  name: How to create postal barcode image in C# using Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – The `EncodeTypes.Planet`
      enum tells Aspose.BarCode to use the *Planet* symbology, which is a standard
      postal barcode in many countries. This is the core of how you **generate planet
      barcode** images. * **`XDimension.Pixels = 4`** – The wid'
  - name: Expected output
    text: 'After running the program, the `YOUR_DIRECTORY` folder contains three PNG
      files:'
  - name: Change image format
    text: If you need a different format (e.g., JPEG for web delivery), replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. Keep in mind that JPEG introduces compression
      artifacts, which can affect scanner performance.
  - name: Adjust image size without scaling
    text: Instead of changing `XDimension`, you can control the overall image dimensions
      via `Parameters.Image.Height` and `Parameters.Image.Width`. This is useful when
      you have a fixed label size.
  - name: Use a different barcode symbology
    text: Aspose.BarCode supports dozens of postal symbologies (e.g., **USPS Intelligent
      Mail**, **Japan Post**). To **generate planet barcode** alternatives, replace
      `EncodeTypes.Planet` with the desired enum value.
  - name: Handling invalid data
    text: Postal barcodes have strict data length rules. If you pass a string that
      does not meet the specification, Aspose.BarCode throws an `ArgumentException`.
      Wrap the generator creation in a `try/catch` block to provide a friendly error
      message.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Cara membuat gambar kode batang pos di C# menggunakan Aspose.BarCode
url: /id/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar barcode pos dalam C# menggunakan Aspose.BarCode

Jika Anda perlu **membuat gambar barcode pos** dalam C#, Aspose.BarCode menyediakan API yang bersih yang menangani pekerjaan berat. Baik Anda sedang membangun sistem label pengiriman atau layanan verifikasi alamat, panduan ini menunjukkan secara tepat cara menghasilkan barcode Planet dan RM4SCC, beralih antara bar yang terisi dan kosong, serta mengekspor hasilnya sebagai file PNG.

Anda akan belajar cara mengonfigurasi ukuran barcode, mengontrol perilaku pengisian bar, dan menyimpan gambar ke disk—semua dalam satu program yang dapat dijalankan. Tidak ada alat eksternal yang diperlukan selain pustaka Aspose.BarCode untuk .NET.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru (kode juga berfungsi dengan .NET Framework 4.7+)
* Visual Studio 2022 atau IDE C# yang kompatibel
* Salinan berlisensi atau evaluasi dari **Aspose.BarCode for .NET** (tersedia via NuGet)

```bash
dotnet add package Aspose.BarCode
```

## Gambaran solusi

Tutorial ini dibagi menjadi tiga langkah logis:

1. **Buat barcode Planet dengan bar default (terisi)** – ini menunjukkan tampilan tipikal untuk layanan pos.  
2. **Buat barcode Planet dengan bar kosong** – berguna ketika proses pencetakan mengharapkan bar yang tidak terisi.  
3. **Buat barcode RM4SCC dengan bar terisi** – format pos umum lain yang digunakan di banyak negara.  

Setiap langkah mengikuti pola yang sama: menginstansiasi `BarcodeGenerator`, mengatur `XDimension` (lebar piksel satu bar), secara opsional menyesuaikan `FilledBars`, dan memanggil `Save` untuk menulis file PNG.

---

## Buat gambar barcode pos dengan Aspose.BarCode

Berikut adalah program lengkap yang berdiri sendiri. Simpan sebagai `Program.cs` dan jalankan dari command line atau IDE Anda.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define the output folder – change this to a writable location on your machine
            string outputDir = @"YOUR_DIRECTORY";

            // -------------------------------------------------
            // Step 1: Generate a Planet barcode with filled bars
            // -------------------------------------------------
            var planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                // XDimension controls the width of a single bar in pixels.
                // A value of 4 gives a good balance between readability and file size.
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string planetFilledPath = System.IO.Path.Combine(outputDir, "PostalPlanetFilledBars.png");
            planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled Planet barcode saved to {planetFilledPath}");

            // -------------------------------------------------
            // Step 2: Generate a Planet barcode with empty bars
            // -------------------------------------------------
            var planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                Parameters = {
                    Barcode = {
                        XDimension = { Pixels = 4 },
                        // Setting FilledBars to false renders the bars as empty outlines.
                        FilledBars = false
                    }
                }
            };
            string planetEmptyPath = System.IO.Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
            planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Empty Planet barcode saved to {planetEmptyPath}");

            // -------------------------------------------------
            // Step 3: Generate an RM4SCC barcode with filled bars
            // -------------------------------------------------
            var rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
            {
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string rm4sccPath = System.IO.Path.Combine(outputDir, "PostalRM4SCCFilledBars.png");
            rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled RM4SCC barcode saved to {rm4sccPath}");

            // End of demo
            Console.WriteLine("All barcode images have been generated successfully.");
        }
    }
}
```

### Mengapa setiap baris penting

* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – Enum `EncodeTypes.Planet` memberi tahu Aspose.BarCode untuk menggunakan simbol *Planet*, yang merupakan barcode pos standar di banyak negara. Ini adalah inti cara Anda **menghasilkan gambar planet barcode**.  
* **`XDimension.Pixels = 4`** – Lebar satu bar memengaruhi baik keandalan pemindaian maupun ukuran visual. Nilai 4 px bekerja baik untuk kebanyakan printer label; Anda dapat meningkatkannya untuk output resolusi lebih tinggi.  
* **`FilledBars = false`** – Secara default, bar terisi. Mengatur ini ke `false` menghasilkan gaya “bar kosong” yang diperlukan oleh beberapa spesifikasi pengiriman.  
* **`Save(..., BarCodeImageFormat.Png)`** – PNG mempertahankan kualitas loss‑less, menjadikannya ideal untuk gambar barcode yang harus dibaca oleh pemindai.  

### Output yang diharapkan

Setelah menjalankan program, folder `YOUR_DIRECTORY` berisi tiga file PNG:

| Nama file | Deskripsi visual |
|-----------|------------------|
| `PostalPlanetFilledBars.png` | Planet barcode dengan bar hitam solid |
| `PostalPlanetEmptyBars.png` | Planet barcode dimana bar digambar sebagai outline (kosong) |
| `PostalRM4SCCFilledBars.png` | RM4SCC barcode dengan bar solid |

Anda dapat membuka salah satu gambar ini di penampil gambar atau menyematkannya langsung dalam label PDF/HTML.

---

## Menyesuaikan barcode lebih lanjut (opsional)

### Ubah format gambar

Jika Anda membutuhkan format berbeda (mis., JPEG untuk pengiriman web), ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg`. Perlu diingat bahwa JPEG memperkenalkan artefak kompresi, yang dapat memengaruhi kinerja pemindai.

### Sesuaikan ukuran gambar tanpa skala

Alih-alih mengubah `XDimension`, Anda dapat mengontrol dimensi gambar secara keseluruhan melalui `Parameters.Image.Height` dan `Parameters.Image.Width`. Ini berguna ketika Anda memiliki ukuran label tetap.

```csharp
planetFilled.Parameters.Image.Height = 150; // pixels
planetFilled.Parameters.Image.Width = 300;  // pixels
```

### Gunakan simbol barcode yang berbeda

Aspose.BarCode mendukung puluhan simbol pos (mis., **USPS Intelligent Mail**, **Japan Post**). Untuk **menghasilkan planet barcode** alternatif, ganti `EncodeTypes.Planet` dengan nilai enum yang diinginkan.

```csharp
var uspsBarcode = new BarcodeGenerator(EncodeTypes.USPSIntelligentMail, "123456789012");
```

### Menangani data tidak valid

Barcode pos memiliki aturan panjang data yang ketat. Jika Anda memberikan string yang tidak memenuhi spesifikasi, Aspose.BarCode akan melempar `ArgumentException`. Bungkus pembuatan generator dalam blok `try/catch` untuk memberikan pesan error yang ramah.

```csharp
try
{
    var invalid = new BarcodeGenerator(EncodeTypes.Planet, "ABC");
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

---

## Jebakan umum dan tip profesional

| Jebakan | Mengapa terjadi | Tip pro |
|---------|----------------|---------|
| **Menggunakan XDimension yang terlalu kecil** | Bar menjadi lebih tipis daripada resolusi minimum pemindai, menyebabkan kesalahan pembacaan. | Mulailah dengan `Pixels = 4` dan uji pada printer target; tingkatkan jika diperlukan. |
| **Menyimpan ke folder read‑only** | `Save` melempar `UnauthorizedAccessException`. | Pastikan `outputDir` mengarah ke lokasi yang dapat ditulis, atau gunakan `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`. |
| **Mengabaikan disposisi generator** | Gambar besar dapat menahan sumber daya yang tidak dikelola. | Bungkus generator dalam pernyataan `using` atau panggil `Dispose()` setelah `Save`. |
| **Mencampur format barcode dalam satu gambar** | Beberapa printer mengharapkan satu simbol per label. | Hasilkan setiap barcode secara terpisah dan gabungkan mereka dengan pustaka grafis jika diperlukan. |

---

## Verifikasi barcode yang dihasilkan

Untuk memastikan barcode valid, Anda dapat menggunakan situs **Aspose.BarCode Demo** gratis atau aplikasi pemindai barcode standar apa pun. Muat file PNG dan pindai; nilai yang didekode harus `123456` untuk contoh Planet dan RM4SCC.

---

## Kesimpulan

Dalam tutorial ini Anda belajar cara **membuat file gambar barcode pos** dalam C# dengan Aspose.BarCode. Anda melihat cara **menghasilkan gambar planet barcode** dengan bar terisi dan kosong, cara menghasilkan barcode RM4SCC, serta cara menyesuaikan ukuran, format, dan penanganan error. Dengan kode lengkap yang dapat dijalankan, Anda kini dapat mengintegrasikan pembuatan barcode pos ke dalam aplikasi .NET apa pun.

**Langkah selanjutnya**

* Jelajahi simbol pos lainnya seperti `EncodeTypes.USPSIntelligentMail` (kata kunci sekunder: postal barcode PNG).

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Buat Gambar Barcode Pos dalam C# – Panduan Langkah‑per‑Langkah Lengkap](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Hasilkan Barcode Pos dalam C# – Panduan Lengkap dengan Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Cara menghasilkan barcode pos dalam C# dengan Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}