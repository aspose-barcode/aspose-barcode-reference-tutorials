---
category: general
date: 2026-07-27
description: Buat gambar barcode planet dengan cepat. Pelajari cara menghasilkan barcode
  planet dengan C# dan sesuaikan batang yang terisi atau kosong.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate planet barcode
- planet barcode C#
- barcode X‑dimension
- filled vs empty bars
language: id
lastmod: 2026-07-27
og_description: Buat gambar kode batang planet dalam hitungan detik. Ikuti panduan
  ini untuk belajar cara menghasilkan kode batang planet, menyesuaikan dimensi X,
  dan beralih antara batang terisi dan kosong.
og_image_alt: Screenshot showing a create planet barcode image with filled bars
og_title: Buat gambar barcode planet – Tutorial C# Lengkap
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  headline: create planet barcode image – Step‑by‑Step Guide
  type: TechArticle
- description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  name: create planet barcode image – Step‑by‑Step Guide
  steps:
  - name: Why the X‑dimension matters
    text: The X‑dimension controls how wide each tiny bar (or “module”) is. A value
      of **4 pixels** yields a barcode that’s clear on screen and prints nicely on
      standard label printers. If you need a denser image for a high‑resolution print,
      bump the value up to 6 or 8.
  - name: Expected output
    text: Open the resulting `PostalPlanetFilledBars.png` and you should see a classic
      Planet barcode—solid vertical bars with a quiet zone on each side. It looks
      just like the example you’d find on a postal envelope.
  - name: What “FilledBars = false” does
    text: Setting `FilledBars` to `false` tells the rendering engine to draw only
      the bar outlines. This is useful when you need a lighter‑weight image for on‑screen
      display or when a printing guideline explicitly requires the empty style.
  - name: Expected output
    text: The `PostalPlanetEmptyBars.png` file shows the same pattern as before, but
      each bar is a thin line instead of a solid block. It’s perfect for low‑contrast
      printing on colored paper.
  - name: When to use RM4SCC
    text: RM4SCC is the Dutch “Postcode” barcode. If you’re building a multi‑country
      logistics platform, having both Planet and RM4SCC generators at hand saves you
      a lot of boilerplate code.
  - name: What if I need a different image format?
    text: Just swap `BarCodeImageFormat.Png` for `Jpeg`, `Bmp`, or `Gif`. The library
      handles the conversion automatically.
  - name: How do I change the barcode height?
    text: Use `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points`
      (or pixels, depending on the library version). Higher values give you a taller
      barcode, which can improve scan reliability on low‑resolution scanners.
  - name: Can I embed the barcode directly into a PDF?
    text: Absolutely. The `Save` method returns a `byte[]` if you call the overload
      that writes to a stream. Feed that stream into a PDF generation library (e.g.,
      iTextSharp) and you’ve got a fully‑automated mailing label.
  - name: What if the data string contains non‑numeric characters?
    text: 'Planet and RM4SCC expect **numeric only** payloads. Passing letters will
      throw an `ArgumentException`. Validate your input first:'
  - name: Does the X‑dimension affect scanning speed?
    text: A larger X‑dimension creates a more robust barcode, which generally improves
      scanning speed, especially on low‑quality scanners. However, it also increases
      the physical size of the label, so balance readability with space constraints.
  type: HowTo
tags:
- barcode
- C#
- imaging
title: Buat gambar kode batang planet – Panduan Langkah demi Langkah
url: /id/python-java/general/create-planet-barcode-image-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# create planet barcode image – Complete C# Tutorial

Pernah bertanya‑tanya **bagaimana cara menghasilkan planet barcode** untuk sistem pengiriman atau aplikasi logistik? Anda bukan yang pertama kebingungan tentang hal itu. Pada tutorial ini kita akan membahas semua yang Anda perlukan untuk **create planet barcode image** file, mulai dari dasar‑dasar kelas `BarcodeGenerator` hingga menyesuaikan X‑dimension dan mengganti bar yang terisi dengan bar kosong.

Kami juga akan melihat simbolologi terkait—RM4SCC—sehingga Anda dapat melihat bagaimana pola yang sama bekerja untuk barcode pos lainnya. Pada akhir tutorial, Anda akan memiliki tiga potongan kode siap‑jalankan yang menghasilkan file PNG yang dapat langsung Anda gunakan dalam proyek.

## What You’ll Need

- .NET 6.0 atau yang lebih baru (kode ini juga bekerja pada .NET Framework 4.7+)
- Referensi ke **Aspose.BarCode** (atau perpustakaan apa pun yang menyediakan `BarcodeGenerator`, `EncodeTypes`, `BarCodeImageFormat`)
- IDE yang Anda nyaman gunakan—Visual Studio, Rider, atau VS Code sudah cukup
- Folder yang dapat ditulisi gambar (ganti `YOUR_DIRECTORY` pada contoh)

Itu saja. Tidak ada paket NuGet tambahan selain perpustakaan barcode itu sendiri.

---

## Step 1: Set Up the Project and Imports

Pertama‑tama, buat aplikasi console kecil agar kita dapat menjalankan kode secara langsung.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll call helper methods here (see later)
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();
        }
```

> **Pro tip:** Jaga metode `Main` Anda tetap rapi; delegasikan setiap skenario ke metode terpisah. Ini membuat kode lebih mudah dibaca dan mencerminkan tiga contoh dalam potongan asli.

---

## Step 2: **create planet barcode image** with Default Filled Bars

Simbolologi Planet digunakan oleh banyak layanan pos untuk nomor pelacakan. Untuk **create planet barcode image** dengan bar solid standar, ikuti tiga baris berikut:

```csharp
        static void GeneratePlanetFilledBars()
        {
            // 1️⃣ Create a generator for the Planet symbology with data "123456"
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the X‑dimension (module width) to 4 pixels for better visibility
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode as a PNG image
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }
```

### Why the X‑dimension matters
X‑dimension mengontrol seberapa lebar setiap bar kecil (atau “module”). Nilai **4 pixel** menghasilkan barcode yang jelas di layar dan tercetak dengan baik pada printer label standar. Jika Anda membutuhkan gambar yang lebih padat untuk cetakan resolusi tinggi, naikkan nilai menjadi 6 atau 8.

### Expected output
Buka file `PostalPlanetFilledBars.png` yang dihasilkan dan Anda akan melihat barcode Planet klasik—bar vertikal solid dengan zona tenang di setiap sisi. Hasilnya persis seperti contoh yang biasanya Anda temukan pada amplop pos.

---

## Step 3: **create planet barcode image** with Empty Bars

Kadang‑kadang spesifikasi pos mengharuskan gaya *empty‑bar*, di mana bar digambar sebagai outline bukan isi solid. Beralih ke mode itu hanya memerlukan satu perubahan properti.

```csharp
        static void GeneratePlanetEmptyBars()
        {
            // 1️⃣ Create the generator (same data as before)
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Keep the X‑dimension consistent
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Disable filled bars → we get an empty‑bar representation
            planetEmpty.Parameters.Barcode.FilledBars = false;

            // 4️⃣ Save the PNG
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }
```

### What “FilledBars = false” does
Menetapkan `FilledBars` ke `false` memberi tahu mesin render untuk menggambar hanya outline bar. Ini berguna ketika Anda memerlukan gambar yang lebih ringan untuk tampilan di layar atau ketika pedoman pencetakan secara eksplisit meminta gaya kosong.

### Expected output
File `PostalPlanetEmptyBars.png` menampilkan pola yang sama seperti sebelumnya, namun setiap bar berupa garis tipis alih‑alih blok solid. Cocok untuk pencetakan kontras rendah pada kertas berwarna.

---

## Step 4: Generate an RM4SCC Barcode (Bonus)

Meskipun fokus utama kami adalah simbolologi Planet, API yang sama memungkinkan Anda **create planet barcode image**‑like hasil untuk kode pos lainnya. Berikut cara **how to generate planet barcode**‑style output untuk RM4SCC:

```csharp
        static void GenerateRM4SCCFilledBars()
        {
            // 1️⃣ Create a generator for the RM4SCC symbology
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // 2️⃣ Align X‑dimension with the other examples
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the image
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

### When to use RM4SCC
RM4SCC adalah barcode “Postcode” Belanda. Jika Anda membangun platform logistik multi‑negara, memiliki generator Planet dan RM4SCC sekaligus menghemat banyak kode boilerplate.

---

## Common Questions & Edge Cases

### What if I need a different image format?
Cukup ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif`. Perpustakaan akan menangani konversi secara otomatis.

### How do I change the barcode height?
Gunakan `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points` (atau pixel, tergantung versi perpustakaan). Nilai yang lebih tinggi menghasilkan barcode yang lebih tinggi, yang dapat meningkatkan keandalan pemindaian pada scanner beresolusi rendah.

### Can I embed the barcode directly into a PDF?
Tentu saja. Metode `Save` mengembalikan `byte[]` bila Anda memanggil overload yang menulis ke stream. Masukkan stream tersebut ke perpustakaan pembuatan PDF (misalnya iTextSharp) dan Anda memiliki label pos yang sepenuhnya otomatis.

### What if the data string contains non‑numeric characters?
Planet dan RM4SCC mengharapkan **payload numerik saja**. Memberikan huruf akan memicu `ArgumentException`. Validasi input Anda terlebih dahulu:

```csharp
if (!Regex.IsMatch(data, @"^\d+$"))
    throw new ArgumentException("Planet barcode data must be numeric.");
```

### Does the X‑dimension affect scanning speed?
X‑dimension yang lebih besar menghasilkan barcode yang lebih kuat, yang umumnya mempercepat pemindaian, terutama pada scanner kualitas rendah. Namun, ini juga meningkatkan ukuran fisik label, jadi seimbangkan keterbacaan dengan batas ruang yang tersedia.

---

## Full Working Example (All Three Methods)

Berikut program lengkap yang dapat Anda salin‑tempel ke proyek console baru. Ganti `YOUR_DIRECTORY` dengan jalur absolut atau relatif yang dapat ditulisi oleh aplikasi Anda.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();

            Console.WriteLine("All barcode images have been saved.");
        }

        static void GeneratePlanetFilledBars()
        {
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }

        static void GeneratePlanetEmptyBars()
        {
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCFilledBars()
        {
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

Jalankan program, buka tiga file PNG, dan Anda akan melihat gambar persis seperti yang dijelaskan sebelumnya. Tidak ada konfigurasi tambahan yang diperlukan.

---

## Recap & Next Steps

Kami telah membahas **how to generate planet barcode** images dari awal, beralih antara gaya solid dan outline, serta memperluas pendekatan yang sama ke RM4SCC. Poin penting yang harus diingat:

1. Instansiasi `BarcodeGenerator` dengan `EncodeTypes` dan data yang tepat.  
2. Sesuaikan `XDimension.Pixels` untuk mengontrol lebar bar.  
3. Gunakan `FilledBars = false` untuk varian bar kosong.  
4. Simpan hasil dalam format gambar pilihan Anda.

Sekarang Anda dapat **create planet barcode image** file, pertimbangkan ide‑ide lanjutan berikut:

- **Batch generation**: Loop melalui CSV nomor pelacakan dan hasilkan PNG untuk masing‑masing.  
- **Dynamic sizing**: Ekspos X‑dimension dan tinggi bar sebagai parameter konfigurasi dalam API web.  
- **Integration with label printers**: Kirim byte PNG langsung ke printer kompatibel ZPL untuk pembuatan label on‑the‑fly.

Silakan bereksperimen—ganti string data, coba dimensi berbeda, atau gabungkan barcode dengan QR code pada label yang sama. Perpustakaan barcode cukup fleksibel untuk menangani semua itu.

Ada skenario rumit yang belum Anda pahami? Tinggalkan komentar di bawah, dan kami akan membantu memecahkannya bersama. Selamat coding!

## What Should You Learn Next?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Buat gambar barcode DotCode – baris & kolom (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Buat gambar barcode C# – Contoh GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Buat gambar barcode c# – Konfigurasi Baris & Kolom Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}