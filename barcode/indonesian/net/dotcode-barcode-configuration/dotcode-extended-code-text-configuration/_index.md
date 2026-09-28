---
date: 2026-09-28
description: Pelajari cara membuat barcode matriks 2d dengan Aspose.BarCode for .NET
  – panduan langkah demi langkah untuk menghasilkan barcode DotCode dengan teks kode
  yang diperluas.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: Konfigurasi Teks Kode Diperluas DotCode
og_description: Pelajari cara membuat barcode matriks 2d menggunakan Aspose.BarCode
  for .NET. Panduan ini menunjukkan langkah demi langkah cara menghasilkan barcode
  DotCode dengan teks kode yang diperluas.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Buat barcode matriks 2d dengan Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Cara membuat barcode matriks 2d via Aspose.BarCode for .NET
url: /id/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode matriks 2d via Aspose.BarCode untuk .NET

## Pendahuluan

Dalam bidang pembuatan dan pengelolaan barcode, Aspose.BarCode untuk .NET menonjol sebagai solusi serbaguna yang mendukung **lebih dari 50 format input dan output** dan dapat memproses dokumen ratusan halaman tanpa memuat seluruh file ke memori. Baik Anda memerlukan barcode untuk pelacakan produk, kontrol inventaris, atau aplikasi kaya data, membuat **barcode matriks 2d** seperti DotCode dengan codetext yang diperluas memungkinkan Anda menyematkan payload teks dan biner dalam simbol kotak yang kompak. Tutorial ini memandu Anda membangun codetext yang diperluas langkah demi langkah dan merender gambar akhir.

## Jawaban Cepat
- **Apa arti “create dotcode extended codetext”?** Artinya membuat barcode DotCode yang mencakup FNC1, ECICodetext, teks biasa, dan pemisah simbol dalam satu payload yang diperluas.  
- **Perpustakaan apa yang diperlukan?** Aspose.BarCode untuk .NET.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh dasar.

## Cara membuat dotcode extended codetext

Muat proyek Anda, atur direktori, bangun extended codetext, dan hasilkan gambar – semua dalam kurang dari selusin baris kode. Jawaban langsung berikut merangkum seluruh proses:

Muat `BarcodeGenerator` dengan `EncodeTypes.DotCode`, bangun extended codetext menggunakan `DotCodeExtendedCodetextBuilder` (menambahkan FNC1, ECICodetext, teks biasa, dan pemisah FNC3), kemudian panggil `Save` untuk menulis file PNG. Urutan ini membuat barcode matriks 2d yang sepenuhnya sesuai dalam satu panggilan.

## Apa itu dotcode extended codetext?

**dotcode extended codetext** adalah string komposit yang menggabungkan beberapa segmen data—seperti pengidentifikasi FNC1, ECICodetext, teks biasa, dan pemisah FNC3—menjadi satu payload yang dapat didekode oleh DotCode. Ini memungkinkan pengkodean teks multibahasa, blob biner, dan data terstruktur dalam satu barcode matriks 2d, menjadikannya ideal untuk skenario rantai pasokan, perawatan kesehatan, dan IoT.

## Mengapa menggunakan Aspose.BarCode untuk tugas ini?

Aspose.BarCode memproses **hingga 500 halaman per detik** pada perangkat keras server tipikal dan mendukung **lebih dari 30 simbol barcode**, termasuk DotCode. API `GetExtendedCodetext`‑nya menjamin penempatan karakter kontrol yang tepat, menghilangkan kesalahan penggabungan string manual dan memastikan kepatuhan dengan ISO/IEC 24724. Selain itu, ia menawarkan koreksi kesalahan bawaan dan penanganan zona tenang otomatis, mengurangi kebutuhan penyesuaian manual.

## Prasyarat

- **Aspose.BarCode untuk .NET** – unduh dari [dokumentasi Aspose.BarCode untuk .NET](https://reference.aspose.com/barcode/net/).  
- Lingkungan pengembangan .NET (Visual Studio 2022 atau yang lebih baru disarankan).  
- Opsional: file lisensi sementara untuk evaluasi.

## Impor namespace

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Namespace ini menyediakan kelas `BarcodeGenerator` dan pembantu `DotCodeExtendedCodetextBuilder` yang diperlukan untuk contoh.

```csharp
using Aspose.BarCode.Generation;
```

Setelah prasyarat terpenuhi, mari kita uraikan proses menghasilkan DotCode Extended Code Text dalam panduan langkah demi langkah.

## Langkah 1: tentukan jalur direktori

Tentukan di mana PNG yang dihasilkan akan disimpan. Gunakan jalur absolut atau relatif yang dapat ditulis oleh aplikasi Anda.

```csharp
string path = "Your Directory Path";
```

Ganti `"Your Directory Path"` dengan jalur sebenarnya pada sistem Anda.

## Langkah 2: buat dotcode extended codetext

Kelas `DotCodeExtendedCodetextBuilder` menyusun berbagai segmen menjadi satu string extended codetext.

Untuk membuat DotCode Extended Code Text, ikuti sub‑langkah berikut:

### 2.1 tambahkan pengidentifikasi format fnc1

Pengidentifikasi format FNC1 menandai awal bidang data baru. Ini diperlukan untuk simbol DotCode yang mematuhi GS1.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 tambahkan ecicodetext

ECICodetext mengkodekan karakter khusus dan teks internasional. Pada contoh ini kami mengkodekan `"犬Right狗"` menggunakan UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 tambahkan plain codetext

Anda juga dapat menambahkan teks biasa ke DotCode Extended Code Text. Di sini, kami menambahkan `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 tambahkan pemisah simbol fnc3

Pemisah simbol FNC3 memisahkan bagian-bagian kode yang berbeda, meningkatkan keterbacaan bagi pemindai.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 tambahkan inisialisasi pembaca fnc3

Langkah ini menambahkan informasi Inisialisasi Pembaca FNC3, yang memberi tahu pemindai cara menafsirkan data berikutnya.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 hasilkan codetext

Sekarang hasilkan DotCode Extended Codetext dengan memanggil metode `GetExtendedCodetext` pada objek `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Langkah 3: hasilkan gambar dotcode

Render gambar barcode dari extended codetext.

#### 3.1 inisialisasi barcode generator

Kelas `BarcodeGenerator` adalah objek inti Aspose.BarCode untuk membuat barcode apa pun. Anda menginstansiasinya dengan simbolologi yang diinginkan (`EncodeTypes.DotCode`) dan extended codetext yang baru saja Anda bangun.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Akhirnya, panggil `Save` untuk menulis file PNG ke disk. Gambar siap untuk disematkan dalam laporan, aplikasi seluler, atau label cetak.

## Masalah umum dan solusi

- **Encoding tidak tepat** – Pastikan Anda menggunakan `ECIEncodings.UTF8` saat menambahkan teks multibahasa; jika tidak, karakter dapat menjadi rusak.  
- **Kesalahan akses file** – Verifikasi aplikasi memiliki izin menulis ke direktori target.  
- **Zona tenang tidak ada** – Atur `gen.Parameters.Barcode.Margin` jika pemindai memerlukan ruang putih tambahan di sekitar simbol.

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menggunakan barcode yang dihasilkan dalam aplikasi seluler?**  
A: Ya. Gambar PNG yang dihasilkan oleh generator dapat disematkan di iOS, Android, atau aplikasi seluler lintas‑platform apa pun.

**Q: Bagaimana jika saya perlu mengkodekan data biner alih-alih teks?**  
A: Gunakan metode `AddECICodetext` dengan `ECIEncodings` yang sesuai (mis., `ECIEncodings.Base64`) untuk menyematkan payload biner.

**Q: Bagaimana cara mengubah ukuran barcode tanpa memengaruhi keterbacaan?**  
A: Sesuaikan properti `XDimension.Pixels`; nilai yang lebih tinggi meningkatkan ukuran modul, sementara nilai yang lebih rendah membuat barcode lebih kompak.

**Q: Apakah ada cara menambahkan zona tenang di sekitar barcode?**  
A: Ya. Atur `gen.Parameters.Barcode.Margin` untuk menentukan zona tenang yang diinginkan dalam piksel.

**Q: Apakah perpustakaan ini mendukung .NET 8?**  
A: Rilis terbaru Aspose.BarCode kompatibel dengan .NET 8; cukup referensikan versi paket NuGet yang sesuai.

Jika Anda memerlukan panduan lebih lanjut atau memiliki pertanyaan, jangan ragu mengunjungi [dokumentasi Aspose.BarCode untuk .NET](https://reference.aspose.com/barcode/net/) atau berinteraksi dengan komunitas di [forum dukungan Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-09-28  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## Tutorial Terkait

- [Buat Barcode DotCode .NET (Mode Otomatis) dengan Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Cara Menghasilkan Barcode DataMatrix Menggunakan Aspose.BarCode untuk .NET – Panduan Langkah demi Langkah](/barcode/net/datamatrix-barcode-configuration/)
- [Cara membuat barcode Aztec dengan Aspose.BarCode untuk .NET](/barcode/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}