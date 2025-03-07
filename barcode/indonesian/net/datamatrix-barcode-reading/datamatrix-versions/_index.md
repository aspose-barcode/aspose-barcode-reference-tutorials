---
title: Hasilkan Barcode DataMatrix dengan Aspose.BarCode untuk .NET
linktitle: Versi DataMatrix
second_title: Aspose.BarCode .NET API
description: Pelajari cara membuat kode batang DataMatrix di .NET menggunakan Aspose.BarCode untuk .NET. Dimensi khusus, dukungan ECC, dan banyak lagi.
weight: 12
url: /id/net/datamatrix-barcode-reading/datamatrix-versions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hasilkan Barcode DataMatrix dengan Aspose.BarCode untuk .NET

Jika Anda mencari solusi andal untuk menghasilkan kode batang DataMatrix di aplikasi .NET Anda, Aspose.BarCode untuk .NET adalah jawabannya. Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses penggunaan Aspose.BarCode untuk .NET untuk membuat kode batang DataMatrix. Kami akan membagi setiap contoh menjadi beberapa langkah, memastikan Anda dapat mengikutinya dengan mudah.

## Prasyarat

Sebelum kita mendalami kodenya, pastikan Anda memiliki prasyarat berikut:
- Lingkungan pengembangan dengan dukungan .NET.
-  Salinan Aspose.BarCode untuk .NET, yang dapat Anda unduh[Link ini](https://releases.aspose.com/barcode/net/).
- Pengetahuan dasar tentang C# dan kerangka .NET.

Sekarang, mari jelajahi versi DataMatrix dan cara membuatnya menggunakan Aspose.BarCode untuk .NET.

## Impor Namespace

Dalam proyek C# apa pun, penting untuk mengimpor namespace yang diperlukan. Dalam kasus Aspose.BarCode, Anda harus menyertakan hal berikut:

```csharp
using Aspose.BarCode.Generation;
```

 Namespace ini menyediakan akses ke`BarcodeGenerator` kelas, yang sangat penting untuk menghasilkan kode batang.

Sekarang, mari kita bagi contoh ini menjadi beberapa langkah.

## Langkah 1: Siapkan Jalur Direktori Anda

Mulailah dengan menentukan jalur direktori tempat Anda ingin menyimpan kode batang DataMatrix yang dihasilkan.

```csharp
string path = "Your Directory Path";
```

 Mengganti`"Your Directory Path"` dengan jalur sebenarnya tempat Anda ingin menyimpan gambar kode batang.

## Langkah 2: Inisialisasi Generator Barcode

 Buat sebuah instance dari`BarcodeGenerator` kelas dan tentukan jenis barcode sebagai`DataMatrix`. Anda juga dapat memberikan data yang ingin Anda kodekan di dalam kode batang.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Kode untuk menghasilkan kode batang ada di sini
}
```

## Langkah 3: Konfigurasikan Properti Barcode

Anda dapat menyesuaikan berbagai properti barcode DataMatrix, seperti dimensinya dan jenis ECC (Error Correction Code). Berikut contoh pengaturan dimensi X menjadi 4 piksel dan memilih ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Langkah 4: Tetapkan Versi DataMatrix dan Simpan

Anda dapat menentukan versi DataMatrix dengan mengatur jumlah baris dan kolom. Setelah mengkonfigurasi versi, simpan gambar barcode.

Misalnya untuk membuat barcode DataMatrix dengan 22 baris dan 22 kolom menggunakan ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

Demikian pula, Anda dapat membuat kode batang dengan parameter berbeda dengan mengubah versi dan jenis ECC sesuai kebutuhan.

## Langkah 5: Ulangi untuk Versi Lain

Anda dapat mengulangi Langkah 4 untuk versi DataMatrix lainnya. Misalnya untuk membuat barcode dengan 12 baris dan 64 kolom menggunakan ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Langkah 6: Ganti Jenis ECC

Jika Anda ingin mengubah tipe ECC menjadi Ecc140, Anda dapat melakukannya dengan memperbarui properti ECC:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Langkah 7: Hasilkan Barcode dengan Versi Berbeda dan ECC

Ulangi Langkah 4 untuk versi DataMatrix dan tipe ECC lainnya, simpan setiap kode batang dengan nama file unik.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Sekarang setelah Anda mempelajari cara membuat kode batang DataMatrix menggunakan Aspose.BarCode untuk .NET, Anda dapat dengan mudah mengintegrasikan fungsi ini ke dalam aplikasi .NET Anda.

## Kesimpulan

Aspose.BarCode untuk .NET menyederhanakan proses pembuatan kode batang DataMatrix di aplikasi .NET Anda. Dengan panduan langkah demi langkah ini, Anda dapat membuat barcode dengan versi dan tipe ECC berbeda, menawarkan fleksibilitas dan penyesuaian untuk memenuhi kebutuhan spesifik Anda.

 Jika Anda memiliki pertanyaan atau memerlukan bantuan, jangan ragu untuk mengunjungi[Aspose.BarCode untuk dokumentasi .NET](https://reference.aspose.com/barcode/net/) atau periksa[Forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) untuk dukungan.

## FAQ

### Q1: Apa itu ECC di barcode DataMatrix?

A1: ECC (Error Correction Code) adalah komponen penting dari barcode DataMatrix yang membantu memastikan integritas data. Level ECC yang berbeda memberikan tingkat koreksi kesalahan yang berbeda-beda.

### Q2: Bisakah saya membuat kode batang DataMatrix dengan dimensi khusus menggunakan Aspose.BarCode untuk .NET?

A2: Ya, Anda dapat menyesuaikan dimensi barcode DataMatrix dengan mengatur jumlah baris dan kolom seperti yang ditunjukkan dalam tutorial.

### Q3: Di mana saya dapat mengunduh Aspose.BarCode untuk .NET?

 A3: Anda dapat mengunduh Aspose.BarCode untuk .NET dari[Link ini](https://releases.aspose.com/barcode/net/).

### Q4: Apakah tersedia uji coba gratis untuk Aspose.BarCode untuk .NET?

 A4: Ya, Anda dapat mengakses uji coba gratis Aspose.BarCode untuk .NET[Di Sini](https://releases.aspose.com/).

### Q5: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.BarCode untuk .NET?

 A5: Untuk mendapatkan lisensi sementara Aspose.BarCode untuk .NET, kunjungi[Link ini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
