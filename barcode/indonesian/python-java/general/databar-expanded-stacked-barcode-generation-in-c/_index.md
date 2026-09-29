---
category: general
date: 2026-09-29
description: Pelajari cara membuat barcode Databar Expanded Stacked dan menghasilkan
  gambar barcode dalam C#. Panduan langkah demi langkah ini menunjukkan cara mengatur
  baris dan kolom menggunakan BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- how to create barcode
- how to set rows
- barcode generator c#
- generate barcode image
language: id
lastmod: 2026-09-29
og_description: Penjelasan tentang pembuatan barcode Databar Expanded Stacked di C#.
  Ikuti tutorial untuk membuat gambar barcode, mengatur baris, dan menyimpan file
  PNG dengan BarcodeGenerator.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode saved as a PNG file
og_title: Panduan lengkap pembuatan barcode Databar Expanded Stacked di C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create a Databar Expanded Stacked barcode and generate
    barcode image in C#. This step‑by‑step guide shows how to set rows and columns
    using BarcodeGenerator.
  headline: Databar Expanded Stacked barcode generation in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Pembuatan barcode Databar Expanded Stacked dalam C#
url: /id/python-java/general/databar-expanded-stacked-barcode-generation-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generasi barcode Databar Expanded Stacked dalam C#

Jika Anda perlu menghasilkan **Databar Expanded Stacked** barcode dalam C#, panduan ini menunjukkan secara tepat **cara membuat barcode** dengan gambar baris dan kolom yang dapat disesuaikan. Anda akan melihat **cara mengatur baris**, cara mengatur kolom, dan **cara menghasilkan file gambar barcode** menggunakan kelas Aspose.BarCode `BarcodeGenerator`.

Dalam tutorial ini Anda akan:

* Menginstal paket NuGet yang diperlukan.
* Menginisialisasi `BarcodeGenerator` untuk simbol Databar Expanded Stacked.
* Mengonfigurasi jumlah kolom dan baris.
* Menyimpan file PNG yang dihasilkan.
* Memahami jebakan umum seperti lisensi yang hilang atau jalur gambar yang tidak tepat.

Prasyarat satu-satunya adalah .NET SDK terbaru (≥ .NET 6) dan IDE seperti Visual Studio 2022. Tidak diperlukan layanan eksternal.

## Instal dan konfigurasi pustaka BarcodeGenerator C# library

Sebelum menulis kode apa pun, tambahkan paket Aspose.BarCode ke proyek Anda:

```bash
dotnet add package Aspose.BarCode
```

Jika Anda menggunakan Visual Studio, Anda juga dapat menginstalnya melalui **NuGet Package Manager** (cari *Aspose.BarCode*). Setelah paket dipulihkan, Anda dapat mulai menulis kode.

> **Pro tip:** Versi evaluasi gratis menambahkan watermark kecil pada barcode yang dihasilkan. Untuk penggunaan produksi, dapatkan file lisensi dan panggil `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` sebelum membuat objek barcode apa pun.

## Hasilkan gambar barcode Databar Expanded Stacked

Buat aplikasi konsol baru (atau integrasikan kode ke dalam proyek C# apa pun) dan tambahkan pernyataan `using` berikut:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Sekarang tulis program lengkapnya. Kode ini mengikuti langkah‑langkah tepat dari contoh asli dan menambahkan komentar penjelas.

```csharp
// Program.cs
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // --------------------------------------------------------------------
        // Step 1: Create a barcode generator for Databar Expanded Stacked
        // --------------------------------------------------------------------
        // The EncodeTypes enum tells the generator which symbology to use.
        var databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 2: Set the number of columns (the default is 1)
        // --------------------------------------------------------------------
        // Columns control the horizontal density of the barcode.
        databarGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // --------------------------------------------------------------------
        // Step 3: Save the barcode image that uses 4 columns
        // --------------------------------------------------------------------
        // BarCodeImageFormat.Png creates a lossless PNG file.
        databarGenerator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // --------------------------------------------------------------------
        // Step 4: Re‑initialize the generator for the same barcode type
        // --------------------------------------------------------------------
        // Re‑creating the object ensures that row settings start from defaults.
        databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 5: Set the number of rows (the default is 1)
        // --------------------------------------------------------------------
        // Rows affect the vertical stacking of the barcode modules.
        databarGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // --------------------------------------------------------------------
        // Step 6: Save the barcode image that uses 3 rows
        // --------------------------------------------------------------------
        databarGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### Mengapa setiap langkah penting

* **Step 1** membuat `BarcodeGenerator` yang terikat pada simbol *Databar Expanded Stacked*, yang diperlukan untuk pemindaian ritel yang kompatibel dengan GS1.  
* **Step 2** mendemonstrasikan **cara mengatur baris** secara tidak langsung dengan terlebih dahulu menyesuaikan kolom—ini menunjukkan bahwa pengaturan kolom dan baris bersifat independen.  
* **Step 3** menyimpan gambar, memungkinkan Anda memverifikasi dampak visual dari jumlah kolom.  
* **Step 4** menginisialisasi ulang generator sehingga konfigurasi baris tidak mewarisi nilai kolom yang sebelumnya diatur, sebuah sumber kebingungan yang umum.  
* **Step 5** secara eksplisit menunjukkan **cara mengatur baris**, yang menjadi fokus utama kata kunci sekunder.  
* **Step 6** menyimpan gambar kedua, memberi Anda perbandingan berdampingan antara kepadatan berbasis kolom vs. baris.  

Menjalankan program menghasilkan dua file PNG di direktori output:

```
DatabarCols4.png   // 4 columns, default row count (1)
DatabarRows3.png   // 3 rows, default column count (1)
```

Buka salah satu file dengan penampil gambar untuk memastikan barcode ditampilkan dengan benar.

## Variasi umum dan kasus tepi

| Skenario | Apa yang diubah | Alasan |
|----------|----------------|--------|
| **Payload data berbeda** | Ganti argumen kedua `BarcodeGenerator` dengan string Anda sendiri (mis., `"123456789012"`). | Barcode mengkodekan teks yang diberikan; pastikan sesuai dengan aturan GS1 untuk Databar. |
| **Format gambar lain** | Gunakan `BarCodeImageFormat.Jpeg` atau `BarCodeImageFormat.Bmp`. | Pilih format yang cocok dengan alur pemrosesan downstream Anda. |
| **Resolusi lebih tinggi** | Panggil `databarGenerator.Save("file.png", BarCodeImageFormat.Png, 300);` dimana argumen terakhir adalah DPI. | Meningkatkan keterbacaan saat mencetak label berukuran besar. |
| **Penanganan lisensi** | Tambahkan potongan kode `License` sebelum pembuatan generator apa pun. | Menghapus watermark evaluasi dan membuka semua fungsi. |

## Tips untuk generasi barcode yang andal

* **Validasi string input** – Databar Expanded Stacked mengharapkan data numerik hingga 70 karakter. Menyertakan karakter non‑numerik dapat menyebabkan pengecualian.  
* **Periksa jalur file** – Gunakan `Path.Combine(Environment.CurrentDirectory, "output.png")` untuk menghindari direktori hard‑coded yang mungkin tidak ada di mesin target.  
* **Dispose objek** – `BarcodeGenerator` mengimplementasikan `IDisposable`. Bungkus dalam blok `using` jika Anda menghasilkan banyak barcode dalam loop untuk membebaskan sumber daya native dengan cepat.  

```csharp
using (var generator = new BarcodeGenerator(...))
{
    // configure and save
}
```

## Kesimpulan

Anda kini tahu **cara membuat Databar Expanded Stacked barcode** dan **cara mengatur baris** (serta kolom) menggunakan API **barcode generator C#**, serta dapat **menghasilkan file gambar barcode** dalam format PNG. Dengan mengikuti contoh lengkap di atas, Anda dapat mengintegrasikan barcode Databar ke dalam sistem inventaris, aplikasi point‑of‑sale, atau solusi .NET apa pun yang memerlukan barcode GS1 berkapasitas tinggi.

**Langkah selanjutnya**

* Bereksperimen dengan simbol lain seperti `EncodeTypes.DatabarExpanded` atau `EncodeTypes.QR`.  
* Jelajahi kelas `BarcodeReader` untuk memverifikasi bahwa gambar yang Anda hasilkan dapat dipindai.  
* Gabungkan generasi barcode dengan pembuatan PDF (mis., menggunakan `Aspose.PDF`) untuk menghasilkan label yang dapat dicetak.  

Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to set columns for a Databar Expanded Stacked barcode – complete C# guide](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [How to change barcode size in C# with DataBar Stacked](/barcode/english/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/)
- [Databar expanded stacked: generate barcode image in C#](/barcode/english/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}