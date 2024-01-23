---
title: Konfigurasi Rasio Lebar-Sempit Satu Dimensi
linktitle: Konfigurasi Rasio Lebar-Sempit Satu Dimensi
second_title: Aspose.BarCode .NET API
description: Hasilkan kode batang khusus dengan mudah menggunakan Aspose.BarCode untuk .NET. Panduan langkah demi langkah untuk konfigurasi rasio lebar-sempit satu dimensi.
type: docs
weight: 22
url: /id/net/one-dimensional-barcode-types/one-dimensional-wide-narrow-ratio-configuration/
---

Apakah Anda ingin membuat dan menyesuaikan kode batang dengan mudah di aplikasi .NET Anda? Tidak perlu mencari lagi! Aspose.BarCode for .NET adalah perpustakaan tangguh yang memudahkan pembuatan dan penyesuaian kode batang. Dalam panduan langkah demi langkah ini, kita akan mempelajari cara memanfaatkan kekuatan Aspose.BarCode untuk .NET untuk membuat kode batang dengan konfigurasi rasio lebar-sempit.

## Prasyarat

Sebelum kita menyelami dunia barcode dengan Aspose.BarCode untuk .NET, Anda harus memiliki prasyarat berikut:

### 1. Lingkungan Visual Studio
   - Pastikan Anda telah menginstal Visual Studio di sistem Anda untuk bekerja dengan aplikasi .NET.
   
### 2. Aspose.BarCode untuk Perpustakaan .NET
   -  Anda harus menginstal perpustakaan Aspose.BarCode untuk .NET. Anda dapat mengunduhnya dari[situs web](https://releases.aspose.com/barcode/net/).

### 3. Kunci Lisensi (Opsional)
   -  Jika Anda memiliki kunci lisensi, kunci tersebut dapat digunakan untuk membuka fitur tambahan perpustakaan. Anda dapat memperoleh lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).

Sekarang setelah Anda memiliki prasyaratnya, mari mulai membuat kode batang satu dimensi dengan konfigurasi rasio lebar-sempit menggunakan Aspose.BarCode untuk .NET.

## Impor Namespace

Pertama, Anda perlu menyertakan namespace yang diperlukan dalam proyek Anda untuk mengakses fitur Aspose.BarCode untuk .NET. Anda dapat melakukan ini dengan menambahkan pernyataan penggunaan berikut di bagian atas kode Anda:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Langkah 1: Tentukan Jalur Direktori Anda

Mulailah dengan menentukan jalur di mana Anda ingin menyimpan gambar barcode yang dihasilkan. Anda dapat melakukannya dengan kode berikut:

```csharp
string path = "Your Directory Path";
```

 Mengganti`"Your Directory Path"` dengan jalur direktori sebenarnya tempat Anda ingin menyimpan gambar kode batang.

## Langkah 2: Buat Barcode Rasio Lebar-Sempit Satu Dimensi

Sekarang, mari buat kode batang satu dimensi dengan konfigurasi rasio lebar-sempit menggunakan Aspose.BarCode untuk .NET. Dalam contoh ini, kita akan menggunakan tipe pengkodean Code39Exended dan mengatur data ke "ASPOSE".

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "ASPOSE");
```

Baris kode ini menginisialisasi generator kode batang dengan jenis pengkodean dan data yang ditentukan.

## Langkah 3: Tetapkan Rasio Lebar/Sempit

Rasio lebar-sempit menentukan rasio antara elemen lebar dan sempit pada barcode. Pada langkah ini, kita akan mengatur rasio lebar-sempit menjadi 2:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 2;
```

Dan kemudian, kami akan menyimpan gambar kode batang yang dihasilkan ke jalur yang ditentukan:

```csharp
gen.Save($"{path}WideNarrow2Code39.png", BarCodeImageFormat.Png);
```

## Langkah 4: Sesuaikan Rasio Lebar-Sempit

Anda dapat bereksperimen dengan rasio lebar-sempit yang berbeda untuk mendapatkan tampilan kode batang yang diinginkan. Misalnya, jika Anda menginginkan kode batang yang lebih lebar, atur rasio lebar-sempit menjadi 5:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 5;
```

Dan simpan gambar barcodenya:

```csharp
gen.Save($"{path}WideNarrow5Code39.png", BarCodeImageFormat.Png);
```

Sekarang Anda telah berhasil membuat barcode satu dimensi dengan rasio lebar-sempit yang berbeda menggunakan Aspose.BarCode untuk .NET. Perpustakaan ini memberi Anda fleksibilitas untuk menghasilkan kode batang yang disesuaikan dengan kebutuhan spesifik Anda.

## Kesimpulan

Aspose.BarCode for .NET adalah perpustakaan serbaguna yang menyederhanakan pembuatan dan penyesuaian kode batang dalam aplikasi .NET Anda. Dalam tutorial ini, kita membahas dasar-dasar pembuatan barcode satu dimensi dengan konfigurasi rasio lebar-sempit. Dengan kemampuan untuk menyempurnakan berbagai parameter, Anda dapat membuat kode batang yang sesuai dengan kebutuhan Anda.

## Pertanyaan yang Sering Diajukan

### 1. Bagaimana cara mendapatkan lisensi Aspose.BarCode untuk .NET?
 Anda dapat membeli lisensi dari[Asumsikan situs web](https://purchase.aspose.com/buy).

### 2. Bisakah saya menggunakan Aspose.BarCode untuk .NET tanpa lisensi?
Ya, Anda dapat menggunakannya dengan lisensi sementara, yang menyediakan fungsionalitas terbatas.

### 3. Apakah Aspose.BarCode untuk .NET kompatibel dengan .NET Core?
Ya, Aspose.BarCode untuk .NET kompatibel dengan .NET Core dan .NET Framework.

### 4. Apakah ada batasan pada jenis barcode yang dapat saya hasilkan?
Aspose.BarCode for .NET mendukung berbagai simbologi barcode, termasuk QR Code, Code 39, dan banyak lagi.

### 5. Bagaimana saya bisa mendapatkan dukungan atau mengajukan pertanyaan tentang Aspose.BarCode untuk .NET?
 Anda dapat mengunjungi[Forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) untuk dukungan dan diskusi.
