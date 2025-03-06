---
title: Konfigurasi Teks Kode Diperluas DotCode dengan Aspose.BarCode untuk .NET
linktitle: Konfigurasi Teks Kode Diperpanjang DotCode
second_title: Aspose.BarCode .NET API
description: Hasilkan Konfigurasi Teks Kode Diperluas DotCode dengan mudah menggunakan Aspose.BarCode untuk .NET. Ikuti panduan langkah demi langkah kami untuk pembuatan kode batang yang efisien.
weight: 13
url: /id/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurasi Teks Kode Diperluas DotCode dengan Aspose.BarCode untuk .NET

## Perkenalan

Di bidang pembuatan dan pengelolaan kode batang, Aspose.BarCode untuk .NET menonjol sebagai solusi serbaguna dan efisien. Baik Anda perlu membuat kode batang untuk produk, inventaris, atau aplikasi lainnya, Aspose.BarCode untuk .NET siap membantu Anda. Dalam tutorial komprehensif ini, kami akan fokus pada pembuatan Konfigurasi Teks Kode Diperluas DotCode menggunakan Aspose.BarCode untuk .NET. DotCode adalah kode batang matriks dua dimensi yang dapat menyandikan data tekstual dan biner, menjadikannya alat yang berharga di berbagai industri.

## Prasyarat

Sebelum kita mempelajari panduan langkah demi langkah, ada beberapa prasyarat yang perlu Anda miliki agar dapat mengikutinya secara efektif:

1.  Aspose.BarCode untuk .NET: Pastikan Anda telah menginstal dan menyiapkan perpustakaan Aspose.BarCode untuk .NET. Jika belum, Anda dapat mendownloadnya dari[Aspose.BarCode untuk dokumentasi .NET](https://reference.aspose.com/barcode/net/).

2. Lingkungan Pengembangan: Anda harus memiliki lingkungan pengembangan .NET yang berfungsi, sebaiknya Visual Studio, yang terinstal di sistem Anda.

Dengan prasyarat ini, sekarang kita dapat melanjutkan dengan membuat Konfigurasi Teks Kode Diperluas DotCode.

## Impor Namespace

Pertama, Anda perlu mengimpor namespace yang diperlukan ke proyek .NET Anda untuk mengakses fungsionalitas yang diperlukan dari perpustakaan Aspose.BarCode. Inilah cara Anda melakukannya:


```csharp
using Aspose.BarCode.Generation;
```

Sekarang setelah prasyaratnya tercakup, mari kita uraikan proses pembuatan Konfigurasi Teks Kode Diperluas DotCode menjadi panduan langkah demi langkah.



## Langkah 1: Tentukan Jalur Direktori

Pada langkah ini, Anda perlu menentukan jalur direktori tempat Anda ingin menyimpan gambar Teks Kode Diperpanjang DotCode yang dihasilkan.

```csharp
string path = "Your Directory Path";
```

 Mengganti`"Your Directory Path"` dengan jalur sebenarnya di sistem Anda.

## Langkah 2: Buat Teks Kode Diperpanjang DotCode

Untuk membuat Teks Kode Diperluas DotCode, ikuti sub-langkah berikut:

### 2.1 Tambahkan Pengidentifikasi Format FNC1

Pengidentifikasi Format FNC1 digunakan untuk menunjukkan awal bidang data baru. Ini adalah bagian penting dari Teks Kode Diperpanjang DotCode.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 Tambahkan EICodeteks

ECICodetext adalah tempat Anda dapat menyandikan karakter khusus dan teks internasional. Dalam contoh ini, kami telah mengkodekan "犬Right狗" menggunakan pengkodean UTF-8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 Tambahkan Teks Kode Biasa

Anda juga dapat menambahkan teks biasa ke Teks Kode Diperpanjang DotCode. Di sini, kami telah menambahkan "Teks biasa".

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 Tambahkan Pemisah Simbol FNC3

Pemisah Simbol FNC3 digunakan untuk memisahkan bagian kode yang berbeda.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 Tambahkan Inisialisasi Pembaca FNC3

Langkah ini menambahkan informasi Inisialisasi Pembaca FNC3.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 Menghasilkan Teks Kode

 Sekarang, hasilkan DotCode Extended Codetext dengan memanggil`GetExtendedCodetext` metode pada`textBuilder` obyek.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Langkah 3: Hasilkan Gambar DotCode

Untuk menghasilkan Teks Kode Diperluas DotCode sebagai gambar, ikuti sub-langkah berikut:

#### 4.1 Inisialisasi Generator Barcode

 Inisialisasi`BarcodeGenerator` dengan parameter yang sesuai. Dalam hal ini, kami menggunakan`EncodeTypes.DotCode` dan teks kode yang dihasilkan.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Atur dimensi X untuk barcode (sesuaikan kebutuhan).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Atur mode pengkodean DotCode ke ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    //Simpan gambar barcode yang dihasilkan.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Dan itu saja! Anda telah berhasil membuat Teks Kode Diperluas DotCode menggunakan Aspose.BarCode untuk .NET.

## Kesimpulan

Aspose.BarCode untuk .NET adalah alat canggih yang menyederhanakan pembuatan kode batang. Dalam tutorial ini, kami fokus pada pembuatan Teks Kode Diperluas DotCode, yang penting dalam berbagai industri, terutama di mana pengkodean karakter multibahasa dan khusus diperlukan. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat dengan mudah membuat DotCode Extended Code Text untuk kebutuhan spesifik Anda.

 Jika Anda memerlukan panduan lebih lanjut atau memiliki pertanyaan, jangan ragu untuk mengunjungi[Aspose.BarCode untuk dokumentasi .NET](https://reference.aspose.com/barcode/net/) atau terlibat dengan komunitas di[Forum dukungan Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## FAQ

### Q1: Untuk apa DotCode digunakan?

A1: DotCode digunakan untuk pengkodean data tekstual dan biner dan umumnya diterapkan di industri seperti perawatan kesehatan dan logistik untuk tujuan pelacakan dan pengkodean data.

### Q2: Bisakah saya menyesuaikan tampilan barcode DotCode?

A2: Ya, Aspose.BarCode untuk .NET menyediakan opsi untuk menyesuaikan tampilan kode batang DotCode, termasuk ukuran dan mode pengkodean.

### Q3: Apakah Aspose.BarCode untuk .NET kompatibel dengan berbagai kerangka .NET?

A3: Ya, Aspose.BarCode untuk .NET kompatibel dengan berbagai kerangka kerja .NET, memastikan fleksibilitas dan kemudahan integrasi.

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.BarCode untuk .NET?

 A4: Anda dapat memperoleh lisensi sementara dari[Situs web Aspose](https://purchase.aspose.com/temporary-license/) untuk tujuan evaluasi dan pengujian.

### Q5: Apakah Aspose.BarCode untuk .NET cocok untuk pembuatan kode batang tingkat perusahaan?

A5: Tentu saja, Aspose.BarCode untuk .NET dirancang untuk memenuhi kebutuhan pembuatan kode batang skala kecil dan tingkat perusahaan, menawarkan skalabilitas dan keandalan.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
