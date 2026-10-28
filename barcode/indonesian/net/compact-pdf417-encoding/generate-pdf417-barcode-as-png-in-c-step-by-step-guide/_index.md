---
category: general
date: 2026-10-28
description: Hasilkan kode batang PDF417 dalam C# dan ekspor sebagai gambar PNG. Pelajari
  cara mengonfigurasi tata letak, mengatur kolom dan baris, serta menyimpan file.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- barcode generator PNG
- how to set PDF417
- how to generate PNG barcode
- how to configure PDF417 barcode
language: id
lastmod: 2026-10-28
og_description: Buat kode batang PDF417 dalam C# dan simpan sebagai gambar PNG. Ikuti
  panduan lengkap ini untuk mengatur tata letak, menentukan kolom dan baris, serta
  menghasilkan file kode batang berkualitas tinggi.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG file
og_title: Buat kode batang PDF417 sebagai PNG – tutorial C#
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate PDF417 barcode in C# and export it as a PNG image. Learn how
    to configure layout, set columns and rows, and save the file.
  headline: Generate PDF417 barcode as PNG in C# – step‑by‑step guide
  type: TechArticle
tags:
- C#
- PDF417
- barcode
- image generation
title: Menghasilkan barcode PDF417 sebagai PNG di C# – panduan langkah demi langkah
url: /id/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hasilkan kode batang PDF417 sebagai PNG di C# – panduan langkah demi langkah

Jika Anda perlu **generate PDF417 barcode** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara membuat kode batang dan menyimpannya sebagai gambar PNG. Anda akan belajar cara mengonfigurasi tata letak kode batang, mengatur jumlah kolom dan baris, serta menghasilkan file yang dapat digunakan dalam inventaris, tiket, atau skenario pemindaian seluler.

Tutorial ini mencakup semuanya mulai dari menginstal pustaka yang diperlukan hingga menangani kasus tepi seperti nilai tata letak yang tidak valid. Tidak diperlukan dokumentasi eksternal—cukup salin kode, jalankan, dan Anda akan memiliki gambar kode batang siap pakai.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terinstal  
* Lingkungan pengembangan C# (Visual Studio, VS Code, atau Rider)  
* Akses internet untuk mengunduh paket NuGet **Aspose.BarCode for .NET** (pustaka yang digunakan dalam contoh)  

Persyaratan ini memastikan kode dapat dikompilasi dan dijalankan tanpa konfigurasi tambahan.

## Langkah 1: Instal pustaka kode batang

Cara paling sederhana untuk mendapatkan kemampuan **barcode generator PNG** adalah dengan menggunakan paket resmi Aspose.BarCode. Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Perintah ini menambahkan pustaka dan dependensinya ke file proyek Anda. Setelah instalasi berhasil, Anda dapat merujuk kelas‑kelas dalam file sumber C# Anda.

## Langkah 2: Buat generator kode batang PDF417

Membuat objek kode batang adalah dasar dari proses. Potongan kode berikut membuat generator yang mengkodekan teks `"Sample"` menggunakan simbol PDF417.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for PDF417
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Mengapa langkah ini penting* – Kelas `BarcodeGenerator` mengenkapsulasi semua pengaturan yang diperlukan untuk rendering. Dengan menentukan `EncodeTypes.Pdf417`, Anda memberi tahu pustaka untuk menghasilkan **PDF417 barcode**, yang merupakan kode linear bertumpuk ideal untuk menyimpan sejumlah besar data.

## Langkah 3: Cara mengatur kolom dan baris PDF417

Kode batang PDF417 dapat disesuaikan dengan mengatur matriksnya. Dua parameter paling umum adalah **columns** (modul horizontal) dan **rows** (modul vertikal). Mengontrol nilai‑nilai ini memengaruhi ukuran dan keterbacaan kode batang.

```csharp
        // Step 3: Configure a custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // allowed range: 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // allowed range: 1‑90
```

### Cara mengonfigurasi kode batang PDF417 untuk dimensi tertentu

* Gunakan nilai dalam rentang yang didokumentasikan; angka di luar rentang akan memicu pengecualian.  
* Jumlah kolom yang lebih tinggi memampatkan kode batang secara horizontal, sementara lebih banyak baris meningkatkan tinggi vertikal.  
* Sesuaikan tata letak agar cocok dengan permukaan cetak target atau jarak pemindaian.

Jika Anda memerlukan bentuk yang berbeda, ubah angka‑angka tersebut sesuai kebutuhan. Pustaka secara otomatis menghitung ulang ukuran modul untuk menjaga kode batang tetap dapat dipindai.

## Langkah 4: Cara menghasilkan kode batang PNG

Menyimpan kode batang sebagai file PNG adalah operasi satu baris setelah generator dikonfigurasi sepenuhnya. PNG menyediakan kompresi lossless, menjadikannya ideal untuk gambar kode batang yang tajam.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        generator.Save("CustomLayout.png", BarCodeImageFormat.Png);
    }
}
```

*Mengapa PNG* – Enum `BarCodeImageFormat.Png` memberi tahu pustaka untuk merender kode batang menggunakan format PNG. Format ini mempertahankan tepi yang tajam, yang penting bagi pemindai kode batang yang mengandalkan tepi kontras tinggi.

### Output yang diharapkan

Menjalankan program membuat file bernama **CustomLayout.png** di direktori kerja aplikasi. Membuka file tersebut menampilkan kode batang PDF417 berbentuk persegi panjang dengan empat kolom dan sembilan baris, mengkodekan string `"Sample"`.

![Generate PDF417 barcode as PNG](https://example.com/images/pdf417-custom.png "Generate PDF417 barcode as PNG")

*​Teks alt gambar*: **Generate PDF417 barcode as PNG** – gambar kode batang yang dihasilkan oleh kode tutorial.

## Langkah 5: Verifikasi kode batang dan selesaikan masalah umum

Setelah menghasilkan gambar, Anda harus memverifikasi bahwa pemindai atau alat validasi dapat membacanya. Berikut beberapa pemeriksaan cepat:

| Masalah | Penyebab | Solusi |
|---------|----------|--------|
| Barcode buram | Gambar diubah ukurannya setelah pembuatan | Pertahankan ukuran PNG asli; hindari skala di kontrol UI |
| Pemindai melaporkan “data tidak valid” | Kolom/baris di luar jangkauan atau data terlalu panjang untuk tata letak yang dipilih | Kurangi jumlah teks yang dikodekan atau tingkatkan baris/kolom |
| File PNG kosong | Path `generator.Save` mengarah ke direktori yang tidak ada | Pastikan direktori ada atau gunakan path absolut |

**Pro tip:** Jika Anda membutuhkan latar belakang transparan (mis., menempatkan kode batang di atas elemen UI), setel `generator.Parameters.Image.TransparentBackground = true;` sebelum memanggil `Save`.

## Contoh lengkap yang berfungsi

Berikut adalah program lengkap yang dapat Anda salin, tempel, dan jalankan tanpa modifikasi (kecuali jalur output jika diinginkan).

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417 with sample data
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // Configure custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 1‑90

        // Optional: make background transparent
        generator.Parameters.Image.TransparentBackground = true;

        // Save the barcode as a PNG file
        string outputPath = "CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Menjalankan program mencetak pesan konfirmasi dan menghasilkan `CustomLayout.png` di folder yang sama dengan executable.

## Kesimpulan

Anda sekarang tahu cara **generate PDF417 barcode** di C#, mengonfigurasi tata letaknya dengan kolom dan baris tertentu, dan mengekspor hasilnya sebagai gambar **barcode PNG**. Langkah‑langkah tersebut mencakup menginstal pustaka Aspose.BarCode, menginisialisasi generator, menerapkan dimensi khusus, menyimpan file, dan memverifikasi output.

Dari sini Anda dapat menjelajahi pengaturan tambahan seperti tingkat koreksi kesalahan, margin kode batang, atau menyematkan gambar langsung ke dalam laporan PDF. Setiap topik tersebut dibangun di atas pola inti yang ditunjukkan dalam panduan ini, sehingga Anda siap menyesuaikan solusi untuk skenario pembuatan kode batang .NET apa pun.

---


## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang dibangun di atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [How to generate PDF417 barcode in C# and set barcode size](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}