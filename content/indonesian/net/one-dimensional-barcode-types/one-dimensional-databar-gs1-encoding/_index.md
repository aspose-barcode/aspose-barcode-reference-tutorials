---
title: Pengkodean GS1 Databar Satu Dimensi
linktitle: Pengkodean GS1 Databar Satu Dimensi
second_title: Aspose.BarCode .NET API
description: Pelajari cara membuat kode batang berkode Databar GS1 di .NET menggunakan Aspose.BarCode. Hasilkan barcode dengan mudah. Ikuti panduan langkah demi langkah kami.
type: docs
weight: 18
url: /id/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan kode batang berkode Databar GS1 satu dimensi menggunakan pustaka Aspose.BarCode untuk .NET. Baik Anda ingin membuat kode batang dengan atau tanpa pengkodean GS1, kami siap membantu Anda. Panduan langkah demi langkah ini akan membantu Anda memahami prasyarat, mengimpor namespace, dan mendemonstrasikan setiap contoh untuk membuat kode batang berkode Databar GS1 dengan mudah.

## Prasyarat

Sebelum kita mendalami kodenya, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.BarCode untuk .NET: Anda harus menginstal Aspose.BarCode untuk .NET. Jika Anda belum melakukannya, Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/barcode/net/).

2.  Jalur Direktori Anda: Ganti`"Your Directory Path"` dalam contoh kode dengan jalur sebenarnya tempat Anda ingin menyimpan gambar kode batang yang dihasilkan.

Sekarang setelah Anda menyiapkan prasyarat yang diperlukan, mari lanjutkan ke bagian pengkodean.

## Mengimpor Namespace

Untuk memulai, Anda perlu mengimpor namespace yang relevan untuk Aspose.BarCode. Tambahkan baris kode berikut di awal proyek .NET Anda:

```csharp
using Aspose.BarCode;
using System;
```

## Langkah 1: Inisialisasi Generator Barcode

Langkah pertama adalah menginisialisasi objek BarcodeGenerator dengan tipe pengkodean yang diinginkan. Dalam hal ini, kami menggunakan pengkodean Databar Expanded. 

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Langkah 2: Hasilkan Barcode dengan Encoding GS1

Sekarang, kita akan mengatur teks kode dengan pemeriksaan GS1Encoding dan menyimpan gambar barcode yang dihasilkan. 

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Langkah 3: Hasilkan Barcode Pengkodean Variabel

Pada langkah ini, kita akan membuat barcode dengan teks kode variabel tanpa pemeriksaan GS1Encoding.

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Langkah 4: Tangani Pengecualian untuk Pemeriksaan Pengkodean GS1

Jika Anda mencoba membuat kode batang dengan teks kode variabel dengan pemeriksaan GS1Encoding diaktifkan, pengecualian akan muncul. Inilah cara Anda mengatasinya:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

Sekarang Anda telah berhasil membuat kode batang berkode Databar GS1 satu dimensi dengan Aspose.BarCode untuk .NET. Anda dapat menjelajahi lebih lanjut dan menyesuaikan pembuatan kode batang berdasarkan kebutuhan spesifik Anda.

## Kesimpulan

Dalam tutorial ini, kami telah membahas proses pembuatan kode batang berkode Databar GS1 satu dimensi menggunakan Aspose.BarCode untuk .NET. Kami membahas prasyarat, mengimpor namespace yang diperlukan, dan memberikan panduan langkah demi langkah untuk membuat kode batang berkode GS1 dan kode batang pengkode variabel.

 Dengan Aspose.BarCode untuk .NET, pembuatan kode batang menjadi tugas yang lancar, menawarkan fleksibilitas dan kontrol atas kebutuhan pembuatan kode batang Anda. Jika Anda mengalami masalah atau memiliki pertanyaan, jangan ragu untuk mengunjungi[Dokumentasi Aspose.BarCode](https://reference.aspose.com/barcode/net/) atau mencari bantuan di[Forum dukungan Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Pertanyaan yang Sering Diajukan

### 1. Apa yang dimaksud dengan pengkodean GS1 dalam barcode?
Pengkodean GS1 adalah standar yang digunakan dalam barcode untuk memastikan struktur dan identifikasi data yang tepat. Ini biasanya digunakan untuk barang-barang di ritel, perawatan kesehatan, dan logistik untuk memfasilitasi pelacakan dan pertukaran informasi yang akurat.

### 2. Bisakah saya menyesuaikan tampilan kode batang yang dihasilkan?
Ya, Anda dapat menyesuaikan tampilan kode batang yang dihasilkan dengan Aspose.BarCode untuk .NET. Anda memiliki kendali atas berbagai parameter seperti ukuran, warna, dan gaya.

### 3. Di mana saya dapat menemukan sumber daya dan dokumentasi tambahan untuk Aspose.BarCode?
 Anda dapat menemukan dokumentasi dan contoh yang komprehensif di[Dokumentasi Aspose.BarCode](https://reference.aspose.com/barcode/net/). Ini adalah sumber berharga untuk pembelajaran dan pemecahan masalah.

### 4. Apakah ada versi uji coba yang tersedia untuk Aspose.BarCode?
 Ya, Anda bisa mendapatkan versi uji coba gratis Aspose.BarCode untuk .NET dari[Di Sini](https://releases.aspose.com/).

### 5. Bagaimana cara membeli lisensi Aspose.BarCode untuk .NET?
 Untuk membeli lisensi Aspose.BarCode untuk .NET, kunjungi[halaman pembelian](https://purchase.aspose.com/buy) di situs web Aspose.
