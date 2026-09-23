---
category: general
date: 2026-07-18
description: Buat kode batang GS1 dalam C# dan pelajari cara menghasilkan gambar kode
  batang, mengatur kolom, serta menggunakan Barcode Generator C# untuk hasil yang
  sempurna.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode
- how to generate barcode
- how to set columns
- barcode generator c#
- create barcode image
language: id
lastmod: 2026-07-18
og_description: Buat barcode GS1 di C# dengan cepat. Pelajari cara menghasilkan gambar
  barcode, mengonfigurasi kolom, dan menguasai Barcode Generator C# dalam hitungan
  menit.
og_image_alt: Screenshot showing a generated GS1 Micro PDF417 barcode image
og_title: Buat Kode Batang GS1 di C# – Panduan Pemrograman Lengkap
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode in C# and learn how to generate barcode images,
    set columns, and use Barcode Generator C# for flawless results.
  headline: Create GS1 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create GS1 barcode in C# and learn how to generate barcode images,
    set columns, and use Barcode Generator C# for flawless results.
  name: Create GS1 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: What if I need a different image format?
    text: Just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The library handles the conversion automatically.
  - name: Can I generate multiple barcodes in a loop?
    text: Absolutely. Wrap the generator creation and `Save` call inside a `foreach`
      that iterates over your data set. Remember to reset or create a fresh `BarcodeGenerator`
      instance for each unique data string to avoid parameter bleed‑over.
  - name: How does error handling work?
    text: 'If the data string violates GS1 rules (e.g., missing mandatory AI), the
      library throws a `BarcodeException`. Catch it and log the problematic input:'
  - name: What about DPI settings for printing?
    text: 'You can control the output resolution via `barcodeGenerator.Parameters.ImageResolution`.
      For high‑quality printouts, set it to 300 dpi:'
  type: HowTo
tags:
- barcode
- C#
- GS1
title: Buat Kode Bar GS1 di C# – Panduan Lengkap Langkah-demi-Langkah
url: /id/net/gs1-barcode-encoding/create-gs1-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Barcode GS1 di C# – Panduan Lengkap Langkah-demi-Langkah

Pernah bertanya-tanya bagaimana cara **create GS1 barcode** menggunakan C# tanpa membuat frustasi? Anda tidak sendirian. Baik Anda membangun sistem pemindaian gudang atau perlu menyematkan data produk dalam aplikasi seluler, menguasai pembuatan barcode GS1 adalah keterampilan penting bagi setiap pengembang .NET.

Dalam tutorial ini kami akan membahas langkah‑langkah tepat untuk membuat gambar **create GS1 barcode**, menjelaskan **how to generate barcode** file dengan pengaturan yang disesuaikan, dan menunjukkan trik‑trik kecil yang membuat seluruh proses menjadi mudah. Pada akhir tutorial Anda akan memiliki file PNG siap pakai dan pemahaman yang jelas tentang API yang mendasarinya.

## Prasyarat

- .NET 6.0 atau yang lebih baru terpasang (kode ini juga bekerja dengan .NET Framework 4.7+).
- Referensi ke pustaka **Barcode Generator C#** (misalnya, Aspose.BarCode untuk .NET atau paket NuGet yang kompatibel).
- Folder di disk tempat Anda dapat menulis gambar output (contoh menggunakan `YOUR_DIRECTORY` – ganti dengan jalur yang sebenarnya).

Tidak diperlukan alat eksternal lainnya.

## Cara Membuat GS1 Barcode di C# – Ikhtisar

Kami akan membagi solusi menjadi empat bagian logis:

1. **Instantiate the barcode generator** dengan simbol GS1 Micro PDF417 dan string data mentah.
2. **Configure visual parameters** seperti X‑dimension (lebar modul) untuk rendering yang lebih tajam.
3. **Set the column count** untuk mengontrol tata letak matriks – di sinilah **how to set columns** menjadi penting.
4. **Save the result** sebagai file PNG, menyelesaikan langkah **create barcode image**.

Setiap bagian berhubungan dengan potongan kode kecil yang dapat diuji, sehingga Anda dapat menyalin‑tempel dan menjalankannya secara langsung.

---

## Langkah 1: Instantiate the Barcode Generator (Create GS1 Barcode)

Hal pertama yang perlu Anda lakukan adalah membuat instance dari `BarcodeGenerator`. Objek ini akan menyimpan semua pengaturan dan data yang diperlukan untuk output **create GS1 barcode**.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for GS1 Micro PDF417 with the required data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(01)12345678901231(240)ABCD123456789012345");
```

> **Mengapa ini penting:** `EncodeTypes.GS1MicroPdf417` enum memberi tahu pustaka bahwa Anda menginginkan simbol Micro PDF417 yang mematuhi GS1, dan string data mengikuti sintaks GS1 Application Identifier (AI). Memastikan format AI benar adalah dasar dari operasi **create GS1 barcode** yang valid.

---

## Langkah 2: Fine‑Tune the X‑Dimension (How to Generate Barcode with Better Detail)

Keterbacaan barcode sering bergantung pada lebar modul, yang dikenal sebagai X‑dimension. Menetapkannya ke jumlah piksel yang lebih rendah menghasilkan detail yang lebih halus, yang dapat penting untuk label kecil.

```csharp
// Step 2: Set the X‑dimension (module width) to 2 pixels for finer detail
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tips profesional:** Jika Anda berencana mencetak barcode pada printer beresolusi tinggi, 2 piksel adalah nilai default yang aman. Untuk layar beresolusi rendah, Anda dapat meningkatkan menjadi 3 atau 4 piksel untuk menghindari tepi yang buram.

---

## Langkah 3: How to Set Columns – Mengontrol Matriks PDF417

Keluarga PDF417 memungkinkan Anda menentukan jumlah kolom dalam matriksnya. Ini memengaruhi ukuran fisik dan kinerja pemindaian. Berikut potongan kode yang menjawab **how to set columns** untuk barcode GS1 Micro PDF417.

```csharp
// Step 3: Define the number of columns in the PDF417 matrix (4 columns)
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

> **Kapan mengubahnya:** Jika ruang label Anda terbatas secara horizontal, kurangi jumlah kolom. Sebaliknya, tingkatkan kolom untuk jejak vertikal yang lebih kompak. Pustaka akan secara otomatis menyesuaikan jumlah baris untuk menampung data.

---

## Langkah 4: Save the Barcode – Create Barcode Image

Sekarang generator telah dikonfigurasi sepenuhnya, Anda akhirnya dapat **create barcode image** dengan menyimpannya ke disk. Baris berikut menulis file PNG, tetapi Anda juga dapat memilih JPEG, BMP, atau GIF.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/GS1MicroPdf417_903to905.png", BarCodeImageFormat.Png);
```

> **Output yang diharapkan:** Setelah menjalankan program, `GS1MicroPdf417_903to905.png` akan muncul di folder target. Buka dengan penampil gambar apa pun dan Anda akan melihat simbol GS1 Micro PDF417 yang bersih dan dapat dipindai.

---

## Contoh Lengkap yang Berfungsi

Berikut adalah program lengkap yang dapat dijalankan yang menggabungkan keempat langkah. Salin ke dalam proyek konsol baru dan tekan **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a barcode generator for GS1 Micro PDF417 with the required data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.GS1MicroPdf417,
                "(01)12345678901231(240)ABCD123456789012345");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels for finer detail
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns in the PDF417 matrix (4 columns)
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;

            // 4️⃣ Save the generated barcode as a PNG image
            const string outputPath = @"C:\Temp\GS1MicroPdf417_903to905.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"GS1 barcode created successfully at: {outputPath}");
        }
    }
}
```

**Menjalankan kode ini** akan menghasilkan file PNG yang dapat Anda sematkan dalam laporan, cetak pada kemasan produk, atau kirim ke aplikasi pemindaian seluler. Pesan konsol mengonfirmasi lokasi, yang berguna untuk debugging cepat.

---

## Pertanyaan Umum & Kasus Tepi

### Bagaimana jika saya membutuhkan format gambar yang berbeda?

Cukup ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg`, `Bmp`, atau `Gif`. Pustaka menangani konversi secara otomatis.

### Bisakah saya menghasilkan banyak barcode dalam loop?

Tentu saja. Bungkus pembuatan generator dan pemanggilan `Save` di dalam `foreach` yang mengiterasi kumpulan data Anda. Ingat untuk mereset atau membuat instance `BarcodeGenerator` baru untuk setiap string data unik agar tidak terjadi tumpang‑tindih parameter.

### Bagaimana cara kerja penanganan error?

Jika string data melanggar aturan GS1 (mis., AI wajib hilang), pustaka akan melempar `BarcodeException`. Tangkap dan catat input yang bermasalah:

```csharp
try
{
    // generator code here
}
catch (BarcodeException ex)
{
    Console.Error.WriteLine($"Invalid GS1 data: {ex.Message}");
}
```

### Bagaimana dengan pengaturan DPI untuk pencetakan?

Anda dapat mengontrol resolusi output melalui `barcodeGenerator.Parameters.ImageResolution`. Untuk cetakan berkualitas tinggi, setel ke 300 dpi:

```csharp
barcodeGenerator.Parameters.ImageResolution = 300;
```

---

## Hasil Visual

Berikut adalah gambar placeholder yang menggambarkan seperti apa output **create GS1 barcode** akhir.

![GS1 Micro PDF417 barcode generated by C# code – create barcode image](https://example.com/gs1-micro-pdf417-sample.png)

*Teks alt:* **Barcode GS1 Micro PDF417 yang dihasilkan oleh kode C# – create barcode image**

---

## Ringkasan: Apa yang Kami Capai

- **Create GS1 barcode** menggunakan pustaka Aspose.BarCode.
- Mempelajari **how to generate barcode** dengan X‑dimension khusus untuk rendering yang tajam.
- Menguasai **how to set columns** untuk menyesuaikan batas label Anda.
- Menggunakan **barcode generator c#** untuk mengonfigurasi dan mengekspor **create barcode image** dalam format PNG.

Semua ini dikemas dalam alur empat langkah yang ringkas yang dapat Anda sesuaikan untuk proyek .NET apa pun.

---

## Langkah Selanjutnya & Topik Terkait

Sekarang Anda dapat membuat gambar **create GS1 barcode**, pertimbangkan untuk menjelajahi:

- [Buat gambar barcode c# – Konfigurasi Baris & Kolom Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Buat gambar barcode DotCode – baris & kolom (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Cara Membuat Zona Tenang Barcode untuk ITF-14 Menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}