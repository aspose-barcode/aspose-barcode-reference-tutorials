---
date: 2026-06-14
description: Pelajari cara membaca datamatrix dan menghasilkan barcode structured
  append di .NET menggunakan Aspose.BarCode, perpustakaan barcode yang cepat dan handal.
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: Konfigurasi Structured Append DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Cara Membaca DataMatrix Append dengan Aspose.BarCode untuk .NET
url: /id/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurasi Structured Append DataMatrix dengan Aspose.BarCode untuk .NET

Jika Anda seorang pengembang yang mencari **how to read datamatrix** menggunakan structured append dalam aplikasi .NET Anda, Aspose.BarCode untuk .NET adalah solusi utama Anda. Dalam panduan langkah demi langkah ini, kami akan membahas cara membuat dan mendekode barcode DataMatrix yang terbagi menjadi beberapa simbol. Pada akhir tutorial ini Anda akan merasa nyaman membuat, mengkonfigurasi, dan membaca barcode DataMatrix structured append dengan Aspose.BarCode untuk .NET.

## Jawaban Cepat
- **Perpustakaan apa yang menangani Structured Append DataMatrix?** Aspose.BarCode untuk .NET.
- **Berapa banyak simbol yang dapat dimiliki satu urutan structured append?** Hingga 16 simbol DataMatrix.
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengembangan dan pengujian.
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Bisakah saya membaca barcode tanpa file gambar?** Ya, Anda dapat mendekode dari array byte atau stream.

## Apa itu how to read datamatrix?
**how to read datamatrix** mengacu pada proses mendekode simbol DataMatrix dan, bila berlaku, menyatukan kembali potongan‑potongan urutan structured‑append untuk mengambil payload data asli. Aspose.BarCode menyediakan dukungan bawaan untuk alur kerja ini, menangani urutan simbol dan penggabungan data secara otomatis.

## Mengapa menggunakan Aspose.BarCode untuk Structured Append DataMatrix?
Aspose.BarCode mendukung **30+ simbol barcode** dan dapat mendekode gambar hingga **10.000 × 10.000 px** dalam waktu kurang dari **200 ms** pada perangkat keras server tipikal. Library ini juga menawarkan **penyebaran tanpa ketergantungan**, artinya Anda tidak memerlukan DLL native tambahan, dan ia bekerja di runtime .NET Windows, Linux, dan macOS.

## Prasyarat

Sebelum menyelam ke tutorial, Anda memerlukan:

1. Aspose.BarCode for .NET Library – unduh dari [di sini](https://releases.aspose.com/barcode/net/).
2. Anda juga dapat menjelajahi produk Aspose lainnya [di sini](https://releases.aspose.com/).
3. Lingkungan pengembangan .NET seperti Visual Studio 2022 atau Visual Studio Code dengan ekstensi C#.

Sekarang, mari kita mulai membuat dan membaca barcode DataMatrix structured append.

## Impor Namespace

Langkah pertama adalah mengimpor namespace yang mengekspos API barcode.

Class `BarCodeWriter` adalah titik masuk Aspose.BarCode untuk membuat barcode, sementara `BarCodeReader` menangani dekode.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Setelah Anda mengimpor namespace yang diperlukan, mari kita buat barcode structured‑append.

## Cara membaca barcode DataMatrix structured append?
Muat gambar (atau stream) yang dihasilkan ke dalam `BarCodeReader`, aktifkan opsi `ReadStructuredAppend`, dan panggil `ReadBarcode`. Reader akan secara otomatis mengembalikan data yang digabungkan dan menampilkan detail urutan seperti `StructuredAppendFileId`, `StructuredAppendTotalCount`, dan `StructuredAppendSegmentId`. Hasil gabungan dikembalikan sebagai string tunggal, dan Anda juga dapat mengambil pengidentifikasi segmen individual melalui properti `StructuredAppendSegmentId` pada reader untuk pemrosesan khusus.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

Pada langkah ini, kami menggunakan reader untuk mengekstrak ID barcode, total count, dan file ID, memastikan bahwa konfigurasi structured‑append telah diinterpretasikan dengan benar.

## Langkah 1: Siapkan Konfigurasi Structured Append DataMatrix
Untuk membuat barcode DataMatrix structured append, Anda perlu menyiapkan konfigurasinya. Ini meliputi penentuan jalur direktori, ID barcode, jumlah barcode, dan file ID.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

Pada langkah ini, kami telah mengkonfigurasi barcode DataMatrix dengan parameter yang diinginkan.

## Masalah Umum dan Solusinya
- **Urutan segmen tidak benar:** Pastikan nilai `StructuredAppendSegmentId` berurutan mulai dari 0; jika tidak, reader tidak dapat menyusun kembali data dengan benar.
- **Jumlah total tidak cocok:** `StructuredAppendTotalCount` harus sama pada semua simbol; ketidaksesuaian akan menyebabkan reader menganggap urutan tidak lengkap.
- **Kualitas gambar:** Gambar beresolusi rendah dapat menyebabkan kegagalan dekode. Usahakan setidaknya **300 dpi** saat merender barcode ke bitmap.

## Pertanyaan yang Sering Diajukan

### Q1: Apa itu Structured Append DataMatrix, dan mengapa digunakan?
A1: Structured Append DataMatrix adalah fitur yang memungkinkan Anda membagi sejumlah besar data menjadi beberapa barcode yang lebih kecil. Ini sangat berguna ketika ruang untuk satu barcode terbatas atau ketika Anda perlu mengatur data secara efisien. Fitur ini umum digunakan dalam logistik, perawatan kesehatan, dan manufaktur.

### Q2: Bisakah saya menggunakan Aspose.BarCode untuk .NET dalam proyek open‑source saya?
A2: Ya, Aspose.BarCode untuk .NET menawarkan versi percobaan gratis yang dapat Anda gunakan dalam proyek open‑source. Anda dapat menemukan versi percobaan [di sini](https://releases.aspose.com/).

### Q3: Apakah ada dukungan komunitas untuk Aspose.BarCode untuk .NET?
A3: Ya, Anda dapat mencari dukungan komunitas dan berinteraksi dengan pengguna lain di forum Aspose.BarCode [di sini](https://forum.aspose.com/c/barcode/13).

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.BarCode untuk .NET?
A4: Jika Anda memerlukan lisensi sementara untuk evaluasi atau pengujian, Anda dapat memperolehnya dari [di sini](https://purchase.aspose.com/temporary-license/).

### Q5: Apakah Aspose.BarCode untuk .NET mendukung tipe barcode lain?
A5: Ya, Aspose.BarCode untuk .NET mendukung berbagai tipe barcode, termasuk QR code, Code 128, EAN‑13, dan banyak lagi. Anda dapat menjelajahi dokumentasi lengkap [di sini](https://reference.aspose.com/barcode/net/) untuk melihat daftar lengkap tipe barcode yang didukung.

---

**Terakhir Diperbarui:** 2026-06-14  
**Diuji Dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Pemrograman Pembaca DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [Hasilkan Barcode DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [Konfigurasi Makro DataMatrix Master dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}