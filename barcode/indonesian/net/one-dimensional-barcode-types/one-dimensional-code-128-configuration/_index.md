---
title: Konfigurasi Kode Satu Dimensi 128
linktitle: Konfigurasi Kode Satu Dimensi 128
second_title: Aspose.BarCode .NET API
description: Pelajari cara membuat kode batang Kode 128 satu dimensi di .NET menggunakan Aspose.BarCode. Ikuti panduan langkah demi langkah kami untuk integrasi kode batang yang lancar.
weight: 10
url: /id/net/one-dimensional-barcode-types/one-dimensional-code-128-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurasi Kode Satu Dimensi 128


Jika Anda seorang pengembang .NET yang mencari alat canggih untuk menghasilkan kode batang di aplikasi Anda, Aspose.BarCode untuk .NET adalah solusi tepat Anda. Panduan komprehensif ini akan memandu Anda melalui proses memanfaatkan kemampuan Aspose.BarCode untuk .NET untuk membuat kode batang Kode 128 satu dimensi, dan dirancang untuk pemula dan pengembang berpengalaman. 

## Prasyarat

Sebelum kita terjun ke dunia pembuatan kode batang yang menarik dengan Aspose.BarCode, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di sistem Anda.

2.  Aspose.BarCode untuk .NET: Anda harus mengunduh dan menginstal Aspose.BarCode untuk .NET. Anda bisa mendapatkannya dari[Di Sini](https://releases.aspose.com/barcode/net/).

3. Proyek .NET Anda: Anda harus menyiapkan proyek .NET dan siap untuk mengintegrasikan pembuatan kode batang.

Sekarang, mari kita mulai!

## Impor Namespace

Langkah pertama adalah mengimpor namespace yang diperlukan untuk proyek Anda. Namespace ini akan memberi Anda akses ke fitur dan fungsi Aspose.BarCode.

### Langkah 1: Impor Namespace

```csharp
using Aspose.BarCode.Generation;
```

## Konfigurasi Kode Satu Dimensi 128

Sekarang, mari buat barcode Kode 128 menggunakan Aspose.BarCode untuk .NET. Kami akan membahas setiap langkah secara mendetail, memastikan Anda memiliki pemahaman yang jelas tentang prosesnya.

### Langkah 2: Tetapkan Jalurnya

Pertama, atur jalur ke direktori tempat Anda ingin menyimpan gambar barcode yang dihasilkan.

```csharp
string path = "Your Directory Path";
```

### Langkah 3: Buat Generator Kode Batang Kode 128

 Membuat`BarcodeGenerator` contoh untuk menghasilkan kode batang Kode 128. Anda dapat menentukan jenis kode batang yang ingin Anda hasilkan (dalam hal ini, Kode128) dan nilai yang ingin Anda kodekan.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "CODE");
```

### Langkah 4: Konfigurasikan Parameter Barcode

Sebelum membuat kode batang, Anda dapat mengonfigurasi berbagai parameter. Misalnya, Anda dapat memilih untuk menampilkan atau menyembunyikan checksum.

#### Opsi 1: Jangan tampilkan checksum

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = false;
```

#### Opsi 2: Tampilkan checksum

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = true;
```

### Langkah 5: Simpan Gambar Barcode

Sekarang, saatnya menyimpan gambar barcode yang dihasilkan ke direktori yang Anda tentukan. Anda dapat menyimpan barcode dengan atau tanpa checksum, tergantung konfigurasi yang Anda pilih pada langkah sebelumnya.

#### Simpan kode batang tanpa checksum

```csharp
gen.Save($"{path}OneCSCode128NotShowChecksum.png", BarCodeImageFormat.Png);
```

#### Simpan kode batang dengan checksum

```csharp
gen.Save($"{path}OneCSCode128ShowChecksum.png", BarCodeImageFormat.Png);
```

Itu dia! Anda telah berhasil membuat kode batang Kode 128 satu dimensi menggunakan Aspose.BarCode untuk .NET. Anda dapat menggunakan kode batang ini dalam berbagai aplikasi, seperti manajemen inventaris, pelabelan produk, dan lainnya.

## Kesimpulan

Aspose.BarCode untuk .NET memberikan solusi yang kuat dan mudah digunakan untuk pembuatan kode batang dalam aplikasi .NET. Dengan API intuitif dan dokumentasi ekstensif, Anda dapat dengan mudah mengintegrasikan fungsionalitas kode batang ke dalam proyek Anda. Apakah Anda perlu membuat kode batang satu dimensi atau dua dimensi, Aspose.BarCode siap membantu Anda.

Gabungkan Aspose.BarCode ke dalam aplikasi .NET Anda sekarang, dan sederhanakan proses pembuatan kode batang Anda dengan mudah.

### FAQ

### Apakah Aspose.BarCode untuk .NET kompatibel dengan .NET Core?
Ya, Aspose.BarCode untuk .NET kompatibel dengan .NET Framework dan .NET Core.

### Bisakah saya menyesuaikan tampilan kode batang yang dihasilkan?
Sangat! Aspose.BarCode memungkinkan Anda menyesuaikan berbagai aspek kode batang, termasuk ukuran, warna, dan penempatan teks.

### Apakah Aspose.BarCode cocok untuk menghasilkan kode QR?
Meskipun Aspose.BarCode terutama berfokus pada kode batang satu dimensi, Anda juga dapat menggunakan Aspose.BarCode untuk .NET untuk menghasilkan kode QR.

### Apakah ada uji coba gratis yang tersedia?
 Ya, Anda dapat mencoba Aspose.BarCode untuk .NET secara gratis dengan mengunduh versi uji coba[Di Sini](https://releases.aspose.com/).

### Di mana saya bisa mendapatkan dukungan untuk Aspose.BarCode untuk .NET?
 Anda dapat mencari bantuan dan berbagi pengalaman Anda di forum Aspose.BarCode untuk .NET[Di Sini](https://forum.aspose.com/c/barcode/13).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
