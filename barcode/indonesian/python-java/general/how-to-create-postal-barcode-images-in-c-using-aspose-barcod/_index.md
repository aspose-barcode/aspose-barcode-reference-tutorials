---
category: general
date: 2026-10-21
description: Pelajari cara membuat gambar barcode pos di C# dengan Aspose.BarCode
  – menghasilkan barcode Planet dan RM4SCC, mengontrol batang yang terisi, dan menyimpan
  file PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- generate planet barcode
- how to generate barcode c#
language: id
lastmod: 2026-10-21
og_description: Buat gambar kode batang pos di C# dengan Aspose.BarCode. Tutorial
  ini menunjukkan cara menghasilkan kode batang Planet dan RM4SCC, mengubah bar yang
  terisi, dan menyimpan file PNG.
og_image_alt: Screenshot of a generated Planet postal barcode with filled bars
og_title: Buat gambar kode batang pos di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  headline: How to create postal barcode images in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  name: How to create postal barcode images in C# using Aspose.BarCode
  steps:
  - name: 1. Prepare the output folder
    text: The barcode images need a writable directory. The code creates the folder
      if it does not exist, preventing a runtime `DirectoryNotFoundException`.
  - name: 2. Generate a Planet barcode with filled bars
    text: Planet barcodes are used by many postal services for domestic mail. The
      default `FilledBars` setting renders solid bars, which is the most common visual
      style.
  - name: 3. Generate a Planet barcode with empty bars
    text: Some postal specifications require **empty** (hollow) bars. You can toggle
      this behavior via the `FilledBars` property.
  - name: 4. Generate an RM4SCC barcode with filled bars
    text: RM4SCC (Royal Mail 4‑State Customer Code) is the UK postal barcode. Like
      Planet, the default appearance uses solid bars.
  - name: Full source code in one block
    text: Copy the following snippet into a new C# console project. It compiles with
      .NET 6.0 and produces three PNG files in the `Barcodes` subfolder.
  - name: Next steps
    text: '* **Generate other postal barcodes** – try `EncodeTypes.Postnet` or `EncodeTypes.USPSIntelligentMail`.
      * **Customize appearance** – experiment with `BarHeight`, `ForeColor`, and `BackColor`
      to match your branding. * **Integrate into a web service** – expose the generation
      logic via ASP.NET Core endp'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara membuat gambar kode batang pos di C# menggunakan Aspose.BarCode
url: /id/python-java/general/how-to-create-postal-barcode-images-in-c-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar barcode pos di C# menggunakan Aspose.BarCode

Jika Anda perlu **membuat barcode pos** dalam proyek .NET, panduan ini menunjukkan solusi lengkap yang siap dijalankan. Anda akan melihat cara menghasilkan barcode Planet dan RM4SCC, beralih antara bar yang terisi dan kosong, serta menyimpan hasilnya sebagai file PNG—semua dengan beberapa baris kode C#.

Menghasilkan barcode pos yang dapat diandalkan penting untuk otomatisasi pengiriman, pencetakan label massal, dan integrasi dengan platform logistik. Pada akhir tutorial ini Anda akan memiliki potongan kode yang dapat digunakan kembali yang dapat Anda salin ke aplikasi konsol atau web C# apa pun.

## Prasyarat

Sebelum Anda mulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Visual Studio 2022 (atau IDE apa pun yang mendukung .NET)  
* Paket NuGet **Aspose.BarCode** yang aktif (`Install-Package Aspose.BarCode`)  

Alat-alat ini cukup untuk mengompilasi dan menjalankan contoh tanpa ketergantungan tambahan.

## Panduan langkah‑demi‑langkah untuk **membuat barcode pos** gambar

Proses terdiri dari empat langkah logis:

1. Siapkan folder output.  
2. Hasilkan barcode Planet dengan bar terisi (penampilan default).  
3. Hasilkan barcode Planet dengan bar kosong.  
4. Hasilkan barcode RM4SCC dengan bar terisi.  

Setiap langkah dijelaskan di bawah, dan kode sumber lengkap muncul setelah penjelasan.

### 1. Siapkan folder output

Gambar barcode memerlukan direktori yang dapat ditulisi. Kode membuat folder jika belum ada, mencegah `DirectoryNotFoundException` pada runtime.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Define the output folder (adjust the path to your environment)
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the folder exists
        Directory.CreateDirectory(outputFolder);
```

*Mengapa ini penting*: Direktori yang hilang menghentikan program sebelum barcode apa pun dihasilkan. Menggunakan `Directory.CreateDirectory` aman karena tidak melakukan apa‑apa jika folder sudah ada.

### 2. Hasilkan barcode Planet dengan bar terisi

Barcode Planet digunakan oleh banyak layanan pos untuk surat domestik. Pengaturan `FilledBars` default menghasilkan bar solid, yang merupakan gaya visual paling umum.

```csharp
        // Step 2: Generate a Planet barcode with filled bars (default)
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // XDimension controls the width of a single bar; 4 pixels works well for screen display
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);
```

*Explanation*:  
* `EncodeTypes.Planet` memberi tahu Aspose.BarCode untuk menggunakan standar Planet.  
* String data `"123456"` adalah payload Planet yang valid (6 karakter numerik).  
* `XDimension.Pixels = 4` menghasilkan lebar bar 4 px, yang menyeimbangkan keterbacaan dan ukuran file.  
* `Save` menulis gambar sebagai PNG, format loss‑less yang cocok untuk pemrosesan lebih lanjut.

### 3. Hasilkan barcode Planet dengan bar kosong

Beberapa spesifikasi pos memerlukan bar **kosong** (berongga). Anda dapat mengubah perilaku ini melalui properti `FilledBars`.

```csharp
        // Step 3: Generate a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        // Setting FilledBars to false creates hollow bars
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);
```

*Tip*: Saat beralih antara bar terisi dan kosong, pertahankan nilai `XDimension` tidak berubah untuk menjaga ukuran yang konsisten di seluruh gambar.

### 4. Hasilkan barcode RM4SCC dengan bar terisi

RM4SCC (Royal Mail 4‑State Customer Code) adalah barcode pos Inggris. Seperti Planet, penampilan default menggunakan bar solid.

```csharp
        // Step 4: Generate an RM4SCC barcode with filled bars (default)
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);
    }
}
```

*Mengapa RM4SCC*: Format RM4SCC mengkodekan string numerik 6‑digit ditambah checksum, menjadikannya ideal untuk layanan pos Inggris.

### Kode sumber lengkap dalam satu blok

Salin potongan berikut ke proyek konsol C# baru. Kode ini dikompilasi dengan .NET 6.0 dan menghasilkan tiga file PNG di subfolder `Barcodes`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // 1. Prepare the output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // -------------------------------------------------
        // 2. Planet barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3. Planet barcode – empty bars
        // -------------------------------------------------
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4. RM4SCC barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been saved to: " + outputFolder);
    }
}
```

#### Output yang diharapkan

Menjalankan program mencetak baris konfirmasi dan membuat tiga file:

* `PostalPlanetFilledBars.png` – barcode Planet dengan bar solid  
* `PostalPlanetEmptyBars.png` – barcode Planet dengan bar berongga  
* `PostalRM4SCCFilledBars.png` – barcode RM4SCC dengan bar solid  

Setiap gambar memiliki lebar 4 px per bar, cocok untuk pratinjau layar atau penyematan PDF siap cetak.

## Pertanyaan umum dan penanganan kasus tepi

| Pertanyaan | Jawaban |
|------------|---------|
| **Bagaimana jika string data tidak valid?** | Aspose.BarCode melempar `ArgumentException`. Validasi panjang input (Planet = 6 numerik, RM4SCC = 6 numerik) sebelum membuat generator. |
| **Apakah saya dapat mengubah format gambar?** | Ya. Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Gif`, `Bmp`, atau `Tiff` sesuai kebutuhan. |
| **Bagaimana cara menyesuaikan tinggi bar?** | Gunakan `planetFilled.Parameters.Barcode.BarHeight` (default 50 px). |
| **Apakah aman menggunakan kode ini dalam web API?** | Tentu saja. Generator ini thread‑safe untuk operasi baca‑saja, tetapi buat instance `BarcodeGenerator` baru per permintaan untuk menghindari state yang dibagikan. |
| **Bagaimana dengan standar pos lainnya?** | Aspose.BarCode juga mendukung `EncodeTypes.Postnet`, `EncodeTypes.USPSIntelligentMail`, dll. Pola yang sama berlaku—cukup ubah nilai `EncodeTypes`. |

## Kesimpulan

Anda kini tahu cara **membuat barcode pos** dalam C# dengan Aspose.BarCode, mencakup format Planet dan RM4SCC serta menunjukkan cara beralih antara bar terisi dan kosong. Contoh lengkap yang dapat dijalankan dapat dimasukkan ke dalam proyek .NET apa pun, memberikan output visual secara langsung.

### Langkah selanjutnya

* **Hasilkan barcode pos lainnya** – coba `EncodeTypes.Postnet` atau `EncodeTypes.USPSIntelligentMail`.  
* **Sesuaikan tampilan** – bereksperimen dengan `BarHeight`, `ForeColor`, dan `BackColor` untuk menyesuaikan merek Anda.  
* **Integrasikan ke layanan web** – ekspos logika pembuatan melalui endpoint ASP.NET Core untuk pembuatan barcode sesuai permintaan.  

Dengan menguasai teknik ini Anda akan dapat **menghasilkan gambar barcode planet** dan menjawab pertanyaan “**cara menghasilkan barcode C#**” dengan percaya diri, baik Anda membangun alat pengiriman desktop maupun API pengiriman berbasis cloud. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to create planet barcode with filled and empty bars](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [How to create RM4SCC barcode and generate planet barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}