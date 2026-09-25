---
category: general
date: 2026-08-22
description: Cara mengubah ukuran barcode di C# menggunakan generator DataBar Stacked
  Omni‑Directional. Pelajari cara mengatur dimensi X dan rasio aspek untuk output
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: id
lastmod: 2026-08-22
og_description: Cara mengubah ukuran barcode di C# dengan generator DataBar Stacked
  Omni‑Directional. Ikuti panduan langkah demi langkah untuk menyesuaikan dimensi
  X dan rasio aspek.
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: Cara mengubah ukuran barcode di C# – panduan lengkap
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara mengubah ukuran barcode di C# dengan DataBar Stacked
url: /id/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengubah ukuran barcode di C# dengan DataBar Stacked

Jika Anda perlu **cara mengubah ukuran barcode** dalam aplikasi .NET, panduan ini menunjukkan langkah‑langkah tepat menggunakan generator barcode DataBar Stacked Omni‑Directional. Anda akan melihat cara mengontrol dimensi X dalam piksel, menyesuaikan rasio aspek barcode, dan menyimpan hasilnya sebagai file PNG.

Mengubah ukuran barcode sering diperlukan ketika ruang label yang dicetak terbatas atau ketika gambar dengan resolusi lebih tinggi dibutuhkan untuk saluran digital. Tutorial ini mencakup semua yang Anda perlukan, mulai dari inisialisasi generator hingga menghasilkan dua gambar dengan ukuran berbeda.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Referensi ke paket NuGet **Aspose.BarCode for .NET**  
* Familiaritas dasar dengan sintaks C#  

Tidak ada konfigurasi tambahan yang diperlukan; kode dapat dijalankan di Windows, Linux, atau macOS.

## Cara mengubah ukuran barcode di C# – langkah demi langkah

Bagian‑bagian berikut memecah proses menjadi langkah‑langkah terpisah yang dapat digunakan kembali. Setiap langkah menjelaskan **mengapa** kode tersebut diperlukan, bukan hanya **apa** yang dilakukannya.

### Langkah 1: Buat generator barcode DataBar Stacked Omni‑Directional

Objek generator menyimpan semua pengaturan barcode. Dengan memberikan `EncodeTypes.DatabarStackedOmniDirectional` dan data contoh, Anda membuat barcode yang valid siap untuk penyesuaian lebih lanjut.

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Mengapa ini penting* – Kelas **C# barcode generator** mengenkapsulasi algoritma enkoding. Memulai dengan generator yang valid memastikan bahwa perubahan ukuran selanjutnya memengaruhi tipe barcode yang tepat.

### Langkah 2: Atur ukuran modul dasar (dimensi X) dalam piksel

Dimensi X menentukan lebar satu modul barcode. Menyesuaikannya mengubah lebar dan tinggi secara proporsional.

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Mengapa ini penting* – Dimensi X yang lebih besar menghasilkan barcode yang lebih besar, berguna untuk printer beresolusi rendah. Sebaliknya, nilai yang lebih kecil menghasilkan barcode kompak yang cocok untuk label kecil.

### Langkah 3: Ubah rasio aspek barcode menjadi 15 dan simpan gambar

**Rasio aspek barcode** mengontrol hubungan tinggi‑ke‑lebar. Rasio 15 menghasilkan barcode yang relatif tinggi.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*Mengapa ini penting* – Berbagai perangkat pemindai memiliki persyaratan rasio‑aspek optimal. Menetapkan rasio menjadi 15 memperlihatkan cara **cara mengubah ukuran barcode** dengan memodifikasi tinggi sementara lebar ditentukan oleh dimensi X.

#### Output yang diharapkan

File `DatabarAspectRatio15.png` menampilkan barcode DataBar Stacked Omni‑Directional yang lebih tinggi daripada default. Lebar barcode mencerminkan dimensi X 2 piksel, dan tinggi mengikuti rasio 15.

### Langkah 4: Ubah rasio aspek barcode menjadi 30 dan simpan gambar baru

Meningkatkan rasio aspek menjadi 30 membuat barcode semakin tinggi, memperlihatkan fleksibilitas penyesuaian ukuran.

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*Mengapa ini penting* – Dengan mengganti nilai **rasio aspek barcode**, Anda langsung melihat cara **cara mengubah ukuran barcode** tanpa harus membuat ulang generator. Ini menghemat waktu pemrosesan pada skenario batch.

#### Output yang diharapkan

File `DatabarAspectRatio30.png` jelas lebih tinggi daripada gambar sebelumnya, mengonfirmasi bahwa rasio aspek secara langsung memengaruhi tinggi barcode.

### Langkah 5: Verifikasi gambar yang dihasilkan

Buka file PNG di penampil gambar apa pun. Anda harus melihat dua barcode dengan lebar identik (dikendalikan oleh dimensi X) tetapi tinggi berbeda (dikendalikan oleh rasio aspek). Jika gambar tampak buram, tingkatkan piksel dimensi X; jika terlalu tinggi, turunkan rasio aspek.

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*Mengapa ini penting* – Verifikasi programatik memastikan bahwa perubahan ukuran telah diterapkan dengan benar, yang penting untuk pipeline build otomatis.

## Variasi umum dan kasus tepi

| Situasi | Penyesuaian | Alasan |
|-----------|------------|--------|
| **Label sangat kecil** | Set `XDimension.Pixels = 1` dan `AspectRatio = 10` | Mengurangi jejak keseluruhan sambil mempertahankan keterbacaan |
| **Cetak beresolusi tinggi** | Set `XDimension.Pixels = 4` dan `AspectRatio = 20` | Meningkatkan kepadatan piksel untuk output yang tajam |
| **Format gambar berbeda** | Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg` | Berguna ketika dukungan PNG terbatas |
| **Data dinamis** | Berikan string variabel ke konstruktor `BarcodeGenerator` | Menghasilkan barcode untuk setiap produk secara otomatis |

Ketika Anda perlu menghasilkan banyak barcode dengan ukuran bervariasi, bungkus langkah‑langkah tersebut dalam sebuah metode:

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Memanggil `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` menghasilkan barcode dengan ukuran khusus dalam satu baris kode.

## Tips pro untuk perubahan ukuran yang andal

* **Selalu set dimensi X sebelum rasio aspek.** Mengubah rasio aspek terlebih dahulu dapat menyebabkan skala tak terduga jika dimensi X menggunakan nilai default yang tidak ideal.  
* **Gunakan folder output yang konsisten.** Hard‑coding `"YOUR_DIRECTORY"` cocok untuk demo, tetapi di produksi lebih baik gunakan `Path.Combine(Environment.CurrentDirectory, "Barcodes")`.  
* **Validasi ukuran gambar yang dihasilkan.** Perubahan kecil pada dimensi X mungkin tidak terlihat di layar; memeriksa dimensi piksel menjamin perubahan telah terjadi.  

## Kesimpulan

Anda kini mengetahui **cara mengubah ukuran barcode** di C# menggunakan generator barcode DataBar Stacked Omni‑Directional. Dengan menyesuaikan **piksel dimensi X** dan **rasio aspek barcode**, Anda dapat menghasilkan gambar PNG yang cocok untuk ukuran label atau kebutuhan resolusi apa pun. Contoh lengkap yang dapat dijalankan di atas memperlihatkan alur kerja penuh mulai dari pembuatan generator hingga verifikasi ukuran.

### Apa yang dapat Anda jelajahi selanjutnya

* **Warna khusus** – coba `barcodeGenerator.Parameters.Barcode.ForeColor` dan `BackColor` untuk menyesuaikan dengan panduan merek.  
* **Tipe barcode lain** – ganti `EncodeTypes.DatabarStackedOmniDirectional` dengan `EncodeTypes.QR` atau `EncodeTypes.Code128` untuk melihat bagaimana parameter ukuran berbeda antar simbol.  
* **Pemrosesan batch** – gabungkan metode `GenerateDatabar` dengan impor CSV untuk membuat ribuan barcode secara otomatis.

Silakan sesuaikan potongan kode dengan arsitektur proyek Anda, dan biarkan penyesuaian ukuran barcode meningkatkan keandalan pemindaian serta desain visual Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}