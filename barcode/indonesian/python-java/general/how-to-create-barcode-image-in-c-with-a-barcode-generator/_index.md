---
category: general
date: 2026-10-02
description: Buat gambar kode batang di C# menggunakan generator kode batang, kontrol
  ukuran piksel kode batang, dan sesuaikan tinggi kode batang untuk dimensi kode batang
  khusus.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- barcode pixel size
- adjust barcode height
- custom barcode dimensions
language: id
lastmod: 2026-10-02
og_description: Buat gambar barcode di C# dengan generator barcode. Pelajari cara
  mengatur ukuran piksel barcode, menyesuaikan tinggi barcode, dan menentukan dimensi
  barcode khusus.
og_image_alt: Sample DataBar Omnidirectional barcode saved at 30 px height and 60 px
  height
og_title: Buat gambar barcode di C# – panduan generator barcode dan dimensi khusus
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode image in C# using a barcode generator, control barcode
    pixel size and adjust barcode height for custom barcode dimensions.
  headline: How to create barcode image in C# with a barcode generator
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Cara membuat gambar barcode di C# dengan generator barcode
url: /id/python-java/general/how-to-create-barcode-image-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar barcode di C# dengan generator barcode

Jika Anda perlu **membuat gambar barcode** secara programatis, panduan ini menunjukkan solusi lengkap yang siap dijalankan dalam C#. Dengan menggunakan generator barcode, Anda dapat mengontrol **ukuran piksel barcode**, **menyesuaikan tinggi barcode**, dan menentukan **dimensi barcode khusus** tanpa meninggalkan IDE Anda.

Anda akan belajar cara menghasilkan dua file PNG—satu dengan tinggi bar 30 px dan satu lagi dengan 60 px—sementara mempertahankan lebar modul tetap. Langkah-langkah ini bekerja dengan jenis barcode apa pun yang didukung oleh perpustakaan, sehingga Anda dapat menyesuaikannya untuk QR code, Code 128, atau simbol lainnya.

## Apa yang Anda butuhkan

- .NET 6.0 atau lebih baru (kode ini juga dapat dikompilasi dengan .NET Framework 4.8)
- Referensi ke perpustakaan barcode (misalnya, Aspose.BarCode untuk .NET atau kelas `BarcodeGenerator` yang kompatibel)
- Pengetahuan dasar C#
- Izin menulis ke folder tempat file PNG akan disimpan

## Langkah 1: Inisialisasi generator barcode untuk **membuat gambar barcode**

Pertama, impor namespace yang diperlukan dan buat instance `BarcodeGenerator`. Konstruktor menerima jenis barcode (`EncodeTypes.DatabarOmniDirectional`) dan string data yang ingin Anda enkode.

```csharp
using Aspose.BarCode.Generation;   // or the namespace of your barcode library
using Aspose.BarCode;               // for BarCodeImageFormat
using System.IO;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator to create barcode image
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Membuat generator adalah fondasi untuk setiap alur kerja **barcode generator c#**. Ini mengalokasikan kanvas gambar internal dan menyiapkan data untuk dirender.

## Langkah 2: Tentukan **ukuran piksel barcode** dan tinggi bar awal

Kualitas visual gambar akhir bergantung pada dua parameter:

| Parameter | Arti |
|-----------|------|
| `XDimension.Pixels` | Lebar satu modul (elemen hitam/putih terkecil). |
| `BarHeight.Pixels` | Tinggi bar untuk gambar saat ini. |

```csharp
        // Step 2: Set common visual parameters – module size and initial bar height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size (module width)
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height in pixels
```

Menjaga **ukuran piksel barcode** tetap konstan sambil mengubah tinggi memungkinkan Anda membuat **dimensi barcode khusus** yang sesuai dengan pedoman merek atau persyaratan pemindaian.

## Langkah 3: Simpan file PNG pertama (tinggi 30 px)

Sekarang tulis gambar ke disk. Metode `Save` menerima jalur file dan format gambar yang diinginkan.

```csharp
        // Step 3: Save the first barcode image (30 px height)
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder); // ensure the folder exists

        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);
```

File yang dihasilkan adalah **gambar barcode** dengan tinggi bar 30 px dan lebar modul 2 px, sempurna untuk label kompak.

## Langkah 4: **Sesuaikan tinggi barcode** untuk versi yang lebih besar

Untuk menghasilkan gambar kedua dengan ukuran visual yang berbeda, hanya properti `BarHeight.Pixels` yang perlu diubah. Ini menunjukkan betapa mudahnya **menyesuaikan tinggi barcode** tanpa membuat ulang generator.

```csharp
        // Step 4: Change the bar height to 60 px for a larger barcode
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

Mengubah tinggi sambil mempertahankan **ukuran piksel barcode** memastikan bar tetap tajam dan rasio aspek keseluruhan tetap konsisten.

## Langkah 5: Simpan file PNG kedua (tinggi 60 px)

Akhirnya, simpan versi yang lebih besar.

```csharp
        // Step 5: Save the second barcode image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

Sekarang Anda memiliki dua **dimensi barcode khusus** yang disimpan berdampingan:

- `DatabarBarHeight30Pixels.png` – tinggi bar 30 px
- `DatabarBarHeight60Pixels.png` – tinggi bar 60 px

Kedua gambar berbagi **ukuran piksel barcode** yang sama sebesar 2 px, menjamin konsistensi visual di berbagai ukuran.

## Mengapa pengaturan ini penting

- **Ukuran piksel barcode** (`XDimension`) memengaruhi keterbacaan pemindai. Lebar 2 px adalah nilai default umum yang menyeimbangkan ukuran file dan keandalan pemindaian.
- **Tinggi bar** menentukan seberapa tinggi barcode muncul pada label. Beberapa pemindai ritel memerlukan tinggi minimum; yang lain memperbolehkan bar lebih tinggi untuk alasan estetika.
- Menjaga instance generator tetap hidup sambil hanya menyesuaikan `BarHeight` mengurangi alokasi memori dan mempercepat pemrosesan batch.

## Kasus tepi dan tips praktik terbaik

| Situasi | Pendekatan yang direkomendasikan |
|---------|----------------------------------|
| **Format gambar berbeda** (JPEG, BMP) | Ubah `BarCodeImageFormat.Jpeg` atau `.Bmp` dalam pemanggilan `Save`. JPEG lebih kecil tetapi dapat menghasilkan artefak kompresi. |
| **Output resolusi tinggi** (mis., 300 DPI) | Tingkatkan `XDimension.Pixels` secara proporsional (mis., 4 px) dan sesuaikan `BarHeight.Pixels` untuk mempertahankan ukuran fisik yang sama. |
| **String data dinamis** | Bungkus pembuatan generator dalam metode yang menerima string data sebagai parameter, lalu gunakan kembali instance `barcode` yang sama untuk beberapa penyimpanan. |
| **Generasi batch thread‑safe** | Buat `BarcodeGenerator` terpisah per thread atau gunakan pool thread‑local untuk menghindari kondisi balapan. |
| **Kesalahan izin sistem file** | Pastikan `outputFolder` ada dan proses memiliki akses menulis; tangani `IOException` dengan baik. |

## Daftar sumber lengkap

Berikut adalah program lengkap yang berdiri sendiri yang dapat Anda salin, tempel, dan jalankan.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.IO;

class Program
{
    static void Main()
    {
        // Create a barcode generator – this is the core of the create barcode image workflow
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Define barcode pixel size (module width) and initial height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height

        // Prepare output folder
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder);

        // Save first image (30 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        // Adjust height for the second image
        barcode.Parameters.Barcode.BarHeight.Pixels = 60; // adjust barcode height

        // Save second image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

### Output yang diharapkan

Setelah menjalankan program, folder `YOUR_DIRECTORY` berisi dua file PNG:

- **DatabarBarHeight30Pixels.png** – barcode kompak yang cocok untuk label kecil.
- **DatabarBarHeight60Pixels.png** – versi lebih besar yang ideal untuk aplikasi dengan visibilitas tinggi.

Kedua file dapat dibuka di penampil gambar apa pun, dicetak, atau disisipkan dalam PDF.

## Kesimpulan

Anda kini tahu cara **membuat gambar barcode** dalam C# dengan **barcode generator c#**, mengontrol **ukuran piksel barcode**, **menyesuaikan tinggi barcode**, dan menghasilkan **dimensi barcode khusus** yang memenuhi persyaratan pemindaian atau merek tertentu. Contoh ini menunjukkan pola yang bersih dan dapat diulang yang dapat diskalakan untuk pemrosesan batch atau simbol yang berbeda.

### Apa yang dapat dijelajahi selanjutnya

- Ganti `EncodeTypes.DatabarOmniDirectional` dengan tipe lain seperti `EncodeTypes.Code128` atau `EncodeTypes.QR`.
- Terapkan warna latar depan/latar belakang melalui `barcode.Parameters.Barcode.ForeColor` dan `BackColor`.
- Hasilkan output SVG atau PDF untuk pencetakan berbasis vektor.
- Gabungkan beberapa barcode menjadi satu gambar menggunakan `Graphics` untuk label komposit.

Silakan bereksperimen dengan parameter, dan integrasikan pola ini ke dalam inventaris, tiket, atau sistem apa pun yang memerlukan pembuatan barcode secara programatis. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membuat gambar barcode di C# dengan tinggi yang dapat disesuaikan](/barcode/english/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/)
- [Cara menghasilkan set barcode dengan ukuran khusus dan menyimpan gambar di C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Buat gambar barcode C# dengan contoh generator barcode](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}