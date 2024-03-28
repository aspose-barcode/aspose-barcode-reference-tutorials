---
title: Menguasai Mode Simbol Aztec dengan Aspose.BarCode untuk .NET
linktitle: Contoh Mode Simbol Aztec
second_title: Aspose.BarCode .NET API
description: Jelajahi Mode Simbol Aztec di Aspose.BarCode untuk .NET dan pelajari cara membuat kode batang serbaguna dengan mudah. Dapatkan pengalaman langsung dengan mode Otomatis, FullRange, Compact, dan Rune dalam tutorial komprehensif ini.
type: docs
weight: 14
url: /id/net/aztec-barcode-encoding/aztec-symbol-mode-example/
---
Jika Anda ingin menggabungkan kemampuan pembuatan kode batang yang kuat ke dalam aplikasi .NET Anda, Aspose.BarCode untuk .NET adalah solusi fantastis. Dalam tutorial ini, kita akan mempelajari Mode Simbol Aztec dan menjelajahi berbagai opsinya menggunakan Aspose.BarCode untuk .NET. Kami akan membahas prasyarat, mengimpor namespace, dan membagi setiap contoh menjadi beberapa langkah untuk memandu Anda melalui prosesnya.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan kerja tentang pengembangan .NET.
- Visual Studio diinstal pada mesin Anda.
-  Salinan Aspose.BarCode untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/barcode/net/).

Sekarang Anda sudah siap, mari selami contoh Mode Simbol Aztec.

## Mengimpor Namespace

Pertama, Anda harus mengimpor namespace yang diperlukan agar berfungsi dengan Aspose.BarCode untuk .NET. Buka proyek Visual Studio Anda dan tambahkan pernyataan penggunaan berikut di bagian atas file kode Anda:

```csharp
using Aspose.BarCode.Generation;
```

Dengan namespace yang ada, Anda sekarang dapat mulai menggunakan Aspose.BarCode untuk .NET.

## Langkah 1: Menyiapkan Generator Kode Batang

Mulailah dengan menginisialisasi Barcode Generator dengan tipe pengkodean Aztec dan memberikan teks kode. Berikut cara melakukannya:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

Pada langkah ini, kami telah menyiapkan generator dan menyediakan teks kode untuk pengkodean.

## Langkah 2: Mengatur Mode Simbol ke Otomatis

Sekarang, mari kita atur Mode Simbol Aztec ke "Otomatis" dan simpan gambar barcode sebagai file PNG. Inilah cara Anda melakukannya:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

Langkah ini memastikan Mode Simbol Aztec ditentukan secara otomatis, dan gambar kode batang yang dihasilkan disimpan.

## Langkah 3: Mengatur Mode Simbol ke FullRange

Jika Anda ingin menentukan Mode Simbol Aztec sebagai "FullRange", Anda dapat melakukannya dengan kode berikut:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

Ini akan membuat barcode dengan Mode Simbol Aztec FullRange.

## Langkah 4: Mengatur Mode Simbol ke Ringkas

Untuk membuat kode batang dengan Mode Simbol Aztec yang disetel ke "Ringkas", gunakan kode berikut:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

Langkah ini mengonfigurasi kode batang yang akan dihasilkan dengan Mode Simbol Aztec Ringkas.

## Langkah 5: Mengatur Mode Simbol ke Rune

Terakhir, jika Anda ingin menggunakan Mode Simbol Aztec "Rune", Anda dapat melakukannya dengan mengaturnya sebagai berikut:

```csharp
gen.CodeText = "123"; // Ubah teks kode jika diperlukan
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

Langkah ini mengubah teks kode menjadi "123" dan menghasilkan barcode dengan Mode Simbol Rune Aztec.

## Kesimpulan

Dalam tutorial ini, kita menjelajahi Mode Simbol Aztec di Aspose.BarCode untuk .NET. Kami membahas pengaturan Generator Kode Batang, mengonfigurasi Mode Simbol Aztec sebagai Otomatis, FullRange, Compact, dan Rune, dan menyimpan gambar kode batang yang dihasilkan. Dengan pengetahuan ini, kini Anda dapat menggabungkan pembuatan kode batang serbaguna ke dalam aplikasi .NET Anda dengan mudah.

 Jika Anda memiliki pertanyaan atau memerlukan bantuan lebih lanjut, jangan ragu untuk menghubungi komunitas Aspose.BarCode di mereka[forum dukungan](https://forum.aspose.com/c/barcode/13).

## FAQ

### Q1: Apa tujuan Mode Simbol Aztec dalam pembuatan kode batang?

A1: Mode Simbol Aztec memungkinkan Anda menentukan metode pengkodean untuk kode batang Aztec, memberikan fleksibilitas dalam pembuatan kode batang.

### Q2: Dapatkah saya mengubah teks kode untuk kode batang Aztec di Aspose.BarCode untuk .NET?

A2: Ya, Anda dapat dengan mudah mengubah teks kode sesuai dengan kebutuhan spesifik Anda saat membuat kode batang Aztec.

### Q3: Apakah tersedia versi uji coba gratis Aspose.BarCode untuk .NET?

A3: Ya, Anda dapat mengunduh Aspose.BarCode versi uji coba gratis untuk .NET[Di Sini](https://releases.aspose.com/).

### Q4: Di mana saya dapat menemukan dokumentasi lengkap Aspose.BarCode untuk .NET?

 A4: Anda dapat merujuk ke dokumentasi lengkap Aspose.BarCode untuk .NET[Di Sini](https://reference.aspose.com/barcode/net/).

### Q5: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.BarCode untuk .NET?

 A5: Anda dapat memperoleh lisensi sementara untuk Aspose.BarCode untuk .NET dengan mengunjungi[Link ini](https://purchase.aspose.com/temporary-license/).