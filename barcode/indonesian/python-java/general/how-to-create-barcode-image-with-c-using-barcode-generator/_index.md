---
category: general
date: 2026-10-28
description: Buat gambar barcode di C# dengan cepat. Pelajari penggunaan generator
  barcode C#, cara mengatur ukuran piksel, dan cara mengubah rasio aspek untuk DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: id
lastmod: 2026-10-28
og_description: Buat gambar barcode di C# dengan Generator Barcode. Ikuti panduan
  ini untuk mengatur ukuran piksel, mengubah rasio aspek, dan menghasilkan barcode
  DataBar.
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: Buat gambar barcode di C# – panduan langkah demi langkah
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: Cara membuat gambar barcode dengan C# menggunakan Barcode Generator
url: /id/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar barcode dengan C# menggunakan Barcode Generator

Jika Anda perlu **membuat gambar barcode** dalam aplikasi .NET, panduan ini menunjukkan secara tepat caranya. Anda akan melihat contoh lengkap yang dapat dijalankan yang menggunakan pustaka Barcode Generator C# untuk menghasilkan barcode DataBar stacked omnidirectional, mengatur ukuran piksel, dan mengubah rasio aspek.

Membuat barcode secara programatik menghilangkan kebutuhan akan alat eksternal dan memungkinkan Anda menyematkan gambar langsung ke PDF, laporan, atau kontrol UI. Pada langkah‑langkah di bawah ini kami juga membahas **cara mengatur ukuran piksel** dan **cara mengubah rasio aspek**, dua kebutuhan umum ketika Anda memerlukan barcode yang tajam dan terukur dengan benar.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru terpasang  
* IDE yang kompatibel dengan C# (Visual Studio, Rider, atau VS Code)  
* Paket NuGet `BarcodeGenerator` (misalnya, `GroupDocs.Barcode` atau `Aspose.Barcode`) terpasang di proyek Anda  

Anda dapat menambahkan paket dengan perintah berikut:

```bash
dotnet add package GroupDocs.Barcode
```

> **Tip pro:** Verifikasi versi paket cocok dengan kerangka target Anda untuk menghindari ketidakcocokan runtime.

## Membuat gambar barcode dengan Barcode Generator C#

Langkah pertama adalah menginstansiasi generator dengan tipe barcode dan data yang diinginkan. Contoh di bawah ini membuat barcode **DataBar stacked omnidirectional**, yang ideal untuk skenario pemindaian ritel.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Mengapa setiap baris penting

* **Instansiasi `BarcodeGenerator`** – Konstruktor menerima simbol barcode (`EncodeTypes.DatabarStackedOmniDirectional`) dan string data mentah. Memilih simbol yang tepat memastikan pemindai dapat membaca kode.  
* **Set `XDimension.Pixels`** – Properti ini mengontrol lebar elemen bar terkecil. Nilai `2` menghasilkan gambar berbutir halus yang tetap dapat dibaca pada kebanyakan layar. Tingkatkan nilainya jika Anda membutuhkan barcode yang lebih besar untuk printer beresolusi rendah.  
* **Konfigurasi `AspectRatio`** – Keluarga DataBar mendukung beberapa rasio aspek yang memengaruhi hubungan tinggi‑lebar. Nilai `15` dan `30` umum; `15` menghasilkan barcode yang lebih pendek, sedangkan `30` menghasilkan yang lebih tinggi.  
* **Metode `Save`** – Menyimpan barcode yang dihasilkan ke file PNG. Anda dapat mengganti `BarCodeImageFormat.Png` dengan `Jpeg` atau `Bmp` jika sistem downstream Anda memerlukan format lain.

## Cara mengatur ukuran piksel untuk konteks rendering yang berbeda

Ukuran piksel menentukan kepadatan visual barcode. Jika barcode akan ditampilkan pada monitor ber‑DPI tinggi, Anda mungkin meningkatkan ukuran piksel menjadi `3` atau `4`. Sebaliknya, untuk printer termal beresolusi rendah, ukuran piksel yang lebih kecil (misalnya, `1`) mengurangi penggunaan tinta.

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**Kasus tepi:** Mengatur ukuran piksel terlalu rendah (< 1) akan memunculkan `ArgumentOutOfRangeException`. Selalu validasi nilai sebelum menetapkannya.

## Cara mengubah rasio aspek tanpa membuat ulang generator

Mengubah rasio aspek hanyalah pembaruan properti sederhana; Anda **tidak** perlu membuat ulang instance `BarcodeGenerator`. Ini menghemat memori dan meningkatkan kinerja ketika Anda membutuhkan beberapa gambar dengan bentuk berbeda.

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

Jika Anda membutuhkan lebih dari dua rasio, Anda dapat melakukan loop melalui sebuah array:

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## Output yang diharapkan

Menjalankan program akan membuat dua file PNG (atau lebih, jika Anda menggunakan loop). Buka mereka di penampil gambar apa pun; Anda akan melihat barcode DataBar yang bersih:

* **DatabarAspectRatio15.png** – barcode pendek dan lebar yang cocok untuk ruang label sempit.  
* **DatabarAspectRatio30.png** – barcode lebih tinggi yang meningkatkan keandalan pemindaian pada pemindai miring.

Kedua gambar memiliki ukuran piksel yang sama (2 px per modul) tetapi hanya berbeda pada tinggi, menunjukkan **cara mengubah rasio aspek** sambil mempertahankan parameter lain tetap.

## Kesalahan umum dan cara menghindarinya

| Gejala | Penyebab | Solusi |
|---------|----------|--------|
| Barcode terlihat buram | `XDimension.Pixels` diatur terlalu rendah untuk resolusi output | Tingkatkan ukuran piksel setidaknya menjadi `2` untuk tampilan layar, `3` untuk cetak |
| Pemindai tidak dapat membaca kode | `EncodeTypes` salah untuk format data | Verifikasi bahwa data GTIN‑14 cocok dengan simbol yang dipilih |
| `ArgumentOutOfRangeException` pada rasio aspek | Nilai rasio tidak didukung oleh pustaka (rentang valid: 15‑30) | Gunakan hanya nilai yang didokumentasikan oleh pustaka, atau tangkap pengecualian dan kembali ke nilai default |
| File tidak ditemukan setelah `Save` | Path relatif mengarah ke direktori yang tidak ada | Gunakan path absolut atau pastikan `Directory.CreateDirectory` dipanggil terlebih dahulu |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## Langkah selanjutnya – memperluas alur kerja barcode

Sekarang Anda dapat **membuat gambar barcode**, Anda mungkin ingin:

* **Menyematkan PNG ke dalam PDF** menggunakan pustaka seperti `PdfSharp` atau `iTextSharp`.  
* **Menghasilkan simbol lain** (QR, Code128, PDF417) dengan mengubah enum `EncodeTypes`.  
* **Menerapkan transformasi warna** dengan mengakses `barcode.Parameters.Barcode.Image.Color`.  
* **Menyajikan gambar melalui endpoint ASP.NET Core** untuk generasi secara langsung dalam aplikasi web.  

Setiap topik ini dibangun di atas konsep inti yang sama yang dibahas dalam tutorial ini, seperti penggunaan **barcode generator c#**, kontrol ukuran piksel, dan manipulasi rasio aspek.

## Kesimpulan

Anda sekarang tahu cara **membuat gambar barcode** di C# dengan Barcode Generator, cara mengatur ukuran piksel, cara mengubah rasio aspek, dan cara menghasilkan barcode DataBar secara efisien. Contoh lengkap yang dapat dijalankan dapat disalin ke proyek .NET mana pun, disesuaikan untuk simbol lain, dan diperluas untuk memenuhi alur kerja dunia nyata.

Silakan bereksperimen dengan nilai `XDimension` yang berbeda, rasio aspek, dan format output. Jika Anda mengalami masalah, tinjau kembali tabel “Kesalahan umum” atau konsultasikan dokumentasi resmi pustaka untuk opsi konfigurasi yang lebih mendalam. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang dibangun di atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membuat gambar barcode dan menyesuaikan rasio aspeknya di C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [Cara menghasilkan set barcode ukuran khusus dan menyimpan gambar di C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Cara menggunakan barcode generator C# untuk membuat barcode DataBar](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}