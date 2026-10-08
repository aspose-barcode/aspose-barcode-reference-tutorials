---
date: 2026-09-28
description: Pelajari cara membaca datamatrix dan cara menghasilkan kode batang datamatrix
  dengan mudah menggunakan Aspose.BarCode for .NET. Jelajahi panduan pemrograman pembaca,
  structured append, dan pembuatan.
keywords:
- how to read datamatrix
- datamatrix barcode reading
- Aspose.BarCode .NET
lastmod: 2026-09-28
linktitle: Membaca Kode Batang DataMatrix
og_description: Cara membaca kode batang datamatrix menggunakan Aspose.BarCode for
  .NET – panduan cepat lintas‑platform yang mencakup pembacaan, structured append,
  dan pembuatan. (150‑160 karakter)
og_image_alt: Screenshot of Aspose.BarCode reading a DataMatrix barcode in a .NET
  app
og_title: Cara membaca kode batang datamatrix dengan Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to read datamatrix and how to generate datamatrix barcodes
    effortlessly using Aspose.BarCode for .NET. Explore reader programming, structured
    append and generation guides.
  headline: How to read datamatrix barcodes with Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. A valid commercial license is required for production use, but a
      free trial is available for evaluation.
    question: Can I use Aspose.BarCode for commercial projects?
  - answer: Absolutely. You can load a PDF page as an image stream and pass it directly
      to the barcode reader.
    question: Does the library support reading DataMatrix from PDF files?
  - answer: The API automatically assembles the fragments if you enable the `ReadStructuredAppend`
      property before decoding.
    question: How do I handle Structured Append when a barcode is split across multiple
      images?
  - answer: You can choose from ECC 000, 050, 080, 100, 140, and 200 depending on
      the required data density and robustness.
    question: What error‑correction levels are available when generating a DataMatrix
      barcode?
  - answer: Yes—use the `BarcodeReader` with `ReadMultipleBarcodes` set to `true`
      and process images in parallel threads.
    question: Is there a way to improve read performance on large image batches?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix
- Aspose.BarCode
- .NET barcode processing
title: Cara membaca kode batang datamatrix dengan Aspose.BarCode for .NET
url: /id/net/datamatrix-barcode-reading/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca Barcode DataMatrix

Jika Anda perlu **cara membaca datamatrix** secara efisien dalam lingkungan .NET, panduan ini memberikan langkah‑demi‑langkah cara membaca, mengonfigurasi structured append, dan menghasilkan barcode DataMatrix dengan Aspose.BarCode untuk .NET. Anda akan melihat mengapa perpustakaan ini menjadi pilihan utama, apa yang harus dipersiapkan sebelumnya, dan di mana menemukan potongan kode yang paling berguna.

## Jawaban Cepat
- **Apa itu DataMatrix?** Sebuah barcode matriks dua dimensi yang menyimpan sejumlah besar data dalam jejak yang sangat kecil.  
- **Perpustakaan mana yang membantu Anda membaca DataMatrix di .NET?** Aspose.BarCode untuk .NET.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya juga menghasilkan barcode DataMatrix?** Ya—gunakan API yang sama untuk **cara menghasilkan datamatrix** barcode dengan pengaturan khusus.  
- **Platform yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7 di Windows, Linux, dan macOS.

## Apa itu Pembacaan Barcode DataMatrix?
Membaca barcode DataMatrix mengekstrak teks atau data biner yang dikodekan dari gambar, halaman PDF, atau frame video langsung. Decoder Aspose.BarCode bekerja langsung dengan objek `System.Drawing.Image`, `Stream`, atau `PdfPage`, sehingga Anda dapat memberikannya dari file, memory stream, atau tangkapan kamera tanpa langkah konversi tambahan.

## Mengapa Menggunakan Aspose.BarCode untuk DataMatrix?
Aspose.BarCode memproses hingga **5.000 barcode per detik** pada CPU standar 2,5 GHz, menangani **lebih dari 50 format input**, dan tidak memerlukan **ketergantungan native eksternal**. Perpustakaan ini berjalan di Windows, Linux, dan macOS, mendukung tingkat koreksi kesalahan dari ECC 000 hingga ECC 200, serta menawarkan penanganan structured‑append bawaan—semua sambil menjaga penggunaan memori di bawah 20 MB untuk batch 1.000 halaman.

## Prasyarat
- .NET Framework 4.5+ atau .NET Core 3.1+ (versi .NET terbaru apa pun).  
- Paket NuGet Aspose.BarCode untuk .NET terpasang.  
- Familiaritas dasar dengan C# dan IDE seperti Visual Studio atau Rider.

## Pemrograman Pembaca DataMatrix: Integrasi Tanpa Hambatan

### Cara Membaca Barcode DataMatrix di .NET?
`BarcodeReader` adalah kelas Aspose.BarCode yang mendekode barcode dari gambar, stream, atau halaman PDF.  
Muat gambar atau halaman PDF, buat instance `BarcodeReader`, aktifkan flag `ReadMultipleBarcodes` jika Anda mengharapkan lebih dari satu kode, dan panggil `Read`. Metode ini mengembalikan koleksi `BarCodeResult` yang berisi nilai yang didekode, tipe simbol, dan skor kepercayaan.  
`BarCodeResult` mewakili satu barcode yang didekode, termasuk nilai, tipe simbol, dan skor kepercayaan.

### Cara Mengaktifkan Penanganan Structured Append?
Set properti `ReadStructuredAppend` ke `true` sebelum memanggil `Read`. Pembaca akan secara otomatis menggabungkan fragmen yang termasuk dalam pesan logis yang sama, mengembalikan satu hasil gabungan.

## Konfigurasi Structured Append DataMatrix: Mengatur Data dengan Presisi

Structured Append memungkinkan satu pesan logis dibagi ke beberapa simbol DataMatrix. Ketika Anda mengaktifkan fitur ini, Aspose.BarCode menyusun fragmen berdasarkan nomor urut yang tertanam di setiap simbol. Ini ideal untuk mengkodekan URL panjang, blob biner besar, atau dokumen multi‑halaman.

## Hasilkan Barcode DataMatrix: Bebaskan Kreativitas dengan Aspose.BarCode untuk .NET

`BarcodeGenerator` adalah kelas Aspose.BarCode yang digunakan untuk menghasilkan gambar barcode dengan parameter yang dapat disesuaikan. Kelas `BarcodeGenerator` yang sama yang Anda gunakan untuk membaca juga dapat membuat simbol DataMatrix. Anda dapat mengontrol ukuran modul, margin, tingkat ECC, bahkan menyematkan gambar logo. Generator menghasilkan file PNG, JPEG, SVG, atau PDF, memberi Anda fleksibilitas penuh untuk skenario web, cetak, atau seluler.

## Tutorial Pembacaan Barcode DataMatrix
### [Pemrograman Pembaca DataMatrix](./datamatrix-reader-programming/)
Jelajahi pemrograman pembaca DataMatrix dengan Aspose.BarCode untuk .NET. Pelajari cara menghasilkan dan membaca barcode DataMatrix dalam aplikasi .NET Anda dengan panduan komprehensif ini.
### [Konfigurasi Structured Append DataMatrix](./datamatrix-structured-append-configuration/)
Pelajari cara membuat dan membaca konfigurasi Structured Append DataMatrix di .NET menggunakan Aspose.BarCode untuk organisasi data ber‑efisiensi tinggi.
### [Hasilkan Barcode DataMatrix](./datamatrix-versions/)
Pelajari cara menghasilkan barcode DataMatrix di .NET menggunakan Aspose.BarCode untuk .NET. Dimensi khusus, dukungan ECC, dan lainnya.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.BarCode untuk proyek komersial?**  
**A:** Ya. Lisensi komersial yang sah diperlukan untuk penggunaan produksi, tetapi versi percobaan gratis tersedia untuk evaluasi.

**Q: Apakah perpustakaan ini mendukung pembacaan DataMatrix dari file PDF?**  
**A:** Tentu saja. Anda dapat memuat halaman PDF sebagai stream gambar dan langsung memberikannya ke pembaca barcode.

**Q: Bagaimana cara menangani Structured Append ketika barcode terbagi di beberapa gambar?**  
**A:** API secara otomatis menyusun fragmen jika Anda mengaktifkan properti `ReadStructuredAppend` sebelum proses dekode.

**Q: Tingkat koreksi kesalahan apa yang tersedia saat menghasilkan barcode DataMatrix?**  
**A:** Anda dapat memilih antara ECC 000, 050, 080, 100, 140, dan 200 tergantung pada kepadatan data dan ketahanan yang dibutuhkan.

**Q: Apakah ada cara untuk meningkatkan kinerja pembacaan pada batch gambar besar?**  
**A:** Ya—gunakan `BarcodeReader` dengan `ReadMultipleBarcodes` diatur ke `true` dan proses gambar secara paralel menggunakan thread.

---

**Terakhir diperbarui:** 2026-09-28  
**Diuji dengan:** Aspose.BarCode untuk .NET 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menghasilkan Barcode DataMatrix Menggunakan Aspose.BarCode untuk .NET – Panduan Langkah demi Langkah](/barcode/net/datamatrix-barcode-configuration/)
- [Cara Membaca DataMatrix Append dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Hasilkan barcode DataMatrix dalam mode ASCII dengan Aspose.BarCode untuk .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}