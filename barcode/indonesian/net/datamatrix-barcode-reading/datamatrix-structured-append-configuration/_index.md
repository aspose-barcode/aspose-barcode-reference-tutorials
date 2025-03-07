---
title: Konfigurasi Penambahan Terstruktur DataMatrix dengan Aspose.BarCode untuk .NET
linktitle: Konfigurasi Penambahan Terstruktur DataMatrix
second_title: Aspose.BarCode .NET API
description: Pelajari cara membuat dan membaca konfigurasi penambahan terstruktur DataMatrix di .NET menggunakan Aspose.BarCode untuk organisasi data efisiensi tinggi.
weight: 11
url: /id/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurasi Penambahan Terstruktur DataMatrix dengan Aspose.BarCode untuk .NET

Jika Anda seorang pengembang yang ingin mengimplementasikan konfigurasi penambahan terstruktur DataMatrix di aplikasi .NET Anda, Aspose.BarCode untuk .NET adalah solusi tepat Anda. Dalam panduan langkah demi langkah ini, kita akan menjelajahi seluk beluk penggunaan perpustakaan canggih ini untuk menghasilkan dan membaca kode batang DataMatrix terstruktur. Kami akan membagi setiap contoh menjadi beberapa langkah yang mudah diikuti, memastikan Anda memahami konsepnya secara menyeluruh. Di akhir tutorial ini, Anda akan diperlengkapi untuk menggunakan Aspose.BarCode untuk .NET agar dapat bekerja dengan konfigurasi penambahan terstruktur DataMatrix secara efektif.

## Prasyarat

Sebelum masuk ke tutorial, Anda harus memiliki prasyarat berikut:

1.  Aspose.BarCode untuk Perpustakaan .NET: Anda harus mengunduh dan menginstal perpustakaan Aspose.BarCode untuk .NET. Anda bisa mendapatkannya dari[Di Sini](https://releases.aspose.com/barcode/net/).

2. Lingkungan Pengembangan: Lingkungan pengembangan .NET, seperti Visual Studio, harus disiapkan di sistem Anda.

Sekarang, mari kita mulai dengan panduan langkah demi langkah untuk bekerja dengan penambahan terstruktur DataMatrix menggunakan Aspose.BarCode untuk .NET.

## Impor Namespace

Sebelum memulai, Anda perlu mengimpor namespace yang diperlukan untuk mengakses fungsionalitas yang disediakan oleh Aspose.BarCode untuk .NET. Ini akan memungkinkan Anda bekerja dengan kode batang secara efisien di aplikasi Anda.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Sekarang setelah Anda mengimpor namespace yang diperlukan, mari lanjutkan membuat dan membaca kode batang tambahan terstruktur DataMatrix.


## Langkah 1: Siapkan Konfigurasi Penambahan Terstruktur DataMatrix

Untuk membuat kode batang tambahan terstruktur DataMatrix, Anda perlu menyiapkan konfigurasinya. Ini termasuk menentukan jalur direktori, ID barcode, jumlah barcode, dan ID file.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Setel mode penambahan terstruktur DataMatrix
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Hasilkan gambar kode batang
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

Pada langkah ini, kita telah mengkonfigurasi barcode DataMatrix dengan parameter yang diinginkan.

## Langkah 2: Baca Barcode DataMatrix Terstruktur

Sekarang Anda telah membuat kode batang, sekarang saatnya membaca informasinya. Kami akan menggunakan perpustakaan Aspose.BarCode untuk memecahkan kode data barcode.

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

Pada langkah ini, kita menggunakan BarCodeReader untuk mengekstrak informasi dari barcode yang dihasilkan, seperti ID barcode, jumlah barcode, dan ID file.

## Kesimpulan

Aspose.BarCode untuk .NET memudahkan pekerjaan dengan konfigurasi penambahan terstruktur DataMatrix. Dengan langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah membuat dan membaca kode batang ini di aplikasi .NET Anda. Perpustakaan menyediakan seperangkat alat canggih untuk pembuatan dan penguraian kode batang, sehingga menyederhanakan proses pengembangan Anda.

Dengan mengikuti panduan ini, Anda mendapatkan wawasan berharga tentang konfigurasi penambahan terstruktur DataMatrix dengan Aspose.BarCode untuk .NET. Pengetahuan ini dapat diterapkan pada berbagai aplikasi, mulai dari manajemen inventaris hingga pelacakan dokumen dan banyak lagi.

## FAQ

### Q1: Apa yang dimaksud dengan penambahan terstruktur DataMatrix, dan mengapa digunakan?

A1: Penambahan terstruktur DataMatrix adalah fitur yang memungkinkan Anda membagi sejumlah besar data menjadi beberapa kode batang yang lebih kecil. Hal ini sangat berguna ketika Anda memiliki ruang terbatas untuk satu kode batang atau perlu mengatur data secara efisien. Ini biasanya digunakan dalam industri seperti logistik, perawatan kesehatan, dan manufaktur.

### Q2: Bisakah saya menggunakan Aspose.BarCode untuk .NET di proyek sumber terbuka saya?

 A2: Ya, Aspose.BarCode untuk .NET menawarkan versi uji coba gratis yang dapat Anda gunakan dalam proyek sumber terbuka. Anda dapat menemukan versi uji coba[Di Sini](https://releases.aspose.com/).

### Q3: Apakah ada dukungan komunitas yang tersedia untuk Aspose.BarCode untuk .NET?

 A3: Ya, Anda dapat mencari dukungan komunitas dan berinteraksi dengan pengguna lain di forum Aspose.BarCode[Di Sini](https://forum.aspose.com/c/barcode/13).

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.BarCode untuk .NET?

 A4: Jika Anda memerlukan lisensi sementara untuk tujuan evaluasi atau pengujian, Anda dapat memperolehnya dari[Di Sini](https://purchase.aspose.com/temporary-license/).

### Q5: Apakah Aspose.BarCode untuk .NET mendukung jenis kode batang lainnya?

 A5: Ya, Aspose.BarCode untuk .NET mendukung berbagai jenis barcode, termasuk kode QR, Kode 128, EAN-13, dan banyak lagi. Anda dapat menjelajahi dokumentasi lengkapnya[Di Sini](https://reference.aspose.com/barcode/net/) untuk melihat daftar lengkap jenis barcode yang didukung.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
