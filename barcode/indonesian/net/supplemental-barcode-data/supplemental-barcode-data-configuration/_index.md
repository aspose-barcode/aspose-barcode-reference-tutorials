---
title: Membuat Data Barcode Tambahan dengan Aspose.BarCode untuk .NET
linktitle: Konfigurasi Data Barcode Tambahan
second_title: Aspose.BarCode .NET API
description: Hasilkan data kode batang tambahan dengan Aspose.BarCode untuk .NET. Sesuaikan kode batang EAN-2 dan EAN-5 dengan mudah. Panduan langkah demi langkah untuk pengembang .NET.
weight: 10
url: /id/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat Data Barcode Tambahan dengan Aspose.BarCode untuk .NET


Dalam dunia pembuatan dan penyesuaian kode batang, Aspose.BarCode untuk .NET menonjol sebagai alat yang ampuh dan serbaguna. Baik Anda seorang pengembang berpengalaman atau baru memulai, panduan langkah demi langkah ini akan memandu Anda melalui proses mengonfigurasi data kode batang tambahan menggunakan Aspose.BarCode untuk .NET. 

## Prasyarat

Sebelum kita mendalami dunia data kode batang tambahan, pastikan Anda memiliki prasyarat berikut:

- Lingkungan pengembangan yang diatur dengan Visual Studio atau alat pengembangan .NET lainnya.
-  Salinan Aspose.BarCode untuk .NET. Jika Anda belum melakukannya, Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/barcode/net/).
- Pengetahuan dasar tentang pemrograman C#.
- Direktori tempat Anda dapat menyimpan gambar kode batang yang dihasilkan.

## Mengimpor Namespace

Pertama, pastikan Anda memiliki namespace yang diperlukan yang disertakan dalam kode C# Anda agar berfungsi dengan Aspose.BarCode untuk .NET. Impor namespace yang diperlukan di awal file C# Anda:

```csharp
using Aspose.BarCode.Generation;
```

Sekarang, mari kita uraikan proses konfigurasi data kode batang tambahan menjadi beberapa langkah.

## Langkah 1: Menyiapkan Jalur Direktori

 Dalam kode C# Anda, tentukan jalur ke direktori tempat Anda ingin menyimpan gambar kode batang yang dihasilkan. Mengganti`"Your Directory Path"` dengan jalur direktori Anda yang sebenarnya.

```csharp
string path = "Your Directory Path";
```

## Langkah 2: Membuat Generator Barcode

 Buat sebuah contoh dari`BarcodeGenerator` dengan menentukan jenis barcode dan data yang ingin dikodekan. Dalam contoh ini, kami menggunakan barcode EAN-13 dengan data "1234567890128".

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## Langkah 3: Menyesuaikan Dimensi Barcode

Mengatur dimensi barcode, seperti dimensi X (lebar elemen terkecil pada barcode) dan spasi tambahan. Dalam contoh ini, kami menetapkan dimensi X menjadi 2 piksel dan ruang tambahan menjadi 20 piksel.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## Langkah 4: Mengonfigurasi Suplemen EAN-2

Untuk mengonfigurasi kode batang tambahan EAN-2, atur data tambahan ke nilai yang diinginkan. Dalam hal ini, kami menyetelnya ke "12". 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## Langkah 5: Menyimpan Gambar Barcode

Simpan gambar barcode yang dihasilkan ke direktori yang Anda tentukan dengan nama yang bermakna. Dalam contoh ini, kami menyimpan kode batang tambahan EAN-2 sebagai "SupplementEAN2.png".

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## Langkah 6: Mengonfigurasi Suplemen EAN-5

 Untuk mengkonfigurasi kode batang tambahan EAN-5, cukup ubah`SupplementData` ke nilai yang Anda inginkan. Di sini, kami menyetelnya ke "12345".

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## Langkah 7: Menyimpan Gambar Barcode (EAN-5)

Terakhir, simpan gambar kode batang tambahan EAN-5 di direktori yang Anda tentukan. Dalam hal ini, kami menyimpannya sebagai "SupplementEAN5.png".

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

Sekarang, Anda telah berhasil mengonfigurasi dan membuat data kode batang tambahan menggunakan Aspose.BarCode untuk .NET. Anda dapat menggunakan pendekatan ini untuk membuat berbagai jenis kode batang dengan data tambahan yang bervariasi.

## Kesimpulan

Aspose.BarCode for .NET adalah alat yang ampuh untuk pembuatan dan penyesuaian kode batang. Dalam panduan ini, kami memandu proses konfigurasi dan pembuatan data kode batang tambahan langkah demi langkah. Dengan prasyarat yang tepat dan sedikit pengkodean, Anda dapat bekerja dengan data kode batang secara efisien dan memenuhi kebutuhan spesifik Anda.

 Untuk informasi lebih lanjut dan penggunaan lanjutan, lihat[Aspose.BarCode untuk dokumentasi .NET](https://reference.aspose.com/barcode/net/).

## Pertanyaan yang Sering Diajukan

### Bisakah saya menggunakan Aspose.BarCode untuk .NET di proyek .NET Core saya?
Ya, Aspose.BarCode untuk .NET kompatibel dengan .NET Core.

### Apakah ada uji coba gratis yang tersedia untuk Aspose.BarCode untuk .NET?
 Ya, Anda dapat mencobanya secara gratis dengan mengunjungi[Link ini](https://releases.aspose.com/).

### Di mana saya bisa mendapatkan lisensi sementara untuk Aspose.BarCode untuk .NET?
 Anda dapat memperoleh lisensi sementara dari[Link ini](https://purchase.aspose.com/temporary-license/).

### Apakah Aspose.BarCode mendukung berbagai jenis kode batang?
Ya, mendukung berbagai jenis barcode, termasuk EAN-13, QR Code, Code 128, dan banyak lagi.

### Bisakah saya menyesuaikan tampilan kode batang yang dihasilkan?
Tentu saja, Anda dapat menyesuaikan dimensi, warna, dan aspek lain dari kode batang untuk memenuhi kebutuhan Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
