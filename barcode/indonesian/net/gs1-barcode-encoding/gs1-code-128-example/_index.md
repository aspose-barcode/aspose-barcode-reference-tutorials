---
title: Panduan Langkah demi Langkah dengan Contoh Kode GS1 128
linktitle: Contoh Kode GS1 128
second_title: Aspose.BarCode .NET API
description: Pelajari cara membuat barcode GS1 Code 128 dengan Aspose.BarCode untuk .NET. Panduan langkah demi langkah untuk pembuatan kode batang di C#. Mulai sekarang!
type: docs
weight: 10
url: /id/net/gs1-barcode-encoding/gs1-code-128-example/
---

## Perkenalan

Selamat datang di dunia Aspose.BarCode untuk .NET! Jika Anda ingin membuat, menyesuaikan, dan bekerja dengan kode batang di aplikasi .NET, Anda berada di tempat yang tepat. Dalam panduan komprehensif ini, kami akan memandu Anda melalui esensi penggunaan Aspose.BarCode untuk .NET, memastikan Anda memiliki pemahaman yang jelas tentang perpustakaan, prasyaratnya, dan berbagai fiturnya. Di akhir tutorial ini, Anda akan dapat membuat barcode dengan mudah dan presisi.

## Prasyarat
Sebelum menyelami dunia Aspose.BarCode untuk .NET yang menarik, penting untuk memastikan Anda memiliki prasyarat yang diperlukan. Inilah yang Anda perlukan:

1. Lingkungan Pengembangan .NET: Anda harus memiliki lingkungan pengembangan .NET yang berfungsi, termasuk Visual Studio atau IDE pilihan lainnya.

2.  Aspose.BarCode untuk .NET: Anda dapat memperoleh Aspose.BarCode untuk .NET dengan mengunduhnya dari[Link ini](https://releases.aspose.com/barcode/net/). Pastikan untuk menginstal dan mengatur perpustakaan dengan benar.

3. Keakraban dengan C#: Pemahaman dasar tentang bahasa pemrograman C# akan bermanfaat untuk mengikuti contoh dan menulis kode Anda.

4. Ide tentang Kode GS1 128: Meskipun tidak wajib, memiliki pengetahuan tentang kode batang GS1 Kode 128 dapat membantu Anda memahami contoh dengan lebih baik.

Sekarang, mari kita uraikan contoh Kode GS1 128 menjadi beberapa langkah untuk panduan langkah demi langkah:

## Impor Namespace
Untuk memulai Aspose.BarCode untuk .NET, Anda perlu mengimpor namespace yang diperlukan. Namespace ini menyediakan akses ke fitur dan fungsionalitas perpustakaan. Inilah cara Anda melakukannya:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Langkah 1: Tetapkan Jalur Direktori Anda
Sebelum membuat barcode GS1 Code 128, Anda perlu menentukan jalur direktori tempat Anda ingin menyimpan gambar barcode. Anda dapat mengatur jalur seperti ini:

```csharp
string path = "Your Directory Path";
```

 Mengganti`"Your Directory Path"` dengan jalur sebenarnya tempat Anda ingin menyimpan gambar barcode.

## Langkah 2: Buat Barcode Kode GS1 128
Sekarang saatnya membuat barcode GS1 Code 128 menggunakan Aspose.BarCode for .NET. Dalam contoh ini, kita akan membuat barcode dengan data "(01)12345678901231(21)ASPOSE(30)9876". Inilah cara Anda melakukannya:

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

Kode ini menginisialisasi generator barcode dengan tipe dan data yang ditentukan.

## Langkah 3: Sesuaikan Parameter Barcode
Aspose.BarCode untuk .NET memungkinkan Anda menyesuaikan berbagai parameter kode batang, seperti XDimension (lebar elemen sempit di kode batang). Dalam contoh ini, kami menyetel XDimension menjadi 2 piksel:

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Anda dapat menyesuaikan parameter ini sesuai kebutuhan Anda.

## Langkah 4: Simpan Gambar Barcode
Terakhir, Anda dapat menyimpan kode batang yang dihasilkan sebagai gambar. Dalam contoh ini, kami menyimpannya sebagai file PNG:

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

 Pastikan untuk mengganti`GS1Code128Example.png` dengan nama file pilihan Anda.

## Kesimpulan:
Dalam panduan langkah demi langkah ini, kami telah memperkenalkan Anda pada Aspose.BarCode untuk .NET dan menjelaskan prasyarat untuk memulai. Kami telah membagi contoh pembuatan kode batang GS1 Kode 128 menjadi beberapa langkah, membantu Anda memahami prosesnya dengan jelas. Sekarang, Anda diperlengkapi untuk bekerja dengan Aspose.BarCode untuk .NET dan membuat kode batang yang disesuaikan untuk aplikasi .NET Anda. Selamat membuat kode!


## FAQ:

### Di mana saya dapat menemukan dokumentasi Aspose.BarCode untuk .NET?
 Anda dapat mengakses dokumentasinya di[https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).

### Bagaimana cara mengunduh Aspose.BarCode untuk .NET?
 Anda dapat mengunduh perpustakaan dari[https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).

### Apakah ada uji coba gratis yang tersedia?
 Ya, Anda bisa mendapatkan uji coba gratis dari[https://releases.aspose.com/](https://releases.aspose.com/).

### Di mana saya dapat membeli lisensi Aspose.BarCode untuk .NET?
 Anda dapat membeli lisensi di[https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).

### Butuh bantuan atau punya pertanyaan? Di mana saya bisa mendapatkan dukungan?
Untuk dukungan dan diskusi komunitas, kunjungi[https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13).