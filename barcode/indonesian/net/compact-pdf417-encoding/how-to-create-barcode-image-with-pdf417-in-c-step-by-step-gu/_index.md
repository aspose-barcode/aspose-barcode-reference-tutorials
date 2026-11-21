---
category: general
date: 2026-11-20
description: Buat gambar barcode di C# menggunakan Aspose.BarCode. Pelajari cara menghasilkan
  barcode PDF417 dengan tata letak khusus dan menyimpannya sebagai PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate pdf417 barcode
- how to generate pdf417
language: id
lastmod: 2026-11-20
og_description: Buat gambar barcode di C# dengan Aspose.BarCode. Panduan ini menunjukkan
  cara menghasilkan barcode PDF417, menyesuaikan tata letak, dan mengekspor ke PNG.
og_image_alt: Screenshot of generated barcode image created with PDF417 using C#
og_title: Buat gambar barcode dengan PDF417 di C# – tutorial lengkap
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  headline: How to create barcode image with PDF417 in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  name: How to create barcode image with PDF417 in C# – step‑by‑step guide
  steps:
  - name: Why this code works
    text: '* **`BarcodeGenerator`** is the entry point for all barcode types. By passing
      `EncodeTypes.Pdf417` you tell the library to produce a PDF417 symbol. * **Columns
      and rows** are the primary levers for layout. Fewer columns produce a taller
      barcode; more columns make it wider. Adjust these values to fit'
  - name: Adjusting data length
    text: 'PDF417 can encode up to 1,850 characters. If you need to encode longer
      strings, consider splitting the data across multiple barcodes or using the **compact
      mode**:'
  - name: Controlling image size
    text: 'The default image size is calculated from the module size (the smallest
      square in the barcode). You can explicitly set the DPI or scale the image after
      generation:'
  - name: Handling special characters
    text: 'PDF417 supports the full ASCII set. If your data contains Unicode characters,
      ensure you encode the string as UTF‑8:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
title: Cara membuat gambar barcode dengan PDF417 di C# – panduan langkah demi langkah
url: /id/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar barcode dengan PDF417 di C# – panduan langkah‑demi‑langkah

Jika Anda perlu **membuat gambar barcode** dalam aplikasi .NET, panduan ini menunjukkan secara tepat **cara menghasilkan barcode PDF417** dengan tata letak khusus dan menyimpannya sebagai file PNG. Anda akan melihat kode lengkap yang dapat dijalankan, memahami mengapa setiap pengaturan penting, dan mempelajari jebakan umum sehingga barcode Anda berfungsi dengan andal di produksi.

Dalam tutorial ini Anda akan:

* Menginisialisasi generator Aspose.BarCode untuk PDF417.
* Mengonfigurasi jumlah kolom dan baris untuk mengendalikan bentuk barcode.
* Mengekspor hasilnya sebagai gambar PNG berkualitas tinggi.
* Menjelajahi pengaturan opsional untuk koreksi kesalahan dan panjang data.

Prasyarat satu-satunya adalah .NET SDK terbaru (.NET 6 atau lebih baru) serta lisensi atau percobaan gratis **Aspose.BarCode for .NET**.

---

## Prasyarat dan penyiapan

Sebelum memulai, pastikan Anda memiliki:

| Persyaratan | Mengapa penting |
|-------------|-----------------|
| .NET 6 SDK atau lebih baru | Menyediakan runtime untuk aplikasi konsol C#. |
| Visual Studio 2022 (atau VS Code) | Memberikan IDE dengan IntelliSense untuk API Aspose. |
| Paket NuGet Aspose.BarCode for .NET | Menyediakan `BarcodeGenerator`, `EncodeTypes`, dan helper ekspor gambar. |
| Izin menulis ke folder output | Generator menulis file PNG ke disk. |

Anda dapat menambahkan paket NuGet dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

---

## Langkah 1: Buat proyek konsol baru

Pertama, buat kerangka aplikasi konsol sederhana yang akan menampung logika pembuatan barcode.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The full barcode generation flow is encapsulated in GeneratePdf417().
            GeneratePdf417();
            Console.WriteLine("Barcode image created successfully.");
        }

        // -----------------------------------------------------------------
        // Generates a PDF417 barcode with a custom layout and saves it as PNG.
        // -----------------------------------------------------------------
        static void GeneratePdf417()
        {
            // -------------------------------------------------------------
            // Step 2: Initialize the barcode generator for PDF417 with text.
            // -------------------------------------------------------------
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data for PDF417 barcode");

            // -------------------------------------------------------------
            // Step 3: Define a custom layout – set the number of columns and rows.
            // -------------------------------------------------------------
            generator.Parameters.Barcode.Pdf417.Columns = 4; // Controls horizontal density.
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // Controls vertical density.

            // Optional: increase error correction level for noisy environments.
            // Values: 0 (no correction) to 8 (maximum correction).
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // -------------------------------------------------------------
            // Step 4: Save the generated barcode as a PNG image.
            // -------------------------------------------------------------
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CustomPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Mengapa kode ini berhasil

* **`BarcodeGenerator`** adalah titik masuk untuk semua jenis barcode. Dengan memberikan `EncodeTypes.Pdf417` Anda memberi tahu pustaka untuk menghasilkan simbol PDF417.
* **Kolom dan baris** adalah tuas utama untuk tata letak. Lebih sedikit kolom menghasilkan barcode yang lebih tinggi; lebih banyak kolom membuatnya lebih lebar. Sesuaikan nilai ini agar cocok dengan ruang tempat gambar akan ditampilkan (misalnya, printer label vs. halaman web).
* **Koreksi kesalahan** meningkatkan keandalan pemindaian ketika barcode mungkin ternoda atau dicetak pada media berkualitas rendah. Tingkat default adalah 0; menaikkannya sedikit (2–4) merupakan kompromi yang baik antara ukuran dan ketahanan.
* **`Save`** menulis gambar ke disk dalam format PNG, yang mempertahankan tepi tajam dan bekerja di semua peramban serta perangkat seluler.

Saat Anda menjalankan program (`dotnet run`), ia membuat `CustomPdf417.png` di folder proyek. PNG tersebut terlihat seperti ini:

![Gambar barcode PDF417 yang dihasilkan](https://example.com/images/pdf417-sample.png "Tangkapan layar gambar barcode yang dihasilkan dengan PDF417 menggunakan C#")

*Teks alternatif:* **create barcode image** – Barcode PDF417 yang dihasilkan di C# dan disimpan sebagai PNG.

---

## Langkah 2: Menyempurnakan barcode untuk skenario dunia nyata

### Menyesuaikan panjang data

PDF417 dapat mengkode hingga 1.850 karakter. Jika Anda perlu mengkode string yang lebih panjang, pertimbangkan memecah data ke beberapa barcode atau menggunakan **mode kompak**:

```csharp
generator.Parameters.Barcode.Pdf417.CompactMode = true;
```

Mode kompak mengurangi jumlah baris tetapi dapat meningkatkan kepadatan visual, jadi uji dengan pemindai Anda.

### Mengendalikan ukuran gambar

Ukuran gambar default dihitung dari ukuran modul (kotak terkecil dalam barcode). Anda dapat secara eksplisit mengatur DPI atau menskalakan gambar setelah pembuatan:

```csharp
generator.Parameters.ImageResolution = new Resolution(300); // 300 DPI for printing.
```

Atau, setelah menyimpan, ubah ukuran dengan `System.Drawing` jika Anda memerlukan thumbnail.

### Menangani karakter khusus

PDF417 mendukung seluruh set ASCII. Jika data Anda berisi karakter Unicode, pastikan Anda mengkode string sebagai UTF‑8:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, System.Text.Encoding.UTF8.GetString(bytes));
```

---

## Langkah 3: Jebakan umum dan cara menghindarinya

| Jebakan | Gejala | Solusi |
|---------|--------|--------|
| Terlalu banyak kolom untuk data yang diberikan | Barcode terpotong atau menimbulkan pengecualian. | Kurangi `Columns` atau biarkan pustaka mengatur ukuran otomatis dengan menghapus pengaturan tersebut. |
| Koreksi kesalahan rendah pada printer berisik | Pemindai gagal membaca barcode secara intermiten. | Tingkatkan `ErrorCorrectionLevel` setidaknya menjadi 2. |
| Menyimpan ke direktori hanya-baca | `UnauthorizedAccessException` saat runtime. | Gunakan folder yang dapat ditulis seperti `Environment.CurrentDirectory` atau `Path.GetTempPath()`. |
| Menggunakan versi Aspose.BarCode yang usang | Properti seperti `CompactMode` tidak tersedia. | Perbarui paket NuGet ke rilis stabil terbaru. |

---

## Langkah 4: Verifikasi hasilnya

Untuk memastikan barcode dihasilkan dengan benar, Anda dapat:

1. Buka `CustomPdf417.png` di penampil gambar apa pun – barcode harus tajam, dengan modul hitam jelas di atas latar putih.
2. Gunakan aplikasi pemindai PDF417 gratis (tersedia di iOS dan Android) untuk memindai gambar. Aplikasi harus menampilkan **“Sample data for PDF417 barcode”**.
3. (Opsional) Muat gambar dalam unit test menggunakan `System.Drawing.Bitmap` dan pastikan bahwa piksel pada `(0,0)` berwarna hitam, menegaskan bahwa gambar tidak kosong.

```csharp
using System.Drawing;

Bitmap bmp = new Bitmap("CustomPdf417.png");
bool topLeftIsBlack = bmp.GetPixel(0, 0).R == 0;
Console.WriteLine($"Top‑left pixel black? {topLeftIsBlack}");
```

Jika asersi berhasil, Anda telah berhasil **create barcode image** dan **generate PDF417 barcode** secara programatik.

---

## Kesimpulan

Anda kini tahu cara **create barcode image** di C# dengan **generating PDF417 barcode** menggunakan tata letak khusus, menyesuaikan koreksi kesalahan, dan mengekspor ke PNG. Contoh lengkap menunjukkan setiap langkah yang diperlukan—dari menginisialisasi `BarcodeGenerator` hingga menyimpan gambar akhir—sehingga Anda dapat menyalin, menempel, dan menjalankannya di proyek Anda sendiri.

Selanjutnya, Anda dapat menjelajahi:

* **Menyematkan PNG dalam API web** sehingga klien dapat meminta barcode sesuai permintaan (`generate pdf417` sebagai layanan).
* **Pembuatan batch** untuk kumpulan data besar—loop melalui daftar string dan simpan setiap PNG ke basis data.
* **Format output alternatif** (SVG, JPEG) dengan mengubah `BarCodeImageFormat`.

Silakan bereksperimen dengan rasio kolom/baris, tingkat koreksi kesalahan, dan resolusi gambar untuk memenuhi persyaratan tepat perangkat pemindai atau desain UI Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membuat gambar barcode PDF417 di C# – panduan lengkap](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)
- [Cara membuat gambar barcode PDF417 di C# dengan opsi Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Cara membuat barcode micro pdf417 dan menghasilkan PNG di C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}