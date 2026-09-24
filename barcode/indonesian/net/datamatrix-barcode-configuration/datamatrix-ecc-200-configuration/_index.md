---
date: 2026-08-02
description: Pelajari cara membuat barcode DataMatrix, menghasilkan DataMatrix, dan
  menjelajahi pembuatan barcode berdensitas tinggi dengan Aspose.BarCode untuk proyek
  .NET.
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: Konfigurasi DataMatrix ECC 200
og_description: Buat barcode DataMatrix dengan Aspose.BarCode untuk .NET. Tutorial
  ini menunjukkan pembuatan barcode berdensitas tinggi, penyiapan lisensi sementara
  Aspose, dan kode C# langkah demi langkah.
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: Buat barcode DataMatrix – panduan Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: Cara membuat barcode DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET
url: /id/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET

## Pendahuluan

Dalam panduan ini Anda akan **membuat barcode DataMatrix** (ECC 200) menggunakan Aspose.BarCode untuk .NET. Baik Anda sedang membangun pelacak inventaris, sistem point‑of‑sale, atau mengotomatiskan alur kerja dokumen, barcode berkapasitas tinggi dapat menyimpan banyak data dalam ruang yang sangat kecil. Kami akan membahas setiap langkah konfigurasi, menjelaskan mengapa setiap pengaturan penting, dan memberikan cuplikan C# yang siap dijalankan.

## Jawaban Cepat
- **Perpustakaan apa yang terbaik untuk DataMatrix di .NET?** Aspose.BarCode for .NET  
- **Level ECC mana yang disediakan oleh ECC 200?** Koreksi kesalahan berkapasitas tinggi untuk pemindaian yang andal.  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Lisensi sementara dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Bisakah saya menghasilkan PNG, JPEG, atau TIFF?** Ya – metode `Save` mendukung berbagai format gambar.

## Apa itu DataMatrix ECC 200?

DataMatrix ECC 200 adalah barcode dua dimensi berkapasitas tinggi yang dapat menyimpan hingga 2.335 karakter alfanumerik atau 1.556 byte data biner dalam pola persegi atau persegi panjang yang kompak. Ia menggunakan koreksi kesalahan Reed‑Solomon untuk memulihkan modul yang hilang atau rusak, menjadikannya ideal untuk aplikasi seperti penandaan komponen dirgantara, pelabelan farmasi, dan logistik di mana keandalan sangat penting.

## Mengapa menggunakan pembuatan barcode Aspose?

Aspose.BarCode mendukung **30+ symbologies**, dapat merender gambar hingga 10.000 × 10.000 px tanpa memuat seluruh file ke memori, dan menyediakan output deterministik di Windows, Linux, dan macOS. API-nya memungkinkan Anda mengontrol setiap parameter rendering, menjadikannya pilihan paling fleksibel untuk skenario **barcode generation ASP.NET**.

## Prasyarat

1. **Lingkungan Pengembangan** – Visual Studio dengan .NET framework yang sesuai terinstal.  
2. **Aspose.BarCode untuk .NET** – Unduh dan instal dari situs web, [di sini](https://releases.aspose.com/barcode/net/).  
3. **Lisensi** – Dapatkan lisensi sementara untuk pengujian dari [di sini](https://purchase.aspose.com/temporary-license/).  
4. **Dasar-dasar C#** – Familiaritas dengan sintaks C# dan struktur proyek.

Setelah kita mencakup dasar-dasarnya, mari lanjutkan ke konfigurasi DataMatrix ECC 200.

## Impor Namespace

Namespace `Aspose.BarCode.Generation` berisi semua kelas yang diperlukan untuk pembuatan barcode. Impor di bagian atas file Anda:

```csharp
using Aspose.BarCode.Generation;
```

## Cara membuat barcode DataMatrix (ECC 200) langkah demi langkah

Untuk menghasilkan barcode DataMatrix ECC 200, Anda cukup memuat data yang ingin dienkode, mengonfigurasi beberapa parameter kunci pada `BarcodeGenerator`, dan kemudian memanggil `Save` untuk menulis file gambar. Alur tiga langkah ini menangani enkoding, koreksi kesalahan, dan pemilihan format output, memungkinkan Anda mengintegrasikan pembuatan barcode ke dalam aplikasi .NET apa pun dengan kode minimal.

### Langkah 1: Inisialisasi Barcode Generator

`BarcodeGenerator` adalah kelas inti Aspose.BarCode yang membuat dan merender barcode. Ia menerima tipe simbol dan teks yang akan dienkode.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

Ganti `"Your Directory Path"` dengan folder tempat Anda ingin menyimpan gambar.

### Langkah 2: Atur XDimension dan Tipe ECC

`XDimension` menentukan ukuran piksel setiap modul DataMatrix, sementara `DataMatrixEcc` memilih tingkat koreksi kesalahan. ECC 200 menyediakan kemampuan koreksi tertinggi untuk simbol ini.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

Sesuaikan nilai piksel jika Anda membutuhkan modul yang lebih besar atau lebih kecil; nilai tipikal adalah 4‑6 px untuk tampilan di layar dan 8‑10 px untuk label cetak.

### Langkah 3: Hasilkan dan Simpan Gambar Barcode

Metode `Save` menulis barcode ke sebuah file. Anda dapat memilih PNG, JPEG, atau TIFF dengan memberikan nilai enum `BarCodeImageFormat` yang sesuai.

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg` atau `BarCodeImageFormat.Tiff` jika alur kerja Anda memerlukan format yang berbeda.

## Masalah Umum & Pemecahan Masalah

| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| Barcode terlihat buram | XDimension terlalu rendah | Tingkatkan `XDimension.Pixels` menjadi 6‑8 |
| Pemindaian gagal pada ponsel | Level ECC salah | Pastikan `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| File tidak dibuat | String path tidak valid | Gunakan path absolut atau pastikan folder ada |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan kode ini dalam aplikasi konsol .NET Core?**  
J: Ya, API yang sama berfungsi di proyek .NET Core, .NET 5, dan .NET 6.

**T: Bagaimana cara mengubah format output menjadi JPEG?**  
J: Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg` pada pemanggilan `Save`.

**T: Apakah memungkinkan menyematkan barcode langsung ke dalam PDF?**  
J: Ya – buat gambar terlebih dahulu, lalu tambahkan ke PDF menggunakan Aspose.PDF atau perpustakaan PDF apa pun.

**T: Bagaimana jika saya perlu mengkodekan karakter Unicode?**  
J: DataMatrix mendukung UTF‑8; cukup berikan string Unicode ke generator seperti yang ditunjukkan.

**T: Apakah perpustakaan ini mendukung pembuatan batch banyak barcode?**  
J: Tentu – letakkan kode pembuatan di dalam loop dan ubah data/nilai untuk setiap iterasi.

## Kesimpulan

Kami telah membahas semua yang Anda perlukan untuk **membuat barcode DataMatrix** (ECC 200) dengan Aspose.BarCode untuk .NET: mulai dari prasyarat dan impor namespace hingga mengonfigurasi X‑dimension, memilih level ECC, dan menyimpan gambar dalam format pilihan Anda. Bereksperimenlah dengan banyak properti tambahan—seperti margin, warna latar belakang, dan rotasi—untuk menyempurnakan output sesuai kebutuhan spesifik Anda.

Jika Anda mengalami tantangan apa pun, komunitas siap membantu di [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13). Selamat coding!

---

**Terakhir Diperbarui:** 2026-08-02  
**Diuji Dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Menghasilkan Barcode DataMatrix ECC 000-140 dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [Cara Membaca Barcode DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-reading/)
- [Buat Barcode PNG – Rasio Aspek DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}